# SIEM Internship - Phase 1: Foundation Setup

This repository contains the setup and configurations done for Phase 1 of the SIEM Internship Program. The goal was to simulate and capture logs for various Windows security activities and forward them to a SIEM/log collection setup on Kali Linux for further analysis.

---

## 🔧 Environment Setup

* **Windows 10 VM** - Target machine for attacks and logging
* **Kali Linux VM** - Log collector and attacker machine
* **Network** - NAT setup with IP communication between VMs

### VM IP Addresses:

* **Windows 10 IP**: `10.0.2.4`
* **Kali Linux IP**: `10.0.2.15`

---

## ✅ Configurations Performed

### 1. PowerShell Logging Enabled

* Registry edits applied to enable detailed PowerShell logging.
* Screenshots:

  * `1_powershell_logging_registry`
  * `2_powershell_logging_registry`

### 2. Event Log Size Increased

* Security event log size increased to capture more entries.
* Screenshot:

  * `3_eventlog_size_security`

### 3. Audit Policy Configuration (auditpol)

* Auditpol commands run to enable logon and sensitive actions auditing.
* Screenshots:

  * `5_auditpol_configuration_windows(1)`
  * `5_auditpol_configuration_windows(2)`

### 4. Sysmon Installed

* Sysmon set up to capture advanced Windows events.
* Screenshot:

  * `Sysmon_Last10_Events`

### 5. Event Log Subscription Activated

* Subscription set up to forward Windows logs to Kali syslog-ng.
* Screenshot:

  * `Phase1_Screenshot6_SubscriptionActive`

---

## 📥 Log Forwarding to Kali (syslog-ng)

* Syslog-ng configured to listen on port 514 (TCP/UDP) and write logs to a file.
* Screenshots:

  * `4_syslog_ng_status_kali`
  * `07_windows_logs_received`

---

## 🧪 Detection Use Cases Simulated

### 1. Brute Force Attack (Manual Wrong Password Attempts)

* Multiple failed login attempts using wrong credentials.
* Screenshot:

  * `brute_force_failed_logon_event_4625`

### 2. Suspicious File Download

* Downloaded and accessed `putty.exe` installer.
* Screenshot:

  * `suspicious-file-download`

### 3. Remote Access via SSH

* Created a new user (`intern123`) on Windows.
* Enabled OpenSSH server on Windows.
* Accessed the Windows machine from Kali and PuTTY.
* Screenshots:

  * `putty ssh acces`
  * `Remote_Access_via_SSH.png`

### 4. Failed SSH Login

* Wrong login attempts recorded in Security logs (Event ID 4625).
* Screenshot:

  * `putty failed login log 4625`

---

## 📸 All Screenshots (in order):

1. 1\_powershell\_logging\_registry
2. 2\_powershell\_logging\_registry
3. 3\_eventlog\_size\_security
4. 5\_auditpol\_configuration\_windows(1)
5. 5\_auditpol\_configuration\_windows(2)
6. Phase1\_Screenshot6\_SubscriptionActive
7. 4\_syslog\_ng\_status\_kali
8. 07\_windows\_logs\_received
9. brute\_force\_failed\_logon\_event\_4625
10. suspicious-file-download
11. putty ssh acces
12. Remote\_Access\_via\_SSH.png
13. Sysmon\_Last10\_Events
14. putty failed login log 4625

---

