# 04 - Python Network Sniffer Development

## 4.1 Introduction

After preparing the development environment and installing Scapy, the next stage involved developing the Python application responsible for capturing and analysing network packets.

The application was designed to monitor IPv4 traffic on the selected network interface and display useful information about captured packets.

## 4.2 Importing Required Libraries

The application uses the following Python modules:

```python
from scapy.all import sniff, IP, TCP, UDP, ICMP, DNS, DNSQR
from datetime import datetime
from pathlib import Path
```

### Library Functions

| Module or Function | Purpose |
|---|---|
| sniff | Captures network packets |
| IP | Identifies IPv4 packets |
| TCP | Identifies TCP packets |
| UDP | Identifies UDP packets |
| ICMP | Identifies ICMP packets |
| DNS | Identifies DNS information |
| DNSQR | Extracts DNS query information |
| datetime | Generates timestamps |
| Path | Handles log file paths |

## 4.3 Project Configuration

The network interface and log file were configured as follows:

```python
INTERFACE = "eth0"
LOG_DIR = Path("logs")
LOG_FILE = LOG_DIR / "packets.log"
```

A packet counter was also introduced to track the number of captured packets.

## 4.4 Packet Analysis Function

The `analyze_packet()` function is responsible for examining captured packets.

It extracts:

- Source IP address
- Destination IP address
- Protocol
- Source port
- Destination port
- Packet size
- Timestamp
- Relevant protocol details

The function identifies TCP, UDP, and ICMP traffic.

It also recognises DNS queries and responses.

## 4.5 DNS Analysis

DNS analysis was included to identify domain-name queries and responses.

For DNS queries, the application extracts the requested domain name.

For DNS responses, it displays the DNS response code (RCODE).

A response code of 0 represents NOERROR, indicating that the DNS server returned a successful response code.

## 4.6 Packet Logging

Captured packet information is displayed in the terminal and written to:

```text
logs/packets.log
```

This allows captured packet metadata to be reviewed after the capture session.

## 4.7 Starting Packet Capture

The application uses Scapy's `sniff()` function:

```python
sniff(
    iface=INTERFACE,
    filter="ip",
    prn=analyze_packet,
    store=False
)
```

### Explanation

| Parameter | Function |
|---|---|
| iface | Selects the network interface |
| filter | Captures IPv4 traffic |
| prn | Calls the analysis function for each packet |
| store=False | Prevents Scapy from retaining all captured packets in memory |

## 4.8 Running the Application

The application was started using:

```bash
sudo .venv/bin/python sniffer.py
```

The program listens for incoming and outgoing IPv4 packets on the configured interface.

Pressing `CTRL+C` stops the capture session.

## 4.9 Practical Evidence

### Screenshot 1: Python Source Code

Capture the complete or clearly readable sections of `sniffer.py` in your Kali editor.

![Python Sniffer Source Code](../screenshots/06-sniffer-source-code.png)

### Screenshot 2: Running Network Sniffer

Capture the terminal showing the application starting successfully and listening for packets.

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/sniffer-running.pdf

## 4.10 Conclusion

The Python application was developed using Scapy's packet-capture functionality.

It combines packet identification, metadata extraction, DNS analysis, timestamps, and local logging to provide a basic network monitoring tool.
