# Day 5b – VM Network Connectivity Test (2025-09-15)

## Goal
Verify that the Windows 10 and Kali Linux VMs can communicate over the Host-Only network.  
This confirms both network configuration and firewall rules are correctly set.

---

## Steps Taken

### 1. Found Windows Host-Only IP
- Booted into the **Windows 10 VM**.  
- Opened **Command Prompt** → ran:

    ipconfig

- Found Host-only Adapter IP in the range `192.168.56.x`.

📸 *Screenshot Evidence:*  
![Windows Host-Only IP](../Screenshots/Windows_HostOnly_IP_2025-09-15.png)

---

### 2. Initial Ping Test (Kali → Windows)
- Booted into the **Kali Linux VM**.  
- Opened a terminal and ran:

    ping -c 4 192.168.56.101

- ❌ Result: Ping failed (`Destination Host Unreachable`).

📸 *Screenshot Evidence:*  
![Kali Ping Fail](../Screenshots/Kali_PingFail_2025-09-15.png)

---

### 3. Enabled Windows Firewall Rule
- Opened **Windows Defender Firewall → Advanced Settings**.  
- Located inbound rule: **File and Printer Sharing (Echo Request – ICMPv4-In)**.  
- Enabled the rule to allow ICMP echo requests.

📸 *Screenshot Evidence:*  
![Windows Firewall Rule Enabled](../Screenshots/Windows_Firewall_ICMP_2025-09-15.png)

---

### 4. Retested Ping (Kali → Windows)
- Re-ran the same command in Kali:

    ping -c 4 192.168.56.101

- ✅ Result: Ping successful → 4 packets transmitted, 4 received, 0% packet loss.

📸 *Screenshot Evidence:*  
![Kali Ping Success](../Screenshots/Kali_PingSuccess_2025-09-15.png)

---

## Outcome
- Verified connectivity between **Windows 10 VM** and **Kali VM** over Host-Only network.  
- Network configuration is correct and firewall rules are properly set.  
- The environment is now ready for the next step.

---

## Next Step
- **Lab 2 – Network Configuration Write-Up**  
- Perform the **first Nmap scan** (Kali → Windows).
