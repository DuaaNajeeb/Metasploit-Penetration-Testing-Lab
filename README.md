# Metasploit Penetration Testing Lab

## Overview
This project documents a hands-on penetration testing lab using the Metasploit Framework against a Metasploitable 2 virtual machine. The objective is to understand exploitation workflows, analyze common security weaknesses, interpret tool output, and recommend appropriate remediation measures.

## Objectives
- Explore and configure Metasploit modules using `msfconsole`.
- Understand vulnerabilities affecting FTP and Apache Tomcat services.
- Demonstrate the security risks of weak default credentials.
- Examine credential exposure over unencrypted HTTP traffic.
- Document exploitation attempts, technical challenges, and remediation strategies.

## Lab Environment

| Component | Details |
|---|---|
| Attacker Machine | Kali Linux |
| Target Machine | Metasploitable 2 |
| Attacker IP | `192.168.1.4` |
| Target IP | `192.168.1.3` |
| Primary Tool | Metasploit Framework |

**Important:** All testing is intended for an isolated, authorized lab environment.

## Tasks Performed

### 1. VSFTPD 2.3.4 Backdoor
- Module: `exploit/unix/ftp/vsftpd_234_backdoor`
- Objective: Examine a known backdoor vulnerability in a compromised version of the FTP service.
- Result: The exploitation attempt encountered payload and LHOST configuration errors. Successful exploitation was not confirmed in this lab.

### 2. Apache Tomcat Manager Exploitation
- Module: `exploit/multi/http/tomcat_mgr_upload`
- Objective: Demonstrate the risk of weak default credentials on the Tomcat Manager interface.
- Result: The module successfully established a Meterpreter session under the `tomcat55` service account, confirming code execution without root privileges.

### 3. Network Traffic Sniffing
- Module: `auxiliary/sniffer/psnuffle`
- Objective: Investigate the exposure of credentials transmitted over unencrypted HTTP.
- Result: The expected credential-capture behavior was documented, but successful live capture was not confirmed because of tool and permission limitations.

## Security Findings
- Backdoored software can provide unauthorized remote access.
- Default administrative credentials can enable unauthorized application deployment and remote code execution.
- HTTP Basic Authentication over unencrypted HTTP can expose credentials to network interception.

## Recommended Mitigations
- Replace compromised software with verified, trusted versions.
- Change default credentials and enforce strong, unique passwords.
- Restrict administrative interfaces to trusted hosts and networks.
- Enforce HTTPS/TLS for sensitive web interfaces.
- Apply firewall rules and network segmentation.
- Monitor systems for suspicious authentication and application-deployment activity.

## Documentation
The accompanying report includes the lab setup, commands, screenshots, module configuration, analysis of findings, technical limitations, and remediation recommendations.

## Disclaimer
This project is for educational purposes only. Perform security testing only on systems you own or have explicit authorization to assess.

## Author
Doaa Najeeb Badwan

Cybersecurity Student | Birzeit University

## Year
2026
