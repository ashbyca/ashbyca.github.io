---
title:  "Recon Techniques"
date:   2015-02-12 15:04:23
categories: [$dayjob]
tags: [threat intelligence]
---
[Google Dorking](http://www.businessinsider.com/term-of-the-day-google-dorking-2014-8) is a powerful technique used to silently obtain information on various targets to assist in both research and furthering attack.
Some of my favorite operators include:

* site
> The site operator instructs Google to restrict a search to a specific web site or domain. The web site to search must be supplied after the colon. 

* filetype
> The filetype operator instructs Google to search only within the text of a particular type of file. The file type to search must be supplied after the colon. Don't include a period before the file extension. 

* link
> The link operator instructs Google to search within hyperlinks for a search term. 

* cache
> The cache operator displays the version of a web page as it appeared when Google crawled the site. The URL of the site must be supplied after the colon. 

* intitle or allintitle
> The intitle, allintitle operator instructs Google to search for a term within the title of a document. 

* inurl or allinurl
> The inurl, allinurl operator instructs Google to search only within the URL (web address) of a document. The search term must follow the colon. 

---
A quick example of how you would construct these in the google search bar are show below.  Please substitute the [website] value with an actual website.

```site:[website] intitle:index.of .bash_history```

> .bash_history file contains what a user typed at a shell command prompt. This file contains commands and usernames and other information that may have been typed in.  .bash_history can also be replaced with .profile, .login, .logout files, .sh_history, etc. 

```site:[website] inurl:admin inurl:userlist```

> This reveals userlists of administrative importance.

```site:[website] inurl:"/root/etc/passwd" intext:"home/*:"
site:[website] intext:"root:x:0:0:root:/root:/bin/bash" inurl:*=/etc/passwd
intitle:index.of.password
```

> These techniques above would reveal any present passwd files 

Additional References:
1. https://www.exploit-db.com/google-hacking-database/
2. https://en.wikipedia.org/wiki/Google_hacking
