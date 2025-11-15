# Lab 01 – Remote File Access (FTP Router Backup)

*Tool:* Cisco Packet Tracer  
*Source:* 101 Labs – Remote File Access — FTP  
*Role Focus:* IT Support • Help Desk • Network Technician  

---

## 1. Scenario – QDL Question

> How do I back up a router’s configuration to a remote FTP server so it can be restored if the device fails?

---

## 2. Why This Matters in IT Support

- Backups prevent loss of router configuration after failure or replacement.  
- IT Support must know where configs live (RAM vs NVRAM) and how to properly save them.  
- FTP is still used in many legacy backup systems.  

---

## 3. Topology & IP Plan

Single router connected to an FTP server using a crossover cable.

| Device | IP Address   | Subnet Mask     | Default Gateway |
|--------|--------------|-----------------|-----------------|
| Router | 192.168.1.1  | 255.255.255.0   | —               |
| Server | 192.168.1.2  | 255.255.255.0   | 192.168.1.1     |

---

## 4. Step-by-Step Summary

### A. Configure router Ethernet interface

```bash
enable
conf t
interface f0/0
 ip address 192.168.1.1 255.255.255.0
 no shut
end
