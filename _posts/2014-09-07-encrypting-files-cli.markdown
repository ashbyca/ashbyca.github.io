---
title:  "Encrypting Files OSX - CLI"
date:   2014-09-07 15:04:23
categories: [osx]
tags: [privacy]
---
MacOS has a great built-in compression utility but unfortunantely the UI options don't include any encryption options.  In 
order to take advantage of this feature you will need to venture down to the CLI.

For reference, I have found the best options to be "ejr".
* "e" indicates encryption
* "j" removes folder hierarchy
* "r" executes recursively

This will be entered in the terminal shown below:
* zip -ejr [name] [path to folder]

An exmaples would be  ```zip -ejr archive.zip ~/Documents```

With the above example, you are asking the application zip to create a new file named "archive,zip" of all data contained in
your "Documents" folder, and finally remove all subfolders, and encrypt with a password.
