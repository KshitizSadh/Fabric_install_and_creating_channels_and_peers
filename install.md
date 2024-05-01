 This is a step-by-step way of installing HyperLedger Fabric on Windows 10:

Open power shell in Admin mode.
Enable windows Subsystem for Linux
`dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`

3. Enable Virtual Machine feature

`dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`

4. Set WSL-2 as default version

`wsl — set-default-version 2`

5. Install Ubuntu app from windows store
Open the Microsoft Store and install Ubuntu 20.04 LTS here

6. Install windows terminal
It enables multiple tabs, quickly between the Linux command line and the windows command prompt.

7. Download linux kernel update package.
To update the WSL package download setup at the below-mentioned link, it needs admin privilege.
  https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

8. Open Windows Terminal and add a new ubuntu tab, you won’t be able to see the ubuntu terminal. Under add new terminal section.

9. Open Installed, “Ubuntu 20.04 LTS” once, So that it will be linked with Windows terminal.

10. Updating and installing basic packages for Ubuntu.

```sudo apt update && sudo apt upgrade```

11. Download Docker for windows latest version from
https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe

Install Docker

12. Enable Docker for Ubuntu
*Go to Settings ->Resources->WSL integration->Enable Ubuntu-20.04
->Then hit Apply & restart->his may take few minutes->After Enabling this we will get docker in the ubuntu command line*

Hit “refresh” if ubuntu does not appear.

13. Run following command to check if you are able to access it on Ubuntu
```
docker -v
docker-compose — version
```
14. Run following command to install and update basic packages on Ubuntu.
```
sudo apt update
sudo apt upgrade
```
15. Check if cURL already exists. Otherwise install it

```sudo apt-get install curl```

16. Check if Go lang exists
```
go version
```
17. If Go doesn’t then install with following steps: Download the Go lang package for Linux from here.

```sudo wget https://golang.org/dl/go1.16.3.linux-amd64.tar.gz```

18. The following command will extract the zip file at the downloaded location.

```tar xvf go1.16.3.linux-amd64.tar.gz```

19. Set GOPATH using following command
```
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
```
20. Run the following command to verify that Go lang is installed successfully
```
go version
```
21. Run the following command to see if git is installed
```
git -–version
```
22. Install Hyperledger Fabric and Fabric samples
Note: Hyperledger fabric version is 2.5.0

23. Create a directory with following command
Creates a new Directory: mkdir -p $HOME/go/src/github.com/
Navigate to that created directory: cd $HOME/go/src/github.com/

24. Download the latest release of fabric samples and docker images.
Run following command under `$HOME/go/src/github.com/ directory
`
`curl -sSL https://bit.ly/2ysbOFE | bash -s`

25. navigate to fabric folder
```
cd $wsl
cd go/src/github.com/fabric-samples
```
26. Go to test-network

`cd test-network`

27. Run following command to remove existing any container or artifacts form previous run.

`./network.sh down`

28. Running following will boot up fabric test network

`./network.sh up`

29. Run following command to list down all running docker images in
```
docker
docker ps –a
```
30. Same you can look at docker GUI

NOTE: Subsystems are mounted on /mnt/c/ from here you can have access to the base system. cd /mnt/c/Users/daser/Desktop. Therefore you can have a directory here and run your codes from here.

use code . to power code editor

Also to set the path to the executables of the hyperledger:

`export PATH=$PATH:$GOPATH/src/github.com/fabric-samples/bin`

![Screenshot (56)](https://github.com/KshitizSadh/Fabric_install_and_creating_channels_and_peers/assets/142923024/6c7ba142-146b-46ed-9402-7917db67ef9f)

![Screenshot (57)](https://github.com/KshitizSadh/Fabric_install_and_creating_channels_and_peers/assets/142923024/a1ac8f94-ec58-49e7-b7e7-30b078c4530a)

![Screenshot (58)](https://github.com/KshitizSadh/Fabric_install_and_creating_channels_and_peers/assets/142923024/3ceef753-e8c9-4c07-98e2-97d64fc141d6)


![Screenshot (59)](https://github.com/KshitizSadh/Fabric_install_and_creating_channels_and_peers/assets/142923024/2c34e2f3-ba0b-4851-be99-6c3049e19251)

