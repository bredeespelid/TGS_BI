## GCP Usage & Billing Model – Overview

This Power BI model is built using a star schema with `F_GCP_COST` as the central fact table, connected to multiple dimension tables such as `D_GCP_PROJECT`, `D_GCP_COST_ALLOCATION`, `D_GCP_CREDITS`, `D_GCP_LOCATION`, and others. It supports both standard and DirectQuery variants to enable real-time insights and flexibility in dashboard design.

The purpose of this structure is to:
- Enable efficient cost tracking and allocation across GCP projects and departments.
- Support granular filtering through labeling (`D_GCP_LABEL`, `D_GCP_PGS_CUSTOM_LABEL`).
- Maintain clarity and normalization by separating metadata dimensions (e.g., SKU, credits, location).
- Align cost data with temporal dimensions like invoice and run dates for consistent time-based analysis.

The model ensures scalability and performance while allowing both operational and financial stakeholders to drill down into GCP spend with precision.

![GCP Usage & Billing Model](https://github.com/bredeespelid/TGS_BI/blob/main/default_structure/default_structure.png?raw=true)
