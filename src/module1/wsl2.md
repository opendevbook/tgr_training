# install  WSL 2

## Enable HyperV
Open Turn Windows Features on or off

![](../assets/images/window_features.png)

Open Power shell with Administor and run command  to Enable HyperV

```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-All
bcdedit /set hypervisorlaunchtype auto

Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

## Install WSL
Open Power shell with Administrator
![](../assets/images/powershell_admin.png)
```
wsl --install
```

![](../assets/images/install_wsl.png)

Test install ubuntu on wsl
```
wsl --set-default-version 2
wsl --list --online
wsl --install -d Ubuntu-24.04
wsl --list
```

## Install Docker Desktop
[https://docs.docker.com/desktop/install/windows-install/](https://docs.docker.com/desktop/install/windows-install/)

![](../assets/images/docker_desktop_web.png)
- Download ```Docker Desktop for window -x86_64```

![](../assets/images/docker_desktop_web2.png)

![](../assets/images/docker_desktop_web3.png)

![](../assets/images/docker_desktop_web4.png)

![](../assets/images/docker_desktop_web5.png)

Install ubuntu 24.04 
```
wsl --install -d Ubuntu-24.04
```
![](../assets/images/docker_desktop_web6.png)
- username: sysadmin
- Password: password

Welcome Screen, click skip on top right corner:
![](../assets/images/docker_desktop_web7.png)

Complete Survey:

![](../assets/images/docker_desktop_web8.png)

Docker Desktop Application:

![](../assets/images/docker_desktop_web9.png)


During installation of Docker Desktop Application. Docker Desktop will install Ubuntu linux distro also

## check ip address of Linux ubuntu
```
> wsl hostname -I
172.20.255.117
```
- We will use this ip to connect service inside docker

**List Linux in wsl:**
- use command ```wsl --list``` to show Linux WSL distribution. Output will show below

![](../assets/images/docker_desktop_web10.png)

- we see linux name **docker-desktop** which install belong to Docker-Desktop which have docker process run inside

- if we want to Change default WSL Distro, we can use command ```wsl --set-default```  `<name linux wsl>`. Example below


```
> wsl --set-default Ubuntu-24.04
```

## Understand WSL command to connect linux
- connect to Linux WSL distro use command ```wsl -d ```  `<name linux wsl>`. if we use command with out name it will connect to Default linux.
After connect already we will go linux shell (Bash) inside linux 

```
wsl 
wsl -d Ubuntu-24.04
```

![](../assets/images/wsl_connect_ubuntu2404.png)

- Congratuation. We inside linux already.
- use exit command to exit from linux


Test 2 Docker Command: to verify
- Open Windows Terminal and use docker command from windows (Remember)
```
> docker ps
> docker info
```

![](../assets/images/docker_desktop_web11.png)


Benefits of WSL 2
To recap:

1. Virtual machines are resource intensive and create a very disconnected experience.
2. The original WSL was very connected, but had fairly poor performance compared to a VM.
3. WSL 2 brings a hybrid approach with a lightweight VM, a completely connected experience, and high performance.


Add in the WSL extension in Visual Studio Code and you have the best of all worlds – Linux and Windows compatibility for your tools with excellent performance and a seamless development experience

![](../assets/images/vscode_container1.png)

Connect to WSL 
- Connect to WSL  (default WSL distribution)
- Connect to WSL using Distro (Select WSL distribution)

![](../assets/images/vscode_container2.png)

Try to select WSL using Distro. VS code will list of WSL distribution

![](../assets/images/vscode_container3.png)

![](../assets/images/vscode_container4.png)
1. show connected WSL distribution
2. Click file explorer
3. Open Folder inside Linux WSL Distro 

![](../assets/images/vscode_container5.png)

![](../assets/images/vscode_container6.png)

## Connect to Linux WSL Distroy
- open Terminal in normal user 
```
wsl -d Ubuntu-24.04
```
![](../assets/images/vscode_container7.png)

- We will get Linux terminal 

## Open VScode Editor directly in Linux WSL 

```
> code .
```
![](../assets/images/vscode_container8.png)

![](../assets/images/vscode_container9.png)