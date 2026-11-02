# 03 - Scapy Installation and Verification

## 3.1 Introduction

Scapy is a powerful Python library used for network packet manipulation, transmission, reception, and analysis.

For this project, Scapy provides the functionality required to capture IPv4 packets and inspect their network and transport-layer information.

## 3.2 Preparing the Python Environment

Before installing Scapy, a dedicated Python virtual environment was created to isolate the project's dependencies.

The following command was used:

```bash
python3 -m venv .venv
```

The environment was activated using:

```bash
source .venv/bin/activate
```

## 3.3 Installing Scapy

Scapy was installed using pip inside the activated virtual environment.

Installation command:

```bash
pip install scapy
```

This installed the packet manipulation and analysis library required by the application.

## 3.4 Verifying the Installation

After installation, Scapy was imported and its version checked using:

```bash
.venv/bin/python -c "import scapy; print(scapy.__version__)"
```

The terminal confirmed the installed version:

```text
2.8.0
```

This confirmed that Scapy was successfully installed and accessible from the project's Python environment.

## 3.5 Testing Python Compatibility

The Python source file was also checked for syntax errors using:

```bash
.venv/bin/python -m py_compile sniffer.py
```

The command completed without reporting any errors.

## 3.6 Practical Evidence

### Screenshot 1: Scapy Installation

This screenshot demonstrates the Scapy installation process in Kali Linux.

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/scapy-installation.pdf

### Screenshot 2: Scapy Version Verification

This screenshot shows the successful installation and verification of Scapy version 2.8.0.

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/scapy-verification.pdf

### Screenshot 3: Python Syntax Verification

This screenshot demonstrates that the Python source file passed the compilation check.

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/scapy-verification.pdf

## 3.7 Conclusion

Scapy was successfully installed and verified in the project's Python virtual environment.

The successful dependency and syntax checks established the foundation for developing the packet capture and analysis functionality.
