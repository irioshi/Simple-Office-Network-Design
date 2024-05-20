# Simple-Office-Network-Design
A case study on designing a basic network to connect Accounts and Delivery departments using Cisco Packet Tracer. Includes subnetting, IP configuration, and connectivity testing.

# Networking Case Study: Connecting Accounts and Delivery Departments

## Introduction
This project demonstrates the design and implementation of a basic network using Cisco Packet Tracer to connect two departments: ACCOUNTS and DELIVERY. The goal is to ensure seamless connectivity between these departments, with proper subnetting, IP addressing, and gateway configurations.

## Project Objectives
- Design a network to connect ACCOUNTS and DELIVERY departments.
- Ensure each department has at least 2 PCs.
- Utilize appropriate switches and routers to facilitate the network.
- Configure all interfaces using the given network address 192.168.40.0 with appropriate IP addresses, subnet masks, and gateways.
- Test and verify connectivity between the ACCOUNTS and DELIVERY departments, ensuring that PCs in the DELIVERY department can ping PCs in the ACCOUNTS department.

## Network Address Subnetting
- **Network Address:** 192.168.40.0
- **Subnets:** 2 (ACCOUNTS and DELIVERY)
- **Subnet Mask Calculation:** 2^n = number of subnets, n = 1
- The value of n is what will represent the number of borrowed network bits in a broadcast address, 255.255.255.255.
- This gives us the following address in binary: 11111111.11111111.11111111.10000000
- When converted from binary, our subnet mask is 255.255.255.128 - 128 is the block size.

## Network Topology
![Network Topology](images/network-topology.png)

## Subnet Details

### First Subnet (ACCOUNTS)
- **Network ID:** 192.168.40.0
- **Subnet Mask:** 255.255.255.128
- **Valid Host Range:** 192.168.40.1 - 192.168.40.126
- **Broadcast ID:** 192.168.40.127

### Second Subnet (DELIVERY)
- **Network ID:** 192.168.40.128
- **Subnet Mask:** 255.255.255.128
- **Valid Host Range:** 192.168.40.129 - 192.168.40.254
- **Broadcast ID:** 192.168.40.255

## Router Configuration
![Router Configuration - start](images/router-config-start.png)
![Router Configuration - state up](images/router-config-up.png)
![Router Configuration - interface](images/config-interfaces.png)
![Router Configuration - successful assignment](images/router-config-success.png)

## IP Address Configuration

### ACCOUNTS Department
- **Router Interface:** 192.168.40.1
- **PC0:**
  - IPv4 Address: 192.168.40.2
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.1
  ![PC-0 IP Configuration](images/pc0-IP.png)
- **PC1:**
  - IPv4 Address: 192.168.40.3
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.1
  ![PC-1 IP Configuration](images/pc1-IP.png)
- **Printer0:**
  - IPv4 Address: 192.168.40.4
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.1
  ![Printer-0 IP Configuration](images/printer0-IP.png)
  ![Printer-0 IP Configuration - gateway](images/printer0-gateway.png)

### DELIVERY Department
- **Router Interface:** 192.168.40.129
- **PC2:**
  - IPv4 Address: 192.168.40.130
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.129
  ![PC-2 IP Configuration](images/pc2-IP.png)
- **PC3:**
  - IPv4 Address: 192.168.40.131
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.129
  ![PC-3 IP Configuration](images/pc3-IP.png)
- **Printer1:**
  - IPv4 Address: 192.168.40.132
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.129
  ![Printer-1 IP Configuration](images/printer1-IP.png)
  ![Printer-1 IP Configuration - gateway](images/printer1-gateway.png)

## Testing Connectivity

### Ping from PC2 in DELIVERY to PC0 in ACCOUNTS:
![Ping from PC2](images/pc2-ping.png)
- **Result:** Successful

### Ping from PC3 in DELIVERY to Printer0 in ACCOUNTS:
![Ping from PC3](images/pc3-ping.png)
- **Result:** Successful
