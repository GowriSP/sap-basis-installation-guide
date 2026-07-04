# Prerequisites

## Overview

Before installing an SAP system, it is important to verify that the hardware, operating system, network, storage, and software requirements are correctly configured. Proper planning helps prevent installation failures and ensures a stable SAP environment.

---

# Hardware Requirements

The hardware requirements depend on the SAP product, database size, and expected workload.

Typical requirements include:

| Component | Recommended |
|-----------|-------------|
| CPU | Multi-Core 64-bit Processor |
| RAM | Minimum 16 GB (Higher for Production) |
| Storage | SSD Recommended |
| Network | 1 Gbps or Higher |
| Architecture | x86_64 |

---

# Operating System Requirements

SAP supports certified operating systems only.

Commonly used Linux distributions include:

- SUSE Linux Enterprise Server (SLES)
- Red Hat Enterprise Linux (RHEL)

Ensure that the operating system version is supported by the SAP release being installed.

---

# Hostname Configuration

The server hostname must be:

- Unique
- Properly resolved
- Configured in DNS or `/etc/hosts`
- Consistent before installation

Verify using:

```bash
hostname
hostname -f
```

---

# Network Configuration

Verify:

- Static IP Address
- DNS Resolution
- Hostname Resolution
- Internet access (if required)
- Required SAP ports are available

Useful commands:

```bash
ping hostname
ip addr
```

---

# File System Planning

Create separate mount points for SAP directories.

Common directories include:

| Directory | Purpose |
|------------|---------|
| /usr/sap | SAP Instance Files |
| /sapmnt | Global SAP Directory |
| /hana/shared | Shared HANA Files |
| /hana/data | Database Data |
| /hana/log | Database Logs |

---

# Disk Space

Ensure sufficient free storage for:

- SAP Software
- HANA Database
- Log Files
- Backups
- Kernel Files
- Transport Files

Running out of disk space during installation may cause installation failures.

---

# Memory Requirements

Verify available physical memory.

Example command:

```bash
free -h
```

Ensure sufficient swap space is also configured.

---

# Swap Space

Swap memory acts as virtual memory when physical RAM is fully utilized.

Verify swap:

```bash
swapon --show
```

---

# Required Linux Packages

Install all required packages recommended by SAP before starting installation.

Examples include:

- compat-sap-c++
- glibc
- libaio
- uuidd
- unzip
- tar

The exact package list depends on the SAP version and operating system.

---

# Time Synchronization

System time should be synchronized using NTP or Chrony.

Verify:

```bash
timedatectl status
```

---

# Firewall Configuration

Ensure that required SAP ports are accessible.

If necessary:

- Configure firewall rules
- Open SAP communication ports
- Verify network connectivity

---

# SELinux Configuration

Many SAP environments operate with SELinux configured according to SAP recommendations.

Verify:

```bash
getenforce
```

---

# SAP Installation Media

Before installation, verify availability of:

- SAP Software Provisioning Manager (SWPM)
- SAP Kernel
- SAP Host Agent
- SAP HANA Installation Media
- SAP Export Files
- SAP License (if applicable)

---

# SAP User Accounts

Typical operating system users include:

| User | Purpose |
|------|---------|
| root | Operating System Administrator |
| <sid>adm | SAP Instance Administrator |
| sapadm | SAP Host Agent User |

---

# Checklist Before Installation

- Hardware verified
- Supported Operating System installed
- Static IP configured
- Hostname configured
- DNS working
- Disk partitions created
- Required packages installed
- Swap configured
- Time synchronized
- Firewall reviewed
- SAP media downloaded
- SAP users created
- Storage verified

---

# Best Practices

- Follow the SAP Product Availability Matrix (PAM).
- Verify all prerequisites before launching SWPM.
- Keep installation media organized.
- Use dedicated storage for SAP data and logs.
- Record system details for future maintenance.
- Perform installation in a clean and stable environment.

---

# Summary

A successful SAP installation begins with careful preparation. Verifying hardware, operating system, storage, network, and software prerequisites helps ensure a smooth installation process and reduces the likelihood of errors during deployment.
