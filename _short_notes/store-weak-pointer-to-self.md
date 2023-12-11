---
layout: post
title:  "Store weak pointer to self"
description: "weak pointer to self: c++ smart pointer"
categories: ["c++"]
author: "Sai Kiran"
---

Was going through https://itecnote.com/tecnote/c-store-weak-pointer-to-self/ and then came to know that [we can have a weak pointer to self](https://en.cppreference.com/w/cpp/memory/enable_shared_from_this).
This technique can be used to make sure everyone is using the same object, kind of like a singleton.
