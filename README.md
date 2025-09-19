# Networking-project

## Overview

This project demonstrates the design and implementation of a simple secured network using Cisco Packet Tracer.
The objective is to configure an **Access Control List (ACL)** on a router to **restrict one PC (PC0) from accessing a server**, while allowing another PC (PC1) to communicate with it. This project introduces the fundamentals of network access control and highlights how ACLs can be used to enforce basic security policies within a local network.

## Technologies Implemented

* Basic Router Configuration (interface addressing)
* Switch-based LAN connectivity
* Static IPv4 addressing and gateway configuration
* Standard Access Control List (ACL) for traffic filtering
* ICMP (ping) testing for verification of access restrictions

## Requirements

* Cisco Packet Tracer (Version 8.x or higher recommended)
* Basic knowledge of:

  * IP addressing and subnetting
  * Router configuration (interfaces, IP assignment)
  * Access Control Lists (ACLs) fundamentals

## Project Design Steps

1. **Network Devices Setup**

   * 1 Router, 1 Switch, 2 PCs, and 1 Server were added.
   * All end devices were connected to the switch, and the switch was connected to the router.

2. **IP Addressing**

   * PC0: `192.168.1.2 / 24`
   * PC1: `192.168.1.3 / 24`
   * Server: `192.168.1.10 / 24`, Gateway: `192.168.1.1`
   * Router (Fa0/0): `192.168.1.1 / 24`

3. **Router Configuration**

   * The router interface was assigned the default gateway IP (`192.168.1.1`).

4. **ACL Implementation**

   * A standard ACL was created to **deny traffic from PC0** and allow all other traffic:

     ```
     access-list 1 deny 192.168.1.2  
     access-list 1 permit any  
     interface FastEthernet0/0  
     ip access-group 1 in  
     ```

5. **Testing**

   * PC0 was unable to ping the server (blocked by ACL).
   * PC1 was able to ping the server successfully (permitted by ACL).

## Deliverables

* The server is **accessible only by PC1**.
* PC0 is successfully **restricted** from accessing the server, validating the ACL configuration.


