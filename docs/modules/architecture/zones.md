A TRE is modelled using three functional zones; not every TRE needs to support all three.

| Zone | Function | Key Requirements |
| :--- | :--- | :--- |
| **Research Analytics Zone (RAZ)** | Provides the Project Environments where a Project Member gains direct access to approved data for analysis. | RAZ **MUST** have one or more Project Environments. RAZ is comparable to the EHDS **Secure Processing Environment (SPE)**. The PI acts as the **Output Approver** for the RAZ Project environment. |
| **Secure Data Zone (SDZ)** | Supports data management, ingress, egress, linkage, curation, and provision of research-ready sensitive datasets. | An SDZ **MUST** have a **Data Management function**. Data movements to or from the SDZ **MUST** pass through this function. |
| **Query Management Zone (QMZ)** | Handles remote queries (direct or indirect) sent from other federated TREs or Job Submission Services. | QMZ supports federated analytics. A QMZ that supports indirect queries **MUST** include a **Job Controller component** and a **Job Approval process**. |