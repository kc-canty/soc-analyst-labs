# Windows Event Log Investigation — Findings Report  
**Analyst:** Keith C. Canty  
**Lab:** SOC Analyst Portfolio Project – Lab 1  
**Date:** November 13, 2025  

---

## 1. Objective  
Analyze Windows Security Events to identify a suspicious authentication pattern involving failed logons, a successful login, privilege escalation, and process creation.

---

## 2. Key Findings

### **2.1 Failed Logon Attempts — Event ID 4625**
- **TargetUserName:** Biskits  
- **Domain:** DESKTOP-O13JHH8  
- **Failure Reason:** Unknown username or bad password  
- **Logon Type:** 2 (interactive)  
- **Source Address:** 127.0.0.1  

### **2.2 Successful Logon — Event ID 4624**
Indicates a shift from unsuccessful to successful access.

### **2.3 Privilege Escalation — Event ID 4672**
Administrative privileges assigned to a new session.  
Indicates elevated rights.

### **2.4 Process Creation — Event ID 4688**
Processes launched after logon:
- `cmd.exe`
- `powershell.exe`
- `net.exe`
- `notepad.exe`

These are commonly used for discovery or malicious activity.

### **2.5 Logoff — Event ID 4634**
Session terminated cleanly.

---

## 3. Timeline Reconstruction  
## Timeline of Events


| Time (Local) | Event ID | Description                                      |
|--------------|----------|--------------------------------------------------|
| 10:44:12 PM  | 4625     | Failed logon attempt for user `Biskits`          |
| 10:44:16 PM  | 4625     | Repeated failed logon attempt                    |
| 10:44:19 PM  | 4625     | Repeated failed logon attempt                    |
| 10:44:21 PM  | 4625     | Repeated failed logon attempt                    |
| 10:44:28 PM  | 4624     | Successful interactive logon                     |
| 11:48:41 PM  | 4672     | Special privileges assigned to new logon         |
| 11:55:19 PM  | 4688     | Process created: `cmd.exe`                       |
| 11:55:19 PM  | 4688     | Process created: `powershell.exe`                |
| 11:55:19 PM  | 4688     | Process created: `net.exe`                       |
| 11:55:19 PM  | 4634     | Logoff / session end                             |

Note: Timeline gaps reflect audit policy corrections and required configuration steps (auditpol adjustments and enabling password-based authentication).


---

## 4. MITRE ATT&CK Mapping

| Technique | ID | Evidence |
|-----------|----|----------|
| Brute Force | **T1110** | 4625 cluster |
| Valid Accounts | **T1078** | Successful 4624 logon |
| Privilege Escalation | **T1068** | 4672 |
| Command Execution | **T1059** | 4688 |
| Account Discovery | **T1087** | net.exe |

---

## 5. Recommendations
- Enforce MFA for all accounts  
- Configure account lockout policy  
- Restrict PowerShell usage  
- Alert on privilege assignment events  
- Monitor sequences: `4625 → 4624 → 4672 → 4688`  
- Collect and centralize logs in a SIEM  

---

## Environment Notes: Audit Policy Troubleshooting & Configuration Steps
---

##  7. Conclusion  
This investigation confirms a complete authentication attack chain including failed logons, successful entry, elevation of privileges, and suspicious command execution. These findings mirror common adversary behavior and validate competence in host-based log analysis.


