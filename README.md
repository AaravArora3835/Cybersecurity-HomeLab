# Cybersecurity Home Lab

A step-by-step documentation of building and configuring a personal cybersecurity home lab using VirtualBox, Windows 10, and Kali Linux. Includes installation notes, troubleshooting logs, and daily progress tracking.

---

## Repository Structure

- /Notes → Daily logs (Day1, Day2, ...)
- /Screenshots → Captured evidence for each step
- /Labs → Formal write-ups of completed labs
- /Guides → How-to guides (VirtualBox, Snapshots, Networking)
- TROUBLESHOOTING.md
- RESOURCES.md
- README.md

---

## Daily Progress

### Day 1 – VirtualBox Setup
- Installed VirtualBox  
- Created placeholder VMs  
- Added first screenshots

**Evidence:**  
![VirtualBox Installed](Screenshots/VirtualBox_7.2_Installed_2025-09-08.png)

---

### Day 2 – Windows 10 Test VM
- Installed Windows 10 in VirtualBox  
- Solved Microsoft account requirement using bypass trick  
- Created local user `labuser`

**Evidence:**  
![Windows10 OOBE Bypass](Screenshots/Win10_OOBE_Bypass_2025-09-08.png)  
![Windows10 Desktop](Screenshots/Win10_Desktop_2025-09-08.png)

---

### Day 3 – Kali Linux VM
- Downloaded Kali Linux ISO  
- Created new VM in VirtualBox  
- Installed Kali with default tools and XFCE  
- Verified VM boots successfully  

**Evidence:**  
![Kali ISO Download](Screenshots/Kali_ISO_DownloadPage_2025-09-10.png)  
![Kali VM Storage](Screenshots/Kali_VM_Storage_2025-09-10.png)  
![Kali Partitioning](Screenshots/Kali_Partitioning_2025-09-10.png)  
![Kali Desktop](Screenshots/Kali_Desktop_2025-09-10.png)

---

### Day 4 – Repo Structure Upgrade
- Added `/Labs` and `/Guides` folders  
- Added `TROUBLESHOOTING.md` and `RESOURCES.md`  
- Wrote **Lab 1 – Initial Setup** report  
- Added **Guide – VirtualBox Networking**

---

### Day 5a – Host-Only Networking Setup
- Created Host-Only Adapter in VirtualBox **Global Tools → Network Manager**  
- Attached Adapter 2 (Host-only) for both Windows and Kali VMs  
- Verified both VMs now have a `192.168.56.x` address  

**Evidence:**  
![Host-only Adapter Created](Screenshots/HostOnly_Adapter_Created_2025-09-15.png)  
![Kali Host-only Adapter](Screenshots/Kali_HostOnly_Adapter_2025-09-15.png)

---

### Day 5b – VM Connectivity Test
- Found IP address of Windows VM (`ipconfig`)  
- From Kali, attempted ping → failed initially (ICMP blocked)  
- Enabled Windows Firewall rule: **File and Printer Sharing (Echo Request - ICMPv4-In)**  
- Retested → successful ping between Kali and Windows 🎉  

**Evidence:**  
![Kali Ping Fail](Screenshots/Kali_Ping_Fail_2025-09-15.png)  
![Kali Ping Success](Screenshots/Kali_Ping_Success_2025-09-15.png)
