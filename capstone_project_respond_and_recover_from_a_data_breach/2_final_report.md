**Security Incident Report**

# \#####################  🔐 Security Incident Report -- Cymbal Retail

**📑 Table of Contents**

- Executive Summary

- Investigation

- Response and Remediation

  - Containment and Eradication Measures

  - Recovery Measures

- Recommendations

**🧾 Executive Summary**

Cymbal Retail, a global e-commerce and retail organization, experienced
a serious security incident involving the unauthorized access and
exfiltration of sensitive customer data, including credit card numbers,
usernames, and associated locations. The compromise originated from a
publicly exposed virtual machine (cc-app-01) that had SSH and RDP
services open and used a default service account with full API access.
The attacker exploited these vulnerabilities to gain initial access,
install malware, escalate privileges, and move laterally to access
BigQuery, where unencrypted customer data was stored.

To complete the exfiltration, the attacker leveraged a misconfigured
Cloud Storage bucket that had public internet access enabled. As a
Junior Cloud Security Analyst, I participated in the containment,
eradication, and recovery processes by identifying misconfigurations,
applying remediation actions across cloud resources, and improving
overall security posture through hardened access controls and
monitoring.

**🔎 Investigation**

A comprehensive investigation revealed the following findings:

1.  **Malware Infection** -- The VM cc-app-01 was compromised and
    infected with persistent malware.

2.  **Unauthorized Access** -- The attacker exploited publicly open SSH
    and RDP ports to perform brute-force login attacks using weak
    credentials.

3.  **Privilege Escalation** -- The attacker gained access to a
    user-managed service account key and escalated privileges to access
    additional services.

4.  **Access to BigQuery** -- Using compromised credentials, the
    attacker accessed sensitive, unencrypted data in BigQuery.

5.  **Data Exfiltration** -- The attacker used a publicly accessible
    Cloud Storage bucket to export the stolen data.

**🛠️ Response and Remediation**

**Containment and Eradication Measures**

- **Isolated compromised VM**: The infected VM (cc-app-01) was shut down
  and removed from the environment.

- **Restricted remote access**: SSH and RDP firewall rules were modified
  to limit access to internal IP ranges only.

- **Removed public bucket access**: The public access setting was
  disabled, and bucket-level IAM was enforced using uniform access
  control.

- **Disabled vulnerable service account**: The default service account
  was removed and replaced with one following the principle of least
  privilege.

- **Enabled firewall logging**: Firewall rules were updated to include
  logging for future auditing and visibility.

**Recovery Measures**

- **Provisioned a new secure VM**: A clean instance (cc-app-02) was
  created from a known-trusted snapshot, with secure boot enabled and no
  public IP address.

- **Reviewed and remediated cloud misconfigurations**: IAM roles,
  storage bucket policies, and firewall settings were audited and
  corrected.

- **Enabled monitoring and detection**: Security Command Center and
  Cloud Logging were configured to provide real-time visibility into
  system activity.

Google Cloud tools and services used during remediation:

- **Security Command Center** -- For vulnerability identification and
  findings analysis

- **Compute Engine** -- To manage and reconfigure VM instances

- **Cloud Storage** -- To apply access control to sensitive data

- **IAM** -- To adjust permissions and disable default service accounts

- **Firewall Rules** -- To restrict external access to critical ports

**🛡️ Recommendations**

1.  **Enforce the Principle of Least Privilege**\
    Avoid use of default service accounts with broad permissions. All
    users and services should have only the permissions required for
    their specific tasks.

2.  **Remove Public IPs and Harden Firewall Rules**\
    Publicly accessible VMs should be avoided unless necessary. All
    ingress traffic must be tightly controlled, and unused ports should
    be closed.

3.  **Enable Logging and Monitoring**\
    Logging must be activated on all services (VMs, Storage, Firewall).
    These logs should feed into Security Command Center for real-time
    threat detection.

4.  **Conduct Periodic Risk Assessments and Penetration Tests**\
    Regular audits and simulated attacks help identify misconfigurations
    and vulnerabilities before attackers do.

5.  **Require Multi-Factor Authentication (MFA)**\
    Enforce MFA for all accounts that have access to administrative
    tools, including service accounts where feasible.
