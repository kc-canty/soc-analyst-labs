# Linux File Integrity Monitoring (FIM) Lab

## Objective
Simulate unauthorized modification of a Linux file and detect it using baseline hashing, timestamp inspection, and recent-change scanning. This lab mirrors the core functionality of enterprise File Integrity Monitoring (FIM) tools such as Tripwire and Wazuh.

## Skills Demonstrated
- Creating baseline file integrity hashes (SHA256)
- Detecting unauthorized file changes
- Using `stat` to inspect timestamps (mtime, ctime)
- Using `find` to identify recent file modifications
- Understanding integrity and persistence-related attack behaviors
- Mapping activity to MITRE ATT&CK

## MITRE ATT&CK Techniques
- **T1565 – Data Manipulation**
- **T1070 – Indicator Removal or Tampering**
- **T1547 – Persistence via Modified Files**
- **T1027 – Obfuscated or Modified Files**

## Tools Used
- sha256sum
- stat
- find
- bash

## Evidence
All screenshots for this lab are stored in `/evidence`.

## Notes
Investigation notes and summary report are located in `/notes`.

