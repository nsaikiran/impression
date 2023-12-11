---
layout: post
title:  "Upgrade MySQL from 5.7.38 to 8.0.34"
description: "MySQL upgrade experience"
categories: ["release-technique"]
date: 11-12-2023
author: "Sai Kiran"
---
We use Amazon MySQL RDS for one of our services. When we wanted to purchase reserved instances to reduce the expenses. We needed to upgrade the MySQL RDS instance type and MySQL engine version.

To upgrade MySQL engine version, I needed to go through the MySQL documentation about migration, features that are removed, features that are deprecated etc. and create a plan of upgrade.

[We needed to do some schema related changes](https://planetscale.com/blog/upgrading-to-mysql-8) like character set, collation and user's authentication plugin.
We needed to move to utf8mb4 character set for all tables. And, we chose utf8mb4_general_ci as the collation, because we don't use sorting or compare functionality of unicode characters (we may store some unicode characters in some fields only when the user's input has unicode characters). I needed to read about character set, collation, how the ALTER table command works. I've inspected our data to check whether we use unicode characters or not.

For execution, we wanted to use Amazon RDS blue-green deployments. 
This method creates a clone of the database and configures it as a read-replica, with this, we can create our new MySQL server with desirable configuration (like upgraded instance type, upgraded mysql engine) and do the required changes to schema, while data-wise, both old and new instances are in sync. As we do changes to the schema, [we needed to do the "replication compatible changes" or tell how mysql can do the replication if it can't proceed with replication.](https://dev.mysql.com/doc/mysql-replication-excerpt/5.7/en/replication-features-different-data-types.html)
In our case, the as the column type of source DB is different from that of the new database (old database has utf8mb3 column type and for new one, we've changed it to utf8mb4), hence, we needed configure [sysvar_slave_type_conversions](https://dev.mysql.com/doc/refman/8.0/en/replication-options-replica.html#sysvar_slave_type_conversions) system variable with [ALL_NO_LOSSY](https://dev.mysql.com/doc/mysql-replication-excerpt/5.7/en/replication-features-different-data-types.html) value. This setting lets us proceed with replication without data loss.

Learnings:
1. Character set, collation of columns of CHAR/VARCHAR type and how to pick relevant charset and collation for our use case.
2. Amazon RDS blue-green deployments.
3. Parameters groups of AWS (system variables of MySQL). For ex: read_only=true, if instance is read-only.
4. Read replica vs Multi-AZ setup (Multi-AZ instance will have synchronous replication and can't be accessed while primary zone is active, whereas read-replica will be asynchronously replicated).
5. The MySQL replication types and replication type conversions.
6. Planning: Prepare the green instance ready (take a couple of days buffer if needed to). Having buffer window will help us stick to the plan from long-running queries, unexpected issues with replication etc.
