# DOCKER IN LINUX (WSL OR UBUNTU)

## WSL INSTALATION
Run the following commands as admin in Powershell

### Enable windows subsystem for linux + virtual machine feature
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
``` 

Restart your PC

<br>

### Install Linux kernel update
[Download here](https://learn.microsoft.com/pt-br/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)

Double click to run (you will need admin privileges) and follow the instructions.

<br>

### Set WSL 2 as default version
```powershell
wsl --set-default-version 2
```

<br>

### Install Distro 
Normal Distro
```powershell
wsl --install -d Ubuntu
```

Distro with CNTLM
```powershell
wsl --import UbuntuCNTLM . <archive.tar>
```
