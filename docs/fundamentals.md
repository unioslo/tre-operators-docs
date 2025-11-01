

# TRE Fundamentals

## What is a TRE?

A **Trusted Research Environment (TRE)** is a secure digital workspace that provides researchers with controlled access to sensitive data (such as health, social, or administrative records) while ensuring strict safeguards around privacy, security, and compliance. TREs function like protected reference libraries, giving approved researchers a single, secure location for both data and analytical tools. For definitions of key terms, see the [Glossary](appendices/glossary.md).

## EOSC-ENTRUST and the Blueprint

EOSC-ENTRUST creates a European network of TREs for sensitive data and promotes interoperability. It uses a common blueprint for federated data access and analysis, based on lessons from the DARE UK Federated Architecture Blueprint and the Five Safes framework.

## Core Characteristics of TREs


- Data protection: Prevent data from being copied or removed. Allow researchers to access only the tools and views needed for analysis.
- Controlled access: Authenticate users and assign permissions so only approved researchers can enter.
- Secure compute: Perform analysis in a segregated, auditable environment (often virtual desktops or containers).
- Governed outputs: Check results before releasing them to ensure you do not compromise data subjects.
- Compliance: Follow legal and ethical frameworks such as GDPR, ISO 27001, or national research governance.

## Why TREs Matter

TREs balance research access with the need to protect sensitive data. They support reproducible, large-scale studies while maintaining privacy and trust. For more on federation and interoperability, see [Federation Integration](./federation.md).

## TRE Architecture Overview

Build TREs using core architectural components and controls:

![TRE Architecture](../images/tre_architecture_ops_docs.png)

### Diagram Legend

| Abbreviation      | Description                                                        |
|-------------------|--------------------------------------------------------------------|
| **AuthZ**         | Authorization service – enforces role- and attribute-based access   |
| **DLP**           | Data Loss Prevention engine – enforces data egress policies         |
| **DQ**            | Data Quality – validation and cleaning of incoming data             |
| **Egress**        | Controlled export of approved outputs after disclosure review       |
| **SIEM**          | Security Information and Event Management – aggregates logs/alerts  |
| **WSP**           | Workspace – secure compute environment (VMs, containers, VDI)      |