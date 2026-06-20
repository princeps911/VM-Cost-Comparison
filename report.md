\# Total Cost of Ownership (TCO) \& Cloud Architecture Infrastructure Report



\## Executive Summary

This comprehensive architectural report delivers an exhaustive total cost of ownership (TCO) comparison between Amazon Web Services (AWS) and Microsoft Azure. The target under evaluation is a baseline multi-tier production web application infrastructure deployed in primary North American data center regions.



Based on detailed multi-variate modeling across compute, storage, and networking layers, \*\*Microsoft Azure provides a more cost-effective baseline framework\*\* for this specific architectural footprint. 



\### Key Bottom-Line Metrics:

\* \*\*AWS Grand Total:\*\* \\$173.66 / month (\\$2,083.92 annualized)

\* \*\*Azure Grand Total:\*\* \\$164.58 / month (\\$1,975.01 annualized)

\* \*\*Net Variance:\*\* Azure delivers a \*\*\\$9.08 / month (5.23%) cost reduction\*\* over AWS.

\* \*\*Primary Cost Driver:\*\* Asymmetrical pricing structures within network egress and data routing allowances. Azure provides a built-in 100 GB/month internet egress tier for free, whereas the standalone AWS pricing model evaluates raw data distribution across un-discounted baseline on-demand brackets.



\---



\## 1. Architectural Profile \& Baseline Specifications

To ensure an objective evaluation, infrastructure specifications were strictly cross-mapped to achieve raw structural and functional parity across both ecosystem catalogs. The application architecture consists of a load-balanced web presentation layer with persistent state object dependencies, modeled against the following parameters:



\* \*\*Regional Scope:\*\* US East (N. Virginia - `us-east-1`) for AWS; East US for Microsoft Azure. This ensures localized market cost parity and low-latency profiles.

\* \*\*Compute Tier:\*\* Two (2) concurrent virtual instances operating continuous 24/7 runtimes (730 hours/month per instance). Each instance requires exactly 2 vCPUs and 8 GiB of RAM.

\* \*\*Persistent Operating System Storage:\*\* 30 GB to 32 GB of durable, non-volatile solid-state block storage attached to each virtual instance.

\* \*\*Object Storage Layer:\*\* 100 GB of highly available, standard-tier object storage housing static web assets and user uploads, subject to an active transaction load of 10,000 write (PUT/COPY) operations and 100,000 read (GET/SELECT) operations per month.

\* \*\*Network Egress Topology:\*\* 500 GB per month of outbound internet data transfer representing application payloads delivered to public external users.



\---



\## 2. Financial Summary Matrix



The following structural matrix itemizes the calculated monthly subtotal costs across both cloud provider platforms:



| Infrastructure Service Component | AWS Configuration Details | AWS Subtotal | Azure Configuration Details | Azure Subtotal | Monthly Variance (Azure vs. AWS) |

| :--- | :--- | :--- | :--- | :--- | :--- |

| \*\*Compute / Virtual Machines\*\* | 2x `t3.large` Instances (Linux, On-Demand) + 2x 30 GB gp3 Volumes | \\$126.27 | 2x `D2as v5` Instances (Linux, Pay-as-You-Go) + 2x 32 GiB Standard SSDs (E4) | \\$130.36 | +\\$4.09 \*(Azure Higher)\* |

| \*\*Object Storage (100 GB)\*\* | S3 Standard Tier + 10k PUT + 100k GET | \\$2.39 | Block Blob Storage (GPv2, Hot Tier, LRS) + API Transactions | \\$2.22 | -\\$0.17 \*(Azure Lower)\* |

| \*\*Data Transfer / Bandwidth\*\* | Outbound Data Transfer to Public Internet (500 GB) | \\$45.00 | Public Internet Egress from East US Region (500 GB) | \\$32.00 | -\\$13.00 \*(Azure Lower)\* |

| \*\*Grand Totals\*\* | \*\*Baseline Application Profile\*\* | \*\*\\$173.66\*\* | \*\*Baseline Application Profile\*\* | \*\*\\$164.58\*\* | \*\*-\\$9.08 (5.23% Savings)\*\* |

| \*\*Annualized Cost\*\* | \*\*Projected 12-Month Run-Rate\*\* | \*\*\\$2,083.92\*\* | \*\*Projected 12-Month Run-Rate\*\* | \*\*\\$1,975.01\*\* | \*\*-\\$108.91 (Azure Wins)\*\* |



\---



\## 3. Deep-Dive Technical Layer Analysis



\### 3.1 Compute \& Local Block Storage Layer

\* \*\*AWS Implementation (`t3.large` + gp3):\*\* The AWS design leverages the `t3.large` instance class on the Nitro hypervisor platform. This instance operates on a burstable performance credit model, which requires ongoing architectural oversight to monitor CPU credit depletion under prolonged high-traffic conditions. The storage relies on the `gp3` Elastic Block Store framework, which cleanly decouples IOPS provision profiling from raw volume capacity sizing, pricing out at a combined \\$126.27 per month.

\* \*\*Azure Implementation (`D2as v5` + E4 Standard SSD):\*\* Azure utilizes the AMD EPYC™ 3rd Generation backed `D2as v5` instance platform. Unlike burstable models, this tier delivers dedicated, steady-state CPU capacity profiles without risk of performance throttling under sustained workload stress. Azure handles OS partitions via predefined disk tiers; mapping a 30 GB baseline requirement lands on the E4 standard SSD tier (32 GiB). This configuration introduces a minor cost premium (+\\$4.09), totaling \\$130.36 per month. However, it returns significant value in hardware stability and predictable production request handling.



\### 3.2 Object Storage Frameworks

\* \*\*AWS S3 Standard vs. Azure Blob Hot (LRS):\*\* Both object architectures operate with extreme operational parity. AWS S3 Standard calculates storage at \\$0.023/GB and applies direct API request multipliers. Azure Blob Storage (General Purpose v2) set to the \*\*Hot Access Tier\*\* with \*\*Locally Redundant Storage (LRS)\*\* evaluates at \\$0.021/GB for the structural data footprint. Transaction metrics are cleanly mirrored via Azure's standard operations multiplier syntax (inputting 1 unit of write operations and 10 units of read operations to scale against the baseline x10,000 platform denominator). The resulting subtotal establishes close financial parity (\\$2.39 on AWS versus \\$2.22 on Azure), highlighting minor unit-rate advantages in Azure’s base volume storage calculations.



\### 3.3 Network Architecture \& Egress Economics

\* \*\*The Definitive Differentiator:\*\* The core economic variance between these environment states rests entirely within the networking layer. 

\* \*\*The Internet Routing Mechanism:\*\* AWS evaluates raw outbound internet data transfer over a standalone baseline pricing card structure at \\$0.09 per GB, bringing 500 GB of data to a rigid \\$45.00 monthly baseline. Conversely, Microsoft Azure natively integrates a generous cloud routing optimization model: the first \*\*100 GB per month of outbound internet egress is granted entirely free of charge\*\* across all subscriptions. Consequently, Azure only bills for the remaining 400 GB of active routing at a standard regional unit rate of \\$0.08 per GB. This architectural nuance results in an immediate, localized monthly savings of \*\*\\$13.00\*\* for the application deployment.


### 3.4 Windows Server Slicing & Azure Hybrid Benefit (AHB) Economics
To satisfy multi-scenario requirements, an alternative analysis was conducted evaluating a Windows Server OS deployment for the compute tier instead of Linux:
* **Standard Windows Server Pay-as-You-Go Premium:** Deploying the two compute nodes with a standard Windows license natively injected by the cloud provider introduces a licensing surcharge. On AWS, this pushes the instance tier costs up significantly. On Azure, the standard Windows pay-as-you-go VM rate increases from $117.24/month to approximately $213.00/month.
* **The Azure Hybrid Benefit (AHB) Impact:** If evaluated through the lens of an enterprise possessing legacy on-premises Windows Server licenses with active Software Assurance (SA), AHB allows the organization to swap the licensing surcharge out completely. This drops the Azure VM cost back down to its base Linux rate ($117.24/month). This mechanism nullifies the cloud licensing penalty—an advantage that cannot be natively mirrored on AWS on-demand instances without transitioning to complex, high-overhead Dedicated Hosts.

### 3.5 Inter-Zone Data Transfer Architecture
Internal data replication patterns (e.g., state clustering across separate Availability Zones for high availability) incur specialized routing charges that differ heavily between ecosystems:
* **AWS Inter-Zone Pricing:** AWS charges a standard linear fee of $0.01 per GB for data transferred across Availability Zones (AZs) within the same region, applying the fee to both ingress and egress directions (meaning a 100 GB cross-AZ replication payload incurs $2.00 in total internal transport costs).
* **Azure Inter-Zone Pricing:** Microsoft Azure provides a massive structural advantage here: as of mid-2024, Microsoft made **Azure Availability Zone data transfer completely free of charge** for all standard data replication paths. This allows application tiers to scale across zone boundaries for high availability without generating hidden, variable internal data transportation line items.


\---



\## 4. Strategic Optimization Roadmap (Long-Term TCO)

To maximize financial efficiency as this application environment transitions from its initial deployment phase toward long-term production operations, the following advanced optimization paths should be pursued:



1\. \*\*Compute Reservation Commitment (RI / Savings Plans):\*\* Transitioning both the AWS `t3.large` and Azure `D2as v5` compute nodes from standard Pay-as-You-Go/On-Demand invoicing into a \*\*1-Year or 3-Year Reserved Instance Commitment\*\* or a Cloud Savings Plan will instantly reduce base compute costs by \*\*32% to 38%\*\*. This optimization shifts the total monthly run-rate down to near double-digit territory.

2\. \*\*Azure Hybrid Benefit (AHB Deployment):\*\* If the application architecture expands to encompass enterprise Windows Server partitions or MSSQL databases, leveraging existing on-premises software licenses via Azure Hybrid Benefit will yield up to a 40% discount over standard public cloud licensing rates—an optimization unmatched on the AWS side.

3\. \*\*Edge Caching Integration (CDN Topologies):\*\* Introducing Amazon CloudFront or Azure Front Door/Content Delivery Network resources directly ahead of the presentation layer will capture static traffic requests closer to user origins. This approach scales down raw back-end internet egress fees by converting expensive VM-to-Internet routing into cheaper, high-speed edge distribution data streams.



\---



\## 5. Architectural Recommendation

While both cloud providers demonstrate world-class reliability and sub-millisecond physical layer execution, \*\*Microsoft Azure is the recommended platform for this specific application architecture\*\*. 



Azure achieves a lower overall baseline TCO (\\$164.58 vs. \\$173.66) while providing structurally superior, non-burstable compute instances (`D2as v5` dedicated hardware vs. `t3.large` credit-constrained configurations). This ensures higher operational stability under production load, paired with lower transactional network overhead costs.



\---



\## 6. Verification Links \& Repository Artifacts

\* \*\*AWS Baseline Active Estimate:\*\* \[Interactive AWS Calculator Summary URL](https://calculator.aws/#/estimate?id=a04c6a74ce6c916b909f4d471e0fbe63e7cbb97c)

\* \*\*Azure Baseline Active Estimate:\*\* \[Interactive Azure Calculator Summary URL](https://azure.com/e/3502308a1cc4400fa86112fcac4ee563)

\* \*\*Visual Audit Assets:\*\* Stored locally within the repository workspace environment under:

&#x20; \* `/screenshots/aws-summary-matrix.png`

&#x20; \* `/screenshots/azure-summary-matrix.png`

