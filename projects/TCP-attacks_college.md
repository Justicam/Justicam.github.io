---
layout: project
type: project
image: img/Screenshot 2024-09-05-005953-tcpattack.png
title: "TCP Attacks"
date: 2024
published: true
labels:
  - Python/Scapy
  - Denial of Service
summary: "My team carried out multiple attacks on a TCP network to explore its vulnerabilities in depth."
---

We conducted a comprehensive examination of the Transmission Control Protocol (TCP), focusing on the TCP SYN flood attack, SYN cookies, TCP reset attack, TCP session hijacking attack, and Reverse shell attacks. This allowed us to gain a better understanding of how attackers can exploit these flaws to disrupt or manipulate network communication.

The SYN flooding attack represents a type of Denial of Service (DoS) attack wherein attackers inundate a target's TCP port with a multitude of SYN requests, with no genuine intention of completing the three-way handshake process. This method allows attackers to overload the victim's queue reserved for half-open connections.

A TCP RST attack is a method employed to disrupt an established TCP connection between two entities, potentially causing a significant interruption in ongoing communications. This disruption can render services unavailable and precipitate various denial-of-service scenarios. To execute a TCP RST attack, an attacker must first pinpoint a valid TCP session to target. This involves identifying the source and destination IP addresses, port numbers, and the sequence numbers of the packets involved in the session. Following this identification, the attacker utilizes custom scripts to forge a TCP packet that mimics one from the targeted session.

The primary goal of the TCP Session Hijacking attack is to seize control of an ongoing TCP connection between two entities, facilitating the injection of malevolent content into this communication channel. Particularly pertinent in the context of telnet sessions, this attack enables perpetrators to embed harmful commands within the session's data flow, compelling the unwitting participants to execute these commands against their interests.


Here is some code that illustrates how we infiltrated a TCP 3 way-handshake:

```py
# Spoof the ACK to finish 3-way handshake 
initiated by the attacker
 # We are only allowed to use the sequence 
number in the captured packet
 def spoof(pkt):
 old_tcp= pkt[TCP]
 if old_tcp.flags== 'SA':
 # Spoof ACK to finish the handshake 
protocol
 ip=  IP( src = srv_ip,
 dst = x_ip)
 tcp= TCP(sport = srv_port,
 dport= x_port,
 seq   = syn_seq+ 1,
 ack   = old_tcp.seq+ 1,
 flags="A")
 data = 'Hello victim\n'
 print('  {}-->{} Spoofing ACK + 
Data'.format(tcp.sport, tcp.dport))
 send(ip/tcp/data, verbose=0)
```

