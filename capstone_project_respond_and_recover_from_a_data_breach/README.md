# 🧩 Capstone Project: Respond and Recover from a Data Breach

This capstone project marks the culmination of the Google Cloud Cybersecurity Certificate program. It simulates a real-world incident response scenario involving a major data breach at Cymbal Retail, a global retail company operating across 28 countries.

As a Junior Cloud Security Analyst at Cymbal Retail, I was responsible for helping the security team investigate, contain, and recover from the breach. This hands-on project integrates all the key cloud security concepts covered in the certification, including threat detection, system recovery, compliance verification, and final documentation.

---

## 🧠 Scenario Summary

Cymbal Retail experienced a serious data breach that compromised sensitive customer information. As part of the incident response team, I was assigned to:

- Investigate and identify vulnerabilities associated with the breach.
- Contain and eradicate the threat.
- Restore compromised systems using secure backups.
- Remediate compliance violations.
- Verify compliance with cloud security standards.
- Document the incident in a final report.

---

## 🧪 Tasks Completed

1. **Analyze the data breach and gather information**
   - Reviewed security findings using Google Cloud Security Command Center.
   - Identified attack vectors, exploited services, and privilege escalation path.

2. **Fix Compute Engine vulnerabilities**
   - Shut down the compromised VM (`cc-app-01`).
   - Deployed a hardened VM (`cc-app-02`) from a trusted snapshot.
   - Removed public IP and enabled secure boot.

3. **Fix Cloud Storage bucket permissions**
   - Disabled public access to affected buckets.
   - Applied uniform bucket-level access control (UBLA).

4. **Limit firewall port access**
   - Modified firewall rules to restrict SSH and RDP ports (22 and 3389) to internal IP ranges.
   - Enabled firewall logging for monitoring.

5. **Fix the firewall configuration**
   - Removed open ingress rules from all external sources.
   - Enforced least privilege and audited rule scopes.

6. **Verify compliance**
   - Rechecked Security Command Center for open findings.
   - Validated that remediations closed identified vulnerabilities.

7. **Create the final report**
   - Documented the incident timeline, technical findings, remediation steps, and post-incident recommendations.
   - Report serves as a complete record of the breach and response lifecycle.

---

## 🔧 Tools & Technologies Used

- Google Cloud Platform (GCP)
- Google Cloud Security Command Center
- Compute Engine
- Identity and Access Management (IAM)
- Cloud Storage
- Cloud Firewall Rules
- GCP Compliance Reports

---

## 📁 Project Deliverables

- Remediation tasks (screenshots, notes, configuration)
- Final incident report (`security_incident_report.md`)
- Summary documentation and recommendations

---

## ✅ Key Learning Outcomes

- Performed end-to-end cloud incident response in a simulated enterprise environment.
- Applied Google Cloud tools to contain and recover from a data breach.
- Reinforced principles such as least privilege, infrastructure hardening, and cloud compliance.
- Developed a portfolio-ready project that demonstrates real-world cloud security experience.
