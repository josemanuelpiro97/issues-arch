## Fixing date and times in dual-boot with Windows

There are two time standards: localtime and UTC. 

- **Standard:**  is dependent on the current time zone. Used by the hardware clock (BIOS time) is set by the operating system. 
- **UTC:**  Global time standard and is independent of time zone values.


To dual boot with Windows it is recommended to configure Windows to use UTC, rather than Linux to use localtime.

It can be done by a simple registry fix: 

<br>

**IN WINDOWS** - Add a QWORD with hexadecimal value 1 to the registry. You can do this from an Administrator Command Prompt running:

```
reg add "HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation" /v RealTimeIsUniversal /d 1 /t REG_QWORD /f
```
<br>

**IN ARCH** - Set UTC as timezone for arch 

```
timedatectl set-timezone UTC
```
