# 06 - TCP, UDP and ICMP Testing

## 6.1 Introduction

After implementing the network sniffer, practical testing was conducted to verify its ability to capture and identify different types of network traffic.

The tests were performed using Kali Linux in a controlled virtual machine environment.

Three major traffic categories were examined:

- TCP
- UDP
- ICMP

## 6.2 TCP Traffic Testing

### Objective

To verify that the application can identify TCP packets and extract their source and destination IP addresses and port numbers.

### Procedure

1. Start the network sniffer.
2. Generate normal TCP network traffic from the testing machine.
3. Observe the captured packets in the terminal.
4. Verify that TCP protocol information and port numbers are displayed.

### Observed Result

The sniffer successfully identified TCP traffic.

Example from the capture session:

```text
Protocol: TCP
Source IP: 104.18.39.21
Destination IP: 172.26.5.60
Source Port: 443
Destination Port: 49014
```

### Result

**Status: Successful**

The application identified TCP traffic and displayed the relevant packet metadata.

## 6.3 ICMP Traffic Testing

### Objective

To verify that the application can identify ICMP Echo Requests and Echo Replies.

### Procedure

The following command was executed:

```bash
ping -c 4 1.1.1.1
```

The sniffer was running simultaneously to observe the generated ICMP traffic.

### Expected Observations

- ICMP Type 8: Echo Request
- ICMP Type 0: Echo Reply

### Result

The application identified ICMP traffic and displayed the corresponding Echo Request and Echo Reply details.

**Status: Successful**

## 6.4 UDP Traffic Testing

### Objective

To verify that the application can identify UDP packets and display their port information.

### Procedure

The following DNS lookup command was executed:

```bash
nslookup example.com 1.1.1.1
```

The sniffer monitored the resulting network traffic.

### Observed Result

The application identified UDP packets associated with DNS communication.

It displayed the source and destination addresses, port numbers, and packet sizes.

**Status: Successful**

## 6.5 Testing Summary

| Test | Traffic | Result |
|---|---|---|
| TCP capture | TCP | Successful |
| ICMP testing | Echo Request and Reply | Successful |
| UDP testing | DNS traffic | Successful |

## 6.6 Practical Evidence

### Screenshot 1: TCP Traffic Capture

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/TCP%20Packet%20Capture.pdf

### Screenshot 2: ICMP Testing

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/ICMP%20Analysis.pdf

### Screenshot 3: UDP and DNS Traffic

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/UDP%20testing.pdf

## 6.7 Conclusion

The practical tests demonstrated that the network sniffer could capture and identify TCP, UDP, and ICMP traffic.

The successful observations confirmed the basic packet identification and metadata extraction functionality of the application.

