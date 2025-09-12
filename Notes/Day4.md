# Day 4 Notes – Repo Upgrade

## Goal
Organize project into a professional structure and prepare for networking/scanning labs.

---

## Changes Made Today
- Created **/labs** with:
  - `Lab_1_Initial_Setup.md` (polished report with evidence)
  - `Lab_2_Network_Config.md` (template for ping + nmap)
- Created **/guides** with:
  - `Guide_VirtualBox_Networking.md`
  - `Guide_VM_Snapshots.md`
- Added **TROUBLESHOOTING.md** with real issues/fixes
- Added **RESOURCES.md** with official links

---

## Evidence (Repo Structure)
- `/labs` now contains Lab 1 (complete) and Lab 2 (template)
- `/guides` now contains Networking and Snapshots guides
- Root files added: `TROUBLESHOOTING.md`, `RESOURCES.md`

---

## Next Steps (Day 5)
- Configure **Host-Only** adapter on both VMs
- Collect evidence for **Lab 2**:
  - Windows: `ipconfig` (screenshot)
  - Kali: `ip a` + `ping <Windows-IP>` (screenshot)
  - Kali: `nmap <Windows-IP>` (screenshot)
- Update README with Day 4 repo upgrades
