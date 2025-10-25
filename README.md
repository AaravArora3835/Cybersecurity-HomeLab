# Cybersecurity Home Lab

## Overview
Self-contained virtualized environment for practicing cybersecurity fundamentals safely. Demonstrates VM configuration, network isolation, and basic reconnaissance skills.

## Technical Environment
- **Hypervisor:** Oracle VirtualBox 7.2
- **Systems:** Windows 10 (22H2) target, Kali Linux (2025.2) attacker platform
- **Network Design:** Dual-adapter configuration (NAT for internet access, Host-Only for isolated testing)
- **Host Machine:** Windows 11 Home, Intel i7-12700H, 16 GB RAM, 512 GB SSD

## Skills Demonstrated

| Category | Skill | Evidence |
|----------|-------|----------|
| Infrastructure | VM installation & configuration | [Lab 1](Labs/Lab_1_Initial_Setup.md) |
| Networking | Host-Only network setup & dual-NIC configuration | [Lab 2](Labs/Lab_2_Network_Config.md) |
| Security Tools | Nmap reconnaissance (host discovery, service detection) | [Lab 3](Labs/Lab_3_Nmap_Scan.md) |
| Troubleshooting | Firewall analysis & ICMP rule configuration | [TROUBLESHOOTING.md](TROUBLESHOOTING.md) |
| Documentation | Professional lab reports with evidence | [All Labs](Labs/) |

## Key Projects

### Network Isolation Architecture
Configured dual-NIC setup preventing accidental LAN exposure during security testing. NAT adapter provides internet access for updates while Host-Only adapter creates isolated 192.168.56.0/24 subnet for VM-to-VM communication.

### Connectivity Troubleshooting
Diagnosed and resolved ICMP blocking between Kali Linux and Windows 10. Root cause identified as Windows Firewall default-deny rule. Remediated by enabling File and Printer Sharing (Echo Request – ICMPv4-In) inbound rule.

### Reconnaissance Practice
Performed host discovery and service enumeration with nmap. Analyzed filtered port responses to understand firewall behavior and defensive posture of default Windows configurations.

## Repository Structure
```
├── Labs/                    # Polished lab reports with objectives, methodology, evidence
├── Notes/                   # Daily learning logs and lessons learned
├── Guides/                  # Reusable documentation (snapshots, networking)
├── Screenshots/             # Timestamped evidence files
├── TROUBLESHOOTING.md       # Symptom → Cause → Fix log
└── RESOURCES.md             # Official documentation references
```

## Labs Completed

1. **[Building the Foundational Home Lab Environment](Labs/Lab_1_Initial_Setup.md)**  
   VirtualBox installation, Windows 10 and Kali Linux VM creation, initial OS configuration

2. **[VirtualBox Host-Only Networking & VM Connectivity](Labs/Lab_2_Network_Config.md)**  
   Dual-adapter setup, IP verification, connectivity testing with ping

3. **[First Network Scan with Nmap](Labs/Lab_3_Nmap_Scan.md)**  
   Host discovery, service/version detection, firewall behavior analysis

## Portfolio Context
This lab provided the foundation for hands-on practice while pursuing CompTIA Security+ and Google Cybersecurity certifications. Demonstrates ability to build controlled test environments independently.

## Part of Larger Journey

**Full Portfolio:** [Cybersecurity-Portfolio-Hub](https://github.com/AaravArora3835/Cybersecurity-Portfolio-Hub)

**Related Projects:**
- [SecureScholar Platform](https://github.com/AaravArora3835/SecureScholar-Platform) — Gamified cybersecurity learning platform  
- [Google Cybersecurity Certificate](https://github.com/AaravArora3835/Google-Cybersecurity-Certificate) — Foundational certification journey

## Technical References
- [Oracle VirtualBox Manual](https://www.virtualbox.org/manual/)  
- [Kali Linux Documentation](https://www.kali.org/docs/)  
- [Nmap Reference Guide](https://nmap.org/book/man.html)
