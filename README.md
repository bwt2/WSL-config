## About
Sample `.wslconfig` file to configure networking settings for WSL2 Windows 11. Place this file in `C:\Users\<UserName>`.
- `networkingMode=mirrored`: mirrors windows networking onto wsl, allows LAN to connecto to WSL directly.
- `hostAddressLoopback=true`: enables host machine to be able to access its own ipv4 address, e.g. http://192.168.0.238:5173/.

## Troubleshooting
The powershell `ipconfig` command should no longer have `Ethernet adapter vEthernet (WSL ...)` as the Windows IP address will be the same as the WSL one.

```powershell
ipconfig
```

If external devices cannot connect to a WSL port, check firewall settings (and disable antivirus firewall settings if any).

For more info, see: https://learn.microsoft.com/en-us/windows/wsl/networking#mirrored-mode-networking