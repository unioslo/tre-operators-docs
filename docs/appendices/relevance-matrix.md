# Relevance Matrix

This matrix shows which parts of the handbook matter for each type of TRE and role. Use it to plan a reading path: find your TRE type and role, then work through the topics marked ● first.

The handbook covers five core modules needed to run a TRE:

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

## Modules

Modules 1 to 5 provide everything needed to run a TRE.

### M1 TRE Architecture and Fundamentals

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| TRE concepts and principles | core | ● | ● | ● | ● | ● | ● | ● | ● |
| Roles and responsibilities | core | ● | ● | ● | ● | ● | ● | ● | ● |

### M2 Template Legal Agreement

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Legal and governance responsibilities | core | ● | ● | ● | ○ | ○ | ○ | ● | |
| EHDS and domain-specific requirements | advanced | ○ | ● | ● | | ○ | ○ | ● | |

### M3 Blueprint Architecture

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| TRE architecture and zones | core | ● | ● | ○ | ● | ● | ○ | ○ | |
| Interface, IAM and AAI | core / advanced | ● | ● | ● | ● | ● | | ○ | |
| Monitoring and audit | core | ● | ● | ● | ● | ● | ○ | ○ | |

### M4 Federation Interface Definitions and Collaboration

| Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Data ingress and egress | core | ● | ● | ● | ● | ○ | ● | ○ | ● |
| Query and response interfaces | advanced | ○ | ● | ● | ● | ● | ○ | ○ | |
| Software interfaces | advanced | ○ | ● | ● | ● | ○ | ● | ○ | |

### M5 Operating Procedures

Module 5 follows the **TRE project operational lifecycle**: a project is taken on, given what it needs to work, operated, has its results checked and released, and is finally closed down. Incident and change management are not a stage; they run across all of them.

| Stage | Topic | Category | ORG | NAT | FED | OPS | BLD | DAT | GOV | OUT |
|---|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 1. Intake | User and project onboarding | core | ● | ● | ● | ● | ○ | ○ | ● | |
| 2. Provisioning | Data and software operations | core | ● | ● | ● | ● | ○ | ● | ○ | |
| 3. Release | Output checking and SDC | core | ● | ● | ● | ○ | | ○ | ● | ● |
| 4. Closure | Project closure, retention and deletion | core | ● | ● | ● | ● | ○ | ● | ● | |
| *Throughout* | Incident and change management | core | ● | ● | ● | ● | ● | ○ | ● | |

| Category | Meaning |
|---|---|
| **core** | Baseline material. Every TRE operator needs it. |
| **advanced** | Needed for a specific capability or implementation choice. |
