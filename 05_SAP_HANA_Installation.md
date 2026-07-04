# SAP HANA Installation

## Overview

SAP HANA (High-Performance Analytic Appliance) is an in-memory relational database developed by SAP. It stores data primarily in memory, enabling high-speed transaction processing and real-time analytics.

SAP HANA serves as the database platform for SAP S/4HANA and many other SAP applications. A successful installation requires careful planning, operating system preparation, storage configuration, and validation.

---

# Objectives

After completing this guide, you will understand:

- SAP HANA architecture
- Installation prerequisites
- HDBLCM tool
- System Database
- Tenant Database
- SAP HANA SID
- Instance Number
- Installation workflow
- Post-installation validation

---

# SAP HANA Architecture

SAP HANA consists of the following components:

- System Database
- Tenant Database(s)
- Index Server
- Name Server
- Statistics Server
- XS Engine (legacy)
- Persistence Layer
- Log Volume
- Data Volume

---

# System Database

The **System Database (SYSTEMDB)** is used to manage the SAP HANA system.

Responsibilities include:

- Create/Delete Tenant Databases
- Monitor the HANA Landscape
- Backup Configuration
- User Administration
- System Configuration

---

# Tenant Database

A Tenant Database stores application data independently within the SAP HANA system.

Each Tenant Database has:

- Own Users
- Own Schemas
- Own Backup
- Own Security Settings

Multiple Tenant Databases can exist within a single SAP HANA system (MDC).

---

# Multi-Database Container (MDC)

Modern SAP HANA installations use the **Multi-Database Container (MDC)** architecture.

Benefits include:

- Better resource utilization
- Isolated tenant environments
- Simplified administration
- Improved scalability

---

# SAP HANA SID

The System ID (SID) uniquely identifies an SAP HANA system.

Example:

```
PRD
QAS
DEV
```

Rules:

- Three characters
- Uppercase letters
- Unique within the landscape

---

# Instance Number

Each SAP HANA installation uses a two-digit instance number.

Example:

```
00
01
02
10
```

The instance number determines service ports and process directories.

---

# Prerequisites

Before installation, verify:

- Supported Linux version
- Static IP Address
- Hostname Resolution
- Required Memory
- Required CPU
- Storage Availability
- SAP Host Agent Installed
- Installation Media Available

---

# Installation Tool

SAP HANA is installed using:

```
hdblcm
```

(HANA Database Lifecycle Manager)

---

# Extract Installation Media

Extract SAP HANA installation files.

Example:

```bash
tar -xvf SAP_HANA_DATABASE.tar
```

Navigate to the extracted directory.

---

# Start Installation

Run:

```bash
./hdblcm
```

The installation wizard starts.

---

# Installation Parameters

During installation provide:

- SID
- Instance Number
- Hostname
- SYSTEM Password
- Installation Path
- Data Volume
- Log Volume

Review the summary before proceeding.

---

# Installation Workflow

1. Verify prerequisites
2. Extract installation media
3. Launch hdblcm
4. Enter installation parameters
5. Configure System Database
6. Configure Tenant Database
7. Complete installation
8. Validate installation
9. Start SAP HANA services

---

# Verify Installation

Check installed version:

```bash
HDB version
```

Check running services:

```bash
HDB info
```

Display process list:

```bash
sapcontrol -nr 00 -function GetProcessList
```

Replace **00** with your HANA instance number.

---

# Start SAP HANA

```bash
HDB start
```

---

# Stop SAP HANA

```bash
HDB stop
```

---

# Restart SAP HANA

```bash
HDB restart
```

---

# Verify Database Status

Login as the SAP HANA administrator.

Example:

```bash
su - <sid>adm
```

Verify database status.

```bash
HDB info
```

---

# Important Directories

| Directory | Purpose |
|------------|---------|
| /hana/shared | Shared Files |
| /hana/data | Database Data |
| /hana/log | Log Files |
| /usr/sap | SAP Executables |

---

# Common Installation Errors

## Hostname Resolution Failed

Cause:

Hostname configuration is incorrect.

Resolution:

Verify:

```bash
hostname
hostname -f
cat /etc/hosts
```

---

## Insufficient Memory

Cause:

Physical RAM is below SAP HANA requirements.

Resolution:

Increase server memory before installation.

---

## Disk Space Insufficient

Cause:

Not enough storage for data and log volumes.

Resolution:

Expand storage and retry installation.

---

## Port Already in Use

Cause:

Required HANA port is occupied.

Resolution:

Identify and stop the conflicting service.

---

## Permission Denied

Cause:

Installation executed without proper user privileges.

Resolution:

Run installation as the correct operating system user.

---

# Best Practices

- Follow SAP Product Availability Matrix (PAM).
- Use certified hardware and operating systems.
- Separate data and log volumes.
- Keep installation media updated.
- Record SID and instance details.
- Validate all services after installation.
- Perform an initial backup after installation.

---

# Interview Questions

### Q1. What is SAP HANA?

SAP HANA is an in-memory relational database platform developed by SAP for high-speed transaction processing and real-time analytics.

---

### Q2. Which tool is used to install SAP HANA?

```
hdblcm
```

(HANA Database Lifecycle Manager)

---

### Q3. What is the difference between SYSTEMDB and Tenant Database?

- **SYSTEMDB** manages the overall SAP HANA system, including tenant creation and system administration.
- **Tenant Database** stores application data and operates independently with its own users, schemas, and backups.

---

### Q4. What is MDC?

MDC (Multi-Database Container) is an SAP HANA architecture that allows multiple isolated Tenant Databases to run under a single System Database.

---

### Q5. Which command is used to check running HANA services?

```bash
HDB info
```

---

# Summary

SAP HANA installation is a critical step in building an SAP landscape. Proper preparation, correct use of the `hdblcm` tool, validation of services, and understanding the roles of SYSTEMDB and Tenant Databases help ensure a stable and efficient SAP HANA environment.
