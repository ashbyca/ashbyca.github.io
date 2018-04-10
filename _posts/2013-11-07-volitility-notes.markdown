---
title:  "Volitility Notes"
date:   2013-11-07 15:04:23
categories: [lab]
tags: [forensics]
---
Below are some notes on using Volitility I have for researching/discovering malware in memory.  This most likely won't apply to anyone other then me for at the moment.  I'm currently in the process of automating most of these tasks when investigations are needed.

```Registry
find operating system: imageinfo
display process listings: pslist
display the process tree: pstree
display actively running processes: psxview
display active network connections: connections- xp/2003 only
display previously closed connections: connscan - xp/2003 only
display previous network connections: netscan - 7/vista/2008
dump potentially malicious processes: malfind --dump-dir "directory" | to submit processes to virustotal run a hash
determine file handles still in memory: filescan
display registry key values: printkey -K "key file"
display available mutexes: mutantscan
``` 
 
Registry Keys to investigate
```Registry
run = printkey -K "Software\Microsoft\Windows\Currentversion\Run"
internet zones = printkey -K "Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\0"

printkey -K "Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\1"
"Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\2"
"Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\3"
```

I started working on a srcript to automate these finding, if your interested in testing or reviewing the code please find it [here](https://ashby.keybase.pub/Blog/Scripts/vol_analysis.sh).
