# Case Study 01 — VM-to-VM Authenticated Connectivity (Oracle VirtualBox)

## 1. Environment
- Host OS: Ubuntu 22.04
- Hypervisor: Oracle VirtualBox
- Guest Virtual Machines:
  - Kali Linux
  - Ubuntu Linux

## 2. Objective
The goal of this project was to enable secure communication between two Linux virtual
machines running on the same host, while respecting isolation and authentication principles.

This scenario reflects real-world infrastructure problems where systems must communicate
securely across defined network boundaries.

## 3. Initial Architecture
- Both VMs were created in Oracle VirtualBox
- Each VM had its own virtual network interface
- By default, the VMs were isolated and could not communicate

## 4. Implementation Steps (A → Z)

### Step 1: Create the Virtual Machines
- Install Kali Linux as one VM
- Install Ubuntu Linux as a second VM
- Ensure both systems boot correctly

### Step 2: Configure VirtualBox Networking
- Assign appropriate network adapters
- Ensure both VMs are connected to a compatible VirtualBox network mode
- Power on both VMs after configuration

### Step 3: Verify IP Configuration
On each VM, check network configuration:
```bash
ip a
ip route



