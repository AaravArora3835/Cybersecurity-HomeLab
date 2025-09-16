# TROUBLESHOOTING

A running log of issues and fixes encountered in the home lab.

---

## Issue: Windows 10 Forced Microsoft Account  
**Date:** 2025-09-09  
**VM/Tool Affected:** Windows 10 VM  

**Problem:**  
During OOBE setup, Windows 10 required a Microsoft account.  
No option was available to create a local account.  

**Cause:**  
Recent Windows 10 versions (22H2) hide the offline account option if an internet connection is present.  

**Solution:**  
1. Pressed `Shift + F10` during setup.  
2. Ran command: `OOBE\BYPASSNRO`.  
3. VM rebooted and displayed the “I don’t have Internet” option.  
4. Chose that option to set up a local account.  
5. Alternate method: temporarily disable the VM’s network adapter before setup.  

**Evidence:**  
*(No screenshot captured for this issue — textual documentation only.)*  

---

## Issue: Kali “No Disk Drive Was Detected”  
**Date:** 2025-09-10  
**VM/Tool Affected:** Kali Linux VM  

**Problem:**  
The installer could not detect any disk to partition.  

**Cause:**  
The VM was created without a virtual hard disk (only the ISO was attached).  

**Solution:**  
1. Powered off the VM.  
2. Added a new **20 GB VDI** under **SATA Controller**.  
3. Rebooted and relaunched the installer.  
4. The disk was detected and installation continued with guided partitioning.  

**Evidence:**  
- ![Kali VM Storage Fix](../Screenshots/Kali_VM_Storage_Fix_2025-09-10.png)  

---

## Issue: Windows ICMP Blocked (Ping Fails)  
**Date:** 2025-09-10  
**VM/Tool Affected:** Windows 10 VM  

**Problem:**  
Ping attempts from Kali to Windows failed.  

**Cause:**  
Windows Defender Firewall blocks ICMP (ping) requests by default.  

**Solution:**  
1. Opened **Windows Defender Firewall → Advanced Settings**.  
2. Enabled inbound rule: **File and Printer Sharing (Echo Request – ICMPv4-In)**.  
3. Retested ping from Kali → Windows successfully.  

**Evidence:**  
*(No screenshot captured for this issue — textual documentation only.)*  

---

## Issue: No Host-Only IP Addresses  
**Date:** 2025-09-10  
**VM/Tool Affected:** Windows 10 & Kali Linux VMs  

**Problem:**  
No `192.168.56.x` addresses appeared on either VM.  

**Cause:**  
The Host-only Adapter was enabled but not active inside the guest OS.  

**Solution:**  
1. Verified **Adapter 2 = Host-only** was enabled in VM settings.  
2. Disabled and re-enabled the adapter inside the VM.  
3. Rebooted the guest OS if needed.  
4. IP addresses in the `192.168.56.x` range were assigned successfully.  

**Evidence:**  
*(No screenshot captured for this issue — textual documentation only.)*  

---

## Issue: Missing Host-Only Adapter Option  
**Date:** 2025-09-15  
**VM/Tool Affected:** VirtualBox (global settings)  

**Problem:**  
In VM → Settings → Network, only Adapter 1 was visible.  
There was no option to attach a Host-only adapter.  

**Cause:**  
On VirtualBox 7.x, Host-only adapters must be created first under  
**File → Tools → Network Manager**.  

**Solution:**  
1. Installed the VirtualBox Extension Pack from the official VirtualBox site.  
2. Navigated to **File → Tools → Network Manager**.  
3. Created a new Host-only Adapter (`VirtualBox Host-Only Ethernet Adapter`).  
4. Verified it appeared in VM settings under Adapter 2.  

**Evidence:**  
- ![Host-only Adapter Created](../Screenshots/HostOnly_Adapter_Created_2025-09-15.png)  
