# Docker on Windows use WSL2

### Requirements
```
Windows 10 19041 (Version 2004) or newer
```

### Enable some feature on Windows 10
```
# Docs https://docs.microsoft.com/en-us/windows/wsl/wsl2-install
# Open PowerShell with Administrator
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
# OR
Enable-WindowsOptionalFeature -Online -FeatureName $("VirtualMachinePlatform", "Microsoft-Windows-Subsystem-Linux")
# After enabled feature
wsl --set-default-version 2
# Check current version
wsl --list --verbose
# OR
wsl -l -v

# Optional
# Set Version
wsl --set-version <Distro> 2
```

### Install Software
#### Ubuntu 18.04
https://www.microsoft.com/store/productId/9N9TNGVNDL3Q
#### Terminal (Microsoft)
https://www.microsoft.com/store/productId/9N0DX20HK701

### Install ZSH and OMZ
```
# Docs https://blog.joaograssi.com/windows-subsystem-for-linux-with-oh-my-zsh-conemu/
# Install ZSH
sudo apt-get install zsh
# Install OMZ
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# Installing missing Powerline Fonts
git clone https://github.com/powerline/fonts.git
# Run with Power Shell
.\install.ps1
```

### Install Docker Desktop WSL 2 backend
Download: https://download.docker.com/win/edge/Docker%20Desktop%20Installer.exe
Docs: https://docs.docker.com/docker-for-windows/wsl-tech-preview/
