---
title:  "Machinae - XForce"
date:   2017-12-15 15:04:23
categories: [$dayjob]
tags: [threat intelligence]
---
Recently I've been playing with a new tool from HuricaneLabs named ["Machinae"](https://github.com/HurricaneLabs/machinae), which is a tool for collecting intelligence from public sites/feeds about various security-related pieces of data: IP addresses, domain names, URLs, email addresses, file hashes and SSL fingerprints. This replaced my daily driver [Automator](http://www.tekdefense.com/automater/) for obtaining context on particular subjects.

I started researching new tools due to the hassle of introducing new repositories of data to lookup against.  Integrating new sources is a snap in Machinae, at most you only need a API key and URL.  If your an [IBM XForce](https://exchange.xforce.ibmcloud.com) user and would like to add this as an additional source the code is below:

```
xforce-malware:
    name: IBM XForce Malware Report
    default: False
    otypes:
        - ipv4
    json:
        request:
            url: https://api.xforce.ibmcloud.com/ipr/malware/{target}
            auth: xforce
        results:
            - key: type
              pretty_name: malware type
            - key: md5
              pretty_name: md5
            - key: domain
              pretty_name: domain name
            - key: firstseen
              pretty_name: first seen
            - key: lastseen
              pretty_name: last seen
```
To add this new source, edit your machinae.yml and add API authentication to your auth file.  This works for IP addresses and will query XForce for malware that might be associated with the target specified.
