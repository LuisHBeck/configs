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

<br>

## DOCKER INSTALATION
Run the following commands in Ubuntu terminal

Docker

`$ sudo apt update`

`$ sudo apt install apt-transport-https ca-certificates curl software-properties-common`

`$ sudo apt install build-essential`

`$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add`

`$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`

`$ sudo apt update`

`$ sudo apt install docker-ce`

`$ sudo docker version`

`$ sudo groupadd docker`

`$ sudo usermod -aG docker $USER`

Docker compose

`$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`

`$ sudo chmod +x /usr/local/bin/docker-compose`

`$ docker-compose --version`

Restart your PC


<br>

## Set Docker aliases
`$ nano ~/.bashrc`


Paste the following aliases

```powershell
alias docker-stop='docker stop $(docker ps -a -q)'

alias docker-psrm='docker rm $(docker ps -a -q)'

alias docker-imgrm='docker rmi $(docker images -q)'

alias docker-vlrm='docker volume rm $(docker volume ls -q)'

alias docker-ntrm='docker network rm $(docker network ls -q)'
```

`Ctrl + X` + `Y` + `ENTER` to save the changes

`$ source ~/.bashrc`

Open a new terminal and enjoy!