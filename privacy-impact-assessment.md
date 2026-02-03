# 🔒 Compliance & Privacy Impact Assessment (PIA)

Ensuring data integrity and security across the **7-Tier Hierarchy**.

### 🕵️ Data Sensitivity Scan
* **PII Data:** Does the system store names, emails, or IDs? (YES/NO)
* **Encryption:** Are AWS S3 buckets and Azure Blobs encrypted at rest? (YES/NO)
* **Access Control:** Is RBAC (Role-Based Access Control) enforced? (YES/NO)

### 🛡️ Compliance Gate
| Requirement | Status | Evidence |
|:--- |:--- |:--- |
| GDPR Art. 32 | Compliant | AES-256 Encryption active |
| Data Retention | Compliant | Lifecycle policy moves data to Glacier after 12 mo |
| Audit Logs | Compliant | CloudTrail / Azure Monitor logs active |
