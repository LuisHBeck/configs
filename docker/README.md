# DOCKER IN LINUX (WSL OR UBUNTU)

## WSL INSTALATION
Run the following commands as admin in Powershell

### Enable windows subsystem for linux + virtual machine feature
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
``` 

Restart your PC

