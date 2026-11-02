# 05 - Network Packet Analysis

## 5.1 Introduction

Network packet analysis involves examining packets transmitted across a network to understand communication between devices.

In this project, Scapy is used to inspect captured IPv4 packets and extract relevant network information.

The application identifies TCP, UDP, and ICMP traffic and provides additional DNS information where available.

## 5.2 Understanding an IP Packet

An IPv4 packet contains information that helps devices communicate across networks.

Some of the important fields examined in this project include:

| Field | Description |
|---|---|
| Source IP | Address of the device sending the packet |
| Destination IP | Address of the receiving device |
| Protocol | Identifies the transport or network protocol |
| Packet Size | Total captured packet length in bytes |
| Timestamp | Time the application processes the packet |

## 5.3 TCP Analysis

Transmission Control Protocol (TCP) is a connection-oriented transport protocol.

It provides reliable, ordered delivery of data between communicating devices.

The sniffer identifies TCP packets and extracts their source and destination port numbers.

Example:

```text
Protocol: TCP
Source IP: 104.18.39.21
Destination IP: 172.26.5.60
Source Port: 443
Destination Port: 49014
```

This represents an example of captured TCP traffic from the testing session.

## 5.4 UDP Analysis

User Datagram Protocol (UDP) is a connectionless transport protocol.

Unlike TCP, UDP does not establish a connection before sending data.

It is commonly used for DNS queries and other network services.

The sniffer identifies UDP packets and extracts their port information.

## 5.5 ICMP Analysis

Internet Control Message Protocol (ICMP) is used for network diagnostics and error reporting.

The application identifies ICMP packets and distinguishes between:

- Echo Request: ICMP Type 8
- Echo Reply: ICMP Type 0

These message types are commonly observed during ping testing.

## 5.6 DNS Analysis

Domain Name System (DNS) translates domain names into information such as IP addresses.

The application checks DNS packets and identifies:

- DNS queries
- DNS responses
- DNS response codes

During testing, the application successfully identified a query for:

```text
example.com
```

It also detected the corresponding DNS response with RCODE 0.

## 5.7 Packet Metadata

For each IPv4 packet, the application displays:

- Packet number
- Timestamp
- Protocol
- Source IP address
- Destination IP address
- Source port
- Destination port
- Packet size
- Additional protocol details

## 5.8 Practical Evidence

### Screenshot 1: TCP Packet Capture

Capture a real TCP packet displayed by the running sniffer.

![TCP Packet Capture](../screenshots/07-live-tcp-packet-capture.png)

### Screenshot 2: ICMP Analysis

Capture the Echo Request and Echo Reply messages.

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/ICMP%20Analysis.pdf

## 5.9 Conclusion

The packet analysis functionality demonstrates how Python and Scapy can be used to identify network protocols and extract useful packet metadata.

The project provides practical exposure to TCP, UDP, ICMP, and DNS traffic analysis.
