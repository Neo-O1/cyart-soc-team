# Incident Classification – Notes

## 1. High-Level Categories

Common incident categories used in this project:

- Phishing
- Malware / Ransomware
- Brute-force / Authentication attacks
- Web application exploit
- Data exfiltration
- Insider misuse
- Reconnaissance / Port scanning

These map to ENISA and VERIS‑style classifications.

## 2. MITRE ATT&CK Mapping

Examples used in this week:

- Phishing → Initial Access / T1566
- Brute-force SSH → Credential Access / T1110
- Exploit VSFTPD backdoor on Metasploitable2 → Initial Access / T1190
- Data exfiltration over HTTP → Exfiltration / T1041

Each alert/incident gets:
- A tactic (Initial Access, Credential Access, etc.)
- A technique ID (e.g. T1566, T1110, T1190)

## 3. ENISA / VERIS Flavor

For practice, you also think in terms of:

- **ENISA type** (e.g., Malware, Intrusion, Availability, Information Leak).
- **VERIS “4 A’s”**:
  - Actor (External attacker, Insider)
  - Action (Hacking, Malware, Social, Misuse)
  - Asset (Server, Endpoint, Application, Data)
  - Attribute (Confidentiality, Integrity, Availability affected)

This gives you a standard way to tag incidents so later dashboards and reports are consistent.
