## About
Sample `.wslconfig` file to configure networking settings for WSL. Place this file in `C:\Users\<UserName>`.
- `networkingMode=mirrored`: mirrors windows networking onto wsl, allows LAN to connecto to WSL directly.
- `hostAddressLoopback=true`: enables host machine to be able to access its own ipv4 address, e.g. http://192.168.0.238:5173/.

For more info, see: https://learn.microsoft.com/en-us/windows/wsl/networking#mirrored-mode-networking