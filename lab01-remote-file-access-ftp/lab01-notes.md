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

### Router Initial Configuration
![Router initial configuration](../lab01-screenshots/router-initial-config.png)

```bash
enable
conf t
interface Gig0/0
 ip address 192.168.1.1 255.255.255.0
 no shut
end
```
 📌 Task 3 — Server IP Configuration
### Server IP Configuration

![Server IP configuration window](lab01-screenshots/server-ip-configuration.png)

📌 Task 4 — Ping Test
### Ping Test (Server → Router)

![Ping test from server to router](lab01-screenshots/ping-test.png)

📌 Task 5 — Saving Running Config
### Saving the Router Running Configuration

![Saving running configuration using copy run start](lab01-screenshots/copy-run-start.png)

📌 Task 6 — FTP Server User Setup
### FTP User Setup on the Server

![FTP user setup](lab01-screenshots/ftp-user-setup.png)

📌 Task 7 — FTP Credentials on Router
### FTP Credentials Added to Router

![FTP credentials added on router](lab01-screenshots/ftp-credentials-router.png)

📌 Task 8 — FTP Backup Success
### Router Configuration Backup to FTP (Success)

![FTP backup success](lab01-screenshots/ftp-backup-success.png)

📌 Task 9 — FTP File List (Verification)
### FTP Server File List (Backup Verified)

The router’s configuration file (15Nov25) appears on the FTP server, confirming a successful backup.

![FTP file list showing backup](lab01-screenshots/ftp-file-list.png)

 
