# Alert Priority – Concepts and Lab Mapping

## 1. Severity vs Priority

- **Severity** describes how bad the impact is:
  - Critical: Ransomware encryption on production, mass data exfiltration.
  - High: Unauthorized admin access, lateral movement on key servers.
  - Medium: Repeated failed logins, malware on a non‑critical workstation.
  - Low: Port scans, policy violations on a test VM.

- **Priority** describes how fast the SOC should respond:
  - P1 (Immediate): Active compromise on critical systems.
  - P2: Serious issue but not yet business‑stopping.
  - P3/P4: Routine or informational issues.

In the lab, severity and priority are usually aligned (Critical → P1), but can differ based on asset criticality.

## 2. CVSS and Alert Mapping

- CVSS base scores:
  - 9.0–10.0 → Critical
  - 7.0–8.9 → High
  - 4.0–6.9 → Medium
  - 0.1–3.9 → Low

- Example mappings:
  - Log4Shell (CVE‑2021‑44228) – CVSS 9.8 → Critical alert if seen on internet‑facing or production systems.
  - A local privilege escalation on a lab VM – CVSS 7.5 → High severity but maybe Medium priority in a training lab.

In your sheet, you combine:
- CVSS score
- Asset type (Production / Internal / Test)
- Exposure (Internet‑facing? Privileged account?)
To decide the final alert priority.

## 3. Lab Examples

Some example alerts and how they are prioritized in this project:

- **[Critical] Log4Shell Exploit Detected on Web‑Server‑1**
  - CVSS: 9.8
  - Asset: Internet‑facing production web server
  - Priority: Critical / P1

- **[High] Unauthorized Admin Login on WIN‑SERVER‑DB**
  - CVSS (underlying vuln): 8.2
  - Asset: Production database server
  - Priority: High / P1–P2

- **[Medium] Brute‑force SSH Attempts on Test‑Linux‑VM**
  - No direct CVE; behavior‑based.
  - Asset: Internal test VM
  - Priority: Medium / P3

- **[Low] Port Scan from Internal Security Scanner**
  - Asset: Test target
  - Context: Known scanner IP
  - Priority: Low / P4 (likely informational or accepted activity)
