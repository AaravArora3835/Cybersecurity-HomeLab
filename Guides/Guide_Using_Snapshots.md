# Using Snapshots in VirtualBox (Safe Rollbacks)

## Objective
Create and restore VirtualBox snapshots so you can experiment safely and revert if something breaks.

## Why Snapshots
- Freeze a VM’s state before risky changes.
- Roll back in seconds (faster than reinstalling).
- Keep a clean “golden” baseline for repeatable labs.

## Prerequisites
- Oracle VirtualBox 7.x installed
- A powered-off or running VM (Windows 10 or Kali)

## Create a Snapshot
1. In **VirtualBox Manager**, select your VM.
2. Click the **Snapshots** view (icon on the right).
3. Click **Take** (camera icon).
4. **Name** it clearly:
   - Example: `Baseline_After_OS_Install_2025-09-10`
   - Example: `Before_Nmap_Scan_2025-09-20`
5. Add a short **Description** (what/why).
6. Click **OK**.

📸 Evidence (optional):
![Take Snapshot](../Screenshots/VirtualBox_Snapshot_Take_2025-09-20.png)

## Restore a Snapshot
1. Power off the VM (recommended).
2. Open the **Snapshots** view.
3. Right-click the snapshot ➜ **Restore**.
4. Choose whether to **Create a snapshot of the current state** (usually yes if you might return).
5. Start the VM.

📸 Evidence (optional):
![Restore Snapshot](../Screenshots/VirtualBox_Snapshot_Restore_2025-09-20.png)

## Manage / Delete Snapshots
- Right-click a snapshot ➜ **Delete** to free disk space.
- Use **Clone** if you want a new VM based on a snapshot.

## Best Practices
- Take a snapshot before:
  - Networking changes
  - Scans / service exposure
  - Installing tools or updates
- Keep one **Golden Baseline** per VM.
- Use **date-stamped names** (YYYY-MM-DD).
- Periodically **export** a VM (OVA) for backup.

## Notes
- Snapshots consume disk space as changes accumulate.
- Snapshots are **not** a substitute for real backups.
