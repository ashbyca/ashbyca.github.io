---
title:  "Lab Architecture"
date:   2015-01-04 15:04:23
categories: [lab]
tags: [architecture]
---
If you have been following along, you have seen a log of [posts](https://ashbyca.github.io/categories/#lab) on various tools, tactical procedures, and systems that I have either built, tested, or recommend.  Today I wanted to put some additional context around that and outline my lab architecture for two distinct purposes:

* Malware Research
* Attack Tooling and Testing

My entire lab consists of a collection of virtual guest systems that are isolated from my host and have a shared storage volume for data interchange (if necessary).  For the host machine, I’m using OSX with a couple of utilities installed through Homebrew.  

#### Malware Research Lab

![Image of Malware Lab](https://user-images.githubusercontent.com/6200040/38623904-d537d4b4-3d74-11e8-9716-0b14047387f8.png)

As shown above, I have a single victim machine that I can submit samples to from my cuckoo platform.  Cuckoo will auto execute the payload and collect a vast amount of artifacts and bring that back and normalize.  During the process a memory dump is collected, and I use volatility and Yara to provide further analysis of suspicious artifacts.  Additionally I have a couple of standalone apps/scripts on a lightweight utilities server.  These includes:

1. jsDetox
2. DNS
3. Proxy
4. FTP

Currently this is a pretty static setup and much isn’t changed, however I am looking at introducing an IDS and Honeypot possibly.

#### Attack Tooling and Testing

My current penetration testing lab is the exact opposite, it’s a dynamic lab.  I’m always adding new virtual (CTF) capture the flag) machines.  

![Image of Attack Lab](https://user-images.githubusercontent.com/6200040/38623930-df82681c-3d74-11e8-8563-c1047f192aba.png)

I also have the same victim machine in this lab, which is just a copy for testing windows exploits, as well as a basic LAMP server.  Kali is my main image for keeping my skill sharp on the various tools available.  I do however have a couple of utilities on my OSX device that I use, but not that many.


A lot of good articles can be found online for building these two skill sets, I included a  good list in the reference section below and will continue to update these when new articles are found.

References:<br>
[Awesome Hacking Tools](https://github.com/m4ll0k/Awesome-Hacking-Tools)<br>
[Debugging Complex Malware](https://www.fireeye.com/blog/threat-research/2018/01/debugging-complex-malware-that-executes-code-on-the-heap.html)<br>
[Penetration Testers’ Guide to Windows 10 Privacy & Security](https://www.linkedin.com/pulse/penetration-testers-guide-windows-10-privacy-security-andrew-douma/)<br>
[Metasploit Walkthrough](http://resources.infosecinstitute.com/metasploitable-1-walkthrough/)<br>
[Windows Privilege Escalation Guide](https://www.sploitspren.com/2018-01-26-Windows-Privilege-Escalation-Guide/)<br>
[Building an Analysis Toolkit](https://swannysec.net/2015/10/10/building-an-analysis-toolkit.html)<br>
[Expiring Payloads](https://www.gironsec.com/blog/2018/01/expiring-payloads-in-the-metasploit-framework/)<br>
[Understanding CSRF](http://www.hackingarticles.in/understanding-csrf-vulnerability-beginner-guide/)<br>
