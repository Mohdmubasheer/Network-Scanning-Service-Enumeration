# Network Scanning & Service Enumeration Lab

## Objective
To perform network scanning and identify open ports, running services, and potential security risks.

---

## Lab Environment
- Attacker Machine: Kali Linux
- Target Machine: Metasploitable 2
- Tool Used: Nmap

---

## Host Discovery

Command Used:
nmap -sn 192.168.1.0/24

---

## Service Enumeration

Command Used:
nmap -sC -sV 192.168.1.170

---

## Open Ports Identified

| Port | Service | Version |
|------|----------|----------|
| 21 | FTP | vsftpd 2.3.4 |
| 22 | SSH | OpenSSH 4.7 |
| 23 | Telnet | - |
| 80 | HTTP | Apache 2.2.8 |

---

## Vulnerability Research

### vsftpd 2.3.4
- CVE ID: CVE-2011-2523
- Severity: Critical
- CVSS Score: 10.0
- Description: Contains a backdoor vulnerability allowing remote command execution.
- Recommendation: Upgrade FTP service.

### Telnet Service
- Risk: Credentials transmitted in plaintext.
- Recommendation: Disable Telnet and use SSH.

### Apache 2.2.8
- Risk: Outdated web server with known vulnerabilities.
- Recommendation: Update Apache to latest version.

---

## Conclusion

The system contains outdated services which increase the attack surface. Regular vulnerability scanning and patch management are required.
