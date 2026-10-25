<div align="center">

# B084-WK1-LABENV-SETUP
This is my first repo for the network walks internship program. I was setting up my lab environment by downloading and setting up kali linux virtual box.

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />

---

## 📌 Project Overview

This project focuses on setting up a **virtual cybersecurity and penetration-testing laboratory** using VirtualBox and Kali Linux.

The lab is a step by step process in creating a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be done without risk to real systems or networks.

The network is built on a private virtual subnet that allows additional machines to be added later for authorized security testing.

---
## 🎯 Objectives

The main objectives of this project are to:

- A working VirtualBox installation acting as the hypervisor
- A Kali Linux VM imported and running
- A dedicated internal network (separate from the default NAT) that supports both internet access and future multi-VM communication
- A Kali machine with a fixed IP instead of a DHCP-assigned one
- Verified internet access and working DNS lookups
- Shared clipboard, drag-and-drop, and a shared folder enabled between host and Kali
- A saved snapshot marking this as a known-good starting point
- Room to expand the lab with more VMs down the line for actual practice exercise
---

## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing, not a live network or a system that is not yours. This lab exists to solve that problem: everything runs inside a virtual machine, cut off from the host network, so tools can be run, scans can be launched, and mistakes can be made without any real-world consequences.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
- Security-tool experimentation

⚠️ **Important:** Every tool and technique used in this lab is restricted to machines within the lab. Nothing should be pointed at a live system without explicit permission.
---

## ⚙️ Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Windows 11         |
| ⚡ Processor       | Intel Core i7      |
| 🧰 Hypervisor      | VirtualBox 7.2.22  |
| 🐉 Security OS     | Kali Linux 2026.2  |
| 🧠 Kali RAM        | 2048 MB            |
| 🌐 Virtual Network | NAT Network        |
| 📡 Network Address | 10.0.0.0/24        |
| 🚪 Default Gateway | 10.0.0.1           |
| 🌍 DNS Server      | 10.0.0.1           |

---
# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip
This was installed to extract Kali Linux VM Package. However if you have other extraction tools like WinRar you can use them.

---
## Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor for running the Kali Linux VM.

---
## Step 3. Create the NAT Network
A dedicated NAT Network was created in the VirtualBox. A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity. This will allow future VMs added to communicate within the lab

Configuration:
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled

<img width="1128" height="752" alt="Screenshot 2026-10-25 181004" src="https://github.com/user-attachments/assets/757966d5-18a4-47c3-925e-99f1b5b16803" />


---
## Step 4. Import Kali Linux
The Kali Linux VM image is downloaded and imported into VirtualBox, with its network adapter attached to the NatNetwork created above.

---
## Step 5. Configure the Kali Linux Network
A static IPv4 address is set on Kali's network connection so the machine has a consistent, predictable address every time it starts:

Example configuration:

```text
IP Address: 10.0.0.1/24
Gateway: 10.0.0.1
DNS: 10.0.0.1
```

<img width="1128" height="752" alt="Screenshot 2026-10-25 181847" src="https://github.com/user-attachments/assets/c22da601-d199-4a05-8d20-1cbc23c49959" />


<img width="1128" height="752" alt="Screenshot 2026-10-25 183636" src="https://github.com/user-attachments/assets/6b7e3951-4388-46ef-a6d5-cdada8ef53e8" />

---
## Step 6. Verify Connectivity
Connectivity and DNS resolution are confirmed by pinging the gateway and testing internet access
<img width="1128" height="752" alt="Screenshot 2026-10-25 183826" src="https://github.com/user-attachments/assets/fb4e7375-2174-44f5-90df-29e6f63876eb" />

---
## Step 7. Create a Clean VM Snapshot
A snapshot of the VM is taken once the setup is complete, providing a clean recovery point in case future changes cause issues.

The snapshot represents the clean baseline of the laboratory.
<img width="1128" height="752" alt="Screenshot 2026-10-25 184025" src="https://github.com/user-attachments/assets/440665d0-fde6-4fb1-acc8-0ece2f18b018" />


---

# 🔎 Lab Verification

| ✅ Test                        | 🧾 Command                      | 🎯 Expected Result              |
| ----------------------------- | ------------------------------- | ------------------------------- |
| 🌐 Check IP address           | `ip a`                          | Correct Kali IP displayed       |
| 📡 Test gateway               | `ping 10.0.0.1`                 | Successful replies              |
| 🌍 Test Internet connectivity | `ping 8.8.8.8`                  | Successful replies              |
| 🔎 Test DNS resolution        | `nslookup networkwalks.com`     | Domain resolves                 |
| 🧰 Verify Nmap                | `nmap --version`                | Nmap version displayed          |
| 🔄 Verify snapshot            | Restore snapshot and run `ip a` | Baseline configuration restored |

---

# 🐞 Problems Encountered & Solutions

Documenting problems is an important part of the project.

## Problem 1. Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity worked on the first attempt but on trying a second time, it failed.

One workaround used during this lab was:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

The network connection was then restarted/rebooted and connectivity was tested again.

> **Important:** Network interface and connection names may differ between systems. Students should first identify their actual connection name before running an `nmcli` command.

---

# 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking

I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3. Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned that a clean snapshot should be created **before performing risky or experimental activities**.

This provides a known-good recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

---

# 🔐 Security & Ethical Use
This laboratory is intended strictly for education purposes only. All tools and techniques are confined to machines within this lab and are never to be used against systems without explicit permission.

---

# 🔗 Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)

---
# 👤 Author

**Michelle Mungai**\
Cybersecurity Professional B084

LinkedIn: [https://www.linkedin.com/in/waqaskarim/](https://www.linkedin.com/in/michellemungai/)

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
