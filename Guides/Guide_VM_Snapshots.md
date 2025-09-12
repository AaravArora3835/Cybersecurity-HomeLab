# Guide – VirtualBox Snapshots (Save & Revert Lab States)

## Why Snapshots
- Freeze a known-good state (e.g., “Fresh Win10 install”, “Kali after tools”)
- Safely experiment; if you break something, roll back instantly

## Create a Snapshot
1. Power **off or on** is fine (consistent state is cleaner).
2. VirtualBox Manager → select VM → **Snapshots** tab
3. Click **Take** → Name it clearly (e.g., `Day2_Fresh_Win10`)
4. Add a short description (what changed since last snapshot)

## Restore a Snapshot
1. VirtualBox Manager → VM → **Snapshots**
2. Right-click snapshot → **Restore**
3. Optionally **Take a snapshot of the current state** before restoring (safety net)

## Best Practices
- Keep names short + dated: `2025-09-09_Fresh_Win10`, `2025-09-10_Kali_Installed`
- Snapshot before risky changes (drivers, networking, big installs)
- Don’t hoard dozens; prune old snapshots to save disk space

## Gotchas
- Snapshots consume space over time (differencing disks)
- Large I/O changes = bigger snapshot sizes
- Export finished labs (OVA) if you want an archive outside snapshot chains

## Screenshot Ideas
- “Take Snapshot” dialog
- Snapshot tree showing milestones
