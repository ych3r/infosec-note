---
description: Not sure if I'm a good programmer, or good at googling...
---

# Search Engines

## Google Hacking

> use advanced Google search operators for creating complex search queries to extract sensitive or hidden information

Get information on "games" from the "google" site:

```
games site:www.google.com
```

Only pages containing the words "google" and "career" in the URL:

```
allinurl:google career
```

Only Google pages in which the URL has the word "copy":

```
inurl:copy site:www.google.com
```

Only pages containing the words "detect" and "malware" in the title:

```
allintitle:detect malware
```

Only pages that have the term “help” in the title, and the terms “malware” and “detection” anywhere within the page:

```
malware detection intitle:help
```

Only pages with anchor text on links to the pages containing the word “Norton” and the page containing the word “Anti-virus”:

```
Anti-virus inanchor:Norton
```

Only pages for which the anchor text links to the pages contain the words “best,” “cloud,” “service,” and “provider”:

```
allinanchor: best cloud service provider
```

Show Google’s cached version of the Electronic Frontier Foundation home page:

```
cache:www.eff.org
```

Pages that point to Google Guide’s home page:

```
link:www.googleguide.com
```

The Google search engine results page with websites similar to microsoft.com:

```
related:www.microsoft.com
```

Information about the national hotel directory GotHotel.com home page:

```
info:gothotel.com
```

Information for a specific location

```
location: 4 seasons restaurant
```

Results based on a file extension:

```
black hat python filetype:pdf
Jordan:jpg
```



Google Hacking Database ([https://www.exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database)) is an authoritative source for querying the ever-widening scope of the Google search engine. In the GHDB, you will find search terms for files containing usernames, vulnerable servers, and even files containing passwords.
