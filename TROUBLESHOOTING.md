# TROUBLESHOOTING

A running log of issues and fixes encountered in the home lab.

---

## 2025-09-09 – Windows 10 forced Microsoft account
**Symptom:** OOBE required Microsoft account, no offline option  
**Fixes tried:**  
- Fake email trick → inconsistent in 22H2  
- ✅ **Solved:** `Shift + F10` → `OOBE\BYPASSNRO` (reboot) → “I don’t have Internet” → local account  
- Alt method: temporarily disable VM network adapter, then continue with limited setup  

---

## 2025-09-10 – Kali “No disk drive was detected”
**Symptom:** Installer couldn’t see any disk  
**Root Cause:** VM had no virtual hard disk attached (only ISO)  
**Fix:**  
- Add new **VDI** (20 GB) under **SATA**  
- Boot installer again → disk detected → guided partition OK  

**Evidence:**  
![Kali VM Storage Fix](Screenshots/Kali_VM_Storage_Fix_2025-09-10.png)  

---

## 2025-09-10 – Windows ICMP blocked (if ping fails later)
**Symptom:** Kali → Windows ping fails  
**Fix:** Enable Windows Defender Firewall inbound rule: **File and Printer Sharing (Echo Request – ICMPv4-In)**  

---

## 2025-09-10 – No Host-Only IP addresses
**Symptom:** No `192.168.56.x` on VM  
**Fix:**  
- Ensure Adapter 2 = Host-Only is enabled in VM settings  
- In guest: disable/enable the interface or reboot  

---

## 2025-09-15 – Missing Host-Only Adapter Option
**Symptom:** In VM → Settings → Network, only Adapter 1 was visible.  
**Root Cause:** On VirtualBox 7.x, Host-only adapters must be created first under **File → Tools → Network Manager**.  
**Fix:**  
1. Installed the VirtualBox Extension Pack from the official VirtualBox site.  
2. Navigated to **File → Tools → Network Manager**.  
3. Created a new Host-only Adapter (`VirtualBox Host-Only Ethernet Adapter`).  
4. Verified it appeared in VM settings under Adapter 2.  

**Evidence:**  
![Host-only Adapter Created](Screenshots/HostOnly_Adapter_Created_2025-09-15.png)  
