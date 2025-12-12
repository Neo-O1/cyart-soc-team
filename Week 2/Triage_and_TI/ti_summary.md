# Threat Intelligence Summary Examples

## 1. Brute-force SSH Attempts (Alert 002)

The source IP 192.168.1.100 was checked against AlienVault OTX and VirusTotal. No malicious reputation or known campaigns were associated with this address, and it belongs to an internal lab subnet. Combined with context (test attack), this strongly suggests a benign, lab‑generated brute‑force scenario.

## 2. Possible Malware File (Alert 003)

The file hash submitted to VirusTotal was associated with multiple antivirus detections and labelled as a common info‑stealing Trojan. Based on this, the alert priority remained High, and remediation steps included isolating the endpoint, removing the file, scanning the system, and resetting potentially exposed credentials.

## 3. Suspicious Outbound Connection (Alert 005)

The destination IP was found in AlienVault OTX as a known command‑and‑control server used in botnet activity. This external confirmation elevated the confidence in malicious activity. Immediate containment actions were justified: isolating the host, blocking the IP at the firewall, and starting a deeper forensic investigation.
