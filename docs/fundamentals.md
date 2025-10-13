# TRE Fundamentals

 **Trusted Research Environment (TRE)** is a secure digital workspace designed to provide researchers controlled access to sensitive data, typically health, social, or administrative records, while ensuring strict safeguards around privacy, security, and compliance.

## Core Characteristics
- **Data protection**: TREs prevent data from being copied or removed. Researchers access only the tools and views needed for analysis.  
- **Controlled access**: User authentication and role-based permissions ensure only approved researchers can enter.  
- **Secure compute**: Analysis is performed within a segregated, auditable environment (often virtual desktops or containers).  
- **Governed outputs**: Results are checked before leaving the environment to ensure they do not compromise data subjects.  
- **Compliance**: TREs align with legal and ethical frameworks such as GDPR, ISO 27001, or national research governance.  

## Why TREs Matter
TREs balance the **need for research access** with the **obligation to protect sensitive data**. They enable reproducible, large-scale studies while ensuring that privacy and trust are maintained.

## TRE Architecture

![TRE Architecture](../images/tre_architecture_ops_docs.png)

## Diagram Legend

| Abbreviation | Description |
|---------------|-------------|
| **DQ** | Data Quality – validation and cleaning of incoming data |
| **PHI** | Protected Health Information – identifiable health data |
| **IdP** | Identity Provider – federated authentication source (e.g., EduGAIN, eIDAS) |
| **AuthZ** | Authorization service – enforces role- and attribute-based access control |
| **WSP** | Workspace – secure compute environment (VMs, containers, VDI) |
| **DLP** | Data Loss Prevention engine – enforces data egress policies |
| **SIEM** | Security Information and Event Management – aggregates logs and alerts |
| **RBAC / ABAC** | Role-Based / Attribute-Based Access Control models |
| **ETL** | Extract, Transform, Load – data curation process |
| **NetIso** | Network Isolation – prevents external network access |
| **Egress** | Controlled export of approved outputs after disclosure review |