# cloudsecurity
Repository contains necessary artifacts for Cloud Security Use cases.
# Simulation of Cloud Security Audit against based on ISO/IEC 27017 and ISO/IEC 27001 standards:

# Step 1: Define Cloud Resources to Create

Here are some resources I have created in a Azure cloud environment that are intentionally misconfigured for audit purposes:

___________________________________________________________________________________________
Resource |	Misconfiguration |	Risk
------------------------------------------------------------------------------------------
|Blob Storage (Azure)	| Public read/write access	| Data leakage |
|Virtual Machine |	Open SSH/RDP to the world (0.0.0.0/0) | Unauthorized access |
|IAM Role / Service Principal | Overly permissive policies (e.g., *:*) |	Privilege escalation |
|Database (RDS / SQL)|	No encryption at rest or in transit	| Data breach|
|Storage Account |	No logging or versioning enabled	|Lack of audit trail|
|Web App / API	| No authentication or rate limiting |	Abuse or DoS |
|Key Vault / Secrets Manager |	Secrets stored in plaintext or exposed |	Credential theft|

# Step 2: Simulate Resource Creation

Blob Storage

Name: public-blob-storage
Misconfig: Public access enabled, no encryption

virtual machine

Open ports: 22 (SSH), 3389 (RDP) to 0.0.0.0/0
No security group restrictions

IAM Role
Policy: Administrator Access attached to a service account

DB Instance
No encryption
Publicly accessible

Secrets in Azure Key Vault
Store AWS keys in a script file on the virtual machine

# Step 3: Prepare for the Audit
Once these resources are created, enable Microsoft Defender for Cloud i.e Cloud Security Posture Management (CSPM) tool.

Go to Environment Setting and Select Standard **ISO/IEC 27017 2015** & Enable It.




Map findings to ISO/IEC 27001 Annex A and ISO/IEC 27017 controls
