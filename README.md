# Home Lab Setup

**Purpose:**  
This is my foundational cybersecurity lab for hands-on learning. It includes virtual machines running **Windows 10** and **Kali Linux** on **VirtualBox**.

**Why This Lab:**  
- Safe environment to practice IT & cybersecurity exercises  
- Supports learning for **CompTIA Tech+**, **A+**, **Google Cybersecurity Certificate**, and **TryHackMe** labs  
- Builds a professional portfolio for college applications and internships  

---

## Current Progress

### ✅ Day 1 – VirtualBox + Placeholders
- VirtualBox installed  
  ![VirtualBox Installed](Screenshots/VirtualBox_7.2_Installed_2025-09-08.png)  
- Placeholder Windows 10 VM created  
  ![Windows 10 VM](Screenshots/Windows10_VM_Created_2025-09-08.png)  
- Placeholder Kali Linux VM created  
  ![Both VMs](Screenshots/Placeholder_VMs_2025-09-08.png)  

📑 [Day 1 Notes](Notes/Day1.md)

---

### ✅ Day 2 – Windows 10 Installation
- Mounted Windows 10 ISO  
  ![Win10 ISO Mounted](Screenshots/Win10_VM_ISO_Mounted_2025-09-09.png)  
- Windows 10 installation in progress  
  ![Win10 Install Start](Screenshots/Win10_Install_Start_2025-09-09.png)  
- Windows 10 fully installed with lab user  
  ![Win10 Installed Desktop](Screenshots/Win10_Installed_Desktop_2025-09-09.png)  

📑 [Day 2 Notes](Notes/Day2.md)

---

### ✅ Day 3 – Kali Linux Installation
- Fixed storage issue (added 20GB VDI)  
  ![Kali Storage Fix](Screenshots/Kali_VM_Storage_Fix_2025-09-10.png)  
- Mounted Kali ISO  
  ![Kali ISO Mounted](Screenshots/Kali_VM_ISO_Mounted_2025-09-10.png)  
- Partitioning confirmed  
  ![Kali Partition](Screenshots/Kali_Install_Partition_2025-09-10.png)  
- Kali installed successfully and booted into desktop  
  ![Kali Desktop](Screenshots/Kali_Installed_Desktop_2025-09-10.png)  

📑 [Day 3 Notes](Notes/Day3.md)

---

### ✅ Day 4 – Repo Upgrade
- Created **/labs** folder  
  - Added `Lab_1_Initial_Setup.md` with complete evidence  
  - Added `Lab_2_Network_Config.md` as template for networking + scans  
- Created **/Guides** folder  
  - Added `Guide_VirtualBox_Networking.md` (how-to for NAT, Host-Only, Bridged, Internal)  
  - Added `Guide_VM_Snapshots.md` (how-to for saving/reverting VM states)  
- Added **TROUBLESHOOTING.md** with issues/fixes from Day 2–3  
- Added **RESOURCES.md** with official download links and references  

📑 [Day 4 Notes](Notes/Day4.md)

---

## Repository Structure
- **/Screenshots** → All VM setup screenshots  
- **/Notes** → Daily lab notes (Day 1–Day 4 so far)  
- **/labs** → Formal lab reports (Lab 1 complete, Lab 2 in progress)  
- **/Guides** → Step-by-step how-to docs  
- **TROUBLESHOOTING.md** → Error log + fixes  
- **RESOURCES.md** → Official references and trusted sources  
- **README.md** → Roadmap + progress tracker (this file)  

---

## Planned Next Steps
- Configure VirtualBox networking (Host-Only or Internal)  
- Prove VM-to-VM connectivity with `ping` and document in **Lab 2**  
- Run first `nmap` scan from Kali → Windows and capture results  
- Expand troubleshooting log with networking issues  
- Add more guides (e.g., setting up shared folders, snapshots workflow)
