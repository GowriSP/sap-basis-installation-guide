# Linux Preparation

## Overview

Proper Linux server preparation is one of the most important steps before installing SAP software. A correctly configured operating system provides the foundation for a stable, secure, and high-performing SAP environment.

This document covers the essential Linux preparation tasks that should be completed before installing SAP HANA or SAP Application Server.

---

# Verify Operating System

Ensure that the Linux distribution and version are certified for the SAP product you plan to install.

Common supported operating systems include:

- Red Hat Enterprise Linux (RHEL)
- SUSE Linux Enterprise Server (SLES)

Verify the operating system version:

```bash
cat /etc/os-release
```

---

# Check System Information

Verify CPU, memory, hostname, and kernel version.

```bash
hostnamectl
```

Check Linux kernel version:

```bash
uname -r
```

Check processor details:

```bash
lscpu
```

Check memory:

```bash
free -h
```

---

# Create SAP Users

SAP installation requires dedicated operating system users.

Typical users include:

| User | Purpose |
|------|---------|
| root | Linux Administrator |
| <SID>adm | SAP System Administrator |
| sapadm | SAP Host Agent User |

Example:

```bash
useradd prdadm
passwd prdadm
```

---

# Create Required Groups

Create the required Linux groups before installation.

Example:

```bash
groupadd sapsys
```

Verify:

```bash
cat /etc/group
```

---

# Configure Hostname

The hostname should be unique and resolvable.

Check hostname:

```bash
hostname
hostname -f
```

Update `/etc/hosts` if necessary.

Example:

```text
192.168.1.20    sapserver.company.local    sapserver
```

---

# Verify Network

Check IP address:

```bash
ip addr
```

Test connectivity:

```bash
ping google.com
```

Test hostname resolution:

```bash
ping sapserver
```

---

# Create SAP Directories

Create the required directories before installation.

Example:

```bash
mkdir -p /usr/sap
mkdir -p /sapmnt
mkdir -p /hana/shared
mkdir -p /hana/data
mkdir -p /hana/log
```

Verify:

```bash
ls -l /
```

---

# Configure File Permissions

Assign appropriate ownership and permissions.

Example:

```bash
chown -R prdadm:sapsys /usr/sap
chmod -R 755 /usr/sap
```

---

# Verify Disk Space

Check available storage.

```bash
df -h
```

Ensure enough space is available for:

- SAP Software
- HANA Database
- Logs
- Backups
- Kernel Files

---

# Verify Memory

Check physical memory.

```bash
free -h
```

Display memory details:

```bash
cat /proc/meminfo
```

---

# Configure Swap Space

Check swap:

```bash
swapon --show
```

Verify usage:

```bash
free -h
```

---

# Install Required Packages

Install prerequisite packages according to SAP recommendations.

Examples:

- glibc
- libaio
- uuidd
- compat-sap-c++
- unzip
- tar
- wget

Package installation (RHEL):

```bash
yum install package-name
```

Package installation (SLES):

```bash
zypper install package-name
```

---

# Configure Time Synchronization

Verify time settings.

```bash
timedatectl status
```

Enable NTP if required.

---

# Firewall Configuration

Verify firewall status.

```bash
systemctl status firewalld
```

Allow required SAP ports according to your organization's security policy.

---

# SELinux Status

Check SELinux.

```bash
getenforce
```

View configuration:

```bash
cat /etc/selinux/config
```

---

# Verify File Systems

Check mounted file systems.

```bash
lsblk
```

View mount points.

```bash
mount
```

---

# Environment Variables

Check environment variables.

```bash
env
```

Example PATH:

```bash
echo $PATH
```

---

# Verify SAP Installation Media

Ensure the following installation files are available:

- SAP HANA Media
- SWPM
- SAP Kernel
- SAP Host Agent
- SAP Export Files

---

# Pre-Installation Checklist

Before starting SAP installation, verify:

- Linux version supported
- Hostname configured
- DNS working
- Static IP assigned
- Required users created
- Groups created
- Storage available
- Swap configured
- Memory verified
- Required packages installed
- Firewall reviewed
- SELinux verified
- SAP directories created
- SAP installation media available

---

# Best Practices

- Keep the operating system updated.
- Use dedicated file systems for SAP and HANA.
- Avoid installing unnecessary software on SAP servers.
- Use meaningful hostnames.
- Monitor disk usage before and after installation.
- Document all Linux configuration changes.
- Validate every prerequisite before executing SWPM.

---

# Summary

Preparing the Linux operating system correctly is a critical prerequisite for a successful SAP installation. Proper user management, storage planning, network configuration, package installation, and security settings help ensure a stable and reliable SAP environment while reducing installation failures.
