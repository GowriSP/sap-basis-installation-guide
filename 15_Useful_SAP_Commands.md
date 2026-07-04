# Useful SAP Commands

## Overview

SAP BASIS administrators frequently use operating system commands to start and stop SAP systems, monitor SAP instances, verify kernel versions, check database connectivity, and troubleshoot issues.

This document provides commonly used SAP commands with their purpose and usage.

---

# SAP System Start & Stop

## Start SAP System

```bash
startsap
```

**Purpose**

Starts all SAP services associated with the current SAP instance.

---

## Stop SAP System

```bash
stopsap
```

**Purpose**

Stops all SAP services gracefully.

---

## Start SAP Using sapcontrol

```bash
sapcontrol -nr <Instance_Number> -function StartSystem ALL
```

**Example**

```bash
sapcontrol -nr 00 -function StartSystem ALL
```

---

## Stop SAP Using sapcontrol

```bash
sapcontrol -nr <Instance_Number> -function StopSystem ALL
```

---

# SAP Process Monitoring

## Display SAP Processes

```bash
sapcontrol -nr <Instance_Number> -function GetProcessList
```

**Purpose**

Displays the status of:

- Dispatcher
- Gateway
- ICM
- Message Server
- Enqueue Server

Expected status:

```
GREEN
```

---

## List SAP Instances

```bash
sapcontrol -function GetSystemInstanceList
```

---

## Check SAP Start Service

```bash
sapcontrol -nr <Instance_Number> -function GetVersionInfo
```

---

# Kernel Commands

## Check Kernel Version

```bash
disp+work -version
```

Displays:

- Kernel Release
- Patch Level
- Build Number

---

## SAP Kernel Executable

```bash
disp+work
```

Starts the SAP dispatcher process.

---

# Database Commands

## Test Database Connectivity

```bash
R3trans -d
```

Expected output:

```
R3trans finished (0000)
```

This confirms successful SAP-to-database connectivity.

---

# SAP HANA Commands

## Check HANA Status

```bash
HDB info
```

---

## Start HANA

```bash
HDB start
```

---

## Stop HANA

```bash
HDB stop
```

---

## Restart HANA

```bash
HDB restart
```

---

## HANA Version

```bash
HDB version
```

---

# SAP Host Agent Commands

## Check Host Agent Version

```bash
saphostctrl -function GetVersionInfo
```

---

## List SAP Instances

```bash
saphostctrl -function ListInstances
```

---

## Get Process List

```bash
saphostctrl -function GetProcessList
```

---

# Transport Commands

## Transport Control Program

```bash
tp
```

Used for:

- Import transports
- Export transports
- Check transport configuration

Example:

```bash
tp showbuffer DEV
```

---

# SAP Profile Commands

Display environment variables:

```bash
echo $DIR_INSTANCE
```

Display SAP SID:

```bash
echo $SAPSYSTEMNAME
```

Display Instance Number:

```bash
echo $SAPSYSTEM
```

---

# Log Monitoring

Display dispatcher log:

```bash
tail -f dev_disp
```

Display work process log:

```bash
tail -f dev_w0
```

Display gateway log:

```bash
tail -f dev_rd
```

---

# SAP Archive Utility

Extract SAP archive:

```bash
SAPCAR -xvf SAPEXE.SAR
```

Create archive:

```bash
SAPCAR -cvf archive.SAR folder
```

---

# IPC Cleanup

```bash
cleanipc <Instance_Number> remove
```

**Purpose**

Removes orphaned shared memory and semaphore objects after abnormal SAP shutdowns.

Use only when SAP is completely stopped.

---

# SAP Copy Program

```bash
sapcpe
```

**Purpose**

Copies kernel executables from the central directory to the local instance.

---

# Frequently Used Commands

| Command | Purpose |
|---------|---------|
| startsap | Start SAP |
| stopsap | Stop SAP |
| sapcontrol | Control SAP instances |
| disp+work -version | Kernel version |
| R3trans -d | Database connectivity |
| HDB info | HANA status |
| HDB start | Start HANA |
| HDB stop | Stop HANA |
| tp | Transport control |
| SAPCAR | Extract SAP archives |
| cleanipc | Clean IPC resources |
| sapcpe | Copy kernel files |

---

# Troubleshooting Commands

Check running SAP processes:

```bash
ps -ef | grep sap
```

Check open SAP ports:

```bash
netstat -tulpn
```

Check disk usage:

```bash
df -h
```

Check memory:

```bash
free -h
```

Monitor CPU:

```bash
top
```

---

# Interview Questions

### Q1. Which command checks the SAP kernel version?

```bash
disp+work -version
```

---

### Q2. Which command tests SAP database connectivity?

```bash
R3trans -d
```

---

### Q3. Which command displays SAP process status?

```bash
sapcontrol -nr <Instance_Number> -function GetProcessList
```

---

### Q4. Which command starts SAP HANA?

```bash
HDB start
```

---

### Q5. What is the purpose of the `cleanipc` command?

It removes orphaned shared memory and semaphore objects after an abnormal SAP shutdown. It should only be used when the SAP instance is completely stopped.

---

# Best Practices

- Always verify SAP process status after starting or stopping an instance.
- Run `R3trans -d` after installation or database changes to confirm connectivity.
- Check kernel version after upgrades.
- Monitor HANA services regularly using `HDB info`.
- Avoid using `cleanipc` unless you are certain the SAP instance is fully stopped.
- Keep a record of commonly used commands for faster troubleshooting.

---

# Summary

Operating system–level SAP commands are essential for SAP BASIS administration. They support system startup and shutdown, process monitoring, database validation, kernel verification, transport management, and troubleshooting. Understanding these commands enables administrators to manage SAP landscapes efficiently and respond quickly to operational issues.
