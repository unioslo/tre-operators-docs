# Module 2: Legal Agreement Templates

<p class="tre-page-context tre-role-operator"><strong>Audience:</strong>TRE Providers and Data Holders</p>

## Ethical Frameworks for Federation

This module defines the legal and ethical foundations for cross-border sensitive data federation. Template legal agreements, operating procedures, and interface definitions will be published in future versions of the ENTRUST Blueprint.

---

## Legal Alignment and Governance Metadata

Legal obligations directly shape the governance metadata required in the federation.

* **Governance metadata** records who can access which assets and why (Project metadata, User metadata).
* **Dataset metadata must record the Data Controller**, who is legally accountable for its use.

---

## Multi-Jurisdictional Compliance

Federation requires clear legal roles, agreements, and responsibilities across countries.

### Legal Roles and Agreements

Define legal responsibility using standard agreements:

| Agreement                         | Purpose                                                                                |
| --------------------------------- | -------------------------------------------------------------------------------------- |
| **Data Sharing Agreement (DSA)**  | Sets overall conditions, licensing, and access rules for sharing data between parties. |
| **Data Transfer Agreement (DTA)** | Template per data type; defines requirements for transferring data securely.           |
| **Data Use Agreement (DUA)**      | Defines access conditions, user obligations, and permitted use of data.                |

Roles must be explicit—including **Data Controller** and **Data Processor**, as defined in GDPR and national laws.

### Process Harmonisation

* The Federation Governance actor must coordinate and simplify the signing of multiple DUAs across TREs.
* A single point of access should route project-based agreements to all relevant TREs.
* TRE SOPs must address **data transfers to third countries** to ensure legal compliance.

---

## EHDS Alignment (Health Data)

The European Health Data Space (EHDS) introduces new rules for secondary health data use.

### EHDS and Secure Processing Environments (SPE)

* The upcoming **EHDS Act** defines requirements for **Secure Processing Environments (SPE)**.
* The TRE **Research Analytics Zone (RAZ)** is functionally equivalent to an EHDS SPE.

### Health Data Access Bodies (HDABs)

* EHDS will create **Health Data Access Bodies (HDABs)** to evaluate and permit access to health data.
* Once operational, access requests in the federation should follow the EHDS procedures.
* The **Data Access Application Management System (DAAMS)** will be the official platform for submitting EHDS access requests.

### Roles under EHDS

* When a project spans multiple TREs, one TRE **must act as the Project Host**.
* Future guidance will clarify legal responsibility between the TRE and PI for output approvals, especially when the TRE is not the Data Controller.

---

## Model Agreements

No legal agreement for a TRE federation currently exists. The frameworks below should be considered when preparing for a TRE federation consortium. An agreement creates legal certainty about the obligations and liabilities of the parties involved.

### How agreements are classified

Frameworks distinguish between types of agreements in four ways:

- By scope: what the agreement applies to (law, federation, organisation, dataset, user). Law may be placed at the highest level, even though it is a legal act, not a contract.
- By precedence: which agreement supersedes the other. Typically a general agreement may be superseded by a more specific agreement (e.g. iSHARE, SURF model DPA, art. 13.4; or Life Science terms of use).
- By number of participants: bilateral versus multilateral.
- By GDPR role: between controller and processor, between two controllers or between processor and sub-processor.

In the EOSC-ENTRUST Blueprint, it is recommended to have more than one type of agreement in a federation:

- A consortium agreement where each member signs
- A Data processing agreement (DPA)
- A joint controller agreement when certain tasks needs to be decided together
- A data access agreement  between data holder and user institution

### Comparison of frameworks

Each framework classifies agreements differently. The table can serve as a starting point for a federation agreement. A dash means the framework does not specify this dimension.

| Framework | Scope | Precedence | Number of participants | GDPR role |
|-----------|-------|-----------|------------------------|-----------|
| [TEHDAS2 D7.4](#tehdas2-d74) | Federation → Domain → Use case | - | - | DPAs with SPE operators |
| [SATRE](#satre-20) | Collaboration + researcher access agreements | - | - | - |
| [DSSC](#dssc-blueprint-v30) | Institutional (data space) → data-sharing (transaction); services separate | - | - | Optional DPA and Data Exchange Agreement (from iSHARE) |
| [iSHARE](#ishare-trust-framework-version-30) | Terms of Use → data space agreement → bilateral | Specific first, except security, suspension, annexes | One Accession Agreement per participant | DPA (processor) and Data Exchange Agreement (controllers) |
| [Sitra](#sitra-rulebook-model-for-a-fair-data-economy-version-30) | Constitutive + Accession (data space) → Dataset Terms of Use (dataset) | Generic first; law prevails | Multilateral only | Presumed separate controllers; processor only under a DPA |
| [FEGA](#fega-collaboration-agreement-for-the-operation-of-a-node-within-the-federated-ega-v13) | Common Kernel (federation) → Agreement (Node) → flow-down terms (providers, users) | - | One agreement per Node with Central EGA (hub) | None in the agreement; bilateral DPAs with data submitters |
| [GDPR, EDPB 07/2020](#gdpr-edpb-072020) | - | - | - | Art. 26 arrangement; Art. 28 contract (incl. sub-processor) |

## References

- SURF Model Data Processing Agreement (English version), SURF, 2025. [https://pec.surf.nl/asset/surf-model-data-processing-agreement-eng/](https://pec.surf.nl/asset/surf-model-data-processing-agreement-eng/)

- Life Science RI Terms of Use for Service Providers, Life Science RI, 2022. [https://www.lifescience-ri.eu/terms-of-use-for-service-providers/](https://www.lifescience-ri.eu/terms-of-use-for-service-providers/)

### TEHDAS2 D7.4

TEHDAS2 D7.4 Technical specification for health data access bodies on the implementation of secure processing environments. [https://doi.org/10.5281/zenodo.20266473](https://doi.org/10.5281/zenodo.20266473)

### SATRE 2.0

SATRE 2.0 Standard Architecture for Trusted Research Environments, specification v2.0.1. [https://satre-specification.readthedocs.io/en/v2.0.1/specification.html](https://satre-specification.readthedocs.io/en/v2.0.1/specification.html)

### DSSC Blueprint v3.0

DSSC Blueprint v3.0, Data Spaces Support Centre. [https://blueprint.dssc.eu/](https://blueprint.dssc.eu/)

### iSHARE Trust Framework version 3.0

iSHARE Trust Framework version 3.0, iSHARE Foundation. [https://framework.ishare.eu/](https://framework.ishare.eu/)

### Sitra Rulebook model for a fair data economy, version 3.0

Sitra Rulebook model for a fair data economy, version 3.0. [https://www.sitra.fi/en/publications/rulebook-for-a-fair-data-economy/](https://www.sitra.fi/en/publications/rulebook-for-a-fair-data-economy/)

The Sitra General Terms and Conditions rank the Constitutive Agreement above the Dataset Terms of Use ('Applicability, Scope, and Governance'), while in contradiction the Dataset Terms of Use template states that it prevails over the Constitutive Agreement ('Applicability and Scope').

### FEGA Collaboration Agreement for the operation of a Node within the Federated EGA, V1.3

FEGA Collaboration Agreement for the operation of a Node within the Federated EGA, V1.3. [https://drive.google.com/file/d/1QAKABRB5ZxAJlQSwFHaJ3e6TdtwZaCYs/view](https://drive.google.com/file/d/1QAKABRB5ZxAJlQSwFHaJ3e6TdtwZaCYs/view)

### GDPR, EDPB 07/2020

- GDPR Regulation (EU) 2016/679, General Data Protection Regulation. [https://eur-lex.europa.eu/eli/reg/2016/679/oj](https://eur-lex.europa.eu/eli/reg/2016/679/oj)

- EDPB Guidelines 07/2020 on the concepts of controller and processor in the GDPR, version 2.1. [https://www.edpb.europa.eu/documents/guideline/guidelines-072020-on-the-concepts-of-controller-and-processor-in-the-gdpr_en](https://www.edpb.europa.eu/documents/guideline/guidelines-072020-on-the-concepts-of-controller-and-processor-in-the-gdpr_en)

