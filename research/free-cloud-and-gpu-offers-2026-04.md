# Free cloud and GPU offers in 2026: forever-free tiers, trial credits, and practical routes

Research date: 2026-04-16
Last verified against the listed source pages: 2026-04-16

## Scope

This note focuses on public cloud and neo-cloud offerings that are useful for real CPU or GPU work, not just marketing freebies.

In particular, it covers:

- forever-free or no-expiry monthly quotas
- self-serve new-user credits and trials
- selective startup, student, and research programs that materially change the economics
- GPU-specific caveats, because many “free” offers break down the moment you need accelerators

I prioritized official pricing, free-tier, and program pages. Where vendor docs were inconsistent, I called that out.

This is a point-in-time research snapshot, not a promise that the listed offers will remain unchanged.

### Methodology and exclusions

Included:

- mainstream public clouds
- popular developer/serverless platforms
- GPU-focused neo-clouds and AI compute platforms
- student, startup, and research programs that materially change cloud economics

Excluded or only mentioned briefly:

- providers with no meaningful public free tier or no clear public credit program
- purely reseller/marketplace offers where the free component was unclear or not publicly documented
- broad low-cost clouds that are attractive on price but not actually free in any material sense

## Executive summary

### Best options by use case

- Best forever-free raw VM offer: Oracle Cloud Always Free
- Best general new-user credit on a hyperscaler: Google Cloud ($300 / 90 days)
- Best “cheap forever” edge/serverless stack: Cloudflare Workers + R2 + Workers AI free quotas
- Best recurring free GPU access for individual experimentation: Modal, Hugging Face ZeroGPU, Paperspace Free notebooks
- Best startup-credit lane for serious AI companies: Google for Startups, Microsoft for Startups Investor Offer, AWS Activate Portfolio, Nebius for Startups, Together AI Startup Accelerator
- Best student stack: GitHub Education + Azure for Students + Colab/Kaggle
- Best research lane: AWS Cloud Credit for Research, Google Cloud research credits, Nebius Research Credits

### The two big truths

1. “Forever free” almost never means free GPUs.
   The strongest forever-free offers are CPU, storage, serverless, or managed-service quotas. True self-serve forever-free GPU is rare and usually comes as queued notebooks or managed inference, not always-on GPU VMs.

2. Status beats signup.
   Students, funded startups, researchers, accelerator-backed teams, and companies publishing through marketplaces get access to much larger and more durable subsidies than ordinary new-user signups.

## Recommendations if CPU and GPU matter most

### For an individual hacker

1. Oracle Cloud Always Free for baseline VM and egress
2. Google Cloud free trial for bursts and product testing
3. Modal Starter for recurring GPU/serverless compute
4. Hugging Face ZeroGPU for demos and short inference jobs
5. Paperspace free notebooks if notebook-style workflows are acceptable

### For a small startup

1. Apply for Google for Startups immediately
2. If you have investor/accelerator ties, pursue Microsoft Investor Offer and AWS Activate Portfolio in parallel
3. Use Nebius / Together / Runpod / Vast / Baseten selectively for AI-heavy credit programs
4. Preserve your biggest credits by offloading prototyping to ZeroGPU, Colab, or Paperspace free notebooks

### For students or academic labs

1. GitHub Education first
2. Azure for Students next
3. Colab and Kaggle for bursty notebook GPU access
4. Apply for AWS / Google / Nebius research credits for heavier projects

## 1) Public cloud and mainstream platform offers

### High-signal comparison

| Provider | Offer type | What is actually free | GPU angle | Important catches | Official sources |
| --- | --- | --- | --- | --- | --- |
| Oracle Cloud | $300 / 30 days + Always Free forever | Always Free includes AMD micro instances, Arm Ampere A1 capacity, block/object/archive storage, load balancer, databases, and 10 TB/mo outbound transfer | No Always Free GPU, but OCI has a broad paid GPU catalog | One account per person; card required; idle accounts can be suspended; capacity can be scarce; home-region placement matters | https://www.oracle.com/free ; https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm |
| Google Cloud | $300 / 90 days + no-expiry Free Tier | 1 e2-micro VM in specific US regions, 30 GB disk, selected product quotas | Trial explicitly blocks attaching GPUs until billing is upgraded | Card required; trial cannot be paused; projects/resources stop if you do not upgrade before expiry | https://cloud.google.com/free/docs/free-cloud-features |
| AWS | Up to $200 credits + free plan up to 6 months + 30+ always-free services | New 2025+ model is credit/plan-based, not the old simple 12-month micro-VM story | Official GPU instances exist but are not free-tier items | Valid payment method required; free plan expires; account can close after expiry; old blog posts about AWS free tier are often outdated | https://aws.amazon.com/free/activate-your-free-tier-account/ ; https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/free-tier-FAQ.html |
| Azure | $200 / 30 days + 12-month free services + always-free services | Free account includes burstable VM hours plus many service quotas | Official N-series GPU exists, but not as a free tier | Must move to pay-as-you-go to continue; card verification; docs currently show SKU inconsistency for the Intel free VM line item | https://azure.microsoft.com/en-us/free/virtual-machines |
| DigitalOcean | $200 / 60 days | Trial credit can be used on Droplets, storage, load balancers, managed services | No meaningful free GPU path surfaced | Credit card required; overages are billed; no forever-free tier | https://try.digitalocean.com/freetrialoffer/ |
| IBM Cloud | $200 / 30 days + Lite plans | Lite is good for managed services/APIs, not strong forever-free raw VM compute | Paid GPU offerings exist, plus occasional promotions, but no real free GPU tier | “Always free” does not mean always-free VM compute; trial requires moving through IBM billing workflow | https://www.ibm.com/cloud/free |
| Alibaba Cloud | Product-specific free offers rather than one clean universal credit | Example public offers include ECS t5 1C/1G for 1 year and other per-product freebies | Official GPU service exists, but I did not find a broad self-serve free GPU lane | Product and region restrictions are heavier than GCP/Azure/OCI; verification/payment friction is common | https://www.alibabacloud.com/free |
| Cloudflare | Forever-free edge/serverless/storage/AI quotas | Workers free tier, R2 free storage/ops, Workers AI daily free inference quota | No raw GPU VMs; Workers AI is managed GPU-backed inference | Great for edge and APIs, not general VM workloads | https://developers.cloudflare.com/workers/platform/pricing/ ; https://developers.cloudflare.com/r2/pricing/ ; https://developers.cloudflare.com/workers-ai/platform/pricing/ |
| Render | Forever-free hobby services | Free web service, free static hosting, limited workspace hours | No GPU offering in public pricing | Free services sleep after idle periods; free Postgres is time-limited; tiny CPU allocation | https://render.com/free ; https://www.render.com/pricing |
| Railway | $5 trial + $1/mo free plan | Small recurring credit and limited app compute | No GPU in public pricing | “Limited trial” can restrict networking/ports unless GitHub verification passes; tiny footprint | https://docs.railway.com/pricing/free-trial ; https://docs.railway.com/pricing/plans |
| Vercel | Forever-free hobby plan | Free function invocations, CPU-hours, memory-hours, bandwidth | No GPU in public pricing | Hobby is personal/non-commercial; no extra usage purchase on hobby | https://vercel.com/docs/accounts/plans/hobby ; https://vercel.com/pricing |
| Netlify | Forever-free credit budget | 300 credits/month across compute/bandwidth/request metering | No GPU in public pricing | Pricing docs recently changed; free budget is small and metered across multiple dimensions | https://www.netlify.com/pricing/?category=developer ; https://www.netlify.com/changelog/2026-04-14-pricing-updates-april-2026/ |
| Fly.io | Barely a trial now | 2 total VM hours or 7 days | GPU offering is being deprecated away | Not a serious long-term free option in 2026 | https://www.fly.io/docs/about/free-trial/ ; https://www.fly.io/docs/pricing/ |

### Public cloud notes that matter in practice

#### Oracle Cloud Infrastructure

OCI is still the strongest pure forever-free infrastructure offer if you want real VMs instead of just serverless.

What stands out:

- $300 free trial credits for 30 days
- Always Free services with no stated end date
- useful baseline compute/storage/networking
- up to 10 TB/month outbound transfer on Always Free

What to watch:

- Oracle explicitly limits free accounts to one per person
- idle accounts can be suspended after long inactivity
- many users hit capacity scarcity, especially on popular Always Free shapes
- the free offer is best if you can live within your home region and keep the tenancy active

#### Google Cloud

Google gives the cleanest mainstream self-serve trial for serious experimentation.

Why it is strong:

- $300 over 90 days
- no automatic charges during the trial
- no-expiry Free Tier still exists after trial expiration

Critical limitation:

- Google explicitly blocks GPU attachment on free-trial VM instances until you upgrade billing

That means GCP is excellent for CPU, storage, and managed-service testing, but not a real free-GPU path.

#### AWS

AWS changed meaningfully after mid-2025. A lot of online guides are stale.

The current mental model should be:

- up to $200 credits
- free plan up to 6 months
- separate always-free services
- later transition to a paid plan if you want full access and continuity

The trap:

- many engineers still assume “12 months of a tiny EC2 instance” is the whole story
- in 2026, the offer is more gated, more credit-driven, and easier to misunderstand

#### Azure

Azure is generous enough to matter, but its documentation is messy.

Good parts:

- $200 / 30 days
- 12-month VM allowance on selected burstable SKUs
- many always-free services

Practical warning:

- Microsoft’s public pages currently disagree on one of the free VM SKU names, so treat exact SKU marketing copy carefully and re-check before publishing hard requirements around it
- if you do not move to pay-as-you-go, the free-account experience stops after the credit/30-day gate

#### Cloudflare

Cloudflare is not a VM cloud, but it is one of the strongest “forever free” platforms if your workload is edge APIs, object storage, or AI inference rather than Linux boxes.

Best uses:

- API endpoints
- edge compute
- static + object storage
- lightweight AI inference through Workers AI

Bad fit:

- full Linux environment
- long-running jobs
- raw GPU training

## 2) GPU-first neo-clouds and AI platforms

### Best recurring offers for individuals

| Provider | Offer | What is really free | Major catches | Official sources |
| --- | --- | --- | --- | --- |
| Modal | Starter includes $30/mo free compute; Team includes $100/mo free compute | Real recurring monthly serverless compute budget usable across CPU/GPU/serverless workloads | Modal billing docs say a payment method must be on file to use the platform; Starter has 10 GPU concurrency and other plan limits | https://modal.com/pricing ; https://modal.com/docs/guide/billing |
| Hugging Face ZeroGPU | Free shared H200-backed ZeroGPU usage; free monthly inference credits for Inference Providers | Great for demos and short GPU-backed app workloads; free users also get $0.10/mo inference-provider credit | Hosting your own ZeroGPU Space requires PRO on personal accounts or Team/Enterprise for orgs; queues and daily quotas are real; this is not a guaranteed dedicated GPU | https://huggingface.co/docs/hub/spaces-zerogpu ; https://huggingface.co/docs/inference-providers/pricing |
| Paperspace | Free CPU and free GPU notebook machines in private workspaces | Good notebook-style GPU access for learning and experimentation | Free machines are notebook-only, not general-purpose free VMs; service limits can require support/verification | https://docs.paperspace.com/products/paperspace/pricing/ ; https://docs.paperspace.com/products/paperspace/accounts-and-teams/ |

### Best self-serve trial offers for GPU-ish experimentation

| Provider | Offer | Useful for | Major catches | Official sources |
| --- | --- | --- | --- | --- |
| Akash Console | $100 free credits for 30 days | Quick one-click deployments and decentralized-cloud experimentation | Trial deployments last only up to 24 hours; card verification required; some GPU deployments can stall or take longer due to demand | https://akash.network/docs/getting-started/quick-start |
| Fireworks AI | New users get free credits (current docs frame it as $1) | API-based inference testing | Extremely small credit; without payment method account is heavily limited and can be suspended after credit is exhausted | https://docs.fireworks.ai/faq-new/billing-pricing/how-much-does-fireworks-cost ; https://docs.fireworks.ai/faq-new/billing-pricing/what-happens-when-i-finish-my-1-dollar-credit |
| Replicate | Limited “try for free” runs on selected models | Quick model evals without infra setup | This is model-run sampling, not general GPU rental; after freebies, billing is required | https://replicate.com/collections/try-for-free ; https://replicate.com/docs/topics/billing |
| Baseten | New workspaces receive free credits (current public amount not cleanly pinned; older public messaging cited $30) | Inference, model serving, some early experimentation | Public docs confirm credits but the current public amount is not cleanly pinned; models deactivate if credits end and no payment method is added | https://docs.baseten.co/observability/usage ; https://www.baseten.co/changelog/usage-based-pricing-with-free-credits/ |

### Selective but very valuable GPU/startup programs

| Provider | Offer | Best fit | Main catches | Official sources |
| --- | --- | --- | --- | --- |
| Nebius for Startups | $5,000 introductory credits + up to $100,000 in compute savings | Serious AI startups moving toward production | Selective, startup-focused, not an open recurring free tier | https://www.nebius.com/startup-program |
| Together AI Startup Accelerator | Up to $15k / $30k / $50k depending on stage | AI startups using inference, fine-tuning, or GPU clusters | Selection-based; credits do not apply to Reserved GPU Clusters | https://www.together.ai/startup-accelerator |
| Runpod Startup Program | Starter: $1,000 free credits; Growth: commit $50k and get $25k bonus | Venture-backed AI startups | Selective; one-time, not recurring; venture backing strongly preferred | https://www.runpod.io/startup-credits |
| Vast.ai Startup Program | Up to 2,500 free compute hours | AI startups willing to work with a marketplace-style GPU platform | Selective; standard Vast usage still has verification, spend throttles, interruptibility, and ongoing storage costs | https://vast.ai/startup |
| Baseten Startup Program | Up to $25k for dedicated inference/training + up to $2.5k for model APIs | AI-native startups serving models | Seed-to-Series A, AI-first, new customers only | https://www.baseten.co/startup-program/ |
| Modal grants | Up to $25k startup credits and up to $10k academic credits | Teams already building on serverless GPU primitives | Still tied to Modal’s platform and billing model | https://modal.com/startups |
| Crusoe | Up to $100k credits | Larger, better-funded AI companies training at scale | Very selective; credits are tied to specific workload profiles and eligibility criteria | https://crusoe.ai/savings |

### Notable non-offers or weak offers

These matter because they are often assumed to be free when they mostly are not:

- Lambda: no meaningful self-serve public free tier; credits are case-by-case and currently capacity constrained
- CoreWeave: no real self-serve public free tier for ordinary users
- TensorDock: effectively prepaid, not free
- CUDO Compute: billing account and positive balance required before serious usage
- Salad Container Engine: public pricing says no SCE free trial

## 3) Ecosystem routes that beat ordinary free tiers

This is where most of the real leverage is.

### Students

| Program | Value | Why it matters | Main catches | Official sources |
| --- | --- | --- | --- | --- |
| GitHub Education | 180 Codespaces hours/month, 3,000 Actions minutes/month, plus Student Developer Pack partner offers | Strong base for development workflows; often the first free compute a student should claim | Requires student verification; partner offers change over time | https://github.com/education/students ; https://education.github.com/pack/offers |
| Azure for Students | $100 Azure credits, valid for one year, renewable yearly while eligible, no credit card required | One of the best student-friendly cloud offers because it renews | Degree-granting institution and academic verification required; one subscription per eligible student | https://learn.microsoft.com/en-us/azure/education-hub/about-azure-for-students |
| Colab / Colab Pro for Education | Free notebook GPU/TPU access; Pro for Education for eligible users | Useful for teaching, experimentation, and bursty notebook work | Resources fluctuate, free notebooks cap runtime, not suitable for guaranteed production compute | https://research.google.com/colaboratory/faq.html |
| Kaggle | Free notebook accelerators including GPU/TPU access | Good complement to Colab for bursty experiments | Session quotas and anti-abuse limits apply; not a general-purpose cloud VM | https://www.kaggle.com/docs |

### Startups

| Program | Public value | Best use | Main catches | Official sources |
| --- | --- | --- | --- | --- |
| Google for Startups Cloud Program | Start: up to $2,000; Scale: Year 1 up to $100k, Year 2 20% coverage up to another $100k; AI-first startups can reach up to $350k total | Strongest public startup credit lane for many AI startups | Business email must match public domain; Marketplace items are excluded; funding and prior-credit thresholds matter | https://cloud.google.com/startup/benefits ; https://cloud.google.com/startup/faq |
| AWS Activate | Founders: $1,000; Portfolio: up to $100k | Strong if you have an Org ID from an Activate Provider | Requires paid-tier AWS account; provider-backed path is where the big value is | https://aws.amazon.com/startups/credits |
| Microsoft for Startups | Public startup path: $1k immediately, then up to $5k with verification | Easy first Microsoft lane for new startups | Auto-converts to pay-as-you-go after credits expire; Marketplace products excluded | https://learn.microsoft.com/en-us/azure/signups/overview |
| Microsoft Investor Offer | Most approved startups start around $100k Azure credits, with some able to reach $150k | Very strong if you are in the right investor / accelerator network | Requires referral path and approval; not the same as the public $5k path | https://learn.microsoft.com/en-us/startups/benefits |
| Microsoft ISV Success | Core $5k Azure sponsorship for 12 months; Expanded path can reach $25k and more | Underused path for B2B SaaS companies publishing to Microsoft Marketplace | Built for software vendors intending to publish to Marketplace, not every startup | https://learn.microsoft.com/en-us/partner-center/membership/isv-success |
| NVIDIA Inception | Partner pricing, credits, and discounts rather than one universal fixed credit table | Strong meta-program for AI startups | Benefits are partner- and program-path dependent, not as transparent as a single cloud credit grant | https://www.nvidia.com/en-us/startups/ |

### Researchers and academic labs

| Program | Value | Best fit | Main catches | Official sources |
| --- | --- | --- | --- | --- |
| AWS Cloud Credit for Research | Up to $5k for students; higher for faculty/staff depending on project | Finite research projects with strong proposal framing | Long review cycle; project-based, not permanent lab funding | https://aws.amazon.com/government-education/research-and-technical-computing/cloud-credit-for-research/ |
| Google Cloud research credits | Research credits for faculty, PhDs, postdocs and eligible nonprofit institutions | Projects that can justify a serious proposal and cost estimate | Competitive, proposal-driven, credits expire after redemption | https://edu.google.com/programs/credits/research/ ; https://cloud.google.com/edu/researchers |
| Nebius Research Credits | Up to 8 GPUs for a full year and up to 10M inference tokens | GPU-heavy academic research | Monthly windows, competitive selection, non-commercial requirement | https://www.nebius.com/nebius-research-credits-program |

## 4) Practical tricks that actually work

### 1. Use status-based programs before burning universal trials

The best mistake to avoid is spending your one-time universal credits before you know which startup/student/research programs you qualify for.

Examples:

- GitHub Education before paying for cloud IDEs or CI minutes
- Azure for Students before using personal Azure trial capacity
- Google for Startups before wasting GCP trial credits on throwaway experiments
- AWS Activate Portfolio before defaulting to the small self-funded package
- Microsoft Investor Offer before settling for the public $5k startup lane

### 2. Preserve expensive credits by offloading prototyping to queue-based GPU platforms

A good pattern is:

- use Colab / Kaggle / ZeroGPU / Paperspace free notebooks for prototyping
- reserve GCP / AWS / Azure / Nebius / Together / Runpod credits for stable workloads that need repeatability

This matters because “free trial” money disappears fast once you run real GPU jobs.

### 3. Treat “free GPU” as one of three very different things

Most confusion comes from mixing these up:

1. Free notebook GPU
   - example: Colab, Kaggle, Paperspace free notebooks
2. Free managed inference credit
   - example: Hugging Face Inference Providers monthly credit, Workers AI daily quota
3. Free or subsidized raw GPU compute
   - example: Modal monthly budget, startup programs, research grants

Only the third category behaves anything like a real GPU cloud budget.

### 4. The biggest lever is often investor or accelerator affiliation

If you have any connection to:

- YC or another accelerator
- a VC fund
- a university incubator
- a cloud partner network
- an NVIDIA or Microsoft partner ecosystem

then ask directly for:

- AWS Activate Org ID
- Microsoft Investor referral code
- Google for Startups referral/support path
- partner perks for observability, databases, and AI tooling

That often multiplies the value of your cloud plan more than any self-serve signup does.

### 5. Use partner perks to save compute credits for compute

If a startup bundle also includes:

- monitoring
- CI/CD
- data tooling
- workspace software
- maps / comms / collaboration

then use those freebies first, so your actual cloud credits can be spent on CPU and GPU rather than support tooling.

## 5) Common traps and gotchas

### Credit-card and payment-method traps

A surprising number of “free” offers still require a real payment method:

- Oracle Cloud: card required, no prepaid/virtual cards
- Google Cloud: card or payment verification required
- AWS: valid payment method required even for free plan
- Azure: card verification for standard free account
- DigitalOcean: valid card required
- Modal: payment method required to use Modal according to billing docs
- Akash: card verification with temporary $1 hold

### Region and capacity traps

- Google’s e2-micro free VM is region-limited
- Oracle Always Free capacity is often scarce in popular regions
- ZeroGPU queue times rise when demand spikes, especially for larger allocations
- Akash GPU availability depends on marketplace supply and template/provider choice

### Auto-convert or hard-stop traps

- AWS free plan expires and can close the account if not upgraded in time
- Azure startup/public credits convert to pay-as-you-go after their window ends
- Google trial resources stop if you do not upgrade
- DigitalOcean bills overages during the trial if you exceed the allowance
- Baseten can deactivate models if credits expire without payment method

### “Free” but not production-grade traps

- Render free services sleep
- Vercel Hobby is personal / non-commercial
- Railway free plan is tiny and can have networking restrictions
- ZeroGPU, Colab, and Kaggle have queueing, runtime caps, or anti-abuse controls
- Paperspace free machines are notebook-only, not equivalent to always-on instances

### Stale-doc traps observed during this research

These are worth remembering because they can break quick comparisons:

- Azure public docs currently show a mismatch around one of the 12-month free VM SKUs
- AWS free-tier explainers written before the 2025 changes are often wrong
- Netlify’s current pricing update landed in a changelog/blog before every pricing page reflected it cleanly
- Runpod has multiple public startup pages with slightly different framing
- Salad has docs that still say “free trial” in some places while pricing says no SCE free trial

## 6) Bottom line

If you care about both CPU and GPU and want the best realistic stack today:

### Best baseline stack for a solo builder

- Oracle Cloud Always Free for baseline VMs
- Google Cloud trial for broader experimentation
- Modal Starter for recurring GPU/serverless budget
- Hugging Face ZeroGPU and Inference Providers for demos and API testing
- Paperspace free notebooks for notebook-centric workflows

### Best baseline stack for a startup

- Google for Startups first
- AWS Activate and Microsoft programs second
- Nebius / Together / Runpod / Vast / Baseten when AI workload shape fits
- Colab / ZeroGPU / Paperspace for prototype burn reduction

### Best baseline stack for students and researchers

- GitHub Education + Azure for Students first
- Colab and Kaggle for everyday notebook workloads
- AWS / Google / Nebius research programs for heavier projects

## Source list

These pages move frequently. Re-verify before signing up or budgeting against any offer.

### Public clouds and platforms

- Oracle Cloud Free Tier: https://www.oracle.com/free
- Oracle Always Free resources: https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm
- Google Cloud Free Program: https://cloud.google.com/free/docs/free-cloud-features
- Azure free VMs / free account: https://azure.microsoft.com/en-us/free/virtual-machines
- AWS Free Tier: https://aws.amazon.com/free/activate-your-free-tier-account/
- AWS Free Tier FAQ: https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/free-tier-FAQ.html
- DigitalOcean free trial: https://try.digitalocean.com/freetrialoffer/
- IBM Cloud free: https://www.ibm.com/cloud/free
- Alibaba Cloud free offers: https://www.alibabacloud.com/free
- Cloudflare Workers pricing: https://developers.cloudflare.com/workers/platform/pricing/
- Cloudflare R2 pricing: https://developers.cloudflare.com/r2/pricing/
- Cloudflare Workers AI pricing: https://developers.cloudflare.com/workers-ai/platform/pricing/
- Render free tier: https://render.com/free
- Railway pricing: https://docs.railway.com/pricing/free-trial and https://docs.railway.com/pricing/plans
- Vercel hobby plan: https://vercel.com/docs/accounts/plans/hobby
- Netlify pricing: https://www.netlify.com/pricing/?category=developer
- Netlify pricing update: https://www.netlify.com/changelog/2026-04-14-pricing-updates-april-2026/
- Fly.io free trial: https://www.fly.io/docs/about/free-trial/

### GPU / AI platforms

- Modal pricing: https://modal.com/pricing
- Modal billing: https://modal.com/docs/guide/billing
- Modal startups and academic grants: https://modal.com/startups
- Hugging Face ZeroGPU: https://huggingface.co/docs/hub/spaces-zerogpu
- Hugging Face Inference Providers pricing: https://huggingface.co/docs/inference-providers/pricing
- Paperspace pricing: https://docs.paperspace.com/products/paperspace/pricing/
- Paperspace accounts/limits: https://docs.paperspace.com/products/paperspace/accounts-and-teams/
- Akash trial quick start: https://akash.network/docs/getting-started/quick-start
- Fireworks pricing/credits: https://docs.fireworks.ai/faq-new/billing-pricing/how-much-does-fireworks-cost and https://docs.fireworks.ai/faq-new/billing-pricing/what-happens-when-i-finish-my-1-dollar-credit
- Replicate try-for-free: https://replicate.com/collections/try-for-free
- Replicate billing: https://replicate.com/docs/topics/billing
- Baseten usage/free credits: https://docs.baseten.co/observability/usage
- Baseten credit announcement: https://www.baseten.co/changelog/usage-based-pricing-with-free-credits/
- Runpod startup credits: https://www.runpod.io/startup-credits
- Runpod referrals: https://docs.runpod.io/get-started/referrals
- Vast startup program: https://vast.ai/startup
- Together Startup Accelerator: https://www.together.ai/startup-accelerator
- Nebius for Startups: https://www.nebius.com/startup-program
- Nebius Research Credits: https://www.nebius.com/nebius-research-credits-program
- Crusoe savings/startup page: https://crusoe.ai/savings

### Student, startup, and research programs

- GitHub Education students: https://github.com/education/students
- GitHub Student Developer Pack: https://education.github.com/pack/offers
- Azure for Students: https://learn.microsoft.com/en-us/azure/education-hub/about-azure-for-students
- Google for Startups benefits: https://cloud.google.com/startup/benefits
- Google for Startups FAQ: https://cloud.google.com/startup/faq
- AWS Activate credits: https://aws.amazon.com/startups/credits
- Microsoft startup offer: https://learn.microsoft.com/en-us/azure/signups/overview
- Microsoft Investor Offer benefits: https://learn.microsoft.com/en-us/startups/benefits
- Microsoft ISV Success: https://learn.microsoft.com/en-us/partner-center/membership/isv-success
- NVIDIA Inception: https://www.nvidia.com/en-us/startups/
- Google Colab FAQ: https://research.google.com/colaboratory/faq.html
- Kaggle docs: https://www.kaggle.com/docs
- AWS Cloud Credit for Research: https://aws.amazon.com/government-education/research-and-technical-computing/cloud-credit-for-research/
- Google research credits: https://edu.google.com/programs/credits/research/ and https://cloud.google.com/edu/researchers
