# cloud-grc-portfolio# AWS Cloud & GRC Portfolio Deployment
**Architect:** Fatima Nasir Muhammad  
**Stack:** AWS S3, CloudFront, Route 53, ACM, NIST 800-53 Framework

## 🚀 Overview
This project is a high-performance, secure personal portfolio hosted on AWS. Unlike a standard deployment, this project was built with a **Security-First** mindset, mapping every technical decision to GRC (Governance, Risk, and Compliance) principles and NIST 800-53 controls.

## 🏗️ Architecture


- **Storage:** Amazon S3 (Private Bucket)
- **CDN:** Amazon CloudFront (Global Edge Locations)
- **Security:** Origin Access Control (OAC), HTTPS/TLS 1.2+
- **Governance:** Custom Cloud Security Policy (SEC-POL-001)

## ⚖️ GRC Decisions & NIST Mapping
| Feature | Architectural Decision | NIST 800-53 Control |
| :--- | :--- | :--- |
| **Data Privacy** | S3 Public Access is blocked; OAC is used for CloudFront access. | **AC-3** (Access Enforcement) |
| **Data in Transit** | Forced HTTPS redirection via CloudFront. | **SC-8** (Transmission Confidentiality) |
| **Least Privilege** | Deployment managed via IAM user with limited S3/CloudFront scopes. | **AC-6** (Least Privilege) |
| **Integrity** | Versioning enabled on S3 to prevent accidental deletion. | **SI-7** (Software/Info Integrity) |

## 🛠️ Security Policy
A formal **Cloud Security Policy** was authored for this environment, establishing requirements for data classification, incident response, and MFA enforcement.

## 📈 Technical Implementation Notes
1. **S3 Private Origin:** The bucket is not public. Access is granted only to the CloudFront distribution via a specific Bucket Policy.
2. **CloudFront OAC:** Replaced the legacy OAI (Origin Access Identity) to support modern security protocols and regional S3 signatures.
3. **Optimized Delivery:** Configured a Default Root Object to ensure seamless navigation without directory listing vulnerabilities.

---
© 2026 Fatima Nasir Muhammad | Cloud Engineering & GRC Compliance
