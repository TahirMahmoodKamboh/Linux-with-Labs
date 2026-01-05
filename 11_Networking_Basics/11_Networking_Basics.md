# Module 11: Networking Basics

## Introduction
Networking is a core part of Linux system administration. This module covers essential commands and concepts for configuring, troubleshooting, and understanding Linux networking.

## Key Topics
- IP configuration and hostname
- Basic network commands (ping, traceroute, netstat, ifconfig/ip)
- Network troubleshooting

## 1. Viewing and Setting IP Configuration
- View IP addresses:
  ```bash
  ip addr
  ifconfig
  ```
- Set IP address (temporary):
  ```bash
  sudo ip addr add 192.168.1.100/24 dev eth0
  ```
- Set hostname:
  ```bash
  hostnamectl set-hostname mylinuxpc
  ```

## 2. Basic Network Commands
- Test connectivity:
  ```bash
  ping 8.8.8.8
  ping google.com
  ```
- Trace route to a host:
  ```bash
  traceroute google.com
  ```
- Show open ports and connections:
  ```bash
  netstat -tuln
  ss -tuln
  ```

## 3. Network Troubleshooting
- Check DNS resolution:
  ```bash
  nslookup google.com
  dig google.com
  ```
- Check default gateway:
  ```bash
  ip route
  route -n
  ```

## Labs
### Lab 1: Check Your IP and Hostname
- View your IP address and hostname.
  ```bash
  ip addr
  hostname
  ```
**Solution:**
- Output shows your network interfaces and current hostname.

### Lab 2: Test Network Connectivity
- Ping a public server and trace the route.
  ```bash
  ping 8.8.8.8
  traceroute google.com
  ```
**Solution:**
- Successful ping and traceroute indicate working network connectivity.

### Lab 3: List Open Ports
- Use netstat or ss to list open ports.
  ```bash
  netstat -tuln
  ss -tuln
  ```
**Solution:**
- Output lists all listening ports and their associated services.

---

Mastering these basics will help you troubleshoot and configure Linux networking effectively!