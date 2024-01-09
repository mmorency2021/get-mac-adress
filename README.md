# get-mac-adress
using idrac or ilom to collect mac adress from NIC card

```bash
ssh root@192.168.19.151 racadm getsysinfo -s 
(root@192.168.19.151) Password: 

System Information:
System Model            = PowerEdge R650
System Revision         = I
System BIOS Version     = 1.5.5
Service Tag             = 8VK9WM3
Express Svc Code        = 19322764635
Host Name               = 
OS Name                 = 
OS Version              = 
Power Status            = ON
Fresh Air Capable       = No
RollupStatus            = Ok

Embedded NIC MAC Addresses:
NIC.Embedded.1-1-1      Ethernet                = B0:7B:25:F8:B2:22
NIC.Integrated.1-1-1    Ethernet                = B4:96:91:D6:7F:08
NIC.Integrated.1-2-1    Ethernet                = B4:96:91:D6:7F:09
NIC.Embedded.2-1-1      Ethernet                = B0:7B:25:F8:B2:23
```

```bash
[marcklyvensmorency@marc ~]$ ssh root@192.168.24.157 racadm getsysinfo -s | grep Inte | awk '{print $4}'
(root@192.168.24.157) Password: 
B8:CE:F6:56:3D:B2
B8:CE:F6:56:3D:B3
[marcklyvensmorency@marc ~]$ ssh root@192.168.24.157 racadm getsysinfo -s | grep Inte | awk '{print $4}' |  tr '[:upper:]' '[:lower:]'
(root@192.168.24.157) Password: 
b8:ce:f6:56:3d:b2
b8:ce:f6:56:3d:b3
```
