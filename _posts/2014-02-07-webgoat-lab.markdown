---
title:  "WebGoat Lab"
date:   2014-02-07 15:04:23
categories: [lab]
tags: [appsec, pentesting, vm]
---
In this post I'm going to demonstrate how to create a new virtual machine which will be used for assessing your web application security skills.  At a high-level this will consist of the following compontents:

* Virtualization Software - [VMWare](https://www.vmware.com) or [VirtualBox.](https://www.virtualbox.org)
* [CentOS](https://www.centos.org) guest operating system
* [WebGoat](https://www.owasp.org/index.php/Category:OWASP_WebGoat_Project) application with dependiencies

Go lets get started....

1. Download [CentOS virtual machine](http://sourceforge.net/projects/virtualboximage/files/CentOS/5.7/CentOS-5.7-i386.7z/download)
 
    * All commands are executed as <b>root</b> untill otherwise noted.
    * Machine settings work best with Bridge Networking & DHCP Enabled.
 
2. Upgrade operating system with latest software patches and operating system.

```Bash
# yum update
# yum upgrade
```

3. Change Hostname and keyboard layouts

```Bash
# /etc/sysconfig/keyboard
# /etc/sysconfig/network
```

```Bash
# hostname <insert hostname> 
# reboot
```

4. Install Java

```Bash
# yum install java7
```

5. Download and install Tomcat 7

```Bash
# wget http://apache.spinellicreations.com/tomcat/tomcat-7/v7.0.47/bin/apache-tomcat-7.0.47.tar.gz
# tar -zcvf apache-tomcat-7.0.47.tar.gz
```

6. Download the WebgGoat files

```Bash
# wget https://webgoat.googlecode.com/files/WebGoat-5.4.war
# wget https://webgoat.googlecode.com/files/README-5.4.txt
```

7. Copy the previously download WebGoat05.4.war to your tomcat webapps directory

```Bash
# cp WebGoat-5.4 apache-tomcat-7.0.47/webapps/WebGoat.war
```

8. Modify the tomcat-users.xml and insert WebGoat users and roles as displayed below:

```Bash
# vi apache-tomcat-7.0.47/conf/tomcat-users.xml
 
<tomcat-users>
      <role rolename="webgoat_basic"/>
      <role rolename="webgoat_admin"/>
      <role rolename="webgoat_user"/>
      <role rolename="tomcat"/>
      <user password="webgoat" roles="webgoat_admin" username="webgoat"/>
      <user password="basic" roles="webgoat_user,webgoat_basic" username="basic"/>
      <user password="tomcat" roles="tomcat" username="tomcat"/>
      <user password="guest" roles="webgoat_user" username="guest"/>
    </tomcat-users>
``` 
9. Start your Tomcat instance

```Bash
# apache-tomcat-7.0.47/bin/startup.sh
``` 

On your local machine, open your preferred browser and point to http://localhost:8080/WebGoat/attack
