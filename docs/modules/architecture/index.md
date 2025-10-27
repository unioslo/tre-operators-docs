**Trusted Research Environment (TRE)**<sup>[[Glossary](appendices/glossary.md#tre-operator)]</sup> is a secure digital workspace designed to provide researchers controlled access to sensitive data, such as health, social, or administrative records, while ensuring strict safeguards around privacy, security, and compliance. By making data available through a TRE, personal information can be accessed safely, ensuring individuals’ privacy is protected. TREs give approved researchers a single, secure location where both data and analytical tools are available, functioning much like a protected reference library. For definitions of key terms, see the [Glossary](appendices/glossary.md).

## Zones
A TRE is modelled using three functional zones; not every TRE needs to support all three.

| Zone | Function | Key Requirements |
| :--- | :--- | :--- |
| **Research Analytics Zone (RAZ)** | Provides the Project Environments where a Project Member gains direct access to approved data for analysis. | RAZ **MUST** have one or more Project Environments. RAZ is comparable to the EHDS **Secure Processing Environment (SPE)**. The PI acts as the **Output Approver** for the RAZ Project environment. |
| **Secure Data Zone (SDZ)** | Supports data management, ingress, egress, linkage, curation, and provision of research-ready sensitive datasets. | An SDZ **MUST** have a **Data Management function**. Data movements to or from the SDZ **MUST** pass through this function. |
| **Query Management Zone (QMZ)** | Handles remote queries (direct or indirect) sent from other federated TREs or Job Submission Services. | QMZ supports federated analytics. A QMZ that supports indirect queries **MUST** include a **Job Controller component** and a **Job Approval process**. |

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

## Generalized AAA Architecture in a TRE

This section presents a **generalized architecture for Authentication, Authorization, and Auditing (AAA)** integration within a Trusted Research Environment (TRE).  
It is derived from the design principles and implementation experience of the **Services for Sensitive Data (TSD)**.

### Architectural Overview

![Generalized AAA Integration Architecture](../../images/aaai_architecture.png)

*Figure: Conceptual model showing how authentication, authorization, and auditing components interact within a TRE.*

### Authentication

The authentication subsystem consists of several coordinated components. At its foundation, the central Identity and Access Management (IAM) system governs all user, project, and group identities, while also providing APIs for authentication, authorization, and resource management. Authentication operations are facilitated by an OpenID Connect (OIDC) provider, which implements standards-based authentication flows—including PKCE for browser clients—and integrates with external identity providers to support multi-institutional access. Federated authentication enables users to log in through trusted third-party providers, simplifying account creation and management processes. The environment enforces multi-factor authentication (MFA), such as time-based (TOTP) or HMAC-based (HOTP) one-time passcodes, which users can manage via self-service portal. Token exchange mechanisms support the issuance of narrowly scoped, short-lived API access tokens. For non-interactive or time-limited workflows, client and instance-based authentication—including “magic links”—enables automated or temporary access, with optional password protection for added security.

### Authorization

Authorization is centrally managed by a policy enforcement engine, which serves as the Policy Enforcement Point (PEP) for all API requests entering the environment through designated gateways. This engine evaluates each request against access control policies (grants) maintained within the IAM database. These policies may be static—maintained as code or configuration under version control—or dynamically managed via programmable interfaces provided by the IAM API. All access tokens and authorization grants are strictly scoped to specific projects or tenants and to designated API gateways. Network and resource-level isolation is maintained through private VLANs and firewall policies. The authorization workflow includes validating the token’s integrity and claims, matching access policy grants to requested API operations and contextual attributes, and enforcing any additional restrictions such as time windows or usage limits.

### Auditing

Auditing is implemented across all relevant system layers to support accountability, regulatory compliance, and operational monitoring. Every API operation—spanning file, data, and resource actions—is logged in detail, with audit logs accessible for both operational staff and authorized project administrators. Changes to IAM data and resource allocations are tracked, capturing all create, update, and delete events. All storage and file access operations are monitored for data integrity and incident response purposes. Exports of data and downloads from publication interfaces are recorded to maintain a verifiable trail of data egress. Finally, system event and operations logs are aggregated and made available for ongoing monitoring, security investigations, and incident response.

### Key Architectural Components and Integration Points

The environment employs multiple API gateways (external, internal, and restricted) to route all API traffic, enforce TLS, and delegate authentication and authorization to centralized control points. A message broker enables event-driven service integrations, publishing relevant events to subscribed internal and external consumers. Microservices synchronize user, group, and project information from the IAM system to external directories as needed. Core research, compute, storage, and notification APIs all integrate directly with the central IAM for authentication and authorization. Web-based self-service and administrative portals, as well as data collection services, interact with the AAA infrastructure for secure, auditable operations. Project-level network isolation is enforced via software-defined firewalls and VLAN segmentation, dynamically configured based on IAM and directory data. Staff operational access is tightly regulated by IAM-based role assignment, group membership, multi-factor authentication, and the use of bastion hosts; all privileged actions are auditable.
