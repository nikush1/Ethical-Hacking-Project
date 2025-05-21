# 🛡 Practical Network Penetration Testing: Exploitation & Defense

## Project Overview
A hands-on cybersecurity exercise demonstrating real-world vulnerability discovery, exploitation techniques, and defensive remediation strategies using industry-standard tools.

## 📖 Introduction
As digital infrastructure expands, proactive security testing becomes essential. This project creates a safe laboratory environment where learners can:
- Practice ethical hacking techniques
- Understand attacker methodologies
- Develop practical remediation skills

## 💡 Core Concepts
**Penetration Testing Methodology:**
1. **Discovery:** Identify systems and services
2. **Vulnerability Analysis:** Detect weaknesses
3. **Exploitation:** Validate security flaws
4. **Reporting:** Document findings and solutions

**Lab Environment:**
- **Attacker Platform:** Kali Linux (Offensive security tools)
- **Target System:** Metasploitable (Deliberately vulnerable VM)

## 🚀 Testing Phases

### Phase 1: Information Gathering
| Task | Command | Purpose |
|------|---------|---------|
| Network Discovery | `nmap -v [IP_RANGE]` | Identify active hosts |
| Comprehensive Scan | `nmap -v -p- [TARGET_IP]` | Detect all open ports |
| Service Analysis | `nmap -v -sV [TARGET_IP]` | Determine service versions |
| OS Fingerprinting | `nmap -v -O [TARGET_IP]` | Identify operating system |

### Phase 2: Vulnerability Assessment
**Sample Findings:**
## 💡 Visual Flowchart

```plaintext
[ Network Scanning ] → [ Reconnaissance ] → [ Enumeration ] → [ Exploitation ]
            ↓                  ↓                  ↓                 ↓
   Basic Scan (nmap)   Hidden Ports, OS, Service  Info Gathering  Exploit 3 Services
            ↓
[ Privilege Escalation ] → [ Password Cracking ] → [ Remediation ]
     ↓                             ↓                     ↓
 Create Root User            Crack Hashes          Recommend Fixes

```
--

## ⚙ Project Requirements

- **Operating Systems:**
  - Kali Linux (Attacking Machine)
  - Metasploitable (Target Machine)

- **Tools Used:**
  - Nmap
  - John the Ripper
  - Metasploit Framework
  - Other enumeration and exploitation tools

---
## 🌐 Network Scanning

### ✅ Task 1: Basic Network Scan

1. Open a terminal on your Kali Linux machine.
2. Run a basic scan on your local network:
   ```bash
   nmap -v YOUR_IP_RANGE

## 🔎 Reconnaissance
### ✅ Task 1: Scanning for Hidden Ports

Scan all ports on the targeted IP address:
```bash
nmap -v -p- YOUR_TARGET_IP_ADDRESS
```
### ✅ Task 2: Service Version Detection
Detect the version of services running on open ports:
```bash
nmap -v -sV YOUR_TARGET_IP_ADDRESS
```

### ✅ Task 3: Operating System Detection
Detect the operating system of target devices:
```bash
nmap -v -O YOUR_TARGET_IP_ADDRESS
```

## 📋 Enumeration
Target IP Address: ENTER_YOUR_TARGET_IP_ADDRESS

Operating System Details: ADD_YOUR_TARGET_OS_DETAILS

MAC Address: 00:0C:29:5D:FE:0B (VMware)

Device Type: General purpose

Running: Linux 2.6.X

OS CPE: cpe:/o:linux:linux_kernel:2.6

OS Details: Linux 2.6.9 - 2.6.33

### Services Version (excluding hidden ports)
| PORT   | STATE | SERVICE | VERSION                             |
| ------ | ----- | ------- | ----------------------------------- |
| 21/tcp | open  | ftp     | vsftpd 2.3.4                        |
| 22/tcp | open  | ssh     | OpenSSH 4.7p1 Debian 8ubuntu1 (2.0) |

### Hidden Ports with Service Versions
| PORT      | STATE | SERVICE  | VERSION                                        |
| --------- | ----- | -------- | ---------------------------------------------- |
| 8787/tcp  | open  | drb      | Ruby DRb RMI (Ruby 1.8; /usr/lib/ruby/1.8/drb) |
| 47436/tcp | open  | mountd   | 1-3 (RPC #100005)                              |
| 50918/tcp | open  | java-rmi | GNU Classpath grmiregistry                     |
| 59995/tcp | open  | nlockmgr | 1-4 (RPC #100021)                              |
| 60004/tcp | open  | status   | 1 (RPC #100024)                                |

## Exploitation of Services
Exploit at least 3 services from the discovered services list.

## 🔑 Create User with Root Permission

### Create a new user:
```bash
adduser your_name
```
Set a simple password (e.g., 12345, hello, 987654321).

### Get user details:
```bash
cat /etc/passwd
```

### Get password hash:
```bash
cat /etc/shadow
```

🔓 Cracking Password Hashes
Store the password hash in a text file (e.g., hashes.txt).

### Crack the hash using John the Ripper:
```bash
john hashes.txt
```
### Display the cracked password:
```bash
john hashes.txt --show
```

## 🛡 Remediation
Research vulnerabilities discovered during scanning and exploitation.

Recommend proper fixes and patches.

Provide references.

If services are outdated, include:

- Current version used in the system.
- Latest secure version for comparison.
