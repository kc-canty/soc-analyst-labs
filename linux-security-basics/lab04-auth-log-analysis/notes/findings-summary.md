# Findings Summary – Linux Authentication Log Analysis

## Overview
Analyzed /var/log/auth.log for authentication-related activity including user login attempts, invalid users, and failed passwords.

## Key Findings
- Detected invalid user attempt for "fakeuser".
- Observed multiple failed SSH password attempts.
- Events were generated locally but simulate real-world external probing.
- No successful unauthorized access occurred.

## MITRE ATT&CK Mapping
- T1110 – Brute Force
- T1078 – Valid Accounts
- T1059 – Command & Scripting (Bash, SSH interactions)

## Impact
If this was from an external attacker, this pattern could indicate:
- Credential stuffing
- Username enumeration
- Preparation for brute-force access

## Recommendations
- Enable fail2ban
- Disable root SSH login
- Enforce strong password policy
- Consider switching SSH to key-based authentication only

