# SOC Analyst Labs
A collection of hands-on SOC Analyst labs demonstrating skills in event log analysis, network traffic analysis, IAM, Linux, Python, Active Directory, and security operations workflows.

# Lab 1 — Windows Event Log Investigation  
_A SOC Analyst Portfolio Project by Keith Canty_

---

## Overview  
This project simulates a Tier 1 SOC Analyst investigation by analyzing Windows Security Event Logs to identify:

- Multiple failed logon attempts (Event ID **4625**)  
- A successful authentication following failures (Event ID **4624**)  
- Privilege escalation via an admin context (Event ID **4672**)  
- Suspicious process creation post-authentication (Event ID **4688**)  
- Session termination (Event ID **4634**)  

This attack chain reflects a common brute-force → compromise → escalation pattern.

---

## Tools Used
- **Windows 11 Pro**
- **Event Viewer**
- **Local Security Policy**
- **Auditpol**
- **PowerShell**

---

## Folder Contents

<details>
<summary>Environment Setup Notes: Audit Policy Troubleshooting & Configuration Steps</summary>

During the initial execution of this lab, several expected security events were not being generated—specifically failed logon attempts (4625) and process creation events (4688). This required deeper investigation into Windows audit policies and authentication behavior. The following details outline the troubleshooting and configuration steps taken to ensure accurate event logging:

1. Problem Identified: Failed Logon Attempts (4625) Not Appearing

Although incorrect passwords were entered multiple times during testing, Event ID 4625 did not appear in the Windows Security Log.

Root Cause 1 — Passwordless Logon Method

Windows was using a PIN/Hello authentication provider instead of password-based logon.
PIN-based logins do not generate 4625 because they bypass traditional Winlogon authentication.

Root Cause 2 — No Password on the Local Account

A local account without a password cannot generate password-based authentication failures.

Fix:

Created a proper local account password

Switched to sign-in using password mode (Sign-in Options → Key Icon)

Retested failed logons
→ 4625 events immediately appeared

2. Problem Identified: Process Creation Events (4688) Not Appearing

Despite launching multiple processes (cmd.exe, powershell.exe, net.exe), 4688 events were missing.

Root Cause:

Windows' default audit policy does not enable Process Creation auditing, even on Pro or enterprise systems.

Fix:

Enabled Process Creation auditing using:

Method A — Local Security Policy

secpol.msc
Security Settings → Local Policies → Audit Policy → Audit process tracking
Enabled: Success & Failure

Method B — auditpol (Confirmed Status)

auditpol /get /subcategory:"Process Creation"

After enabling this policy → 4688 events began appearing properly.

3. Problem Identified: Log Events Were Spread Out Instead of Sequential

Due to troubleshooting steps, the timeline contained wider gaps between events.

 Explanation:

Time was required to enable correct audit policies

A local password had to be added

Logons had to be repeated using the password provider

Process tracking configuration required enabling and retesting

Once these conditions were corrected, the final attack chain was regenerated cleanly.

4. Skills Demonstrated

These troubleshooting steps demonstrate multiple real-world SOC and sysadmin competencies:

* Audit policy configuration and verification

Understanding how auditing works beyond the GUI interface.

* Investigation of missing security events

A common real problem analysts face when logs don’t align.

* Authentication mechanism awareness

PIN/Hello vs. password provider and how they impact logs.

* Using Windows built-in tools for diagnosis

Event Viewer

auditpol

Local Security Policy (secpol.msc)

PowerShell

* Iterative testing and verification

Systematic approach to testing → adjusting → retesting.


</details>
