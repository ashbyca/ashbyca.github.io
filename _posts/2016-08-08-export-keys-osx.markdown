---
title:  "Exporting Private Keys - OSX"
date:   2016-08-08 15:04:23
categories: [osx]
tags: [backup, sysadmin, privacy]
---
In this post I’m going to explain how to successfully export private/public key pairs from OS X Keychain to a new computer. 
As your aware, under normal export procedures, the private key isn’t exported — just the public.  This is true for
certificates, specifically S/MIME.

I found out the hard way, having received a new machine and resorted to my backup to find that the certification couldn’t be
imported/used as the private key was missing.  

One the machine where you have the key pair, open a Terminal session followed by typing the command:

```Bash
$ sudo /Applications/Utilities/Keychain\ Access.app/Contents/MacOS/Keychain\ Access
```

This will open the Keychain application as root.  Once the application is opened, find your value that you wish to export and
right-click and select export.

Add a password if necessary.
