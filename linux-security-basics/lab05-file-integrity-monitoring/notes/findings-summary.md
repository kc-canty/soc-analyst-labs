
# Findings Summary – Linux File Integrity Monitoring

## Overview
This lab simulated unauthorized modification of a Linux file and demonstrated how to detect integrity changes using SHA256 hashing, timestamps, and recent-change scanning. It mirrors how File Integrity Monitoring (FIM) tools such as Tripwire or Wazuh identify tampering and persistence on servers.

## Key Findings
- file2.txt was intentionally modified after the baseline was created.
- The SHA256 hash for file2.txt no longer matched the original baseline value.
- `stat` showed recent modify/change timestamps for file2.txt.
- `find . -mmin -2` identified file2.txt as a recently modified file.

## MITRE ATT&CK Mapping
- T1565 – Data Manipulation
- T1070 – Indicator Removal / Tampering
- T1547 – Persistence via Modified Files or Configurations

## Impact
If this activity occurred on a production system, it could indicate:
- Malicious configuration changes
- Hidden backdoors
- Persistence mechanisms
- Attempts to weaken security controls

## Recommendations
- Implement automated FIM solutions (e.g., Wazuh, Tripwire, OSSEC).
- Restrict write permissions on critical configuration directories.
- Alert on unexpected file hash or timestamp changes.
- Combine FIM alerts with authentication and sudo logs for better context.
