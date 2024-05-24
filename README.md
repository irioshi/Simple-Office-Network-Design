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
![Network Topology](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/f4ba5d9f-a678-4e8b-bc7a-c110569bc185)


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

## Cisco Packet Tracer Router Configuration
### Router Configuration - start
![router config-start](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/6515f29f-dcec-4008-8374-65e31dc76fa6)
### Router Configuration - state up
![router config-up](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/e3f9142c-75eb-4c3e-b103-105503122f86)
### Router Configuration - interface
![config interfaces](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/9bb48938-70b3-46d9-991e-c8aa3e9c58d0)
### Router Configuration - successful assignment
![router config-success](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/cd6c85fe-437f-40ae-a164-26389fe8532d)

## IP Address Configuration

### ACCOUNTS Department
- **Router Interface:** 192.168.40.1
- **PC0:**
  - IPv4 Address: 192.168.40.2
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.1
### PC-0 IP Configuration
![pc0-IP](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/a72989c1-fc2f-4e4e-8122-ac11c5cb88ac)

- **PC1:**
  - IPv4 Address: 192.168.40.3
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.1
### PC-1 IP Configuration
![pc1-IP](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/71d7c860-fd7e-401c-b234-672cb9293205)

- **Printer0:**
  - IPv4 Address: 192.168.40.4
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.1
### Printer-0 IP Configuration
![printer0-IP](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/2ffa9fe8-15ef-4df1-8b03-06f8517e5910)

### Printer-0 IP Configuration - gateway
![printer0-gateway](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/aa065c13-2bec-48d3-af19-207b83383649)


### DELIVERY Department
- **Router Interface:** 192.168.40.129
- **PC2:**
  - IPv4 Address: 192.168.40.130
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.129
### PC-2 IP Configuration
![pc2-IP](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/171c5627-23d6-4dcb-a06f-1399f5d4941c)

- **PC3:**
  - IPv4 Address: 192.168.40.131
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.129
### PC-3 IP Configuration
![pc3-IP](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/55ae5aec-c376-434f-9698-cf1821168077)

- **Printer1:**
  - IPv4 Address: 192.168.40.132
  - Subnet Mask: 255.255.255.128
  - Default Gateway: 192.168.40.129
### Printer-1 IP Configuration
![printer1-IP](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/4b93e16d-1725-4429-9e07-9b5d7821dcc8)

### Printer-1 IP Configuration - gateway
![printer1-gateway](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/96da42ce-65f2-420a-ae42-31efec36e4d7)

## Testing Connectivity

### Ping from PC2 in DELIVERY to PC0 in ACCOUNTS:
![pc2-ping](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/88c831a8-8fbf-4189-9c6b-4ab1c26cdd09)

- **Result:** Successful

### Ping from PC3 in DELIVERY to Printer0 in ACCOUNTS:
![pc3-ping](https://github.com/irioshi/Simple-Office-Network-Design/assets/98143751/330e8182-d8bf-4cd4-8696-1ce86bceeddc)
- **Result:** Successful
