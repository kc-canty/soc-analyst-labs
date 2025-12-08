# Linux Authentication Log Analysis (auth.log)

## Objective
Analyze `/var/log/auth.log` to identify failed login attempts, invalid users, and suspicious sudo activity on a Linux system. This lab demonstrates foundational SOC-level log analysis skills relevant for threat detection and incident response.

## Skills Demonstrated
- Linux log analysis
- Failed authentication investigation
- Privilege escalation detection (sudo)
- Basic bash log filtering
- MITRE ATT&CK mapping (Credential Access, Privilege Escalation)

## Tools Used
- Ubuntu Linux 
- Bash terminal
- grep, cat, less, tail, awk

## Log Sources Analyzed
- `/var/log/auth.log`

## Evidence Collected
See `evidence/` folder for screenshots of:
- Invalid user attempts
- Failed password attempts
- Sudo misuse or failed sudo attempts
- Any suspicious pattern observed

## Summary of Findings
See `notes/findings-summary.md` for a human-readable breakdown of all detected events and their meaning.

## MITRE Mappings
- T1110 – Brute Force
- T1078 – Valid Accounts
- T1059 – Command & Scripting Interpreter (Bash)
- T1068 – Privilege Escalation (sudo misuse)

## Author
Keith C. Canty – Cybersecurity Analyst (In Progress)
GitHub: github.com/kc-canty/soc-analyst-labs/

