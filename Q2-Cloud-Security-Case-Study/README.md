# Q2 — Cloud Security Case Study: Snowflake Customer-Account Breaches

## Overview
This case study examines customer-account compromises involving Snowflake-hosted customer data environments publicly discussed in 2024. The report describes activity attributed by Mandiant to the threat cluster UNC5537. The key lesson is that provider platform security and customer identity, credential and data-access controls are related but distinct responsibilities.

Public reporting described attackers using stolen customer credentials to access customer instances. Do not describe this as a breach of Snowflake's own corporate enterprise environment unless a source directly supports that claim.

## Incident themes
- Stolen credentials, including credentials exposed through infostealer malware.
- Accounts without multi-factor authentication enabled.
- Previously stolen credentials that remained usable.
- The importance of trusted-network restrictions and monitoring unusual activity.
- Potential exposure of customer data when accounts have broad access.

Mandiant reported that multiple organisations could have been affected. Publicly reported organisations included Ticketmaster and Santander. Verify company-specific statements against their official disclosures and relevant regulatory filings.

## Shared responsibility
Cloud security is shared. The provider secures the underlying service and infrastructure; customers remain responsible for identity configuration, credential hygiene, access permissions, data governance and monitoring within their environments.

## Recommended controls
1. **Enforce MFA:** Require strong multi-factor authentication for user and administrative access wherever supported.
2. **Manage credentials:** Rotate exposed credentials, remove stale accounts and prevent reuse of compromised secrets.
3. **Apply least privilege:** Grant only the access needed for each role.
4. **Restrict and monitor access:** Use trusted-IP/network restrictions where appropriate and monitor logins, queries and exports for unusual behaviour.
5. **Prepare incident response:** Maintain a process for revocation, evidence preservation, impact assessment, notification and recovery.
6. **Strengthen data governance:** Classify sensitive data, limit unnecessary retention and review export permissions.

## Evaluation
The case demonstrates why organisations cannot rely only on a cloud provider's controls. Strong identity configuration, credential management, least privilege and monitoring are also needed at the customer level. Effective protection combines prevention, detection, incident response and data governance.

## Evidence and references
- Include the conceptual shared-responsibility diagram from the report if separate evidence is required.
- Ensure all in-text citations match the APA 7 reference list.
- Use sources that directly support incident-specific claims.

Sources to verify and cite:
- Mandiant reporting on UNC5537 and Snowflake customer instances: https://cloud.google.com/blog/topics/threat-intelligence/unc5537-snowflake-data-theft-extortion
- Snowflake security information: https://www.snowflake.com/en/security/
- For company-specific impact, cite the exact official company disclosures or regulatory filings consulted.

This README summarises the case-study scope; the final report should contain complete APA 7 references.
