# Post Installation Activities

## Overview

After a successful SAP system installation, several configuration and validation tasks must be completed before the system is ready for business use. These activities ensure the SAP landscape is secure, stable, properly configured, and ready for administration.

This guide covers the essential post-installation tasks performed by SAP BASIS Administrators.

---

# Objectives

After completing post-installation activities, the administrator should ensure:

- SAP system is accessible
- SAP license is installed
- System users are configured
- Transport Management System (TMS) is configured
- Profiles are verified
- Background jobs are scheduled
- Backup strategy is established
- System health is validated

---

# Verify SAP Instance

Confirm that all SAP services are running.

Linux Command:

```bash
sapcontrol -nr <Instance_Number> -function GetProcessList
```

SAP GUI Transaction:

```
SM51
```

Verify:

- Dispatcher
- Gateway
- Message Server
- ICM
- Work Processes

---

# Verify Work Processes

Transaction:

```
SM50
```

Check:

- DIA (Dialog)
- BTC (Background)
- UPD (Update)
- SPO (Spool)
- ENQ (Enqueue)

Ensure all work processes are in a healthy state.

---

# Review System Log

Transaction:

```
SM21
```

Review:

- Startup messages
- Errors
- Warnings
- Database connection messages
- Operating system events

---

# Check ABAP Dumps

Transaction:

```
ST22
```

Ensure no critical dumps occurred during installation.

---

# Install SAP License

Transaction:

```
SLICENSE
```

Steps:

1. Open SLICENSE
2. Install the license key
3. Verify expiration date
4. Confirm installation

Without a valid license, the SAP system may become unavailable after the temporary license expires.

---

# Create Administrative Users

Transaction:

```
SU01
```

Typical administrative users:

- BASIS Administrator
- System Administrator
- Support User
- Monitoring User

Assign appropriate roles and authorizations.

---

# Configure Transport Management System

Transaction:

```
STMS
```

Activities:

- Create Transport Domain
- Add Systems
- Configure Routes
- Verify Domain Controller
- Test Transport Connectivity

---

# Verify Profiles

Transactions:

```
RZ10
```

```
RZ11
```

Review important profile parameters:

- Memory configuration
- Work process settings
- Login parameters
- Security parameters
- Gateway parameters

---

# Configure Operation Modes

Transaction:

```
RZ04
```

Operation Modes allow administrators to allocate work processes based on business requirements, such as increasing background work processes during batch processing hours.

---

# Configure Background Jobs

Transaction:

```
SM36
```

Examples:

- Database Backup Jobs
- Housekeeping Jobs
- Monitoring Jobs
- Cleanup Jobs

Monitor scheduled jobs using:

```
SM37
```

---

# Configure Spool Administration

Transaction:

```
SPAD
```

Verify:

- Output Devices
- Print Servers
- Default Printer
- Spool Requests

---

# Configure RFC Connections

Transaction:

```
SM59
```

Verify:

- Destination Availability
- Connection Test
- Authorization
- Gateway Connectivity

---

# Backup Configuration

Ensure a backup strategy is in place.

Typical backups include:

- SAP HANA Data Backup
- Log Backup
- Profile Backup
- Kernel Backup
- Transport Directory Backup

Verify backup schedules and retention policies.

---

# Performance Validation

Review system performance using:

| Transaction | Purpose |
|------------|---------|
| ST03N | Workload Analysis |
| ST06 | Operating System Monitor |
| DBACOCKPIT | Database Monitoring |
| ST02 | Buffer Monitoring |
| ST04 | Database Performance |

---

# Security Validation

Verify:

- Default passwords changed
- Unnecessary users locked
- Profile parameters reviewed
- Audit logging enabled (if applicable)
- Secure RFC configuration

---

# Health Check Checklist

Ensure the following are verified:

- SAP Instance Running
- HANA Database Running
- No ABAP Dumps
- No Critical System Logs
- Transport System Configured
- Users Created
- License Installed
- Background Jobs Active
- Backup Configured
- System Performance Verified

---

# Common Issues

## License Not Installed

**Cause**

License key missing or expired.

**Resolution**

Install a valid license using `SLICENSE`.

---

## Work Process Errors

**Cause**

Incorrect profile parameters or resource issues.

**Resolution**

Review `SM50`, `SM21`, and profile settings.

---

## Transport Configuration Failed

**Cause**

Domain Controller not configured correctly.

**Resolution**

Reconfigure the Transport Domain using `STMS`.

---

## Background Jobs Not Running

**Cause**

Job scheduling issues.

**Resolution**

Review job definitions in `SM36` and monitor execution in `SM37`.

---

## RFC Connection Failed

**Cause**

Incorrect destination settings or network issues.

**Resolution**

Test the RFC connection in `SM59` and verify network connectivity.

---

# Best Practices

- Verify system health immediately after installation.
- Change all default passwords.
- Configure transport management before development activities begin.
- Schedule regular backups.
- Monitor system logs during the first few days after installation.
- Document all post-installation configurations.
- Perform a complete validation before handing the system over to users.

---

# Interview Questions

### Q1. Which transaction is used to install the SAP license?

```
SLICENSE
```

---

### Q2. Which transaction is used to configure Transport Management?

```
STMS
```

---

### Q3. Which transaction is used to create SAP users?

```
SU01
```

---

### Q4. Which transactions are used to maintain profile parameters?

```
RZ10
RZ11
```

---

### Q5. Why are post-installation activities important?

Post-installation activities ensure that the SAP system is secure, properly configured, validated, and ready for productive use. They help establish system stability, enable administration, and reduce the risk of operational issues.

---

# Summary

Post-installation activities are a crucial phase of SAP BASIS administration. They involve validating system functionality, configuring administration tools, establishing security, enabling transport management, scheduling backups, and confirming that the SAP landscape is fully operational. A thorough post-installation checklist helps ensure a reliable and production-ready SAP environment.
