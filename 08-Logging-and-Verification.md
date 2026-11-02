# 08 - Packet Logging and Verification

## 8.1 Introduction

Capturing network packets is only one part of network monitoring. Recording captured information is also important because it allows security analysts to review network activity after a capture session has ended.

In this project, a local logging mechanism was implemented to save captured packet metadata to a text file.

## 8.2 Logging Configuration

The application uses Python's pathlib module to manage the log directory and file.

The following configuration was implemented:

```python
LOG_DIR = Path("logs")
LOG_FILE = LOG_DIR / "packets.log"
```

The log directory is automatically created when the application starts:

```python
LOG_DIR.mkdir(exist_ok=True)
```

## 8.3 Saving Captured Packets

After analysing each packet, the application writes its information to the log file.

The following code performs the logging operation:

```python
with LOG_FILE.open("a", encoding="utf-8") as log:
    log.write(output)
```

The append mode (`a`) ensures that new packet records are added without replacing existing records.

## 8.4 Log File Location

Captured packet information is stored locally at:

```text
logs/packets.log
```

The file contains information such as:

- Packet number
- Timestamp
- Protocol
- Source IP address
- Destination IP address
- Source port
- Destination port
- Packet size
- Additional protocol details

## 8.5 Verifying the Log File

The log directory was checked using:

```bash
ls -lh logs/
```

The captured packet records were inspected using:

```bash
tail -n 30 logs/packets.log
```

These commands allowed the generated log file and its contents to be verified.

## 8.6 Capture Session Management

The application uses a packet counter to track captured packets.

When the user stops the sniffer using `CTRL+C`, the application displays a summary containing the total number of packets captured and the location of the log file.

## 8.7 Practical Evidence

### Screenshot 1: Packet Logging Directory

Capture the terminal showing the log file and its size.

![Packet Logging Directory](../screenshots/12-packet-logging.png)

### Screenshot 2: Captured Packet Records

Capture the terminal showing packet records from `logs/packets.log`.

https://github.com/SheuSec/CodeAlpha-Basic-Network-Sniffer/blob/main/screenshots/Captured%20Packet%20Records.pdf

## 8.8 Security Considerations

Packet logs may contain network metadata, including IP addresses, DNS queries, and communication details.

For this reason:

- Capture only traffic you are authorised to monitor.
- Protect log files from unauthorised access.
- Avoid publishing real network logs containing private information.
- Keep generated logs out of the public GitHub repository.

The project's `.gitignore` file excludes the local `logs/` directory.

## 8.9 Conclusion

The logging functionality successfully records captured packet metadata in a local file.

This feature makes it possible to review network activity after packet capture has stopped and demonstrates an important aspect of practical network monitoring.
