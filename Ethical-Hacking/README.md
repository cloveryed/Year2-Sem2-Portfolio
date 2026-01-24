# Ethical Hacking: Penetration Testing Simulation

**Course:** Ethical Hacking, Year 2 Sem 3  
**Objective:** Conduct a comprehensive penetration test on a simulated SME network to identify and exploit security vulnerabilities.  
**Tools Used:** Kali Linux, Metasploit, Mimikatz, EternalBlue, vsftpd 2.3.4, Wireshark, Proxychains  
**Key Skills:** Vulnerability exploitation, Lateral movement, Credential dumping, Post-exploitation, Persistence establishment  
**Methodology:** Reconnaissance → Initial Access → Privilege Escalation → Lateral Movement → Persistence → Exfiltration  

## Target Assessment!
- **Target:** ChickenCheck SME network (simulated environment)
- **Architecture:** Ubuntu server (vsftpd), Windows 10 client, Kali Linux attacker
- **Scope:** External FTP server, internal Windows systems, network pivoting, data exfiltration

## Key Findings & Exploits!

### Critical Vulnerabilities
- **vsftpd 2.3.4 Backdoor (CVE-2011-2523)** - Unauthenticated remote command execution
- **EternalBlue (MS17-010)** - SMBv1 remote code execution on unpatched Windows 10
- **Weak Session Management** - Session persistence across user logins
- **Missing Security Patches** - Outdated vsftpd and unpatched Windows systems

### Medium Severity
- **Default Configuration** - Anonymous FTP enabled on production server
- **Weak Credential Storage** - NTLM hashes stored without proper protection
- **Poor Network Segmentation** - Internal systems accessible from compromised DMZ

### Security Controls Bypassed
- **Antivirus Evasion** - Payload generation and execution bypassing Windows Defender
- **Log Clearing** - Successful removal of Windows event logs
- **Persistence Mechanisms** - Backdoor installation surviving system reboots

## Tools & Techniques!
- **Exploitation:** Metasploit Framework, custom payloads
- **Post-Exploitation:** Mimikatz (Kiwi module), CrackMapExec, Pass-the-Hash
- **Lateral Movement:** SMB exploitation, PSExec, credential reuse
- **Persistence:** Meterpreter backdoors, registry modifications
- **Coverage:** Log clearing, anti-forensics techniques

## Attack Chain!
1. **Initial Compromise:** vsftpd backdoor exploitation → root access on Ubuntu server
2. **Reconnaissance:** Network scanning from compromised Ubuntu host
3. **Pivoting:** SOCKS proxy setup → internal network access
4. **Lateral Movement:** EternalBlue exploitation → Windows 10 compromise
5. **Privilege Escalation:** SYSTEM privilege acquisition via Mimikatz
6. **Credential Harvesting:** NTLM hash dumping and Pass-the-Hash attacks
7. **Persistence:** Backdoor installation and scheduled task creation
8. **Exfiltration:** Simulated ransomware deployment and data encryption

## Defensive Gaps Identified!
### Technical Controls
- Lack of patch management for critical services
- Insufficient network segmentation between DMZ and internal networks
- Absence of endpoint detection and response (EDR) solutions
- Poor password policies and credential management

### Operational Issues
- No security monitoring or SIEM implementation
- Missing incident response procedures
- Inadequate backup and recovery processes
- Lack of employee security awareness training

## Learning Outcomes!
- Practical experience with full penetration testing lifecycle
- Hands-on exploitation of real-world vulnerabilities (vsftpd, EternalBlue)
- Advanced post-exploitation techniques (Mimikatz, Pass-the-Hash)
- Network pivoting and lateral movement strategies
- Anti-forensics and persistence mechanisms
- Professional penetration testing reporting and documentation

## Assignment Document!
- [Full Penetration Test Report](./T02_GRP4_EH_ASSG_2025.docx)

## Recommendations!
### Immediate Actions (24-48 hours)
1. **Patch Critical Vulnerabilities**
   - Update vsftpd to latest version or disable anonymous access
   - Apply MS17-010 patches to all Windows systems
   - Disable SMBv1 protocol where not required

2. **Network Segmentation**
   - Implement strict firewall rules between DMZ and internal networks
   - Isolate critical systems (finance, HR) from general network
   - Implement VLAN segmentation by department

3. **Credential Management**
   - Enforce strong password policies (minimum 12 characters, complexity)
   - Implement multi-factor authentication for administrative access
   - Regularly rotate service account passwords

### Short-term (1-4 weeks)
1. **Monitoring & Detection**
   - Deploy SIEM solution with alerting for suspicious activities
   - Implement endpoint detection and response (EDR) on all systems
   - Set up centralized logging with immutable storage

2. **Access Control**
   - Implement principle of least privilege for all user accounts
   - Regular review of administrative privileges
   - Session timeout enforcement (15-30 minutes of inactivity)

3. **Backup & Recovery**
   - Implement 3-2-1 backup strategy (3 copies, 2 media types, 1 offsite)
   - Regular backup testing and restoration drills
   - Air-gapped backups for critical systems

### Long-term (1-6 months)
1. **Security Program Development**
   - Establish formal patch management process
   - Implement security awareness training program
   - Develop and test incident response plan
   - Regular penetration testing and vulnerability assessments

2. **Technical Controls Enhancement**
   - Implement application whitelisting
   - Deploy network segmentation with micro-segmentation
   - Implement deception technologies (honeypots)
   - Regular security configuration reviews

3. **Compliance & Governance**
   - Align with industry frameworks (NIST, ISO 27001)
   - Regular security audits and compliance checks
   - Executive-level security reporting and metrics

**Note:** This penetration test was conducted in a controlled, isolated lab environment as part of academic training. All techniques demonstrated were performed with proper authorization and within legal boundaries for educational purposes.
