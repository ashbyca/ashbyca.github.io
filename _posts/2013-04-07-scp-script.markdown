---
title:  "SCP Script"
date:   2013-04-07 15:04:23
categories: [ashby]
tags: [scripts]
---
Here is another script I created for automating scp downloads.  While this script uses expect to securely transfer the password to scp, you have to take precautions to safeguard the script itself as it contains the password.  I wouldn’t use this script across the internet, but for LAN transfers using scp it works.
  
Prior to use, modifications will need to be made and include:

* Change the user value<br>
* Change the server value<br>
* Change the remote dir<br>
* Change the local directory<br>
* Change the password value<br>
 

After save the file and execute the script.  All output will be shown in the command window. If you receive errors they will be displayed in the command window.

You can download the script [here](https://ashby.keybase.pub/Blog/Scripts/scptransfer.sh).
