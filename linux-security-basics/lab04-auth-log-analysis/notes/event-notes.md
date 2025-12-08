# Event Notes – Linux Auth Log Analysis

## Invalid User Attempts
- An invalid user "fakeuser" attempted to log in via SSH.
- Source IP: 127.0.0.1 (loopback)
- This indicates username enumeration or probing.

## Failed Password Attempts
- Multiple failed password attempts for user "fakeuser".
- Authentication failed via SSH protocol.

## Observed Behavior Summary
- Pattern resembles brute-force credential guessing.
- System rejected several attempts, no escalation achieved.

## Analyst Thoughts
- Repeated invalid user + failed password attempts are common early indicators of unauthorized access attempts.
- Further monitoring recommended.

