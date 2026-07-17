# Incident Report 01 – Wazuh Home Lab

**Report Date:** 17 July 2026  
**Prepared by:** Abhiyan  
**Lab Environment:** Wazuh SIEM + Windows Agent  
**Report Type:** Security Incident Analysis  

---

## 1. Executive Summary

During monitoring of the Wazuh SIEM home lab, multiple security events were detected on the Windows-Workstation agent. The main events included repeated failed login attempts and File Integrity Monitoring (FIM) alerts related to file and registry changes. These events were analyzed and documented with recommended countermeasures.

---

## 2. Incident Details

### Incident 1: Multiple Failed Login Attempts

| Field                    | Details                                              |
|--------------------------|------------------------------------------------------|
| **Threat Category**      | Suspicious User Behaviour / Anomaly Detection        |
| **Detection Source**     | Wazuh SIEM – Windows-Workstation Agent               |
| **Alert Description**    | Logon failure - Unknown user or bad password         |
| **Rule ID**              | 60122                                                |
| **Severity**             | Medium                                               |
| **Timestamp**            | 17 July 2026                                         |

**Analysis:**  
Multiple failed login attempts were detected. This behaviour is consistent with a possible brute-force or password guessing attack.

**Potential Impact:**  
Unauthorized access to the system if the correct password is eventually guessed (Confidentiality risk).

**Recommended Countermeasures:**
- Enable account lockout policy after 5 failed attempts
- Monitor the affected account for further suspicious activity
- Notify the system owner
- Consider enabling multi-factor authentication (MFA) if possible

---

### Incident 2: File Integrity Monitoring Alert

| Field                    | Details                                              |
|--------------------------|------------------------------------------------------|
| **Threat Category**      | File Integrity Monitoring / Unauthorized Change      |
| **Detection Source**     | Wazuh SIEM – syscheck (FIM)                          |
| **Alert Description**    | File added to the system / Registry Integrity Change |
| **Rule ID**              | 554 / 750                                            |
| **Severity**             | Low – Medium                                         |
| **Timestamp**            | 17 July 2026                                         |

**Analysis:**  
Wazuh detected new file creation and registry value changes on the Windows endpoint. While some activity may be legitimate (Microsoft diagnostics), unauthorized changes in system locations can indicate malware or persistence techniques.

**Potential Impact:**  
Possible persistence mechanism or unauthorized system modification.

**Recommended Countermeasures:**
- Verify whether the changes are related to legitimate software
- Monitor the affected directories and registry keys
- Investigate the process that created the file if activity continues
- Strengthen FIM rules on critical system paths

---

## 3. Overall Recommendations

1. Implement account lockout policy on Windows endpoints.
2. Continue monitoring FIM alerts for unusual file and registry activity.
3. Document all findings and escalate according to incident response procedures.
4. Regularly review and tune Wazuh detection rules to reduce false positives.

---

## 4. Conclusion

The Wazuh SIEM successfully detected and alerted on suspicious login behaviour and file system changes. This exercise demonstrates practical skills in threat detection, alert analysis, and incident documentation — core responsibilities of a Cybersecurity Operator.

---

**End of Report**
