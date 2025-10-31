# Federation Integration

Core Services collectively define the Federation, providing common functions necessary for coordinated and secure operation.

## Security Server (SS)

The Security Server is mandatory for every Federation Participant and acts as the **secure common gateway for all inter-TRE traffic**.

*   **Deployment:** Every Federation Participant **MUST** run a standard Security Server.
*   **Configuration:** Security Servers **MUST** operate to an agreed and approved global configuration.
*   **Resilience:** If control-plane connectivity to Federation Management Services is interrupted, **Security Servers MUST be able to continue operating independently**.

## Federation Registry Services

Registry services record information about the Federation's different elements. All Projects **MUST** be registered with the Federation Registry.

The Registry records information across three key categories:
1.  **Infrastructure Metadata:** Static descriptions of Participants (e.g., service types, capabilities) and dynamic Operational Metadata (e.g., logging data).
2.  **Content Metadata (Dataset Metadata):** High-level, catalogue-level information about datasets (e.g., Data Controller, name, time coverage).
3.  **Governance Metadata:** Information about users and activities. This includes **Project metadata** (title, host TRE, duration, authorised members) and **User metadata** (affiliation, accreditation status, training records).

## Trust Services and AAAI

Trust services are crucial for securing the foundational data exchange layer, supporting confidentiality, integrity, non-repudiation, and availability.

*   **Project Context:** The **Project** defines the authorisation context, linking Project Members to the data they are authorised to use and defining the host TRE.
*   **Identities:** Federation Identities for **Projects**, **Project Members**, and **Datasets** **MUST** be globally recognizable and unique within the Federation.
*   **Researcher Accreditation:** Best practice requires that all users of sensitive data be **trained or accredited** to an acceptable level ("Safe People").

For definitions of federation-related terms, see the [Glossary](appendices/glossary.md). For architectural details, see [Reference Architecture](appendices/reference-architecture.md).