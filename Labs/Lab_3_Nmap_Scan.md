# Lab 3 – First Network Scan with Nmap

## Objective
To perform a basic network scan from Kali Linux against the Windows 10 VM using nmap, verifying connectivity and identifying open services.

## Introduction
Network scanning is a fundamental skill in cybersecurity. This lab demonstrates the use of nmap for host discovery and service detection in a safe, isolated lab environment.

As a student building my first scanning lab, this exercise helps me understand how attackers and defenders map systems on a network.

## Tools Used
- **Kali Linux (2025.2)** with nmap
- **Windows 10 (22H2)** as the scan target
- **VirtualBox Host-Only Network** (192.168.56.0/24)

## Methodology

### Phase 1: Identify Windows Host-Only IP
- On Windows VM, ran `ipconfig`.
- Host-Only IP: `192.168.56.101`.

### Phase 2: Run Host Discovery (Ping Scan)
- On Kali VM, ran:
  `nmap -sn 192.168.56.101`
- Result: Host is up.

📸 Evidence:

![Host Discovery Scan](../Screenshots/Kali_Nmap_HostDiscovery_2025-09-20.png)

### Phase 3: Run Service & Version Detection
- On Kali VM, ran:
  `nmap -sV 192.168.56.101`
- Result: All 1000 TCP ports filtered (Windows Firewall blocked responses).

📸 Evidence:

![Service Detection Scan](../Screenshots/Kali_Nmap_ServiceScan_2025-09-20.png)

## Evidence of Success
- Nmap confirmed Windows VM is online and reachable.
- Service detection scan returned filtered ports, consistent with Windows Firewall defaults.

## Analysis & Observations
## Analysis & Observations
- Connectivity verified — Windows responded to host discovery probes.
- Service scan returned only filtered ports, showing Windows Firewall is blocking probes.
- **Security Insight:** The filtered ports result is significant from a defensive perspective. Unlike "closed" ports (which respond with RST packets), "filtered" indicates a firewall is actively dropping packets. This tells an attacker that: (1) a firewall exists, (2) it's configured to silently drop unauthorized traffic, and (3) further enumeration requires firewall bypass techniques. In a real assessment, this would inform the next phase of testing.
- A default Windows 10 system demonstrates secure-by-default configurations with no openly exposed services.

---

## Conclusion
This lab successfully used nmap from Kali to discover the Windows 10 VM and attempt service enumeration. The lack of open ports highlights how firewalls protect systems from reconnaissance.

As my first scanning lab, it bridges connectivity (Lab 2) and network reconnaissance.

## Next Steps
- None for now...

## References
- [Nmap Reference Guide](https://nmap.org/book/man.html)
- [Kali Linux Documentation](https://www.kali.org/docs/)
