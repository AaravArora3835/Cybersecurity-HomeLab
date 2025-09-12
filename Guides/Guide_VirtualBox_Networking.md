# Guide – VirtualBox Networking (NAT, Bridged, Host-Only, Internal)

## TL;DR
- **NAT**: VM → Internet (good defaults). VMs can’t see each other unless you tweak.
- **Bridged**: VM sits on your real LAN (acts like another device on your Wi-Fi/Ethernet).
- **Host-Only**: Private network between **host ↔ VMs**, no Internet (unless you add NAT too).
- **Internal**: Private network **VM ↔ VM only**, host can’t see it.

## Recommended Lab Layout
- Keep each VM with **Adapter 1 = NAT** (Internet access).
- Add **Adapter 2 = Host-Only** (for VM↔VM lab traffic).
  - This gives reliable connectivity for ping/Nmap without touching your real LAN.

## How to Configure (per VM)
1. **Settings → Network**
2. **Adapter 1**  
   - ☑ Enable Network Adapter  
   - Attached to: **NAT**
3. **Adapter 2**  
   - ☑ Enable Network Adapter  
   - Attached to: **Host-only Adapter**  
   - Name: select your host-only network (e.g., `vboxnet0`)
4. **OK**

## Verify IPs
- **Windows (inside VM):**  
  `ipconfig`  
  - Look for **Ethernet adapter** tied to Host-Only (usually `192.168.56.x`)
- **Kali (inside VM):**  
  `ip addr` or `ip a`  
  - Look for the Host-Only interface (often `enp0s8`) with `192.168.56.x`

## Connectivity Tests
1. **Ping Windows from Kali:**  
   `ping -c 4 <Windows-HostOnly-IP>`
2. **Ping Kali from Windows:**  
   `ping <Kali-HostOnly-IP>`

> If ping fails on Windows, allow ICMP Echo in Windows Defender Firewall (Inbound rule → File and Printer Sharing (Echo Request – ICMPv4)).

## Optional: Internal Network
- Use **Internal Network** instead of Host-Only if you want **VM↔VM only** with no host visibility.
- Both VMs must use the **same Internal Network name** (e.g., `intnet`).

## Troubleshooting Quick Hits
- No IP on Host-Only? Disable/Enable Adapter 2 inside the guest, or reboot the VM.
- Ping blocked? Check Windows Firewall ICMP inbound rule.
- Name resolution flaky? Ping by IP, not hostname.

## Screenshot Ideas (when you do Lab 2)
- VirtualBox Network settings (Adapters 1 & 2)
- Windows `ipconfig`
- Kali `ip a`
- Ping success both directions
