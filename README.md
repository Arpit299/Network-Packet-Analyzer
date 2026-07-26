## Network Packet Analyser

A basic command-line network sniffer built with Python and Scapy. This tool captures network packets and displays source/destination IP addresses along with the protocol used (TCP/UDP).

## Features
- Real-time packet interception.
- Protocol identification (TCP, UDP, and others).
- IP address extraction for source and destination.

## Installation

Ensure you have Python installed, then install the dependencies:

```bash
pip install scapy
```

## Usage

To run the sniffer, execute the script with administrative privileges:

```python
from scapyall import sniff, IP, TCP, UDP

# Define the callback function
def packet_callback(packet):
    if IP in packet:
        ip_src = packet[IP].src
        ip_dst = packet[IP].dst
        proto = "TCP" if TCP in packet else "UDP" if UDP in packet else "Other"
        print(f"[+] {proto} Packet: {ip_src} -> {ip_dst}")
```

# Start sniffing
sniff(prn=packet_callback, count=10)

## Disclaimer
This tool is for educational purposes only. Unauthorised sniffing of network traffic may be illegal in your jurisdiction.
