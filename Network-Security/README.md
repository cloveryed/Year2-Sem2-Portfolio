# Network Security: Enterprise Firewall & VPN Implementation

**Course:** Network Security, Year 2 Sem 3  
**Objective:** Design and implement a secure network architecture for a multinational company with offices in Singapore and Kuala Lumpur.  
**Tools Used:** Palo Alto NGFW (PA-Series), VMware, Wireshark, Network Simulation  
**Key Skills:** Next-Gen Firewall configuration, Site-to-Site VPN setup, Network segmentation, Security policy design, SSL decryption policies  
**Technologies:** IPSec VPN, VLAN segmentation, Application-aware policies, Threat prevention profiles  

## Project Overview!
- Conducted firewall comparison (Palo Alto vs Fortinet vs Cisco vs Sophos)
- Designed network architecture with DMZ, HR, IT, and Sales zones
- Configured Palo Alto NGFW for both Singapore and KL offices
- Implemented secure site-to-site VPN with IPSec/IKE
- Created granular security policies (application control, URL filtering, user access restrictions)
- Configured SSL decryption with banking website exclusions

## Key Configurations!
- **Zone-based security architecture**
- **Department-specific policies** (HR access to LinkedIn/Facebook, IT restrictions)
- **Decryption policies** (inspect all traffic except banking websites)
- **VPN configuration** with pre-shared keys and tunnel interfaces
- **NAT policies** for internet access
- **DHCP server configuration** for internal networks

## Testing & Validation!
- Verified inter-zone traffic routing
- Tested VPN connectivity between SG and KL offices
- Validated security policies (blocked/denied traffic as per requirements)
- Confirmed SSL decryption working for non-banking sites
- Tested application control (LinkedIn messaging blocked, Facebook chat restrictions)

## Assignment Document!
- [Full Assignment Report](./NS_Assignment_2025.docx)

## Learning Outcomes!
- Understanding of enterprise firewall selection criteria
- Hands-on experience with Palo Alto NGFW configuration
- Site-to-site VPN implementation skills
- Network segmentation and policy design
- Real-world testing and validation procedures
