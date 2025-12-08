# Event Notes – File Integrity Monitoring Lab

## Baseline Creation
- Created three files: file1.txt, file2.txt, file3.txt.
- Generated SHA256 hashes for all three files and stored them in baseline/hashes.txt.
- Baseline represents the “known good” state of these files.

## Simulated Malicious Activity
- Modified file2.txt by appending: "Injected malicious config".
- This simulates an attacker tampering with a configuration file.

## Detection Methods
- Re-ran `sha256sum *` and observed a hash mismatch for file2.txt compared to baseline/hashes.txt.
- Used `stat file2.txt` to confirm recent modification and change timestamps.
- Ran `find . -mmin -2` to identify recently modified files (file2.txt was flagged).

## Analyst Thoughts
- Unauthorized changes to config or system files are strong indicators of potential persistence or data manipulation.
- Hash baselines and timestamp monitoring are effective low-cost ways to detect this behavior in Linux environments.

