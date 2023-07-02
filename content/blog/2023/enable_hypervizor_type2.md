title=Enabling hypervisor of required type in Windows 11
date=2023-07-02
type=post
tags=blog
status=published
~~~~~~
Unfortunately, in Windows 11 one cannot have both type 1 and type 2 hypervisors enabled. A common consequence of this is following two cases:
1. Virtualbox and VMWare Workstation working, but Windows Subsystem For Linux / Windows Sandbox does not
2. Windows Subsystem For Linux and Windows Sandbox are working, but Virtualbox and VMWare Workstation are not.
As an illustration for second case is inability of VMWare player effectively virtualise Macs OS X on Windows 11 host:
![VMWare player failure](/img/Screenshot%202023-07-02%20211913.png)

In order to switch from Hypervisor type 1 to type 2.

Run as admin
```
bcdedit /set hypervisorlaunchtype disable
```
to switch it back use
```
bcdedit /set hypervisorlaunchtype auto
```

Go to "Turn Windows features on or off" and un-check "Virtual Machine Platform"

After those operation your VMWare Workstation / Virtualbox will support virtualisation properly