# Basic Home Lab Running Active Directory

This repository contains steps on how I set up a basic home lab running Active Directory following a tutorial by [Josh Madakor](https://www.youtube.com/@JoshMadakor) and making a few changes of my own (including learning about the use of GPO and possibly Microsoft Intune and distributing a suite of software and/or different kinds of access to users according to positions/roles) and yes, Windows Server 2022 instead of 2019

## Diagram
![Diagram](https://i.imgur.com/dsFYYpW.jpeg)

## Download and install Oracle VirtualBox from the official website.
[Oracle Virtual Box](https://www.virtualbox.org/)

## Download the Windows 10 and Server 2022 ISO files.
[Windows 10 iso](https://www.microsoft.com/en-us/software-download/windows10ISO)
[Windows Server 2022](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022)

## Create a new virtual machine by clicking on "New" in VirtualBox, naming it "Domain Controller," and selecting the "Windows Server 2022" ISO file as the boot media.

![](https://i.imgur.com/enQpiPE.png)

You can create the VM with the minimum required memory but it's recommended to have at least 4 cores in the CPU
![](https://i.imgur.com/n5PVwGN.png)

This is optional, it enables copying and pasting to/from the guest and host machine, makes the job easier
![](https://i.imgur.com/s7BV5Np.png)

##  Configure the virtual machine by giving it two network adapters: one for connecting to the internet and the other for the private network.

![](https://i.imgur.com/Lz80e2h.png)

![](https://i.imgur.com/5AlNj1d.png)

##  Install Server 2022 on the virtual machine 
![](https://i.imgur.com/MdWjA1X.png)

##  Install the guest additions
![](https://i.imgur.com/kwbCOfQ.png)

##  Figure out which NIC is connected to the internet and which one is internal 
![](https://i.imgur.com/8tMRKds.png)

##  Name the NIC drives to make differentiating between them easier.
![](https://i.imgur.com/AQdeJWZ.png)

##  Assign IP addressing for the internal network.
![](https://i.imgur.com/wJI315f.png)


##  Install Active Directory Domain Services.

![](https://i.imgur.com/DNsPDE3.png)

![]([img]https://i.imgur.com/gVaHzh8.png[/img])

![]([img]https://i.imgur.com/rwFmtqg.png[/img])


##  Configure routing so that clients on the private network can access the internet through the domain controller.

![](https://i.imgur.com/lgHv9KE.png)

![](https://i.imgur.com/6fkxOc5.png)

![](https://i.imgur.com/zydGRHC.png)

Make sure you select the external NIC card in this step
![](https://i.imgur.com/OEecOKV.png)


##  Set up DHCP on the domain controller.
![](https://i.imgur.com/nhkUJHV.png)

![](https://i.imgur.com/1DoT360.png)

![](https://i.imgur.com/azR5xwB.png)

![](https://i.imgur.com/iPYH4Bo.png)

![](https://i.imgur.com/dXjjd7g.png)

![](https://i.imgur.com/yL01xDh.png)

##  Run the PowerShell script to create 1000 users in Active Directory.

[Power Shell script for creating users](https://github.com/joshmadakor1/AD_PS)
![](https://i.imgur.com/g5v8Zux.png)

##  Create a new virtual machine named "Client1" and install Windows 10 on it.

![](attachments/Pasted%20image%2020230402155056.png)


##  Connect the client machine to the private network and join it to the domain.

![](attachments/Pasted%20image%2020230402155713.png)

![](attachments/Pasted%20image%2020230402155807.png)

##  Log into the client machine with a domain account.

![](attachments/Pasted%20image%2020230402160005.png)

![](attachments/Pasted%20image%2020230402160120.png)
