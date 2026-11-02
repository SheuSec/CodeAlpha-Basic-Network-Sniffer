# 🛡️ CodeAlpha Basic Network Sniffer

**A Python-based network packet capture and analysis tool developed using Scapy.**

![Python](https://img.shields.io/badge/Python-3.14-blue)
![Scapy](https://img.shields.io/badge/Scapy-2.8.0-green)
![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-purple)
![Internship](https://img.shields.io/badge/Internship-CodeAlpha-orange)

## 📌 Project Overview

Network communication happens every second, with devices exchanging packets of information across networks.

But what exactly travels across a network, and how can we observe it?

This project explores that question through the development of a basic network sniffer using Python and Scapy.

The application captures IPv4 packets, identifies common network protocols, extracts packet metadata, analyses DNS queries and responses, and saves captured information to a local log file.

Developed as part of the **CodeAlpha Cybersecurity Internship**.

## 🎯 Project Objectives

- Understand network packet capture and analysis.
- Identify TCP, UDP, and ICMP traffic.
- Extract source and destination IP addresses.
- Identify source and destination ports.
- Analyse DNS queries and responses.
- Display packet timestamps and sizes.
- Record captured packet information locally.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Application development |
| Scapy | Packet capture and analysis |
| Kali Linux | Development and testing |
| Hyper-V | Virtual machine environment |

## ⚙️ Key Features

- IPv4 packet capture.
- TCP, UDP, and ICMP identification.
- Source and destination IP extraction.
- Port identification.
- ICMP Echo Request and Reply detection.
- DNS query and response identification.
- Packet timestamps and size reporting.
- Local packet logging.

## 📂 Repository Structure

```text
CodeAlpha-Basic-Network-Sniffer/
│
├── 01-Project-Overview/
│   ├── 01-Introduction.md
│   └── 02-Tools-and-Environment.md
│
├── 02-Implementation/
│   ├── 03-Scapy-Installation.md
│   ├── 04-Python-Sniffer-Development.md
│   └── 05-Packet-Analysis.md
│
├── 03-Testing-and-Results/
│   ├── 06-TCP-UDP-ICMP-Testing.md
│   ├── 07-DNS-Traffic-Analysis.md
│   └── 08-Logging-and-Verification.md
│
├── screenshots/
│
├── sniffer.py
├── requirements.txt
├── .gitignore
└── README.md
```

## 🚀 Installation and Usage

### 1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd CodeAlpha-Basic-Network-Sniffer
```

### 2. Create a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the network sniffer

```bash
sudo .venv/bin/python sniffer.py
```

The application is configured to monitor the `eth0` interface.

Press `CTRL+C` to stop packet capture.

## 🧪 Practical Testing

The application was tested using controlled network activity.

| Test | Method | Result |
|---|---|---|
| TCP capture | Normal TCP network traffic | Successful |
| ICMP analysis | `ping -c 4 1.1.1.1` | Successful |
| UDP/DNS analysis | `nslookup example.com 1.1.1.1` | Successful |
| Packet logging | Local log inspection | Verified |

## 📸 Project Evidence

Practical screenshots documenting the development, execution, and testing process are available in the [`screenshots`](screenshots/) directory.

## 📚 Technical Documentation

Explore the project documentation:

1. [Project Introduction](01-Project-Overview/01-Introduction.md)
2. [Tools and Development Environment](01-Project-Overview/02-Tools-and-Environment.md)
3. [Scapy Installation and Verification](02-Implementation/03-Scapy-Installation.md)
4. [Python Sniffer Development](02-Implementation/04-Python-Sniffer-Development.md)
5. [Network Packet Analysis](02-Implementation/05-Packet-Analysis.md)
6. [TCP, UDP and ICMP Testing](03-Testing-and-Results/06-TCP-UDP-ICMP-Testing.md)
7. [DNS Traffic Analysis](03-Testing-and-Results/07-DNS-Traffic-Analysis.md)
8. [Packet Logging and Verification](https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/08-Logging-and-Verification.md)

## 🔐 Security and Ethical Considerations

This tool is intended for educational purposes and authorised network monitoring.

Only capture traffic on systems and networks you own or have explicit permission to monitor.

Packet logs may contain sensitive network metadata. They are excluded from the public repository.

## ⚠️ Current Limitations

- IPv4 traffic only.
- Configured for the `eth0` interface.
- Requires appropriate packet-capture permissions.
- Does not decrypt encrypted communications.
- Provides basic packet metadata analysis rather than advanced intrusion detection.

## 👨‍💻 Author

**Sheu Abduljelil**

Cybersecurity Analyst & SOC Specialist

Developed as part of the CodeAlpha Cybersecurity Internship.

---

*Learning how networks communicate, one packet at a time.*
