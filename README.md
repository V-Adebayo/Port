# Ports Lab

This repository contains my study notes and hands-on exercises on networking ports. It covers common port numbers, their associated services, and practical investigations using Windows networking tools.

## Repository Structure

```text
Port/
├── README.md
├── notes/
│   └── port.md
└── project/
    ├── netstat-investigation.md
    ├── netstat-output.png
    └── tasklist-pid.png
```

## What's Included

### Notes

The **notes** folder contains my study notes on:

* Port numbers
* Common TCP and UDP ports
* Well-known, registered, and dynamic ports
* Services associated with common ports

### Project

The **project** folder contains a hands-on investigation using `netstat` to examine network activity on my Windows machine.

During the investigation, I:

* Identified listening ports
* Observed different connection states
* Mapped Process IDs (PIDs) to running processes using `tasklist`
* Investigated ports and the services associated with them

## Images

The project includes screenshots captured during the investigation:

* `netstat-output.png`
* `tasklist-pid.png`

## Tools Used

* Windows Command Prompt
* `netstat`
* `tasklist`

## Skills Practised

* Port identification
* Network connection analysis
* Process identification using PIDs
* Basic network troubleshooting
* Understanding common connection states (`LISTENING`, `ESTABLISHED`, `TIME_WAIT`)

## Note

This repository documents my learning and practical exercises on networking ports. It combines study notes with hands-on investigations to strengthen my understanding of network communication and troubleshooting.
