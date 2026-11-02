# 07 - DNS Traffic Analysis

## 7.1 Introduction

The Domain Name System (DNS) is an essential part of network communication. It translates human-readable domain names into information that computers use to communicate across networks.

DNS analysis helps security professionals understand domain lookups, identify communication patterns, and investigate potentially suspicious network activity.

In this project, Scapy was used to identify DNS queries and responses within captured IPv4 traffic.

## 7.2 Objective

The objective of this test was to verify that the network sniffer could:

- Identify DNS packets.
- Recognise DNS queries.
- Extract requested domain names.
- Identify DNS responses.
- Display DNS response codes.

## 7.3 Generating DNS Traffic

The following command was executed in Kali Linux:

```bash
nslookup example.com 1.1.1.1
```

This command requests DNS information for `example.com` using the DNS resolver at `1.1.1.1`.

The network sniffer was running simultaneously to capture the resulting traffic.

## 7.4 DNS Query Identification

The application checks whether a captured packet contains DNS information.

For DNS queries, it checks the DNS query flag and extracts the requested domain name using Scapy's DNSQR layer.

Example observed output:

```text
Protocol: UDP
Source IP: 172.26.5.60
Destination IP: 1.1.1.1
Source Port: 48179
Destination Port: 53
Details: DNS Query: example.com.
```

This represents an outgoing DNS query from the Kali machine to the DNS resolver.

## 7.5 DNS Response Identification

The application also identifies DNS responses.

Example observed output:

```text
Protocol: UDP
Source IP: 1.1.1.1
Destination IP: 172.26.5.60
Source Port: 53
Destination Port: 48179
Details: DNS Response (RCODE: 0)
```

The response code `0` represents `NOERROR`, indicating a successful DNS response code.

It does not, by itself, guarantee that the response contains the requested record.

## 7.6 Understanding DNS Communication

The test demonstrated the following communication sequence:

1. The Kali machine generates a DNS query.
2. The query is sent to the DNS resolver.
3. The resolver processes the request.
4. A DNS response is returned.
5. The sniffer identifies and displays both query and response metadata.

## 7.7 Practical Evidence

### Screenshot 1: DNS Query and Response

Capture the terminal showing the DNS query for `example.com` and its corresponding response.

![DNS Query and Response](../screenshots/10-dns-query-response-analysis.png)

### Screenshot 2: DNS Lookup Command

Capture the terminal showing the command:

```bash
nslookup example.com 1.1.1.1
```

and its result.

![DNS Lookup Test](../screenshots/13-dns-lookup-test.png)

## 7.8 Security Relevance

DNS traffic analysis is useful in cybersecurity investigations.

Security analysts can examine DNS activity to help identify:

- Unexpected domain lookups.
- Communication with suspicious domains.
- Unusual DNS request patterns.
- Potential indicators of compromise.

This project demonstrates basic DNS metadata analysis and is not a complete DNS threat-detection system.

## 7.9 Conclusion

The network sniffer successfully identified DNS queries and responses during the practical test.

It extracted the requested domain name and displayed the DNS response code, demonstrating how Scapy can support basic DNS traffic analysis.
