# 02 - Tools and Development Environment

## 2.1 Introduction

The Basic Network Sniffer was developed and tested in a virtualized Linux environment. The development environment provides the tools required to write Python code, capture network packets, and analyse network communication.

## 2.2 Development Environment

| Component | Configuration |
|---|---|
| Operating System | Kali Linux |
| Virtualization Platform | Microsoft Hyper-V |
| Programming Language | Python 3.14.7 |
| Packet Analysis Library | Scapy 2.8.0 |
| Network Interface | eth0 |
| Project Environment | Python Virtual Environment |
| Package Manager | pip 26.1.2 |

## 2.3 Tools Used

### Kali Linux

Kali Linux provides the Linux environment used to develop and execute the network sniffer.

### Python

Python is the primary programming language used to implement the packet capture and analysis functionality.

### Scapy

Scapy is a Python library used to capture, inspect, and manipulate network packets. It provides the packet-processing functionality used by this project.

### Hyper-V

Hyper-V provides the virtual machine environment in which Kali Linux runs.

## 2.4 Python Virtual Environment

A Python virtual environment was created to isolate the project's dependencies from the system-wide Python installation.

The environment was created using:

```bash
python3 -m venv .venv
```

It was activated using:

```bash
source .venv/bin/activate
```

Scapy was installed inside the virtual environment.

## 2.5 Dependency Verification

The installed Scapy version was verified using:

```bash
.venv/bin/python -c "import scapy; print(scapy.__version__)"
```

The result confirmed:

```text
2.8.0
```

Python syntax was checked using:

```bash
.venv/bin/python -m py_compile sniffer.py
```

The command completed without reporting a syntax error.

## 2.6 Network Interface

The application was configured to capture traffic through:

```text
eth0
```

The interface was used to monitor IPv4 packets during the practical tests.

## 2.7 Conclusion

The development environment was successfully prepared, the required Scapy dependency was installed and verified, and the Python source file passed its syntax compilation check.

This environment provided the foundation for implementing and testing the network packet sniffer.

---

**Project:** CodeAlpha Basic Network Sniffer  
**Author:** Sheu Abduljelil  
**Internship:** CodeAlpha Cybersecurity Internship
