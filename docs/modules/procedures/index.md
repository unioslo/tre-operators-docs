# Module 4: Operations & Procedures

This module defines consensus-based Standard Operating Procedures (SOPs) required for operational alignment across the federation.

---

## The Need for Standardisation

The federation must enforce consistent workflows across all TRE governance actors. SOPs should cover:

* Interoperability standards, service onboarding, change management, and incident response.
* A user journey that supports non-linear analysis: researchers may refine analyses, request new software, or add data sources after project start.
* Coordination of multi-party agreements, federated queries, and ad-hoc Data Access Committees (DACs) by the federation governance actor.

---

## User Handling and Training

Operating procedures must manage the entire user lifecycle, ensuring access only by authorized and certified individuals.

### Core User Roles

1. Data User: conducts analyses, requests software or output release.
2. TRE Governance: manages project spaces, prepares data, installs software, performs SDC.
3. Data Holder (Data Controller): assesses access requests and supplies data.
4. Federation Governance: coordinates multi-party agreements and federated queries.

### Training and Certification

To implement the “Safe People” principle:

* All users must complete mandatory training covering project spaces, statistical disclosure control (SDC), and data access policies.
* Maintain an electronic record (or “Researcher Passport”) linked to the AAAI system for interoperability across the network.
* Ensure users understand their ethical responsibilities, either via the TRE or their home organisation.

### Data Access Requests

SOPs must standardise the fragmented access-request process:

* Establish a unified process supporting cross-TRE data requests.
* A single point of access should funnel requests to relevant TREs via federation governance.
* Coordinate signing of multiple Data Use Agreements (DUAs) through federation governance to streamline researcher workflows.

---

## Software Management

Define clear procedures for software provisioning while maintaining security controls:

* TRE Operators must be authorised to invoke software interface services.
* SOPs must describe how Researchers request additional software. In mature TREs, software installation is handled by TRE staff.
* Prefer downloading Environment Software Artifacts via federation software services.

---

## Statistical Disclosure Control (SDC) & Output Release

This module outlines the process for output checking and SDC application before any result release.

### Terminology and Focus Shift

Replace the concept of simple “export” with full SDC application. All result outputs **must** pass SDC checks before release to eliminate residual disclosure risk.

### Output Approver Roles

The Output Approver oversees all research outputs leaving the TRE:

* In the ENTRUST RAZ model, the Principal Investigator (PI) acts as Output Approver to reduce bottlenecks and clarify legal responsibility.
* The Data Controller retains legal decision-making authority under GDPR.
* TRE Governance performs SDC checks using a rules-based, triaged approach.

### Output for Federation vs Outside World

* **Within the federation:** Response Objects (query results) may be classified “SDC amber” and exchanged between participants under the federation’s closed, trusted environment.
* **Outside the federation:** Outputs destined for publication must pass the project’s approved disclosure-control process and undergo Output Control oversight.

### Credit Attribution

SOPs must ensure accurate credit to original data generators and enforce data citation (for example via DOIs).

---

## Risk Management & Service Alignment

Operational procedures must safeguard service security, resilience, and quality through robust frameworks.

### Security and Control

* All data exchanges (extracts, queries, results, index data) must be encrypted to ensure confidentiality and integrity.
* TREs must secure data access through systems like AAAI, SSO, and multi-factor authentication.
* Project environments must be strictly isolated.
* Each participant must run a Security Server (SS) that remains operable even if disconnected from central management.

### IT Service Management (ITSM) Standards

* TREs must implement an efficient Service Management System (SMS) to manage security components.
* Adoption of standards such as FitSM is recommended to support the federated service delivery model.

### Compliance and Certification

* TREs should pursue formal certifications (e.g., ISO / IEC 27001) to demonstrate strong information-security management.
* SOPs must address compliance with national legal frameworks governing data sharing.

### Data Protection

* Minimize data collection and storage in line with GDPR principles.
* Implement encryption both in transit and at rest.
* Apply Privacy-by-Design to embed user data protection from system inception.

---

## Data Deletion and Archiving Policies

Define procedures for managing data at the end of a project lifecycle to ensure legal compliance and reproducibility.

### Timely Data Deletion

* TREs must implement mechanisms to delete user data once its authorised retention period expires or when required by the data provider.
* Project environments must have a defined finite duration in the metadata.

### Archiving for Reproducibility

* Instead of closing projects outright, TREs should archive project spaces to allow reinstatement (e.g., for peer review follow-up).
* Archive project analysis environments, code, and intermediate results via the Software Service.
* For certain datasets (especially clinical regulatory ones), implement long-term digital archiving and formal curation.
* Each TRE must publish a clear archival policy outlining retention and recovery conditions.
