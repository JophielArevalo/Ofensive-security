# Active Directory Penetration Test – Full Domain Compromise

## Objectives
- Discover domain structure, weak credentials, and misconfigurations.
- Escalate privileges via attack path analysis and ACL abuse.
- Achieve domain administrator access and validate with flags.

## Steps (High-Level)
1. **Recon** – `ldapsearch` naming contexts; dump users.
2. **AS‑REP Roasting** – Identify no‑preauth users; extract hashes.
3. **Cracking** – John the Ripper (weak passwords).
4. **Domain Dump** – `ldapdomaindump` for users/groups/ACLs.
5. **BloodHound** – Upload data, find DCSync principals and shortest path.
6. **GenericAll Chain** – Password resets across chained users; gain target.
7. **Privilege Escalation** – Add compromised user to DCSync group.
8. **DCSync** – `secretsdump` to extract NTLM for Administrator.
9. **Final Access** – Evil‑WinRM with hash (pass‑the‑hash); capture flags.

## Evidence
- `ldap-enum.txt`, `kerberoast-hashes.txt`, `dcsync.txt`
- `bloodhound-analysis/` screenshots or notes
- `report.pdf` (full write‑up)

## Skills
AD recon · Kerberos attacks · Password cracking · ACL abuse · DCSync · Lateral movement
