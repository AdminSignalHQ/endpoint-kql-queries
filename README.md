# Endpoint Engineering KQL Hunting & Compliance Queries 🔍

[![Website](https://img.shields.io/badge/Companion%20Guides-adminsignal.com-0078D4?style=for-the-badge&logo=google-chrome&logoColor=white)](https://adminsignal.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Defender XDR](https://img.shields.io/badge/Defender%20XDR-Advanced%20Hunting-00A4EF?style=for-the-badge&logo=microsoft&logoColor=white)](https://security.microsoft.com)

A collection of practical **Kusto Query Language (KQL)** queries built specifically for **Windows Endpoint Engineers and Intune Administrators** using Microsoft Defender XDR Advanced Hunting.

While most KQL repositories focus purely on SOC threat hunting, this library focuses on **operational endpoint engineering**: auditing Attack Surface Reduction (ASR) impact before enforcing Block mode, finding vulnerable OEM drivers before enabling HVCI, verifying Tamper Protection, and tracking local admin sprawl.

---

## 📂 Query Index

| Category | Query File | Engineering Use Case |
| :--- | :--- | :--- |
| **ASR Rules** | [**ASR-Rules/Audit-ASRRuleTriggers.kql**](ASR-Rules/Audit-ASRRuleTriggers.kql) | Group ASR audit & block events by path, process, and affected device count to build clean exclusions before enforcing Block mode. |
| **Drivers & HVCI** | [**Driver-and-Hardware/Find-VulnerableDriversBlocked.kql**](Driver-and-Hardware/Find-VulnerableDriversBlocked.kql) | Identify legacy OEM or third-party kernel drivers hitting the Microsoft Vulnerable Driver Blocklist. |
| **Patch & OS** | [**Patch-and-Compliance/Find-MissingCriticalUpdates.kql**](Patch-and-Compliance/Find-MissingCriticalUpdates.kql) | Locate internet-facing or corporate endpoints missing Critical/High Windows cumulative updates. |
| **Security Posture** | [**BitLocker-and-Security/Audit-TamperProtectionAndSensorHealth.kql**](BitLocker-and-Security/Audit-TamperProtectionAndSensorHealth.kql) | Audit endpoints where Tamper Protection, Real-Time Protection, or BitLocker encryption is non-compliant. |
| **Local Admins** | [**Access-and-Identity/Track-LocalAdminAdditions.kql**](Access-and-Identity/Track-LocalAdminAdditions.kql) | Detect accounts added to the local Administrators group (S-1-5-32-544) outside of Windows LAPS. |

---

## ⚡ How to Use
1. Open the [**Microsoft Defender Portal**](https://security.microsoft.com).
2. Navigate to **Investigation & response** > **Hunting** > **Advanced hunting**.
3. Paste any .kql query from this repository and adjust the go(30d) window as needed.

---

## 📖 Related Guides on AdminSignal
* [Rolling Out Defender ASR Rules Without Breaking Line-of-Business Apps](https://adminsignal.com)
* [Using Defender Advanced Hunting for Endpoint Engineering & Patch Validation](https://adminsignal.com)
