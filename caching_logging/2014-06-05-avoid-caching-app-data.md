---
layout: guide
title: "Avoid Caching App Data"
description: "Data can be captured in a variety of artifacts – many unintended. Developers often overlook some of the ways data can be stored including log/debug files, cookies, web history, web cache, property lists, files and SQLite databases."
published: 1
categories:
  - caching-and-logging
series:
  name: Caching and Logging
  index: 2
order: 301
--- 

## Details 

Data can be captured in a variety of artifacts – many unintended. Developers often overlook some of the ways data can be stored including log/debug files, cookies, web history, web cache, property lists, files and SQLite databases. Storing data securely on a mobile device requires proper technique. Whenever possible, ***simply do not store/cache data.*** This is the most sure way to avoid data compromise on the device.

## Remediation

Prevent HTTP caching. Developers can configure iOS and Android to not cache web data, particularly HTTPS traffic. In iOS look into implementing an NSURLConnection delegate and disabling newCachedResponse. In addition, we recommend that steps be taken to avoid caching of URL history and page data for any Web process such as registration. HTTP Caching headers are important in this, and are configured on the web server. The HTTP protocol supports a “no-store” directive in a response header that instructs the browser that it must not store any part of either the response or the request that elicited it. For Web applications, HTML form inputs can use the autocomplete=off setting to instruct browsers not to cache values. The avoidance of caching should be validated through forensic examination of device data after app utilization.


## References

 * [http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html)


## CWE/OWASP

 * [M2 - Insecure Data Storage](https://www.owasp.org/index.php/Mobile_Top_10_2014-M2), [M4 - Unintended Data Leakage](https://www.owasp.org/index.php/Mobile_Top_10_2014-M4)
 * [CWE 312](http://cwe.mitre.org/data/definitions/312.html), [313](http://cwe.mitre.org/data/definitions/313.html), [522](http://cwe.mitre.org/data/definitions/522.html), [200](http://cwe.mitre.org/data/definitions/200.html)

