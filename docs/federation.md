# Federation Integration

Core Services define the Federation and provide common functions for coordinated and secure operation.

## Security Server (SS)

Every Federation Participant runs a standard Security Server, which acts as the secure gateway for all inter-TRE traffic.

- Deploy a standard Security Server for each Federation Participant.
- Configure Security Servers according to the approved global settings.
- Security Servers continue operating independently if control-plane connectivity to Federation Management Services is interrupted.

## Federation Registry Services

Registry services record information about the Federation's elements. Register all Projects with the Federation Registry.

The Registry records information in three categories:
1. Infrastructure Metadata: Describe Participants and log operational data.
2. Content Metadata (Dataset Metadata): Record catalogue-level information about datasets, such as Data Controller, name, and time coverage.
3. Governance Metadata: Track users and activities, including Project metadata (title, host TRE, duration, authorised members) and User metadata (affiliation, accreditation status, training records).

## Trust Services and AAAI

Trust services secure the data exchange layer and support confidentiality, integrity, non-repudiation, and availability.

- The Project defines the authorisation context, links Project Members to the data they can use, and specifies the host TRE.
- Assign globally recognizable and unique Federation Identities to Projects, Project Members, and Datasets.
- Train or accredit all users of sensitive data to an acceptable level ("Safe People").

For definitions of federation-related terms, see the [Glossary](appendices/glossary.md). For architectural details, see [Reference Architecture](appendices/reference-architecture.md).
