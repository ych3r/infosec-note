---
description: It's always DNS.
---

# DNS

## Extracting DNS Information

DNS zone data include DNS domain names, computer names, IP addresses, and much more information about a network.

| Record Type | Description                                      |
| ----------- | ------------------------------------------------ |
| A           | Points to a host's IP address                    |
| MX          | Points to domain's mail server                   |
| NS          | Points to host's name server                     |
| CNAME       | Canonical naming allows aliases to a host        |
| SOA         | Indicate authority for a domain                  |
| SRV         | Service records                                  |
| PTR         | Maps IP address to a hostname                    |
| RP          | Responsible person                               |
| HINFO       | Host information record includes CPU type and OS |
| TXT         | Unstructured text records                        |

### SecurityTrails

link: [https://securitytrails.com/](https://securitytrails.com/)

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption><p>SecurityTrails</p></figcaption></figure>

## Reverse DNS Lookup

DNS lookup is used to find the IP addresses for a given domain name, and a reverse DNS operation is performed to obtain the domain name of a given IP address.

### DNSRecon

link: [https://github.com/darkoperator/dnsrecon](https://github.com/darkoperator/dnsrecon)

```
dnsrecon -r 162.241.216.0-162.241.216.255
```

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>dnsrecon in Kali</p></figcaption></figure>

### Reverse Lookup

link: [https://mxtoolbox.com/](https://mxtoolbox.com/)

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>mxtoolbox</p></figcaption></figure>
