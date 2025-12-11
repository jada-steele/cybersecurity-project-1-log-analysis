# 📄 Incident Report — Authentication Log Investigation

## **1. Executive Summary**
Between **November 20–21, 2025**, an attacker successfully compromised the **j.smith** account through a brute-force login attack originating from a foreign IP address.  
After gaining access, the attacker performed a **privilege escalation** from a Russian IP at approximately **03:04 AM**, indicating deeper unauthorized system access.  
Additional failed login attempts were observed targeting the **admin** account from multiple foreign countries.

This activity strongly suggests a coordinated unauthorized access incident.

---

## **2. Timeline of Events**

| Date/Time (UTC) | User | IP Address | Event | Notes |
|-----------------|------|------------|-------|-------|
| 2025-11-20 12:05–12:07 | j.smith | 185.244.23.17 (RU) | Multiple Failed Logins → Success | Successful brute-force attack |
| 2025-11-21 00:44 | j.smith | 102.133.98.200 (ZA) | Failed Logins | Continued attempts post-compromise |
| 2025-11-21 03:03 | j.smith | 185.244.23.17 (RU) | Successful Login | Unauthorized after-hours access |
| 2025-11-21 03:04 | j.smith | 185.244.23.17 (RU) | Privilege Escalation | Attacker elevated permissions |
| 2025-11-21 03:05 | j.smith | 185.244.23.17 (RU) | Logout | Attacker ended session |
| Various Times | admin | 77.91.68.22 (DE), 203.0.113.55 (BR) | Failed Logins | Attempted admin credential attacks |

---

## **3. Indicators of Compromise (IOCs)**

### **Suspicious IP Addresses**
- **185.244.23.17** — Russia (brute force + privilege escalation)  
- **102.133.98.200** — South Africa (repeated failed attempts)  
- **77.91.68.22** — Germany (admin account targeting)  
- **203.0.113.55** — Brazil (admin account targeting)  

### **Compromised Account**
- **j.smith** — Unauthorized logins and privilege escalation detected

### **Suspicious Events**
- Multiple failed authentication attempts  
- Successful login from foreign countries  
- Privilege escalation at abnormal hours  
- Failed admin login attempts from multiple regions  

---

## **4. Root Cause Analysis**
The **j.smith** account compromise was caused by:

- Weak or reused password credentials  
- No account lockout policy to stop brute-force attempts  
- Lack of geo-restrictions or MFA enforcement  

The attacker successfully authenticated after repeated failures and escalated privileges.

---

## **5. Impact Assessment**
Potential impacts include:

- Unauthorized access to sensitive systems  
- Possible exposure or modification of user data  
- Elevated risk due to stolen privileges  
- Repeated attempts to compromise administrator accounts  

No clear evidence of data exfiltration is visible in the provided logs, but deeper system review is recommended.

---

## **6. Mitigation Actions Taken**
- Reset password for **j.smith**  
- Forced session termination for all suspicious IPs  
- Temporarily disabled compromised user accounts  
- Reviewed privilege escalation logs for further anomalies  

---

## **7. Recommendations**
- Enable **multi-factor authentication (MFA)** for all accounts  
- Implement **account lockout thresholds** (e.g., after 5 failed attempts)  
- Restrict foreign IP logins or require **VPN access**  
- Strengthen **password policies** and enforce complexity  
- Increase monitoring on privileged accounts  
- Conduct a deeper audit for lateral movement or data access  

---

## **8. Conclusion**
The analysis confirms a **successful brute-force attack** resulting in **account compromise and privileg**

