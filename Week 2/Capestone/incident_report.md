# Incident Report – INC-2025-VSFTPD-001

## 1. Executive Summary

On 2025‑08‑18, a simulated attack exploited the vsftpd 2.3.4 backdoor on a Metasploitable2 server, resulting in unauthorized shell access. The attack was performed in a controlled lab environment to test detection and response capabilities. Wazuh successfully logged and surfaced suspicious FTP activity, and the target was contained without real data impact.

## 2. Scope

- Affected system: Metasploitable2 VM (FTP service).
- Affected users: None (lab‑only environment).
- Time window: 2025‑08‑18 11:00–12:00.
- Logs: FTP daemon logs, system logs, Wazuh alerts.

## 3. Timeline of Events

| Timestamp            | Event / Action                                          |
|----------------------|---------------------------------------------------------|
| 2025‑08‑18 11:00:00 | Attacker VM started and connectivity to target verified |
| 2025‑08‑18 11:10:00 | Metasploit module vsftpd_234_backdoor configured        |
| 2025‑08‑18 11:15:00 | Exploit executed; shell access obtained                 |
| 2025‑08‑18 11:20:00 | Wazuh logs showed anomalous FTP connection patterns     |
| 2025‑08‑18 11:30:00 | Attack flagged as a training exercise and contained     |
| 2025‑08‑18 11:45:00 | FTP service disabled and VM snapshot restored           |

## 4. Technical Details

- Service exploited: vsftpd 2.3.4 with known backdoor.
- Exploit used: Metasploit `exploit/unix/ftp/vsftpd_234_backdoor`.
- MITRE ATT&CK mapping:
  - Tactic: Initial Access
  - Technique: T1190 (Exploit Public‑Facing Application)
- Observations from logs:
  - Unusual connection pattern on FTP port from attacker IP.
  - Post‑exploitation commands visible in system logs/shell history (lab only).

## 5. Impact Analysis

- No production systems affected (lab only).
- No sensitive or business data at risk.
- Demonstrated that exploitation could lead to full shell access on a vulnerable service if found in production.

## 6. Containment

- FTP service on Metasploitable2 stopped after the test.
- Attacker IP blocked in host firewall rules for demonstration purposes.
- VM snapshot reverted to a clean state.

## 7. Eradication

- Vulnerable vsftpd version would be upgraded or disabled in a real environment.
- Any malicious processes or backdoors would be removed.
- Configuration hardening steps documented for reference.

## 8. Recovery

- Lab environment reset to pre‑attack condition.
- Monitoring rules tuned based on what was observed.
- No ongoing impact, as this was an isolated training exercise.

## 9. Lessons Learned

- Even “simple” services like FTP can be high‑risk when unpatched.
- SIEM visibility into service logs and network patterns is essential.
- Having clear runbooks for service isolation speeds up containment.

## 10. Recommendations

- Disable or upgrade legacy services like vsftpd 2.3.4 in any real environment.
- Create and maintain Wazuh rules for known exploit behaviors where possible.
- Regularly run vulnerability scans and correlate results with SIEM alerts.
