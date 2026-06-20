# Multi-Cloud Infrastructure Baseline & Cost Analysis Workspace

## Project Overview
This repository functions as the central documentation and engineering workspace for a multi-cloud infrastructure total cost of ownership (TCO) analysis. It details a rigorous baseline comparison between Amazon Web Services (AWS) and Microsoft Azure for a core, high-availability production web application architecture.

The objective of this analysis is to evaluate cost-performance alignment, ensure regional feature parity, and deliver concrete financial data models for engineering stakeholders.

---

## Repository Directory Architecture Map
This project workspace is organized according to the following tree structure to maintain immutable documentation trails and clear separation of concerns:

```text
├── estimates/
│   ├── aws-estimate-link.txt       # Public cloud-hosted shareable link for the active AWS configuration
│   └── azure-estimate-link.txt     # Public cloud-hosted shareable link for the active Azure configuration
├── screenshots/
│   ├── aws-summary-matrix.png      # Complete, verified summary view of the AWS Calculator canvas
│   ├── azure-summary-matrix.png    # Complete, verified summary view of the Azure Calculator canvas
│   ├── azure-vm-configuration.png  # Detailed instance type and hardware capacity capture for Azure
│   ├── azure-storage-top.png       # Region, capacity tier, and performance scope for Blob Storage
│   └── azure-bandwidth.png         # Internet egress routing profiles and subtotal validation
├── ExportedEstimate.xlsx           # Complete backing spreadsheet exported directly from Azure Calculator
├── report.md                       # Comprehensive, full-length Total Cost of Ownership (TCO) report
└── README.md                       # Workspace landing guide and executive cost dashboard
```

---

## Quick-Reference Financial Dashboard

The infrastructure evaluation yields the following high-level cost metrics based on the specified engineering profiles:

* **Target Target Profile:** 2 Web Server VMs (2 vCPUs, 8 GiB RAM each), 100 GB Object Storage + API operations, 500 GB Outbound Internet Egress/Month.
* **AWS Deployment Cost:** **$173.66 / Month** ($2,083.92 Annualized)
* **Azure Deployment Cost:** **$164.58 / Month** ($1,975.01 Annualized)
* **Financial Decision Advantage:** **Microsoft Azure** represents the optimal baseline architecture, yielding an immediate savings of **$9.08 per month** ($108.91 per year).

---

## Verification & Active Audit Links

The interactive, live cloud configurations are maintained via hosted endpoints and can be audited directly through the cloud vendor infrastructure engines below:

* **AWS Live Calculator Canvas:** [Verify AWS Architecture State](https://calculator.aws/#/estimate?id=a04c6a74ce6c916b909f4d471e0fbe63e7cbb97c)
* **Azure Live Calculator Canvas:** [Verify Azure Architecture State](https://azure.com/e/3502308a1cc4400fa86112fcac4ee563)

---

## How to Reproduce and Validate the Data Models

To audit, adjust, or expand upon these baseline calculations:
1. Access the provided public calculator links to inspect active regional variables, instance family profiles, or itemized transactional cost structures.
2. Review the `/screenshots/` directory to audit visual configuration states captured at the time of architectural baseline sign-off.
3. Open `ExportedEstimate.xlsx` to analyze the raw, multi-tab data structures containing precise decimal unit rates, lifecycle pricing parameters, and localized subscription configurations.
4. For contextual technical justifications and deep optimizations (such as Reserved Instances and CDN caching shifts), read the full production-ready analysis report located in **`report.md`**.