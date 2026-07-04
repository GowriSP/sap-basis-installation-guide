# Appendix

## Overview

This appendix provides a quick reference to commonly used SAP BASIS terms, abbreviations, components, and concepts. It serves as a glossary for beginners and a handy reference for SAP BASIS administrators during installation, administration, and troubleshooting activities.

---

# SAP Acronyms

| Acronym | Full Form |
|----------|-----------|
| SAP | Systems, Applications and Products in Data Processing |
| BASIS | Business Application Software Integrated Solution |
| HANA | High-Performance Analytic Appliance |
| SWPM | Software Provisioning Manager |
| SUM | Software Update Manager |
| SID | System Identifier |
| GUI | Graphical User Interface |
| RFC | Remote Function Call |
| TMS | Transport Management System |
| ICM | Internet Communication Manager |
| OS | Operating System |
| DB | Database |
| CPU | Central Processing Unit |
| RAM | Random Access Memory |
| DNS | Domain Name System |
| NTP | Network Time Protocol |

---

# SAP Landscape

A standard SAP landscape consists of:

- Development (DEV)
- Quality Assurance (QAS)
- Production (PRD)

Purpose:

- **DEV** – Development and customization
- **QAS** – Testing and validation
- **PRD** – Live business operations

---

# SAP System Components

## Presentation Layer

- SAP GUI
- User Interface

---

## Application Layer

- Dispatcher
- Work Processes
- Gateway
- Message Server
- ICM

---

## Database Layer

- SAP HANA Database
- Data Files
- Log Files

---

# SAP Work Processes

| Type | Description |
|------|-------------|
| DIA | Dialog Processing |
| BTC | Background Processing |
| UPD | Update Processing |
| UPD2 | Secondary Update |
| ENQ | Lock Management |
| SPO | Spool Processing |

---

# Important SAP Directories

| Directory | Purpose |
|------------|---------|
| /usr/sap | SAP System Files |
| /sapmnt | Global SAP Directory |
| /hana/shared | Shared HANA Files |
| /hana/data | Database Data |
| /hana/log | Database Logs |
| /usr/sap/hostctrl | SAP Host Agent |

---

# Important Linux Commands

| Command | Purpose |
|----------|---------|
| hostname | Display Hostname |
| df -h | Disk Usage |
| free -h | Memory Usage |
| top | CPU & Memory Monitoring |
| ps -ef | Running Processes |
| systemctl status | Service Status |
| ping | Network Connectivity |
| uname -r | Kernel Version |

---

# Important SAP Commands

| Command | Purpose |
|----------|---------|
| startsap | Start SAP System |
| stopsap | Stop SAP System |
| sapcontrol | SAP Service Control |
| disp+work -version | Check Kernel Version |
| HDB info | HANA Service Status |
| HDB start | Start HANA |
| HDB stop | Stop HANA |
| R3trans -d | Database Connectivity Test |

---

# Common SAP Transactions

| Transaction | Purpose |
|--------------|---------|
| SM50 | Work Process Monitoring |
| SM51 | Application Server List |
| SM21 | System Log |
| ST22 | ABAP Dumps |
| STMS | Transport Management |
| SU01 | User Administration |
| SM59 | RFC Destinations |
| SPAD | Spool Administration |
| DBACOCKPIT | Database Administration |
| ST03N | Workload Analysis |
| ST06 | Operating System Monitor |
| RZ10 | Profile Maintenance |
| RZ11 | Display Profile Parameters |
| SLICENSE | License Management |

---

# Common SAP Ports

| Service | Default Port Example |
|----------|----------------------|
| SAP GUI | 32<Instance Number> |
| Gateway | 33<Instance Number> |
| Message Server | 36<Instance Number> |
| ICM HTTP | 80<Instance Number> |
| ICM HTTPS | 443<Instance Number> |

> **Note:** The actual port number depends on the SAP instance number.

---

# Frequently Used SAP Users

| User | Purpose |
|------|---------|
| `<SID>adm` | SAP System Administrator (OS User) |
| `sapadm` | SAP Host Agent Administrator |
| `SYSTEM` | SAP HANA Database Administrator |
| `DDIC` | SAP Data Dictionary User |
| `SAP*` | Emergency SAP User |

---

# SAP Installation Tools

| Tool | Purpose |
|------|---------|
| SAPCAR | Extract SAP Archives |
| SWPM | SAP System Installation |
| SUM | Software Update |
| HDBLCM | SAP HANA Installation & Lifecycle Management |
| SAP Host Agent | Host Monitoring & Administration |

---

# Best Practices

- Follow SAP Product Availability Matrix (PAM) before installation.
- Keep SAP Kernel and Host Agent updated.
- Perform regular backups of SAP systems and databases.
- Monitor system logs and work processes daily.
- Document all system changes and maintenance activities.
- Test changes in Development and Quality systems before Production.

---

# References

For official guidance, always refer to:

- SAP Help Portal
- SAP Product Availability Matrix (PAM)
- SAP Notes
- SAP Support Portal

---

# Summary

This appendix serves as a quick reference guide for SAP BASIS administrators. It consolidates commonly used terminology, commands, transactions, system components, and best practices into a single document, making day-to-day administration and interview preparation more efficient.
