# Module 3: Interfaces and Configuration: A Practical Guide

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

---

## Federated AAAI Overview

Federated AAAI provides a secure, consistent approach to identity, access, and auditing across multiple Trusted Research Environments (TREs).

---

## Core Federation Requirements

All EOSC Nodes, including TRE Providers, must:

* **Architecture:** Run an AAAI infrastructure compliant with the AARC Blueprint.
* **Federation Model:** Use a hub-and-spoke model with **MyAccessID** as the central hub for trust and identity services.
* **Protocols:** Support **OpenID Connect (OIDC)** and **OAuth 2.0**.
* **Federation Membership:** Join **eduGAIN** as a Service Provider, submit technical metadata, and meet security requirements.
* **Authentication:** Enforce multi-factor authentication (MFA) for access to secure services.

---

## Identity, Collaboration, and Claims

Access is based on collaboration and project membership.

* **Project Identity:** Assign a globally unique Project ID and grant access through membership in that project.
* **Attribute Exchange:** Use the AARC Blueprint model (AARC-G069) to express user roles and project membership across organisations so services can determine entitlement.
* **Cross-Node Use:** When a user presents an Access Token from Node X to a service in Node Y, Node Y uses MyAccessID for token introspection.
* **Researcher Certification:** Track user training and certification as a “Researcher Passport” to support the “Safe People” principle.
* **Transparency:** Publish a web page listing supported collaborations or projects, including URNs, status, and jurisdiction.

---

## Cross-TRE Authorisation

Each TRE keeps full control over its final authorisation decision.

### Authorisation Context

* Use the **Project** as the unit defining access scope: members, datasets, duration.
* Use OIDC UserInfo or OAuth 2.0 Token Introspection to answer general questions (e.g. “Is this user a member of Project X?”).

### Fine-Grained Authorisation

For detailed access rules:

* Exchange request attributes (subject, object, action, environment) using **JSON over REST APIs**.
* Define policies in **ODRL** or **REGO**.
* Provide policy bundles as **.tar.gz** archives.
* Each TRE aggregates policies from federation services and local sources using **Open Policy Agent (OPA)** before making a decision.

---

## Secure Data and Workflow Exchange

### Data Flow Security

* Use REST interfaces to exchange structured objects such as Query Objects or Job Request Objects.
* **Query Objects** contain executable queries, usually no sensitive data (SDC green), and may leave the originating environment without output control.
* Only **Data Manager** roles can invoke interfaces that expose sensitive metadata or data extracts.

---

## Encryption Requirements

Encrypt all traffic between Federation Participants:

* Data transfers (e.g. data extracts via ingress/egress)
* Query exchanges (direct and indirect)
* Index data
* All interface traffic must route through each Participant’s Security Server.

---

## Auditing and Accounting

Maintain traceability and compliance (e.g. GDPR).

* Use a central **ELK Stack** (Elasticsearch, Logstash, Kibana) as the federation’s auditing/accounting service. TREs may also run local ELK instances.
* Submit all accounting data through an **ELK-compatible API**.
* TREs and federation services must send audit logs to the central ELK stack.
* Use the standard audit model to answer “who,” “what,” “when,” and “where” during audits.

