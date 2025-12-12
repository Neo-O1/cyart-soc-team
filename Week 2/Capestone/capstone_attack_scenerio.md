# Capstone Scenario – VSFTPD Exploit on Metasploitable2

## Overview

- **Attacker:** Kali or attacker VM
- **Target:** Metasploitable2 VM (vsftpd 2.3.4 service)
- **Tool:** Metasploit Framework
- **Objective:** Simulate exploitation of a vulnerable FTP service and practice detection, triage, response, and reporting.

## Steps (High Level)

1. Confirm Metasploitable2 is running and reachable from the attacker VM.
2. In Metasploit, use the `exploit/unix/ftp/vsftpd_234_backdoor` module.
3. Set RHOSTS to the Metasploitable2 IP and run the exploit.
4. Confirm you obtain a shell or some indication of successful exploitation.
5. Ensure your Wazuh agent/logging is capturing relevant logs from the target or from network logs.
6. Build detection logic in Wazuh/Kibana to spot this exploit attempt or suspicious FTP activity.
7. Perform triage, containment (e.g. stop service, block IP), and document the incident.
