# Day 6 – Lab 2: Networking & Connectivity (2025-09-19)

## Goal
Establish direct communication between the Windows 10 and Kali Linux VMs over the **VirtualBox Host-Only network**, confirm bidirectional connectivity, and document the process as part of Lab 2.

---

## Steps Taken

### 1. Verified Windows Host-Only IP
- Booted into the **Windows 10 VM**.  
- Ran `ipconfig` in Command Prompt.  
- Located the Host-Only Adapter IP in the `192.168.56.x` subnet.  

📸 *Screenshot Evidence:*  
![Windows Host-Only IP](../Screenshots/Windows_VM_HostOnly_IP_2025-09-16.png)  

---

### 2. Verified Kali Host-Only IP
- Booted into the **Kali Linux VM**.  
- Ran `ip -4 a` to list IPv4 addresses.  
- Confirmed Host-Only Adapter also in the `192.168.56.x` subnet.  

📸 *Screenshot Evidence:*  
![Kali Host-Only IP](../Screenshots/Kali_VM_HostOnly_IP_2025-09-16.png)  

---

### 3. Initial Connectivity Test (Kali → Windows)
- From Kali, attempted to ping the Windows IP:  
  `ping -c 4 192.168.56.101`  
- ❌ Result: `Destination Host Unreachable`.  

📸 *Screenshot Evidence:*  
![Kali Ping Fail](../Screenshots/Kali_Ping_Windows_Fail_2025-09-16.png)  

---

### 4. Fixed with Windows Firewall Rule
- Opened **Windows Defender Firewall → Advanced Settings**.  
- Located inbound rule: **File and Printer Sharing (Echo Request – ICMPv4-In)**.  
- Enabled the rule to allow ICMP echo requests.  

📸 *Screenshot Evidence:*  
![Windows Firewall Rule Enabled](../Screenshots/Windows_Firewall_ICMP_Enable_2025-09-16.png)  

---

### 5. Retested Connectivity
- Re-ran ping from Kali → Windows:  
  `ping -c 4 192.168.56.101`  
- ✅ Result: 4 packets transmitted, 4 received, 0% packet loss.  

📸 *Screenshot Evidence:*  
![Kali Ping Success](../Screenshots/Kali_Ping_Windows_Success_2025-09-16.png)  

---

### 6. Optional Reverse Test (Windows → Kali)
- From Windows, ran:  
  `ping 192.168.56.102`  
- ✅ Result: Successful replies from Kali VM.  
- (Screenshot optional, not required for Lab 2 write-up.)

---

## Outcome
- **Confirmed bidirectional connectivity** between Windows 10 and Kali Linux over the Host-Only network.  
- Firewall correctly configured to allow ICMP traffic.  
- This lab proves that the VMs can communicate securely in an isolated environment, forming the foundation for more advanced scans and attacks.  
