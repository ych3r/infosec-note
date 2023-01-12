---
description: I have a networking joke, but it got lost in the way.
---

# Network

## Network Range

link: [https://www.arin.net/](https://www.arin.net/)

With network range, hackers can obtain information about how the network is structured and which machines in the network are alive.

## Traceroute

Traceroute utility traces the path or route through which the target host packets travel in the network.

It uses the ICMP protocol and Time to Live (TTL) field of the IP header to find the path of the target host in the network.

It can trace the number of routers the packets travel through, the round-trip time, and, if the routers have DNS entries, the names of the routes and their network affiliation.

The TTL indicates the maximum number of routers a packet may traverse.

Windows has **ICMP traceroute**:

```powershell
C:\>tracert 216.239.36.10
```

But many devices in the network generally block ICMP traceroute messages. So we use TCP or UDP traceroute.

In Linux:

```shell
$ sudo tcptraceroute www.google.com
```

Linux's traceroute uses UDP protocol.

```shell
$ traceroute www.google.com
```

## Traceroute Analysis

Example:

* traceroute 1.10.10.20, second to last hop is 1.10.10.1
* traceroute 1.10.20.10, third to last hop is 1.10.10.1
* traceroute 1.10.20.10, second to last hop is 1.10.10.50
* traceroute 1.10.20.15, third to last hop is 1.10.10.1
* traceroute 1.10.20.15, second to last hop is 1.10.10.50

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>from CEH</p></figcaption></figure>
