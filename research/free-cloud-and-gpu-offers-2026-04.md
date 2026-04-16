# BOINC-suitable free cloud and compute offers (filtered 2026-04 shortlist)

Research date: 2026-04-16
Source note: `Projects/BOINC free compute shortlist.md` in Obsidian

## Filter rules

- Removed entries that were explicitly marked `Not suitable`, `Poor fit`, `Weak BOINC fit`, or otherwise incompatible with persistent BOINC service/container hosting.
- Removed entries that generally require a startup, company, marketplace publisher, ISV path, or other legal-entity application flow.
- Kept self-serve individual offers, plus student/research lanes that can be accessed without forming a company.

## Filtered table

| Offer | Access lane | Amount | Compute estimate | BOINC fit / caveats |
| --- | --- | --- | --- | --- |
| [Oracle Cloud Always Free Arm A1](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm) | Self-serve individual | 3,000 OCPU-hr/month + 18,000 GB-hr/month, up to 4 OCPU / 24 GB | ≈ 4 Arm cores 24/7; baseline always-on Linux host | Verified fit: native BOINC as a Linux service is practical; BOINC in Docker on Linux is also plausible. Not a practical Windows path on the free offer. |
| [Oracle Cloud Always Free AMD micro](https://www.oracle.com/free) | Self-serve individual | 2 AMD VMs at 1/8 OCPU + 1 GB each | ≈ 0.25 OCPU 24/7 total; tiny always-on Linux capacity | Verified fit for very small Linux BOINC service installs; Docker is possible but cramped. Not a practical Windows path on the free offer. |
| [Google Cloud free trial](https://cloud.google.com/free/docs/free-cloud-features) | Self-serve individual | $300 / 90 days | Credit-based burst capacity; runtime depends on chosen VM shape | Verified fit: credits can fund BOINC on Linux VMs, Linux containers, and Windows VMs. Windows/container use is credit-dependent rather than effectively free. |
| [Google Cloud Always Free e2-micro](https://cloud.google.com/free/docs/free-cloud-features) | Self-serve individual | 1 non-preemptible e2-micro VM/month in selected US regions | ≈ 1 always-on tiny shared-core VM; ≈ 730 wall-hr/month | Verified fit for a very small native Linux BOINC service; Docker is possible but marginal on this size. No practical free Windows BOINC path here. |
| [AWS free plan / credits](https://aws.amazon.com/free/activate-your-free-tier-account/) | Self-serve individual | Up to $200 credits + free plan up to 6 months + always-free services | Credit-based; enough for testing, but exact runtime depends on instance pricing | Verified fit: BOINC can run on Linux VMs, Linux containers, and Windows VMs if you spend credits that way. Windows is possible, but not a clean forever-free path. |
| [Azure free account](https://azure.microsoft.com/en-us/free/virtual-machines) | Self-serve individual | $200 / 30 days + 12-month free services + always-free services | Credit-based plus limited burstable VM allowance | Verified fit: Linux BOINC service/container is practical while credits or free VM allowance last. Windows BOINC is possible if you spend credits there, but not a clean free-tier lane. |
| [DigitalOcean trial](https://try.digitalocean.com/freetrialoffer/) | Self-serve individual | $200 / 60 days | Credit-based Linux VM time; exact runtime depends on Droplet choice | Verified fit for Linux BOINC service or Docker while credits last. No strong public Windows BOINC path in this offer. |
| [IBM Cloud free / Lite](https://www.ibm.com/cloud/free) | Self-serve individual | $200 / 30 days + Lite plans | Trial capacity is credit-based; Lite is mostly managed services, not steady VM compute | Limited fit: BOINC is only sensible if you spend trial credits on general compute. Lite plans are not a BOINC host. |
| [Alibaba Cloud free offers](https://www.alibabacloud.com/free) | Self-serve individual | Product-specific freebies such as ECS t5 1C/1G for 1 year | Small Linux VM capacity where the offer applies | Verified fit for lightweight Linux BOINC service usage on eligible ECS offers; Windows suitability is offer-specific and not the main free path. |
| [Akash Console trial](https://akash.network/docs/getting-started/quick-start) | Self-serve individual | $100 free credits for 30 days | Credit-based decentralized-cloud capacity; trial deployments capped at 24 hours | Verified fit mainly for Linux containerized BOINC experiments while credits last; not a practical Windows path, and 24-hour trial limits are a real constraint. |
| [Azure for Students](https://learn.microsoft.com/en-us/azure/education-hub/about-azure-for-students) | Student status, no company required | $100 Azure credits, valid for one year, renewable yearly while eligible, no credit card required | Credit-based VM/runtime budget | Verified fit: credits can fund BOINC on Linux VMs/containers and potentially Windows VMs, but practical runtime depends on chosen SKUs. |
| [AWS Cloud Credit for Research](https://aws.amazon.com/government-education/research-and-technical-computing/cloud-credit-for-research/) | Research status, no company required | Up to $5k for students; higher for faculty/staff depending on project | Research credit pool for standard AWS compute | Strong BOINC fit on Linux VMs/containers; Windows also possible if credits are allocated there. |
| [Google Cloud research credits](https://edu.google.com/programs/credits/research/) | Research status, no company required | Research credits for faculty, PhDs, postdocs, and eligible nonprofits | Research credit pool for standard GCP compute | Strong BOINC fit on Linux VMs/containers and possible Windows VMs, subject to credit budget. |
| [Nebius Research Credits](https://www.nebius.com/nebius-research-credits-program) | Research status, no company required | Up to 8 GPUs for a full year and up to 10M inference tokens | Large GPU-heavy research allocation | Strong BOINC fit for Linux-based raw compute if the awarded resources expose standard host control. Windows is not the primary path. |

## Removed from this filtered view

- Offers that are not suitable for BOINC hosting: Cloud Shell, Cloudflare Workers, Render, Railway, Vercel, Netlify, Fly.io, Modal Starter, Hugging Face ZeroGPU, Paperspace free notebooks, Fireworks AI, Replicate, Baseten workspace credits, GitHub Education, Colab, and Kaggle.
- Offers that generally require a legal entity or company/program approval path: Google for Startups, AWS Activate, Microsoft for Startups, Microsoft Investor Offer, Microsoft ISV Success, NVIDIA Inception, Nebius for Startups, Together AI Startup Accelerator, Runpod Startup Program, Vast.ai Startup Program, Baseten Startup Program, Modal startup grants, and Crusoe credits.
