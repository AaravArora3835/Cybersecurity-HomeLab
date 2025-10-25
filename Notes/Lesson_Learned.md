# Lessons Learned

## Technical Insights

### 1. Network Isolation Is Critical
Host-Only networking prevents accidental scans of real networks. Production pentests require strict scope boundaries — this lab taught controlled testing fundamentals.

### 2. Default Deny Principle
Windows blocked ICMP by default (secure), Kali allowed it (convenience). Real environments prioritize security over ease — defenders must balance both.

### 3. Documentation Under Pressure
Timestamped screenshots and troubleshooting logs proved essential when returning to work after interruptions. Professional security work requires audit trails.

## What I'd Do Differently
- **Snapshots Earlier:** Should have created baseline snapshots before network changes
- **Wireshark Integration:** Capturing packets during ping tests would have added protocol analysis practice
- **Automation:** Bash scripts for repetitive scans would have saved time

## Applicable to Future Work
- VM skills transfer directly to cloud environments (AWS EC2, Azure VMs)
- Troubleshooting methodology applies to any IT issue (isolate, test, document)
- Lab documentation format matches professional security assessment reports
