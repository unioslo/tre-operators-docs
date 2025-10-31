

# TRE Fundamentals

## What is a TRE?

A **Trusted Research Environment (TRE)** is a secure digital workspace that provides researchers with controlled access to sensitive data (such as health, social, or administrative records) while ensuring strict safeguards around privacy, security, and compliance. TREs function like protected reference libraries, giving approved researchers a single, secure location for both data and analytical tools. For definitions of key terms, see the [Glossary](appendices/glossary.md).

A Trusted Research Environment (TRE) is a secure digital workspace. It gives researchers controlled access to sensitive data, such as health, social, or administrative records, and protects privacy, security, and compliance. TREs work like protected reference libraries, providing approved researchers a single, secure location for data and analytical tools. For definitions of key terms, see the [Glossary](appendices/glossary.md).

## EOSC-ENTRUST and the Blueprint

[**EOSC-ENTRUST**](https://eosc-entrust.eu/) aims to create a European network of TREs for sensitive data and drive interoperability between them. This is achieved through a common blueprint for federated data access and analysis—the [**EOSC-ENTRUST Blueprint & Interoperability Framework**](https://eosc.eu/roadmap/blueprint-architecture-for-trusted-research-environments-tres/). The blueprint incorporates lessons from the [**DARE UK Federated Architecture Blueprint**](https://dareuk.org.uk/how-we-work/federated-architecture-blueprint/), which uses the [Five Safes](appendices/glossary.md#five-safes) framework and data space design thinking.

EOSC-ENTRUST creates a European network of TREs for sensitive data and promotes interoperability. It uses a common blueprint for federated data access and analysis, based on lessons from the DARE UK Federated Architecture Blueprint and the Five Safes framework.

## Core Characteristics of TREs


- Data protection: Prevent data from being copied or removed. Allow researchers to access only the tools and views needed for analysis.
- Controlled access: Authenticate users and assign permissions so only approved researchers can enter.
- Secure compute: Perform analysis in a segregated, auditable environment (often virtual desktops or containers).
- Governed outputs: Check results before releasing them to ensure you do not compromise data subjects.
- Compliance: Follow legal and ethical frameworks such as GDPR, ISO 27001, or national research governance.

## Why TREs Matter

TREs balance the need for research access with the obligation to protect sensitive data. They enable reproducible, large-scale studies while maintaining privacy and trust. For more on federation and interoperability, see [Federation Integration](./federation.md).

TREs balance research access with the need to protect sensitive data. They support reproducible, large-scale studies while maintaining privacy and trust. For more on federation and interoperability, see [Federation Integration](./federation.md).

## TRE Architecture Overview

TREs are built on a set of core architectural components and controls:

Build TREs using core architectural components and controls:

![TRE Architecture](../images/tre_architecture_ops_docs.png)

For a detailed overview, see [Reference Architecture](appendices/reference-architecture.md).

For a detailed overview, see [Reference Architecture](appendices/reference-architecture.md).

### Diagram Legend

For definitions of abbreviations, see the [Glossary](appendices/glossary.md).

| Abbreviation      | Description                                                        |
|-------------------|--------------------------------------------------------------------|
| **AuthZ**         | Authorization service – enforces role- and attribute-based access   |
| **DLP**           | Data Loss Prevention engine – enforces data egress policies         |
| **DQ**            | Data Quality – validation and cleaning of incoming data             |
| **Egress**        | Controlled export of approved outputs after disclosure review       |
| **ETL**           | Extract, Transform, Load – data curation process                   |
| **IdP**           | Identity Provider – federated authentication source                |
| **NetIso**        | Network Isolation – prevents external network access               |
| **PHI**           | Protected Health Information – identifiable health data            |
| **RBAC / ABAC**   | Role-Based / Attribute-Based Access Control models                 |
| **SIEM**          | Security Information and Event Management – aggregates logs/alerts  |
| **WSP**           | Workspace – secure compute environment (VMs, containers, VDI)      |

For configuration examples, see [Config Examples](appendices/config-examples.md). For further reading, see [Resources](appendices/resources.md).

