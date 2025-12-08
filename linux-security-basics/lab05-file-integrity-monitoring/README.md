# Linux File Integrity Monitoring (FIM) Lab

## Objective
Simulate unauthorized modification of Linux system files and detect the changes using baseline SHA256 hashing, timestamp inspection, and recent-modification scanning.  
This lab mirrors core functionality found in enterprise File Integrity Monitoring tools such as **Wazuh**, **Tripwire**, and **OSSEC**.

---

## Skills Demonstrated

- Establishing a baseline of trusted file hashes  
- Detecting unauthorized file changes (hash mismatch)  
- Using `stat` to analyze modification timestamps (mtime/ctime)  
- Identifying recently changed files with `find`  
- Understanding persistence and tampering behaviors  
- Mapping Linux activity to MITRE ATT&CK  
- Producing SOC-style notes and a findings summary  

---

## Lab Summary

This lab shows how a defender can detect unauthorized file modification—one of the most common methods attackers use to:

- modify configurations  
- hide malicious code  
- establish persistence  
- weaken system security  

By comparing current file states against a trusted baseline, we can quickly determine whether a file has been altered.

---

## Methodology

1. **Created a clean baseline** of three system-like files.  
2. Generated SHA256 hashes and saved them to `baseline/hashes.txt`.  
3. Simulated an attack by modifying `file2.txt`.  
4. Recalculated hashes and identified the mismatch.  
5. Used `stat` to reveal updated modification/change timestamps.  
6. Used `find` to identify recently modified files.  
7. Documented all findings and mapped activity to MITRE ATT&CK.  

---

## MITRE ATT&CK Techniques

| Technique ID | Name                                  |
|--------------|----------------------------------------|
| **T1565**    | Data Manipulation                      |
| **T1070**    | Indicator Removal / Tampering          |
| **T1547**    | Persistence via Modified Files         |
| **T1027**    | Obfuscated or Modified Files           |

---

## Tools Used
- `sha256sum`  
- `stat`  
- `find`  
- Bash (Ubuntu / WSL2)

---

## Evidence
All screenshots for this lab are stored in the `evidence/` directory:
- Baseline hashes  
- Modified file hash comparison  
- Timestamp changes  
- Recent-modification scan output  

---

## Notes & Reporting
- Analyst notes located in `notes/event-notes.md`  
- Findings summary located in `notes/findings-summary.md`

---

## Analyst Value

This lab demonstrates my ability to:

- Build defensive detection processes from scratch  
- Validate file integrity without relying on third-party tools  
- Identify indicators of tampering, persistence, and misconfiguration  
- Explain system artifacts in clear, SOC-ready language  
- Analyze Linux behavior in a methodical, evidence-driven manner  

These are foundational skills for **SOC Analyst**, **Threat Hunter**, **Incident Responder**, and **Cloud Security** roles.

---

## Author
**Keith C. Canty**  
Aspiring Security Analyst & Cloud Security Engineer  
GitHub Portfolio: https://github.com/kc-canty/soc-analyst-labs
