---
title:  “FTP Script"
date:   2013-03-07 15:04:23
categories: [ashby]
tags: [scripts]
---
Below is a link to a quick script I created for automating local ftp transfers.  I wouldn’t recommend this be used across the internet or from/to networks that aren’t trusted.  As you should be aware, FTP isn’t a secure protocol and all information is sent in clear-text across the wire.  If you in need of a local script, you can give the one below a try, it’s a basic script that uses simple values to pass to the ftp daemon, downloading files requested without any user interaction.
  
Prior to use, modifications will need to be made and include:

* Change the host value<br>
* Change the user value<br>
* Change the passwd value<br>
* Change the file value (this is the local file to upload)
* Change the remotefile value (this is the remote file to be uploaded)
 

After save the file, execute the script and when completed you will have a txt file that contains complete results.  If you receive errors they will be displayed in the command window.

You can download the script [here](https://ashby.keybase.pub/Blog/Scripts/ftptransfer.sh).
