# Nmap Network Scan – Cyber Security Internship Task

## Task Summary
Performed a TCP SYN scan on the local network using Nmap to identify live hosts and open ports.

## Tools Used
- Nmap v7.97
- Windows Command Prompt

## Target Range
Scanned: 192.168.24.0/24

## Steps Performed
1. Installed Nmap and added it to system PATH.
2. Identified local IP using `ipconfig`.
3. Scanned the network using:`nmap -sS 192.168.24.0/24`
4. Saved output using:`nmap -sS 192.168.24.0/24 -oN myscan.txt`

## Key findings:
- Open ports: 53 (DNS), 135 (MSRPC), 139 (NetBIOS), 443 (HTTPS), 445 (SMB), 1521 (Oracle), 3306 (MySQL), 8090 (Ops Messaging)
- Some ports filtered (SMTP, POP3, AFP)
- Services running that may require attention for security hardening.

## Analysis of Results

The following ports were found open:
- 135 (MSRPC): Used by Windows services, may be vulnerable to DCOM exploits.
- 139, 445 (NetBIOS & SMB): Commonly exploited in ransomware attacks.
- 3306 (MySQL): Indicates a database server — could be targeted for SQL injection if exposed.
- 1521 (Oracle): Oracle DB — should be firewalled.
- 443 (HTTPS): Secure web traffic — usually safe if patched.

These services should be monitored and restricted using a firewall if not in use.

![image](https://github.com/user-attachments/assets/66739522-eaa4-4387-a7dd-2926d3548e2b)
