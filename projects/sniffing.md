---
layout: project
type: project
image: img/Screenshot 2024-09-04-221342-sniffing.png
title: "Packet Sniffing/Spoofing"
date: 2024
published: true
labels:
  - Wireshark
  - Python
  - Scapy
summary: "My team used Wireshark along with custom Python scripts to capture and analyze packets of information transmitted over both TCP and UDP networks. "
---

The objective of this project was to grasp the significance of packet sniffing and packet spoofing as threats to network communications. Comprehending these threats is crucial for understanding the security measures required in networking. We explored the tools employed for packet sniffing and spoofing and developed our own sniffer and spoofing program. 

We mainly utilized Wireshark and Python/Scapy which are widely used by both security professionals and attackers. This specifically includes packet sniffing with the Wireshark and Scapy, packet spoofing via raw sockets and Scapy, and the manipulation of packets using Scapy. This knowledge forms our foundation for employing these tools and techniques in the context of network security and threat mitigation.

Firstly, we simulated a network connection within a virtual environment, using two users as targets. As these users communicated, we employed Python and Scapy scripts to spoof packets directed at one user and poison their ARP cache. This allowed us to successfully intercept and manipulate the network traffic. As a result, we were able to sniff packets of information exchanged between the victims, enabling us to analyze the data without their knowledge. 

Next, we employed the same connection between the victims to enable promiscuous mode in Wireshark. Promiscuous mode is a configuration setting for network devices that allows them to capture and process all network packets traversing the device, regardless of their destination. Under normal conditions, a network card only processes packets specifically addressed to it. However, in promiscuous mode, the network card intercepts all packets on the network, even those not intended for it. By capturing these packets with Wireshark, we were able to analyze and inspect the data being transmitted from the victims, gaining deeper insight into the network traffic.

Here is some code that illustrates how we used python to spoof packets:

```py
 #!/usr/bin/python3
 from scapy.all import *
 x_ip = "10.9.0.6"  # X-Terminal
 x_port = 9090         # Port number used by X-Terminal
 srv_ip = "10.9.0.5"  # The trusted server
 srv_port = 8000         # Port number used by the trusted server
 syn_seq = 0x1000       # Initial sequence number 
# Spoof a SYN from Trusted Server to X-Terminal
 ip = IP(  src = srv_ip, dst = x_ip)
 tcp= TCP( sport = srv_port, dport= x_port, 
seq   = syn_seq, flags = 'S')
 print('Sending SYN...')
 send(ip/tcp, verbose=1
```

