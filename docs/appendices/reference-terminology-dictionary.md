# Reference Terminology Dictionary for Secure Research Environments
*A practical guide to related terms used in the European Health Data Space (EHDS), United Kingdom Trusted Research Environment (UK TRE), DARE UK, and EOSC-ENTRUST sources cited below.*

## Scope and Status
This dictionary compares terms from different frameworks. It is not legal advice, a certification scheme, or a standard. Similar terms may still have different legal meanings, controls, or technical scope. The relevant law, regulator guidance, access decision, and local procedures always take priority.

For concise EHDS definitions, see the [Glossary](glossary.md). This dictionary adds cross-framework comparisons and implementation terminology. Where the documents overlap, the glossary definition and its cited legislation govern the EHDS meaning.

The mapping classifications are this guide's analysis, not classifications assigned by the cited sources:

- **Shared legal concept:** the same legal definition governs both uses.
- **Functional correspondence:** the terms serve a similar purpose but have different legal or governance contexts.
- **Operational analogy:** the comparison may help with implementation, but it is not a formal match.
- **Project-specific proposal:** a suggested design that needs local approval.

Each source claim below identifies a document and section or article. The mapping conclusions remain interpretive and should be reviewed for the intended implementation and jurisdiction.

## The 5-Stage Terminology Pipeline
The following lifecycle and table are an editorial crosswalk created for this guide. They are not defined by the cited frameworks, and they do not claim that every system uses the same workflow or zones.

1. **Data Discovery:** Researchers use data catalogues and metadata to find relevant datasets and their custodians. Finding a dataset does not grant access.
2. **Access Approval:** Researchers submit access requests and receive the relevant legal or administrative decision.
3. **Data Preparation:** Data holders prepare the datasets for the approved project. This may include pseudonymisation, linkage, and de-identification.
4. **Use of Data:** Researchers work in an isolated project workspace inside a Secure Processing Environment (SPE) or Trusted Research Environment (TRE). They may use federated computing where it is available.
5. **Finalisation:** Proposed outputs go through Statistical Disclosure Control (SDC) or another output review. They may be released only when the project rules, legal requirements, and security controls allow it. Local retention and disposal rules govern what then happens to the project environment.

| Lifecycle stage | EHDS-oriented term | UK TRE-oriented term | Relationship | Main caveat |
|---|---|---|---|---|
| Data discovery | Dataset catalogue | Catalogue or search service | Functional correspondence | Metadata visibility does not imply access |
| Access approval | Data permit / access permit | Approval and authorisation workflow | Functional correspondence | Legal authority and decision paths differ |
| Data preparation | SPE preparation services | SDZ / ingestion and curation | Functional correspondence | Zone boundaries vary by implementation |
| Data use | SPE project workspace | RAZ | Narrower functional mapping | A RAZ is not the whole TRE |
| Finalisation | Output control / SDC | Disclosure control / release review | Functional correspondence | Release criteria are governance-specific |

## 1. Architectural & Environmental Mappings

### Secure processing environment (SPE) / trusted research environment (TRE)
*   **Mapping type:** Functional correspondence.
*   **Meaning:** Both terms describe controlled settings for work with sensitive data. They are not synonyms: SPE has a legal definition under the Data Governance Act and specific EHDS requirements, while TRE is used for a broader class of systems and governance practices in the UK TRE Glossary. Treating them as functionally corresponding is this guide's interpretation.
*   **Sources:**
    *   **EU:** [Data Governance Act Article 2(20)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022R0868) defines an SPE; [EHDS Article 73](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327) specifies requirements for EHDS secondary use.
    *   **UK:** The [UK TRE Glossary: Trusted Research Environment](https://glossary.uktre.org/en/latest/#term-trusted-research-environment--tre-) defines the TRE term and relates it to Five Safes governance.

### Research analytics zone (RAZ)
*   **Mapping type:** Functional correspondence.
*   **Meaning:** DARE UK describes the RAZ as the zone where a Project Member directly accesses approved project data, often through a virtual desktop or computational notebook. Comparing it to a user-facing workspace within an SPE is this guide's functional mapping, not a DARE UK or EHDS equivalence.
*   **Source:** [DARE UK Federated Architecture Blueprint v2.2, section 4.3.1.1](https://doi.org/10.5281/zenodo.14192786).

### Secure data zone (SDZ) / secure data storage (SDS)
*   **Mapping type:** Functional correspondence.
*   **Meaning:** DARE UK defines the SDZ as supporting ingress, egress, management, linkage, curation, and provision of research-ready sensitive datasets, with access limited to specified governance roles. EOSC-ENTRUST separately describes SURF's SDS implementation as storage mounted through a non-interactive Secure Data Server on a private network. SDZ and SDS are related but not equivalent terms.
*   **Sources:**
    *   [DARE UK Federated Architecture Blueprint v2.2, section 4.3.1.2](https://doi.org/10.5281/zenodo.14192786).
    *   [EOSC-ENTRUST D13.4, section 5.2.2](https://doi.org/10.5281/zenodo.14362388).

### Query management zone (QMZ)
*   **Mapping type:** Proposed operational analogy; no equivalence is established here.
*   **Meaning:** DARE UK defines the QMZ as handling queries sent to a TRE by remote TREs or external Job Submission services. No equivalence to an EHDS component is asserted.
*   **Source:** [DARE UK Federated Architecture Blueprint v2.2, section 4.3.1.3](https://doi.org/10.5281/zenodo.14192786).

### Orchestration zone (OZ)
*   **Mapping type:** Framework-specific term.
*   **Meaning:** The administration area that deploys, configures, maintains, and removes the secure environment.
*   **Source:** [UK TRE Glossary: Orchestration Zone](https://glossary.uktre.org/en/latest/#term-orchestration-zone--oz-).

### Security server
*   **Mapping type:** Functional correspondence.
*   **Meaning:** In DARE UK, Security Servers are gateways used by Federation Participants. They support secure data exchange and protect the confidentiality, integrity, and auditability of inter-participant exchanges. The blueprint discusses X-Road, GAIA-X, IDSA, and SiMPl as related federated-infrastructure concepts but does not establish direct equivalence to their individual components.
*   **Source:** [DARE UK Federated Architecture Blueprint v2.2, sections 2.3 and 4.6.2](https://doi.org/10.5281/zenodo.14192786).

## 2. Legal & Data Protection States

### Anonymisation
*   **Mapping type:** Related EU and UK legal concepts; jurisdiction-specific assessment required.
*   **Meaning:** Anonymisation means processing personal data so that an individual is no longer identifiable, taking account of all means reasonably likely to be used for identification. SDC and other output controls reduce disclosure risk, but they do not normally prove that the risk is zero. An output may leave the secure environment only when the relevant law, project rules, and release controls allow it.
*   **Sources:**
    *   [GDPR Recital 26](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679).
    *   [UK TRE Glossary: Anonymisation](https://glossary.uktre.org/en/latest/#term-anonymisation).

### Pseudonymisation
*   **Mapping type:** EU GDPR legal concept; UK use must be checked against UK law.
*   **Meaning:** Under GDPR, pseudonymisation requires separately kept additional information protected by technical and organisational measures. Pseudonymised data remain personal data when they can be attributed to a person using additional information.
*   **Sources:** [GDPR Article 4(5) and Recital 26](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679).

### De-identification / restricted research data
*   **Mapping type:** Operational terminology; not automatically the same as legal anonymisation.
*   **Meaning:** These are operational terms whose meanings vary. Removing direct identifiers does not by itself establish anonymisation under GDPR Recital 26. This dictionary does not assign either term a universal legal meaning.
*   **Source for the legal distinction:** [GDPR Recital 26](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679).

### Data permit
*   **Mapping type:** EHDS legal term; no cross-framework equivalence asserted.
*   **Meaning:** An administrative decision issued by an HDAB to a health data user to process specified electronic health data for specified secondary-use purposes. This audit did not locate a stable, versioned source supporting the previous “access permit” comparison, so that comparison has been removed.
*   **Sources:** [EHDS Articles 2(2)(v) and 68](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327).

## 3. Key Technical and Organisational Roles

### Data controller
*   **Mapping type:** EU GDPR legal concept; UK use must be checked against UK law.
*   **Meaning:** Under GDPR, the organisation that decides why and how personal data is processed and is responsible for compliance.
*   **Source:** [GDPR Article 4(7)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679).

### Health data holder / data custodian
*   **Mapping type:** Functional correspondence; Data Custodian is not an EHDS legal synonym.
*   **Meaning:** Under EHDS, a Health Data Holder is a natural or legal person, public authority, agency, or other body that meets the conditions in Article 2(2)(t). In a UK TRE context, a Data Custodian or Data Provider may perform a similar operational role, but the legal duties and scope can differ.
*   **Sources:**
    *   [EHDS Article 2(2)(t)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327).
    *   [UK TRE Glossary: Data Custodian](https://glossary.uktre.org/en/latest/#term-data-custodian). The functional comparison is this guide's interpretation.

### Health data user / researcher / project member
*   **Mapping type:** Functional correspondence; the UK project roles are narrower than the EHDS legal term.
*   **Meaning:** A natural or legal person, including a Union institution, body, office, or agency, that has lawful access to electronic health data for secondary use. In a TRE context, the closest operational roles may include Researcher or Project Member, but these are not direct legal equivalents.
*   **Sources:**
    *   [EHDS Article 2(2)(u)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327).
    *   [DARE UK Federated Architecture Blueprint v2.2, section 3.2](https://doi.org/10.5281/zenodo.14192786) defines Project Member, Job Submitter, and Catalogue Searcher roles. The mapping is this guide's interpretation.

### Data processor
*   **Mapping type:** EU GDPR legal concept; no equivalence to an environment operator asserted.
*   **Meaning:** GDPR defines a processor as a person or body that processes personal data on behalf of a controller. An organisation operating an SPE or TRE is not automatically a processor for every activity; its role depends on the processing and applicable governance arrangements. EHDS Article 74 assigns specific controller and processor roles for EHDS secondary use.
*   **Sources:** [GDPR Article 4(8)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679); [EHDS Article 74](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327).

### Trusted health data holder
*   **Mapping type:** Framework-specific role; designation conditions are set by EHDS Article 72.
*   **Meaning:** A health data holder designated under EHDS Article 72 that can provide access through a compliant Secure Processing Environment and participate in the simplified application procedure. It may assess an application and propose a decision, but the Health Data Access Body remains responsible for issuing the decision.
*   **Source:** [EHDS Article 72](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327).

### Trusted third party (TTP)
*   **Mapping type:** Distinct framework-specific uses; no equivalence asserted.
*   **Meaning:** EHDS Article 66(3) refers to an entity acting as a trusted third party under national law that may hold information needed to reverse pseudonymisation. Separately, the DARE UK data-pooling pattern uses “trusted third-party Index Service” for a service that creates a master index for linkage inside the analysis TRE.
*   **Sources:**
    *   [EHDS Article 66(3)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32025R0327) uses “trusted third party” for an entity that may hold information needed to reverse pseudonymisation under national law.
    *   [DARE UK Federated Architecture Blueprint v2.2, section 2.2.2](https://doi.org/10.5281/zenodo.14192786) uses “trusted third-party index service” in its data-pooling pattern. These uses are not asserted to be equivalent.

### Indexing or linkage service
*   **Mapping type:** Operational analogy to some TTP functions; not a legal synonym.
*   **Meaning:** In the DARE UK blueprint, an Index Service creates linkage spines for datasets. For personal data, it converts between personal identifiers and project-specific linkage keys and must be sufficiently trustworthy to handle personal identifiers. The blueprint leaves the construction of those indexes out of scope.
*   **Source:** [DARE UK Federated Architecture Blueprint v2.2, section 4.3.2](https://doi.org/10.5281/zenodo.14192786).

### Principal investigator (PI) as input/output approver
*   **Mapping type:** Provider-specific implementation described by EOSC-ENTRUST.
*   **Meaning:** EOSC-ENTRUST D13.4 reports that the SAFE, TSD, and CSC SD Services models require the project PI to act as Output Approver and assign a separate Input Approver role to the PI. This is a provider-specific architecture finding, not a general rule for TREs or SPEs.
*   **Source:** [EOSC-ENTRUST D13.4, section 6.2.2](https://doi.org/10.5281/zenodo.14362388).

## 4. Identity, Trust, and Security (AAI)

### EOSC-ENTRUST AAAI
*   **Mapping type:** Project-specific architecture.
*   **Meaning:** EOSC-ENTRUST D16.1 proposes an Authentication, Authorization, and Accounting Infrastructure for a federation of TREs. It builds on the AARC Blueprint Architecture and adds requirements including account creation, identity vetting, attribute-based access control, accounting, and auditing.
*   **Source:** [EOSC-ENTRUST D16.1, sections 5 to 7](https://doi.org/10.5281/zenodo.15006945).

### eID / eIDAS / EUDI Wallet
*   **Mapping type:** Related legal framework and identity mechanisms; not interchangeable terms.
*   **Meaning:** eIDAS is the EU legal framework for electronic identification and trust services; Regulation (EU) 2024/1183 amended it to establish the European Digital Identity Framework. EOSC-ENTRUST D16.1 proposes high-assurance electronic identity vetting, for example through eID or electronic know-your-customer processes. It treats identity wallets as a future option rather than a mandatory requirement in that version.
*   **Sources:** [Regulation (EU) No 910/2014](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32014R0910); [Regulation (EU) 2024/1183](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1183); [EOSC-ENTRUST D16.1, section 6.1](https://doi.org/10.5281/zenodo.15006945).

### GA4GH passports and visas
*   **Mapping type:** Technical standard used as an implementation option.
*   **Meaning:** D16.1 describes a GA4GH Passport as a collection of digitally signed Visas containing subject attributes such as affiliations, organisational roles, accepted terms and policies, researcher status, and dataset-access decisions. It models the Passport as an attribute repository within attribute-based access control and notes limitations in the Visa types available in specification version 1.2.1.
*   **Source:** [EOSC-ENTRUST D16.1, sections 6.2.1 and 6.2.3](https://doi.org/10.5281/zenodo.15006945).
