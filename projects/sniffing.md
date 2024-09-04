---
layout: project
type: project
image: img/
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

Next we used the same connection between the victims to utilize promiscuous mode with wireshark. Promiscuous mode enabled allows 






Here is some code that illustrates how we read values from the line sensors:

```py
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```

