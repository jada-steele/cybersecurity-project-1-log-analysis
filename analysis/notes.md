# Log Analysis Notes

## 1. Dataset Used
authentication_logs.csv

## 2. Initial Observations
- Contains internal and external IP addresses
- Multiple users: j.smith, k.jones, m.garcia, a.martin, admin, guest
- Mix of successful and failed login attempts
- Includes login, logout, and privilege escalation events

## 3. Suspicious Activity Identified

### A. Brute-Force Attempts
- User: j.smith
- Source IP: 185.244.23.17 (Russia)
- Pattern: 5 consecutive failed logins followed by a successful login at 12:07
- Indicates a successful brute-force attack

### B. Unauthorized Geographic Access
- Multiple successful logins from Russia (RU) and South Africa (ZA)
- These locations are unusual based on typical login patterns

### C. Privilege Escalation After Compromise
- j.smith account had a successful privilege escalation at 03:04 from RU
- This suggests attacker lateral movement

### D. Suspicious Admin Account Activity
- admin account repeated failed logins from DE (Germany) and BR (Brazil)
- Indicates targeted attempts to compromise administrator credentials

## 4. Normal Baseline Activity
- Internal logins from 192.168.x.x and 10.x.x.x
- Users logging in during daytime hours in US-NC and US-TX
- Expected login/logout sequences

## 5. Preliminary Conclusion
The dataset shows clear signs of:
- A successful brute-force attack on j.smith
- Unauthorized foreign access
- Privilege escalation indicating deeper compromise
- Multiple attempts to break into admin accounts

A full incident report should be created based on these findings.

