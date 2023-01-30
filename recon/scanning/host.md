---
description: Who's alive?
---

# Host

**Host discovery** is the first step in scanning because we need to figure out which system is up.

## ARP Ping Scan

The [ARP](https://en.wikipedia.org/wiki/Address\_Resolution\_Protocol) packets are sent to discover all active devices in the IPv4 range even though restrictive firewalls hide some devices.

In most networks, especially LAN, many IP addresses are unused. So when hackers send IP packets to the target host, the OS must respond with the hardware destination address (MAC address). In that case, when hackers send ARP requests to the target host, if they receive any ARP response, then the host is active.

\-sn: disable the port scan

\-PR: perform ARP ping scan

```shell
nmap -sn -PR 192.168.1.1
```

{% hint style="info" %}
Nmap uses ARP ping scan as the default ping scan. To disable it: `--disable-arp-ping`
{% endhint %}

## UDP Ping Scan

Nmap sends [UDP](https://en.wikipedia.org/wiki/User\_Datagram\_Protocol) packets to the target host.

The default port used by nmap is 40, 125.

\-PU: perform UDP ping scan

```shell
nmap -sn -PU 192.168.1.1
```

## ICMP Ping Scan

### ICMP ECHO Ping Scan

ICMP ECHO ping scan involves sending ICMP ECHO requests to a host. If it is alive, it will respond with an ICMP ECHO reply.

{% hint style="info" %}
It doesn't work on Windows-based networks, their TCP/IP stack implementation doesn't reply to ICMP probes.
{% endhint %}

\-PE: perform the ICMP ECHO ping scan

```shell
nmap -sn -PE 192.168.1.1
```

### ICMP ECHO Ping Sweep

Add an IP range to a normal scan.

```shell
nmap -sn -PE 192.168.1.1-255
```

### ICMP Timestamp Ping Scan

Hackers query a timestamp message to acquire information related to the current time from the target host machine.

\-PP: perform an ICMP timestamp ping scan

```shell
nmap -sn -PP 192.168.1.1
```

### ICMP Address Mask Ping Scan

Hackers send an ICMP address mask query to the target host to acquire information related to the subnet mask.

\-PM: perform an ICMP address mask ping scan

```shell
nmap -sn -PM 192.168.1.1
```

## TCP Ping Scan

### TCP SYN Ping Scan

In TCP SYN ping, hackers initiate the three-way handshake by sending the empty TCP SYN flag to the target host. After the reception of the ACK flag for the target, the hacker confirms the target host is active and sends an RST flag to terminate the connection.

Port 80 is used as the default destination port.

\-PS: perform a TCP SYN ping scan

```shell
nmap -sn -PS 192.168.1.1
```

### TCP ACK Ping Scan

Hackers send an empty TCP ACK packet to the target host directly. Since there is no prior connection, the target host responds with an RST flag to terminate the request. The reception of RST indicates the host is active.

\-PA: perform a TCP ACK ping scan

```shell
nmap -sn -PA 192.168.1.1
```

## IP Protocol Scan

### IP Protocol Ping Scan

Hackers send IP ping packets with the IP header of any specified protocol number.

\-PO: perform an IP protocol ping scan

<pre class="language-shell"><code class="lang-shell"><strong>nmap -sn -PO 192.168.1.1
</strong></code></pre>
