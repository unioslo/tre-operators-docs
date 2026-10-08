# Relevance Matrix

This matrix shows which parts of the handbook matter for each type of TRE and role. Use it to plan a reading path: find your TRE type and role, then work through the topics marked ● first.

The handbook is split into two scopes:

- **Core TRE — Modules 1 to 5.** Everything needed to run a TRE on its own, whether or not it joins a federation.
- **Federated TRE — Module 6.** Additional obligations that apply when a TRE connects to other TREs through the federation.

## How to Read This Matrix

### Relevance

| Symbol | Meaning |
|---|---|
| ● | Relevant. Expected reading for this TRE type or role. |
| ○ | Informative, or relevant only for specific implementations. |
| *(blank)* | Not relevant. |

### TRE Types

| Code | TRE type |
|---|---|
| **ORG** | Organisational TRE — operated by and for a single institution. |
| **NAT** | National TRE — operated at national scale, typically serving registry and health data. |
| **FED** | Federated TRE — connected to other TREs through the federation. |

### Roles and Responsibilities

Role names follow the terminology used elsewhere in this handbook. Security architecture and configuration are shown under TRE Builder; day-to-day operations and incident response are shown under TRE Operator.

| Code | Role | Responsibility |
|---|---|---|
| **OPS** | TRE Operator | Day-to-day operations, monitoring, incident response, and user support. |
| **BLD** | TRE Builder | Infrastructure, security architecture and controls, interface and AAAI configuration. |
| **DAT** | Data Manager | Data ingress, curation, linkage, and egress preparation. |
| **GOV** | TRE / Federation Governance | Legal and compliance decisions, policy, access approvals, and multi-party coordination. |
| **OUT** | Output Approver | Disclosure control and oversight of output release. |

## Core TRE

Modules 1 to 5 apply to every TRE, federated or not.

### M1 Fundamentals

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| TRE concepts and principles | core | ● | ● | ● | ● | ● | ● | ● | ● |
| Roles and responsibilities | core | ● | ● | ● | ● | ● | ● | ● | ● |

### M2 Architecture and Setup

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| TRE architecture and zones | core | ● | ● | ○ | ● | ● | ○ | ○ | |
| Interface, IAM and AAI | core / advanced | ● | ● | ● | ● | ● | | ○ | |
| Monitoring and audit | core | ● | ● | ● | ● | ● | ○ | ○ | |

### M3 Interfaces and Configuration

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Data ingress and egress | core | ● | ● | ● | ● | ○ | ● | ○ | ● |
| Query and response interfaces | advanced | ○ | ● | ● | ● | ● | ○ | ○ | |
| Software interfaces | advanced | ○ | ● | ● | ● | ○ | ● | ○ | |

### M4 Operations and Procedures

Module 4 follows the **TRE project operational lifecycle**: a project is taken on, given what it needs to work, operated, has its results checked and released, and is finally closed down. Incident and change management are not a stage; they run across all of them.

| Stage | Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 1. Intake | User and project onboarding | core | ● | ● | ● | ● | ○ | ○ | ● | |
| 2. Provisioning | Data and software operations | core | ● | ● | ● | ● | ○ | ● | ○ | |
| 3. Release | Output checking and SDC | core | ● | ● | ● | ○ | | ○ | ● | ● |
| 4. Closure | Project closure, retention and deletion | core | ● | ● | ● | ● | ○ | ● | ● | |
| *Throughout* | Incident and change management | core | ● | ● | ● | ● | ● | ○ | ● | |

### M5 Legal and Compliance

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Legal and governance responsibilities | core | ● | ● | ● | ○ | ○ | ○ | ● | |
| EHDS and domain-specific requirements | advanced | ○ | ● | ● | | ○ | ○ | ● | |

## Federated TRE

Module 6 applies only to a TRE that connects to other TREs. An organisational TRE that operates on its own can treat this module as background reading.

### M6 Federation

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Federation governance | federated | ○ | ● | ● | ○ | ○ | | ● | |
| Federation trust, registry and AAI | federated | ○ | ● | ● | ● | ● | | ○ | |
| Federation incident coordination | federated | | ● | ● | ● | ● | | ● | |

## Content Categories

| Category | Meaning |
|---|---|
| **core** | Baseline material. Every TRE operator needs it. |
| **advanced** | Needed for a specific capability or implementation choice. |
| **federated** | Applies once the TRE joins a federation. |
