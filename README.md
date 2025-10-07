# How to Install DaVinci Resolve on Arch Linux

A guide to installing DaVinci Resolve on Arch Linux and other distributions.

## NVIDIA Driver Installation

### For standard kernel users
```bash
sudo pacman -S --needed nvidia nvidia-utils cuda opencl-nvidia
```

### For custom kernel users (linux-zen, etc.)
```bash
sudo pacman -S --needed nvidia-dkms nvidia-utils cuda opencl-nvidia
```

## Download DaVinci Resolve

**⚠️ DO NOT INSTALL DAVINCI FROM THE AUR, IT WILL NOT WORK**

Instead, go to the official site and download from there:
- Visit https://www.blackmagicdesign.com/products/davinciresolve
- Download the Linux version: `DaVinci_Resolve_Studio_your_version_Linux.zip`

## Installation

1. Unzip the downloaded file:
```bash
unzip DaVinci_Resolve_Studio_your_version_Linux.zip
```

2. Make the installer executable:
```bash
sudo chmod +x DaVinci_Resolve_Studio_your_version_Linux.run
```

3. Install DaVinci Resolve:

**For Wayland users (recommended):**
If you are using Wayland (90% probability), you can just double click the run file and install it from there.

**For X11 users or command line:**
```bash
sudo ./DaVinci_Resolve_Studio_your_version_Linux.run
```

## Post-Installation Fix

**DO NOT open DaVinci Resolve yet!** You need to run this first:

```bash
cd /opt/resolve/libs && sudo mkdir disabled-libraries && sudo mv libglib* libgio* libgmodule* disabled-libraries
```

## Troubleshooting

If it still doesn't work, you probably need to install:
```bash
yay -S libpng12 ffmpeg-compat-57
```

## That's it!

You should now be able to run DaVinci Resolve from your application menu or by running `/opt/resolve/bin/resolve`.