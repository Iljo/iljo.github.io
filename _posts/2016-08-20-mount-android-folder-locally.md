---
layout: post
title: "Mount Android folder locally"
date: 2016-08-20
---

When using MTP protocol, you don't have access to whole Android file system. So as a developer, you used `adb` command to create/change/delete some files of your application. One of it could be database file. 
Read this recepie and you won't have to do all those adb push and pulls. Furthermore, you'll directly manipulate with database file, explore Android system with your favorite file manager, and maybe use it instead MTP protocol for copying stuff from phone.

> First, try this with Android emulator. Also, be aware that on nonrooted devices you can't access whole filesystem.

For there are reasons because you don't want to root one device, _e.g._ it's someone elses phone, loosing warranty, or you don't have time for it. There is a workaround to access your `sqlite` database like described here.
But, it's only safe for development enviroment, don't use it in production. Basicly it's about making your application store database file in accessable folder for everyone, like cache folder. I'll write about it in another post.

So, to mount Android folder locally, here are steps to be done:

1. Run ssh server on device
2. Mount remote folder locally
3. Make it accessable whithout network

Every step has it's chapter, whitch explains it in more detail. You can live without last step, if don't need access when not connected to network. 
In last parts of this blog post, you'll see script that does this things for you, and a little retrospection from using it.












{% gist b957d077681eb73571c4a1b27787b1ba shoro.sh %}

There are other options for browsing sqlite database of your Android app. 
Like adb to phone, then use sqlite3 command line client. But then you don't have all the confort of using gui client. 
Or use stetho in your app. Which then again slows your app, and currently, lacks of descent sql editor. And if you have many columns in table, there is that annoying manual resizing of columns, so that you can see their values.

At the time of writing this post, firebase database is stored in sqlite3 database on android, so you can see how it look now, and change it in real time.


{::comment}
vdfslvj
{:/comment}
