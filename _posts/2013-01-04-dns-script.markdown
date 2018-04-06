---
title:  "DNS Script"
date:   2013-01-04 15:04:23
categories: [ashby]
tags: [scripts]
---
Below is a link to a quick script I created while doing some research on various endpoint and needed DNS information.  This script basically performs large lookups and writes all the information to a results file.  It’s a basic but works great, it’s intended to work on any Windows computer.

Prior to use, modifications will need to be made and include:

* Change the <dir> value with the absolute path where the script is located<br>
* Change ns1 and ns2 to include your DNS servers<br>
* Change the endpoint1 and endpoint2 values to include the hostnames you wish to perform a lookup against<br>

After save the file, execute the script and when completed you will have a txt file that contains complete results.  If you receive errors they will be displayed in the command window.

You can download the script [here](https://ashby.keybase.pub/Blog/Scripts/dnslookups.bat).
