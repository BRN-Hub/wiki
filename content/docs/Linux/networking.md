---
title: Networking
linkTitle: Networking
---
# Networking in Linux

## Overview
This tutorial will introduce you to basic networking concepts in Linux, including configuring network interfaces, using common network commands, and setting up SSH for remote access.

## Prerequisites
- Basic knowledge of Linux commands (covered in previous tutorials).
- A Linux environment to practice in.

## Objectives
By the end of this tutorial, you will:
1. Understand how to configure network interfaces in Linux.
2. Know how to use common network commands to troubleshoot and manage network connections.
3. Be able to set up SSH for secure remote access.

## 1. Configuring Network Interfaces

### Viewing Network Interfaces
- **ifconfig**:
```bash
  ifconfig
```

Displays information about all network interfaces.
- ip addr:
```bash
Copy code
ip addr

```
	Another command to display network interface information.
#### Configuring a Static IP Address
1. Open the network configuration file for your interface. For example, on Debian-based systems:
```bash
Copy code
sudo nano /etc/network/interfaces

```
2. Add the following configuration for a static IP (replace eth0 with your interface name):
```bash
Copy code
auto eth0
iface eth0 inet static
    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.1

```
3. Restart the networking service:
```bash
Copy code
sudo systemctl restart networking

```
#### Configuring a Dynamic IP Address (DHCP)
1. Open the network configuration file for your interface:
```bash
Copy code
sudo nano /etc/network/interfaces

```
2. Add the following configuration for DHCP:
```bash
Copy code
auto eth0
iface eth0 inet dhcp

```
3. Restart the networking service:
```bash
Copy code
sudo systemctl restart networking

```
### 2. Common Network Commands
#### Checking Network Connectivity
- ping:
```bash
Copy code
ping google.com

```
	Sends ICMP echo requests to check connectivity to a host.
#### Tracing Route to a Host
- traceroute:
```bash
Copy code
traceroute google.com

```
	Shows the path packets take to reach a host.
#### Displaying Network Statistics
- netstat:
```bash
Copy code
netstat -tuln

```
	Displays network connections, routing tables, interface statistics, masquerade connections, and multicast memberships.
#### Checking DNS Resolution
- nslookup:
```bash
Copy code
nslookup google.com

```
	Queries DNS servers for information about a domain.
- dig:
```bash
Copy code
dig google.com

```
	Another command to query DNS servers.
### 3. Setting Up SSH for Remote Access
#### Installing SSH Server
- Debian-based systems:
```bash
Copy code
sudo apt install openssh-server

```
- Red Hat-based systems:
```bash
Copy code
sudo yum install openssh-server

```
#### Starting and Enabling SSH Service
- Start the SSH service:
```bash
Copy code
sudo systemctl start ssh

```
- Enable the SSH service to start on boot:
```bash
Copy code
sudo systemctl enable ssh

```
#### Connecting to a Remote Machine
- Using SSH:
```bash
Copy code
ssh username@hostname_or_ip

```
#### Configuring SSH for Security
1. Open the SSH configuration file:
```bash
Copy code
sudo nano /etc/ssh/sshd_config

```
2. Disable root login:
```bash
Copy code
PermitRootLogin no

```
3. Change the default SSH port (optional):
```bash
Copy code
Port 2222

```
4. Restart the SSH service:
```bash
Copy code
sudo systemctl restart ssh

```
### 4. Practical Examples
#### Example 1: Configuring a Static IP Address
1. Open the network configuration file:
```bash
Copy code
sudo nano /etc/network/interfaces

```
2. Add the static IP configuration:
```bash
Copy code
auto eth0
iface eth0 inet static
    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.1

```
3. Restart the networking service:
```bash
Copy code
sudo systemctl restart networking

```
#### Example 2: Testing Network Connectivity
1. Check connectivity to a host:
```bash
Copy code
ping google.com

```
2. Trace the route to a host:
```bash
Copy code
traceroute google.com

```
#### Example 3: Setting Up SSH Access
1. Install SSH server:
```bash
Copy code
sudo apt install openssh-server

```
2. Start and enable SSH service:
```bash
Copy code
sudo systemctl start ssh
sudo systemctl enable ssh

```
3. Connect to a remote machine:
```bash
Copy code
ssh username@hostname_or_ip

```
### Summary
In this tutorial, you learned how to configure network interfaces, use common network commands, and set up SSH for remote access in Linux. These skills are essential for managing and troubleshooting network connections on a Linux system.
### Next Steps
Proceed to the next tutorial, Linux Permissions and Security, to learn how to manage file permissions, ownership, and implement basic security practices.