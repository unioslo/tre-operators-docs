
# TRE Fundamentals

**Trusted Research Environment (TRE)**<sup>[[see Glossary](appendices/glossary.md#tre-operator)]</sup> is a secure digital workspace designed to provide researchers controlled access to sensitive data, typically health, social, or administrative records, while ensuring strict safeguards around privacy, security, and compliance. For definitions of key terms, see the [Glossary](appendices/glossary.md).


## Core Characteristics
- **Data protection**: TREs prevent data from being copied or removed. Researchers access only the tools and views needed for analysis.  
- **Controlled access**: User authentication and role-based permissions ensure only approved researchers can enter.  
- **Secure compute**: Analysis is performed within a segregated, auditable environment (often virtual desktops or containers).  
- **Governed outputs**: Results are checked before leaving the environment to ensure they do not compromise data subjects.  
- **Compliance**: TREs align with legal and ethical frameworks such as GDPR, ISO 27001, or national research governance. See [Compliance & Certification](../compliance.md).


## Why TREs Matter
TREs balance the **need for research access** with the **obligation to protect sensitive data**. They enable reproducible, large-scale studies while ensuring that privacy and trust are maintained. For more on federation and interoperability, see [Federation Integration](../federation.md).


## TRE Architecture

![TRE Architecture](../images/tre_architecture_ops_docs.png)

For a detailed overview, see [Reference Architecture](appendices/reference-architecture.md).

## Diagram Legend

For definitions of abbreviations, see the [Glossary](appendices/glossary.md).

| Abbreviation | Description |
|---------------|-------------|
| **AuthZ** | Authorization service – enforces role- and attribute-based access control |
| **DLP** | Data Loss Prevention engine – enforces data egress policies |
| **DQ** | Data Quality – validation and cleaning of incoming data |
| **Egress** | Controlled export of approved outputs after disclosure review |
| **ETL** | Extract, Transform, Load – data curation process |
| **IdP** | Identity Provider – federated authentication source (e.g., EduGAIN, eIDAS) |
| **NetIso** | Network Isolation – prevents external network access |
| **PHI** | Protected Health Information – identifiable health data |
| **RBAC / ABAC** | Role-Based / Attribute-Based Access Control models |
| **SIEM** | Security Information and Event Management – aggregates logs and alerts |
| **WSP** | Workspace – secure compute environment (VMs, containers, VDI) |

For configuration examples, see [Config Examples](appendices/config-examples.md). For further reading, see [Resources](appendices/resources.md).