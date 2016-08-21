---
layout: post
title: "Mount Android folder locally"
date: 2016-08-20
---

As a developer you're familiar with `adb` command, and sometimes used it to create/change/delete some file of your application. One of it could be database file. 
Read this recepie and you won't have to do all those adb push and pulls. Furthermore, you'll directly manipulate with database file, expore Android system with your favorite file manager, and forget about missery of MTP protocol for copying photos from phone.

{% gist b957d077681eb73571c4a1b27787b1ba shoro.sh %}
