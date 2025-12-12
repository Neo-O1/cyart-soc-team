# Phishing Investigation Checklist

- [ ] Review email content and subject line.
- [ ] Inspect sender address and display name.
- [ ] Collect and analyze full email headers.
- [ ] Check embedded URLs using a safe reputation service.
- [ ] Inspect attachments in a safe environment, if present.
- [ ] Identify all recipients and affected users.
- [ ] Search mail system for similar messages.
- [ ] Check SIEM for HTTP/HTTPS requests to suspicious domains.
- [ ] Quarantine or delete malicious emails.
- [ ] Block malicious domains/IPs at proxy/DNS/firewall.
- [ ] Notify affected users and provide guidance.
- [ ] Document the incident (timeline, impact, IOCs, actions taken).
- [ ] Update rules/playbooks if needed.
