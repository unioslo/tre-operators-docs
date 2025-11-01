
# Interface Types: A Practical Guide

This guide explains how TREs in the federation exchange data securely and efficiently. You will learn how to package data, use the right interface type, and ensure compliance with federation requirements.

## How Data Moves Between TREs

TREs exchange Structured Data Objects using well-defined interface types. Route all traffic to and from interface services through the Security Servers of the host Participant to ensure security and traceability.

## Packaging Structured Data

Always package objects exchanged between Participants in a standard way:

- Use the **“Five Safes” RO-Crate standard** for all structured data objects.
- Tag each object with metadata that indicates the **Project context** for traceability.

## Choosing the Right Interface Type

Select the interface type that matches your data flow and security needs:

- **Query (Direct):**
    - Use this when your query is fully contained in the payload (e.g., SQL).
    - Exchange a Query Object.
    - Connect only to other Query (Direct) services.

- **Query (Indirect):**
    - Use this for queries that reference an external executable artifact (e.g., workflow URL).
    - Exchange a Job Request Object.
    - Connect only to other Query (Indirect) services.

- **Data Ingress/Egress:**
    - Use this to move complete sensitive datasets or large extracts between Participants.
    - Exchange a Data Extract Object.
    - Data Egress must connect only to Data Ingress services.

- **Index:**
    - Use this to exchange lists of personal or depersonalized identifiers and master linkage spines.
    - Exchange an Index Object.
    - Connect only to Index interface services.

- **Software:**
    - Use this to download approved software artifacts (environment or research) from a Software Service.
    - Exchange an Environment or Job Payload Artifact.
    - Connect only to Software interface services.

- **Response:**
    - Use this to encapsulate and send results or answers to queries.
    - Exchange a Response Object.
    - Connect only to other Response services.

## Federation Security and Compliance

To maintain security and compliance:

- Route all interface traffic through Security Servers.
- Encrypt all data exchanges between Participants.
- Tag all objects with project metadata for traceability.

By following these practices, you help ensure the integrity, confidentiality, and traceability of all data exchanged in the federation.

## Federated AAAI (Authentication, Authorization, and Auditing Infrastructure)

Federated AAAI provides a consistent, secure approach to identity and access across multiple TREs.

### EOSC AAAI Federation Requirements

EOSC Nodes, including TRE Providers, comply with Federation AAAI requirements.

*   **Architecture:** Operate an **AARC Blueprint compliant AAAI infrastructure** on each Node.
*   **Model:** Use a **"hub-and-spoke" model** in the EOSC AAAI Federation, with **MyAccessID** as the central hub providing the Trust & Identity Layers.
*   **Protocols:** Support **OpenID Connect (OIDC)** and **OAuth 2.0** protocols.
*   **Enrol:** Join the eduGAIN Federation as a Service Provider. Provide technical metadata (e.g., Redirect URIs, security endpoints) and confirm compliance with security requirements (e.g., Sirtfi) during registration.
*   **Authenticate:** Require a separate multi-factor authentication (MFA) step to access secure services.

### Identity and Collaboration

The AAAI system uses standardized identity claims to manage access based on collaborations and projects.

*   **Project Context:** Grant access through membership in a collaboration or project. Assign a globally recognizable and unique Project Identity.
*   **Attribute Exchange:** Use the AARC Blueprint Architecture (BPA) model to express a user’s membership in collaborations across administrative domains (AARC-G069), ensuring services can accurately determine user entitlement.
*   **Cross-Node Workflow:** Enable cross-node workflows by using the central hub (MyAccessID) to perform token introspection when a service in EOSC Node Y receives an Access Token issued by EOSC Node X.

### User Certification

The AAAI system supports the "Safe People" principle through certified identity.

*   **Researcher Passport:** Record training in the AAAI capability, ideally acting as a **‘Researcher Passport’** to enable interoperability across the network.
*   **Required Information:** Provide a web page listing all Collaborations/Projects supported by each Node, including their URN namespace, status, and jurisdiction.

## Cross-TRE Authorisation

This section describes the protocols for handling authorization decisions, especially for complex, fine-grained access across multiple TREs.

### Authorization Decision Principle

*   **Local Autonomy:** Each TRE retains **full control over the final authorization decision**.
*   **Authorization Context:** Use the **Project** concept to define the context (members, datasets, duration) necessary for the TRE to make an access decision.

### Policy and Attribute Exchange

Exchange authorization information via standard interfaces.

*   **Project-Based Control:** Exchange information for general access control (e.g., is the user a member of Project X?) via the **OIDC User Info endpoint** or **OAuth 2.0 Token Introspection endpoint**.
*   **Fine-Grained Control (REST APIs):** For detailed, context-sensitive authorization decisions:
    *   Transmit request attributes (subject, object, action, environment) in **JSON format** over **REST APIs**.
    *   Describe authorization policies using either **ODRL or REGO** language.
    *   Provide policy bundles as **.tar.gz archives**.

*   Policy Enforcement: Aggregate policies from multiple sources (AAAIs and registries) using the TRE’s Open Policy Agent (OPA) component before making the final authorization decision.

### Data Flow Security

Use authorization interfaces to exchange Structured Data Objects (Query Objects, Job Request Objects).

*   **Query Objects (Direct Queries):** Use these objects to contain the executable query. They typically do not contain sensitive data and are designated **“SDC green”**. Usually, you do not need output control before they leave their originating environment.
*   **Data Manager Roles:** Allow only system actors in **Data Manager** roles to invoke interface types that exchange sensitive metadata or data extracts.

## Secure Data Exchange and Auditing

This section lists the mandatory requirements for ensuring the confidentiality, integrity, and traceability of data exchanged between Federation Participants.

### Mandatory Encryption

Encrypt all network traffic between Federation Participants to maintain a secure and trustworthy foundation.

*   Data Exchange: Encrypt all data exchanged between Federation Participants. This applies to large transfers of Data Extract Objects (via Data Ingress/Egress).
*   Query Exchange: Encrypt all query exchanges (both direct and indirect) between Participants.
*   Index Exchange: Encrypt all index data exchanged between Participants.
*   Security Server Role: Route all traffic to and from interface services through the Security Servers of the host Participant.

### Auditing and Accounting Infrastructure

Use a standardized auditing system to maintain accountability and address auditing requirements (e.g., GDPR compliance).

*   **Centralized Service:** Implement a centralized **ELK stack** (Elasticsearch, Logstash, Kibana) for the accounting/auditing federation service. TREs MAY deploy their own local ELK stack.
*   **API Standard:** Use the **ELK compatible API** for all data submissions.
*   **Mandatory Data Submission:** Send accounting information from TRE and federation services to an ELK stack.
*   **Audit Model:** Use the prescribed accounting/auditing model for submitted information and make it available during the audit process to answer the basic questions: "who", "what", "when", "where".
