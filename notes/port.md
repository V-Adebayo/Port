# Port Numbers

## Overview

While studying networking, I learned that port numbers are used to identify specific services running on a device. Although devices communicate using IP addresses, port numbers help ensure that data reaches the correct application or service.

A simple way to think about it is:

- IP Address = House Address
- Port Number = Specific Room in the House

This allows multiple services to run on the same device without interfering with one another.

---

## Port Number Ranges

| Range | Category |
|---------|----------|
| 0 - 1023 | Well-Known Ports |
| 1024 - 49151 | Registered Ports |
| 49152 - 65535 | Dynamic/Private Ports |

---

## Common Ports

| Port | Protocol | Service |
|------|----------|---------|
| 20/21 | TCP | FTP |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP/UDP | DNS |
| 67/68 | UDP | DHCP |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 143 | TCP | IMAP |
| 161 | UDP | SNMP |
| 443 | TCP | HTTPS |

---

## Key Takeaways

- HTTP uses Port **80** for web communication.
- HTTPS uses Port **443** to provide encrypted communication.
- DNS uses Port **53** to translate domain names into IP addresses.
- SSH uses Port **22** for secure remote administration.
- DHCP uses Ports **67** and **68** to automatically assign IP addresses to hosts.

---

## What I Learned

One thing I found interesting is that a single device can host multiple services at the same time because each service listens on a different port number.

For example, a web server may use:

- Port **80** for HTTP traffic
- Port **443** for HTTPS traffic

Understanding common ports is important for networking, troubleshooting, system administration, and cybersecurity because they help identify the type of traffic flowing across a network.

---

## Quick Summary

Port numbers act as communication endpoints that allow network traffic to reach the correct service or application running on a device.
