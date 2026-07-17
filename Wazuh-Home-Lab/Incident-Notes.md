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


Incident Note 2 – File Added to the System

Threat Category: File Integrity Monitoring / Unauthorized file creation
Detection Method: Wazuh SIEM – File Integrity Monitoring (syscheck) on Windows-Workstation
What Happened: A new file was added to the system:
C:\Users\All Users\Microsoft\Diagnosis\AggregatorStorage\Triggers\9229153479643334637_trigger.dat
Alert Details:
Rule Description: File added to the system
Rule ID: 554
Agent: Windows-Workstation

Possible Cause:
Normal system/Microsoft diagnostic activity
Or potentially suspicious software creating files in system locations

Impact:
Low to Medium – New files in system folders can sometimes be used by malware for persistence or data collection
Recommended Countermeasure:
Verify whether this file is related to legitimate Microsoft diagnostics
Monitor the folder for further unusual file creations
Investigate the process that created the file if the activity continues
Consider adding tighter FIM rules on sensitive system directories
