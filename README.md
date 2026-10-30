
# 🛡️ Cybersecurity Lab Environment Setup

<p align="center">
  <img src="https://img.shields.io/badge/Platform-VirtualBox-blue?style=for-the-badge&logo=virtualbox" />
  <img src="https://img.shields.io/badge/OS-Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux" />
  <img src="https://img.shields.io/badge/Network-NAT%20Network-green?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Project-Cybersecurity-red?style=for-the-badge&logo=hackthebox" />
</p>

## 📌 Project Overview

This project focuses on building and configuring a virtual cybersecurity testing laboratory using **Oracle VM VirtualBox** and **Kali Linux**.

The objective is to establish a dedicated testing environment that allows me to perform hands-on cybersecurity exercises, network reconnaissance, vulnerability assessments, and penetration testing in a controlled virtual environment.

The lab uses a dedicated NAT Network with a custom IP addressing scheme, shared folders, and virtual machine integration features to provide a functional environment for cybersecurity learning and practical experimentation.

## 🎯 Project Objectives

- Install and configure Oracle VM VirtualBox.
- Deploy Kali Linux as the primary attacking machine.
- Create a dedicated NAT Network using the `10.0.0.0/24` subnet.
- Configure Kali Linux with a static IP address of `10.0.0.2/24`.
- Enable full internet connectivity for Kali Linux.
- Configure bidirectional clipboard sharing.
- Enable drag-and-drop functionality.
- Configure shared folders between the host and virtual machine.
- Verify network connectivity and IP configurations.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Virtualization Platform | Oracle VM VirtualBox |
| Attacking Machine | Kali Linux |
| Network Mode | NAT Network |
| Network Name | NatNetwork |
| Network Subnet | `10.0.0.0/24` |
| Kali Linux IP | `10.0.0.2/24` |
| Shared Folder | `/downloads` |
| Clipboard | Bidirectional |
| Drag and Drop | Bidirectional |
| Internet Access | Enabled |

## 🏗️ Lab Architecture

The following diagram illustrates the planned virtual lab architecture.

```text
          HOST MACHINE
        (Windows / Linux)
                |
                |
        Oracle VirtualBox
                |
                |
          NAT Network
          10.0.0.0/24
                |
                |
         Kali Linux VM
          10.0.0.2/24
                |
                |
        Internet Connectivity
                |
                |
           External Network
```

## ⚙️ Implementation & Configuration

### 1. Install Oracle VM VirtualBox

Installed Oracle VM VirtualBox on the host machine to create and manage the virtual cybersecurity laboratory.

VirtualBox provides the virtualization infrastructure required to run Kali Linux independently of the host operating system.

**Screenshot: VirtualBox Installation**

![VirtualBox Installation](screenshots/01-virtualbox-installation.png)

### 2. Download and Configure Kali Linux

Downloaded the Kali Linux VirtualBox image and imported it into Oracle VM VirtualBox.

Kali Linux serves as the primary attacking machine for conducting cybersecurity testing and practical security exercises.

**Screenshot: Kali Linux Virtual Machine**

![Kali Linux VM](screenshots/02-kali-linux-vm.png)

### 3. Configure NAT Network

Created a dedicated NAT Network in VirtualBox to establish network connectivity for the virtual machine.

The following network configuration was applied:

| Network Parameter | Configuration |
|---|---|
| Network Name | `NatNetwork` |
| IPv4 Network | `10.0.0.0/24` |
| Network Mode | NAT Network |
| DHCP | As configured in VirtualBox |

**Screenshot: NAT Network Configuration**

![NAT Network Configuration](screenshots/03-nat-network-configuration.png)

### 4. Configure Kali Linux Network Adapter

Configured the Kali Linux virtual machine to connect through the previously created NAT Network.

The network adapter was assigned to `NatNetwork` to ensure that the virtual machine uses the designated laboratory network.

**Screenshot: Network Adapter Configuration**

![Network Adapter](screenshots/04-network-adapter-settings.png)

### 5. Configure Shared Folders

Enabled shared folder functionality to allow file exchange between the host operating system and Kali Linux.

The host machine's `/downloads` folder was configured as the shared folder.

This provides a convenient way to transfer files, scripts, tools, and other resources between the two environments.

**Screenshot: Shared Folder Configuration**

![Shared Folder](screenshots/05-shared-folder-settings.png)

### 6. Enable Clipboard and Drag-and-Drop

Enabled the following VirtualBox integration features:

- Shared Clipboard: Bidirectional
- Drag and Drop: Bidirectional

These settings improve interaction between the host machine and Kali Linux.

**Screenshot: Clipboard and Drag-and-Drop Settings**

![Clipboard and Drag Drop](screenshots/06-clipboard-drag-drop-settings.png)

### 7. Configure Kali Linux IP Address

Configured Kali Linux with the required static IPv4 address within the laboratory network.

| Network Parameter | Value |
|---|---|
| IP Address | `10.0.0.2` |
| Subnet Mask | `255.255.255.0` |
| CIDR | `/24` |
| Network Address | `10.0.0.0` |

The configuration ensures that Kali Linux operates within the specified `10.0.0.0/24` network.

**Screenshot: Kali Linux Desktop**

![Kali Linux Desktop](screenshots/07-kali-desktop.png)

**Screenshot: IP Address Configuration**

![IP Configuration](screenshots/08-ip-address-configuration.png)

## 🔍 Network Configuration & Verification

After completing the configuration, several Linux networking commands were used to verify the network setup and connectivity.

### 1. Verify IP Address

Command:

```bash
ip addr show
```

Purpose:
- Identify the active network interface.
- Verify the assigned IP address.
- Confirm the subnet configuration.

**Screenshot: IP Address Verification**

![IP Verification](screenshots/09-ip-verification.png)

### 2. Verify Routing Configuration

Command:

```bash
ip route
```

Purpose:
- Inspect the routing table.
- Verify the default gateway.
- Confirm the available network routes.

### 3. Test Network Connectivity

Command:

```bash
ping -c 4 8.8.8.8
```

Purpose:
- Test connectivity to an external IP address.
- Verify internet connectivity from Kali Linux.

**Screenshot: Internet Connectivity Test**

![Internet Connectivity](screenshots/10-internet-connectivity.png)

### 4. Verify DNS Resolution

Command:

```bash
nslookup google.com
```

Purpose:
- Verify DNS resolution.
- Confirm that domain names can be resolved into IP addresses.

**Screenshot: DNS Verification**

![DNS Verification](screenshots/11-dns-verification.png)

## 🔐 Final Lab Configuration

The cybersecurity testing environment is configured with the following required settings:

| Requirement | Status |
|---|---|
| VirtualBox Installation | Completed |
| Kali Linux Deployment | Completed |
| NAT Network Configuration | Completed |
| Subnet `10.0.0.0/24` | Configured |
| Kali Linux IP `10.0.0.2/24` | Configured |
| Internet Connectivity | Configured |
| Shared Clipboard | Enabled |
| Drag-and-Drop | Enabled |
| Shared Folder `/downloads` | Configured |

## 📚 Key Learning Outcomes

Through this practical implementation, I gained hands-on experience in:

**Virtualization**
- Understanding virtual machine deployment and management.
- Configuring Kali Linux within Oracle VM VirtualBox.

**Networking**
- Configuring NAT Networks.
- Understanding IPv4 addressing and subnetting.
- Configuring static IP addresses.
- Understanding default gateways and routing.

**Linux Administration**
- Using Linux networking commands.
- Inspecting network interfaces and routing tables.
- Troubleshooting connectivity and DNS issues.

**Virtual Machine Integration**
- Configuring shared folders.
- Enabling clipboard sharing and drag-and-drop functionality.
- Understanding host-to-guest integration.

## 🚀 Future Scope

This laboratory will serve as the foundation for further cybersecurity practical exercises, including:

- Network reconnaissance and scanning.
- Vulnerability assessment.
- Service enumeration.
- Penetration testing.
- Web application security testing.
- Network security monitoring.
- Ethical hacking exercises.

## ⚠️ Disclaimer

This laboratory is created strictly for educational purposes and authorized cybersecurity testing.

All security assessments and penetration-testing activities will be conducted only against systems that I own or have explicit permission to test.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Oracle VM VirtualBox | Virtualization |
| Kali Linux | Penetration Testing Distribution |
| Linux Terminal | Network Configuration & Testing |
| GitHub | Project Documentation |

## 👨‍💻 Author

**Usman Naushard**

Cybersecurity Undergraduate | Aspiring Penetration Tester

- [LinkedIn](https://linkedin.com/in/usmannaushard)
- [GitHub](https://github.com/usmannaus)

---

<p align="center">
  <b>Building Practical Skills. Exploring Cybersecurity. Securing the Digital World. 🔐</b>
</p>
