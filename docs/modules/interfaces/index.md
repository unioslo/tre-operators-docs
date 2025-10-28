# Overview of Interface Types

Interoperability is achieved through the exchange of **Structured Data Objects** over a small number of defined **Interface Types**. Traffic to and from all interface services MUST route first through the Security Servers of the host Participant.

## Structured Data Packaging

The Federation requires that all objects exchanged between Participants **MUST** be packaged in a standard way.

*   **Recommended Standard:** The use of the **“Five Safes” RO-Crate standard** is suggested as the packaging format for all structured data objects.
*   **Traceability:** All structured data objects exchanged **SHOULD** be tagged with a metadata record indicating the **Project context**.

## Interface Types and Data Flow

Interface services are classified by type, defining their security context and permitted external connections.


### Interface Types

- **Query (Direct)**
    - *Function*: Supports queries where the executable query is fully contained in the payload (e.g., SQL).
    - *Data Object(s)*: Query Object.
    - *Connection Requirement*: MUST connect solely to other Query (Direct) services.

- **Query (Indirect)**
    - *Function*: Supports queries referring to an external executable artifact (e.g., workflow URL).
    - *Data Object(s)*: Job Request Object.
    - *Connection Requirement*: MUST connect solely to other Query (Indirect) services.

- **Data Ingress/Egress**
    - *Function*: Moves complete sensitive Datasets or large extracts between Participants.
    - *Data Object(s)*: Data Extract Object.
    - *Connection Requirement*: Data Egress MUST connect solely to Data Ingress services.

- **Index**
    - *Function*: Exchanges lists of personal/depersonalized identifiers and master linkage spines.
    - *Data Object(s)*: Index Object.
    - *Connection Requirement*: MUST connect solely to Index interface services.

- **Software**
    - *Function*: Downloads approved software artifacts (environment or research) from a Software Service.
    - *Data Object(s)*: Environment/Job Payload Artifact.
    - *Connection Requirement*: MUST connect solely to Software interface services.

- **Response**
    - *Function*: Encapsulates the results/answers to queries.
    - *Data Object(s)*: Response Object.
    - *Connection Requirement*: MUST connect solely to other Response services.

## Federated AAAI (Authentication, Authorization, and Auditing Infrastructure)

Federated AAI ensures a consistent, secure approach to identity and access across multiple TREs, addressing the Federation Readiness training gap.

### EOSC AAI Federation Requirements

EOSC Nodes, including TRE Providers, must comply with Federation AAI requirements.

*   **Architecture:** The Node must operate an **AARC Blueprint compliant AAI infrastructure**.
*   **Model:** The EOSC AAI Federation uses a **"hub-and-spoke" model**, with **MyAccessID** acting as the central hub providing the Trust & Identity Layers.
*   **Protocols:** Supported protocols include **OpenID Connect (OIDC)** and **OAuth 2.0**.
*   **Enrolment:** The Node **MUST** join the **eduGAIN Federation** as a Service Provider. Registration requires providing technical metadata (e.g., Redirect URIs, security endpoints) and confirming compliance with security requirements (e.g., Sirtfi).
*   **Authentication:** Access to secure services needs a separate **multi-factor authentication (MFA) step**.

### Identity and Collaboration

The AAI system relies on standardized identity claims to manage access based on collaborations and projects.

*   **Project Context:** Access is typically granted through membership in a collaboration or project. The **Project Identity** must be globally recognizable and unique.
*   **Attribute Exchange:** The AARC Blueprint Architecture (BPA) model supports the expression of a user’s membership in collaborations across administrative domains (AARC-G069), ensuring services can accurately determine user entitlement.
*   **Cross-Node Workflow:** The Federation enables cross-node workflows by using the central hub (MyAccessID) to perform token introspection when a service in EOSC Node Y receives an Access Token issued by EOSC Node X.

### User Certification

The AAI system should support the "Safe People" principle through certified identity.

*   **Researcher Passport:** Ideally, the AAAI capability should include the ability to record training, potentially acting as a **‘Researcher Passport’**, enabling interoperability across the network.
*   **Required Information:** Nodes **MUST** provide a web page listing all Collaborations/Projects they support, including their URN namespace, status, and jurisdiction.

## Cross-TRE Authorisation

This section details the protocols required for handling authorization decisions, especially for complex, fine-grained access across multiple TREs.

### Authorization Decision Principle

*   **Local Autonomy:** TREs **MUST** retain **full control over the final authorization decision**.
*   **Authorization Context:** Authorization relies heavily on the **Project** concept, which defines the context (members, datasets, duration) necessary for the TRE to make an access decision.

### Policy and Attribute Exchange

Information necessary for authorization is exchanged via standard interfaces.

*   **Project-Based Control:** Information for general access control (e.g., is the user a member of Project X?) is exchanged via the **OIDC User Info endpoint** or **OAuth 2.0 Token Introspection endpoint**.
*   **Fine-Grained Control (REST APIs):** For detailed, context-sensitive authorization decisions:
    *   Request attributes (subject, object, action, environment) **MUST** be transmitted in **JSON format** over **REST APIs**.
    *   Authorization policies **MUST** be described using either **ODRL or REGO** language.
    *   Policy bundles **MUST** be provided as **.tar.gz archives**.
*   **Policy Enforcement:** The TRE’s **Open Policy Agent (OPA) component** is responsible for aggregating policies from multiple sources (AAAIs and registries) before making the final authorization decision.

### Data Flow Security

Authorization interfaces support the exchange of Structured Data Objects (Query Objects, Job Request Objects).

*   **Query Objects (Direct Queries):** These objects contain the executable query and are not expected to contain sensitive data. They are designated **“SDC green”** and typically require no output control before leaving their originating environment (unless they encapsulate elements like partially trained neural networks).
*   **Data Manager Roles:** Interface types that exchange sensitive metadata or data extracts (Index, Data Ingress/Egress) **SHALL** only be invoked by system actors in **Data Manager** roles.

## Secure Data Exchange and Auditing

This section defines the mandatory requirements for ensuring the confidentiality, integrity, and traceability of data exchanged between Federation Participants.

### Mandatory Encryption

To maintain a secure and trustworthy foundation, encryption is mandatory for all network traffic between Federation Participants.

*   **Data Exchange:** All data exchange between Federation Participants **MUST** be encrypted. This applies to large transfers of Data Extract Objects (via Data Ingress/Egress).
*   **Query Exchange:** All query exchange (both direct and indirect) between Participants **MUST** be encrypted.
*   **Index Exchange:** All index data exchange between Participants **MUST** be encrypted.
*   **Security Server Role:** Traffic to and from all interface services **MUST** route through the **Security Servers** of the host Participant.

### Auditing and Accounting Infrastructure

A standardized auditing system is necessary to maintain accountability and address auditing requirements (e.g., GDPR compliance).

*   **Centralized Service:** A centralized **ELK stack** (Elasticsearch, Logstash, Kibana) implements the accounting/auditing federation service. TREs **MAY** deploy their own local ELK stack.
*   **API Standard:** The interface for all data submissions is the **ELK compatible API**.
*   **Mandatory Data Submission:** TRE and federation services **ARE REQUIRED** to send accounting information to an ELK stack.
*   **Audit Model:** The information submitted **MUST** use the prescribed accounting/auditing model and be available during the audit process to answer the basic questions: **“who”, “what”, “when”, “where”**.