# Incident Report – INC-2025-PHISH-001

## 1. Executive Summary

On 2025‑08‑18, a phishing email was sent to multiple HR team members, attempting to harvest credentials via a fake HR portal login page. The attack was detected through a user report and verified via email header analysis and URL reputation checks. No credentials were confirmed compromised.

## 2. Scope

- Affected users: 3 HR staff mailboxes.
- Affected systems: Email client and web browser on HR endpoints.
- Time window: 2025‑08‑18 13:45–16:00.
- Related alerts: One Wazuh rule triggered on suspicious URL domain.

## 3. Timeline of Events

| Timestamp            | Event / Action                                  |
|----------------------|-------------------------------------------------|
| 2025‑08‑18 13:45:00 | Phishing email received by HR distribution list |
| 2025‑08‑18 14:05:00 | User reported suspicious email to SOC           |
| 2025‑08‑18 14:15:00 | SOC isolated email (moved to quarantine)        |
| 2025‑08‑18 14:30:00 | URL analyzed; flagged as malicious              |
| 2025‑08‑18 15:00:00 | Email search performed; similar emails removed  |
| 2025‑08‑18 16:00:00 | Incident closed with no confirmed compromise    |

## 4. Technical Details

- Subject: “Urgent: HR Policy Update – Action Required”
- Sender: spoofed HR mailbox on external domain.
- Malicious URL: hxxps://hr-portal‑secure[.]example
- MITRE ATT&CK:
  - Tactic: Initial Access
  - Technique: T1566 (Phishing)
- Wazuh correlating alerts on HTTP requests to the malicious domain.

## 5. Impact Analysis

- No confirmed credential theft.
- Limited to small HR test group.
- Business impact: Low, due to early detection and user awareness.

## 6. Containment

- Quarantined all copies of the phishing email.
- Blocked the malicious domain at proxy/DNS layer.
- Notified targeted users and instructed them not to click links.

## 7. Eradication

- Verified no auto‑forwarding rules were created.
- Checked endpoints for any suspicious browser extensions or malware.
- No evidence of additional compromise found.

## 8. Recovery

- Email services unaffected.
- Monitoring of HR mailboxes increased for 48 hours.
- Wazuh rule updated to catch similar subject patterns.

## 9. Lessons Learned

- User awareness training was effective; user reported quickly.
- URL filtering could be further tightened.
- A standardized phishing triage checklist proved useful.

## 10. Recommendations

- Run a focused phishing awareness refresher for HR.
- Extend Wazuh correlation rules to flag repeated targeting from same domains.
- Integrate additional URL reputation feeds into proxy/SIEM.
