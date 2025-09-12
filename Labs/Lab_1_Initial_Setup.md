# Lab 1 – Initial Setup

## Goal
Document how the home lab environment was created using VirtualBox, Windows 10, and Kali Linux.

---

## Steps Taken
1. Installed VirtualBox (Day 1)  
2. Created placeholder VMs for Windows 10 and Kali Linux (Day 1)  
3. Downloaded official ISOs (Windows 10 – Day 2, Kali – Day 3)  
4. Installed Windows 10 (Day 2)  
5. Installed Kali Linux (Day 3)  

---

## Evidence

### VirtualBox Installation
![VirtualBox Installed](../Screenshots/VirtualBox_7.2_Installed_2025-09-08.png)  

### Placeholder VMs
![Windows 10 VM Created](../Screenshots/Windows10_VM_Created_2025-09-08.png)  
![Kali VM Placeholder](../Screenshots/Placeholder_VMs_2025-09-08.png)  

### Windows 10 Install
![Win10 ISO Mounted](../Screenshots/Win10_VM_ISO_Mounted_2025-09-09.png)  
![Win10 Install Start](../Screenshots/Win10_Install_Start_2025-09-09.png)  
![Win10 Installed Desktop](../Screenshots/Win10_Installed_Desktop_2025-09-09.png)  

### Kali Linux Install
![Kali Storage Fix](../Screenshots/Kali_VM_Storage_Fix_2025-09-10.png)  
![Kali ISO Mounted](../Screenshots/Kali_VM_ISO_Mounted_2025-09-10.png)  
![Kali Partition Confirmed](../Screenshots/Kali_Install_Partition_2025-09-10.png)  
![Kali Installed Desktop](../Screenshots/Kali_Installed_Desktop_2025-09-10.png)  

---

## Observations
- VirtualBox runs smoothly with 4 GB RAM per VM  
- Networking defaults to NAT and provides internet access out-of-the-box  
- Documentation with screenshots helps catch misconfigurations quickly (example: Kali disk detection issue)  

---

## Next Steps
- Configure VM-to-VM networking  
- Document connectivity tests (ping, nmap) in **Lab 2**
