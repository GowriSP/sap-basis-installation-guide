# Useful SAP BASIS Transactions

## Overview

SAP BASIS administrators use a wide range of SAP transactions for system administration, monitoring, performance tuning, security, transport management, database administration, and troubleshooting.

This document provides a categorized reference of commonly used SAP BASIS transactions.

---

# System Monitoring

| T-Code | Description |
|---------|-------------|
| SM50 | Work Process Overview |
| SM51 | Application Server List |
| SM66 | Global Work Process Overview |
| SM21 | System Log |
| ST22 | ABAP Runtime Errors (Dumps) |
| ST06 | Operating System Monitor |
| ST03N | Workload Analysis |
| ST02 | Tune Summary (Buffers) |
| ST04 | Database Performance Monitor |
| DBACOCKPIT | Database Administration |

---

# User Administration

| T-Code | Description |
|---------|-------------|
| SU01 | User Maintenance |
| SU10 | Mass User Maintenance |
| SU53 | Authorization Check |
| PFCG | Role Maintenance |
| SUIM | User Information System |
| SLICENSE | License Management |

---

# Transport Management

| T-Code | Description |
|---------|-------------|
| STMS | Transport Management System |
| SE09 | Workbench Requests |
| SE10 | Customizing Requests |
| SCC1 | Client Transport |
| SCC4 | Client Administration |

---

# Client Administration

| T-Code | Description |
|---------|-------------|
| SCC4 | Client Maintenance |
| SCCL | Local Client Copy |
| SCC9 | Remote Client Copy |
| SCC3 | Client Copy Logs |
| SCC5 | Client Deletion |

---

# Background Jobs

| T-Code | Description |
|---------|-------------|
| SM36 | Schedule Background Jobs |
| SM37 | Job Monitoring |
| SM62 | Event Maintenance |
| SM64 | Event Administration |

---

# Spool Administration

| T-Code | Description |
|---------|-------------|
| SPAD | Output Device Configuration |
| SP01 | Display Spool Requests |
| SP02 | Own Spool Requests |

---

# RFC & Communication

| T-Code | Description |
|---------|-------------|
| SM59 | RFC Destinations |
| SMGW | Gateway Monitor |
| SMICM | Internet Communication Manager |
| SICF | ICF Service Maintenance |
| STRUST | SSL Certificate Management |

---

# Profile Administration

| T-Code | Description |
|---------|-------------|
| RZ10 | Profile Maintenance |
| RZ11 | Display Profile Parameters |
| RZ20 | CCMS Monitoring |
| RZ04 | Operation Modes |

---

# System Administration

| T-Code | Description |
|---------|-------------|
| AL11 | SAP Directories |
| SM12 | Lock Entries |
| SM13 | Update Records |
| SM04 | User Sessions |
| AL08 | Global User Sessions |
| SMLG | Logon Groups |
| SM02 | System Messages |

---

# Database & SAP HANA

| T-Code | Description |
|---------|-------------|
| DBACOCKPIT | Database Administration |
| ST04 | Database Performance |
| DB02 | Database Space Analysis |
| DB12 | Backup Scheduler (Classic DBs) |

---

# Performance Analysis

| T-Code | Description |
|---------|-------------|
| ST03N | Workload Analysis |
| ST05 | SQL Trace |
| ST12 | Performance Trace |
| SAT | Runtime Analysis |
| ST02 | Buffer Analysis |
| ST06 | OS Performance |

---

# Logs & Troubleshooting

| T-Code | Description |
|---------|-------------|
| SM21 | System Log |
| ST22 | ABAP Dumps |
| SM13 | Update Errors |
| SLG1 | Application Log |
| SMQ1 | Outbound qRFC |
| SMQ2 | Inbound qRFC |

---

# Software Maintenance

| T-Code | Description |
|---------|-------------|
| SPAM | Support Package Manager |
| SAINT | Add-On Installation Tool |
| SNOTE | SAP Note Assistant |
| SPAU | Repository Object Adjustment |
| SPDD | Dictionary Object Adjustment |

---

# Printing & Output

| T-Code | Description |
|---------|-------------|
| SPAD | Printer Administration |
| SP01 | Spool Requests |
| SP02 | User Spool Requests |

---

# Security

| T-Code | Description |
|---------|-------------|
| SU01 | User Maintenance |
| PFCG | Role Maintenance |
| SU53 | Authorization Errors |
| SUIM | User Information |
| STRUST | Trust Manager |
| SNCWIZARD | Secure Network Communication |

---

# Commonly Used Daily Transactions

| T-Code | Purpose |
|---------|----------|
| SM50 | Check Work Processes |
| SM51 | Verify Application Servers |
| SM21 | Review System Log |
| ST22 | Analyze Dumps |
| SM37 | Monitor Background Jobs |
| SP01 | Check Print Requests |
| DBACOCKPIT | Monitor Database |
| ST03N | Analyze Performance |
| SM59 | Test RFC Connections |
| AL11 | View SAP Directories |

---

# Interview Questions

### Q1. Which transaction is used to monitor work processes?

```
SM50
```

---

### Q2. Which transaction is used to analyze ABAP dumps?

```
ST22
```

---

### Q3. Which transaction is used to configure Transport Management?

```
STMS
```

---

### Q4. Which transaction is used for user administration?

```
SU01
```

---

### Q5. Which transaction is used to analyze workload?

```
ST03N
```

---

# Summary

SAP BASIS administrators use transactions across multiple functional areas including monitoring, security, transport management, performance tuning, and troubleshooting. Familiarity with these transactions enables efficient system administration and is essential for day-to-day BASIS operations as well as interview preparation.
