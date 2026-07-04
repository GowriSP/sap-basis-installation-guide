# Useful Linux Commands for SAP BASIS

## Overview

Linux is the most commonly used operating system for SAP environments. SAP BASIS administrators should be familiar with essential Linux commands for system monitoring, file management, service administration, networking, and troubleshooting.

This document provides a collection of frequently used Linux commands during SAP installation and daily administration.

---

# System Information

| Command | Purpose |
|---------|---------|
| hostname | Display hostname |
| hostname -f | Display fully qualified hostname |
| hostnamectl | Show system information |
| uname -a | Display kernel information |
| uname -r | Display kernel version |
| cat /etc/os-release | Display OS version |

---

# CPU & Memory

| Command | Purpose |
|---------|---------|
| lscpu | CPU information |
| free -h | Memory usage |
| top | Real-time system monitoring |
| vmstat | Virtual memory statistics |
| uptime | System uptime and load |

---

# Disk & Storage

| Command | Purpose |
|---------|---------|
| df -h | Disk usage |
| du -sh * | Directory size |
| lsblk | Block devices |
| mount | Mounted file systems |
| fdisk -l | Disk partition information |

---

# File & Directory Management

| Command | Purpose |
|---------|---------|
| pwd | Current directory |
| ls -l | List files |
| mkdir | Create directory |
| rmdir | Remove empty directory |
| cp | Copy files |
| mv | Move or rename files |
| rm -rf | Remove files/directories |
| find | Search files |
| locate | Locate files |
| tree | Display directory structure |

---

# File Viewing

| Command | Purpose |
|---------|---------|
| cat | Display file |
| less | View large files |
| more | View file page by page |
| head | First 10 lines |
| tail | Last 10 lines |
| tail -f | Monitor log file |
| grep | Search text |
| wc -l | Count lines |

---

# User Administration

| Command | Purpose |
|---------|---------|
| whoami | Current user |
| id | User information |
| passwd | Change password |
| useradd | Create user |
| userdel | Delete user |
| groupadd | Create group |
| groups | Display user groups |

---

# Permissions

| Command | Purpose |
|---------|---------|
| chmod | Change permissions |
| chown | Change ownership |
| chgrp | Change group ownership |
| umask | Display default permissions |

---

# Process Management

| Command | Purpose |
|---------|---------|
| ps -ef | List running processes |
| pgrep | Search process |
| kill | Terminate process |
| kill -9 | Force terminate |
| jobs | Background jobs |
| nice | Start process with priority |

---

# Service Management

| Command | Purpose |
|---------|---------|
| systemctl status | Service status |
| systemctl start | Start service |
| systemctl stop | Stop service |
| systemctl restart | Restart service |
| systemctl enable | Enable service |
| systemctl disable | Disable service |

---

# Network Commands

| Command | Purpose |
|---------|---------|
| ip addr | Show IP address |
| ping | Test connectivity |
| traceroute | Trace network path |
| nslookup | DNS lookup |
| netstat -tulpn | Open ports |
| ss -tulpn | Socket statistics |
| curl | Test HTTP connectivity |

---

# Archive & Compression

| Command | Purpose |
|---------|---------|
| tar -cvf | Create archive |
| tar -xvf | Extract archive |
| gzip | Compress file |
| gunzip | Extract gzip |
| unzip | Extract ZIP |
| zip | Create ZIP archive |

---

# Log Files

| Command | Purpose |
|---------|---------|
| journalctl | System logs |
| dmesg | Kernel messages |
| tail -f /var/log/messages | Monitor logs |
| tail -f /var/log/secure | Security logs |

---

# SAP Related Commands

| Command | Purpose |
|---------|---------|
| sapcontrol | SAP instance control |
| startsap | Start SAP system |
| stopsap | Stop SAP system |
| disp+work -version | Kernel version |
| HDB info | SAP HANA status |
| HDB start | Start HANA |
| HDB stop | Stop HANA |
| R3trans -d | Database connectivity test |

---

# Useful Search Commands

```bash
find /usr/sap -name "*.log"
```

Search for log files.

```bash
grep "ERROR" sapinst.log
```

Search for errors in installation logs.

```bash
tail -100 sapinst.log
```

Display the last 100 lines of a log file.

---

# Interview Questions

### Q1. Which command displays memory usage?

```bash
free -h
```

---

### Q2. Which command checks disk usage?

```bash
df -h
```

---

### Q3. Which command displays running processes?

```bash
ps -ef
```

---

### Q4. Which command checks SAP HANA status?

```bash
HDB info
```

---

### Q5. Which command is used to restart a Linux service?

```bash
systemctl restart <service_name>
```

---

# Best Practices

- Use `tail -f` to monitor logs during SAP installation.
- Check disk space before large installations or upgrades.
- Monitor CPU and memory during kernel upgrades.
- Verify service status after restarting SAP components.
- Keep Linux updated with security patches.
- Avoid running SAP administration tasks as the `root` user unless required.

---

# Summary

Linux knowledge is essential for SAP BASIS administrators. These commands help manage servers, monitor system health, troubleshoot issues, and perform SAP installation and maintenance tasks efficiently. Regular practice with these commands improves administration skills and simplifies daily SAP BASIS operations.
