## About
Sample `.wslconfig` file to configure networking settings for WSL2 Windows 11. Place this file in `C:\Users\<UserName>`.
- `networkingMode=mirrored`: mirrors windows networking onto wsl, allows LAN to connecto to WSL directly.
- `hostAddressLoopback=true`: enables host machine to be able to access its own ipv4 address, e.g. http://192.168.0.238:5173/.

Run the following command in admin powershell to allow the [Hyper-V firewall](https://learn.microsoft.com/en-us/windows/security/operating-system-security/network-security/windows-firewall/hyper-v-firewall) (WSL's firewall) to allow inbound connections.

```powershell
Set-NetFirewallHyperVVMSetting -Name '{40E0AC32-46A5-438A-A0B2-2B479E8F2E90}' -DefaultInboundAction Allow
```
For more info, see: https://learn.microsoft.com/en-us/windows/wsl/networking#mirrored-mode-networking

## Troubleshooting
The powershell `ipconfig` command should no longer have `Ethernet adapter vEthernet (WSL ...)` as the Windows IP address will be the same as the WSL one.

```powershell
ipconfig
```

If external devices cannot connect to a WSL port, check firewall settings (and disable antivirus firewall settings if any).

