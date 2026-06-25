# Brute Force Detection

## Overview

This project demonstrates the detection of repeated failed authentication attempts using Splunk and Windows Security Logs.

The objective was to simulate suspicious insider activity and identify accounts exhibiting multiple failed login attempts.

---

## Scenario

A test user account was used to generate multiple failed login attempts on a Windows system.

Windows Security Event Logs were forwarded to Splunk for monitoring and analysis.

---

## Detection Logic

### Event ID

4625 - Failed Logon

### Detection Threshold

More than 5 failed login attempts from the same account.

### Splunk Query

```spl
index=* source="WinEventLog:Security" EventCode=4625
```

---

## Results

The simulated account generated six failed authentication attempts.

The detection rule successfully identified the activity and flagged the account for investigation.

---

## MITRE ATT&CK Mapping

Technique: T1110 - Brute Force

---

## Skills Demonstrated

* Splunk
* Windows Event Logs
* Security Monitoring
* Detection Engineering
* Threat Detection
* Log Analysis

---

## Screenshot

![Detection Results](screenshots/detection-results.png)

---

## Lessons Learned

Repeated Event ID 4625 activity may indicate brute-force attacks, password spraying attempts, or unauthorized access attempts.

Monitoring authentication failures is an important component of Security Operations Center (SOC) monitoring.
