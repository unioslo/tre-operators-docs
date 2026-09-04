# Reference Terminology Dictionary for Secure Research Environments
*A practical guide to related terms used in the European Health Data Space (EHDS/TEHDAS2) and United Kingdom Trusted Research Environment (UK TRE/SATRE/DARE UK) frameworks.*

## Scope and Status
This dictionary compares terms from different frameworks. It is not legal advice, a certification scheme, or a standard. Similar terms may still have different legal meanings, controls, or technical scope. The relevant law, regulator guidance, access decision, and local procedures always take priority.

The mappings use these categories:

- **Direct legal match:** the terms have roughly the same legal meaning.
- **Functional correspondence:** the terms serve a similar purpose but have different legal or governance contexts.
- **Operational analogy:** the comparison may help with implementation, but it is not a formal match.
- **Project-specific proposal:** a suggested design that needs local approval.

References should include the document title, version or publication date, section or article, and a stable URL where possible. File names in square brackets are placeholders. Replace them with full references before using this document as a formal specification.

## The 5-Stage Terminology Pipeline
The terms in this dictionary follow five common stages of a research project. This is a guide, not a claim that every system uses the same workflow or zones.

1. **Data Discovery:** Researchers use data catalogues and standard metadata, such as DCAT-AP, to find relevant datasets and their custodians. Finding a dataset does not grant access.
2. **Access Approval:** Researchers submit access requests and receive the relevant legal or administrative decision. The decision may be represented by a machine-readable permit such as DAAMS.
3. **Data Preparation:** Data holders prepare the datasets for the approved project. This may include pseudonymisation, linkage, and de-identification.
4. **Use of Data:** Researchers work in an isolated project workspace inside a Secure Processing Environment (SPE) or Trusted Research Environment (TRE). They may use federated computing where it is available.
5. **Finalisation:** Proposed outputs go through Statistical Disclosure Control (SDC) or another output review. They may be released only when the project rules, legal requirements, and security controls allow it. The project environment is then archived.

| Lifecycle stage | EHDS-oriented term | UK TRE-oriented term | Relationship | Main caveat |
|---|---|---|---|---|
| Data discovery | Dataset catalogue | Catalogue or search service | Functional correspondence | Metadata visibility does not imply access |
| Access approval | Data Permit / Access Permit | Approval and authorisation workflow | Functional correspondence | Legal authority and decision paths differ |
| Data preparation | SPE preparation services | SDZ / ingestion and curation | Functional correspondence | Zone boundaries vary by implementation |
| Data use | SPE project workspace | RAZ | Narrower functional mapping | A RAZ is not the whole TRE |
| Finalisation | Output control / SDC | Disclosure control / release review | Functional correspondence | Release criteria are governance-specific |

## 1. Architectural & Environmental Mappings

### Secure Processing Environment (SPE) / Trusted Research Environment (TRE)
*   **Mapping type:** Functional correspondence.
*   **Meaning:** An EHDS Secure Processing Environment and a UK Trusted Research Environment are both secure settings, but they are based on different laws, governance models, and technical designs. A UK Research Analytics Zone is closer to the project workspace inside an SPE or TRE. It is not the same as the whole environment.
*   **Authoritative References:**
    *   **EU Data Governance Act (DGA) & EHDS:** [DGA Article 2(20)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022R0868) and [EHDS Article 73](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327) define an SPE as a secure physical or virtual environment under the control of a public authority or designated operator.
    *   **UK TRE Framework & SATRE:** The [UK TRE Glossary](https://glossary.uktre.org/en/latest/) and [SATRE Specification v1.0.0](https://satre-specification.readthedocs.io/en/v1.0.0/) define a TRE as a secure environment wrapped in information governance (the Five Safes "Safe Setting").
    *   **DSSC:** The [Data Spaces Support Centre (DSSC) Glossary](https://dssc.eu/page/blueprint) defines secure processing components for cross-sectoral dataspaces.

### Research Analytics Zone (RAZ)
*   **Mapping type:** Functional correspondence.
*   **Meaning:** The secure virtual workspace, such as a virtual desktop or notebook, where researchers work with project data. It is similar to the user-facing project workspace inside an SPE. An SPE may also contain other services and control zones.
*   **Authoritative References:**
    *   **DARE UK Blueprint:** [DARE UK Blueprint v2.2 (4.3.1.1)](https://doi.org/10.5281/zenodo.14192786) defines the RAZ as providing the means for a Project Member to gain direct access to approved data in an isolated project environment.
    *   **TEHDAS2 Specs:** [TEHDAS2 M7.4 (6.5.3)](https://tehdas.eu/) defines the interactive remote desktop or API interface for the data user.

### Secure Data Zone (SDZ) / Secure Data Storage (SDS)
*   **Mapping type:** Functional correspondence.
*   **Meaning:** A background zone used to ingest, curate, standardise, and link data. This may include OMOP or CDISC conversions. Researchers normally cannot access it directly, but the exact boundary depends on the local TRE or SPE design.
*   **Authoritative References:**
    *   **DARE UK Blueprint:** [DARE UK Blueprint v2.2 (4.3.1.2)](https://doi.org/10.5281/zenodo.14192786) defines the SDZ as the zone supporting the ingress, egress, management, linkage, and curation of research-ready sensitive datasets.
    *   **SURF SANE:** SANE utilizes a **Secure Data Storage (SDS)** or Secure Data Server, which is a non-interactive VM hosting a Samba server, mounted to Tinker or Blind SANE via a private network to separate raw data from the analysis space [EOSC-ENTRUST_D13.4 - Year one version of EOSC-ENTRUST Blueprint & Interoperability Framework.pdf].

### Query Management Zone (QMZ) / SPE Service Endpoint
*   **Meaning:** The component that receives and runs remote federated queries without moving the raw data.
*   **Authoritative References:**
    *   **DARE UK Blueprint:** [DARE UK Blueprint v2.2 (4.3.1.3)](https://doi.org/10.5281/zenodo.14192786) defines the QMZ as the boundary component supporting federated query submission, execution, and output control.
    *   **TEHDAS2 SPE Specifications:** [TEHDAS2 M7.4 (6.5.4)](https://tehdas.eu/) defines the "SPE Service Endpoint" supporting secure bidirectional streaming protocols (e.g., gRPC with HTTP/2) for federated computing [draft-technical-functional-and-security-specifications-of-secure-processing-environments.pdf].

### Orchestration Zone (OZ)
*   **Meaning:** The administration area that deploys, configures, maintains, and removes the secure environment.
*   **Authoritative References:**
    *   **UK TRE Glossary:** Defines the OZ as the zone managing the deployment, maintenance, and configuration of the TRE, containing no research data and accessible only to infrastructure management roles [UK TRE Glossary].

### Security Server
*   **Mapping type:** Functional correspondence.
*   **Meaning:** A secure gateway or proxy at the edge of a participant’s infrastructure. It routes and protects traffic between environments. The exact security controls depend on the federation design.
*   **Authoritative References:**
    *   **DARE UK Blueprint:** [DARE UK Blueprint v2.2 (4.6.2)](https://doi.org/10.5281/zenodo.14192786) defines the Security Server as a distributed, global-plane synchronized component that secures connections between participants.
    *   **X-Road / SMP / GAIA-X Mappings:** Aligns directly with the X-Road Security Server, GAIA-X Intermediary, or the EU's Smart Middleware Platform (Simpl) Agent.

## 2. Legal & Data Protection States

### Anonymisation
*   **Mapping type:** Direct legal concept with local release controls.
*   **Meaning:** Anonymisation means that people can no longer be identified by means that are reasonably likely to be used. SDC and other output controls reduce disclosure risk, but they do not normally prove that the risk is zero. An output may leave the secure environment only when the relevant law, project rules, and release controls allow it.
*   **Authoritative References:**
    *   **European Union Law:** [Directive (EU) 2019/1024 (Open Data Directive), Recital 52](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32019L1024) and [GDPR Recital 26](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679) define anonymised data as data that does not relate to an identified or identifiable natural person.
    *   **UK TRE Framework:** The [UK TRE Glossary](https://glossary.uktre.org/en/latest/) defines anonymisation as altering personal data so that the individual can no longer be identified, directly or indirectly [TRE Operators Docs Glossary].

### Pseudonymisation
*   **Mapping type:** Direct legal concept under GDPR, with local controls.
*   **Meaning:** Pseudonymised data is still personal data under GDPR if someone can identify a person using additional information. It must be protected accordingly. Encryption, separate storage of identifying information, and separate key management may be suitable controls. The required controls depend on the risk assessment and system design.
*   **Authoritative References:**
    *   **GDPR:** [GDPR Article 4(5)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679) defines pseudonymisation as processing personal data such that it can no longer be attributed to a specific subject without the use of additional, separately kept information.
    *   **TEHDAS2 Specs:** [TEHDAS2 M7.2 Guidelines](https://tehdas.eu/) outline standards for secure pseudonymisation and transient dataset management.

### De-identification / Restricted Research Data
*   **Mapping type:** Operational terminology; not automatically the same as legal anonymisation.
*   **Meaning:** These terms often describe research data from which direct identifiers have been removed. The remaining risk is managed through technical, environmental, and administrative controls such as the Five Safes. Unless an appropriate assessment says otherwise, the data should still be treated as potentially personal data. Do not use “factual anonymisation” as a simple synonym for legal anonymisation.
*   **Authoritative References:**
    *   **UK Digital Economy Act (DEA) Standards:** The UKSA DEA Data Capability Guidance.
    *   **Social Sciences and Humanities Open Cloud (SSHOC):** Baseline guidelines developed in SSHOC WP5.4 for cross-national secure access.

### Access Permit / Data Permit
*   **Mapping type:** Functional correspondence; check the legal status in the relevant framework.
*   **Meaning:** A Data Permit is an administrative or legal decision allowing a specified secondary use, where that term is used. An Access Permit may express the decision in a machine-readable form. It may start environment setup or data delivery, but those actions must still be checked against the decision and the system’s policies.
*   **Authoritative References:**
    *   **EHDS Regulation:** [EHDS Article 2(2y)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327) and [EHDS Article 68](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327).
    *   **TEHDAS2 Specs:** [TEHDAS2 M7.4 Annex A](https://tehdas.eu/) defines the Access Permit as a machine-actionable data structure that contains the information from a data permit in a standardised format.

## 3. Key Technical and Organisational Roles

### Data Controller
*   **Meaning:** Under GDPR, the organisation that decides why and how personal data is processed and is responsible for compliance.
*   **Authoritative References:**
    *   **GDPR:** [GDPR Article 4(7)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679).

### Health Data Holder / Data Custodian
*   **Meaning:** The organisation that collects, stores, or manages sensitive data. Under EHDS, a data holder may be required or allowed to provide approved data to an SPE after receiving a valid permit.
*   **Authoritative References:**
    *   **EHDS:** [EHDS Article 2(2y)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327) defines the Health Data Holder as any entity with the right or obligation to provide electronic health data.
    *   **UK TRE Framework:** Aligns with the role of **Data Custodian** or **Data Provider** defined in the [UK TRE Glossary](https://glossary.uktre.org/en/latest/).

### Health Data User / Researcher / Project Member
*   **Meaning:** A person who has been given limited, lawful access to the secure environment for an approved research project.
*   **Authoritative References:**
    *   **EHDS:** [EHDS Article 2(2u)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327) defines the Health Data User.
    *   **DARE UK Blueprint:** Maps to the **Project Member**, **Job Submitter**, and **Catalogue Searcher** roles.

### Data Processor / SPE Operator
*   **Meaning:** The organisation that runs and manages the SPE or TRE, usually for the Data Controller.
*   **Authoritative References:**
    *   **GDPR:** [GDPR Article 4(8)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679).
    *   **TEHDAS2 Specs:** Aligns with the **SPE Operator**.

### Trusted Health Data Holders
*   **Mapping type:** Framework-specific role; check the local accreditation rules.
*   **Meaning:** Data holders that are authorised or accredited to run their own secure processing environments. They can process their own data internally without sending it elsewhere. The accreditation and role boundaries depend on the framework.
*   **Authoritative References:**
    *   **EHDS Regulation:** Articulated as part of the accredited secure data environments under the EHDS framework.

### Trusted Third Party (TTP) / Indexing Service
*   **Meaning:** An independent organisation that creates and manages linkage keys across datasets, such as matching NHS numbers with education IDs, without seeing the sensitive data itself [DARE-UK-FederatedArchitecture-2_2-full.pdf].
*   **Authoritative References:**
    *   **DARE UK Blueprint:** [DARE UK Blueprint v2.2 (5.5.4)](https://doi.org/10.5281/zenodo.14192786) [DARE-UK-FederatedArchitecture-2_2-full.pdf].

### Principal Investigator (PI) as Input/Output Approver
*   **Mapping type:** Project-specific proposal.
*   **Meaning:** In some projects, the PI may approve inputs or outputs. This must still follow the operator’s controls, the data holder’s requirements, separation-of-duties rules, and any independent review. The PI role does not automatically replace TRE or SPE operator checks.
*   **Authoritative References:**
    *   **ENTRUST Blueprint Architecture:** [D13.4 Section 6.2.2](https://doi.org/10.5281/zenodo.14362388) [EOSC-ENTRUST_D13.4 - Year one version of EOSC-ENTRUST Blueprint & Interoperability Framework.pdf].

### Anonymous Reviewers
*   **Meaning:** A reviewer who receives temporary, limited access to the project area to check results before publication. The reviewer may use a pseudonymous account so the project members do not know their identity [draft-technical-functional-and-security-specifications-of-secure-processing-environments.pdf].
*   **Authoritative References:**
    *   **TEHDAS2 Specs:** [TEHDAS2 M7.4 (4.5.1)](https://tehdas.eu/) [draft-technical-functional-and-security-specifications-of-secure-processing-environments.pdf].

## 4. Identity, Trust, and Security (AAI)

### Community AAI
*   **Mapping type:** Functional correspondence.
*   **Meaning:** The services that connect a researcher’s institutional login, through federations such as eduGAIN, to an identity and set of attributes used by the research network. Authentication, authorisation, identity federation, and attribute exchange are related but different functions [AAI interfaces.pdf, EOSC AAI Architecture 2025 - March 2025.pdf].
*   **Authoritative References:**
    *   **AARC Blueprint Architecture:** The AARC Blueprint Architecture 2025 (AARC-BPA-2025) introduces the "Identity Layer" as a new logical component distinct from the "Community AAI" and "Infrastructure Proxy" [EOSC AAI Architecture 2025 - March 2025.pdf].
    *   **AARC BPA Guidelines:** Expressing group membership and roles according to [AARC-G069](https://aarc-community.org/guidelines/aarc-g069/) [EOSC AAI Architecture 2025 - March 2025.pdf].

### MyAccessID
*   **Mapping type:** Named service; not a general identity model.
*   **Meaning:** A federated identity service used in parts of the European Open Science Cloud. Its role, trust relationships, and supported protocols must be checked in the service documentation. They should not be assumed for every federation [EOSC AAI Architecture 2025 - March 2025.pdf].
*   **Authoritative References:**
    *   **EOSC AAI March 2025 Specification:** Highlights MyAccessID as the initial hub-and-spoke federated login gateway [EOSC AAI Architecture 2025 - March 2025.pdf].

### eID / eIDAS / EUDI Wallet
*   **Meaning:** European digital identity terms and services. For high-assurance access to medical or public-sector data, an institution’s login may need to connect to a verified national electronic ID or the European Digital Identity (EUDI) Wallet [draft-technical-functional-and-security-specifications-of-secure-processing-environments.pdf].
*   **Authoritative References:**
    *   **eIDAS Regulation:** Regulation (EU) No 910/2014 [EOSC AAI Architecture 2025 - March 2025.pdf, draft-technical-functional-and-security-specifications-of-secure-processing-environments.pdf].
    *   **OpenID Federation Wallet Architectures:** [OID-Fed-Wallet 1.0](https://openid.net/specs/openid-federation-wallet-1_0.html) [EOSC AAI Architecture 2025 - March 2025.pdf].

### GA4GH Passports and Visas
*   **Meaning:** Machine-readable credentials that can contain a researcher’s identity, organisation, training, and current access permissions. They can support automated checks at the SPE boundary [EOSC-ENTRUST_D13.4 - Year one version of EOSC-ENTRUST Blueprint & Interoperability Framework.pdf, draft-technical-functional-and-security-specifications-of-secure-processing-environments.pdf].
*   **Authoritative References:**
    *   **Global Alliance for Genomics and Health (GA4GH):** The GA4GH Passport & Visa standard [EOSC AAI Architecture 2025 - March 2025.pdf, draft-technical-functional-and-security-specifications-of-secure-processing-environments.pdf].
