### Incident Note 1 – Multiple Failed Logins

- **Threat Category**: Suspicious user behaviour / Anomaly detection
- **Detection Method**: Wazuh SIEM alert on Windows-Workstation agent
- **What Happened**: Multiple “Logon failure - Unknown user or bad password” events detected
- **Possible Attack**: Brute force or password guessing attempt
- **Impact**: Risk of unauthorized access (Confidentiality)
- **Recommended Countermeasure**:
  - Enable account lockout policy after 5 failed attempts
  - Monitor this user/account for further attempts
  - Notify system owner if activity continues
