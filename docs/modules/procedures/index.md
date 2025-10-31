# Operating Procedures

This module addresses formalized, consensus-based Standard Operating Procedures (SOPs), essential for operational alignment in the federation.

## The Need for Standardisation

Federation requires coordination and commonality in key workflows across TRE Governance actors.

*   **Governance Focus:** SOPs must address the governance focus of the Federation Authority (FA), which includes **interoperability standards, service onboarding, coordinated change management, and incident response**.
*   **Workflow Flexibility:** The new user journey **MUST** support a non-linear analysis process, allowing researchers to refine analyses, request new software, or add data sources *after* starting a project.
*   **Federation Governance Role:** The generic user journey includes the **Federation Governance** actor, responsible for coordinating multi-party agreements, receiving/distributing federated queries, and coordinating ad hoc Data Access Committees (DACs).

*   Governance Focus: Address the governance focus of the Federation Authority (FA) in SOPs, including interoperability standards, service onboarding, coordinated change management, and incident response.
*   Workflow Flexibility: Support a non-linear analysis process in the new user journey, allowing researchers to refine analyses, request new software, or add data sources after starting a project.
*   Federation Governance Role: Include the Federation Governance actor in the user journey to coordinate multi-party agreements, receive and distribute federated queries, and coordinate ad hoc Data Access Committees (DACs).

## User Journey Gaps to Address

The SOPs must address critical operational gaps identified by Drivers:

Address critical operational gaps in SOPs as identified by Drivers:

1.  **Missing Steps:** Administrative and support steps missing from traditional user journeys, such as explicit **cost management and payment** and formal **project start procedures**.
2.  **User Support:** Dedicated **User Support** must be available at both the TRE level and the federation level throughout the project duration.
3.  **Role Clarity:** The user journey must support two distinct use cases: 1) the user discovers data and applies for access, and 2) the user uploads their own data to the TRE for secure analysis.

## User Handling and Training

Operating procedures must cover the full user lifecycle, ensuring only authorized and certified personnel access sensitive resources.

Cover the full user lifecycle in operating procedures to ensure only authorized and certified personnel access sensitive resources.

### Core User Roles

The user journey operates around four principal roles:

1.  **Data user:** Performs analysis, requests software, requests output release.
2.  **TRE Governance:** Manages project space, handles data preparation, installs software, performs SDC.
3.  **Data holder (Data Controller):** Evaluates data access requests and provides data.
4.  **Federation Governance:** Coordinates multi-party agreements and federated queries.

### Training and Certification

To achieve the "Safe People" principle, all users must be accredited.

Accredit all users to achieve the "Safe People" principle.

*   **Mandatory Training:** Safe Researcher Training and Certification are required. This training should cover **using the TRE project space, statistical disclosure, and data access policies**.
*   **Electronic Records:** The federation requires an **electronic training record/researcher passport** linked to the AAAI to ensure interoperability and queryability across the network.
*   **Ethical Guidance:** TREs **SHOULD** assure that users understand their ethical responsibilities while analyzing sensitive data, which may be offered by the TRE or required from the user's home organization.

*   Mandatory Training: Complete Safe Researcher Training and Certification. Cover using the TRE project space, statistical disclosure, and data access policies in training.
*   Electronic Records: Link electronic training records or researcher passports to the AAAI to ensure interoperability and queryability across the network.
*   Ethical Guidance: Ensure users understand their ethical responsibilities while analyzing sensitive data. TREs may offer this guidance or require it from the user's home organization.

### Data Access Requests

Currently, the access application process is highly fragmented. SOPs will need to standardize this:

Standardize the access application process in SOPs to address current fragmentation.

*   **Unified Process:** A standardized data access request process that supports requesting data from multiple TREs needs to be developed.
*   **Single Point of Access:** Ideally, requests should be funneled through a **single point of access**, where Federation Governance distributes the request to the relevant TREs.
*   **Multi-Party Agreements:** Federation Governance **MUST** coordinate the signing of multiple data use agreements (DUAs) to streamline the process for researchers.

*   Unified Process: Develop a standardized data access request process that supports requesting data from multiple TREs.
*   Single Point of Access: Funnel requests through a single point of access, where Federation Governance distributes the request to the relevant TREs.
*   Multi-Party Agreements: Coordinate the signing of multiple data use agreements (DUAs) through Federation Governance to streamline the process for researchers.

### Software Management

Procedures are needed for providing approved software while maintaining security:

Provide approved software through procedures that maintain security.

*   **TRE Operator Role:** System actors in the role of **TRE Operator SHALL be authorised to invoke Software interface services**.
*   **Controlled Access:** SOPs must detail the process for Researchers requesting additional software. Note that at some mature TREs (e.g., UKDS/GESIS), **self-installation of software is not allowed** by the user and must be performed by TRE staff.
*   **Software Service Integration:** TREs **SHOULD** download Environment Software Artifacts from Federation Software Services (rather than downloading directly from the source) to ensure an audit trail and proper metadata encapsulation.

*   TRE Operator Role: Authorize system actors in the role of TRE Operator to invoke Software interface services.
*   Controlled Access: Detail the process for Researchers requesting additional software in SOPs. At some mature TREs (e.g., UKDS/GESIS), TRE staff must perform software installation; users cannot self-install software.
*   Software Service Integration: Download Environment Software Artifacts from Federation Software Services to ensure an audit trail and proper metadata encapsulation, rather than downloading directly from the source.

## Statistical Disclosure Control (SDC) and Output Release

This module details the critical process of output checking, emphasizing the mandatory application of Statistical Disclosure Control (SDC) before results are released.

Detail the critical process of output checking in this module, emphasizing the mandatory application of Statistical Disclosure Control (SDC) before releasing results.

### Shift in Terminology and Focus

The Drivers strongly advised shifting the focus from simple “export” to **Statistical Disclosure Control (SDC)**, as **all results outputs MUST undergo an SDC check** before being released to the user to ensure that **no residual risk of disclosure exists**.

Shift the focus from simple export to Statistical Disclosure Control (SDC). Check all results outputs with SDC before releasing them to the user to ensure no residual risk of disclosure exists.

### Output Approver Roles

The Output Approver is responsible for checking any and all research outputs to be released from the TRE to the "outside world".

*   **ENTRUST RAZ Model:** The **Principal Investigator (PI)** is designated as the **Output Approver** for the Project environment. This approach aims to limit infrastructure scalability bottlenecks and clarify legal responsibility.
*   **Legal Basis:** The **Data Controller** needs to make the decision about the **export of results under GDPR**.
*   **Process Requirements:** SDC checks are performed by TRE Governance. The process is based on a rules-based, triaged approach, often including suppression of small cell counts.

### Output for Federation vs. Outside World

The level of oversight required depends on the destination of the output.

*   **Exchange within Federation:** Response Objects (query results) are designated **"SDC amber"** but are often considered safe when exchanged between Federation Participants due to the network's closed nature and guaranteed confidentiality, integrity, and traceability.
*   **Release to Outside World:** Outputs destined for publication (Response Objects created in response to Discovery Services or final results) **MUST** pass the Project’s approved disclosure control and are overseen by an **Output Control process**.

*   Release to Outside World: Pass outputs destined for publication (Response Objects created in response to Discovery Services or final results) through the Project’s approved disclosure control and oversee them with an Output Control process.

### Credit Attribution

SOPs must include procedures to ensure proper credit and citation.

Include procedures in SOPs to ensure proper credit and citation.

*   **Requirement:** There is a requirement for **Credit attribution to the original data generator**.
*   **Data Citation:** Policies or processes are needed to ensure data is properly cited, potentially including the use of DOIs.

*   Requirement: Attribute credit to the original data generator.
*   Data Citation: Ensure data is properly cited through policies or processes, potentially including the use of DOIs.

## Risk Management and Service Alignment

Operational procedures must ensure the security, resilience, and quality of the federation services through robust management and compliance frameworks.

Ensure the security, resilience, and quality of federation services through robust management and compliance frameworks in operational procedures.

### Security and Control

*   **Data Confidentiality and Integrity:** The Federation **MUST** ensure the **confidentiality and integrity of data exchange**. All data exchange (extracts, queries, results, index data) **MUST** be encrypted.
*   **Access Security:** TREs **MUST** ensure the security of data access and use, which is partly achieved via AAI, SSO solutions, and two-factor authentication.
*   **Project Isolation:** Project Environments **MUST** maintain strict isolation from one another, which is a key security measure.
*   **Security Servers (SS):** Every Participant **MUST** run a standard SS. The SS **MUST** be able to continue operating independently if disconnected from management services.

*   Data Confidentiality and Integrity: Ensure the confidentiality and integrity of data exchange in the Federation. Encrypt all data exchange (extracts, queries, results, index data).
*   Access Security: Ensure the security of data access and use in TREs, using AAI, SSO solutions, and two-factor authentication.
*   Project Isolation: Maintain strict isolation between Project Environments as a key security measure.
*   Security Servers (SS): Run a standard SS for every Participant. Ensure the SS can continue operating independently if disconnected from management services.

### IT Service Management (ITSM) Standards

To ensure consistent service quality and management across nodes:

*   **SMS Requirement:** EOSC Nodes are required to establish an efficient framework to control security aspects.
*   **Recommended Standard:** Adoption of the **FitSM standard** is recommended for the Service Management System (SMS), as it is suited to the federated nature of service delivery in EOSC.

*   SMS Requirement: Establish an efficient framework to control security aspects in EOSC Nodes.
*   Recommended Standard: Adopt the FitSM standard for the Service Management System (SMS), as it suits the federated nature of service delivery in EOSC.


### Compliance and Certification

TREs need to demonstrate compliance through formal certification.

Demonstrate compliance in TREs through formal certification.

*   **Certification:** TREs **SHOULD** demonstrate good information management and security via certifications, such as **ISO/IEC 27001** (Information Security Management).
*   **Legal Compliance:** SOPs must address **Compliance with various national legal frameworks for data sharing**.

*   Certification: Demonstrate good information management and security in TREs through certifications, such as ISO/IEC 27001 (Information Security Management).
*   Legal Compliance: Address compliance with various national legal frameworks for data sharing in SOPs.

### Data Protection

The TRE MUST ensure **Data Protection and Encryption**:

Ensure Data Protection and Encryption in the TRE:

*   **Minimisation:** Processes and stores only the data necessary for intended operations, following **GDPR principles**.
*   **Encryption:** Adopt **Encryption Standards when needed** to ensure Data Protection In-Transit and At-Rest.
*   **Privacy by Design:** Ensures all systems prioritize user data protection from the initial stages of development.

*   Minimisation: Process and store only the data necessary for intended operations, following GDPR principles.
*   Encryption: Adopt encryption standards when needed to ensure Data Protection In-Transit and At-Rest.
*   Privacy by Design: Prioritize user data protection in all systems from the initial stages of development.

## Data Deletion and Archiving Policies

Procedures are required for managing data at the end of the project lifecycle to ensure compliance with legal mandates and reproducibility requirements.

Manage data at the end of the project lifecycle through procedures to ensure compliance with legal mandates and reproducibility requirements.

### Timely Data Deletion

*   **Mandatory Mechanisms:** TREs **MUST** implement mechanisms for **timely deletion of the data** (e.g., from user project space) once the authorized period expires, or completely from the TRE when required by the data provider.
*   **Project Duration:** Project Environments have a finite duration defined by the Project metadata.

*   Mandatory Mechanisms: Implement mechanisms for timely deletion of data in TREs (e.g., from user project space) once the authorized period expires, or completely from the TRE when required by the data provider.
*   Project Duration: Define a finite duration for Project Environments in the Project metadata.

### Archiving for Reproducibility

Procedures must balance timely deletion with the necessity of preserving research context for validation and reuse.

Balance timely deletion with the necessity of preserving research context for validation and reuse in procedures.

*   **Project Archival:** Instead of simple closure, Project spaces **SHOULD be archived** to allow reinstatement (e.g., following a peer review resulting in further requests).
*   **Code and Environment:** Archiving for reproducibility (R025) can be done by using the **Software Service** to store Project environments, including project analysis software, code, and intermediate results.
*   **Long-Term Preservation (Clinical Data):** Certain datasets, especially those used in clinical research for regulatory submissions, **MUST** be preserved long-term. This introduces the need for **formal digital archiving processes** and curation actions.
*   **Policy:** Each TRE **MUST** maintain and communicate a transparent **archival policy** outlining data retention and recovery conditions.

*   Project Archival: Archive Project spaces instead of simply closing them to allow reinstatement (e.g., following a peer review resulting in further requests).
*   Code and Environment: Use the Software Service to store Project environments, including project analysis software, code, and intermediate results, for reproducibility (R025).
*   Long-Term Preservation (Clinical Data): Preserve certain datasets, especially those used in clinical research for regulatory submissions, long-term. Implement formal digital archiving processes and curation actions.
*   Policy: Maintain and communicate a transparent archival policy in each TRE, outlining data retention and recovery conditions.