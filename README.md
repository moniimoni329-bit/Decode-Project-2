
\# 🚀 Server Commander: AWS Cloud Infrastructure Project



\*\*A hands-on cloud infrastructure deployment project demonstrating IaaS best practices on AWS.\*\*

\## 🎯 Project Overview



\*\*The Server Commander\*\* is a comprehensive, hands-on project that teaches real-world cloud infrastructure provisioning, security hardening, and application deployment on \*\*Amazon Web Services (AWS)\*\*.



\### What This Project Demonstrates

\- ✅ \*\*IaaS Concepts\*\*: Infrastructure as Code principles and virtual machine management

\- ✅ \*\*Cloud Security\*\*: Security Groups, firewall rules, and key-based authentication

\- ✅ \*\*Linux Administration\*\*: SSH access, package management, service configuration

\- ✅ \*\*Web Server Deployment\*\*: Nginx installation, configuration, and HTML hosting

\- ✅ \*\*Cloud Architecture\*\*: Understanding the shared responsibility model



\---



\## 📚 The 6-Phase Workflow



This project follows a structured 6-phase approach to take a server from concept to live production:



\### \*\*Phase 1: PROVISIONING\*\* 🖥️

Launch and configure an EC2 instance on AWS

\- Instance Type: `t2.micro` (AWS Free Tier eligible)

\- AMI: Amazon Linux 2023 (AWS-optimized)

\- Key Pair: Secure `.pem` file for SSH access

\- Storage: Default EBS configuration



\### \*\*Phase 2: SECURING THE PERIMETER\*\* 🔐

Configure Security Groups with least-privilege firewall rules



| Port | Service | Source | Status |

|------|---------|--------|--------|

| 22 | SSH | Your IP Only | 🔒 RESTRICTED |

| 80 | HTTP | 0.0.0.0/0 | 🌐 PUBLIC |

| 443 | HTTPS | 0.0.0.0/0 | 🌐 PUBLIC |



\### \*\*Phase 3: THE HANDSHAKE\*\* 🤝

Establish secure SSH connection using key-based authentication

```bash

chmod 400 keyname.pem

ssh -i keyname.pem ec2-user@<Public-IPv4>

```



\### \*\*Phase 4: DEPLOYING THE PAYLOAD\*\* ⚙️

Install and configure Nginx web server

```bash

sudo dnf update -y

sudo dnf install nginx -y

sudo systemctl start nginx

sudo systemctl enable nginx

```



\### \*\*Phase 5: CUSTOMIZING THE ASSET\*\* 🎨

Deploy custom HTML content to the web root

```bash

sudo nano /usr/share/nginx/html/index.html

```



\### \*\*Phase 6: VERIFICATION\*\* ✅

Test the live server by accessing the public IP in a browser

```

http://<EC2-Public-IP>

```



\---



\## 🏗️ Architecture Overview


```

┌─────────────────────────────────────────────────────┐

│              Internet (Public Access)               │

├─────────────────────────────────────────────────────┤

│                  Security Group                      │

│  (Firewall: Port 80 \& 443 Open, Port 22 Restricted) │

├─────────────────────────────────────────────────────┤

│                    AWS EC2 Instance                  │

│  ┌────────────────────────────────────────────────┐ │

│  │         Amazon Linux 2023 (OS Layer)           │ │

│  │  ┌──────────────────────────────────────────┐  │ │

│  │  │     Nginx Web Server                     │  │ │

│  │  │  (Listens on :80 \& :443)                │  │ │

│  │  │  ┌────────────────────────────────────┐  │  │ │

│  │  │  │   Custom HTML Content              │  │  │ │

│  │  │  │   /usr/share/nginx/html/           │  │  │ │

│  │  │  └────────────────────────────────────┘  │  │ │

│  │  └──────────────────────────────────────────┘  │ │

│  └────────────────────────────────────────────────┘ │

└─────────────────────────────────────────────────────┘


\## 🔑 Key Concepts Mastered



\### \*\*IaaS Model (Infrastructure as Code)\*\*

\- AWS provides and manages physical hardware, hypervisors, and networking

\- You own the OS, software stack, patches, and application security

\- Full control vs. managed services trade-off



\### \*\*Hypervisor \& Virtualization\*\*

\- AWS Nitro System creates isolated VM instances on shared physical hardware

\- Each instance runs independently without accessing host kernel

\- Resources allocated and monitored per instance



\### \*\*SSH Key Authentication\*\*

\- \*\*Public Key\*\* stored on the server (in `\~/.ssh/authorized\_keys`)

\- \*\*Private Key\*\* (.pem file) kept secure locally — \*\*NEVER share this\*\*

\- Lose the key = lose server access (no password reset!)


\## 🚀 Quick Start (From Scratch)



If you want to \*\*recreate this project\*\* yourself:



\### Prerequisites

\- AWS Account (with free tier eligibility)

\- SSH client (Terminal on Mac/Linux, PuTTY/WSL on Windows)

\- Browser to test the live server



\### Setup Steps (5 minutes)



1\. \*\*Launch EC2 Instance\*\*




```

✓ Phase 1: Instance Provisioning    \[COMPLETE]

✓ Phase 2: Security Configuration   \[COMPLETE]

✓ Phase 3: SSH Connection           \[COMPLETE]

✓ Phase 4: Nginx Deployment         \[COMPLETE]

✓ Phase 5: HTML Customization       \[COMPLETE]

✓ Phase 6: Live Server Verification \[COMPLETE]


MISSION STATUS: ✅ ACCOMPLISHED

=======
# Decode-Project-2
AWS Cloud Computing Project 2 – Server Commander. Deployed and configured a Linux EC2 instance, secured network access using Security Groups, configured SSH authentication, installed Nginx web server, and hosted a custom web page on AWS.

🚀 Server Commander: AWS Cloud Infrastructure Project

**A hands-on cloud infrastructure deployment project demonstrating IaaS best practices on AWS.**

![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![AWS](https://img.shields.io/badge/AWS-EC2-FF9900?style=for-the-badge&logo=amazonaws)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

---

## 🎯 Project Overview

**The Server Commander** is a comprehensive, hands-on project that teaches real-world cloud infrastructure provisioning, security hardening, and application deployment on **Amazon Web Services (AWS)**.

### What This Project Demonstrates
- ✅ **IaaS Concepts**: Infrastructure as Code principles and virtual machine management
- ✅ **Cloud Security**: Security Groups, firewall rules, and key-based authentication
- ✅ **Linux Administration**: SSH access, package management, service configuration
- ✅ **Web Server Deployment**: Nginx installation, configuration, and HTML hosting
- ✅ **Cloud Architecture**: Understanding the shared responsibility model

---

## 📚 The 6-Phase Workflow

This project follows a structured 6-phase approach to take a server from concept to live production:

### **Phase 1: PROVISIONING** 🖥️
Launch and configure an EC2 instance on AWS
- Instance Type: `t2.micro` (AWS Free Tier eligible)
- AMI: Amazon Linux 2023 (AWS-optimized)
- Key Pair: Secure `.pem` file for SSH access
- Storage: Default EBS configuration

### **Phase 2: SECURING THE PERIMETER** 🔐
Configure Security Groups with least-privilege firewall rules

| Port | Service | Source | Status |
|------|---------|--------|--------|
| 22 | SSH | Your IP Only | 🔒 RESTRICTED |
| 80 | HTTP | 0.0.0.0/0 | 🌐 PUBLIC |
| 443 | HTTPS | 0.0.0.0/0 | 🌐 PUBLIC |

### **Phase 3: THE HANDSHAKE** 🤝
Establish secure SSH connection using key-based authentication
```bash
chmod 400 keyname.pem
ssh -i keyname.pem ec2-user@<Public-IPv4>
```

### **Phase 4: DEPLOYING THE PAYLOAD** ⚙️
Install and configure Nginx web server
```bash
sudo dnf update -y
sudo dnf install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```

### **Phase 5: CUSTOMIZING THE ASSET** 🎨
Deploy custom HTML content to the web root
```bash
sudo nano /usr/share/nginx/html/index.html
```

### **Phase 6: VERIFICATION** ✅
Test the live server by accessing the public IP in a browser
```
http://<EC2-Public-IP>
```

## 🚀 Quick Start (From Scratch)

If you want to **recreate this project** yourself:

### Prerequisites
- AWS Account (with free tier eligibility)
- SSH client (Terminal on Mac/Linux, PuTTY/WSL on Windows)
- Browser to test the live server

### Setup Steps (5 minutes)

1. **Launch EC2 Instance**
   ```bash
   AWS Console → EC2 → Launch Instance
   - Name: Server-Commander-01
   - AMI: Amazon Linux 2023
   - Type: t2.micro
   - Download .pem key file
   ```

2. **Configure Security Group**
   ```
   Inbound Rules:
   - Port 22 (SSH): Your IP only
   - Port 80 (HTTP): 0.0.0.0/0
   - Port 443 (HTTPS): 0.0.0.0/0
   ```

3. **Connect via SSH**
   ```bash
   chmod 400 your-key.pem
   ssh -i your-key.pem ec2-user@<PublicIP>
   ```

4. **Install Nginx**
   ```bash
   sudo dnf update -y
   sudo dnf install nginx -y
   sudo systemctl start nginx
   sudo systemctl enable nginx
   ```

5. **Deploy Custom HTML**
   ```bash
   sudo nano /usr/share/nginx/html/index.html
   # Paste your HTML content
   # Ctrl+O → Enter → Ctrl+X
   ```

6. **Test in Browser**
   ```
   http://<Your-EC2-Public-IP>
   ```
## 🔒 Security Best Practices Applied

✅ **SSH Key Encryption**
- Private key permissions set to `400` (read-only)
- Public key authentication (no weak passwords)

✅ **Principle of Least Privilege**
- SSH restricted to your IP only
- Web traffic (80/443) open only when needed

✅ **Stateful Firewall**
- Security Groups default to deny-all
- Only explicitly allowed traffic passes through

✅ **Instance Hardening**
- Latest security patches via `dnf update`
- Firewall rules enforced at network level

### Future Hardening (Not in Scope for Project 2)
- [ ] SSL/TLS certificates (Let's Encrypt)
- [ ] fail2ban for brute-force protection
- [ ] VPC Flow Logs for audit trails
- [ ] CloudWatch monitoring & alarms
- [ ] Automated backups with EBS snapshots

See [SECURITY.md](./SECURITY.md) for detailed hardening strategies.

---

## 📚 Learning Resources

### AWS Documentation
- [EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [Security Groups Guide](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)
- [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)

### Web Server (Nginx)
- [Nginx Official Documentation](https://nginx.org/en/docs/)
- [Nginx Beginner's Guide](http://nginx.org/en/docs/beginners_guide.html)

### Linux/SSH
- [OpenSSH Manual](https://man.openbsd.org/ssh)
- [Linux File Permissions](https://www.linux.com/training-tutorials/understanding-linux-file-permissions/)

---


## 📝 Project Metadata

| Property | Value |
|----------|-------|
| **Project** | Server Commander (Project 2) |
| **Training** | DecodeLabs Cloud Computing Internship |
| **Batch** | 2026 |
| **Duration** | ~1-2 hours (hands-on) |
| **Cloud Provider** | Amazon Web Services (AWS) |
| **Primary Services** | EC2, Security Groups, VPC |
| **Difficulty** | Beginner → Intermediate |
| **Cost** | Free (AWS Free Tier) |

---

## 🤝 Contributing

This is an educational project. Contributions and improvements welcome:
1. Fork this repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -m "Add detailed docs"`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

---
---

## 📧 Contact & Support

**DecodeLabs Cloud Computing Program**
- Email: decodelabs.tech@gmail.com
- Website: www.decodelabs.tech
- Location: Greater Lucknow, India

---

## 🏆 Completion Status

```
✓ Phase 1: Instance Provisioning    [COMPLETE]
✓ Phase 2: Security Configuration   [COMPLETE]
✓ Phase 3: SSH Connection           [COMPLETE]
✓ Phase 4: Nginx Deployment         [COMPLETE]
✓ Phase 5: HTML Customization       [COMPLETE]
✓ Phase 6: Live Server Verification [COMPLETE]

MISSION STATUS: ✅ ACCOMPLISHED
```

**YOU ARE NOW A SERVER COMMANDER** 🎖️

---

**Last Updated**: June 2026  
**Project Version**: 1.0.0  
**Status**: Production Ready
