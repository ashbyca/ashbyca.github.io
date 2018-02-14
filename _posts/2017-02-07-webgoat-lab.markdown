---
title:  "WebGoat Lab"
date:   2017-09-07 15:04:23
categories: [osx]
tags: [backup, privacy]
---
In this post I'm going to demonstrate how to create a new virtual machine which will be used to test your application security skills.  At a high-level this will consist of the following compontents:

*Virtualization Software - VMWare or VirtualBox
*CentOS operating system
*WebGoat application with dependiencies

Go lets get started....

Download *nix virtual machine
http://sourceforge.net/projects/virtualboximage/files/CentOS/5.7/CentOS-5.7-i386.7z/download
 
***Machine settings work best with Bridge Networking & DHCP Enabled***
 
Upgrade machine to latest versions
$ yum update
$ yum upgrade
 
Change Hostname and keyboard layouts
$ /etc/sysconfig/keyboard
$ /etc/sysconfig/network
 
# hostname <insert hostname>
 
# reboot
 
Install Java
# yum install java7
 
Download and install Tomcat 7
# wget http://apache.spinellicreations.com/tomcat/tomcat-7/v7.0.47/bin/apache-tomcat-7.0.47.tar.gz
# tar -zcvf apache-tomcat-7.0.47.tar.gz
 
Download the WebgGoat files
# wget https://webgoat.googlecode.com/files/WebGoat-5.4.war
# wget https://webgoat.googlecode.com/files/README-5.4.txt
 
Copy the previously download WebGoat05.4.war to your tomcat webapps directory
# cp WebGoat-5.4 apache-tomcat-7.0.47/webapps/WebGoat.war
 
Modify the tomcat-users.xml and insert WebGoat users and roles as displayed below:
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
 
Start your Tomcat instance
# apache-tomcat-7.0.47/bin/startup.sh
 
On your local machine browse to http://localhost:8080/WebGoat/attack
