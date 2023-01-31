---
description: So, what are you running?
---

# Port & Service

## TCP Scanning

### TCP Connect/Full-open Scan

In TCP Connect scanning, TCP `connect()` system call tries to open a connection to every port of interest on the target system.

\-sT: perform TCP Connect/full open scan

```shell
nmap -sT 192.168.1.1
```

However, this type of scan is easily **detectable** and **filterable**.

### Half-open Scan

In Stealth scanning, it resets the TCP connection between the client and the server abruptly before the completion of the three-way handshake. It sends a single frame to a TCP port without any TCP handshaking.

* The hacker sends a single SYN packet.
* If the port is open, the target responds with an SYN/ACK packet.
* If not, the target responds with an RST packet.

\-sS: perform a stealth scan/TCP half-open scan

```shell
nmap -sS 192.168.1.1
```

### Inverse TCP Flag Scan

Use TCP flag (**FIN, URG, PSH**) set or no flags. If the port is open, we'll receive nothing. If the port is closed, we'll **receive RST**.

> Some firewalls and IDS can detect SYN packets sent to the sensitive ports. Syslog can even log hal-open SYN flag scan attempts.

However, it requires super-user privileges and not working against Windows (it will show that all the ports are open).

#### Xmas Scan

Use FIN, URG, and PUSH flags.

\-sX: perform Xmas scan

\-sF: perform FIN scan

\-sN: perform NULL scan

```shell
nmap -sX 192.168.1.1
```

#### TCP Maimon Scan

Use FIN/ACK flags.

> "In most cases, to determine if the port is open or closed, the RST packet should be generated as a response to a probe request. However, in many BSD systems, the port is open if the packet gets dropped in response to a probe."

\-sM: perform TCP Maimon scan

```shell
nmap -sM 192.168.1.1
```

### ACK Flag Probe Scan

### IDLE/IP ID Header Scan

## UDP Scanning

## SCTP Scanning

### SCTP INIT Scanning

### SCTP COOKIE/ECHO Scanning

## SSDP Scanning

## IPv6 Scanning
