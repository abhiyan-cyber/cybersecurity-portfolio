# Wazuh SOC Home Lab

This project simulates a basic Security Operations Center (SOC) using Wazuh SIEM.

## Lab Overview
- **Wazuh Manager**: Ubuntu Server
- **Endpoint**: Windows 11 (Agent installed)
- **Network**: Bridged Adapter

## What Was Implemented
- Agent deployment and monitoring
- Detection of failed login attempts
- File Integrity Monitoring (FIM)
- Registry change detection
- Incident analysis and documentation

## Folder Structure
- `Screenshots/` → Evidence of alerts and dashboard
- `Incident-Notes.md` → Short analysis of individual alerts
- `Incident-Reports/` → Formal incident reports

## Key Alerts Detected
- Multiple failed login attempts (possible brute force)
- File added to the system
- Registry integrity checksum changes
