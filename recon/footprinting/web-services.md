---
description: The wild wild web where there's nothing to hide~
---

# Web Services

## Top-Level Domains (TLDs) and Sub-domains

While a public website is designed to attract public customers, its sub-domains are generally not public. Sub-domains might be used to test new features and, of course, they are very likely to have vulnerabilities.

### Google Hacking

```
site:microsoft.com -inurl:www
```

### Netcraft

link: [https://www.netcraft.com/](https://www.netcraft.com/)

```
https://searchdns.netcraft.com/?host=microsoft.com
```

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption><p>Netcraft DNS search</p></figcaption></figure>

### Sublist3r

link: [https://github.com/aboul3la/Sublist3r](https://github.com/aboul3la/Sublist3r)

<figure><img src="../../.gitbook/assets/image (1) (2).png" alt=""><figcaption><p>Sublist3r in Kali</p></figcaption></figure>

## People Search

### Spokeo

link: [https://www.spokeo.com/](https://www.spokeo.com/)

Not very accurate.

### theHarvester

link: [https://github.com/laramies/theHarvester](https://github.com/laramies/theHarvester)

```
theHarvester -d microsoft -l 200 -b all
```

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>theHarvester in Kali</p></figcaption></figure>

## Operating System

### Netcraft

link: [https://www.netcraft.com/](https://www.netcraft.com/)

```
https://sitereport.netcraft.com/?url=http://microsoft.com
```

<figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption><p>Netcraft Site report search</p></figcaption></figure>

### SHODAN

link: [https://www.shodan.io/](https://www.shodan.io/)

```
https://www.shodan.io/search?query=microsoft.com
```

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>SHODAN</p></figcaption></figure>

### Censys

link: [https://search.censys.io/](https://search.censys.io/)

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Censys</p></figcaption></figure>

## GitHub

### Recon-ng

link: [https://github.com/lanmaster53/recon-ng](https://github.com/lanmaster53/recon-ng)

