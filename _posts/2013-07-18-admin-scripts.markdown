---
title:  "Admin Scripts"
date:   2013-06-17 15:04:23
categories: [automation]
tags: [scripts]
---
Lately I've been buidling a bunch of systems and in an effort to streamline and standardize configurations I've been scripting some of this activity.  Below are two scripts to install a FW using iptables and a dynamic motd.

All scripts have been tested to work with CentOS v5/6.

* [iptables.sh](https://ashby.keybase.pub/Blog/Scripts/iptables.sh) - script to install and setup IPTables and Fail2ban.  After execution only ports 22/80/443 are accessible.
  
* [motd.sh](https://ashby.keybase.pub/Blog/Scripts/motd.sh) - script for CentOS that creates a simple motd output.

I'll post more to this page as they become available.
