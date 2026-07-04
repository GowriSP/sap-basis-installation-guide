# SAP Installation Checklist

## Overview

This checklist provides a structured approach to SAP installation activities. It helps SAP BASIS administrators verify that all prerequisites, installation steps, and post-installation activities are completed successfully.

Use this checklist before handing over the SAP system to the project team or business users.

---

# Phase 1 – Planning

| Status | Task |
|---------|------|
| ☐ | SAP Product selected |
| ☐ | SAP Version verified |
| ☐ | SAP Product Availability Matrix (PAM) checked |
| ☐ | Installation guide reviewed |
| ☐ | Maintenance window approved |
| ☐ | Backup plan prepared |
| ☐ | Rollback plan documented |

---

# Phase 2 – Hardware Verification

| Status | Task |
|---------|------|
| ☐ | CPU requirements verified |
| ☐ | RAM requirements verified |
| ☐ | Disk space available |
| ☐ | Network connectivity verified |
| ☐ | Storage configured |
| ☐ | Virtual machine/resources allocated |

---

# Phase 3 – Operating System Preparation

| Status | Task |
|---------|------|
| ☐ | Supported Linux version installed |
| ☐ | Latest OS updates applied |
| ☐ | Hostname configured |
| ☐ | DNS resolution verified |
| ☐ | Static IP assigned |
| ☐ | Time synchronization configured |
| ☐ | Required packages installed |
| ☐ | Firewall reviewed |
| ☐ | SELinux configuration verified |

---

# Phase 4 – SAP Prerequisites

| Status | Task |
|---------|------|
| ☐ | SAP installation media downloaded |
| ☐ | SAPCAR available |
| ☐ | SAP Host Agent installed |
| ☐ | SAP users created |
| ☐ | SAP groups created |
| ☐ | Required directories created |
| ☐ | File permissions verified |

---

# Phase 5 – SAP HANA Installation

| Status | Task |
|---------|------|
| ☐ | HDBLCM executed |
| ☐ | SYSTEM password configured |
| ☐ | SID created |
| ☐ | Instance number assigned |
| ☐ | SYSTEMDB verified |
| ☐ | Tenant Database created |
| ☐ | HANA services running |

---

# Phase 6 – SWPM Installation

| Status | Task |
|---------|------|
| ☐ | SWPM extracted |
| ☐ | sapinst started |
| ☐ | Product selected |
| ☐ | Installation parameters verified |
| ☐ | SAP instance installed |
| ☐ | Installation logs reviewed |
| ☐ | Installation completed successfully |

---

# Phase 7 – SAP GUI Configuration

| Status | Task |
|---------|------|
| ☐ | SAP GUI installed |
| ☐ | SAP Logon configured |
| ☐ | System entry created |
| ☐ | Login successful |
| ☐ | Client verified |

---

# Phase 8 – Kernel Validation

| Status | Task |
|---------|------|
| ☐ | Kernel version verified |
| ☐ | Kernel files backed up |
| ☐ | Latest kernel installed (if applicable) |
| ☐ | SAP started successfully |

---

# Phase 9 – Post-Installation Activities

| Status | Task |
|---------|------|
| ☐ | SAP License installed |
| ☐ | Administrative users created |
| ☐ | STMS configured |
| ☐ | Profile parameters reviewed |
| ☐ | Background jobs configured |
| ☐ | RFC destinations configured |
| ☐ | Printers configured (SPAD) |

---

# Phase 10 – Validation Checks

| Status | Task |
|---------|------|
| ☐ | SM51 verified |
| ☐ | SM50 verified |
| ☐ | SM21 reviewed |
| ☐ | ST22 checked |
| ☐ | DBACOCKPIT reviewed |
| ☐ | SLICENSE verified |
| ☐ | STMS tested |
| ☐ | SM59 connection test successful |
| ☐ | Performance validation completed |

---

# Phase 11 – Backup & Documentation

| Status | Task |
|---------|------|
| ☐ | Initial database backup completed |
| ☐ | System configuration documented |
| ☐ | SID documented |
| ☐ | Instance numbers documented |
| ☐ | Installed software versions recorded |
| ☐ | Installation logs archived |

---

# Final Sign-Off Checklist

| Item | Status |
|------|--------|
| SAP System Installed | ☐ |
| SAP HANA Operational | ☐ |
| SAP GUI Accessible | ☐ |
| No Critical Errors | ☐ |
| Validation Completed | ☐ |
| Backup Completed | ☐ |
| Documentation Completed | ☐ |
| Ready for Handover | ☐ |

---

# Best Practices

- Complete each phase before moving to the next.
- Review SAP installation logs after every major step.
- Verify database connectivity before starting SWPM.
- Test SAP login before handing over the system.
- Perform an initial backup immediately after successful installation.
- Keep installation documentation for future audits and troubleshooting.

---

# Summary

A structured installation checklist helps SAP BASIS administrators perform consistent and reliable installations. It minimizes configuration errors, ensures all mandatory tasks are completed, and provides a documented record of the installation process for future maintenance and support.
