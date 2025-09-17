
---

## `TROUBLESHOOTING.md` (updated)

# TROUBLESHOOTING

A running log of issues and fixes encountered in the home lab.

---

## 2025-09-09 – Windows 10 forced Microsoft account
**Symptom:** OOBE required Microsoft account, no offline option  
**Fixes tried:**  
- Fake email trick → inconsistent in 22H2  
- ✅ **Solved:** `Shift + F10` → `OOBE\BYPASSNRO` (reboot) → “I don’t have Internet” → local account  
- Alt method: disable VM network adapter, then continue with limited setup  

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

## 2025-09-15 – Missing Host-Only Adapter Option
**Symptom:** No Adapter 2 available in VM network settings  
**Root Cause:** Host-only adapter wasn’t created globally  
**Fix:**  
1. Installed VirtualBox Extension Pack  
2. File → Tools → Network Manager → Created Host-only Adapter  
3. Adapter now appears in VM settings  
**Evidence:**  
![Host-only Adapter Created](Screenshots/HostOnly_Adapter_Created_2025-09-15.png)

---

## 2025-09-15 – Kali to Windows Ping Fails
**Symptom:** Ping from Kali to Windows timed out  
**Cause:** Windows Firewall blocked ICMP requests  
**Fix:** Enabled inbound rule **File and Printer Sharing (Echo Request – ICMPv4-In)**  
**Evidence:**  
- Before: ![Kali Ping Fail](Screenshots/Kali_Ping_Fail_2025-09-15.png)  
- After: ![Kali Ping Success](Screenshots/Kali_Ping_Success_2025-09-15.png)
