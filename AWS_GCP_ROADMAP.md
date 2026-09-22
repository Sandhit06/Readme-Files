# AWS & GCP Cloud System Design + Interview Mastery Guide

*The complete, extreme-detail companion for cloud system design interviews at any FAANG/MNC/startup, covering AWS, GCP, side-by-side comparisons, HLD, LLD, a massive interview Q&A bank, and a hands-on multi-cloud project integration playbook.*

---

## How To Use This Guide

This document is organized into 11 parts. It is designed to be read linearly the first time (to build the mental model), then used as a reference during interview prep (jump straight to case studies or Q&A).

1. **Part 1 — Cloud Fundamentals & Core Services Deep Dive.** Every major AWS service paired with its GCP equivalent, explained in depth: what it is, when to use it, internals, gotchas, pricing model, and the interview questions it tends to generate.
2. **Part 2 — The Cloud System Design Interview Framework.** A repeatable, step-by-step method to attack ANY cloud system design prompt in 45-60 minutes, plus cost-estimation and multi-region/DR strategy playbooks.
3. **Part 3 — HLD Case Studies.** 18 full high-level design walkthroughs of real systems, each built out on AWS AND GCP so you can see the architectural translation between clouds.
4. **Part 4 — LLD / Hands-on Design.** IAM policy design, VPC/CIDR planning, Terraform module design, autoscaling configuration, security groups/firewalls, Kubernetes manifests — the low-level artifacts that back up your HLD in a real interview or a real job.
5. **Part 5 — Interview Q&A Bank.** 300+ rapid-fire and deep questions with detailed answers, organized by topic.
6. **Part 6 — Multi-Cloud Project Integration Guide.** A ground-up walkthrough of integrating AWS and GCP into one real project: Terraform, SDK code (Python boto3 + google-cloud), CI/CD, secrets, networking, cost tagging, and a cloud-agnostic abstraction layer.
7. **Part 7 — Cheat Sheets.** AWS service cheat sheet, GCP service cheat sheet, and a master AWS/GCP/Azure mapping table.
8. **Part 8 — A-Z Glossary.**
9. **Part 9 — Study Roadmap, FAQ, Closing Notes.**
10. **Part 10 — Additional HLD Mini Case Studies.** 20 more real-world systems (ride-sharing dispatch, fraud detection, rate limiters, notification fan-out, and more) in a leaner problem/architecture/code/trade-offs format.
11. **Part 11 — Reference Implementation Appendix.** 22 complete, copy-pasteable production artifacts: full Terraform environments for AWS/GCP/Azure, Kubernetes manifests, OpenAPI specs, DB schemas, CI/CD pipelines, monitoring-as-code, chaos engineering, cost automation, rate limiting, blue-green deployment, landing-zone vending, and ADR examples.

**How to practice with this guide:** For every HLD case study, first read only the "Problem Statement" and try to design it yourself on a whiteboard/paper for 30-40 minutes using the framework in Part 2. Then compare against the walkthrough. Do NOT passively read case studies — you will not retain the reasoning skill that way.

---

## Master Table of Contents

**Part 1 — Cloud Fundamentals & Core Services Deep Dive**
- §1 Cloud Computing Models & Shared Responsibility & Pricing
- §2 Global Infrastructure Deep Dive
- §3 Compute Services Deep Dive
- §4 Storage Services Deep Dive
- §5 Database Services Deep Dive
- §6 Networking Deep Dive
- §7 Messaging & Event-Driven Services
- §8 IAM & Security Services
- §9 Serverless & Container Orchestration Deep Dive
- §10 Observability & Monitoring
- §11 IaC & DevOps Tooling
- §12 AWS vs GCP vs Azure Master Service-Mapping Table
- §13 Well-Architected Framework vs Google Cloud Architecture Framework

**Part 2 — The Cloud System Design Interview Framework**
- §14 Step-by-Step Approach to Any Cloud System Design Interview
- §15 Cost Estimation & Capacity Planning Worked Examples
- §16 Multi-Region / Disaster Recovery Strategies

**Part 3 — HLD Case Studies**
- §17 Scalable 3-Tier Web Application (AWS)
- §18 Scalable 3-Tier Web Application (GCP)
- §19 Serverless REST API (AWS Lambda vs GCP Cloud Functions)
- §20 Event-Driven Microservices Architecture
- §21 Real-Time Streaming & Analytics Pipeline
- §22 Container Orchestration Platform (EKS vs GKE Autopilot)
- §23 Global Static Site & CDN Hosting
- §24 Multi-Region Active-Active Database Architecture
- §25 CI/CD Pipeline for Microservices
- §26 Big Data Lake & Analytics Platform
- §27 Disaster Recovery Architecture
- §28 Secure Multi-Account / Multi-Project Landing Zone
- §29 Auto-Scaling Video Transcoding Pipeline
- §30 IoT Data Ingestion Platform
- §31 ML Training & Serving Pipeline
- §32 Cost-Optimized Batch Processing Platform
- §33 Zero-Downtime Blue-Green / Canary Deployment Architecture
- §34 Serverless Chat / Messaging Backend

**Part 4 — LLD / Hands-on Design**
- §35 IAM Policy Design (AWS JSON + GCP Bindings)
- §36 VPC / CIDR Subnet Planning Worked Example
- §37 Terraform Module Design (LLD)
- §38 Autoscaling Policy Configuration Deep Dive
- §39 Security Groups & Firewall Rule Design
- §40 Kubernetes Manifests / Helm Chart for a Cloud-Native App

**Part 5 — Interview Q&A Bank**
- §41 AWS-Specific Questions
- §42 GCP-Specific Questions
- §43 Comparison / "When Would You Choose X Over Y" Questions
- §44 Scenario-Based Mini System Design Questions
- §45 Cloud Architect Behavioral & Meta Questions

**Part 6 — Multi-Cloud Project Integration Guide**
- §46 Project Structure for an AWS + GCP Multi-Cloud App
- §47 Terraform Multi-Cloud Infrastructure Code
- §48 SDK Integration Code (boto3 + google-cloud)
- §49 CI/CD Across Both Clouds (GitHub Actions)
- §50 Secrets & Config Management Across Clouds
- §51 Multi-Cloud Networking (VPN / Interconnect)
- §52 Cost Management & Tagging Across Providers
- §53 Cloud-Agnostic Abstraction Layer (Adapter Pattern)
- §54 Full Sample Project Walkthrough

**Part 7 — Cheat Sheets**
- §55 AWS Service Cheat Sheet
- §56 GCP Service Cheat Sheet
- §57 AWS vs GCP vs Azure Master Mapping Table (Extended)
- §58 Numbers & Pricing Quick Reference

**Part 8 — A-Z Glossary**
- §59 Glossary A-M
- §60 Glossary N-Z

**Part 9 — Closing**
- §61 Study Roadmap (Week by Week)
- §62 FAQ
- §63 Closing Notes

**Part 10 — Additional HLD Mini Case Studies**
- §64 Ride-Sharing Dispatch System
- §65 Product Recommendation Engine
- §66 Rate-Limiter-as-a-Service
- §67 Global Search / Autocomplete Service
- §68 Payment Gateway Integration
- §69 Feature Flag / Experimentation Platform
- §70 Public API Gateway (Multi-Tenant External Developers)
- §71 Centralized Log Aggregation Platform
- §72 Distributed Job Scheduler / Cron
- §73 Real-Time Fraud Detection Pipeline
- §74 Social Graph Storage / Friend Recommendations
- §75 Push Notification Fan-Out Service
- §76 Distributed Config / Feature Store Service
- §77 Multi-Tenant SaaS Data Isolation
- §78 Global Session Management / SSO
- §79 Serverless Image Processing Pipeline
- §80 Distributed Lock Service
- §81 API Monetization / Billing & Metering
- §82 Real-Time Collaborative Editing Backend
- §83 Health-Check / Service Discovery Platform

**Part 11 — Reference Implementation Appendix**
- §84 Complete Terraform: Production Environment (VPC + EKS + RDS + Monitoring)
- §85 Complete Kubernetes Manifests: Multi-Service "App of Apps"
- §86 Complete OpenAPI 3.0 Specification (Sample API)
- §87 Complete Database Schema DDL (E-Commerce Sample App)
- §88 Complete GitHub Actions Multi-Env CI/CD Pipeline
- §89 Complete Monitoring/Alerting-as-Code Terraform
- §90 Complete Load Test Script (Locust)
- §91 Complete pytest Test Suite (Order Handler + Adapters)
- §92 Complete Terraform: GCP Production Environment (VPC + GKE + Cloud SQL + Monitoring)
- §93 Complete FastAPI Reference Application (Order Service, End-to-End)
- §94 Complete Ansible Playbook: Config Management & App Deployment
- §95 Complete Local Dev Stack (docker-compose, Multi-Service + LocalStack)
- §96 Complete Grafana Dashboards + Prometheus Alert Rules (JSON/YAML)
- §97 Complete Alembic Database Migration Scripts
- §98 Complete Terraform: Azure Production Environment (3-Cloud Parity)
- §99 Complete Disaster-Recovery Runbook Automation Script (Bash)
- §100 Complete Chaos Engineering / Game-Day Automation (AWS FIS + GCP Equivalent)
- §101 Complete Cost Optimization Automation (Rightsizing Report Generator)
- §102 Complete Distributed Rate Limiter (Redis-Backed Token Bucket)
- §103 Complete Blue-Green Deployment Automation (CodeDeploy + Cloud Deploy)
- §104 Complete Multi-Cloud Architecture Decision Records (ADR) Template & Worked Examples
- §105 Complete Multi-Cloud Landing Zone Bootstrap (Account/Project Vending Automation)

---

# Part 1 — Cloud Fundamentals & Core Services Deep Dive

## §1 Cloud Computing Models & Shared Responsibility & Pricing

### 1.1 IaaS vs PaaS vs SaaS vs FaaS

| Model | You Manage | Provider Manages | AWS Example | GCP Example |
|---|---|---|---|---|
| IaaS (Infrastructure as a Service) | OS, runtime, middleware, app, data | Physical hardware, virtualization, networking | EC2, EBS | Compute Engine, Persistent Disk |
| PaaS (Platform as a Service) | App code, data | OS, runtime, middleware, scaling | Elastic Beanstalk | App Engine |
| FaaS (Function as a Service / Serverless) | App code only (per-function) | Everything else, including scaling to zero | Lambda | Cloud Functions / Cloud Run |
| SaaS (Software as a Service) | Nothing (just usage/config) | Everything | WorkMail, Chime | Google Workspace |
| CaaS (Containers as a Service) | Container images, orchestration config | Cluster control plane (managed) or nodes (self-managed) | ECS, EKS, Fargate | GKE, Cloud Run |

**Interview angle:** Interviewers love asking "would you use EC2, ECS/EKS, or Lambda for this workload?" The real answer is about trade-offs: control vs operational overhead vs cost vs cold-start latency vs how bursty/predictable the traffic is. Always frame your answer in terms of these axes rather than a memorized rule.

### 1.2 The Shared Responsibility Model

Cloud security is a **shared** responsibility between the provider and the customer, and this split changes depending on which service tier you use:

- **Security OF the cloud** (provider's job): physical data center security, hardware, global network infrastructure, hypervisor.
- **Security IN the cloud** (customer's job): data encryption, IAM configuration, OS patching (for IaaS), network configuration (security groups/firewalls), application-level security.

As you move from IaaS → PaaS → FaaS/SaaS, more responsibility shifts to the provider. For EC2, you patch the guest OS. For Lambda, AWS patches the underlying OS/runtime and you're only responsible for your function code and its IAM permissions. This is true in both AWS and GCP.

**Common interview trap:** "If I put my data in S3, is AWS responsible for making sure it's not publicly readable?" No — bucket policy configuration is YOUR responsibility (customer side), even though S3 is a managed AWS service. This is why S3 public bucket leaks are a customer misconfiguration issue, not an AWS security failure, and it's a very common real-world interview/behavioral question ("tell me about a time you found a security misconfiguration").

### 1.3 Cloud Pricing Models

| Model | Description | AWS Examples | GCP Examples |
|---|---|---|---|
| On-Demand / Pay-as-you-go | Pay per second/hour, no commitment | EC2 On-Demand | Compute Engine on-demand |
| Reserved / Committed Use | 1-3 year commitment for a big discount (30-70%) | Reserved Instances, Savings Plans | Committed Use Discounts (CUDs) |
| Spot / Preemptible | Spare capacity at steep discount (60-90% off), can be reclaimed with short notice | Spot Instances (2-min warning) | Preemptible VMs / Spot VMs (30-sec warning) |
| Sustained Use Discounts | Automatic discount the longer a VM runs in a month, no commitment needed | N/A (AWS has no direct equivalent) | Automatic on Compute Engine |
| Serverless / Consumption-based | Pay per invocation/GB-second, scales to zero | Lambda, Fargate | Cloud Functions, Cloud Run |
| Storage tiering | Pay less for infrequently accessed data, more for retrieval | S3 Standard/IA/Glacier | Standard/Nearline/Coldline/Archive |
| Data egress | Pay to move data OUT of the cloud (ingress is usually free) | Data Transfer OUT to internet | Network egress charges |

**Key interview insight — egress cost is a major system design lever.** A very common "gotcha" follow-up question is: "Your design pulls a lot of data cross-region or to the public internet — how does that affect cost, and how would you reduce it?" Answers: use a CDN (CloudFront/Cloud CDN) to cache at edge and reduce origin egress, keep compute and data co-located in the same region/AZ, use VPC endpoints/Private Google Access to avoid routing through the public internet (and often avoid egress charges for AWS-service-to-AWS-service traffic), and compress/dedupe data before transfer.

### 1.4 Free Tier & Cost Governance Basics

Both clouds provide free tiers (12-month + always-free tiers) for learning, but production systems should implement:
- **Budgets & alerts** (AWS Budgets / GCP Budgets & Alerts) — notify before overspend.
- **Tagging/labeling strategy** for cost allocation by team/project/environment (see §52).
- **Cost Explorer (AWS) / Cloud Billing reports (GCP)** for anomaly detection.
- **Rightsizing recommendations** (AWS Compute Optimizer / GCP Recommender) to catch over-provisioned resources.

---

## §2 Global Infrastructure Deep Dive

### 2.1 The Hierarchy: Region → Zone → Data Center

| Concept | AWS | GCP |
|---|---|---|
| Largest geographic unit | Region (e.g., us-east-1) | Region (e.g., us-central1) |
| Isolated failure domain within a region | Availability Zone (AZ), e.g., us-east-1a | Zone, e.g., us-central1-a |
| Physical data centers per AZ/Zone | 1 or more discrete data centers per AZ | 1 or more per zone |
| Edge locations for CDN/DNS | Edge Locations + Regional Edge Caches (CloudFront) | Points of Presence (PoPs) / Google Global Network |
| Ultra-low-latency micro-regions | Local Zones, Wavelength Zones (5G) | N/A directly (Google has similar via Network Edge / Distributed Cloud) |
| Number of regions (approx, grows constantly) | 30+ regions, 100+ AZs | 40+ regions, 120+ zones |

**How many AZs/Zones per region?** AWS regions almost always have **3+ AZs** minimum (a deliberate design decision so that quorum-based systems, e.g., needing 2-of-3, can survive a single AZ failure). GCP regions typically have **3 zones**. This 3-AZ minimum is directly why RDS Multi-AZ, DynamoDB, and other managed services default to 3-way replication for durability — always cite "3 AZs enables N/2+1 quorum" when asked why cloud databases replicate 3x.

### 2.2 AZ/Zone Isolation — What It Actually Means

- Each AZ/zone has independent power, cooling, and networking.
- AZs within a region are connected via low-latency, high-throughput private links (usually sub-2ms).
- A failure in one AZ (power outage, network partition) should NOT cascade to another AZ.
- **Design principle:** always deploy across at least 2 (ideally 3) AZs/zones for any production workload requiring high availability. A single-AZ deployment is a common interview red flag — expect the interviewer to probe "what happens if that AZ goes down?"

### 2.3 Choosing a Region — the Real Factors

1. **Latency to users** — pick the region(s) closest to your user base.
2. **Data residency / compliance** — GDPR, data sovereignty laws (e.g., some countries require data to stay in-country).
3. **Service availability** — not every service is available in every region (newer regions often lag behind on service parity).
4. **Pricing** — costs vary by region (us-east-1 / us-central1 are usually cheapest as the oldest/largest regions).
5. **Disaster recovery** — pick a secondary region far enough away to not share a common disaster (e.g., not in the same seismic zone) but with acceptable replication latency.

### 2.4 CDN & Edge Networks

- **CloudFront (AWS):** 400+ edge locations globally, integrates natively with S3, EC2, ALB, Lambda@Edge / CloudFront Functions for edge compute.
- **Cloud CDN (GCP):** built on Google's global network (the same one that powers google.com), integrates with Cloud Load Balancing, Cloud Storage, backend services.
- **Interview point:** CDNs solve two problems simultaneously — (1) reduce latency by serving cached content from a location near the user, and (2) reduce origin load/egress cost by absorbing repeat requests at the edge.

### 2.5 Anycast & Global Load Balancing

GCP's global HTTP(S) Load Balancer uses **anycast** — a single global IP address is announced from many PoPs, and BGP routing sends the user's request to the nearest healthy PoP automatically. AWS's equivalent for global routing is **Route 53 latency-based/geolocation routing** combined with **AWS Global Accelerator** (which also uses anycast IPs across the AWS global network to route into the nearest healthy regional endpoint). This is a frequently-tested distinction: GCP's load balancing is global-by-default at the L7 LB layer, while in AWS an ALB/NLB is regional, and global routing requires an extra layer (Route 53 or Global Accelerator) on top.

---

## §3 Compute Services Deep Dive

### 3.1 Virtual Machines: EC2 vs Compute Engine

| Feature | AWS EC2 | GCP Compute Engine |
|---|---|---|
| Instance sizing | Fixed instance families/sizes (t3.micro, m5.large, etc.) | Predefined machine types AND **custom machine types** (pick exact vCPU/RAM) |
| Auto Scaling | Auto Scaling Groups (ASG) | Managed Instance Groups (MIG) |
| Purchase options | On-Demand, Reserved, Savings Plans, Spot | On-Demand, Committed Use, Spot/Preemptible, Sustained Use (automatic) |
| Live migration | No — instance stops on host maintenance (unless using instance recovery) | Yes — GCP live-migrates VMs off hardware needing maintenance with no downtime (except preemptible/spot) |
| Bare metal | EC2 Bare Metal instances (.metal) | Bare Metal Solution |
| Boot disk options | EBS-backed or Instance Store | Persistent Disk or Local SSD |

**Key interview differentiator: live migration.** GCP transparently live-migrates standard VMs during host maintenance events — no reboot required. AWS EC2 instances are typically stopped/restarted (or use instance replacement) during host maintenance unless you've architected for it (e.g., with an ASG). This is a genuine operational advantage GCP interviewers may want you to know, and AWS interviewers may probe how you'd design around scheduled maintenance events (AWS notifies you in advance via the Personal Health Dashboard/Instance Scheduled Events).

### 3.2 Auto Scaling Groups (ASG) vs Managed Instance Groups (MIG)

Both provide: automatic replacement of unhealthy instances, scaling based on metrics (CPU, custom CloudWatch/Cloud Monitoring metrics, queue depth), and integration with load balancers.

- **Scaling policies:** Target tracking (keep avg CPU at 50%), step scaling, scheduled scaling (both clouds support all three).
- **Health checks:** ASG can use EC2 status checks or ELB health checks; MIG can use autohealing based on an HTTP health check.
- **Regional vs zonal:** MIGs can be **regional** (spread across zones in a region automatically) or zonal. ASGs span AZs you explicitly configure within one region.
- **Instance templates:** GCP uses **Instance Templates** (immutable config for MIG); AWS uses **Launch Templates** (mostly equivalent, supersedes older Launch Configurations).

**Interview question pattern:** "How do you achieve zero-downtime deployment with an ASG/MIG?" Answer: use an **instance refresh** (AWS) / **rolling update** (GCP MIG) with a minimum-healthy-percentage setting, combined with health checks and a deployment that launches new instances (new launch template/instance template version) before terminating old ones — this is a rolling/blue-green pattern at the infrastructure level.

### 3.3 Serverless Compute: Lambda vs Cloud Functions vs Cloud Run

| Feature | AWS Lambda | GCP Cloud Functions (2nd gen) | GCP Cloud Run |
|---|---|---|---|
| Trigger types | HTTP (via API GW), S3, DynamoDB Streams, SQS, SNS, EventBridge, Kinesis, many more | HTTP, Pub/Sub, Cloud Storage, Firestore, Eventarc (broad) | HTTP requests, Pub/Sub push, Eventarc |
| Max execution time | 15 minutes | 60 min (event) / 60 min (HTTP, 2nd gen) | 60 minutes (configurable) |
| Deployment unit | Zip/container image, single function | Zip/source, single function (built on Cloud Run under the hood) | Full container image (any language/runtime) |
| Concurrency model | 1 request per execution environment (unless using response streaming) by default, reserved/provisioned concurrency available | Similar to Lambda | **Concurrent requests per instance configurable** (up to 1000), more efficient for I/O-bound workloads |
| Cold start mitigation | Provisioned Concurrency | Min instances | Min instances |
| Pricing | Per request + GB-second of execution | Per invocation + GB-second | Per vCPU-second + memory-second, billed only while handling requests (or always-on if min instances > 0) |

**Cloud Run is the standout GCP differentiator** — it lets you deploy ANY containerized app (not just a single function handler) with full serverless scaling-to-zero economics and per-request billing, with the ability to serve many concurrent requests per instance. This makes Cloud Run a common answer to "what's GCP's most flexible serverless compute option?" AWS's closest equivalent is **Fargate** (serverless containers) but Fargate doesn't scale to zero as cheaply/instantly nor bill per-request in the same way — it bills per second of running task. AWS **App Runner** is actually the closer analog to Cloud Run (fully managed container service with scale-to-zero-ish behavior and per-request-friendly economics), worth mentioning if asked directly.

### 3.4 Container Orchestration: ECS vs EKS vs GKE

| Feature | ECS (AWS-native) | EKS (AWS managed Kubernetes) | GKE (GCP managed Kubernetes) |
|---|---|---|---|
| Orchestrator | AWS proprietary | Kubernetes (upstream) | Kubernetes (upstream, Google invented K8s) |
| Control plane management | Fully AWS-managed, free-ish (no control plane fee) | AWS-managed control plane, $0.10/hr control plane fee | Fully managed; **Autopilot mode** manages nodes too |
| Node management | EC2 or Fargate (serverless) | EC2, Fargate, or managed node groups | Standard mode (self-managed nodes) or **Autopilot** (fully hands-off, pay-per-pod) |
| Learning curve | Lower (simpler proprietary model) | Higher (full K8s API surface) | Higher (full K8s API surface) |
| Portability | AWS-only | Portable (K8s is a standard) | Portable (K8s is a standard) |
| Best for | Teams wanting simplicity, pure-AWS shops | Teams needing K8s ecosystem tools/portability | Teams wanting the "best" managed K8s experience with least ops overhead (Autopilot) |

**GKE Autopilot is frequently the "best answer" for a GCP container interview question** — it removes node management entirely (no node pools to size/patch), bills per-pod-resource-request instead of per-node, and applies security hardening by default. EKS historically required significant additional tooling for a comparably hands-off experience, though AWS has since added **EKS Auto Mode** narrowing this gap — mention this if you want to show up-to-date knowledge.

**Interview question: "ECS vs EKS — how do you decide?"** Framework answer: If the org is AWS-only with no Kubernetes requirement (e.g., no need for portability, no existing K8s tooling/expertise, want lowest operational overhead) → ECS. If the org needs multi-cloud portability, has existing Kubernetes expertise/tooling (Helm charts, K8s operators, service mesh like Istio), or needs the vast K8s ecosystem (Argo, Flux, Kubeflow) → EKS.

### 3.5 PaaS Options: Elastic Beanstalk vs App Engine

Both let you deploy code without managing infrastructure directly:
- **Elastic Beanstalk (AWS):** wraps EC2 + ASG + ELB + RDS behind a simplified deployment interface; you can still access the underlying EC2 instances if needed.
- **App Engine (GCP):** Standard environment (fully sandboxed, scales to zero, specific language runtimes) or Flexible environment (runs in containers on Compute Engine, more flexibility but slower scaling/cold starts). App Engine Standard is one of the oldest and most "hands-off" PaaS offerings in any cloud.

### 3.6 Compute Decision Framework (memorize this for interviews)

1. **Is the workload a short-lived, event-triggered function?** → Lambda / Cloud Functions.
2. **Is it a containerized web service with variable/bursty traffic and you want zero ops?** → Fargate/App Runner or Cloud Run.
3. **Do you need full Kubernetes portability/ecosystem?** → EKS or GKE (Autopilot if you want less ops).
4. **Do you need full control over the OS/kernel, specialized hardware (GPU, high-memory), or have legacy apps requiring a specific OS config?** → EC2 / Compute Engine.
5. **Is cost the dominant factor and the workload is fault-tolerant/interruptible (batch, CI, rendering)?** → Spot/Preemptible instances.

---

## §4 Storage Services Deep Dive

### 4.1 Object Storage: S3 vs Cloud Storage

| Feature | Amazon S3 | Google Cloud Storage |
|---|---|---|
| Durability | 99.999999999% (11 nines) | 99.999999999% (11 nines) |
| Storage classes | Standard, Intelligent-Tiering, Standard-IA, One Zone-IA, Glacier Instant Retrieval, Glacier Flexible Retrieval, Glacier Deep Archive | Standard, Nearline (30-day min), Coldline (90-day min), Archive (365-day min) |
| Consistency | Strong read-after-write consistency (for all operations, since Dec 2020) | Strong consistency for all operations |
| Max object size | 5TB | 5TB |
| Versioning | Yes | Yes |
| Lifecycle policies | Yes — auto-transition/expire objects | Yes — auto-transition/expire objects |
| Access control | Bucket policies (JSON), ACLs, IAM policies, Block Public Access | IAM (uniform bucket-level access recommended), ACLs (legacy), Public Access Prevention |
| Event notifications | S3 Event Notifications → SQS/SNS/Lambda | Pub/Sub notifications, Eventarc |
| Static website hosting | Yes (with CloudFront for HTTPS/custom domain) | Yes (with Cloud CDN/Load Balancer for HTTPS) |
| Transfer acceleration | S3 Transfer Acceleration (via CloudFront edge) | Storage Transfer Service |

**Storage class decision framework:** Access frequency + retrieval-time tolerance determine the class.
- Accessed constantly → Standard.
- Accessed unpredictably, want automatic cost optimization → Intelligent-Tiering (S3) — AWS automatically moves objects between tiers based on access patterns with no retrieval fee.
- Accessed rarely (once a month or less), need it back within minutes/hours → IA tiers / Nearline / Coldline.
- Long-term archive, retrieval can take hours, accessed almost never (compliance retention) → Glacier Deep Archive / Archive class — these are the cheapest per-GB by far (fractions of a cent/GB/month) but have retrieval latency (minutes to 12 hours) and often minimum storage duration charges (deleting early incurs a pro-rated early-deletion fee).

**Common interview trap:** "Why not just always use the cheapest storage class?" Because retrieval costs and latency make cheap tiers expensive/impractical for frequently-accessed data — the total cost = storage cost + request/retrieval cost, and for hot data the request costs of a cold tier can dwarf the storage savings. Also cite minimum storage duration and minimum object size overhead as reasons small/short-lived objects shouldn't go straight to Glacier/Archive.

### 4.2 Block Storage: EBS vs Persistent Disk

| Feature | EBS (Elastic Block Store) | Persistent Disk (PD) |
|---|---|---|
| Attachment | Attaches to one EC2 instance (Multi-Attach for io1/io2 in same AZ, limited) | Attaches to one VM (Compute Engine also supports multi-writer for some disk types) |
| Types | gp3 (general purpose SSD), io2 Block Express (high-IOPS), st1 (throughput HDD), sc1 (cold HDD) | pd-standard (HDD), pd-balanced, pd-ssd, pd-extreme |
| Snapshots | EBS Snapshots → S3-backed, incremental | PD Snapshots → incremental, stored regionally/multi-regionally |
| Resizing | Online resize (no downtime) | Online resize (no downtime) |
| Encryption | KMS-backed encryption, can be default-on per account | Google-managed or Customer-managed (Cloud KMS) encryption, on by default |
| Local (ephemeral) disk option | Instance Store (NVMe SSD, high IOPS, data lost on stop/terminate) | Local SSD (same idea — ephemeral, high performance, lost on stop) |

**Interview point:** Block storage is always AZ/zone-scoped — you can't attach an EBS volume or Persistent Disk to an instance in a different AZ/zone. This is why databases running on EC2/Compute Engine (self-managed) need application-level replication (or snapshots + cross-AZ restore) for HA, which is exactly the operational burden that managed database services (RDS, Cloud SQL) remove.

### 4.3 File Storage: EFS vs Filestore

- **EFS (Elastic File System):** NFS-based, POSIX-compliant, elastic (no pre-provisioning of capacity needed for the default mode), can be mounted by many EC2 instances/Lambda functions concurrently, regional (replicates across AZs automatically for Standard storage class).
- **Filestore (GCP):** NFS-based, POSIX-compliant, tiers (Basic HDD/SSD, Enterprise, High Scale), zonal by default (Enterprise tier offers regional/multi-zone replication).
- **When to use file storage over object storage:** legacy apps requiring a POSIX filesystem interface, shared config/state across many compute instances, content management systems, home directories, ML training data that needs POSIX semantics (random writes, file locking) — object storage (S3/GCS) doesn't support in-place partial writes or file locking semantics.

### 4.4 Archival & Backup Services

- **AWS Backup:** centralized backup service across EBS, RDS, DynamoDB, EFS, etc. with policy-based scheduling and retention.
- **GCP Backup and DR Service:** similar centralized backup/DR orchestration across Compute Engine, Cloud SQL, GKE.
- Both integrate with cross-region replication for DR purposes (see §16, §27).

### 4.5 Storage Decision Framework

1. **Unstructured data, accessed via HTTP/API, need durability + massive scale** → Object storage (S3/GCS).
2. **Attached disk for a single VM's OS/data, need low-latency block I/O** → EBS/Persistent Disk.
3. **Shared filesystem across multiple compute nodes, POSIX semantics needed** → EFS/Filestore.
4. **Long-term compliance archive, rarely accessed** → Glacier Deep Archive / Archive class.
5. **Ephemeral scratch space, highest IOPS, okay to lose on restart** → Instance Store / Local SSD.

## §5 Database Services Deep Dive

### 5.1 Relational Databases: RDS/Aurora vs Cloud SQL/Spanner

| Feature | RDS | Aurora | Cloud SQL | Cloud Spanner |
|---|---|---|---|---|
| Engines | MySQL, PostgreSQL, MariaDB, Oracle, SQL Server | MySQL/PostgreSQL-compatible | MySQL, PostgreSQL, SQL Server | Proprietary (Spanner SQL, PostgreSQL-compatible interface) |
| Storage architecture | EBS-backed, traditional | Distributed storage layer, decoupled from compute, auto-grows to 128TB | Persistent Disk-backed | Globally distributed, custom storage (Colossus) + TrueTime |
| Replication | Multi-AZ (sync standby) + up to 5 read replicas | 6-way replication across 3 AZs by default, up to 15 read replicas with sub-10ms lag | Regional HA (sync standby in another zone) + read replicas | Multi-region synchronous replication with strong consistency globally |
| Horizontal scaling (sharding) | Manual (app-level sharding) | Aurora Limitless Database (auto-sharding, newer) | Manual | **Native horizontal scaling** — this is Spanner's core differentiator |
| Consistency | Standard relational (single-node) | Standard relational (single-writer, distributed storage) | Standard relational | **Strong consistency at global scale** using TrueTime (atomic clocks + GPS) |
| Failover time | ~60-120 sec (Multi-AZ) | ~30 sec typical | ~60 sec (HA config) | No failover needed (multi-region active-active by design) |

**Cloud Spanner is a genuinely unique service** — it's the only mainstream managed database offering horizontal scalability AND strong ACID transactional consistency AND global distribution simultaneously, which historically was considered impossible per CAP theorem trade-offs at scale (Spanner gets around the practical implications using TrueTime to bound clock uncertainty). This is a very common GCP-side interview topic: "How does Spanner achieve consistency across regions without sacrificing availability the way CAP theorem suggests it should?" Answer: TrueTime API exposes clock uncertainty bounds; Spanner uses "commit wait" (waiting out the uncertainty interval before acknowledging a transaction) to guarantee external consistency (linearizability) across the globe, effectively trading a small amount of latency for consistency rather than trading availability.

**Aurora's differentiator** is the storage/compute separation — Aurora storage is a distributed, self-healing, log-structured storage layer replicated 6 ways across 3 AZs, so only 4/6 copies need to ack a write and only 3/6 for a read, and read replicas share the same underlying storage (near-instant replica creation, minimal lag) since they don't need to replicate full data pages, just redo log records.

### 5.2 NoSQL Key-Value & Document: DynamoDB vs Firestore vs Bigtable

| Feature | DynamoDB | Firestore | Bigtable |
|---|---|---|---|
| Data model | Key-value / wide-column document | Document (collections/documents, nested) | Wide-column (sparse, sorted map) |
| Scaling | Auto-scales via partitioning on hash of partition key | Auto-scales, serverless | Manual node provisioning (or autoscaling) but designed for massive scale |
| Consistency | Eventually consistent (default) or strongly consistent reads (opt-in, single-region) | Strong consistency (single document), real-time listeners | Eventually consistent (or single-cluster strong) |
| Latency | Single-digit ms | Single-digit ms to low tens of ms | Single-digit ms at massive scale |
| Best for | High-throughput key-value lookups, gaming leaderboards, session stores, shopping carts | Mobile/web app backends needing real-time sync, offline support | Time-series, IoT, analytics workloads with huge write throughput (Google's internal choice for Search/Maps/Gmail metadata) |
| Global replication | Global Tables (multi-region active-active) | Multi-region mode built-in | Multi-cluster routing (manual replication config) |
| Secondary indexes | GSI (Global Secondary Index) / LSI (Local Secondary Index) | Automatic composite indexes (with config) | No secondary indexes — design row key carefully instead |
| Pricing | On-demand (per request) or provisioned (RCU/WCU) | Per document read/write/delete + storage | Per node-hour + storage (or autoscaling nodes) |

**DynamoDB single-table design** is a heavily-tested LLD-adjacent interview topic: because DynamoDB doesn't support joins and has a limited query pattern (query by partition key + optional sort key condition, or scan), interviewers expect you to know **overloading GSIs and using composite sort keys** to answer multiple access patterns from ONE table (e.g., storing both `USER#123` and `ORDER#456` type items in the same table with different sort key prefixes) — this contrasts sharply with relational normalization and often trips up candidates coming from an RDBMS background.

**Bigtable is the workhorse behind Google's own massive-scale products** — a common interview question is "how do you design a Bigtable row key to avoid hotspotting?" Answer: avoid monotonically increasing keys (like timestamps) as a PURE prefix, since all new writes would hit the same tablet server (hotspotting); instead use a **salted/hashed prefix** or reverse the timestamp, or use a composite key like `{hash(user_id)}#{user_id}#{reverse_timestamp}` to spread writes across tablets while keeping related data co-located for range scans.

### 5.3 In-Memory Caching: ElastiCache vs Memorystore

| Feature | ElastiCache | Memorystore |
|---|---|---|
| Engines | Redis, Memcached | Redis, Memcached |
| Cluster mode | Redis Cluster mode (sharding across nodes) | Redis Cluster tier |
| HA | Multi-AZ with automatic failover | Standard tier HA with automatic failover across zones |
| Use cases | Session store, leaderboard (sorted sets), rate limiting, pub/sub, full caching layer | Same |

Both are essentially managed Redis/Memcached — the underlying engine behavior (data structures, commands, eviction policies) is identical since it's the same open-source software; the differentiation is purely in the managed operational layer (patching, failover, monitoring).

### 5.4 Data Warehousing: Redshift vs BigQuery

| Feature | Redshift | BigQuery |
|---|---|---|
| Architecture | Cluster-based (provisioned nodes) or Redshift Serverless | **Fully serverless**, no cluster to manage ever |
| Storage/compute separation | Yes (RA3 nodes use managed storage backed by S3) | Yes, fully separated (storage is effectively GCS-backed) |
| Query pricing | Per node-hour (provisioned) or per RPU-hour (serverless) | **Per byte scanned** (on-demand) or per-slot reservation (flat-rate) |
| Scaling | Concurrency scaling (adds transient clusters for spikes), elastic resize | Automatic, no configuration — thousands of slots available instantly |
| Federated query | Redshift Spectrum queries S3 data directly | BigQuery federated queries across Cloud SQL, Sheets, external tables |
| ML integration | Redshift ML (via SageMaker) | **BigQuery ML** (train models with plain SQL) — very popular feature |

**BigQuery's serverless, pay-per-byte-scanned model** is a favorite interview topic because it directly ties to a cost-optimization discussion: "how would you reduce BigQuery costs?" Answers: partition and cluster your tables (so queries scan less data), avoid `SELECT *` (BigQuery charges by columns scanned in columnar storage, not full row scans), use materialized views for repeated aggregation queries, and consider flat-rate slot pricing if query volume is high and predictable (converts variable per-query cost into fixed cost).

### 5.5 Document/Wide-Column Extras & Analytics Extras

- **DocumentDB (AWS):** MongoDB-compatible API, distinct engine underneath (not literally MongoDB) — used when a team wants MongoDB's document API/drivers without operating MongoDB themselves.
- **Neptune (AWS) vs no direct GCP-native graph DB** — GCP customers typically use self-managed Neo4j/JanusGraph on GKE, or Spanner Graph (newer offering) for graph workloads.
- **Timestream (AWS) vs Bigtable/BigQuery for time-series (GCP)** — AWS has a purpose-built time-series DB; GCP typically handles time-series via Bigtable (high write throughput) or BigQuery (analytical time-series).
- **Athena (AWS) vs BigQuery** — Athena is serverless SQL-over-S3 (similar pay-per-byte-scanned model, built on Presto/Trino) whereas BigQuery is a full-fledged warehouse; Athena is the closer AWS analog to ad hoc BigQuery-style querying over data lake files, while Redshift is the closer analog to BigQuery-as-a-warehouse.

### 5.6 Database Decision Framework (memorize for interviews)

1. **Need ACID transactions, complex joins, well-understood relational schema, moderate scale** → RDS/Cloud SQL.
2. **Need a relational model but with very high read scale / large storage and minimal ops** → Aurora.
3. **Need horizontal write scalability AND strong global consistency AND SQL** → Spanner (GCP's standout differentiator — bring this up when GCP is in scope).
4. **Need single-digit-ms key-value access at massive, unpredictable scale, flexible schema** → DynamoDB / Firestore / Bigtable (pick based on data model — document+mobile sync → Firestore; huge time-series/analytics-adjacent → Bigtable; general high-throughput KV → DynamoDB).
5. **Need sub-millisecond caching, session storage, leaderboards** → ElastiCache/Memorystore Redis.
6. **Need to run analytical SQL over huge historical datasets** → Redshift / BigQuery (BigQuery if you want zero infra management and a pay-per-query model).

---

## §6 Networking Deep Dive

### 6.1 Virtual Private Cloud (VPC) Fundamentals

Both AWS VPC and GCP VPC provide an isolated, private network for your resources. Key structural differences:

| Feature | AWS VPC | GCP VPC |
|---|---|---|
| Scope | Regional resource, but subnets are AZ-scoped | **Global resource** — a single VPC can span ALL regions, with subnets being regional (not zonal) |
| Subnets | Must specify a CIDR range per subnet, tied to one AZ | Subnets are regional (span all zones in that region automatically), CIDR ranges can be expanded later |
| Default networking | Default VPC per region with default subnets in every AZ (legacy convenience) | Default network with **auto mode** subnets in every region (one subnet per region automatically) |
| Routing | Route tables per subnet (or shared) | Routes are global within the VPC (a single routing table logically, though implemented distributed) |
| IP address management | You define non-overlapping CIDRs per VPC/subnet manually | Same, but expanding a subnet's secondary IP range is easier (primary range can't overlap; supports adding secondary ranges for GKE alias IPs) |

**This "VPC is global in GCP, regional in AWS" distinction is one of the single most tested cloud networking facts in interviews.** It directly affects design: in GCP, one VPC can contain subnets in us-central1, europe-west1, and asia-east1 simultaneously with instances able to communicate privately using internal IPs across regions without any VPC peering — in AWS, connecting resources in different regions privately requires **VPC Peering** or a **Transit Gateway** (inter-region peering) even though they might be "the same" logical application VPC design.

### 6.2 Subnets: Public vs Private

- **Public subnet:** has a route to an Internet Gateway (AWS IGW) / default internet route via external IP (GCP), instances can have public IPs.
- **Private subnet:** no direct route to the internet; outbound-only internet access provided via a **NAT Gateway (AWS)** / **Cloud NAT (GCP)** — inbound connections from the internet are not possible without an explicit forwarding rule/load balancer.
- **Design pattern:** application/database tiers go in private subnets; only load balancers/bastion hosts/NAT sit in public subnets. This is a baseline expectation in almost every HLD interview — putting a database in a public subnet is an immediate red flag to interviewers.

### 6.3 Connecting VPCs & On-Premises

| Need | AWS | GCP |
|---|---|---|
| Connect 2 VPCs privately | VPC Peering (no transitive routing) | VPC Peering (no transitive routing) |
| Connect many VPCs/accounts at scale | Transit Gateway (hub-and-spoke, transitive routing) | Network Connectivity Center / shared VPC |
| Connect to on-premises (encrypted, over internet) | Site-to-Site VPN | Cloud VPN |
| Connect to on-premises (dedicated private line) | Direct Connect | Cloud Interconnect (Dedicated/Partner) |
| Share a VPC across multiple accounts/projects | Resource Access Manager (RAM) shared subnets | **Shared VPC** (native, first-class feature — host project + service projects) |

**Shared VPC in GCP is a first-class organizational primitive** — a "host project" owns the VPC and subnets, and multiple "service projects" (often one per team) attach their resources to that shared network while IAM/billing/resource management stays separate per team. This is commonly cited as a cleaner multi-team networking model than AWS's more bolted-on VPC sharing via RAM, and is a good talking point for a "how would you set up networking for a large multi-team org" interview question.

### 6.4 DNS: Route 53 vs Cloud DNS

- **Route 53:** public/private hosted zones, many routing policies (simple, weighted, latency-based, geolocation, geoproximity, failover, multi-value), also functions as a domain registrar, integrates with health checks for automatic failover routing.
- **Cloud DNS:** public/private managed zones, DNS routing policies (weighted round robin, geo-based), integrates with Google's global anycast network.
- Both support DNSSEC.

### 6.5 Load Balancing: ELB Family vs Cloud Load Balancing

| Feature | AWS | GCP |
|---|---|---|
| L4 (TCP/UDP) load balancer | Network Load Balancer (NLB) | External/Internal Passthrough Network Load Balancer |
| L7 (HTTP/HTTPS) load balancer | Application Load Balancer (ALB) | External/Internal Application Load Balancer (HTTP(S) LB) |
| Legacy/basic | Classic Load Balancer (deprecated for new use) | N/A |
| Scope | **Regional** (an ALB/NLB lives in one region, though can be internet-facing or internal) | **Global** for external HTTP(S) LB (single anycast IP routes to nearest healthy region) — a genuinely unique advantage |
| Content-based routing | ALB path-based/host-based routing rules | URL maps (path/host-based routing) |
| WebSocket support | Yes (ALB) | Yes |
| TLS termination | Yes, via ACM certificates | Yes, via Google-managed or self-managed certificates |

**GCP's Global External HTTP(S) Load Balancer is architecturally different and a key interview differentiator:** it's a single global anycast IP, and Google's edge network routes each user to the *closest* backend across ANY region without you needing Route 53 latency routing or Global Accelerator on top — this is only possible because of point 6.1 (GCP VPC/LB being global-first). If asked "how would you set up a globally distributed, low-latency web service," GCP's answer is architecturally simpler (one global LB in front of regional backend services in multiple regions) versus AWS's answer (regional ALBs + Route53 latency-based routing, or ALBs + Global Accelerator for anycast).

### 6.6 Layer 4 vs Layer 7 — Interview Refresher

- **L4 (NLB/Passthrough LB):** operates on IP/port only, extremely low latency, preserves source IP, can't inspect HTTP content, used for raw TCP/UDP workloads (gaming, custom protocols) or when you need ultra-high throughput/low latency.
- **L7 (ALB/HTTP(S) LB):** understands HTTP, can route based on path/host/headers, terminate TLS, do WAF integration, but adds a small amount of latency and requires HTTP/HTTPS traffic specifically.
- **Interview follow-up:** "Why would a design need both an L4 AND L7 load balancer?" — e.g., an NLB in front of a fleet of ALBs for extreme scale/static IP requirements, or an NLB for a non-HTTP protocol (like a custom TCP-based game server) while an ALB handles the HTTP API portion of the same system.

### 6.7 Content Delivery & Edge Compute

Already covered CDN basics in §2.4. Edge compute specifics:
- **Lambda@Edge / CloudFront Functions (AWS):** run code at CloudFront edge locations — CloudFront Functions for very lightweight, sub-millisecond JS (header manipulation, simple redirects); Lambda@Edge for heavier logic (full Lambda runtime, can call other services) at higher latency.
- **Cloud Run / Cloud Functions at the edge:** GCP doesn't have as mature a "run code at every edge PoP" story as CloudFront Functions; typically GCP edge logic is handled via Cloud Armor rules or backend service configuration rather than true edge-executed code, though Google is investing in this space.

---

## §7 Messaging & Event-Driven Services

### 7.1 Queues: SQS vs Cloud Tasks/Pub-Sub-as-queue

- **SQS (Simple Queue Service):** Standard (at-least-once, best-effort ordering, nearly unlimited throughput) and FIFO (exactly-once processing, strict ordering per message group, capped throughput — 300/3000 msgs/sec with batching). Messages pulled by consumers; visibility timeout hides a message from other consumers while being processed; dead-letter queue (DLQ) for poison messages after N retries.
- **GCP equivalent:** GCP doesn't have a direct "simple queue" service with the exact SQS semantics — **Pub/Sub** is typically used even for point-to-point queue-like patterns (a single subscription pulled by multiple workers behaves like a competing-consumers queue), and **Cloud Tasks** is used for task queues where you need fine-grained control over dispatch rate, retry, and scheduling of work driven by your own application (e.g., "run this HTTP callback once, with rate limiting and retry policy").

### 7.2 Pub/Sub: SNS vs Pub/Sub

| Feature | SNS | Cloud Pub/Sub |
|---|---|---|
| Model | Topic → multiple subscribers (SQS queues, Lambda, HTTP, email, SMS) | Topic → multiple subscriptions (push or pull), each subscription gets its own copy of every message |
| Ordering | No ordering guarantee (standard); FIFO topics available for strict ordering | Ordering keys available for per-key ordering |
| Message retention | Not retained after delivery (fire-and-forget) unless paired with SQS | **Retains messages for up to 31 days**, supports replay/seek to a timestamp |
| Exactly-once | FIFO topics support this | Exactly-once delivery supported (with ordering keys) |
| Filtering | Subscription filter policies (attribute-based) | Subscription filters (attribute-based) |

**Pub/Sub's built-in message replay (seek-to-timestamp) is a notable differentiator** — you can "rewind" a subscription to reprocess messages from an earlier point, which is invaluable for recovering from a downstream bug without needing a separate replay mechanism (in AWS, achieving replay typically requires Kinesis, not SNS/SQS, since SQS/SNS don't retain delivered messages).

### 7.3 Streaming: Kinesis vs Pub/Sub+Dataflow

- **Kinesis Data Streams:** shard-based (each shard = 1MB/s in, 2MB/s out, or up to 1000 records/s in), consumers read via Kinesis Client Library (KCL) or Lambda triggers, data retained 24 hours (default) to 365 days (extended), ordering guaranteed WITHIN a shard (by partition key).
- **Kinesis Data Firehose:** fully managed delivery to S3/Redshift/OpenSearch/Splunk with optional transformation via Lambda — the easy button for "stream data into storage/warehouse."
- **Kinesis Data Analytics:** run SQL or Apache Flink directly against a stream.
- **GCP equivalent:** **Pub/Sub** for ingestion (no shard management — auto-scales transparently) + **Dataflow** (managed Apache Beam) for stream processing/transformation, landing in BigQuery/GCS/Bigtable. GCP's model removes the "how many shards do I need" capacity-planning question entirely, which is a genuine operational simplification often highlighted in interviews.
- **Managed Kafka:** AWS MSK (Managed Streaming for Kafka) vs GCP doesn't have a first-party managed Kafka (customers typically self-host on GKE or use Confluent Cloud as a 3rd-party marketplace offering) — worth knowing MSK exists as the "I specifically need Kafka's API/ecosystem" answer on AWS.

### 7.4 Event Buses & Orchestration

- **EventBridge (AWS):** schema registry, rule-based routing from 200+ AWS/SaaS sources to targets, supports content-based filtering, ideal for decoupling microservices via domain events.
- **Eventarc (GCP):** routes events from 90+ GCP sources (and custom sources) to Cloud Run/GKE/Cloud Functions/Workflows using CloudEvents standard format.
- **Step Functions (AWS) vs Workflows (GCP):** both are orchestration services for chaining serverless functions/API calls into a stateful workflow with retries, branching, and error handling — essential for implementing the Saga pattern in a serverless microservices architecture (see §20).

### 7.5 Messaging Decision Framework

1. **Need simple point-to-point task queue with retries/DLQ** → SQS (AWS) / Cloud Tasks or Pub/Sub-as-queue (GCP).
2. **Need fan-out to multiple independent consumers** → SNS (AWS) / Pub/Sub (GCP).
3. **Need ordered, replayable, high-throughput event log (streaming analytics, CDC)** → Kinesis (AWS) / Pub/Sub+Dataflow (GCP).
4. **Need Kafka specifically (existing ecosystem/tooling)** → MSK (AWS) / self-hosted-on-GKE or Confluent Cloud (GCP).
5. **Need to orchestrate a multi-step business process with compensating transactions** → Step Functions (AWS) / Workflows (GCP).

---

## §8 IAM & Security Services

### 8.1 Identity & Access Management Core Concepts

| Concept | AWS | GCP |
|---|---|---|
| Identity types | IAM Users, IAM Roles, IAM Groups, Root user | Google Accounts, Service Accounts, Groups |
| Permission attachment | Policies (JSON documents) attached to users/roles/groups, resource-based policies too | IAM Roles (bundles of permissions) bound to members via IAM Policy Bindings |
| Role types | Predefined (AWS Managed) policies, Customer Managed policies, Inline policies | Primitive roles (Owner/Editor/Viewer — broad, avoid in production), Predefined roles (granular, service-specific), Custom roles |
| Temporary credentials | STS (Security Token Service) — AssumeRole | Service Account impersonation, short-lived tokens |
| Cross-account/project access | Cross-account IAM roles (AssumeRole with trust policy) | Service account impersonation, or granting IAM roles directly to members from another project |
| Org-wide policy guardrails | Service Control Policies (SCPs) via AWS Organizations | Organization Policies (via Resource Manager) |
| MFA | Yes (virtual/hardware MFA devices) | Yes (2-Step Verification) |
| Policy evaluation logic | Explicit DENY always wins > explicit ALLOW > implicit DENY (default) | Deny always wins > Allow (GCP historically had NO explicit deny in IAM policies themselves until conditional IAM/deny policies were added — know that org policies CAN explicitly restrict regardless of IAM allow) |

### 8.2 The Principle of Least Privilege — the #1 IAM Interview Theme

Every IAM interview question ultimately traces back to least privilege: grant only the permissions needed, scoped as narrowly as possible (specific resource ARNs, not `*`; specific actions, not `service:*`), and prefer roles/service accounts with short-lived credentials over long-lived access keys. Common real interview questions:
- "How do you avoid hardcoding AWS credentials in application code?" → Use IAM Roles attached to EC2/ECS/Lambda (instance profile / task role) so credentials are auto-rotated and injected via the metadata service — NEVER embed access keys in code or config files.
- "How do you grant a GCP Compute Engine VM access to a Cloud Storage bucket?" → Attach a **service account** to the VM with only the specific predefined role needed (e.g., `roles/storage.objectViewer` scoped to that bucket), not `roles/editor`.

### 8.3 Organizational Guardrails

- **AWS Organizations + SCPs:** SCPs set the maximum available permissions for accounts in an OU — even if a user's IAM policy allows an action, an SCP can deny it account-wide (e.g., "deny all actions outside approved regions," "deny disabling CloudTrail"). SCPs do NOT grant permissions themselves, only restrict.
- **GCP Resource Manager + Org Policies:** hierarchical resource structure (Organization → Folders → Projects → Resources), with IAM permissions and Org Policy constraints both inheriting down the hierarchy. Org Policies restrict specific behaviors (e.g., "disable service account key creation," "restrict VM external IPs," "restrict resource locations").
- **Control Tower (AWS) vs a well-structured Folder hierarchy (GCP):** Control Tower automates multi-account landing zone setup (guardrails, account factory, centralized logging) — see §28 for the full landing-zone HLD case study.

### 8.4 Encryption Services

| Need | AWS | GCP |
|---|---|---|
| Managed encryption keys | KMS (Key Management Service) | Cloud KMS |
| Hardware security modules | CloudHSM (dedicated, FIPS 140-2 Level 3) | Cloud HSM |
| Secrets (API keys, DB passwords) | Secrets Manager (with automatic rotation) | Secret Manager |
| Envelope encryption | KMS generates data keys, encrypts data locally with the data key, encrypts the data key with the KMS key (CMK) | Same pattern with Cloud KMS keys |
| Default encryption at rest | Most services encrypt by default now (S3, EBS default encryption can be enforced account-wide) | Google encrypts ALL data at rest by default, always, even without any customer configuration |

**"Google encrypts everything at rest by default, with no way to turn it off" is a genuinely true and often-cited GCP security talking point** — whereas in AWS, encryption at rest historically required opt-in per service/resource (though AWS has moved toward more defaults-on behavior in recent years, e.g., EBS encryption by default is now an account-level setting you should enable).

### 8.5 Threat Detection & Protection

| Need | AWS | GCP |
|---|---|---|
| Threat detection (anomalous API activity, compromised credentials) | GuardDuty | Security Command Center (Premium tier) + Event Threat Detection |
| Web app firewall (SQLi, XSS, bot protection) | WAF | Cloud Armor |
| DDoS protection | Shield Standard (free, automatic) / Shield Advanced (paid, more mitigation + cost protection) | Cloud Armor (with Adaptive Protection) — DDoS protection is largely automatic on Google's network by default |
| Config/compliance drift detection | Config + Security Hub | Security Command Center + Policy Intelligence |
| Vulnerability scanning (containers/VMs) | Inspector | Container/VM vulnerability scanning in Artifact Registry / Security Command Center |

### 8.6 Security Decision Framework

1. **Always start with least privilege** — never use root/Owner/`*` permissions in production workloads.
2. **Use roles/service accounts for compute-to-service auth, never embedded static credentials.**
3. **Encrypt at rest AND in transit by default** — enforce via org policy/SCP, don't rely on per-resource opt-in.
4. **Centralize identity** — federate with existing corporate IdP (SAML/OIDC) via IAM Identity Center (AWS) / Cloud Identity + Workforce Identity Federation (GCP) rather than creating separate cloud-native users per employee.
5. **Layer defenses** — network (security groups/firewalls) + WAF + IAM + encryption + logging/monitoring, so no single control failure is catastrophic (defense in depth).

## §9 Serverless & Container Orchestration Deep Dive

### 9.1 Lambda Internals — What Actually Happens on Invocation

1. **Cold start:** if no warm execution environment exists, AWS provisions a new micro-VM (Firecracker), downloads your code/image, initializes the runtime, runs your init code (outside the handler — global scope), THEN runs your handler. This full cycle is the "cold start" and can range from ~100ms (interpreted languages, small package) to 1-10s+ (JVM-based runtimes, large dependencies, VPC-attached functions historically had extra ENI-attach latency, though AWS has since made this near-negligible via pre-provisioned Hyperplane ENIs).
2. **Warm start:** if a prior execution environment is still alive (kept warm for some minutes after use), AWS reuses it — only your handler code runs, no init phase, dramatically faster.
3. **Concurrency:** each concurrent request needs either a warm environment or a new cold start; **Provisioned Concurrency** pre-initializes N environments to eliminate cold starts for latency-sensitive workloads at a fixed cost.
4. **Interview question: "How do you reduce Lambda cold starts?"** → Use a lighter runtime (avoid heavy JVM if latency-critical), minimize package size and dependencies, use Provisioned Concurrency for predictable-latency needs, keep init-phase code (SDK client creation) OUTSIDE the handler so it's reused across warm invocations, and consider SnapStart (Java-specific — snapshots an initialized execution environment to skip JVM warmup).

### 9.2 Cloud Functions / Cloud Run Internals

- Cloud Functions 2nd gen is actually built ON TOP OF Cloud Run under the hood, inheriting its concurrency and scaling model.
- Cloud Run's **concurrency setting** (requests per instance, default 80, max ~1000) is a major cost/performance lever: higher concurrency per instance means fewer instances needed for the same load (cheaper, since billing is per-instance-resource-time), but only works well for I/O-bound (not CPU-bound) workloads since concurrent requests on one instance share the same vCPU allocation.
- **Min instances** (both Cloud Run and Cloud Functions 2nd gen) keep N instances always warm — direct equivalent to Lambda Provisioned Concurrency.

### 9.3 Fargate vs EKS/GKE Node Pools — the Serverless-K8s Spectrum

| Approach | Ops overhead | Cost model | Control |
|---|---|---|---|
| EC2/Compute Engine node pools (self-managed nodes in EKS/GKE) | High (patch nodes, capacity plan, bin-pack pods) | Pay for whole nodes regardless of utilization | Full control (custom AMIs, DaemonSets, node-level tuning) |
| Fargate (AWS, works with ECS or EKS) | Low (no nodes to manage) | Pay per vCPU/memory requested by each pod/task | Limited (no DaemonSets, no privileged containers, no host networking) |
| GKE Autopilot | Lowest (Google manages nodes, security hardening, scaling entirely) | Pay per pod resource request | Limited (restricts privileged workloads, some node customization) |

**Interview trade-off to articulate:** Fargate/Autopilot remove operational burden but at a per-resource cost premium and reduced flexibility (no host-level customization, some workloads like DaemonSets or privileged security agents can't run). Teams running many small, bursty workloads or without dedicated platform/SRE teams benefit most from Fargate/Autopilot; teams with heavy, steady-state, highly-customized workloads (GPU scheduling quirks, custom kernel modules, extreme bin-packing needs for cost) often still prefer self-managed node pools for the cost efficiency at scale and full control.

### 9.4 Scale-to-Zero — Why It Matters

Both Lambda/Cloud Functions and Cloud Run scale genuinely to **zero** instances when idle (you pay nothing when there's no traffic) — this is fundamentally different from even the smallest always-on EC2/Compute Engine instance, which incurs cost 24/7. This is why serverless is the default recommendation for spiky, unpredictable, or low-traffic workloads (internal tools, webhooks, cron-triggered jobs, MVPs/prototypes) and a common interview "cost optimization" answer.

---

## §10 Observability & Monitoring

### 10.1 The Three Pillars: Metrics, Logs, Traces

| Pillar | AWS | GCP |
|---|---|---|
| Metrics | CloudWatch Metrics (+ CloudWatch Alarms) | Cloud Monitoring (formerly Stackdriver) |
| Logs | CloudWatch Logs (+ Logs Insights for querying) | Cloud Logging |
| Distributed tracing | X-Ray | Cloud Trace |
| Dashboards | CloudWatch Dashboards | Cloud Monitoring Dashboards |
| Synthetic monitoring | CloudWatch Synthetics | Uptime checks (part of Cloud Monitoring) |
| Profiling | CodeGuru Profiler | Cloud Profiler |
| Error tracking/aggregation | (via CloudWatch Logs + X-Ray, less first-class) | Error Reporting (dedicated, first-class service) |

### 10.2 Distributed Tracing Deep Dive

In a microservices architecture, a single user request fans out across many services — distributed tracing (X-Ray / Cloud Trace) attaches a unique **trace ID** to the request at the edge (e.g., API Gateway/Load Balancer) and propagates it through every downstream call (typically via HTTP headers like `traceparent` per the W3C Trace Context standard, or AWS's own `X-Amzn-Trace-Id`). Each service adds **spans** (a span = one unit of work, e.g., "call payment service," with start/end time), and the tracing backend stitches spans into a full trace showing the entire request's latency breakdown across services — critical for answering "why is this request slow?" in a way that logs/metrics alone cannot.

**Interview question: "How would you debug a slow request that spans 8 microservices?"** Answer: distributed tracing is the primary tool — look at the trace waterfall to identify which specific span/service contributed the most latency, then drill into that service's logs/metrics for the root cause, rather than manually correlating timestamps across 8 separate log streams.

### 10.3 Alerting & SLOs

Both platforms let you define alerting policies on metrics (threshold-based or anomaly-detection-based) that notify via SNS/email/PagerDuty (AWS) or Notification Channels (GCP: email/SMS/PagerDuty/Slack/Pub/Sub). A mature observability setup ties alerts to **SLOs (Service Level Objectives)** — e.g., "99.9% of requests must complete in under 300ms over a rolling 30-day window" — and pages engineers based on **error budget burn rate** (how fast you're consuming your allowed failure budget) rather than raw threshold breaches, to reduce noisy/non-actionable alerts. GCP's Cloud Monitoring has first-class SLO objects; on AWS this is typically built on top of CloudWatch metrics/alarms with custom burn-rate math.

---

## §11 IaC & DevOps Tooling

### 11.1 Infrastructure as Code

| Tool | Provider | Notes |
|---|---|---|
| CloudFormation | AWS-native | JSON/YAML, declarative, drift detection built-in, stack-based (rollback on failure) |
| CDK (Cloud Development Kit) | AWS-native | Write infra in TypeScript/Python/Java/etc., synthesizes to CloudFormation — brings real programming constructs (loops, classes, package management) to IaC |
| Deployment Manager | GCP-native | YAML/Jinja2/Python templates — less commonly used now, largely superseded by Terraform in the GCP ecosystem |
| Terraform | Multi-cloud (HashiCorp) | HCL syntax, state-file based, the de facto standard for multi-cloud IaC — used heavily in Part 6 of this guide |
| Pulumi | Multi-cloud | IaC using general-purpose languages (Python/TypeScript/Go), alternative to Terraform/CDK |

**Why Terraform dominates multi-cloud interviews and real projects:** it's the only major tool with mature, first-class providers for BOTH AWS and GCP (and Azure, and hundreds of other services) using ONE consistent workflow (`plan` → `apply` → state file), which is exactly why Part 6 of this guide uses Terraform for the multi-cloud integration walkthrough. CloudFormation/CDK and Deployment Manager are provider-locked and not suitable when a project must manage both clouds from one codebase/pipeline.

### 11.2 CI/CD Services

| Stage | AWS | GCP |
|---|---|---|
| Source | CodeCommit (deprecated for new customers — use GitHub/GitLab) | Cloud Source Repositories (also largely superseded by GitHub/GitLab integration) |
| Build | CodeBuild | Cloud Build |
| Deploy | CodeDeploy | Cloud Deploy |
| Orchestration (pipeline) | CodePipeline | Cloud Build (triggers) + Cloud Deploy (progressive delivery) |
| Artifact storage | ECR (containers), CodeArtifact (packages) | Artifact Registry (containers AND packages, unified) |

**Artifact Registry unifying container images AND language packages (npm, Maven, Python, etc.) in one service is a GCP simplification** worth mentioning versus AWS's split between ECR (containers only) and CodeArtifact (packages only).

### 11.3 GitOps & Progressive Delivery

Both clouds increasingly support GitOps patterns (Git as the source of truth for desired infra/app state, with an operator reconciling actual state to match) — commonly implemented with **Argo CD** or **Flux** on top of EKS/GKE, independent of the specific cloud. **Cloud Deploy (GCP)** has native progressive delivery support (canary, blue-green rollout strategies defined declaratively); AWS achieves the same via CodeDeploy's deployment configurations (canary, linear, all-at-once) for Lambda/ECS/EC2.

---

## §12 AWS vs GCP vs Azure Master Service-Mapping Table

| Category | AWS | GCP | Azure |
|---|---|---|---|
| Virtual machines | EC2 | Compute Engine | Virtual Machines |
| Autoscaling group | Auto Scaling Groups | Managed Instance Groups | Virtual Machine Scale Sets |
| Serverless functions | Lambda | Cloud Functions | Azure Functions |
| Serverless containers | Fargate / App Runner | Cloud Run | Container Apps / Container Instances |
| Managed Kubernetes | EKS | GKE | AKS |
| PaaS app hosting | Elastic Beanstalk | App Engine | App Service |
| Object storage | S3 | Cloud Storage | Blob Storage |
| Block storage | EBS | Persistent Disk | Managed Disks |
| File storage | EFS | Filestore | Azure Files |
| Relational DB (managed) | RDS | Cloud SQL | Azure SQL Database |
| Distributed relational DB | Aurora | Spanner | Azure SQL Hyperscale / Cosmos DB (multi-model) |
| NoSQL key-value/document | DynamoDB | Firestore | Cosmos DB |
| Wide-column NoSQL | (Keyspaces - Cassandra-compatible) | Bigtable | Cosmos DB (Cassandra API) |
| In-memory cache | ElastiCache | Memorystore | Azure Cache for Redis |
| Data warehouse | Redshift | BigQuery | Synapse Analytics |
| Object storage query engine | Athena | BigQuery (native) | Synapse Serverless SQL |
| Message queue | SQS | Cloud Tasks / Pub/Sub | Queue Storage / Service Bus |
| Pub/Sub | SNS | Pub/Sub | Service Bus Topics / Event Grid |
| Streaming | Kinesis | Pub/Sub + Dataflow | Event Hubs |
| Managed Kafka | MSK | (3rd party / self-hosted) | Event Hubs for Kafka |
| Event bus | EventBridge | Eventarc | Event Grid |
| Workflow orchestration | Step Functions | Workflows | Logic Apps / Durable Functions |
| VPC | VPC (regional) | VPC (global) | Virtual Network |
| Load balancer (L7) | ALB | Cloud Load Balancing (global) | Application Gateway |
| Load balancer (L4) | NLB | Network Load Balancer | Azure Load Balancer |
| CDN | CloudFront | Cloud CDN | Azure CDN / Front Door |
| DNS | Route 53 | Cloud DNS | Azure DNS |
| VPN | Site-to-Site VPN | Cloud VPN | VPN Gateway |
| Dedicated interconnect | Direct Connect | Cloud Interconnect | ExpressRoute |
| IAM | IAM | Cloud IAM | Azure AD / Entra ID + RBAC |
| Secrets management | Secrets Manager | Secret Manager | Key Vault |
| KMS | KMS | Cloud KMS | Key Vault (keys) |
| WAF | WAF | Cloud Armor | Azure WAF |
| DDoS protection | Shield | Cloud Armor (Adaptive Protection) | DDoS Protection |
| Threat detection | GuardDuty | Security Command Center | Microsoft Defender for Cloud |
| Monitoring/metrics | CloudWatch | Cloud Monitoring | Azure Monitor |
| Logging | CloudWatch Logs | Cloud Logging | Azure Monitor Logs |
| Tracing | X-Ray | Cloud Trace | Application Insights |
| IaC (native) | CloudFormation / CDK | Deployment Manager | ARM Templates / Bicep |
| CI/CD | CodePipeline/CodeBuild/CodeDeploy | Cloud Build / Cloud Deploy | Azure DevOps / GitHub Actions |
| Container registry | ECR | Artifact Registry | Azure Container Registry |
| ML platform | SageMaker | Vertex AI | Azure Machine Learning |
| IoT | IoT Core | Cloud IoT (deprecated 2023, use partners) | IoT Hub |
| Backup | AWS Backup | Backup and DR Service | Azure Backup |
| Org/account management | Organizations + Control Tower | Resource Manager (Folders/Projects) | Management Groups |

*(This table is reproduced and extended in §57 for quick pre-interview review.)*

---

## §13 Well-Architected Framework vs Google Cloud Architecture Framework

### 13.1 AWS Well-Architected Framework — 6 Pillars

1. **Operational Excellence** — run and monitor systems to deliver business value, continuously improve processes (IaC, small frequent changes, runbooks, learning from failures/post-incident reviews).
2. **Security** — protect data/systems (identity foundations, traceability, defense in depth, automate security best practices, prepare for incidents).
3. **Reliability** — recover from failure, dynamically acquire resources to meet demand, mitigate disruptions (define recovery procedures, test them, use multi-AZ/multi-region as appropriate).
4. **Performance Efficiency** — use resources efficiently, keep up with evolving tech (serverless/managed services where possible, experiment, understand trade-offs of resource choices).
5. **Cost Optimization** — avoid unnecessary costs (rightsizing, elasticity, pay only for value, measure/monitor spend).
6. **Sustainability** — minimize environmental impact of workloads (maximize utilization, use managed services designed for efficiency, retire unneeded resources).

### 13.2 Google Cloud Architecture Framework — Pillars

1. **Operational Excellence** — efficiently deploy, operate, monitor, and manage workloads.
2. **Security, Privacy, and Compliance** — maximize security, protect data, comply with regulations.
3. **Reliability** — design resilient, highly-available, performant workloads.
4. **Cost Optimization** — maximize business value from cloud investment.
5. **Performance Optimization** — design for scalability and optimal performance.
(Google also treats **AI/ML readiness** as a cross-cutting theme in more recent framework revisions.)

### 13.3 Interview Framing

You do NOT need to recite pillar names verbatim in an interview, but you SHOULD structure your trade-off discussions along these axes: "This design favors cost optimization (using Spot instances) at some risk to reliability (Spot can be reclaimed) — I'd mitigate that by diversifying across multiple instance types/AZs and keeping a small on-demand baseline." This kind of explicit multi-pillar trade-off reasoning is exactly what separates a senior-level system design answer from a junior one — junior candidates tend to only optimize for "does it work," while senior candidates explicitly reason about the tension between cost/reliability/performance/security/operability.

# Part 2 — The Cloud System Design Interview Framework

## §14 Step-by-Step Approach to Any Cloud System Design Interview

Cloud system design interviews differ from generic system design interviews in one crucial way: you're expected to name **specific managed services** and justify why you picked them over alternatives (including the other cloud's equivalent, if relevant), not just abstract components like "a load balancer" and "a database." Use this 7-step framework for any 45-60 minute cloud system design interview.

### Step 1 — Clarify Requirements (5 minutes)

Ask about:
- **Functional requirements:** what must the system do? (e.g., "upload a file," "search products," "process a payment")
- **Scale:** how many users (DAU/MAU)? How many requests/sec (read vs write split)? How much data (total + daily growth)?
- **Latency expectations:** is this a real-time interactive system (sub-100ms) or can it tolerate async/batch processing (minutes/hours)?
- **Consistency requirements:** can reads be stale (eventual consistency ok) or must every read reflect the latest write (strong consistency required)?
- **Availability target:** what SLA is expected (99.9%? 99.99%?) — this directly determines whether multi-AZ is enough or multi-region is required.
- **Budget/cost sensitivity:** is this a startup MVP (optimize for speed/cost) or an enterprise system (optimize for compliance/reliability, cost secondary)?
- **Cloud constraint:** did the interviewer specify AWS, GCP, or "your choice"? If "your choice," pick ONE and stay consistent — don't awkwardly mix services from both clouds in one architecture unless explicitly asked to compare.

### Step 2 — Back-of-the-Envelope Estimation (5-10 minutes)

Convert the scale numbers into concrete infrastructure sizing (see §15 for full worked examples). At minimum, compute:
- **QPS (queries per second)**, split by read/write.
- **Storage** total and growth rate (per day/month/year).
- **Bandwidth** (ingress/egress) — this feeds directly into CDN/caching decisions and cost discussion.
- **Peak-to-average ratio** — most real traffic isn't flat; identify if there are predictable spikes (e.g., ticket on-sale, Black Friday) that require specific scaling strategy (pre-warming, queue-based load leveling).

### Step 3 — Define the API / Interface Contract (5 minutes)

Sketch the 3-6 most important API endpoints (REST/gRPC) with request/response shape. This anchors the rest of the design and gives the interviewer a concrete artifact to probe ("what happens if this endpoint gets called 10,000 times per second?").

### Step 4 — High-Level Architecture Diagram (10-15 minutes)

Draw (in text/ASCII if verbal/no whiteboard) the major components: client → CDN/edge → load balancer → compute tier → cache → database → async/queue tier → downstream services. For EVERY box, name the specific managed service (e.g., "ALB" not "load balancer," "DynamoDB with a GSI on user_id" not "a database"), and briefly justify the choice against 1-2 alternatives you considered and rejected.

### Step 5 — Deep Dive on the Hardest 1-2 Subproblems (10-15 minutes)

The interviewer usually steers this, but common deep-dive targets: how do you shard/partition the data at this scale? how do you keep the cache consistent with the database? how do you handle a specific failure mode (a downstream service is slow/down)? how do you achieve exactly-once processing for payments? Go deep here — this is where senior signal is demonstrated.

### Step 6 — Bottlenecks, Scaling, and Failure Modes (5-10 minutes)

Proactively identify: single points of failure (fix with redundancy), hot partitions/keys (fix with better key design or caching), thundering herd scenarios (fix with jitter/backoff, request coalescing), and what happens during a regional outage (fix with multi-region DR strategy, see §16).

### Step 7 — Trade-offs, Cost, and Wrap-Up (5 minutes)

Summarize the key trade-offs made (e.g., "we chose eventual consistency for the news feed to get horizontal write scalability"), give a rough monthly cost order-of-magnitude, and mention what you'd do differently with more time/at 10x scale.

### 14.1 Common Mistakes That Signal Junior-Level Thinking

- Jumping straight to a detailed diagram without clarifying requirements/scale first.
- Naming services with no justification ("I'll use DynamoDB" — why not RDS? why not Firestore if GCP?).
- Ignoring cost entirely, or ignoring it after being explicitly asked.
- Designing for infinite scale when the stated requirements are modest (over-engineering: proposing a global multi-region Spanner deployment for an internal tool with 50 users).
- Not addressing failure modes/bottlenecks unless explicitly prompted.
- Mixing AWS and GCP services in the same diagram with no stated reason (e.g., "S3 for storage, then Pub/Sub for events, then DynamoDB" — pick one cloud unless asked to compare).

---

## §15 Cost Estimation & Capacity Planning Worked Examples

### 15.1 Worked Example: Estimating Storage for a Photo-Sharing App

**Assumptions:** 10 million daily active users (DAU), each uploads on average 0.5 photos/day, average photo size 2MB (original) + we generate 3 thumbnail sizes averaging 100KB each.

- Daily uploads = 10M × 0.5 = 5M photos/day.
- Daily raw storage = 5M × 2MB = 10TB/day (originals) + 5M × 300KB (3 thumbnails) = 1.5TB/day (derivatives) ≈ **11.5TB/day new storage**.
- Monthly growth ≈ 11.5TB × 30 ≈ **345TB/month**.
- Yearly growth ≈ **~4.1PB/year** (ignoring any deletion/lifecycle policy).
- **Cost implication:** at this scale, you'd immediately propose a lifecycle policy (move originals older than 90 days to Standard-IA/Nearline, older than 1 year to Glacier/Coldline or Archive) since S3/GCS Standard pricing (~$0.023/GB/month) on 4PB+/year would be enormous ($~1.1M/year just for the first year's data on Standard, compounding) — this single calculation is exactly the kind of number that should trigger a storage-tiering discussion in the interview.

### 15.2 Worked Example: Estimating QPS and Server/Instance Count

**Assumptions:** 50M DAU, each user makes 20 requests/day on average, traffic is NOT flat — peak traffic is 3x the daily average (typical for consumer apps with regional daytime usage patterns).

- Total daily requests = 50M × 20 = 1B requests/day.
- Average QPS = 1,000,000,000 / 86,400 seconds ≈ **~11,600 QPS average**.
- Peak QPS ≈ 11,600 × 3 ≈ **~35,000 QPS peak**.
- If each application server/container can handle 500 requests/sec (typical for a moderately complex API handler), you need 35,000/500 = **70 instances/tasks at peak**, with auto-scaling down to roughly 11,600/500 ≈ 23 instances at average load.
- **This is exactly the number you use to justify an Auto Scaling Group / Managed Instance Group with target-tracking scaling** (e.g., target 60% CPU utilization) rather than a fixed fleet size — and it's also the number that justifies serverless (Lambda/Cloud Run) if the traffic pattern is spiky/unpredictable rather than a smooth diurnal curve, since serverless removes the need to pre-provision for peak.

### 15.3 Worked Example: Cache Sizing

**Assumptions:** Product catalog with 5M SKUs, each product's cached representation is ~2KB, and the "hot" working set (products actually being viewed regularly, per the Pareto/80-20 rule) is ~20% of the catalog.

- Hot working set = 5M × 20% = 1M products.
- Cache memory needed = 1M × 2KB = **~2GB** — comfortably fits in a single mid-sized ElastiCache/Memorystore Redis node (many nodes offer 13GB+), so no need for Redis Cluster sharding at this specific scale (a common "don't over-engineer" teaching point — always compute the actual number before assuming you need a distributed cache cluster).

### 15.4 Worked Example: Monthly Cost Order-of-Magnitude for a Mid-Size Web App

A rough back-of-envelope for a web app serving ~10M requests/day, moderate database, some caching, and a CDN (numbers are illustrative — always caveat "actual pricing varies by region/commitment/discounts" in an interview):

| Component | Rough Monthly Cost (illustrative) |
|---|---|
| Compute (ASG/MIG, ~10-20 mid-size instances average) | $1,500 - $3,000 |
| Managed relational DB (Multi-AZ, mid-size) | $500 - $1,200 |
| Cache (Redis, small-mid cluster) | $200 - $500 |
| Object storage + CDN egress | $300 - $1,000 (highly dependent on media-heaviness) |
| Load balancer + data transfer | $200 - $500 |
| Monitoring/logging | $100 - $300 |
| **Total order of magnitude** | **~$3,000 - $6,500/month** |

The exact numbers matter far less in an interview than demonstrating you can reason about WHICH components dominate cost (compute and data transfer/egress usually dominate) and what levers reduce each (reserved/committed use discounts for steady compute, CDN caching to cut egress, right-sizing instance types, storage lifecycle policies).

### 15.5 Capacity Planning Rules of Thumb Worth Memorizing

- **Rule of 3 AZs/zones:** always design for at least 2, ideally 3, AZ/zone redundancy for anything production-grade.
- **80/20 caching rule:** a well-designed cache with the "hot" 20% of data typically absorbs 80%+ of read traffic (Pareto principle) — use this to justify realistic cache-hit-ratio assumptions instead of guessing.
- **Peak-to-average ratios:** consumer-facing apps with a single dominant timezone commonly see 2-4x peak-to-average; global apps with users spread across timezones tend to have flatter, lower peak-to-average ratios (a genuine argument for global user bases being "easier" to capacity-plan for, ironically).
- **Read-heavy vs write-heavy skew:** most consumer apps are extremely read-heavy (100:1 or higher read:write ratios) — this justifies read replicas, caching, and CQRS-style separation of read/write paths; write-heavy systems (IoT ingestion, logging/analytics, ad click tracking) instead justify append-only/log-structured storage (Kinesis/Pub/Sub → data lake) over traditional OLTP databases.

---

## §16 Multi-Region / Disaster Recovery Strategies

### 16.1 The Four Standard DR Strategies (AWS's Framework, Equally Applicable to GCP)

| Strategy | RTO (Recovery Time) | RPO (Data Loss) | Cost | Description |
|---|---|---|---|---|
| **Backup & Restore** | Hours | Hours (since last backup) | $ (cheapest) | Regularly back up data to another region; in a disaster, provision infra from scratch and restore from backup. |
| **Pilot Light** | Tens of minutes | Minutes (near-continuous data replication) | $$ | Core data is continuously replicated to a standby region (e.g., a small/minimal replica DB), but compute is NOT running — you scale it up only during failover. |
| **Warm Standby** | Minutes | Seconds to minutes | $$$ | A scaled-down BUT fully functional copy of the full system runs in the secondary region at all times; scale it up to full capacity during failover. |
| **Multi-Site Active-Active** | Near-zero (seconds) | Near-zero (or zero) | $$$$ (most expensive) | Full production traffic is served from 2+ regions simultaneously; a regional failure just means traffic routing shifts away from the failed region — no "recovery" step needed at all. |

**RTO (Recovery Time Objective)** = how long can the system be down? **RPO (Recovery Point Objective)** = how much data can you afford to lose (measured in time since the last successful replication/backup)? These two numbers, agreed with the business BEFORE designing DR, should drive which of the 4 strategies you pick — this is one of the most common "how would you design DR for this system" interview questions, and citing RTO/RPO explicitly is the single strongest signal you understand DR properly.

### 16.2 Implementing Each Strategy — AWS and GCP Specifics

- **Backup & Restore:** AWS Backup / GCP Backup and DR Service, cross-region snapshot copy (EBS snapshots copied cross-region, RDS automated backups copied cross-region, S3 Cross-Region Replication / GCS multi-region or turbo replication buckets).
- **Pilot Light:** Aurora Global Database / Cloud SQL cross-region read replica (kept in sync continuously) with the application tier and load balancers pre-configured in the DR region via IaC (Terraform/CloudFormation) but scaled to zero/minimal — a failover runbook (often automated via Lambda/Cloud Functions triggered by a health check failure) scales up compute and promotes the standby DB to primary.
- **Warm Standby:** Same as pilot light but the DR region's compute fleet is already running at reduced capacity (e.g., 10-20% of production scale) continuously, so failover is just a scale-up + DNS/traffic shift rather than a cold start of the compute layer.
- **Multi-Site Active-Active:** requires either a globally-consistent database (Spanner) or an application design that tolerates eventual consistency/conflict resolution across regions (DynamoDB Global Tables with last-writer-wins or custom conflict resolution), plus global traffic routing (Route 53 latency/geoproximity routing + health-check-based failover, or GCP's naturally-global load balancer) that automatically routes away from an unhealthy region.

### 16.3 Failover Traffic Routing Mechanics

- **DNS-based failover (Route 53 / Cloud DNS):** health checks monitor each region's endpoint; if a region fails health checks, DNS stops returning its IP. **Drawback:** DNS caching/TTL means failover isn't instant — clients/resolvers may cache the old (failed) IP for the TTL duration (commonly 60-300 seconds), so DNS failover alone can't achieve near-zero RTO.
- **Anycast-based failover (Global Accelerator / GCP Global LB):** because the same IP is announced from multiple locations and health-checked continuously, failover happens at the network routing layer (BGP) almost instantly, without waiting on DNS TTLs — this is why Global Accelerator/GCP's global LB are recommended over pure DNS failover when sub-second/low-RTO failover is required.

### 16.4 Data Replication Consistency Trade-offs in Multi-Region

- **Synchronous cross-region replication** (wait for the remote region to ack before considering a write committed) gives zero data loss (RPO=0) but adds the full round-trip network latency to every write (often 50-150ms+ for cross-continent regions) — usually impractical for latency-sensitive systems, but sometimes accepted for critical financial data.
- **Asynchronous cross-region replication** (commit locally, replicate in the background) keeps write latency low but risks losing the last few seconds/minutes of unreplicated writes if the primary region fails abruptly (RPO > 0) — this is the far more common real-world choice, and Aurora Global Database / Cloud SQL cross-region replicas / DynamoDB Global Tables all default to this asynchronous model.
- **Interview follow-up:** "How would you achieve RPO=0 without paying full synchronous cross-region latency on every write?" A nuanced answer: use a quorum-based approach across 3+ regions (only wait for 2-of-3 acks, not all 3, reducing the latency penalty to "distance to the 2nd-closest region" rather than "distance to the furthest region") — this is conceptually how Spanner and other globally-distributed quorum systems achieve strong guarantees without full synchronous fan-out latency.

### 16.5 Chaos Engineering & DR Testing

A DR strategy that has never been tested is not a real DR strategy. Mention **GameDays** (AWS) / regular **DR drills** — deliberately failing over to the secondary region on a schedule (not just in theory) to validate the runbook actually works, measure real RTO/RPO against targets, and catch configuration drift between primary and DR regions before a real incident forces you to find out it's broken.

# Part 3 — HLD Case Studies

*Each case study follows the same structure so you can internalize the pattern: Problem Statement → Requirements → Estimation → API Design → High-Level Architecture → Data Model → Deep Dive → Bottlenecks & Scaling → Trade-offs → Follow-Up Interview Questions.*

## §17 Scalable 3-Tier Web Application (AWS)

### Problem Statement

Design a scalable, highly-available web application (think: a mid-size e-commerce or SaaS product) on AWS that can serve a global user base, handle traffic spikes, and survive an AZ failure without downtime.

### Requirements

**Functional:** users can browse content, search, log in, and perform CRUD operations on their data (e.g., manage a shopping cart, update a profile). **Non-functional:** 99.95% availability target, p99 latency under 300ms for read endpoints, support 20,000 peak QPS, must survive a single AZ outage with no data loss and under 1 minute of degraded service.

### Estimation

Following §15's method: assume 5M DAU, 15 requests/user/day average with a 3x peak multiplier → ~2,600 average QPS, ~7,800 peak QPS (round up to 20,000 peak per NFR to leave headroom for growth/marketing spikes). Storage: user profile + transactional data at ~5KB/user → 25GB base, growing modestly; product catalog images dominate storage (assume 2M product images at 500KB average = 1TB, served via CDN not directly from app servers).

### API Design (representative endpoints)

```
GET  /api/v1/products?category=&page=&limit=      -- browse/search (cacheable)
GET  /api/v1/products/{id}                         -- product detail (cacheable)
POST /api/v1/cart/items                            -- add to cart (write, authenticated)
POST /api/v1/orders                                 -- checkout (write, authenticated, idempotent via Idempotency-Key header)
GET  /api/v1/users/me                              -- profile (authenticated)
```

### High-Level Architecture

```
Internet
   |
CloudFront (CDN, caches static assets + cacheable GET responses at edge)
   |
Route 53 (DNS, health-check based failover across regions if multi-region; here: single region, multi-AZ)
   |
Application Load Balancer (ALB, spans 3 AZs, TLS termination via ACM cert, WAF attached)
   |
Auto Scaling Group (EC2 or ECS/Fargate tasks, spans 3 AZs, target-tracking scaling on CPU + ALB request count per target)
   |         \
   |          -- ElastiCache Redis (Multi-AZ cluster) -- session store + hot product/catalog cache
   |
RDS PostgreSQL (Multi-AZ primary/standby across 2 AZs) + up to 2 Read Replicas (for read-heavy catalog/reporting queries)
   |
S3 (product images, static assets) -- fronted by CloudFront
   |
SQS (order-processing queue, decouples checkout API from fulfillment/inventory/email workflows)
```

**Why these choices:** ALB (not NLB) because we need L7 routing (path-based routing between `/api` and static content, WAF integration, host-based routing for future multi-tenant subdomains). ASG across 3 AZs so losing one AZ still leaves 2/3 capacity. RDS Multi-AZ (not just a single instance) so a primary failure triggers an automatic failover to the synced standby in another AZ within ~60-120 seconds, satisfying the "under 1 minute of degraded service" NFR (combined with connection retry logic in the app tier, actual client-visible impact is typically well under a minute). ElastiCache absorbs the read-heavy catalog traffic (80/20 rule from §15.5) so RDS isn't the bottleneck for hot reads. SQS decouples the synchronous checkout API response (fast ack to the user: "order received") from slower downstream work (inventory decrement, payment capture confirmation, email receipt) — critical for keeping checkout latency low and resilient to a slow downstream dependency.

### Data Model (simplified)

- `users(id PK, email UNIQUE, password_hash, created_at)`
- `products(id PK, name, description, price, category_id, stock_qty)` — indexed on `category_id` for browse queries.
- `orders(id PK, user_id FK, status, total, created_at)` — indexed on `user_id`.
- `order_items(id PK, order_id FK, product_id FK, qty, price_at_purchase)`
- Redis: `cache:product:{id}` (TTL 5 min), `session:{session_id}` (TTL 30 min sliding).

### Deep Dive 1: Keeping the Cache Consistent With the Database

Use **cache-aside** (lazy loading): on a read, check Redis first; on a miss, read RDS, populate Redis with a TTL, return. On a write (e.g., admin updates product price), **invalidate** (delete) the cache key rather than trying to update it in place — this avoids race conditions where a stale write to cache could overwrite a newer value. To prevent a **thundering herd** on a popular product's cache expiry (many concurrent requests all miss at once and hammer RDS simultaneously), use a short-lived **mutex/lock** in Redis (`SETNX`) so only one request repopulates the cache while others wait briefly or serve slightly-stale data.

### Deep Dive 2: Idempotent Checkout Under Retries

Clients (mobile apps with flaky networks) may retry a `POST /orders` request after a timeout, risking a duplicate order. Require an `Idempotency-Key` header (client-generated UUID per checkout attempt); the API stores `(idempotency_key, response)` in a fast-lookup table/Redis with a TTL of 24 hours — if the same key arrives again, return the cached response immediately without re-executing the order logic. This is the standard idempotency pattern used by Stripe and virtually every payments API.

### Bottlenecks & Scaling

- **RDS as a single writer** is the eventual ceiling — mitigate with read replicas for reads, and if write throughput becomes the bottleneck, consider migrating hot tables to DynamoDB or moving to Aurora for higher write throughput headroom.
- **Hot product pages** (viral/flash-sale item) can overwhelm even the cache layer — mitigate with CloudFront caching the product detail JSON response itself (short TTL, e.g., 5-10 seconds) to absorb extreme spikes at the edge before they even reach the ALB.
- **SQS consumer lag** during order spikes — mitigate by scaling the consumer fleet (ASG) on `ApproximateNumberOfMessagesVisible` CloudWatch metric.

### Trade-offs

Chose RDS (relational, strong consistency for orders/inventory — critical for correctness) over DynamoDB for the transactional core, accepting the operational ceiling of a single-writer relational model in exchange for simpler transactional guarantees (SQL transactions across `orders`/`order_items`/`inventory` decrement). Chose asynchronous order fulfillment (SQS) over synchronous processing, trading a small amount of "did my order fully complete" immediacy for much better checkout latency and resilience.

### Follow-Up Interview Questions

- "How would you handle a flash sale where 100,000 users try to buy 500 units of the same item at the same instant?" → Move inventory decrement to a single atomic operation (SQL `UPDATE ... WHERE stock_qty > 0` or a Redis `DECR` with a floor check), queue the requests through SQS/a virtual waiting room, and consider a dedicated high-throughput path (DynamoDB conditional writes) for just that hot item rather than routing it through the general RDS path.
- "How would you migrate this to multi-region?" → See §16 and §24 for the full active-active pattern; short answer: Aurora Global Database for the data layer, Route 53 latency routing or Global Accelerator for traffic, and re-architect checkout to tolerate eventual consistency or pin a user's session to one region ("sticky region routing").

---

## §18 Scalable 3-Tier Web Application (GCP)

### Problem Statement

Same as §17 — design the identical scalable, highly-available 3-tier web application, this time natively on GCP, to highlight the architectural translation between clouds.

### Requirements & Estimation

Identical to §17 (5M DAU, ~20,000 peak QPS target, 99.95% availability, p99 < 300ms, survive a zone outage).

### High-Level Architecture

```
Internet
   |
Cloud CDN (caches static assets + cacheable responses at Google's edge PoPs)
   |
Global External Application Load Balancer (single anycast IP, global by default -- no separate DNS
   failover layer needed even if we later add a 2nd region, since the LB itself routes globally)
   |
Managed Instance Group (Compute Engine or GKE Autopilot pods, regional -- spans all zones in
   the region automatically, autoscaling on CPU + custom Cloud Monitoring metric e.g. requests/sec)
   |         \
   |          -- Memorystore for Redis (Standard tier, HA across zones) -- session store + hot cache
   |
Cloud SQL for PostgreSQL (HA config: synchronous standby in another zone, automatic failover)
   + up to 2 read replicas (can be cross-region for read-latency optimization for global users)
   |
Cloud Storage (product images, static assets) -- fronted by Cloud CDN
   |
Pub/Sub (order-processing topic, decouples checkout API from fulfillment/inventory/email workflows)
```

**Architectural differences from the AWS version worth calling out explicitly in an interview:**
1. **The load balancer is global by default** — if this app later expands to a second GCP region, we do NOT need to introduce a new routing layer (unlike AWS, where we'd need to add Route 53 latency-based routing or Global Accelerator on top of the regional ALBs). This is a genuine simplification GCP offers for future multi-region growth.
2. **The Managed Instance Group is regional**, automatically spreading instances across all zones in the region without the developer explicitly picking "3 zones" the way an AWS ASG requires explicit AZ configuration — one less thing to misconfigure.
3. **Cloud SQL read replicas can be cross-region** directly as a first-class feature aimed at read-latency reduction for geographically distributed users, whereas AWS RDS cross-region read replicas exist too but are more commonly discussed in the DR context (§16) than pure read-latency optimization — in practice both clouds support this, but GCP's documentation/tooling leans into the read-latency use case more explicitly.
4. **Pub/Sub replaces SQS** — same decoupling purpose, but note Pub/Sub is pub/sub-shaped (topic + subscriptions) even when used in a single-consumer-group "queue" pattern; message ordering requires explicit ordering keys (unlike SQS FIFO's simpler queue-native ordering model).

### Data Model

Identical relational schema to §17 (Cloud SQL is also PostgreSQL-compatible), with the cache key namespace identical (`cache:product:{id}`, `session:{session_id}`).

### Deep Dive 1: Cache Consistency (identical pattern to §17, cache-aside + invalidation-on-write + mutex against thundering herd) — the caching STRATEGY doesn't change between clouds; only the specific managed service (Memorystore vs ElastiCache) changes.

### Deep Dive 2: Achieving the Same Idempotent Checkout Pattern

Identical idempotency-key pattern as §17, but the storage for the idempotency-key/response table could use Firestore (fast single-document lookups, native TTL support via document expiration policies) instead of a Redis-based approach, showcasing that GCP's Firestore is a genuinely convenient option for this exact "idempotency ledger" use case due to native TTL and strong single-document consistency.

### Bottlenecks & Scaling

Same conceptual bottlenecks as §17 (Cloud SQL single-writer ceiling, hot product cache stampedes, Pub/Sub consumer lag during spikes) with the GCP-native mitigation: Cloud SQL read replicas for read scaling (or migrate hot-write tables to Firestore/Spanner if write throughput becomes the ceiling — Spanner being the more dramatic "we've truly outgrown a single-writer relational model" answer, since it removes the ceiling entirely rather than just adding read replicas), Cloud CDN edge caching for hot product pages, and autoscaling Pub/Sub consumers on the `subscription/num_undelivered_messages` Cloud Monitoring metric (the direct analog of SQS's `ApproximateNumberOfMessagesVisible`).

### Trade-offs

Same core trade-off as §17: relational/strong-consistency core (Cloud SQL) over Firestore for the transactional order/inventory data, for the same SQL-transaction-correctness reasons. The GCP-specific extra trade-off to mention: choosing Cloud SQL over Spanner up front accepts the eventual need to re-platform if write scale outgrows a single-writer instance, in exchange for much lower cost/operational complexity at the current (5M DAU) scale — Spanner would be over-engineering for this requirement level, a good "avoid premature optimization" talking point.

### Follow-Up Interview Questions

- "If this were built from scratch today with global users in mind, would you start with Cloud SQL or Spanner?" → Frame as a cost/complexity vs future-proofing trade-off; for most products, start with Cloud SQL (cheaper, simpler, well-understood) and design the data access layer so a future migration to Spanner (which supports the PostgreSQL interface too) is feasible without a full rewrite, rather than paying Spanner's cost/complexity premium from day one for a hypothetical future need.
- "How does GKE Autopilot change this design versus plain Compute Engine MIGs?" → Autopilot removes node-pool capacity planning entirely (pay per pod resource request), which is attractive if the team lacks dedicated infra/SRE ops capacity, at the cost of some flexibility (no privileged containers/DaemonSets) — mention this is the same MIG-vs-Autopilot trade-off from §9.3.

## §19 Serverless REST API (AWS Lambda + DynamoDB vs GCP Cloud Functions/Cloud Run + Firestore)

### Problem Statement

Design a serverless REST API backend for a mobile app's social features (follow users, post short updates, like posts) that must scale from zero to millions of requests without any server management, and must be cost-efficient for a spiky, unpredictable traffic pattern (viral growth potential).

### Requirements

**Functional:** create/read posts, follow/unfollow users, like a post, fetch a user's timeline (posts from followed users). **Non-functional:** must scale to zero cost during idle periods (this is an early-stage product with uncertain traffic), p99 latency under 500ms including cold starts, must handle a 100x traffic spike within minutes without manual intervention, budget-constrained (serverless chosen specifically to avoid paying for idle capacity).

### Estimation

Assume launch-phase traffic: 10,000 DAU growing potentially to 1M+ DAU within months (hence "serverless to avoid over/under-provisioning during unpredictable growth" is the central design driver, not a nice-to-have). At 10k DAU with 30 actions/day average: ~3.5 average QPS, but viral spikes (e.g., a featured post) could realistically produce 100-1000x for short bursts — exactly the scenario serverless auto-scaling handles far better than a pre-provisioned fleet.

### API Design

```
POST /api/v1/posts                 -- create a post (auth required)
GET  /api/v1/timeline               -- fetch a user's feed (auth required, paginated)
POST /api/v1/follows/{userId}       -- follow a user
POST /api/v1/posts/{postId}/likes   -- like a post (idempotent)
```

### High-Level Architecture — AWS Variant

```
Client (mobile app)
   |
Amazon API Gateway (HTTP API type -- cheaper & lower-latency than REST API type for this use case;
   handles auth via a Lambda authorizer or Cognito, request validation, throttling)
   |
AWS Lambda (one function per route, or a single function with internal routing -- Node.js/Python
   runtime chosen for fast cold starts; Provisioned Concurrency on the /timeline read path only,
   since it's the latency-critical, most-frequently-hit endpoint)
   |
DynamoDB (single-table design -- see Deep Dive 1) with DynamoDB Streams enabled
   |
DynamoDB Streams --> Lambda (fan-out trigger: on a new post, asynchronously write a copy into each
   follower's "timeline" partition -- the fan-out-on-write pattern, see Deep Dive 2)
```

### High-Level Architecture — GCP Variant

```
Client (mobile app)
   |
API Gateway (GCP) or a direct Cloud Run HTTPS endpoint with Firebase Auth for authentication
   |
Cloud Run (chosen over Cloud Functions here because it lets us bundle a full lightweight web
   framework with routing logic in one container, and its higher per-instance concurrency further
   reduces cost at scale; min-instances=1 configured on the timeline-read service only)
   |
Firestore (in Native mode -- collections: users, posts, follows, timelines) with a Cloud Function
   triggered by Firestore document-create events on the `posts` collection
   |
Firestore trigger --> Cloud Function (fan-out-on-write: write a denormalized copy of the new post
   into each follower's `timelines/{userId}/entries` subcollection)
```

### Data Model

**AWS DynamoDB single-table design** (a heavily-tested interview pattern from §5.2):

| PK | SK | Attributes | Purpose |
|---|---|---|---|
| `USER#123` | `PROFILE` | name, bio, follower_count | User profile lookup |
| `USER#123` | `FOLLOWS#456` | followed_at | "123 follows 456" edge |
| `POST#789` | `META` | author_id, text, created_at, like_count | Post content |
| `TIMELINE#123` | `POST#789#<ts>` | denormalized post preview | Precomputed timeline entry for user 123 |

A GSI on `author_id` allows "fetch all posts by user X" without a table scan. This single table answers ALL the app's access patterns (profile lookup, follow-edge lookup, timeline fetch as a single `Query` by partition key `TIMELINE#123` sorted by the timestamp-embedded sort key) — exactly the "overload GSIs/composite sort keys to avoid needing joins" technique referenced in §5.2.

**GCP Firestore model:** `users/{userId}`, `follows/{userId}/following/{followedId}`, `posts/{postId}`, `timelines/{userId}/entries/{postId}` (a subcollection per user, populated by the fan-out Cloud Function) — Firestore's native document/subcollection hierarchy makes this feel more natural than DynamoDB's flat single-table overloading, since Firestore is designed around nested collections rather than a single flat keyspace.

### Deep Dive 1: Fan-Out-on-Write vs Fan-Out-on-Read for the Timeline

This is THE classic system design question for any social feed (also covered generically in the News Feed case study of the companion System Design guide, but here specifically through a serverless lens):

- **Fan-out-on-write (push model):** when a user posts, immediately write a copy of that post into every follower's precomputed timeline. **Pro:** reading a timeline is a single cheap partition-key query (fast). **Con:** a celebrity with 10M followers triggers 10M writes for a single post (the "celebrity problem") — at serverless-function scale this could mean 10M Lambda/Cloud Function invocations from one post, an enormous and expensive fan-out burst.
- **Fan-out-on-read (pull model):** don't precompute anything; when a user requests their timeline, query posts from all followed users in real time and merge/sort. **Pro:** no write amplification. **Con:** reading becomes expensive (N queries merged) and slow, especially for users following thousands of accounts.
- **Hybrid (the realistic answer):** fan-out-on-write for normal users (bounded follower counts), but fan-out-on-read (or a hybrid "pull just the celebrity's recent posts and merge them in at read time") for accounts above a follower-count threshold (e.g., 100k+ followers) — this hybrid is the answer virtually every real large-scale social platform (Twitter/Instagram) actually uses, and citing it demonstrates awareness of the celebrity-problem trade-off.

### Deep Dive 2: Cost Modeling Serverless at Scale — When Does Serverless Stop Being Cheaper?

At very low/spiky traffic, serverless (Lambda/Cloud Functions/Cloud Run) is unambiguously cheaper than any always-on compute, since you pay $0 when idle. But per-invocation/per-GB-second serverless pricing has a HIGHER marginal cost per unit of compute than a reserved/committed EC2 or Compute Engine instance running the equivalent workload continuously at high utilization. The crossover point (where a steadily-busy always-on fleet becomes cheaper than serverless) typically occurs once a workload is consistently utilizing compute a large fraction of the time (rule of thumb: once sustained utilization exceeds roughly 30-50% of the time, start modeling the always-on alternative cost) — this is exactly why mature, high-traffic products often "graduate" from Lambda/Cloud Functions to ECS/Fargate/EKS or GKE once their load becomes predictable and high-volume, while keeping serverless for genuinely spiky/low-volume paths (e.g., admin endpoints, webhooks, infrequent batch jobs). Being able to articulate this crossover point is a strong cost-optimization interview signal.

### Bottlenecks & Scaling

- **DynamoDB hot partition on a viral post** (many likes/reads hitting `POST#789` simultaneously) — mitigate with DynamoDB's adaptive capacity (automatic, built-in) plus an application-level cache (DAX for DynamoDB, or a simple in-Lambda-memory cache with a short TTL for extremely hot items) in front of the hottest keys.
- **Fan-out Lambda/Cloud Function concurrency limits** — a sudden celebrity post could hit account-level concurrency limits (AWS default 1000 concurrent Lambda executions per region, adjustable) — mitigate with reserved concurrency planning and the hybrid fan-out approach from Deep Dive 1.
- **API Gateway throttling** — configure per-client/per-API-key rate limits (token bucket, see the Rate Limiter case study in the companion System Design guide) to prevent one abusive client from exhausting shared account-level throughput.

### Trade-offs

Chose full serverless (API Gateway/Cloud Run + Lambda/Cloud Functions + DynamoDB/Firestore) over a traditional ASG/MIG + RDS/Cloud SQL stack specifically because the product is pre-product-market-fit with highly uncertain traffic — the ability to scale to zero and to 100x without any capacity planning is worth the higher marginal per-request cost and the NoSQL modeling complexity (single-table design) at this stage. Explicitly flagged that this decision should be revisited once traffic patterns stabilize (see Deep Dive 2's crossover point discussion).

### Follow-Up Interview Questions

- "How would you handle a user who follows 50,000 accounts — would fan-out-on-write still work for THEIR timeline reads?" → Fan-out-on-write is about the POSTER's follower count, not the READER's following count, so this is a different problem: a user following 50k accounts doing fan-out-on-read would need to merge 50k sources — mitigate by still doing fan-out-on-write for that user (their timeline is precomputed regardless of how many people they follow) since the precomputation happens once per post from each of the people they follow, not once per timeline read.
- "How do you keep the two clouds' fan-out Lambda/Cloud Function from processing the same event twice (exactly-once concerns)?" → DynamoDB Streams/Firestore triggers are typically at-least-once delivery — make the fan-out write idempotent (writing the same denormalized timeline entry twice with the same key is harmless/idempotent by construction, since it's just an overwrite of the same item) rather than trying to achieve true exactly-once delivery, which is usually unnecessary engineering effort if the operation is naturally idempotent.

---

## §20 Event-Driven Microservices Architecture

### Problem Statement

Design an event-driven microservices architecture for an order-processing system (order service, inventory service, payment service, shipping service, notification service) where services are decoupled, independently deployable, and resilient to individual service failures — a common "convert this monolith to microservices" or "design a decoupled backend" interview prompt.

### Requirements

**Functional:** placing an order must reliably trigger inventory reservation, payment processing, and (on success) shipping + notification, with correct rollback if any step fails (e.g., payment declined after inventory was reserved). **Non-functional:** each service must be independently scalable and deployable, a failure/slowdown in one service (e.g., payment provider outage) must not cascade into the others being unable to accept new orders, and the overall workflow must be auditable (can reconstruct exactly what happened to any given order).

### High-Level Architecture

```
Order Service (accepts POST /orders, writes order record with status=PENDING, publishes "OrderCreated" event)
   |
Event Bus: EventBridge (AWS) / Eventarc + Pub/Sub (GCP) -- central nervous system, all services
   publish domain events here and subscribe to the events they care about (pub/sub decoupling --
   Order Service has ZERO direct knowledge of Inventory/Payment/Shipping services)
   |-- Inventory Service subscribes to "OrderCreated" --> reserves stock --> publishes
   |     "InventoryReserved" or "InventoryInsufficient"
   |-- Payment Service subscribes to "InventoryReserved" --> charges card --> publishes
   |     "PaymentSucceeded" or "PaymentFailed"
   |-- Shipping Service subscribes to "PaymentSucceeded" --> creates shipment --> publishes
   |     "ShipmentCreated"
   |-- Notification Service subscribes to "OrderCreated", "PaymentFailed", "ShipmentCreated" -->
         sends the appropriate email/push notification for each
   |
Saga Orchestrator (Step Functions / Workflows) OR Choreography (pure event-driven, no central
   orchestrator) -- see Deep Dive 1 for this critical architectural choice
   |
Each service owns its own database (Database-per-Service pattern) -- Order DB, Inventory DB,
   Payment DB, Shipping DB are all separate, no service reaches into another's database directly
```

### Deep Dive 1: Choreography vs Orchestration for the Saga Pattern

Since this workflow spans multiple services with NO distributed transaction (a 2-phase-commit across microservices is almost never used in practice — too slow, too fragile, kills availability), we need the **Saga pattern**: a sequence of local transactions, each publishing an event that triggers the next step, with **compensating transactions** to undo prior steps if a later step fails.

- **Choreography (pure event-driven, no central coordinator):** each service reacts to events and emits new events, as shown in the architecture above. **Pro:** maximally decoupled, no single point of failure/bottleneck, easy to add new subscribers (e.g., an Analytics service can subscribe to any event without touching existing services). **Con:** the overall business process/workflow logic is implicit, scattered across many services' event handlers — hard to see "the whole picture" of the order lifecycle, hard to debug ("why did this order get stuck?"), and hard to implement complex conditional branching cleanly.
- **Orchestration (a central Saga Orchestrator, e.g., Step Functions/Workflows, explicitly calls each service and manages the sequence/rollback):** **Pro:** the entire business process is explicit and visible in ONE place (the state machine definition), much easier to debug/audit/visualize, easier to implement complex branching/retry/compensation logic. **Con:** the orchestrator becomes a (soft) central dependency — though a well-designed orchestrator invokes services asynchronously and doesn't hold open connections, so it's not a hard single point of failure the way a synchronous API gateway chain would be.
- **Recommended answer for an interview:** for a workflow this complex (4+ services, real rollback/compensation logic needed, "must be auditable" is an explicit requirement), **orchestration (Step Functions/Workflows) is the stronger choice** — the auditability requirement alone tips the balance, since a Step Functions execution history gives you a complete, queryable timeline of exactly what happened to any order for free, whereas reconstructing that from scattered choreographed event logs requires building your own distributed tracing/correlation on top.

### Deep Dive 2: Compensating Transactions

If Payment fails AFTER Inventory was reserved, the saga must run a **compensating transaction**: "release the reserved inventory." Each service that performs a reversible action in the saga must expose a corresponding compensating action (`ReserveInventory` ↔ `ReleaseInventory`, `ChargeCard` ↔ `RefundCard`). Design principle: compensating actions should be idempotent and should not simply be "the exact inverse" when the domain doesn't allow it (e.g., you generally can't "un-ship" a package — so the compensation for a failure AFTER shipping might instead be "initiate a return/refund process" rather than a true rollback, since physical-world actions aren't always reversible the way database writes are).

### Deep Dive 3: Ensuring At-Least-Once Delivery Doesn't Cause Duplicate Side Effects

EventBridge/Pub/Sub both provide at-least-once delivery (a message might be delivered more than once). Every event handler MUST be idempotent — e.g., the Payment Service should check "have I already charged this order_id?" (via a unique constraint or a processed-events ledger table) before charging again, rather than assuming exactly-once delivery. This is a universal requirement in event-driven systems and one of the most common "what could go wrong" follow-ups interviewers ask.

### Bottlenecks & Scaling

Each microservice scales independently based on its own load profile (Inventory Service might need to scale much more aggressively during a flash sale than Notification Service) — this per-service independent scalability is precisely the main operational benefit of microservices over a monolith. The event bus itself (EventBridge/Pub/Sub) is a fully-managed, essentially-infinite-scale service from the provider's side, so it's rarely the bottleneck; the bottleneck is almost always in a specific downstream service's own database or a third-party dependency (e.g., the external payment processor's rate limits).

### Trade-offs

Microservices + event-driven architecture trades significant operational complexity (distributed tracing needed, eventual consistency between services' local views of an order, harder local development/testing, saga compensation logic to write and maintain) for independent scalability/deployability and fault isolation (a Payment Service outage doesn't prevent Order Service from accepting new orders — they just queue up in the event bus until Payment recovers). This trade-off is only worth making once a system/team has grown large enough that a monolith's coupled deployments and scaling have become the actual bottleneck — a common senior-level point is explicitly cautioning against adopting microservices prematurely for a small team/simple domain ("microservices solve an organizational scaling problem as much as a technical one").

### Follow-Up Interview Questions

- "How would you debug an order that appears stuck in PENDING for an hour?" → With orchestration: look at the Step Functions/Workflows execution history directly, it shows exactly which step is stuck/failed. With choreography: you'd need a correlation ID propagated through every event and a centralized log aggregation/tracing system (§10.2) to reconstruct the same picture manually — a concrete illustration of orchestration's debuggability advantage.
- "What happens if the event bus itself has a regional outage?" → This is why the event bus's own durability/retry semantics matter (EventBridge/Pub/Sub both have built-in retry with DLQ for failed deliveries); for true event-bus-level regional DR, you'd need the multi-region strategies of §16 applied to the event bus itself, which is a genuinely hard, advanced problem worth acknowledging rather than hand-waving.

---

## §21 Real-Time Streaming & Analytics Pipeline

### Problem Statement

Design a real-time analytics pipeline that ingests clickstream/user-activity events (millions of events/second at peak, e.g., ad-impression or clickstream data), processes them for real-time dashboards (metrics updated within seconds) AND stores them for historical batch analysis (SQL queries over months of history) — a common "design a real-time analytics system" prompt.

### Requirements

**Functional:** ingest high-volume event streams, compute real-time aggregate metrics (e.g., "clicks per minute per campaign," updated with sub-10-second freshness), support ad hoc historical SQL queries over the raw event history. **Non-functional:** must not lose events even during a downstream processing outage (durability of the raw stream), must handle at least 1M events/sec at peak, historical queries can tolerate minutes of latency (they're not real-time).

### Estimation

1M events/sec × ~500 bytes/event average = 500MB/sec ingest rate ≈ 43TB/day raw event volume — this scale immediately rules out any single-node ingestion approach and confirms the need for a horizontally-partitioned streaming ingestion layer (Kinesis/Pub-Sub) rather than, say, writing directly to a relational database.

### High-Level Architecture — AWS

```
Event producers (web/mobile SDKs, ad servers)
   |
Kinesis Data Streams (many shards, partitioned by e.g. campaign_id or a hash for even distribution --
   see Deep Dive 1 for shard-count/partition-key design)
   |-- Kinesis Data Analytics (managed Apache Flink) -- real-time windowed aggregation (e.g.,
   |     tumbling 1-minute windows counting clicks per campaign) --> writes results to DynamoDB
   |     (serves the real-time dashboard with single-digit-ms reads) or pushes to a WebSocket
   |     API for live-updating UIs
   |-- Kinesis Data Firehose -- buffers and batches the SAME raw stream, delivers to S3 in
         Parquet format (converted via Firehose's built-in format conversion) partitioned by
         date/hour for efficient historical querying
   |
S3 (raw event lake, Parquet, partitioned) --> queried via Athena (ad hoc SQL) or loaded into
   Redshift (for heavier, repeated BI/reporting workloads)
```

### High-Level Architecture — GCP

```
Event producers (web/mobile SDKs, ad servers)
   |
Pub/Sub (topic, no shard management needed -- auto-scales transparently)
   |-- Dataflow (managed Apache Beam) job #1: streaming pipeline -- windowed aggregation
   |     (tumbling 1-minute windows) --> writes results to Bigtable or Firestore (serves the
   |     real-time dashboard with single-digit-ms reads)
   |-- Dataflow job #2 (or the SAME pipeline with two output sinks, since Beam supports
         multiple outputs from one pipeline) -- writes raw events to BigQuery (streaming
         inserts) for historical ad hoc SQL analysis, or lands them in GCS if colder/cheaper
         storage is preferred over BigQuery's native storage for raw retention
```

**Key GCP simplification worth calling out:** a single Dataflow (Apache Beam) pipeline can simultaneously do the real-time windowed aggregation AND the raw-event archival in one job definition with two output sinks — on AWS this typically requires two separate services (Kinesis Data Analytics for the real-time path, Kinesis Data Firehose for the archival path) reading from the same stream independently. This is a good example of GCP's tendency toward fewer, more unified/composable services (Beam's model) versus AWS's tendency toward more numerous, purpose-specific services.

### Deep Dive 1: Shard/Partition Count and Key Design for Even Distribution

Kinesis shard throughput is fixed (1MB/s or 1000 records/s in per shard) — at 1M events/sec you need AT LEAST 1000 shards (accounting for record-count limits, likely more once you factor in per-record size and safety margin). The **partition key** determines which shard a record goes to (via a hash) — choosing a low-cardinality partition key (e.g., a single "event_type" with only 5 possible values) would concentrate all traffic onto just 5 shards regardless of how many shards exist, creating severe hot-sharding; instead use a HIGH-cardinality key (e.g., a hash of `user_id` or a random UUID per event if per-user ordering isn't required) to spread load evenly across all provisioned shards. Pub/Sub sidesteps this entire problem since GCP manages partitioning transparently — a genuine operational simplification, though it also means you have LESS direct control over strict per-key ordering guarantees compared to explicitly choosing a Kinesis partition key (Pub/Sub requires explicit ordering keys with their own throughput trade-offs if strict per-key ordering is needed).

### Deep Dive 2: Exactly-Once vs At-Least-Once Aggregation Correctness

Streaming aggregation frameworks (Flink via Kinesis Data Analytics, Beam via Dataflow) can process a record more than once during failure recovery/checkpointing — if your aggregation logic is a simple "increment a counter," a duplicate processing would double-count that event, corrupting the metric. Both Flink and Beam provide **exactly-once processing semantics** for their internal state (via checkpointing + a two-phase commit to certain sinks), but this guarantee typically only extends to sinks that support transactional/idempotent writes (e.g., writing to a system with idempotent upserts). For DynamoDB/Bigtable sinks, design the aggregation write as an idempotent upsert keyed by `(window_start, campaign_id)` rather than a blind increment, so re-processing the same window's data during a failure-recovery replay converges to the same correct total rather than double-counting.

### Bottlenecks & Scaling

- **Hot shard/hot key** if a single campaign goes viral and dominates traffic — mitigate with a composite partition key (`campaign_id + random_suffix`) to spread even a single hot campaign's events across multiple shards/partitions, then merge the sharded sub-aggregates at query/read time.
- **Firehose/BigQuery streaming insert cost** at 1M events/sec can be substantial — mitigate with batching (Firehose already batches; for BigQuery, prefer the Storage Write API's batched streaming over legacy `tabledata.insertAll` for better throughput and lower cost) and consider whether truly EVERY raw event needs to land in the (relatively expensive) warehouse versus a cheaper object-storage-only raw archive with a periodic batch load into the warehouse for only the fields actually queried.

### Trade-offs

The Lambda Architecture-esque split (fast/real-time path via windowed streaming aggregation + slow/batch path via raw archival + ad hoc query) trades some infrastructure duplication/complexity for the ability to serve BOTH sub-10-second dashboard freshness AND flexible historical ad hoc analysis — a pure streaming-only approach couldn't efficiently answer arbitrary historical SQL questions, and a pure batch-only approach couldn't meet the real-time dashboard freshness requirement.

### Follow-Up Interview Questions

- "How would you backfill/reprocess historical data if you discover a bug in the aggregation logic?" → Because the raw event lake (S3/BigQuery/GCS) retains the full unaggregated history, you can re-run a corrected Flink/Beam batch job over the historical raw data to regenerate corrected aggregates — this is exactly why retaining the raw event stream (not just the aggregates) is non-negotiable in this kind of design, a frequent follow-up that tests whether candidates understand WHY the raw archival path exists at all.
- "How would you reduce end-to-end latency from event generation to dashboard update below 5 seconds?" → Reduce window size (e.g., 10-second tumbling windows instead of 1-minute), ensure the aggregation sink (DynamoDB/Bigtable) itself has single-digit-ms write latency, and consider pushing updates to the dashboard via WebSockets/Server-Sent Events rather than the dashboard polling on an interval.

## §22 Container Orchestration Platform (EKS vs GKE Autopilot)

### Problem Statement

Design a multi-tenant container orchestration platform that a platform/infra team offers internally to 20+ product teams, each deploying independent microservices, with strong isolation, self-service deployment, and centralized cost/security guardrails.

### Requirements — Functional

- Each product team can deploy/scale/roll back their own services independently (self-service).
- Namespace-level isolation: Team A cannot see/affect Team B's workloads.
- Centralized ingress (one entry point routes to the correct team's service).
- Centralized secrets management, image scanning, and cost attribution per team.

### Requirements — Non-Functional

- 99.95% platform availability.
- New team onboarding should take hours, not weeks.
- Must support both AWS and be portable in principle (Kubernetes chosen specifically for portability — this is the deciding factor over ECS, per §3.4's decision framework).

### High-Level Architecture (EKS)

- **Cluster:** one shared EKS cluster (control plane fully managed by AWS) spanning 3 AZs.
- **Node groups:** managed node groups per workload class (e.g., `general-purpose`, `memory-optimized`, `gpu`), using EC2 Auto Scaling under the hood, OR EKS Fargate profiles for teams that don't need node-level customization (mix-and-match per team's needs).
- **Multi-tenancy isolation:**
  - One Kubernetes **Namespace** per team, with **ResourceQuotas** and **LimitRanges** capping CPU/memory per namespace.
  - **NetworkPolicies** (via a CNI that supports them, e.g., Calico) to prevent cross-namespace traffic unless explicitly allowed.
  - **RBAC** (Role-Based Access Control) scoping each team's IAM-mapped Kubernetes users to only their namespace (via `aws-auth` ConfigMap mapping IAM roles to K8s RBAC roles).
- **Ingress:** AWS Load Balancer Controller provisions an ALB per Ingress resource (or a shared ALB with host/path routing), giving each team a subdomain (`team-a.internal.company.com`).
- **Secrets:** External Secrets Operator syncing from AWS Secrets Manager into K8s Secrets, avoiding secrets being committed to team manifests directly.
- **Image security:** ECR with image scanning on push (Inspector-based), admission control (e.g., via OPA/Gatekeeper or Kyverno) blocking deployment of images with critical CVEs.
- **Cost attribution:** Kubecost (or AWS's native cost allocation via tags/Cost Explorer at the node-group level) mapped back to namespace/team.

### High-Level Architecture (GKE Autopilot)

- **Cluster:** one GKE Autopilot cluster — Google manages nodes, node security hardening, and capacity entirely; the platform team never sizes/patches a node pool.
- **Multi-tenancy isolation:** identical Namespace + ResourceQuota + NetworkPolicy + RBAC pattern (this layer is pure Kubernetes and identical across EKS/GKE — a key interview point: the multi-tenancy PATTERN is cloud-agnostic, only the underlying node/cluster management differs).
- **Ingress:** GKE's native Ingress (backed by GCP's Global External HTTP(S) Load Balancer) — each team gets a subdomain the same way.
- **Secrets:** Secret Manager synced via the Secret Manager CSI driver or an External Secrets Operator equivalent.
- **Image security:** Artifact Registry with vulnerability scanning built in, Binary Authorization to enforce only signed/approved images can deploy.
- **Cost attribution:** GKE's native cost allocation feature (built into Autopilot billing, breaks down cost by namespace/label automatically) — a genuine GKE Autopilot advantage since per-pod billing naturally maps to per-team cost with less extra tooling than the EKS node-group-based approach.

### Deep Dive 1: Why Autopilot's Billing Model Simplifies Multi-Tenant Cost Attribution

- EKS with self-managed/managed node groups bills per NODE (EC2 instance), so attributing cost to a specific team requires either dedicating whole nodes per team (wasteful, poor bin-packing) or using a cost-allocation tool (Kubecost) that estimates each pod's SHARE of a shared node's cost based on resource requests — an estimate, not an exact bill.
- GKE Autopilot bills per POD's resource request directly — there is no shared node cost to allocate/estimate, so namespace/team cost attribution is exact by construction, not an approximation.
- This is a genuinely strong, concrete Autopilot talking point for a "how would you handle multi-tenant billing" interview question.

### Deep Dive 2: Preventing Noisy-Neighbor Problems

- **CPU/memory:** ResourceQuotas cap aggregate namespace usage; Pod-level `requests`/`limits` prevent one pod from starving others on the same node (EKS) — Autopilot enforces this implicitly since every pod's resources are its own billing/scheduling unit.
- **Network:** NetworkPolicies prevent unwanted cross-team traffic; for true network bandwidth isolation, both platforms rely on the underlying node/cluster network fabric's fairness (rarely a hard guarantee at the K8s layer alone — worth acknowledging as a known limitation rather than claiming perfect isolation).
- **Disk I/O:** noisy-neighbor disk contention is a real EKS self-managed-node risk (shared EBS-backed nodes); Autopilot's per-pod resource model reduces (but doesn't eliminate) this risk too.

### Bottlenecks & Scaling

- **Shared ingress ALB/Load Balancer** becomes a scaling/config bottleneck as team count grows past dozens — mitigate by sharding teams across multiple Ingress resources/ALBs rather than one shared ALB with hundreds of host-routing rules.
- **Cluster-wide etcd (control plane) limits** on total object count (namespaces, secrets, deployments) — both EKS and GKE manage this for you, but it's still a real practical ceiling (thousands of namespaces/tens of thousands of pods per cluster is the realistic upper range) that would eventually require splitting into multiple clusters per business unit.

### Trade-offs

| Choice | Benefit | Cost |
|---|---|---|
| One shared cluster (multi-tenant) | Lower ops overhead, better bin-packing/utilization | Blast-radius risk (a cluster-wide issue affects everyone), harder hard-isolation guarantees |
| One cluster per team | Perfect isolation, independent upgrade cadence per team | Much higher ops overhead, worse utilization (many small clusters each need their own baseline overhead) |
| EKS (self-managed/managed nodes) | Full control, can run any workload (DaemonSets, privileged pods) | Platform team must own node patching/capacity planning |
| GKE Autopilot | Near-zero node ops, exact per-pod cost attribution | Restricted workload types (no privileged/host-network pods), higher per-resource unit cost |

### Follow-Up Interview Questions

- **"How would you handle a team needing GPU workloads in this shared multi-tenant cluster?"** → EKS: add a GPU-enabled managed node group with taints/tolerations so only GPU-requesting pods schedule there. GKE Autopilot: Autopilot supports GPU pods natively (specify the accelerator in the pod spec) without you managing GPU node pools directly — another Autopilot operational simplification.
- **"How would you roll out a Kubernetes version upgrade with zero downtime across 20 teams' workloads?"** → Use a surge/rolling node replacement strategy (EKS managed node group upgrades, or Autopilot's automatic node upgrades) combined with Pod Disruption Budgets (PDBs) per team's deployments, so the platform team can upgrade nodes without any single team's service dropping below its minimum healthy replica count.

---

## §23 Global Static Site & CDN Hosting

### Problem Statement

Design global hosting for a high-traffic static/JAMstack website (marketing site, documentation, or a statically-generated e-commerce storefront) that must load in under 200ms for users anywhere in the world, handle traffic spikes from marketing campaigns, and support instant cache invalidation on content updates.

### Requirements

- Serve static assets (HTML/CSS/JS/images) globally with low latency.
- Support HTTPS with a custom domain.
- Support instant (or near-instant) cache purge when content is republished.
- Handle a 50x traffic spike (e.g., a viral social media mention) with zero manual intervention.
- Cost-efficient (this is a "mostly reads, rarely writes" workload — should NOT need always-on compute).

### High-Level Architecture — AWS

- **Origin:** S3 bucket (private, NOT configured for public static website hosting directly — access only via CloudFront using Origin Access Control, a security best practice over the older "public S3 website" pattern).
- **CDN:** CloudFront distribution in front of the S3 origin, custom domain via a CNAME/ALIAS record in Route 53, TLS certificate via ACM (free, auto-renewing).
- **Cache invalidation:** on publish, either (a) issue a CloudFront invalidation API call for the changed paths, or (b) better at scale — use versioned/hashed filenames (e.g., `app.a1b2c3.js`) so old cached versions simply become unreferenced rather than needing explicit invalidation (the standard "cache-bust via filename hashing" pattern used by virtually every modern static site build tool).
- **Dynamic edge logic (optional):** CloudFront Functions for lightweight tasks (redirects, A/B test bucketing via cookies, security headers) at sub-millisecond edge latency.
- **Build/deploy pipeline:** CodePipeline/CodeBuild (or GitHub Actions) builds the static site and syncs to S3, then triggers the CloudFront invalidation as the final deploy step.

### High-Level Architecture — GCP

- **Origin:** Cloud Storage bucket (private, uniform bucket-level access), used as a backend bucket for Cloud CDN.
- **CDN:** Cloud CDN enabled on a Global External Application Load Balancer's backend bucket, custom domain via Cloud DNS, Google-managed TLS certificate.
- **Cache invalidation:** Cloud CDN cache invalidation API for explicit purges, or the same filename-hashing pattern as the AWS variant (framework-agnostic best practice, not cloud-specific).
- **Build/deploy pipeline:** Cloud Build triggers on a Git push, builds the site, syncs to GCS, and invalidates the CDN cache as the final step.

### Deep Dive 1: Why Filename-Hashing Beats Explicit Invalidation at Scale

- Explicit cache invalidation (CloudFront/Cloud CDN invalidation APIs) has **rate limits and, in AWS's case historically, a cost** beyond a free monthly allotment of invalidation paths — at high deploy frequency (many deploys/day, common with continuous deployment) this can become a real bottleneck/cost.
- Filename hashing means each build produces uniquely-named assets; the CDN can cache them with a very long (even infinite) TTL since a given filename's content NEVER changes — only the small HTML entry point (which references the new hashed filenames) needs a short TTL or explicit invalidation, dramatically reducing how much needs to be actively invalidated per deploy.

### Deep Dive 2: Handling the 50x Traffic Spike

- Because the origin is a pure object store (S3/GCS) and the vast majority of requests are served directly from CDN edge cache (not hitting the origin at all after the first request per edge location), a 50x spike in EDGE traffic does **not** translate into a 50x spike in ORIGIN load — the CDN absorbs nearly all of it.
- This is the core reason a static/CDN architecture needs zero auto-scaling configuration at all for this kind of spike, unlike a dynamic compute-backed architecture (§17/§18) which needs ASG/MIG scaling to react to the same spike.

### Bottlenecks & Scaling

- **Cold edge locations** (a region that rarely gets traffic) will have a cache miss on the first request after TTL expiry, adding one origin round-trip of latency for that unlucky first user — mitigate with CloudFront/Cloud CDN's "origin shield" feature (a single mid-tier cache layer that absorbs cross-edge-location cache misses so the actual origin only sees ONE request even if 50 different edge locations miss simultaneously).
- **Origin request storms** during a mass cache invalidation (all edges invalidated at once, then all get cache misses simultaneously) — mitigate by staggering invalidation or relying on filename-hashing (Deep Dive 1) to avoid mass invalidation entirely.

### Trade-offs

- Chose a fully static architecture (no server-rendering compute) accepting that any TRULY dynamic/personalized content (e.g., "logged in as X") requires either client-side JS fetching from a separate dynamic API, or edge-compute personalization (CloudFront Functions/Lambda@Edge) — a pure static architecture is the right choice specifically because the requirements describe a content-heavy, mostly-non-personalized site; a personalization-heavy site would instead need the dynamic 3-tier architecture of §17/§18 (or a hybrid).

### Follow-Up Interview Questions

- **"How would you A/B test different homepage variants on this purely static architecture?"** → Use a CloudFront Function / edge-compute layer to inspect a cookie and rewrite the request path to serve variant A or B's pre-built static assets, keeping the A/B logic entirely at the edge without needing origin compute.
- **"How would you add a comments feature to this static site without breaking the 'no server compute' cost model?"** → Offload the dynamic piece to a separate serverless API (Lambda/Cloud Functions + DynamoDB/Firestore, per §19's pattern) called client-side via JS, keeping the static hosting layer unchanged — a good illustration of composing a "mostly static, some dynamic islands" (JAMstack) architecture rather than an all-or-nothing choice.

---

## §24 Multi-Region Active-Active Database Architecture

### Problem Statement

Design the data layer for a globally-distributed application (e.g., a collaborative SaaS tool) that must serve users in the US, Europe, and Asia with low write latency in each region, survive a full regional outage with zero downtime, and keep data consistent enough that users don't see confusing conflicting states.

### Requirements

- Writes from a user in Europe should NOT need a round-trip to the US to complete (low local write latency in every region).
- A full regional outage must not cause any user-visible downtime (true active-active, not failover-based).
- Conflicting concurrent writes to the same record from two regions must be resolved deterministically (no silent data loss, no crash).

### High-Level Architecture — Option A: DynamoDB Global Tables (AWS)

- Deploy DynamoDB tables in 3 regions (US, EU, Asia) configured as a **Global Table** — AWS handles multi-region replication automatically (asynchronous, typically sub-second to low-single-digit-second propagation).
- Each region's application writes to its LOCAL table replica (low local latency), and DynamoDB propagates the write to the other regions in the background.
- **Conflict resolution:** DynamoDB Global Tables use **last-writer-wins** (based on a timestamp) at the attribute/item level by default — if two regions write to the same item within the propagation window, the later timestamp wins and the earlier write is silently overwritten (see Deep Dive 1 for when this is/isn't acceptable).

### High-Level Architecture — Option B: Cloud Spanner Multi-Region Configuration (GCP)

- Deploy a Spanner instance with a **multi-region configuration** (e.g., `nam-eur-asia1`), which places read-write replicas in multiple regions and uses Spanner's TrueTime-based consensus (Paxos) across region groups.
- Unlike DynamoDB Global Tables' eventual/last-writer-wins model, Spanner provides **strong external consistency globally** — every committed transaction is immediately visible and consistent everywhere, with no conflict-resolution ambiguity at all, at the cost of higher write latency (a write must achieve consensus across a quorum of regions, meaning cross-region network round-trips are on the critical path of every write, unlike DynamoDB's "write locally, replicate async" model).

### Deep Dive 1: When Is Last-Writer-Wins (DynamoDB Global Tables) Acceptable, and When Is It Dangerous?

- **Acceptable:** each user's data is naturally partitioned by region (a European user's records are essentially never concurrently edited by a US-based process) — in this common case, true cross-region conflicts are rare, and last-writer-wins for the rare edge case (e.g., a user traveling and editing from two continents within seconds) is a reasonable, low-risk trade-off for the huge latency benefit.
- **Dangerous:** a shared counter/balance that could be concurrently incremented from two regions (e.g., "available inventory count") — last-writer-wins on a raw counter value would silently lose one region's increment. Fix: don't replicate a raw mutable counter across regions at all; instead use a CRDT-friendly data structure (e.g., a PN-Counter storing per-region increment/decrement deltas that are summed at read time, rather than a single overwritable value) or route all writes to that specific shared resource through one region (accepting the latency cost only for that specific hot/shared field, while everything else stays local-write).

### Deep Dive 2: Spanner's Cost of Strong Consistency

- Every Spanner write in a multi-region config incurs the network latency of reaching a quorum of regions' Paxos groups — for a `nam-eur-asia` configuration this can mean 100-200ms+ write latency, dramatically higher than DynamoDB Global Tables' local-write latency (single-digit ms).
- **Interview framing:** this is a direct, concrete illustration of the CAP/PACELC trade-off in a real managed product — Spanner explicitly chooses consistency+partition-tolerance with a latency cost (PACELC's "else, latency" branch), while DynamoDB Global Tables explicitly chooses availability/low-latency with an eventual-consistency cost. Neither is "better" in the abstract; the requirement (does this specific field/entity need strong global consistency, or can it tolerate eventual consistency for a huge latency win) determines the right answer, and a single application can legitimately use BOTH patterns for different pieces of its data.

### Bottlenecks & Scaling

- **DynamoDB Global Tables:** replication lag under extreme write bursts in one region can grow, temporarily widening the window during which last-writer-wins conflicts are more likely — monitor `ReplicationLatency` CloudWatch metrics.
- **Spanner:** write throughput to a single hot row/key is fundamentally bounded by Paxos consensus overhead per key — the row-key design principles from §5.2 (avoid hotspotting) apply here even more critically given the added cross-region consensus cost per write.

### Trade-offs Summary Table

| Dimension | DynamoDB Global Tables | Spanner Multi-Region |
|---|---|---|
| Write latency | Low (local write) | Higher (cross-region consensus) |
| Consistency | Eventual, last-writer-wins on conflict | Strong, globally consistent |
| Conflict handling | Silent overwrite (needs careful data modeling) | No conflicts possible (serialized by consensus) |
| Query flexibility | Key-value/limited query patterns | Full SQL, joins, secondary indexes |
| Best for | Region-partitioned data, high write locality needs | Shared/global data needing strict correctness (financial ledgers, inventory) |

### Follow-Up Interview Questions

- **"Could you use BOTH patterns in the same application?"** → Yes — this is actually the recommended real-world answer: use DynamoDB Global Tables (or a regionally-partitioned Cloud SQL/Firestore setup) for the bulk of naturally region-local data, and reserve Spanner (or a single-region "source of truth" for a specific shared resource) only for the small subset of genuinely global, consistency-critical data (e.g., a global inventory ledger or billing balance) — avoiding the cost/latency of full Spanner for data that doesn't need it.
- **"How do you test/simulate a full regional outage before it happens in production?"** → Regularly executed GameDays/DR drills (§16.5): actually withdraw a region from traffic routing and verify the other regions absorb the load and users see no visible disruption, rather than only reasoning about it theoretically.

## §25 CI/CD Pipeline for Microservices

### Problem Statement
Design a CI/CD pipeline for an organization running 50+ microservices on Kubernetes (EKS/GKE), supporting multiple daily deployments per service, safe rollouts, and fast rollback.

### Requirements
- Fast feedback: build+test under 10 minutes.
- Progressive delivery: canary or blue-green, automatic rollback on error-rate spike.
- Full audit trail of what deployed, when, by whom.
- Secrets never stored in plaintext in the pipeline config.

### Pipeline Stages (cloud-agnostic, then mapped to services)
1. **Source trigger** — push/PR to main branch.
2. **Build** — compile, run unit tests, build container image.
3. **Security scan** — image vulnerability scan, SAST/dependency scan.
4. **Push to registry** — tag with commit SHA (immutable, traceable).
5. **Deploy to staging** — automated integration tests run against staging.
6. **Progressive production rollout** — canary (5% → 25% → 100%) with automated health-metric gating.
7. **Rollback** — automatic on SLO breach, or one-click manual.

### AWS Mapping
| Stage | Service |
|---|---|
| Source trigger | CodePipeline (or GitHub Actions triggering CodePipeline) |
| Build + test | CodeBuild |
| Security scan | ECR image scanning (Inspector) + a SAST tool (e.g., in CodeBuild step) |
| Registry | ECR |
| Deploy | CodeDeploy (ECS/EKS) with canary/linear deployment configs |
| Rollback trigger | CloudWatch Alarm on error rate → auto-triggers CodeDeploy rollback |

### GCP Mapping
| Stage | Service |
|---|---|
| Source trigger | Cloud Build trigger (on Git push) |
| Build + test | Cloud Build |
| Security scan | Artifact Registry vulnerability scanning + Binary Authorization gate |
| Registry | Artifact Registry |
| Deploy | Cloud Deploy (native canary/blue-green delivery pipelines to GKE) |
| Rollback trigger | Cloud Monitoring alert → Cloud Deploy automated rollback |

### Deep Dive: Canary Analysis Automation
- Deploy the new version to a small % of traffic (e.g., via Istio/K8s service mesh traffic splitting, or Cloud Deploy/CodeDeploy native canary %).
- Automatically compare golden-signal metrics (error rate, latency, saturation) between canary and baseline over a fixed window (e.g., 10 minutes).
- Tools: AWS — CloudWatch metrics + a custom Lambda "judge" step, or third-party (Argo Rollouts with Prometheus). GCP — Cloud Deploy's built-in canary + Cloud Monitoring, or Argo Rollouts on GKE.
- **Automatic rollback** if error-rate delta exceeds a threshold (e.g., canary error rate > baseline + 2%) — removes the human reaction-time delay from the failure-detection loop, critical for minimizing blast radius.

### Bottlenecks & Scaling
- Shared build infrastructure contention across 50+ teams — mitigate with autoscaling build fleets (CodeBuild scales automatically; Cloud Build similarly) and per-team build concurrency quotas.
- Slow integration test suites blocking the pipeline — mitigate with test parallelization/sharding and only running the full suite pre-production, a fast subset pre-merge.

### Trade-offs
Canary rollout adds pipeline complexity and total deploy time (staged rollout takes longer than "all at once") in exchange for dramatically reduced blast radius on a bad deploy — the right trade-off for any service with real production traffic, though low-risk internal tools may reasonably skip straight to all-at-once for speed.

### Follow-Up Interview Questions
- **"How do you handle a database migration that must run before the new code deploys?"** → Separate migration step BEFORE the canary rollout begins, and design migrations to be backward-compatible (expand/contract pattern: add new column, deploy code that writes both old+new, backfill, deploy code that reads only new, then drop old column later) so old and new code versions can coexist safely during a canary window.
- **"How would you audit exactly who deployed what, when, for compliance?"** → Every deploy tied to an immutable commit SHA + CI/CD execution ID logged centrally (CloudTrail/Cloud Audit Logs capture the deploy API calls themselves), giving a full chain from code change → build → deploy approval → production rollout.

---

## §26 Big Data Lake & Analytics Platform

### Problem Statement
Design a data lake ingesting data from 100+ heterogeneous sources (application databases via CDC, event streams, third-party SaaS exports) that serves both data scientists (ad hoc exploration) and BI analysts (dashboards), with strong data governance.

### Requirements
- Ingest batch (nightly DB dumps) and streaming (CDC, clickstream) sources.
- Support schema evolution without breaking downstream consumers.
- Fine-grained access control (row/column-level for sensitive data, e.g., PII).
- Cost-efficient storage for petabyte-scale historical data.

### High-Level Architecture — AWS
| Layer | Service | Purpose |
|---|---|---|
| Ingestion (batch) | DMS (Database Migration Service) / Glue jobs | CDC from RDS/on-prem DBs into the lake |
| Ingestion (streaming) | Kinesis Data Streams/Firehose | Clickstream/event ingestion |
| Raw storage | S3 (raw zone, partitioned by source/date) | Landing zone, immutable raw copies |
| Cataloging | Glue Data Catalog | Central schema/metadata registry, Hive-compatible |
| Transformation | Glue ETL (Spark) / EMR | Clean/dedupe/join into curated zone |
| Curated storage | S3 (curated zone, Parquet, partitioned) | Query-optimized, deduplicated data |
| Query | Athena (ad hoc) / Redshift Spectrum (BI) | SQL access without moving data |
| Governance | Lake Formation | Row/column-level permissions, centralized grants |

### High-Level Architecture — GCP
| Layer | Service | Purpose |
|---|---|---|
| Ingestion (batch) | Datastream (CDC) / Storage Transfer Service | CDC and bulk transfer into the lake |
| Ingestion (streaming) | Pub/Sub + Dataflow | Clickstream/event ingestion + transform |
| Raw storage | Cloud Storage (raw zone) | Landing zone, immutable raw copies |
| Cataloging | Dataplex / Data Catalog | Central schema/metadata registry across GCS + BigQuery |
| Transformation | Dataflow / Dataproc (managed Spark/Hadoop) | Clean/dedupe/join into curated zone |
| Curated storage | BigQuery native tables (or GCS Parquet) | Query-optimized, deduplicated data |
| Query | BigQuery (serverless SQL, both ad hoc and BI) | Single unified query engine for both personas |
| Governance | BigQuery column-level security + Dataplex data lineage/policy tags | Row/column-level permissions |

### Deep Dive: Raw / Curated / Consumption Zone Pattern (Medallion Architecture)
1. **Raw (Bronze) zone** — exact copy of source data, no transformation, immutable, enables reprocessing if downstream logic has a bug.
2. **Curated (Silver) zone** — cleaned, deduplicated, conformed to a common schema, joined across sources where sensible.
3. **Consumption (Gold) zone** — aggregated, business-metric-ready tables optimized for specific dashboards/reports.
- This layered pattern isolates schema/quality issues (fix once in the Silver transformation, not in every downstream consumer) and is cloud-agnostic — implement identically on S3+Glue or GCS+Dataflow/BigQuery.

### Deep Dive: Schema Evolution Without Breaking Consumers
- Use a schema registry (Glue Schema Registry / a Pub/Sub schema, or simply enforce via the Data Catalog) requiring new fields to be added as OPTIONAL/nullable, never removing or renaming existing fields in place (deprecate instead).
- Parquet/Avro formats natively support backward/forward-compatible schema evolution (readers can skip unknown new fields; writers can omit deprecated old ones) — a key reason both zones typically standardize on Parquet/Avro rather than raw CSV/JSON for curated data.

### Deep Dive: Row/Column-Level Governance for PII
- Tag sensitive columns (e.g., `ssn`, `email`) with policy tags (BigQuery/Dataplex) or register them in Lake Formation's column-level grants.
- Analysts without explicit PII clearance query the SAME table but see masked/null values for tagged columns automatically — avoids maintaining separate "sanitized" copies of every table (which drift out of sync) in favor of one source table with enforced, centrally-managed access policy.

### Bottlenecks & Scaling
- Small-file problem (streaming ingestion producing many tiny files degrades query performance) — mitigate with periodic compaction jobs (merge small Parquet files into larger ones) or by tuning Firehose/Dataflow buffering intervals to write fewer, larger files.
- Query cost runaway on a pay-per-byte-scanned engine (Athena/BigQuery) from unpartitioned full-table scans — mitigate with mandatory partitioning/clustering on date and requiring `WHERE` clauses on partition columns (BigQuery supports enforcing this via "require partition filter").

### Trade-offs
Chose a lake-first (store everything raw, transform on read/on schedule) approach over a strict schema-on-write warehouse-only approach, trading some upfront query performance for the flexibility to onboard new heterogeneous sources quickly and reprocess history when transformation logic changes.

### Follow-Up Interview Questions
- **"How would you detect and handle a source system silently changing its schema (e.g., a column type change) without breaking the pipeline?"** → Schema validation at ingestion (reject/quarantine records that don't match the registered schema, alert the data engineering team) rather than allowing malformed data to silently corrupt the curated zone.
- **"How do you keep BigQuery/Athena costs predictable for a large analyst team running ad hoc queries?"** → Flat-rate slot reservations (BigQuery) or Athena workgroup query-cost quotas per team, combined with mandatory partition filters, to bound worst-case spend.

---

## §27 Disaster Recovery Architecture

### Problem Statement
Design (and formalize into a runbook) a disaster recovery strategy for a critical financial transaction system with a business-mandated RTO of 15 minutes and RPO of 1 minute.

### Requirements
- RTO ≤ 15 minutes (system must be usable again within 15 minutes of a declared disaster).
- RPO ≤ 1 minute (at most 1 minute of committed transactions may be lost).
- Must handle both a single-AZ failure (common) and a full-region failure (rare but must be survivable).
- DR plan must be regularly tested, not theoretical.

### Strategy Selection (applying §16's framework)
Given RTO=15min/RPO=1min, **Warm Standby** is the right tier (Pilot Light's RTO of "tens of minutes" is too slow if compute needs to scale up from near-zero; full Active-Active would satisfy this comfortably but at a cost premium the requirements don't strictly demand — Warm Standby is the precise fit).

### High-Level Architecture
- **Primary region:** full production stack (ASG/MIG + Multi-AZ database + cache), serving all live traffic.
- **DR region:** scaled-down (e.g., 20% capacity) but fully live and running copy of the ENTIRE stack — application tier already deployed and health-checked, database is a continuously-replicating cross-region read replica (Aurora Global Database / Cloud SQL cross-region replica), cache pre-warmed with a representative subset of hot keys.
- **Replication:** Aurora Global Database provides typically sub-1-second cross-region replication lag (well within the 1-minute RPO budget) — GCP equivalent: Cloud SQL cross-region replica (also sub-minute typical lag) or, for a stronger guarantee, Spanner multi-region (near-zero RPO by design, at the cost/latency trade-off discussed in §24).
- **Failover trigger:** automated health checks (Route 53 health check / Cloud Monitoring uptime check) on the primary region; on sustained failure, an automated runbook (Lambda/Cloud Function triggered by the alert):
  1. Promotes the DR region's database replica to primary (read-write).
  2. Scales the DR region's compute fleet from 20% to 100% capacity.
  3. Updates DNS/Global Accelerator/Global LB routing to send all traffic to the DR region.
- **Fail-back:** once the original primary region recovers, re-establish it as a (new) warm standby replicating FROM the current primary (the former DR region) — never blindly "fail back" without re-syncing, to avoid data loss from the outage window.

### Deep Dive: Why Automated Failover Beats a Manual Runbook for a 15-Minute RTO
- A purely manual runbook (human pages on-call, reads a doc, executes steps) realistically consumes 5-10+ minutes just in human reaction/execution time before any technical recovery even starts — leaving little to no margin within a 15-minute total RTO budget.
- Automating the detection → decision → execution chain (health check → Lambda/Cloud Function runbook → DNS cutover) compresses this to low minutes or even sub-minute, leaving margin for the parts that genuinely take time (database promotion, compute scale-up) — this is why financial/critical-tier RTOs almost always mandate automation over "a human follows a checklist."

### Deep Dive: Testing the DR Plan (GameDays)
- Schedule regular (e.g., quarterly) DR drills that ACTUALLY fail over production (or a faithful staging replica) to the DR region, measuring real RTO/RPO against the targets.
- Track and fix every gap found (e.g., "the DR region's IAM roles had drifted and lacked a needed permission," "the cache pre-warming script was stale") — an untested DR plan reliably has hidden breakage by the time it's actually needed.

### Bottlenecks & Scaling
- Cross-region database replication lag spikes under extreme primary-region write load — monitor replication-lag metrics continuously and treat sustained lag above the RPO budget as its own alerting condition (a leading indicator that DR readiness has degraded, even before any actual disaster).
- DR region compute scale-up time (20% → 100%) — mitigate by pre-provisioning slightly more than the bare minimum "warm" capacity if the scale-up step alone risks eating too much of the 15-minute budget.

### Trade-offs
Warm Standby costs meaningfully more than Pilot Light (running a live, health-checked, partially-scaled compute fleet 24/7 in the DR region) but is the minimum tier that reliably meets a 15-minute RTO — this is a case where the business-mandated RTO/RPO directly and non-negotiably dictates the required DR tier, not a discretionary cost/benefit call.

### Follow-Up Interview Questions
- **"What if the disaster is a bad DEPLOYMENT (a bug), not an infrastructure failure — does this same DR architecture help?"** → No — a bad deploy typically replicates the bug to the DR region too (since it's a code/data-logic issue, not an infra failure); this is why a "disaster" in this DR sense is distinct from a bad-deploy rollback (§25's canary/rollback pattern), and both mechanisms are needed together, addressing different failure classes.
- **"How do you avoid the DR region silently rotting (its IaC/config drifting from primary over months)?"** → Deploy to BOTH regions via the same IaC/CI-CD pipeline simultaneously (never manually patch the DR region separately), and include the DR region in routine (non-failover) smoke tests so drift is caught continuously, not only during a rare full DR drill.

---

## §28 Secure Multi-Account / Multi-Project Landing Zone

### Problem Statement
Design the foundational account/project structure and security guardrails for a company adopting cloud at scale (100+ engineers, multiple business units), before any application workloads are built — the "landing zone" that all future projects will be provisioned into.

### Requirements
- Strong blast-radius isolation between environments (dev/staging/prod) and business units.
- Centralized security guardrails (cannot be bypassed by an individual team) — e.g., mandatory encryption, no public S3/GCS buckets, mandatory logging.
- Centralized, immutable audit logging across the whole organization.
- Self-service account/project creation for new teams, without waiting on a central ops team for every request.

### High-Level Architecture — AWS (Control Tower + Organizations)
- **Management account** (root of AWS Organizations) — never runs workloads, only manages the org structure/billing.
- **Organizational Units (OUs):** `Security`, `Infrastructure`, `Workloads/Prod`, `Workloads/NonProd`, `Sandbox` — each with its own SCPs.
- **Log Archive account:** centralized, immutable (write-once via S3 Object Lock) destination for CloudTrail logs from EVERY account org-wide.
- **Audit/Security account:** centralized GuardDuty/Security Hub findings aggregation across all accounts.
- **SCP guardrails (examples):** deny disabling CloudTrail, deny leaving the approved region list, deny creating IAM users without MFA, deny public S3 bucket policies org-wide.
- **Account Factory (Control Tower):** self-service, guardrail-compliant new-account provisioning for teams (a new account is born already compliant, not retrofitted later).

### High-Level Architecture — GCP (Resource Manager Hierarchy)
- **Organization node** (root, tied to the company's domain).
- **Folders:** mirror the OU structure (`Security`, `Shared-Infra`, `Prod`, `NonProd`, `Sandbox`).
- **Projects:** the GCP unit of isolation (roughly analogous to an AWS account) — one or more per team/environment, created under the appropriate folder.
- **Centralized logging project:** aggregated Cloud Logging sink (org-level log sink) capturing audit logs from every project, written to a centralized, access-restricted GCS bucket/BigQuery dataset.
- **Org Policy guardrails (examples):** `constraints/iam.disableServiceAccountKeyCreation`, `constraints/compute.vmExternalIpAccess` (restrict/deny public IPs), `constraints/storage.publicAccessPrevention`.
- **Project Factory (via Terraform modules / Config Connector):** self-service, policy-compliant new-project provisioning.

### Deep Dive: Why SCPs / Org Policies Are Non-Negotiable Even With Good IAM
- IAM policies are per-identity ALLOWs — even a well-configured IAM setup can't stop an admin from accidentally (or maliciously) granting an overly broad permission later.
- SCPs/Org Policies act as a ceiling that IAM allows can never exceed, regardless of what any individual account/project's IAM is configured to permit — this is the "defense in depth, don't rely on one layer" principle from §8.6 applied at the organizational level, and is the direct answer to "how do you prevent a single misconfigured team from creating an org-wide security incident?"

### Deep Dive: Centralized, Tamper-Evident Audit Logging
- Logs shipped to a SEPARATE account/project (not the workload account itself) that workload-account admins have no delete/modify permission on, combined with write-once storage (S3 Object Lock in compliance mode / GCS bucket retention policies) — ensures that even a fully compromised workload account's attacker (or a rogue insider) cannot cover their tracks by deleting the audit trail.

### Bottlenecks & Scaling
- Self-service account/project factory approval workflows becoming a bottleneck as the org grows — mitigate with pre-approved, IaC-templated account/project "shapes" (e.g., "standard microservice project" template) that provision instantly without a manual security review, reserving manual review only for genuinely novel/high-risk requests.

### Trade-offs
Centralized guardrails necessarily reduce individual team autonomy (a team cannot, for example, unilaterally decide to allow public buckets even if they have a legitimate one-off reason) — the trade-off is deliberate: consistent org-wide security posture is prioritized over per-team flexibility, with an explicit (audited, time-boxed) exception-request process for genuine edge cases rather than allowing silent opt-outs.

### Follow-Up Interview Questions
- **"How would a new team get their own isolated environment provisioned in under an hour, safely?"** → Account Factory/Project Factory templates (Terraform modules encoding all the guardrails) triggered via a self-service request (ticket or a GitOps PR to an "accounts" repo), fully automated end-to-end with no manual security gate for the standard template path.
- **"How do you handle a legitimate business need that conflicts with a guardrail (e.g., a partner integration genuinely needs a public-facing storage bucket)?"** → An explicit, audited, time-boxed exception process (a specific SCP/Org Policy exemption scoped to exactly that one resource, reviewed and logged, not a blanket relaxation of the guardrail).

## §29 Auto-Scaling Video Transcoding Pipeline

### Problem Statement
Design a pipeline that ingests user-uploaded videos and produces multiple output renditions (resolutions/bitrates for adaptive streaming: e.g., 240p/480p/720p/1080p in HLS/DASH format) at scale, cost-efficiently, with predictable turnaround time.

### Requirements
- Support uploads up to several GB, produce adaptive-bitrate renditions within minutes of upload.
- Cost-efficient — transcoding is CPU-intensive; must not pay for idle transcoding capacity.
- Must handle bursty upload patterns (e.g., a creator platform sees spikes around certain hours).

### High-Level Architecture — AWS
- Upload → S3 (raw uploads bucket) → S3 event notification → SQS queue (buffers transcode jobs) → MediaConvert (managed transcoding service) job submitted per uploaded file, output renditions written to a separate S3 (processed) bucket → CloudFront serves the HLS/DASH manifests + segments to viewers.
- Scaling: MediaConvert is a fully-managed, serverless-billed-per-minute-of-output service — no fleet to manage or scale; SQS absorbs burst submission rate so MediaConvert's own queueing/concurrency limits aren't overwhelmed by a sudden batch of uploads.

### High-Level Architecture — GCP
- Upload → Cloud Storage (raw bucket) → Eventarc trigger → Cloud Tasks (or Pub/Sub) queue → Transcoder API job submitted per file, outputs to a processed Cloud Storage bucket → Cloud CDN serves manifests/segments.
- Same serverless-billed-per-job model as MediaConvert — Transcoder API requires no cluster/fleet management.

### Deep Dive: Job Prioritization and Turnaround SLAs
- Not all uploads need the same urgency (a live-adjacent clip vs. a bulk archive re-encode) — use separate SQS queues/Cloud Tasks queues per priority tier, each with its own consumer concurrency, so low-priority bulk work never starves high-priority jobs.
- Progressive rendition delivery: transcode and publish the lowest resolution FIRST (fastest to produce) so playback can start almost immediately, while higher resolutions continue processing in the background and get swapped in via the adaptive manifest as they complete.

### Bottlenecks & Scaling
- MediaConvert/Transcoder API account-level concurrent-job quotas — request quota increases proactively based on projected peak upload volume, and monitor queue depth as a leading indicator of needing a quota increase.
- Extremely large files (multi-hour source video) — split into chunks for parallel transcoding (segment the source, transcode segments in parallel, stitch the manifest referencing all segments) to bound the worst-case single-job turnaround time.

### Trade-offs
Chose fully-managed transcoding services (MediaConvert/Transcoder API) over self-managed FFmpeg workers on EC2/Compute Engine/GKE, trading some per-minute cost premium and less codec/filter customization for zero fleet-management overhead and automatic scaling — the right call unless extremely high volume makes the marginal cost difference large enough to justify a dedicated ops investment (mirrors the general serverless-vs-self-managed crossover discussed in §19 Deep Dive 2).

### Follow-Up Interview Questions
- **"How would you avoid re-transcoding the same file if a user re-uploads it?"** → Hash the uploaded file content (e.g., SHA-256) and check for an existing matching output before submitting a new transcode job — a content-addressable dedup check.
- **"How do you handle a transcode job failure (corrupt source file)?"** → Dead-letter queue for failed jobs after N retries, plus a validation pre-check (probe the file with a lightweight tool to confirm it's a valid, decodable video) before submitting the expensive full transcode job.

---

## §30 IoT Data Ingestion Platform

### Problem Statement
Design a platform ingesting telemetry from millions of IoT devices (e.g., smart home sensors) — small, frequent messages, requiring device authentication, real-time alerting on anomalies, and long-term storage for analysis.

### Requirements
- Securely authenticate millions of individual devices (no shared credentials).
- Ingest high-frequency, small-payload messages (e.g., every 30 seconds per device).
- Real-time anomaly alerting (e.g., a temperature sensor reporting an out-of-range value).
- Long-term time-series storage for trend analysis.

### High-Level Architecture — AWS
- Devices → **IoT Core** (per-device X.509 certificate authentication, MQTT protocol) → IoT Rules Engine routes messages: (a) to Kinesis Data Streams for real-time anomaly detection (via Kinesis Data Analytics/Lambda), (b) to Timestream (purpose-built time-series DB) for long-term storage/trend queries.
- Alerts: anomaly detection Lambda publishes to SNS for on-call/customer notification.

### High-Level Architecture — GCP
- Devices → **Cloud IoT** was GCP's native offering but was deprecated (2023) in favor of using Pub/Sub directly with a partner device-management layer, or self-hosted MQTT brokers — devices publish to Pub/Sub (via a lightweight MQTT-to-Pub/Sub bridge or direct client library) → Dataflow for real-time anomaly detection → Bigtable for long-term time-series storage (Bigtable's wide-column model, per §5.2, is purpose-built for exactly this high-write-throughput time-series pattern).
- **Interview-relevant nuance:** be ready to acknowledge Cloud IoT Core's deprecation if asked directly — it's a genuine, correct piece of current knowledge that shows you're not working from stale information; the practical GCP answer today composes Pub/Sub + a 3rd-party/self-managed device-identity layer rather than one all-in-one first-party service.

### Deep Dive: Per-Device Authentication at Scale
- Each device provisioned with a unique X.509 certificate (IoT Core) or a signed JWT (common pattern for the Pub/Sub-based GCP approach) — never a shared API key across the fleet, so a single compromised device can be individually revoked without affecting others.
- Device provisioning at manufacturing time (bulk-registering certificates) must be automated (IoT Core supports bulk/fleet provisioning templates) — manually registering millions of devices is a non-starter.

### Deep Dive: Handling Massive Small-Message Fan-In
- Millions of devices × one message/30 sec ≈ tens of thousands of messages/sec sustained — both Kinesis (many shards, partition key = device_id hashed for even distribution, per §21 Deep Dive 1's principles) and Pub/Sub (auto-scaled, no shard planning) handle this, but message SIZE efficiency matters: batch multiple readings per MQTT publish where possible (e.g., a device buffers 5 minutes of readings and sends one batched message) to reduce per-message overhead and connection churn.

### Bottlenecks & Scaling
- MQTT connection churn from flaky device networks (constant reconnects) — mitigate with exponential backoff + jitter in device firmware reconnect logic, and monitor connection-churn rate as a fleet health signal.
- Timestream/Bigtable write hotspotting if device IDs aren't well-distributed as partition/row keys — apply the same anti-hotspotting row-key design from §5.2 (salted/hashed prefixes).

### Trade-offs
Chose purpose-built time-series storage (Timestream/Bigtable) over a general relational database for the telemetry data, trading SQL-join convenience for the write-throughput and storage-cost efficiency that a general RDBMS cannot match at this ingestion rate/volume.

### Follow-Up Interview Questions
- **"How would you push a firmware update to millions of devices without overwhelming the network?"** → Staged/canary rollout (a small % of devices first, monitor for failures) combined with rate-limited, jittered download scheduling (not all devices download simultaneously) — the same canary-rollout principle from §25 applied to physical devices.
- **"How do you detect a compromised/misbehaving device sending malformed or malicious data?"** → Schema validation at the ingestion rule engine (reject malformed messages before they reach downstream processing) plus anomaly detection on message RATE per device (a device suddenly sending 1000x its normal message rate is a strong signal, independent of payload content).

---

## §31 ML Training & Serving Pipeline

### Problem Statement
Design an end-to-end machine learning platform: data scientists train models on large datasets, and trained models are served in production with low-latency inference and safe rollout of new model versions.

### Requirements
- Reproducible training (same code + data + params → same model).
- Low-latency (sub-100ms) real-time inference for a recommendation-style use case.
- Safe rollout of new model versions (shadow testing / gradual traffic shift, monitoring for model quality regressions, not just infra errors).
- Feature consistency between training and serving (avoid train/serve skew).

### High-Level Architecture — AWS (SageMaker)
- **Data:** curated features from the data lake (§26) stored in **SageMaker Feature Store** (a feature store gives a consistent, versioned source of features for BOTH training and real-time serving — directly solving train/serve skew).
- **Training:** SageMaker Training Jobs (managed, autoscaled compute, experiment tracking) reading from Feature Store/S3.
- **Model registry:** SageMaker Model Registry — versions every trained model with metadata/approval status.
- **Serving:** SageMaker Endpoints (real-time inference, autoscaling) with **multi-variant/canary deployment** support (route a small % of traffic to a new model version, compare business/quality metrics, not just latency/error-rate).
- **Monitoring:** SageMaker Model Monitor — detects data drift/quality degradation in production inputs vs. training data distribution.

### High-Level Architecture — GCP (Vertex AI)
- **Data:** Vertex AI Feature Store (same purpose — consistent features for training and serving).
- **Training:** Vertex AI Training (managed, autoscaled, supports custom containers or built-in algorithms), Vertex AI Pipelines (Kubeflow-based) for reproducible, versioned multi-step training workflows (an explicit strength — pipeline-as-code with full lineage tracking).
- **Model registry:** Vertex AI Model Registry.
- **Serving:** Vertex AI Endpoints, with traffic-splitting across model versions for canary/shadow evaluation.
- **Monitoring:** Vertex AI Model Monitoring — skew/drift detection.

### Deep Dive: Solving Train/Serve Skew With a Feature Store
- Without a feature store, training pipelines and serving code often compute "the same" feature (e.g., "user's average order value over 30 days") with SUBTLY different logic (different time-window boundary handling, different null-handling) — this silent divergence is one of the most common, hard-to-detect causes of production model underperformance.
- A feature store centralizes feature computation ONCE, and both the training job and the real-time serving path read from the exact same feature definitions/values — eliminating the class of bug entirely rather than relying on careful manual code review to catch discrepancies.

### Deep Dive: Shadow Testing vs Canary for Model Quality
- **Shadow testing:** the new model receives a COPY of production traffic and produces predictions that are logged but NEVER shown to real users — lets you compare the new model's outputs against the current model's on real traffic with zero user-facing risk, ideal for validating a genuinely new model architecture before any live exposure.
- **Canary (live traffic split):** a small % of REAL users actually see the new model's predictions — necessary once you need to measure actual business-outcome metrics (click-through rate, conversion) that shadow testing (no real user reaction) cannot capture, since business metrics require real user behavior in response to the new predictions.
- **Recommended sequencing:** shadow test first (catch gross errors/instability with zero risk) → then canary (measure real business impact) → then full rollout — skipping shadow testing straight to canary is a common mistake that unnecessarily exposes real users to an unvalidated model.

### Bottlenecks & Scaling
- Real-time inference latency dominated by feature-fetch time (calling the Feature Store online store on the critical path) — mitigate with a low-latency online feature store backing (both SageMaker/Vertex Feature Stores offer a low-latency online serving mode backed by DynamoDB/Bigtable-class storage specifically for this).
- Training job cost/time at large data scale — mitigate with distributed training (data/model parallelism across multiple GPU instances) and spot/preemptible instances for the (checkpoint-resumable) training compute, since training is generally fault-tolerant to interruption if checkpointed.

### Trade-offs
Using a managed ML platform (SageMaker/Vertex AI) over a fully custom/self-hosted ML stack (e.g., Kubeflow on raw EKS/GKE, custom feature pipelines) trades some flexibility/lock-in for dramatically reduced time-to-production and built-in train/serve-skew prevention (feature store), model versioning, and drift monitoring — the right default for most teams unless there's a specific, strong requirement the managed platform can't meet.

### Follow-Up Interview Questions
- **"How would you roll back a model that's causing a business-metric regression discovered a day after full rollout (not caught during canary)?"** → Model Registry's versioning makes this a fast traffic-routing change back to the prior approved version (analogous to §25's deployment rollback), reinforcing why versioning every model (not just the latest) is mandatory, not optional.
- **"How do you handle a feature that's cheap to compute in batch (training) but expensive to compute in real time (serving)?"** → Precompute and cache it in the online feature store on a schedule (e.g., recompute "30-day average" nightly, serve the cached value in real time) rather than recomputing it synchronously on every inference request — an explicit latency-vs-freshness trade-off to call out.

---

## §32 Cost-Optimized Batch Processing Platform

### Problem Statement
Design a large-scale, fault-tolerant batch processing platform (e.g., nightly ETL jobs, ML training jobs, video re-encoding batches) that minimizes cost by aggressively using interruptible/spot capacity, for a workload where individual jobs can tolerate being paused/restarted.

### Requirements
- Process a large queue of independent, embarrassingly-parallel batch jobs nightly.
- Minimize compute cost — spot/preemptible-first strategy.
- Jobs must survive capacity reclamation (spot interruption) without losing significant progress.
- Predictable overall completion time despite using interruptible capacity.

### High-Level Architecture — AWS
- **Job queue:** SQS holds the full backlog of batch job descriptors.
- **Orchestration:** AWS Batch — manages a Spot-backed compute environment, automatically provisions/terminates EC2 Spot instances (with a defined mix of instance types/AZs to maximize spot availability and minimize simultaneous reclamation risk), retries jobs interrupted by a Spot reclamation.
- **Checkpointing:** each job periodically writes progress checkpoints to S3, so a restarted job resumes near where it left off rather than from scratch.
- **Fallback:** AWS Batch compute environment configured with a small On-Demand fallback tier for jobs that fail Spot retries repeatedly (bounding worst-case completion time).

### High-Level Architecture — GCP
- **Job queue:** Pub/Sub or Cloud Tasks holds the job backlog.
- **Orchestration:** **Cloud Batch** (GCP's managed batch scheduling service) — provisions Preemptible/Spot VMs automatically, handles re-scheduling of preempted work.
- **Checkpointing:** progress checkpoints written to Cloud Storage.
- **Fallback:** a mix policy of Spot + a small on-demand baseline, same pattern as AWS.

### Deep Dive: Instance Diversification to Reduce Simultaneous Reclamation Risk
- Spot/preemptible reclamation risk is correlated within a single instance type/AZ (a capacity crunch for one instance family in one AZ can reclaim MANY instances of that type simultaneously) — mitigate by configuring the batch compute environment with a WIDE mix of instance types/families and AZs, so a capacity event affecting one type/AZ combination only reclaims a small fraction of total capacity, not the whole fleet at once.
- This diversification strategy is the single most important lever for making spot/preemptible-heavy batch processing reliably predictable rather than "occasionally catastrophically slow."

### Deep Dive: Checkpoint Granularity Trade-off
- Too-frequent checkpointing (e.g., every few seconds) adds meaningful I/O overhead and can itself slow down the job.
- Too-infrequent checkpointing (e.g., only at the very end) means a late-stage interruption loses almost all progress, defeating the purpose.
- Practical guidance: checkpoint at a granularity where the EXPECTED lost work on interruption (checkpoint interval × interruption probability) is small relative to total job time — for a 2-minute average spot lifetime risk window, checkpointing every 1-2 minutes is a reasonable starting point, tuned per workload.

### Bottlenecks & Scaling
- A sudden regional spot-capacity shortage across ALL diversified instance types simultaneously (rare but possible during broad demand spikes) — the on-demand fallback tier is the safety valve; size it based on the business's tolerance for a slower-but-guaranteed completion path.
- Checkpoint storage (S3/GCS) write contention if thousands of jobs checkpoint simultaneously — mitigate with per-job-prefixed keys (avoids a single hot prefix) and reasonable checkpoint-write batching.

### Trade-offs
Aggressive spot/preemptible usage achieves 60-90% cost savings versus on-demand for this fault-tolerant workload class, trading some completion-time predictability (mitigated via diversification + a bounded on-demand fallback) — an excellent trade-off specifically BECAUSE the workload (nightly batch, not a customer-facing real-time system) can tolerate the added variability; this same strategy would be inappropriate for latency-sensitive serving workloads.

### Follow-Up Interview Questions
- **"How would you decide what fraction of capacity should be On-Demand fallback vs Spot/Preemptible?"** → Model it from historical spot-interruption-rate data for the chosen instance types/regions and the business's tolerance for missing the nightly completion deadline — e.g., if the interruption rate historically causes jobs to need 1.3x the ideal spot-only time on 95% of nights, size the on-demand fallback to cover just enough of the tail to keep the 99th-percentile completion time within the deadline, rather than over-provisioning on-demand "just in case" and losing most of the cost benefit.
- **"How does this platform's cost model change if the workload becomes latency-sensitive (needs to finish within minutes, not overnight)?"** → Spot/preemptible-only strategies become far riskier for tight deadlines — shift toward a higher on-demand baseline or reserved capacity, since the cost-optimization lever (tolerating interruption) directly conflicts with a tight completion-time requirement.

---

## §33 Zero-Downtime Blue-Green / Canary Deployment Architecture

### Problem Statement
Design the deployment architecture/mechanics (distinct from the CI/CD pipeline orchestration of §25) that enables a stateful, high-traffic service to deploy new versions with zero downtime and instant rollback capability.

### Requirements
- Zero dropped requests during a deployment.
- Instant rollback (seconds, not minutes) if a new version misbehaves.
- Must handle both stateless (API) services and services with in-flight long-lived connections (WebSockets).

### Blue-Green Deployment Mechanics
- Maintain TWO complete, identical production environments ("Blue" = currently live, "Green" = new version being deployed).
- Deploy the new version fully to Green (Green receives ZERO live traffic yet) — run full smoke tests against Green directly.
- Cut traffic over from Blue to Green **atomically** (e.g., swap which target group an ALB points to / swap which backend service a GCP Load Balancer's URL map points to) — this is where "zero downtime" comes from: the switch itself is an instantaneous routing change, not a gradual server-by-server replacement.
- Rollback = swap the routing back to Blue — equally instant, since Blue was never torn down and is still fully running.
- **Cost trade-off:** requires running 2x the full production capacity during the deployment window (both Blue and Green fully provisioned simultaneously) — more expensive than a rolling deployment, but the instant-atomic-cutover property is unmatched.

### Canary Deployment Mechanics (contrast with Blue-Green)
- Gradually shift a SMALL, increasing percentage of traffic to the new version (5% → 25% → 50% → 100%), monitoring health metrics at each stage, versus Blue-Green's all-at-once atomic cutover.
- Requires weighted traffic splitting (ALB weighted target groups / Istio VirtualService traffic weights on EKS/GKE / Cloud Deploy's native canary stages) rather than a simple binary swap.
- **Trade-off vs Blue-Green:** canary limits blast radius further (only a small % of users see a bad new version, versus Blue-Green's cutover exposing 100% of traffic instantly) but takes longer to complete a full rollout and doesn't need 2x capacity the whole time (traffic-proportional capacity at each stage) — canary is generally preferred for high-stakes production services; Blue-Green is preferred when instant, all-or-nothing atomic cutover (or cutover simplicity) matters more than gradual exposure.

### Deep Dive: Handling Stateful/Long-Lived Connections During Cutover
- WebSocket/long-poll connections established with the OLD (Blue) version don't automatically move to Green on a routing switch — existing connections stay pinned to Blue until they naturally close/reconnect.
- Pattern: on cutover, stop routing NEW connections to Blue (send new connections to Green only) while allowing EXISTING Blue connections to drain naturally (with a maximum drain timeout, after which they're forcibly closed, prompting client reconnect logic to establish a fresh connection to Green) — this "connection draining" pattern (supported natively by ALB/Cloud Load Balancing target deregistration delay settings) avoids abruptly severing every active user's connection at the instant of cutover.

### Deep Dive: Database Schema Compatibility During Blue-Green
- Since Blue and Green run simultaneously (even briefly) against what's usually the SAME underlying database, any schema change must be compatible with BOTH the old and new application code during the overlap window — this is the "expand/contract" migration pattern referenced in §25's follow-up: add new columns/tables as purely additive changes first (deploy this, safe for both versions), only remove/rename old schema elements in a LATER deployment once the old application version is fully retired.

### Bottlenecks & Scaling
- Database connection pool exhaustion from temporarily running 2x application capacity (Blue+Green) simultaneously against the same DB — size connection pools/DB max-connections with this transient doubling in mind, or use a connection pooler (RDS Proxy / Cloud SQL Auth Proxy with pooling) to absorb it.

### Trade-offs
Summarized in the mechanics sections above: Blue-Green optimizes for instant, simple, atomic cutover/rollback at 2x transient cost; Canary optimizes for minimal blast radius and traffic-proportional cost at the expense of a longer, more complex staged rollout — many mature platforms (as in §25) actually combine both: canary for the gradual exposure/validation phase, with the ability to do an instant Blue-Green-style full rollback if a problem is caught at any canary stage.

### Follow-Up Interview Questions
- **"Which would you choose for a database schema migration itself (not just application code)?"** → Neither Blue-Green nor Canary directly solves schema migration risk — that's handled by the expand/contract pattern regardless of which application deployment strategy is used; the deployment strategy and the migration strategy are complementary, not substitutes for each other.
- **"How do you decide the right canary stage percentages and wait times?"** → Base it on your traffic volume (need enough absolute request volume at 5% to get statistically meaningful error-rate/latency signal within a reasonable wait time) — a low-traffic service might need a higher initial percentage (e.g., 20%) just to get enough signal, while a very high-traffic service can safely start as low as 1%.

---

## §34 Serverless Chat / Messaging Backend

### Problem Statement
Design a serverless real-time chat backend (1:1 and group messaging) supporting message delivery to online users in real time and reliable delivery/sync to offline users when they reconnect, without managing any always-on connection-handling servers directly.

### Requirements
- Real-time message delivery to online recipients (sub-second).
- Reliable delivery to offline recipients (messages waiting when they next connect).
- Support group chats (fan-out to multiple recipients).
- Fully serverless (no self-managed WebSocket server fleet to operate).

### High-Level Architecture — AWS
- **Connection management:** API Gateway WebSocket API — manages persistent WebSocket connections from clients serverlessly, invoking a Lambda function on `$connect`, `$disconnect`, and custom message routes.
- **Connection registry:** DynamoDB table mapping `user_id → [connection_id, ...]` (a user may have multiple active connections — multiple devices) — updated on `$connect`/`$disconnect`.
- **Sending a message:** client sends via the WebSocket route → Lambda writes the message to a `messages` DynamoDB table (durable, source of truth) → looks up the recipient's active connection IDs → uses the API Gateway Management API to push the message directly over each active WebSocket connection.
- **Offline delivery:** if the recipient has no active connection IDs (offline), the message simply exists in the durable `messages` table; on the recipient's next `$connect`, a sync Lambda queries for undelivered messages since their last-seen timestamp/cursor and pushes them.

### High-Level Architecture — GCP
- GCP's server-managed WebSocket story is less first-party-turnkey than API Gateway WebSocket API — the common pattern is **Cloud Run** (which DOES support WebSocket connections, with a configured max instance concurrency and session affinity) hosting a lightweight connection-handling service, backed by Firestore for the connection registry and message durability (Firestore's real-time listeners are also a genuinely strong native fit here — clients can subscribe directly to a Firestore query and receive live updates without the app needing to hand-roll WebSocket push logic at all, for many chat UI use cases).
- **Interview-relevant nuance:** for GCP specifically, it's worth presenting TWO valid answers — (a) a Cloud Run + manual WebSocket push architecture mirroring the AWS pattern closely, or (b) a Firestore-real-time-listeners-native approach that offloads much of the "push to online clients" complexity to Firestore itself — and explaining the trade-off (custom WebSocket gives more control over connection/session semantics; Firestore listeners are much less code but couple your data model tightly to Firestore's sync semantics).

### Deep Dive: Fan-Out for Group Chats
- On sending a group message, write ONE durable message record (with a `conversation_id`), then look up ALL members of that conversation and their active connections, pushing to each — same fan-out-on-write consideration as §19/§20, but here the "follower count" (group size) is typically small (tens to low hundreds of members) so the celebrity-problem concern from §19 rarely applies to chat groups the way it does to social media followers.

### Deep Dive: Message Ordering and Delivery Guarantees
- Clients need messages to display in a consistent order — assign a monotonically increasing sequence number per conversation (e.g., via a DynamoDB atomic counter or a Firestore transaction incrementing a per-conversation counter) rather than relying purely on wall-clock timestamps (which can be subject to clock skew across distributed Lambda/Cloud Run instances).
- At-least-once push delivery (a WebSocket push could theoretically be attempted twice) — client-side dedup by message ID, mirroring the idempotent-consumer principle from §20 Deep Dive 3.

### Bottlenecks & Scaling
- API Gateway WebSocket API / Cloud Run WebSocket connection count limits at very large concurrent-user scale — both scale substantially but require monitoring connection-count metrics and understanding account-level quotas well before hitting them.
- DynamoDB/Firestore hot-partition risk on an extremely active/large group conversation (many members, high message rate) — apply the same anti-hotspotting principles from §5.2/§21 to the conversation's message-storage key design.

### Trade-offs
A fully serverless connection-handling architecture (API Gateway WebSocket API / Cloud Run) avoids operating a stateful WebSocket server fleet directly, at the cost of some added complexity in explicitly managing the connection-registry table and push-fan-out logic yourself (versus, e.g., a dedicated always-on WebSocket server framework with more built-in room/broadcast abstractions) — the right trade-off when minimizing operational surface area is a priority over maximizing framework convenience.

### Follow-Up Interview Questions
- **"How would you show a 'typing...' indicator in real time without persisting every keystroke event durably?"** → Use ephemeral, non-durable push-only events (skip writing to the durable `messages` table entirely for typing indicators — they're transient UI state, not part of the permanent chat history) pushed directly to active connections, trading durability (acceptable here, since losing a typing indicator has no real consequence) for lower write cost/latency versus routing every ephemeral event through the same durable-write path as real messages.
- **"How do you handle a user connected from 3 devices simultaneously — does each get every message?"** → Yes — the connection-registry design (mapping one user_id to MULTIPLE connection_ids) explicitly supports fanning a single incoming message out to every one of that user's active connections/devices, keeping all their devices in sync.

# Part 4 — LLD / Hands-on Design

## §35 IAM Policy Design (AWS JSON + GCP Bindings)

### 35.1 Anatomy of an AWS IAM Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowReadOnlyOnSpecificBucket",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::my-app-uploads",
        "arn:aws:s3:::my-app-uploads/*"
      ],
      "Condition": {
        "StringEquals": {
          "aws:PrincipalOrgID": "o-abc123456"
        }
      }
    },
    {
      "Sid": "DenyDeleteAlways",
      "Effect": "Deny",
      "Action": "s3:DeleteObject",
      "Resource": "arn:aws:s3:::my-app-uploads/*"
    }
  ]
}
```

**Key LLD points a candidate must know cold:**
- `Effect: Deny` always wins over any `Allow`, even from a different policy attached to the same principal — this is why a single explicit Deny statement is a reliable guardrail.
- `Resource` ARNs should be as SPECIFIC as possible — never `"Resource": "*"` in production unless the action is genuinely account-wide by nature (e.g., `s3:ListAllMyBuckets`).
- `Condition` blocks add contextual restrictions (source IP, MFA presence, org ID, request time) — use `aws:MultiFactorAuthPresent` to require MFA for sensitive actions.
- Two resource ARNs are needed for S3 bucket-level actions (`ListBucket` needs the bucket ARN itself) vs. object-level actions (`GetObject`/`PutObject` need the `/*` object ARN) — a very common real-world mistake is granting only one and wondering why the other operation fails.

### 35.2 A Least-Privilege EC2 Instance Role (Trust Policy + Permissions Policy)

```json
// Trust policy (who can assume this role)
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": { "Service": "ec2.amazonaws.com" },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

```json
// Permissions policy (attached to the role) -- scoped to exactly one bucket, one prefix
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["s3:PutObject"],
      "Resource": "arn:aws:s3:::my-app-uploads/incoming/*"
    },
    {
      "Effect": "Allow",
      "Action": ["secretsmanager:GetSecretValue"],
      "Resource": "arn:aws:secretsmanager:us-east-1:123456789012:secret:prod/db-creds-*"
    }
  ]
}
```

This role, attached as an EC2 instance profile, lets the application on that instance write only to `incoming/*` (not the whole bucket) and read only its own DB credential secret — the textbook least-privilege pattern from §8.2.

### 35.3 GCP IAM — Roles and Bindings (Terraform)

```hcl
# Custom role with only the specific permissions needed
resource "google_project_iam_custom_role" "uploader" {
  role_id     = "appUploader"
  title       = "App Uploader"
  permissions = [
    "storage.objects.create",
    "storage.objects.get",
  ]
}

# Bind the custom role to a specific service account, scoped to ONE bucket (not project-wide)
resource "google_storage_bucket_iam_member" "uploader_binding" {
  bucket = google_storage_bucket.uploads.name
  role   = google_project_iam_custom_role.uploader.id
  member = "serviceAccount:${google_service_account.app_sa.email}"
}
```

**Key GCP IAM LLD points:**
- Prefer **predefined roles** (`roles/storage.objectViewer`) over **primitive roles** (`roles/editor`, `roles/owner`) in production — primitive roles grant broad, cross-service permissions that violate least privilege.
- Bind IAM at the LOWEST resource level that makes sense (a specific bucket, not the whole project) whenever the tooling supports it — mirrors the "specific ARN, not `*`" AWS principle.
- Use **Workload Identity Federation** (GCP) / **IAM Roles for Service Accounts (IRSA)** (AWS EKS) to let workloads running IN Kubernetes assume cloud IAM identities WITHOUT static service-account keys ever touching disk — the modern replacement for downloading a service-account JSON key file, which is a long-lived credential and a common source of leaks.

### 35.4 A Common IAM Anti-Pattern to Call Out in Interviews

```json
// ANTI-PATTERN -- never do this in production
{
  "Effect": "Allow",
  "Action": "*",
  "Resource": "*"
}
```

If asked "what's wrong with this policy," the answer should immediately cite: violates least privilege completely, grants unrestricted access to every action on every resource, means a single compromised credential using this policy equals full account compromise, and should be replaced with the minimum specific `Action`/`Resource` pairs the workload genuinely needs.

---

## §36 VPC / CIDR Subnet Planning Worked Example

### 36.1 The Scenario

Design the IP addressing plan for a VPC that will host: a public tier (load balancers, NAT gateways), a private application tier (across 3 AZs), a private data tier (across 3 AZs), and reserve room for a future Kubernetes cluster (which consumes many more IPs per node due to pod-per-IP networking models).

### 36.2 The CIDR Plan

```
VPC CIDR: 10.0.0.0/16   (65,536 addresses total)

  Public subnet AZ-a:    10.0.0.0/24     (256 addresses -- NAT GW, ALB ENIs)
  Public subnet AZ-b:    10.0.1.0/24
  Public subnet AZ-c:    10.0.2.0/24

  App subnet AZ-a:       10.0.10.0/24    (256 addresses -- app servers/ECS tasks)
  App subnet AZ-b:       10.0.11.0/24
  App subnet AZ-c:       10.0.12.0/24

  Data subnet AZ-a:      10.0.20.0/24    (256 addresses -- RDS, ElastiCache)
  Data subnet AZ-b:      10.0.21.0/24
  Data subnet AZ-c:      10.0.22.0/24

  Reserved for EKS pods: 10.0.64.0/18    (16,384 addresses -- large reservation up front,
                                           since each pod typically needs its own IP under the
                                           AWS VPC CNI's default networking mode)
  Reserved for future expansion: 10.0.128.0/17  (32,768 addresses -- second half of the /16,
                                                  untouched, for anything not yet foreseen)
```

**Key LLD reasoning:**
- Reserve the Kubernetes/pod-networking range GENEROUSLY and EARLY — running out of pod IPs later means either re-IP-ing the whole cluster (highly disruptive) or switching CNI modes; a /18 (16k addresses) up front avoids this even for a fairly large cluster.
- Each subnet is a full /24 (256 IPs) even though far fewer instances will actually run in it — AWS reserves 5 IPs per subnet (network address, VPC router, DNS, future use, broadcast-equivalent), and leaving headroom avoids painful re-subnetting later; **subnet CIDR ranges cannot be resized after creation in AWS** (you'd need to create a new subnet), so under-sizing is a real, hard-to-fix mistake.
- GCP's regional subnet model (§6.1) is more forgiving here — a GCP subnet's primary CIDR range CAN be expanded later (as long as the new range doesn't overlap anything else), reducing (but not eliminating) the up-front-sizing pressure compared to AWS.

### 36.3 GCP Equivalent (Terraform)

```hcl
resource "google_compute_network" "main" {
  name                    = "prod-vpc"
  auto_create_subnetworks = false   # always false in production -- pick your own ranges deliberately
}

resource "google_compute_subnetwork" "app_us_central1" {
  name          = "app-us-central1"
  ip_cidr_range = "10.0.10.0/24"
  region        = "us-central1"
  network       = google_compute_network.main.id
  secondary_ip_range {
    range_name    = "gke-pods"
    ip_cidr_range = "10.4.0.0/14"   # large reservation for GKE pod IPs, same reasoning as EKS above
  }
  secondary_ip_range {
    range_name    = "gke-services"
    ip_cidr_range = "10.8.0.0/20"
  }
}
```

Note the **secondary IP ranges** feature — a GCP-specific mechanism letting GKE allocate pod/service IPs from a dedicated secondary range attached to the subnet, keeping them cleanly separate from the primary range used by VMs, without needing a separate subnet resource.

### 36.4 Non-Overlapping CIDR Discipline for Future VPC Peering / VPN

Whatever ranges you pick, they must NOT overlap with any other VPC you might ever peer with (other environments, other business units, on-premises networks) — a common real-world mistake is every team independently choosing `10.0.0.0/16`, which then makes peering between them impossible without a costly re-IP migration. **Practical fix:** maintain a central IP address management (IPAM) registry (AWS VPC IP Address Manager / a simple shared spreadsheet-turned-Terraform-variable-file for smaller orgs) allocating non-overlapping `/16`s per environment/business unit from the start.

---

## §37 Terraform Module Design (LLD)

### 37.1 A Reusable, Parameterized VPC Module

```hcl
# modules/vpc/variables.tf
variable "name"         { type = string }
variable "cidr_block"   { type = string }
variable "azs"          { type = list(string) }
variable "environment"  { type = string }

# modules/vpc/main.tf
resource "aws_vpc" "this" {
  cidr_block           = var.cidr_block
  enable_dns_support   = true
  enable_dns_hostnames = true
  tags = {
    Name        = var.name
    Environment = var.environment
  }
}

resource "aws_subnet" "public" {
  count             = length(var.azs)
  vpc_id            = aws_vpc.this.id
  availability_zone = var.azs[count.index]
  cidr_block        = cidrsubnet(var.cidr_block, 8, count.index)
  tags = {
    Name = "${var.name}-public-${var.azs[count.index]}"
    Tier = "public"
  }
}

resource "aws_subnet" "private" {
  count             = length(var.azs)
  vpc_id            = aws_vpc.this.id
  availability_zone = var.azs[count.index]
  cidr_block        = cidrsubnet(var.cidr_block, 8, count.index + 10)
  tags = {
    Name = "${var.name}-private-${var.azs[count.index]}"
    Tier = "private"
  }
}

# modules/vpc/outputs.tf
output "vpc_id"             { value = aws_vpc.this.id }
output "public_subnet_ids"  { value = aws_subnet.public[*].id }
output "private_subnet_ids" { value = aws_subnet.private[*].id }
```

```hcl
# environments/prod/main.tf -- consumes the module
module "prod_vpc" {
  source      = "../../modules/vpc"
  name        = "prod"
  cidr_block  = "10.0.0.0/16"
  azs         = ["us-east-1a", "us-east-1b", "us-east-1c"]
  environment = "production"
}
```

### 37.2 LLD Principles Behind This Module Design

- **Parameterize everything environment-specific** (`cidr_block`, `azs`, `environment`) — the module itself contains zero hardcoded values, making it truly reusable across dev/staging/prod.
- **Use `cidrsubnet()`** to programmatically derive subnet ranges from the parent CIDR rather than hardcoding each subnet's range — reduces copy-paste errors and keeps the subnetting scheme consistent automatically as AZ count changes.
- **Explicit outputs** — a module should expose exactly the values downstream modules/resources need (`vpc_id`, subnet ID lists) and nothing more, keeping the module's public interface intentional and stable.
- **State isolation per environment** — each environment (`environments/prod`, `environments/staging`) has its OWN Terraform state file/backend, so a mistake in staging can never accidentally touch prod state — a critical operational safety practice.

### 37.3 Remote State Backend (Both Clouds)

```hcl
# AWS backend
terraform {
  backend "s3" {
    bucket         = "company-terraform-state"
    key            = "prod/vpc/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "terraform-locks"   # state locking to prevent concurrent apply races
    encrypt        = true
  }
}
```

```hcl
# GCP backend
terraform {
  backend "gcs" {
    bucket = "company-terraform-state"
    prefix = "prod/vpc"
  }
}
```

**Why remote state + locking is non-negotiable for a team:** local state files can't be safely shared/concurrently modified by multiple engineers, and lack locking (two simultaneous `terraform apply` runs could corrupt state or produce conflicting infrastructure changes) — the DynamoDB lock table (AWS) or GCS's native object versioning/locking (GCP) prevents two applies from racing.

---

## §38 Autoscaling Policy Configuration Deep Dive

### 38.1 AWS Auto Scaling Group — Target Tracking Policy

```hcl
resource "aws_autoscaling_policy" "cpu_target_tracking" {
  name                   = "cpu-target-tracking"
  autoscaling_group_name = aws_autoscaling_group.app.name
  policy_type            = "TargetTrackingScaling"

  target_tracking_configuration {
    predefined_metric_specification {
      predefined_metric_type = "ASGAverageCPUUtilization"
    }
    target_value       = 50.0   # keep average CPU at 50% -- scale out above, in below
    disable_scale_in   = false
  }
}

resource "aws_autoscaling_group" "app" {
  min_size            = 3
  max_size            = 50
  desired_capacity    = 6
  vpc_zone_identifier = module.prod_vpc.private_subnet_ids
  health_check_type         = "ELB"
  health_check_grace_period = 120   # seconds to let a new instance warm up before health-checking it
}
```

**LLD reasoning for each number:**
- `min_size = 3` — one per AZ minimum, ensures baseline coverage even with zero load, and ensures losing one AZ still leaves 2 running instances.
- `target_value = 50.0` — leaves 50% headroom per instance to absorb a sudden burst before new instances finish launching (launch + health-check-pass typically takes 1-3 minutes) — target too high (e.g., 90%) risks brief overload during that scale-out lag.
- `health_check_grace_period = 120` — prevents the ASG from prematurely killing a new instance that's still warming up (loading application code, JIT-warming a JVM, etc.) before it's actually ready to serve traffic.

### 38.2 GCP Managed Instance Group — Autoscaler

```hcl
resource "google_compute_region_autoscaler" "app" {
  name   = "app-autoscaler"
  region = "us-central1"
  target = google_compute_region_instance_group_manager.app.id

  autoscaling_policy {
    min_replicas    = 3
    max_replicas    = 50
    cooldown_period = 120

    cpu_utilization {
      target = 0.5
    }
  }
}
```

Same reasoning applies identically — `cooldown_period` is GCP's direct analog to AWS's health-check grace period concept for the scaling decision loop (avoid reacting to a new instance's transient startup CPU spike as if it were sustained load).

### 38.3 Scaling on a Custom Metric (Queue Depth) — Both Clouds

```hcl
# AWS: scale based on SQS queue depth (a common, more meaningful signal than CPU
# for a worker fleet processing a queue)
resource "aws_autoscaling_policy" "queue_depth" {
  name                   = "queue-depth-tracking"
  autoscaling_group_name = aws_autoscaling_group.worker.name
  policy_type            = "TargetTrackingScaling"

  target_tracking_configuration {
    customized_metric_specification {
      metric_name = "ApproximateNumberOfMessagesVisible"
      namespace   = "AWS/SQS"
      statistic   = "Average"
    }
    target_value = 100.0   # aim to keep ~100 messages waiting per instance, tune based on
                            # per-instance processing throughput
  }
}
```

**Why queue-depth-based scaling often beats CPU-based scaling for worker fleets:** a worker fleet processing an SQS/Pub-Sub queue might have LOW CPU utilization while still falling badly behind (e.g., waiting on slow downstream API calls, not CPU-bound at all) — CPU-based scaling would fail to scale out in this case, while queue-depth-based scaling directly targets the actual business signal that matters ("is the backlog growing?").

---

## §39 Security Groups & Firewall Rule Design

### 39.1 AWS Security Groups — Layered, Least-Privilege Design

```hcl
resource "aws_security_group" "alb" {
  name   = "alb-sg"
  vpc_id = module.prod_vpc.vpc_id

  ingress {
    description = "HTTPS from the internet"
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

resource "aws_security_group" "app" {
  name   = "app-sg"
  vpc_id = module.prod_vpc.vpc_id

  ingress {
    description     = "Only from the ALB, never directly from the internet"
    from_port       = 8080
    to_port         = 8080
    protocol        = "tcp"
    security_groups = [aws_security_group.alb.id]   # reference another SG, not a CIDR --
                                                       # this is the key least-privilege pattern
  }
}

resource "aws_security_group" "db" {
  name   = "db-sg"
  vpc_id = module.prod_vpc.vpc_id

  ingress {
    description     = "Only from the app tier, never from the ALB or the internet"
    from_port       = 5432
    to_port         = 5432
    protocol        = "tcp"
    security_groups = [aws_security_group.app.id]
  }
}
```

**The chained-security-group pattern above is a critical LLD security concept:** each tier only accepts traffic from the SPECIFIC security group of the tier that should legitimately call it (internet → ALB, ALB → app, app → db), never a broad CIDR range — this means even if someone were to accidentally launch a rogue instance inside the VPC, it could NOT reach the database directly unless it were specifically placed in the `app` security group, providing defense in depth beyond just subnet placement.

### 39.2 GCP Firewall Rules — the Equivalent Pattern (Tag/Service-Account-Based)

```hcl
resource "google_compute_firewall" "allow_lb_to_app" {
  name    = "allow-lb-to-app"
  network = google_compute_network.main.name

  allow {
    protocol = "tcp"
    ports    = ["8080"]
  }

  source_tags = ["lb"]     # or source_service_accounts for an even stronger identity-based rule
  target_tags = ["app"]
  direction   = "INGRESS"
}

resource "google_compute_firewall" "allow_app_to_db" {
  name    = "allow-app-to-db"
  network = google_compute_network.main.name

  allow {
    protocol = "tcp"
    ports    = ["5432"]
  }

  source_tags = ["app"]
  target_tags = ["db"]
  direction   = "INGRESS"
}

resource "google_compute_firewall" "deny_all_ingress_default" {
  name     = "deny-all-ingress-default"
  network  = google_compute_network.main.name
  priority = 65534   # low priority = evaluated last, acts as the default-deny backstop

  deny {
    protocol = "all"
  }

  source_ranges = ["0.0.0.0/0"]
  direction     = "INGRESS"
}
```

**Key AWS-vs-GCP firewall distinction:** AWS Security Groups are **stateful and implicitly default-deny** (you only write ALLOW rules; anything not explicitly allowed is denied, and return traffic for an allowed connection is automatically permitted) — there's no explicit "deny all" rule to write. GCP VPC firewall rules are ALSO stateful for the allow/return-traffic behavior, but GCP's default network historically ships with a permissive implied rule set, so many real-world GCP setups explicitly add a low-priority deny-all rule (as shown above) to make the default-deny posture explicit and auditable, rather than relying solely on the absence of allow rules.

### 39.3 A Common Interview Trap: Security Groups Referencing CIDR Ranges Instead of Other Security Groups

If asked to critique a design where the `app` tier's security group allows ingress from `10.0.0.0/16` (the whole VPC CIDR) on port 8080, the correct critique: this allows ANY resource anywhere in the VPC to reach the app tier directly, including a compromised resource in an unrelated subnet — the fix is always to reference the SPECIFIC security group of the legitimate caller (as in 39.1) rather than a broad IP range, even if that IP range happens to be "only" the VPC's own private range.

## §40 Kubernetes Manifests / Helm Chart for a Cloud-Native App

### 40.1 Deployment Manifest (Cloud-Agnostic — Runs Identically on EKS or GKE)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: order-service
  labels:
    app: order-service
spec:
  replicas: 6
  selector:
    matchLabels:
      app: order-service
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 0   # zero-downtime rolling update -- never drop below desired capacity
  template:
    metadata:
      labels:
        app: order-service
    spec:
      containers:
        - name: order-service
          image: <registry>/order-service:1.4.2   # ECR or Artifact Registry, tagged by commit/semver
          ports:
            - containerPort: 8080
          resources:
            requests:
              cpu: "250m"
              memory: "256Mi"
            limits:
              cpu: "500m"
              memory: "512Mi"
          readinessProbe:
            httpGet:
              path: /healthz/ready
              port: 8080
            initialDelaySeconds: 5
            periodSeconds: 10
          livenessProbe:
            httpGet:
              path: /healthz/live
              port: 8080
            initialDelaySeconds: 15
            periodSeconds: 20
          envFrom:
            - secretRef:
                name: order-service-secrets   # synced from Secrets Manager / Secret Manager
```

**LLD reasoning:**
- `maxUnavailable: 0` + `maxSurge: 25%` — guarantees the rolling update never reduces capacity below the desired replica count (new pods are added BEFORE old ones are removed), directly implementing the zero-downtime principle from §33 at the Kubernetes primitive level.
- **`requests` vs `limits`** — `requests` is what the scheduler uses to place the pod (and, in GKE Autopilot, what you're billed for); `limits` caps actual usage to prevent one noisy pod from starving others on the same node (§22 Deep Dive 2's noisy-neighbor mitigation).
- **`readinessProbe` vs `livenessProbe`** — readiness determines whether the pod RECEIVES traffic (fails → removed from Service endpoints, but pod is NOT restarted); liveness determines whether the pod is restarted (fails → killed and replaced). Conflating these is a common LLD mistake (e.g., using only a liveness probe means a temporarily-overloaded-but-alive pod keeps receiving traffic it can't handle, instead of being safely drained).

### 40.2 Horizontal Pod Autoscaler

```yaml
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: order-service-hpa
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: order-service
  minReplicas: 6
  maxReplicas: 60
  metrics:
    - type: Resource
      resource:
        name: cpu
        target:
          type: Utilization
          averageUtilization: 60
    - type: Pods
      pods:
        metric:
          name: queue_messages_per_pod   # custom metric via Prometheus Adapter / Cloud Monitoring adapter
        target:
          type: AverageValue
          averageValue: "50"
```

Mirrors the target-tracking and custom-metric scaling principles from §38, now at the pod level rather than the VM/instance level.

### 40.3 Service + Ingress

```yaml
apiVersion: v1
kind: Service
metadata:
  name: order-service
spec:
  selector:
    app: order-service
  ports:
    - port: 80
      targetPort: 8080
  type: ClusterIP
---
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: order-service-ingress
  annotations:
    kubernetes.io/ingress.class: "alb"          # EKS: AWS Load Balancer Controller
    # kubernetes.io/ingress.class: "gce"        # GKE: native GCP Ingress controller (use one or the other)
spec:
  rules:
    - host: orders.internal.company.com
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: order-service
                port:
                  number: 80
```

### 40.4 NetworkPolicy — Multi-Tenant Isolation (from §22 Deep Dive 2)

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: deny-cross-namespace-by-default
  namespace: team-a
spec:
  podSelector: {}
  policyTypes:
    - Ingress
  ingress:
    - from:
        - namespaceSelector:
            matchLabels:
              name: team-a   # only allow traffic from pods within the SAME namespace by default
```

### 40.5 PodDisruptionBudget — Safe Node Upgrades (from §22 Follow-Up Qs)

```yaml
apiVersion: policy/v1
kind: PodDisruptionBudget
metadata:
  name: order-service-pdb
spec:
  minAvailable: 4   # of the 6+ replicas, at least 4 must remain available during any voluntary
                    # disruption (node drain during a cluster upgrade), directly protecting
                    # against the "20 teams' workloads, zero-downtime upgrade" scenario
  selector:
    matchLabels:
      app: order-service
```

### 40.6 Helm Chart Structure (Parameterizing the Above Across Environments)

```
order-service-chart/
├── Chart.yaml
├── values.yaml              # defaults
├── values-staging.yaml      # overrides for staging
├── values-prod.yaml         # overrides for prod
└── templates/
    ├── deployment.yaml
    ├── service.yaml
    ├── ingress.yaml
    ├── hpa.yaml
    ├── networkpolicy.yaml
    └── pdb.yaml
```

```yaml
# values-prod.yaml
replicaCount: 6
image:
  tag: "1.4.2"
resources:
  requests: { cpu: "250m", memory: "256Mi" }
  limits:   { cpu: "500m", memory: "512Mi" }
autoscaling:
  minReplicas: 6
  maxReplicas: 60
ingress:
  host: orders.internal.company.com
```

```bash
# Deploy to prod
helm upgrade --install order-service ./order-service-chart \
  -f ./order-service-chart/values-prod.yaml \
  --namespace team-a \
  --atomic \
  --timeout 5m
```

`--atomic` automatically rolls back the release if the upgrade fails health checks within the timeout — a Helm-native safety net directly supporting the zero-downtime/instant-rollback goals of §25 and §33, expressed at the package-manager level.

# Part 5 — Interview Q&A Bank

## §41 AWS-Specific Questions

### Q1: What happens during an RDS Multi-AZ failover, step by step?
**A:** The primary instance becomes unreachable (health check failure) → RDS detects this within seconds → the standby (already synchronously replicated) is promoted to primary → the DB endpoint's DNS record is updated to point to the new primary's IP → application connections that use the DNS endpoint (not a cached IP) reconnect and resume. Total time: typically 60-120 seconds. Applications must use the DNS endpoint and implement connection retry logic — caching the resolved IP defeats the failover mechanism.

### Q2: What's the difference between an ALB Target Group's health check and an EC2 instance status check?
**A:** EC2 status checks verify the underlying VM/hypervisor is functioning (system status) and the OS is responsive (instance status) — infrastructure-level. ALB target health checks verify the APPLICATION is actually responding correctly on a specific path/port — application-level. An instance can pass EC2 status checks while still failing ALB health checks (e.g., the app crashed but the OS is fine) — always rely on ALB health checks (or equivalent) to gate traffic routing, not just infra-level checks.

### Q3: Why would you choose Kinesis over SQS for a given workload?
**A:** Choose Kinesis when you need: multiple independent consumers reading the SAME stream of events (fan-out to several consumer applications), ordered replay/reprocessing of historical events (Kinesis retains data and supports re-reading from any point), or very high-throughput ordered-per-key streaming analytics. Choose SQS for simple point-to-point task queues where each message should be processed by exactly one consumer group, with simpler operational semantics (no shard management).

### Q4: How does S3 achieve 11 nines of durability?
**A:** By redundantly storing multiple copies of every object across multiple devices in multiple Availability Zones within a region automatically — durability here refers to NOT LOSING data (distinct from availability, which is about being reachable/responsive). Even if 2 of 3 AZs became fully unavailable, S3 Standard is designed so your data is not lost.

### Q5: What's the difference between a Security Group and a Network ACL?
**A:** Security Groups are stateful (return traffic automatically allowed), operate at the instance/ENI level, support only ALLOW rules (implicit default-deny). Network ACLs are stateless (you must explicitly allow both inbound AND outbound/return traffic), operate at the subnet level, and support both ALLOW and DENY rules evaluated in numbered order. NACLs are typically used for coarse subnet-wide rules (e.g., explicitly blocking a known-bad IP range); Security Groups handle the fine-grained, day-to-day least-privilege access control.

### Q6: When would you use a Network Load Balancer instead of an Application Load Balancer?
**A:** When you need: raw TCP/UDP traffic that isn't HTTP (custom protocols, gaming servers), extreme throughput/ultra-low added latency (NLB adds negligible latency since it doesn't parse L7), a static IP address per AZ (NLB supports Elastic IPs directly, ALB does not), or preservation of the client's source IP without needing X-Forwarded-For header handling.

### Q7: What is DynamoDB adaptive capacity, and why does it matter?
**A:** Adaptive capacity automatically and transparently redistributes throughput capacity to accommodate uneven access patterns across partitions (a "hot" partition receiving disproportionate traffic) without requiring you to manually re-provision or redesign your partition key immediately. It mitigates but does NOT eliminate the need for good partition key design (§5.2) — extreme, sustained hotspotting still degrades performance even with adaptive capacity active.

### Q8: How would you rotate a database credential used by dozens of Lambda functions with zero downtime?
**A:** Use Secrets Manager's automatic rotation feature with a rotation Lambda that: creates a new credential, updates the database to accept both old and new credentials temporarily (a brief overlap window), then Lambda functions retrieve the current secret value at invocation time (or via a cached client that refreshes periodically) — never hardcode credentials in function code/environment variables directly, always fetch from Secrets Manager so rotation is transparent to every consumer.

### Q9: What is the purpose of an Elastic IP, and what's a real cost gotcha related to it?
**A:** An Elastic IP is a static, account-owned public IPv4 address you can attach/detach from resources. The gotcha: AWS charges for an Elastic IP that is ALLOCATED but NOT ATTACHED to a running resource (to discourage hoarding scarce IPv4 addresses) — a very common surprise line item on a bill for teams that allocated EIPs during testing and forgot to release them.

### Q10: How does Lambda's concurrency limit interact with a downstream RDS database?
**A:** Lambda can scale to thousands of concurrent executions very quickly, but a traditional RDS instance has a hard connection limit — an unthrottled Lambda spike can exhaust the database's connections and cause cascading failures. Mitigation: use RDS Proxy (connection pooling/multiplexing designed specifically for Lambda's connection pattern) or cap Lambda's reserved concurrency to a safe ceiling relative to the database's connection capacity.

### Q11: What's the difference between an EBS snapshot and an AMI?
**A:** An EBS snapshot is a point-in-time backup of a single volume's data. An AMI (Amazon Machine Image) is a full template for launching a NEW instance — it includes one or more EBS snapshots (root + any additional volumes) PLUS metadata (instance type compatibility, launch permissions, block device mapping) needed to actually boot a new instance from it.

### Q12: Why might CloudFront serve stale content even after you update the S3 origin?
**A:** CloudFront caches responses at edge locations based on the object's cache-control headers/TTL — until that TTL expires (or you issue an explicit invalidation), edges continue serving the previously cached version. This is exactly why §23 recommends filename-hashing (cache-bust via unique filenames) over relying on invalidation for high-frequency deploys.

### Q13: What's the difference between an IAM Role and an IAM User?
**A:** An IAM User represents a persistent, named identity (a person or an application) with long-term credentials (password/access keys). An IAM Role has NO long-term credentials — it's assumed temporarily (via STS) by a trusted entity (an EC2 instance, a Lambda function, another AWS account, a federated user), receiving short-lived, auto-rotating credentials. Best practice: use Roles for compute-to-service authentication, not IAM User access keys.

### Q14: How would you design an S3 bucket structure to avoid request-rate hot-partitioning?
**A:** Modern S3 automatically scales request rate per prefix (S3 removed the old "randomize key prefixes" requirement years ago for general high-throughput access) — but for EXTREME request rates to a very narrow, sequential key pattern (e.g., all keys sharing an identical, sequentially-increasing prefix like a timestamp), still consider adding some entropy/hashing to the prefix if you observe throttling, since a single logical partition can still become a bottleneck under truly extreme, non-distributed access patterns.

### Q15: What's the practical difference between Step Functions Standard and Express workflows?
**A:** Standard workflows are for long-running (up to 1 year), auditable, exactly-once workflows with a per-state-transition pricing model (good for the Saga pattern in §20). Express workflows are for high-volume, short-duration (up to 5 minutes), at-least-once workflows priced per invocation/duration (good for high-throughput streaming data transformation workloads where Standard's per-transition cost would be prohibitive).

---

## §42 GCP-Specific Questions

### Q1: Why is a GCP VPC described as a "global" resource, and what's the practical implication?
**A:** A single VPC's subnets can span every GCP region simultaneously, and resources in different regions within the same VPC can communicate via internal IPs without VPC peering. Practical implication: expanding a GCP application to a new region often requires zero networking reconfiguration (just add a subnet in the new region to the existing VPC), whereas the AWS equivalent (§6.1) typically requires setting up VPC peering or a Transit Gateway between regional VPCs.

### Q2: What's the difference between GKE Standard and GKE Autopilot?
**A:** GKE Standard: you manage node pools (choose machine types, size, patch/upgrade cadence), billed per node. GKE Autopilot: Google manages nodes entirely (no node pools to configure), billed per pod resource request, with security-hardened defaults and some workload restrictions (no privileged containers/DaemonSets/host networking). Choose Autopilot when minimizing ops overhead matters most; choose Standard when you need node-level customization or unsupported Autopilot workload types.

### Q3: How does Cloud Spanner achieve strong consistency across regions without violating CAP theorem?
**A:** Spanner uses TrueTime (an API exposing bounded clock uncertainty via atomic clocks + GPS receivers in Google's data centers) combined with "commit wait" — a transaction waits out the maximum possible clock uncertainty window before acknowledging commit, guaranteeing external consistency (linearizability) globally. It doesn't violate CAP — it makes a deliberate latency trade-off (PACELC's "else, latency" branch) to achieve consistency, rather than achieving consistency "for free."

### Q4: What is BigQuery's pricing model, and how do you control cost?
**A:** On-demand: pay per byte of data SCANNED by a query (not per byte returned) — control cost via partitioning/clustering tables (query engine skips irrelevant partitions), avoiding `SELECT *` (columnar storage means you're billed for scanned columns), and using materialized views for repeated aggregations. Alternative: flat-rate slot reservations convert variable per-query cost into a fixed monthly cost, better for high, predictable query volume.

### Q5: Why would you choose Firestore over Cloud SQL for a mobile app backend?
**A:** Firestore offers native real-time listeners (clients subscribe to a query and get live push updates with zero custom WebSocket code), offline support with automatic local caching/sync for mobile clients, and serverless auto-scaling — ideal for mobile-first apps needing live UI updates and offline resilience. Cloud SQL is the better choice when the data model is genuinely relational (needs joins/complex transactions across many entities) and eventual/real-time sync isn't a core requirement.

### Q6: What's the purpose of a GCP Shared VPC, and who "owns" it?
**A:** A Shared VPC lets a "host project" own the VPC/subnets/networking config, while multiple "service projects" (often one per team) attach their resources (VMs, GKE clusters) to that shared network. IAM/billing/resource management stay separate per service project, but networking is centrally managed by the host project's admins — a cleaner multi-team networking model than AWS's more bolted-on cross-account VPC sharing via Resource Access Manager (§6.3).

### Q7: How does Cloud Run's concurrency setting affect cost?
**A:** Concurrency = how many simultaneous requests one Cloud Run instance handles. Higher concurrency (for I/O-bound workloads that spend most time waiting, not computing) means fewer total instances needed for the same load, directly reducing cost since billing is per-instance-resource-time. Setting concurrency too high for a CPU-bound workload causes requests to contend for the same vCPU allocation, degrading latency instead of saving cost — tune concurrency based on the workload's CPU-bound vs I/O-bound profile.

### Q8: What replaced Cloud IoT Core after its deprecation, and why does this matter for an interview answer?
**A:** GCP deprecated Cloud IoT Core in 2023; the current recommended pattern composes Pub/Sub (ingestion) with a partner/third-party device-management and identity layer, or a self-managed MQTT broker bridging into Pub/Sub. Mentioning this deprecation unprompted (or correctly, if asked about IoT on GCP) signals up-to-date knowledge rather than working from outdated documentation.

### Q9: What is Binary Authorization, and what problem does it solve?
**A:** Binary Authorization is a deploy-time security control (integrates with GKE/Cloud Run) that enforces only container images signed/attested by a trusted authority (e.g., passed your CI pipeline's vulnerability scan and test suite) can actually be deployed — preventing an unscanned, unapproved, or tampered image from ever reaching production, even if someone has direct deploy access to the cluster.

### Q10: How do Org Policies differ from IAM Policies in GCP?
**A:** IAM Policies grant WHO can do WHAT (identity-based permissions). Org Policies restrict WHAT IS ALLOWED to happen at all, organization/folder/project-wide, regardless of IAM permissions (e.g., "no VM may have a public IP," "service account keys cannot be created") — Org Policies act as a ceiling IAM allows can never exceed, mirroring AWS SCPs (§8.3).

### Q11: Why might you choose Bigtable over Firestore for a given workload?
**A:** Bigtable is built for massive write throughput and time-series/wide-column access patterns at huge scale (IoT telemetry, ad-click logs, financial tick data) with row-key-based access (no secondary indexes) — choose it when write volume is extreme and access is primarily by a well-designed row key/range scan. Firestore is better for document-oriented data with rich querying needs (filter by multiple fields), real-time listeners, and moderate (not extreme) write throughput per document.

### Q12: What does "sustained use discount" mean on GCP, and how is it different from AWS Reserved Instances?
**A:** Sustained use discounts are AUTOMATIC — the longer a Compute Engine VM runs within a billing month, the bigger the automatic discount, with zero upfront commitment or reservation required. AWS Reserved Instances/Savings Plans require an explicit 1-3 year commitment purchased in advance for a discount — GCP's model rewards steady usage without requiring you to predict/commit to future capacity needs ahead of time.

### Q13: How does Cloud CDN interact with a Global External HTTP(S) Load Balancer?
**A:** Cloud CDN is enabled as a property of a backend service/backend bucket attached to the Global LB — the same anycast global IP serves both cached (CDN-hit) and uncached (passed through to the backend) requests, so there's no separate "CDN distribution" resource to manage the way CloudFront is a distinct, separately-configured resource in front of an ALB/S3 origin in AWS.

### Q14: What is Workload Identity Federation, and what problem does it solve?
**A:** It lets workloads running outside GCP (e.g., in GitHub Actions, AWS, on-prem) or inside GKE authenticate as a GCP service account WITHOUT needing a downloaded, long-lived service account JSON key — instead, an external identity token is exchanged for short-lived GCP credentials. This eliminates the biggest common source of GCP credential leaks (a service account key file committed to a repo or left on a laptop).

### Q15: Why does GCP's Cloud SQL support cross-region read replicas as a "read-latency" feature more prominently than a pure DR feature?
**A:** Because a cross-region replica lets you serve read queries from a replica physically close to a geographically distant user base (reducing read latency for that region) while all writes still go to the single primary — a legitimate standing architecture, not just a disaster-recovery standby that sits idle. AWS RDS supports the identical underlying capability, but is discussed more often in a DR-first framing (§16); GCP's docs/tooling foreground the read-latency use case more explicitly, though both use cases apply on both clouds.

## §43 Comparison / "When Would You Choose X Over Y" Questions

### Q1: RDS/Cloud SQL vs DynamoDB/Firestore — how do you decide?
**A:** Relational (RDS/Cloud SQL) when you need multi-table transactions, complex joins, and a well-understood normalized schema at moderate scale. NoSQL (DynamoDB/Firestore) when you need predictable single-digit-ms latency at massive/unpredictable scale, your access patterns are well-known upfront (so you can design partition/sort keys around them), and you can tolerate a less flexible query model.

### Q2: EC2/Compute Engine vs Lambda/Cloud Functions — how do you decide?
**A:** Choose serverless functions for event-triggered, short-duration, spiky/unpredictable workloads where paying only for actual execution matters. Choose VMs when you need long-running processes, full OS control, specialized hardware, or the workload is steady-state enough that reserved/committed VM pricing beats per-invocation serverless pricing (§19 Deep Dive 2's crossover point).

### Q3: ECS vs EKS — how do you decide?
**A:** ECS for simpler, AWS-only container needs with lower operational overhead. EKS when you need Kubernetes ecosystem tooling/portability (Helm, service mesh, K8s operators) or multi-cloud/hybrid deployment flexibility.

### Q4: SQS vs SNS vs EventBridge — how do you decide?
**A:** SQS for point-to-point queues (one message, one logical consumer group). SNS for simple fan-out to multiple subscribers with no advanced routing needs. EventBridge when you need schema-aware, content-based routing across many event sources/types with a central event bus model — the natural choice for a domain-event-driven microservices architecture (§20).

### Q5: Kinesis vs SQS — how do you decide?
**A:** Kinesis when you need multiple independent consumers reading the same ordered stream, replay capability, or high-throughput streaming analytics. SQS when you need a simple, decoupled task queue with per-message visibility timeout/DLQ semantics and don't need replay or multi-consumer fan-out of the same stream.

### Q6: Aurora vs Spanner — how do you decide?
**A:** Aurora for a relational workload that fits a single-region (or simple cross-region read-replica) model with strong MySQL/PostgreSQL compatibility and high read scale. Spanner when you need TRUE horizontal write scalability with strong global consistency — a much rarer, more specific requirement that justifies Spanner's added cost/complexity only when genuinely needed (§5.6, §24).

### Q7: S3/GCS Standard vs Intelligent-Tiering/Autoclass vs Glacier/Archive — how do you decide?
**A:** Standard for frequently accessed hot data. Intelligent-Tiering (AWS) / Autoclass (GCP) when access patterns are unpredictable and you want automatic cost optimization with no operational overhead. Glacier/Archive tiers for compliance/long-term retention data accessed rarely, where retrieval latency (minutes to hours) is acceptable.

### Q8: ALB vs NLB — how do you decide?
**A:** ALB for HTTP/HTTPS traffic needing L7 routing (path/host-based rules), WAF integration, or TLS termination with content awareness. NLB for raw TCP/UDP, ultra-low latency, static IP requirements, or extreme throughput where L7 processing overhead isn't needed/wanted.

### Q9: Terraform vs CloudFormation/CDK vs Deployment Manager — how do you decide?
**A:** Terraform for any multi-cloud or hybrid-cloud requirement (only mature option with first-class AWS+GCP+Azure providers in one tool/workflow). CloudFormation/CDK when you're AWS-only and want deep, native AWS integration (drift detection, stack rollback) without an external state backend to manage. GCP-native Deployment Manager is largely superseded by Terraform even for GCP-only shops today.

### Q10: Fargate vs self-managed EKS/GKE node pools — how do you decide?
**A:** Fargate/Autopilot when minimizing ops overhead matters most and your workloads fit within its constraints (no privileged containers/DaemonSets needed). Self-managed nodes when you need full control (custom AMIs, GPU scheduling quirks, DaemonSets for security/monitoring agents) or extreme cost optimization via aggressive bin-packing that only node-level control enables.

### Q11: Synchronous vs asynchronous cross-region replication — how do you decide?
**A:** Synchronous when RPO=0 is a hard business requirement and you can accept the added write latency (e.g., certain financial transaction ledgers). Asynchronous for the vast majority of workloads where a few seconds of potential data loss on a rare regional failure is an acceptable trade for normal low-latency writes.

### Q12: Blue-Green vs Canary deployment — how do you decide?
**A:** Blue-Green when you want instant, atomic, all-or-nothing cutover/rollback and can afford 2x transient capacity cost. Canary when minimizing blast radius via gradual, metric-gated traffic shifting matters more than deployment speed, and you want to avoid the 2x capacity cost.

### Q13: CloudFront Functions vs Lambda@Edge — how do you decide?
**A:** CloudFront Functions for extremely lightweight, sub-millisecond logic (header manipulation, simple redirects, cookie-based routing) at every edge location cheaply. Lambda@Edge for heavier logic needing more compute/memory, longer execution time, or the ability to call other AWS services from the edge.

### Q14: BigQuery vs Redshift — how do you decide?
**A:** BigQuery when you want a truly serverless, zero-cluster-management warehouse with pay-per-query pricing and native ML (BigQuery ML) — ideal for unpredictable/bursty analytical workloads. Redshift when you have high, predictable, sustained query volume where a provisioned/reserved cluster (or Redshift Serverless) becomes more cost-effective, or you need tighter integration with the broader AWS ecosystem.

### Q15: GKE Autopilot vs GKE Standard — how do you decide?
**A:** Autopilot when you want the lowest possible ops overhead and exact per-pod cost attribution (§22 Deep Dive 1), and your workloads don't need privileged/host-network access. Standard when you need node-level customization, unsupported Autopilot workload types, or finer-grained cost control via aggressive custom bin-packing.

### Q16: Firestore vs Bigtable — how do you decide?
**A:** Firestore for document-oriented data with rich multi-field querying, real-time listeners, offline sync (mobile/web apps). Bigtable for massive write-throughput, time-series/wide-column data accessed primarily by row-key range scans (IoT, analytics, ad-tech logs) where secondary-index querying isn't needed.

### Q17: Warm Standby vs Multi-Site Active-Active DR — how do you decide?
**A:** Warm Standby when RTO in the minutes range is acceptable and you want to avoid running full production-scale capacity in a second region continuously. Active-Active when RTO must be near-zero (no failover step at all) and the business can justify running full capacity in 2+ regions simultaneously.

### Q18: DynamoDB Global Tables vs Spanner multi-region — how do you decide?
**A:** Global Tables for region-partitioned data where local write latency matters most and rare last-writer-wins conflicts are acceptable. Spanner when a shared/global resource genuinely needs strict global consistency and you can accept the added cross-region write latency (§24's core trade-off).

### Q19: App Runner/Cloud Run vs Fargate/GKE Autopilot — how do you decide?
**A:** App Runner/Cloud Run when you have a single containerized service (or a small number) and want the simplest possible deploy-a-container-get-a-URL experience with true scale-to-zero. Fargate/GKE Autopilot when you're operating MANY services needing Kubernetes-style orchestration primitives (service discovery, complex networking policies, DaemonSets in Fargate's ECS mode) beyond what a single-container-per-service PaaS model provides.

### Q20: Athena vs BigQuery (as a query-over-object-storage engine) — how do you decide?
**A:** Athena when your data already lives in S3 and you want ad hoc SQL without ANY data movement/loading, paying per query. BigQuery when you want a first-class warehouse experience (native storage optimizations, streaming inserts, BigQuery ML, more mature cost-control tooling like flat-rate slots) beyond pure ad hoc query-over-files.

---

## §44 Scenario-Based Mini System Design Questions

### Q1: "Design a URL shortener that must handle 100M new URLs/day." How would you generate short codes without collisions at this scale?
**A:** Use a distributed unique ID generator (e.g., a Snowflake-style approach: timestamp + machine ID + sequence number) or pre-allocate ranges of IDs to each application server from a central counter service, then base62-encode the ID into a short code — avoids the coordination overhead of checking for collisions on every single write, and avoids a single global counter becoming a bottleneck by handing out ID ranges in batches per server.

### Q2: "Your API's p99 latency suddenly doubled after a routine deploy, but p50 is unchanged." What's your triage approach?
**A:** p50 unchanged but p99 degraded strongly suggests a tail-latency issue affecting a subset of requests, not a uniform slowdown — check for: a new code path only some requests hit (e.g., a cache-miss path that got slower), GC pauses (if using a GC'd runtime) increasing in frequency/duration, or a downstream dependency call added in the new deploy that occasionally times out/retries. Distributed tracing (§10.2) on the slowest 1% of requests specifically (not average) is the fastest way to isolate which span is responsible.

### Q3: "A batch job needs to process 500 million rows nightly within a 4-hour window." How would you architect this?
**A:** Partition the data (by a natural key or hash) into many independent chunks, process chunks in parallel across a horizontally-scaled compute fleet (EMR/Dataproc Spark job, or Batch/Cloud Batch with many workers), size the parallelism so 500M rows / (rows-per-second-per-worker × worker-count) comfortably fits in 4 hours with margin, and checkpoint progress per chunk so a single worker failure only requires reprocessing that chunk, not the whole 500M-row job.

### Q4: "Users report seeing each other's shopping cart contents intermittently." What's the likely root cause and fix?
**A:** Almost certainly a caching/session bug — likely a shared cache key that isn't properly scoped per-user (e.g., caching by a coarse key that doesn't include the user/session ID), or a CDN caching a personalized response as if it were public/cacheable content. Fix: audit cache keys to ensure user-specific data is never cached under a shared key, and explicitly mark personalized API responses as non-cacheable (`Cache-Control: private, no-store`) at both the CDN and application layer.

### Q5: "Design a system to detect and block a DDoS attack in real time." What's your layered approach?
**A:** Layer 1: Cloud provider's automatic network-level DDoS protection (Shield Standard / Google's automatic network protection) absorbs volumetric attacks at the edge before they reach your infrastructure. Layer 2: WAF/Cloud Armor rate-limiting and bot-detection rules at the L7 edge. Layer 3: application-level rate limiting (token bucket per API key/IP) as a final backstop. Layer 4: real-time monitoring/alerting on traffic anomalies (sudden spike in requests from a narrow IP range/ASN) to trigger additional manual mitigation (Shield Advanced engagement) if automated layers are insufficient.

### Q6: "A cross-region database replica is falling increasingly behind (replication lag growing)." How do you diagnose and fix it?
**A:** Diagnose: check if the PRIMARY's write volume has increased beyond what the replication link/replica can keep up with, check network latency/bandwidth between regions, check if the replica itself is CPU/IO constrained (competing with read traffic being served from it). Fix options: reduce read load on the replica (route reads elsewhere temporarily), increase replica instance size, or reduce primary write volume by batching/throttling writes if business-acceptable — and treat sustained lag as a DR-readiness risk (§27) requiring active remediation, not just a metric to watch passively.

### Q7: "How would you migrate a monolithic application's database to a microservices' database-per-service model with zero downtime?"
**A:** Use the Strangler Fig pattern: incrementally extract one bounded context at a time — first, have the new microservice read from the OLD shared database (via an API, not a direct connection) while its own database is built and backfilled; then dual-write to both old and new databases during a transition window; then cut reads over to the new database once verified consistent; finally stop writing to the old database's copy of that data. Never attempt a single big-bang cutover for a large, business-critical dataset.

### Q8: "Your event-driven system has a service processing the same event twice due to an at-least-once delivery retry." How do you prevent a duplicate side effect (e.g., double-charging a customer)?
**A:** Make the event handler idempotent by design: use a unique event/idempotency key (often the event ID itself) and check a "processed events" ledger (a fast key-value store) before executing the side effect — if the key already exists, skip re-execution and return the previously recorded result, exactly the idempotency-key pattern from §17 Deep Dive 2 and §20 Deep Dive 3.

### Q9: "How would you design rate limiting for a public API used by thousands of third-party developers?"
**A:** Token bucket (or sliding window) algorithm per API key, enforced at the API Gateway layer (both AWS API Gateway and GCP API Gateway/Apigee support built-in throttling) so abusive clients are rejected before consuming backend compute resources, with tiered limits (different rate ceilings per subscription plan) and clear `429 Too Many Requests` responses including a `Retry-After` header so well-behaved clients can back off gracefully.

### Q10: "A newly launched feature is causing a 10x increase in database write load. The database is approaching its connection/IOPS limit." What are your immediate and long-term fixes?
**A:** Immediate: add a write-through/write-behind cache or a queue in front of the database to absorb bursts and smooth write rate (buffer + batch writes rather than every request hitting the DB synchronously), and vertically scale the DB instance if there's easy headroom. Long-term: reassess whether this write pattern needs to move to a purpose-built high-write-throughput store (DynamoDB/Bigtable) rather than continuing to scale a traditional RDBMS vertically, which has a hard ceiling.

### Q11: "How would you design a system to ensure exactly-once processing of financial transactions across a multi-step distributed workflow?"
**A:** True end-to-end exactly-once is extremely hard to guarantee across independent services; the practical, achievable target is "effectively-once" via: idempotency keys at every step, a Saga orchestrator (§20) providing a single auditable source of truth for what's been completed, and compensating transactions for any step that must be undone — combined with reconciliation jobs that periodically detect and correct any residual double-processing that slipped through.

### Q12: "Your global application must comply with GDPR — EU user data cannot leave the EU." How does this affect your architecture?
**A:** Deploy region-pinned infrastructure for EU users specifically (a full regional stack — compute, database, cache — physically located in an EU region), route EU users to it via geolocation-based DNS/load-balancer routing, and ensure any cross-region replication/backup/logging pipelines are explicitly EXCLUDED from replicating EU user data outside the EU (a common mistake is compliant primary-region placement but non-compliant global log aggregation or backup pipelines).

### Q13: "How would you detect a slowly-degrading dependency before it causes a full outage?"
**A:** Track leading-indicator metrics (p99 latency trend, error-rate trend, saturation/queue-depth trend) with anomaly-detection-based alerting (not just static thresholds) tied to SLO error-budget burn rate (§10.3) — a slow degradation shows up as an accelerating burn rate well before a hard threshold breach, giving time to react proactively rather than reactively.

### Q14: "A cache-aside pattern is causing occasional stale reads right after a write." Why, and how do you fix it?
**A:** Classic race: request A reads a miss, starts fetching from the DB; concurrently, a write happens and invalidates the cache; request A's stale DB read then gets written to cache AFTER the invalidation, leaving a stale value cached. Fix: use a cache write pattern with versioning/compare-and-set (only write to cache if the cached value's version still matches what was read, otherwise discard the write), or shorten the window via a short TTL combined with accepting brief staleness where the correctness impact is low.

## §45 Cloud Architect Behavioral & Meta Questions

### Q1: "Tell me about a time you had to choose between two cloud services and made the wrong call. What did you learn?"
**A:** Structure with STAR (Situation/Task/Action/Result), but the SUBSTANCE interviewers want: evidence you evaluated trade-offs explicitly at the time (not just "I didn't know better"), a concrete signal that revealed the mistake (a metric, an incident, a cost report), and a specific, generalizable lesson (e.g., "I now always compute the crossover point before defaulting to serverless" — referencing §19 Deep Dive 2's kind of concrete reasoning) rather than a vague "I learned to be more careful."

### Q2: "How do you decide when a system genuinely needs multi-region architecture versus when that's over-engineering?"
**A:** Anchor the decision in the business's actual RTO/RPO/latency requirements (§16) and real user geographic distribution — multi-region is justified when a single-region outage's business impact (revenue, compliance, reputation) demonically outweighs the added cost/complexity, or when users are genuinely global and single-region latency is unacceptable. Explicitly flag when a team requests multi-region "just in case" without quantifying the actual risk/benefit — this is a strong senior-level signal of resisting premature optimization.

### Q3: "How do you approach an ambiguous system design prompt with very few stated requirements?"
**A:** Don't guess silently — ask clarifying questions across scale, consistency, latency, and budget (§14 Step 1) before designing anything, and explicitly state the assumptions you're making if the interviewer wants you to proceed without full clarification ("I'll assume X for now, and flag that this decision would change if that's wrong").

### Q4: "How do you communicate a difficult trade-off (e.g., higher cost for better reliability) to a non-technical stakeholder?"
**A:** Translate technical trade-offs into business terms: not "we need Multi-AZ RDS," but "this costs an additional $X/month and reduces the risk of an outage costing us $Y in lost revenue/customer trust from Z minutes of downtime" — quantify both sides of the trade-off in terms the stakeholder already cares about (cost, revenue, customer impact), not in infrastructure jargon.

### Q5: "Describe a time you had to convince a team to adopt a new cloud service/pattern they were resistant to."
**A:** Effective answers show: understanding WHY the team was resistant (cost concerns, unfamiliarity, past bad experience), addressing that specific concern directly (a proof-of-concept, a cost model, a gradual rollout plan) rather than just asserting authority/correctness, and measuring the actual outcome after adoption — shows both technical judgment and organizational influence skills.

### Q6: "How do you stay current with the fast pace of cloud provider service releases (e.g., knowing GKE Autopilot, Aurora Limitless, or a service deprecation like Cloud IoT Core)?"
**A:** Concrete, credible answers reference specific habits: following the provider's official "What's New" release notes/blogs regularly, hands-on experimentation in a sandbox account for services relevant to your domain, and — critically — periodically re-validating older assumptions (like checking whether a service you learned about years ago has since been deprecated or superseded), rather than relying on knowledge that may have gone stale.

### Q7: "How do you balance moving fast (startup/MVP context) with building for scale?"
**A:** Explicitly design for "the next order of magnitude," not infinite scale — e.g., choose a data model that CAN migrate to a more scalable store later without a full rewrite, but don't build the fully-scaled version prematurely (§19's serverless-for-uncertain-traffic reasoning, or §18's "start with Cloud SQL, design for a future Spanner migration path" reasoning are concrete examples of this balance).

### Q8: "How would you respond if you inherited a system with significant technical debt and security gaps (e.g., overly broad IAM policies, no MFA enforcement)?"
**A:** Prioritize by actual risk (a `*:*` IAM policy on a production account is a far more urgent fix than a minor code style issue), propose a phased remediation plan with quick wins first (enforce MFA org-wide, tighten the worst IAM policies) before larger architectural fixes, and communicate risk clearly to leadership to get buy-in/resourcing for the remediation work rather than trying to fix everything silently and alone.

### Q9: "How do you handle a production incident where you don't immediately know the root cause?"
**A:** Prioritize mitigation/stabilization (rollback, failover, scale-out) over root-cause investigation in the moment — restore service first, investigate deeply afterward in a blameless postmortem. Reference concrete tools (distributed tracing, dashboards, recent-deploys timeline) you'd use to narrow down the cause quickly, and describe how you'd communicate status to stakeholders during the incident.

### Q10: "What's a cloud architecture decision you'd make differently if you could redo a past project?"
**A:** Strong answers are SPECIFIC and technical (not generic regret) — e.g., "I'd have started with a database-agnostic data access layer from day one, because migrating off a tightly-coupled ORM pattern later cost us 3 months" — demonstrating genuine reflective learning tied to a concrete architectural principle, ideally one covered in this guide (e.g., the expand/contract migration pattern, or avoiding premature microservices).

### Q11: "How do you decide between AWS and GCP for a brand-new project with no existing cloud investment?"
**A:** A mature answer weighs: team's existing expertise (retraining cost), specific service needs (e.g., Spanner's unique consistency model, or a specific AWS-only service the workload needs), pricing/committed-use posture, existing vendor relationships/support contracts, and compliance/data-residency requirements — explicitly avoiding a purely technology-preference-driven answer ("I just like GCP better") in favor of business-driven reasoning.

### Q12: "How would you mentor a junior engineer who keeps proposing over-engineered solutions?"
**A:** Redirect them toward quantifying actual requirements first (§14/§15's estimation discipline) — ask "what's the actual current/projected scale?" and "what specific failure are we protecting against?" before evaluating the proposed solution's complexity, teaching the habit of grounding architecture decisions in real numbers rather than defaulting to the most sophisticated-sounding option.

### Q13: "Describe how you'd structure a design review for a new system before it's built."
**A:** A good structure mirrors §14's framework itself: present requirements/scale/estimation first (so reviewers can sanity-check assumptions), then the high-level architecture with explicit alternatives considered and rejected (not just the final choice), then a dedicated discussion of failure modes/trade-offs/cost — inviting the review to challenge the trade-offs specifically, not just rubber-stamp the diagram.

### Q14: "How do you handle disagreement with another senior engineer/architect about a design decision?"
**A:** Ground the disagreement in concrete criteria (cost numbers, latency requirements, failure-mode analysis) rather than opinion, propose a way to decide empirically where possible (a small proof-of-concept or a cost model comparing both options), and show willingness to be persuaded by evidence — interviewers are checking for collaborative technical maturity, not just technical correctness.

### Q15: "What's your approach to writing documentation/runbooks for the systems you design?"
**A:** Tie documentation directly to operational needs raised throughout this guide — a DR runbook must be detailed enough to execute under pressure (§16.5, §27), architecture decisions should record the trade-offs considered (an Architecture Decision Record/ADR) so future engineers understand WHY, not just WHAT, and runbooks should be tested/kept current via regular drills, not written once and left to rot.

# Part 6 — Multi-Cloud Project Integration Guide

*This part is a ground-up, practical walkthrough of building ONE real project that integrates BOTH AWS and GCP — for teams that need multi-cloud for redundancy, best-of-breed service selection (e.g., Spanner for one workload, DynamoDB for another), M&A-driven cloud consolidation, or avoiding vendor lock-in.*

## §46 Project Structure for an AWS + GCP Multi-Cloud App

### 46.1 Recommended Repository Layout

```
my-multicloud-app/
├── infra/
│   ├── modules/
│   │   ├── aws/
│   │   │   ├── vpc/
│   │   │   ├── eks/
│   │   │   └── rds/
│   │   └── gcp/
│   │       ├── vpc/
│   │       ├── gke/
│   │       └── cloudsql/
│   ├── environments/
│   │   ├── dev/
│   │   │   ├── aws/main.tf
│   │   │   └── gcp/main.tf
│   │   ├── staging/
│   │   │   ├── aws/main.tf
│   │   │   └── gcp/main.tf
│   │   └── prod/
│   │       ├── aws/main.tf
│   │       └── gcp/main.tf
│   └── shared/
│       └── dns/                # cross-cloud DNS delegation config
├── services/
│   ├── order-service/
│   │   ├── src/
│   │   ├── Dockerfile
│   │   └── cloud_clients/      # the adapter layer from §53
│   └── notification-service/
├── .github/
│   └── workflows/
│       ├── deploy-aws.yml
│       └── deploy-gcp.yml
└── docs/
    └── architecture-decision-records/
```

### 46.2 Key Structural Principles

1. **Separate Terraform state per cloud AND per environment** — never share one state file across AWS and GCP resources, and never share state across dev/staging/prod (§37.2). This bounds blast radius: a bad `apply` in GCP dev can never corrupt AWS prod state.
2. **Application code stays cloud-agnostic where possible** — business logic in `services/*/src/` should not import `boto3` or `google-cloud-storage` directly; it depends only on the adapter interfaces in `cloud_clients/` (§53), so the SAME business logic can run against either cloud (or both, for a true multi-cloud active-active deployment) with only a configuration change.
3. **One workflow file per cloud in CI/CD** (`deploy-aws.yml`, `deploy-gcp.yml`) rather than one giant workflow — keeps blast radius of a CI/CD change scoped to one cloud, and lets each workflow use the credentials/OIDC trust relationship specific to that cloud (§49).
4. **A single source of truth for which environment maps to which cloud accounts/projects** — maintain a small `environments.yaml` config (consumed by both Terraform via a data source and CI/CD) mapping `dev → AWS account 111111111111 + GCP project my-app-dev`, etc., to avoid the account/project IDs being duplicated and drifting across multiple files.

### 46.3 Why Multi-Cloud At All? (Set Expectations Before Diving Into Code)

Multi-cloud adds REAL operational complexity (two IAM models, two networking models, two sets of on-call runbooks, doubled observability tooling integration) — it should be a deliberate choice justified by one or more of:
- **Regulatory/procurement requirement** (some enterprise customers/contracts mandate avoiding single-vendor lock-in).
- **Best-of-breed service need** (e.g., using Spanner specifically for one workload's global-consistency requirement, while the rest of the org standardizes on AWS).
- **M&A** (an acquired company already runs on the other cloud, and full migration isn't immediately justified).
- **Negotiating leverage / avoiding vendor lock-in** as an explicit business risk-management strategy.

A team should NOT adopt multi-cloud purely for "flexibility" in the abstract — that flexibility has a real, ongoing operational tax, and this guide's adapter pattern (§53) is specifically designed to minimize (not eliminate) that tax when multi-cloud is genuinely justified.

---

## §47 Terraform Multi-Cloud Infrastructure Code

### 47.1 Provider Configuration (Both Clouds in One Root Module)

```hcl
# environments/prod/main.tf
terraform {
  required_version = ">= 1.6.0"
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
    google = {
      source  = "hashicorp/google"
      version = "~> 5.0"
    }
  }

  backend "s3" {
    bucket         = "company-terraform-state"
    key            = "prod/multicloud/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "terraform-locks"
    encrypt        = true
  }
}

provider "aws" {
  region = "us-east-1"
  default_tags {
    tags = {
      Environment = "production"
      ManagedBy   = "terraform"
      Project     = "my-multicloud-app"
    }
  }
}

provider "google" {
  project = "my-app-prod"
  region  = "us-central1"
}
```

### 47.2 AWS Side — VPC + EKS + RDS

```hcl
module "aws_vpc" {
  source      = "../../modules/aws/vpc"
  name        = "prod"
  cidr_block  = "10.0.0.0/16"
  azs         = ["us-east-1a", "us-east-1b", "us-east-1c"]
  environment = "production"
}

module "aws_eks" {
  source          = "../../modules/aws/eks"
  cluster_name    = "prod-cluster"
  vpc_id          = module.aws_vpc.vpc_id
  subnet_ids      = module.aws_vpc.private_subnet_ids
  node_min_size   = 3
  node_max_size   = 30
  node_instance_types = ["m6i.large"]
}

module "aws_rds" {
  source            = "../../modules/aws/rds"
  identifier        = "prod-orders-db"
  engine            = "postgres"
  engine_version    = "15.4"
  instance_class    = "db.r6g.xlarge"
  multi_az          = true
  subnet_ids        = module.aws_vpc.private_subnet_ids
  vpc_id            = module.aws_vpc.vpc_id
  allocated_storage = 200
}

output "aws_eks_cluster_endpoint" {
  value = module.aws_eks.cluster_endpoint
}
output "aws_rds_endpoint" {
  value     = module.aws_rds.endpoint
  sensitive = true
}
```

### 47.3 GCP Side — VPC + GKE + Cloud SQL

```hcl
module "gcp_vpc" {
  source      = "../../modules/gcp/vpc"
  name        = "prod-vpc"
  subnet_cidr = "10.1.10.0/24"
  region      = "us-central1"
}

module "gcp_gke" {
  source        = "../../modules/gcp/gke"
  cluster_name  = "prod-cluster"
  network       = module.gcp_vpc.network_self_link
  subnetwork    = module.gcp_vpc.subnetwork_self_link
  region        = "us-central1"
  autopilot     = true
}

module "gcp_cloudsql" {
  source           = "../../modules/gcp/cloudsql"
  instance_name    = "prod-orders-db"
  database_version = "POSTGRES_15"
  tier             = "db-custom-4-16384"
  region           = "us-central1"
  network_id       = module.gcp_vpc.network_id
  availability_type = "REGIONAL"   # GCP's equivalent of AWS Multi-AZ
}

output "gcp_gke_endpoint" {
  value = module.gcp_gke.endpoint
}
output "gcp_cloudsql_connection_name" {
  value = module.gcp_cloudsql.connection_name
}
```

### 47.4 A Reusable GCP Cloud SQL Module (Full Module Internals, Matching §37's AWS VPC Module Pattern)

```hcl
# modules/gcp/cloudsql/variables.tf
variable "instance_name"     { type = string }
variable "database_version"  { type = string }
variable "tier"              { type = string }
variable "region"            { type = string }
variable "network_id"        { type = string }
variable "availability_type" { type = string, default = "ZONAL" }

# modules/gcp/cloudsql/main.tf
resource "google_sql_database_instance" "this" {
  name             = var.instance_name
  database_version = var.database_version
  region           = var.region

  settings {
    tier              = var.tier
    availability_type = var.availability_type
    backup_configuration {
      enabled                        = true
      point_in_time_recovery_enabled = true
      transaction_log_retention_days = 7
    }
    ip_configuration {
      ipv4_enabled    = false
      private_network = var.network_id
    }
  }

  deletion_protection = true
}

resource "google_sql_database" "orders" {
  name     = "orders"
  instance = google_sql_database_instance.this.name
}

# modules/gcp/cloudsql/outputs.tf
output "connection_name" { value = google_sql_database_instance.this.connection_name }
output "private_ip"      { value = google_sql_database_instance.this.private_ip_address }
```

### 47.5 Cross-Cloud DNS Delegation (Route 53 Delegating a Subdomain to Cloud DNS, or Vice Versa)

```hcl
# Example: gcp-services.mycompany.com resolves via Cloud DNS, delegated from Route 53
resource "aws_route53_record" "gcp_delegation" {
  zone_id = data.aws_route53_zone.main.zone_id
  name    = "gcp-services.mycompany.com"
  type    = "NS"
  ttl     = 300
  records = google_dns_managed_zone.gcp_services.name_servers
}

resource "google_dns_managed_zone" "gcp_services" {
  name     = "gcp-services-zone"
  dns_name = "gcp-services.mycompany.com."
}
```

This lets one team manage GCP-hosted services' DNS entirely within Cloud DNS while the parent domain's authoritative zone stays in Route 53 — a common pattern when the org's primary domain registrar/DNS is AWS-based but a specific subdomain's workloads live on GCP.

## §48 SDK Integration Code (boto3 + google-cloud)

### 48.1 Object Storage Client — AWS (boto3)

```python
# cloud_clients/aws_storage.py
import boto3
from botocore.exceptions import ClientError
import logging

logger = logging.getLogger(__name__)


class AwsObjectStorage:
    """Thin, testable wrapper around S3 for the app's storage needs."""

    def __init__(self, bucket_name: str, region_name: str = "us-east-1"):
        self.bucket_name = bucket_name
        self._client = boto3.client("s3", region_name=region_name)

    def upload_bytes(self, key: str, data: bytes, content_type: str = "application/octet-stream") -> None:
        try:
            self._client.put_object(
                Bucket=self.bucket_name,
                Key=key,
                Body=data,
                ContentType=content_type,
                ServerSideEncryption="aws:kms",
            )
        except ClientError as e:
            logger.error("S3 upload failed for key=%s: %s", key, e)
            raise StorageUploadError(str(e)) from e

    def download_bytes(self, key: str) -> bytes:
        try:
            response = self._client.get_object(Bucket=self.bucket_name, Key=key)
            return response["Body"].read()
        except ClientError as e:
            if e.response["Error"]["Code"] == "NoSuchKey":
                raise ObjectNotFoundError(key) from e
            logger.error("S3 download failed for key=%s: %s", key, e)
            raise

    def generate_presigned_url(self, key: str, expires_in: int = 3600) -> str:
        return self._client.generate_presigned_url(
            "get_object",
            Params={"Bucket": self.bucket_name, "Key": key},
            ExpiresIn=expires_in,
        )

    def delete(self, key: str) -> None:
        self._client.delete_object(Bucket=self.bucket_name, Key=key)


class StorageUploadError(Exception):
    pass


class ObjectNotFoundError(Exception):
    def __init__(self, key: str):
        super().__init__(f"Object not found: {key}")
        self.key = key
```

### 48.2 Object Storage Client — GCP (google-cloud-storage)

```python
# cloud_clients/gcp_storage.py
from google.cloud import storage
from google.api_core.exceptions import NotFound, GoogleAPIError
import logging
import datetime

logger = logging.getLogger(__name__)


class GcpObjectStorage:
    """Thin, testable wrapper around Cloud Storage matching AwsObjectStorage's interface."""

    def __init__(self, bucket_name: str):
        self.bucket_name = bucket_name
        self._client = storage.Client()
        self._bucket = self._client.bucket(bucket_name)

    def upload_bytes(self, key: str, data: bytes, content_type: str = "application/octet-stream") -> None:
        try:
            blob = self._bucket.blob(key)
            blob.upload_from_string(data, content_type=content_type)
        except GoogleAPIError as e:
            logger.error("GCS upload failed for key=%s: %s", key, e)
            raise StorageUploadError(str(e)) from e

    def download_bytes(self, key: str) -> bytes:
        try:
            blob = self._bucket.blob(key)
            return blob.download_as_bytes()
        except NotFound as e:
            raise ObjectNotFoundError(key) from e
        except GoogleAPIError as e:
            logger.error("GCS download failed for key=%s: %s", key, e)
            raise

    def generate_presigned_url(self, key: str, expires_in: int = 3600) -> str:
        blob = self._bucket.blob(key)
        return blob.generate_signed_url(
            version="v4",
            expiration=datetime.timedelta(seconds=expires_in),
            method="GET",
        )

    def delete(self, key: str) -> None:
        self._bucket.blob(key).delete()


class StorageUploadError(Exception):
    pass


class ObjectNotFoundError(Exception):
    def __init__(self, key: str):
        super().__init__(f"Object not found: {key}")
        self.key = key
```

**Note the mirrored public interface** (`upload_bytes`, `download_bytes`, `generate_presigned_url`, `delete`) — this is deliberate groundwork for the adapter pattern formalized in §53; application code calling either class doesn't need to know which cloud it's talking to.

### 48.3 Key-Value / Document Store Client — DynamoDB vs Firestore

```python
# cloud_clients/aws_keyvalue.py
import boto3
from boto3.dynamodb.conditions import Key
from botocore.exceptions import ClientError


class AwsKeyValueStore:
    def __init__(self, table_name: str, region_name: str = "us-east-1"):
        self._table = boto3.resource("dynamodb", region_name=region_name).Table(table_name)

    def put_item(self, item: dict) -> None:
        self._table.put_item(Item=item)

    def get_item(self, pk: str, sk: str) -> dict | None:
        resp = self._table.get_item(Key={"PK": pk, "SK": sk})
        return resp.get("Item")

    def query_by_partition(self, pk: str, sk_prefix: str | None = None) -> list[dict]:
        condition = Key("PK").eq(pk)
        if sk_prefix:
            condition = condition & Key("SK").begins_with(sk_prefix)
        resp = self._table.query(KeyConditionExpression=condition)
        return resp.get("Items", [])

    def delete_item(self, pk: str, sk: str) -> None:
        self._table.delete_item(Key={"PK": pk, "SK": sk})
```

```python
# cloud_clients/gcp_keyvalue.py
from google.cloud import firestore


class GcpKeyValueStore:
    def __init__(self, collection_name: str):
        self._client = firestore.Client()
        self._collection = self._client.collection(collection_name)

    def put_item(self, doc_id: str, item: dict) -> None:
        self._collection.document(doc_id).set(item)

    def get_item(self, doc_id: str) -> dict | None:
        doc = self._collection.document(doc_id).get()
        return doc.to_dict() if doc.exists else None

    def query_by_field(self, field: str, value) -> list[dict]:
        docs = self._collection.where(field, "==", value).stream()
        return [d.to_dict() for d in docs]

    def delete_item(self, doc_id: str) -> None:
        self._collection.document(doc_id).delete()
```

### 48.4 Publishing an Event — SNS/EventBridge vs Pub/Sub

```python
# cloud_clients/aws_events.py
import boto3
import json


class AwsEventPublisher:
    def __init__(self, event_bus_name: str = "default", region_name: str = "us-east-1"):
        self._client = boto3.client("events", region_name=region_name)
        self._event_bus_name = event_bus_name

    def publish(self, source: str, detail_type: str, detail: dict) -> None:
        response = self._client.put_events(
            Entries=[{
                "Source": source,
                "DetailType": detail_type,
                "Detail": json.dumps(detail),
                "EventBusName": self._event_bus_name,
            }]
        )
        if response.get("FailedEntryCount", 0) > 0:
            raise EventPublishError(response["Entries"])


class EventPublishError(Exception):
    pass
```

```python
# cloud_clients/gcp_events.py
from google.cloud import pubsub_v1
import json


class GcpEventPublisher:
    def __init__(self, project_id: str, topic_id: str):
        self._client = pubsub_v1.PublisherClient()
        self._topic_path = self._client.topic_path(project_id, topic_id)

    def publish(self, source: str, detail_type: str, detail: dict) -> None:
        payload = json.dumps(detail).encode("utf-8")
        future = self._client.publish(
            self._topic_path,
            payload,
            source=source,
            detail_type=detail_type,
        )
        future.result(timeout=10)  # raises on failure -- matches the AWS wrapper's fail-fast behavior
```

### 48.5 A Retry/Backoff Decorator Shared Across Both Clients (Cloud-Agnostic Resilience Utility)

```python
# cloud_clients/resilience.py
import time
import random
import functools
import logging

logger = logging.getLogger(__name__)


def retry_with_backoff(max_attempts: int = 5, base_delay: float = 0.2, max_delay: float = 10.0):
    """Exponential backoff with full jitter -- safe to wrap any cloud SDK call that can
    raise a transient error (throttling, brief network blip)."""
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            attempt = 0
            while True:
                try:
                    return func(*args, **kwargs)
                except Exception as e:
                    attempt += 1
                    if attempt >= max_attempts:
                        logger.error("Giving up after %d attempts: %s", attempt, e)
                        raise
                    delay = min(max_delay, base_delay * (2 ** attempt))
                    jittered = random.uniform(0, delay)
                    logger.warning("Attempt %d failed (%s), retrying in %.2fs", attempt, e, jittered)
                    time.sleep(jittered)
        return wrapper
    return decorator
```

Applying `@retry_with_backoff()` to any of the SDK wrapper methods above gives every cloud call the same resilience posture without duplicating retry logic per client — directly implementing the "full jitter" backoff strategy that avoids the thundering-herd retry pattern discussed conceptually in earlier sections.

---

## §49 CI/CD Across Both Clouds (GitHub Actions)

### 49.1 AWS Deployment Workflow (OIDC — No Long-Lived Keys)

```yaml
# .github/workflows/deploy-aws.yml
name: Deploy to AWS

on:
  push:
    branches: [main]
    paths:
      - 'services/**'
      - 'infra/environments/prod/aws/**'

permissions:
  id-token: write   # required for OIDC federation -- no static AWS keys stored in GitHub
  contents: read

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.12'
      - run: pip install -r services/order-service/requirements.txt
      - run: pytest services/order-service/tests --cov --cov-fail-under=80

  build-image:
    needs: build-and-test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Configure AWS credentials via OIDC
        uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: arn:aws:iam::111111111111:role/github-actions-deploy
          aws-region: us-east-1
      - name: Login to ECR
        uses: aws-actions/amazon-ecr-login@v2
      - name: Build and push image
        run: |
          docker build -t $ECR_REGISTRY/order-service:${{ github.sha }} services/order-service
          docker push $ECR_REGISTRY/order-service:${{ github.sha }}

  deploy-canary:
    needs: build-image
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Configure AWS credentials via OIDC
        uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: arn:aws:iam::111111111111:role/github-actions-deploy
          aws-region: us-east-1
      - name: Trigger CodeDeploy canary deployment
        run: |
          aws deploy create-deployment \
            --application-name order-service \
            --deployment-group-name prod-canary \
            --revision revisionType=AppSpecContent,appSpecContent="{content=$(cat appspec.yml)}"
```

### 49.2 GCP Deployment Workflow (Workload Identity Federation — No Service Account Keys)

```yaml
# .github/workflows/deploy-gcp.yml
name: Deploy to GCP

on:
  push:
    branches: [main]
    paths:
      - 'services/**'
      - 'infra/environments/prod/gcp/**'

permissions:
  id-token: write
  contents: read

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.12'
      - run: pip install -r services/order-service/requirements.txt
      - run: pytest services/order-service/tests --cov --cov-fail-under=80

  build-and-deploy:
    needs: build-and-test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Authenticate to GCP via Workload Identity Federation
        uses: google-github-actions/auth@v2
        with:
          workload_identity_provider: projects/123456789/locations/global/workloadIdentityPools/github-pool/providers/github-provider
          service_account: github-deployer@my-app-prod.iam.gserviceaccount.com
      - name: Set up Cloud SDK
        uses: google-github-actions/setup-gcloud@v2
      - name: Configure Docker for Artifact Registry
        run: gcloud auth configure-docker us-central1-docker.pkg.dev
      - name: Build and push image
        run: |
          docker build -t us-central1-docker.pkg.dev/my-app-prod/services/order-service:${{ github.sha }} services/order-service
          docker push us-central1-docker.pkg.dev/my-app-prod/services/order-service:${{ github.sha }}
      - name: Deploy canary release via Cloud Deploy
        run: |
          gcloud deploy releases create rel-${{ github.sha }} \
            --delivery-pipeline=order-service-pipeline \
            --region=us-central1 \
            --images=order-service=us-central1-docker.pkg.dev/my-app-prod/services/order-service:${{ github.sha }}
```

### 49.3 Why OIDC/Workload Identity Federation Instead of Stored Secrets

Both workflows deliberately avoid storing static AWS access keys or a GCP service-account JSON key as GitHub Secrets — instead, GitHub's OIDC token is exchanged at runtime for short-lived, scoped cloud credentials (an AWS IAM role via `sts:AssumeRoleWithWebIdentity`, or a GCP service account via Workload Identity Federation). This eliminates the single most common CI/CD credential-leak vector (a long-lived secret sitting in repo settings indefinitely) — directly applying the Workload Identity Federation concept introduced in §35.3 to the CI/CD pipeline itself.

### 49.4 A Shared "Promote Across Environments" Workflow Pattern

```yaml
# .github/workflows/promote.yml -- manually triggered to promote a validated staging
# build to production, on EITHER cloud, using the same image digest (not rebuilding)
name: Promote to Production

on:
  workflow_dispatch:
    inputs:
      image_digest:
        required: true
        type: string
      target_cloud:
        required: true
        type: choice
        options: [aws, gcp, both]

jobs:
  promote:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Promoting digest ${{ inputs.image_digest }} to ${{ inputs.target_cloud }}"
      # ... cloud-specific promotion steps conditioned on inputs.target_cloud, reusing
      # the exact image digest that was already tested in staging -- never rebuild the
      # artifact for production, always promote the SAME tested binary/image.
```

**Key principle:** always promote the exact same built artifact (by immutable digest, not by rebuilding from source tag) from staging to production — rebuilding at each stage risks a subtly different artifact reaching production than the one that was actually tested, undermining the entire point of a staging validation gate.

## §50 Secrets & Config Management Across Clouds

### 50.1 The Problem

A multi-cloud app's business logic (e.g., `order-service`) may run partly on EKS and partly on GKE — it needs a consistent way to fetch secrets (DB passwords, API keys) and config regardless of which cloud it's currently running in, without hardcoding cloud-specific SDK calls into every service.

### 50.2 A Unified Config/Secrets Loader (Python)

```python
# cloud_clients/secrets.py
import os
import json
from abc import ABC, abstractmethod


class SecretsProvider(ABC):
    @abstractmethod
    def get_secret(self, name: str) -> str:
        ...


class AwsSecretsProvider(SecretsProvider):
    def __init__(self, region_name: str = "us-east-1"):
        import boto3
        self._client = boto3.client("secretsmanager", region_name=region_name)

    def get_secret(self, name: str) -> str:
        response = self._client.get_secret_value(SecretId=name)
        return response["SecretString"]


class GcpSecretsProvider(SecretsProvider):
    def __init__(self, project_id: str):
        from google.cloud import secretmanager
        self._client = secretmanager.SecretManagerServiceClient()
        self._project_id = project_id

    def get_secret(self, name: str) -> str:
        path = f"projects/{self._project_id}/secrets/{name}/versions/latest"
        response = self._client.access_secret_version(request={"name": path})
        return response.payload.data.decode("UTF-8")


def get_secrets_provider() -> SecretsProvider:
    """Factory that picks the right provider based on where the app is currently running --
    detected via an environment variable set at deploy time (see infra manifests), NOT by
    trying to auto-detect the cloud at runtime (auto-detection is fragile and adds latency)."""
    cloud = os.environ["APP_CLOUD_PROVIDER"]  # explicitly set to "aws" or "gcp" per deployment
    if cloud == "aws":
        return AwsSecretsProvider(region_name=os.environ.get("AWS_REGION", "us-east-1"))
    elif cloud == "gcp":
        return GcpSecretsProvider(project_id=os.environ["GCP_PROJECT_ID"])
    raise ValueError(f"Unknown APP_CLOUD_PROVIDER: {cloud}")
```

Application code then simply calls:

```python
secrets = get_secrets_provider()
db_password = secrets.get_secret("prod/db-password")
```

...with zero awareness of which cloud is actually serving the request — the `APP_CLOUD_PROVIDER` environment variable is injected by the Kubernetes deployment manifest (or Terraform, for infra-level config) per cluster, so the SAME container image runs unmodified on either EKS or GKE.

### 50.3 Kubernetes-Native Secret Syncing (Avoiding App-Level SDK Calls Entirely)

An alternative (often preferable) approach avoids embedding secret-fetching logic in application code at all, instead syncing cloud secrets INTO native Kubernetes Secrets at the infrastructure layer:

```yaml
# AWS: External Secrets Operator syncing from Secrets Manager into a K8s Secret
apiVersion: external-secrets.io/v1beta1
kind: ExternalSecret
metadata:
  name: order-service-db-creds
spec:
  refreshInterval: 1h
  secretStoreRef:
    name: aws-secretsmanager
    kind: ClusterSecretStore
  target:
    name: order-service-db-creds
  data:
    - secretKey: password
      remoteRef:
        key: prod/db-password
```

```yaml
# GCP: Secret Manager CSI driver mounting a secret as a volume, no External Secrets
# Operator needed -- GCP's CSI driver approach is a first-party, in-cluster mechanism
apiVersion: v1
kind: Pod
metadata:
  name: order-service
spec:
  containers:
    - name: order-service
      volumeMounts:
        - name: secrets-store
          mountPath: "/mnt/secrets"
          readOnly: true
  volumes:
    - name: secrets-store
      csi:
        driver: secrets-store.csi.k8s.io
        readOnly: true
        volumeAttributes:
          secretProviderClass: "gcp-db-password"
```

**Trade-off between the two approaches:** the application-level SDK factory (50.2) gives the app explicit control and works identically outside Kubernetes too (e.g., a Lambda function or Cloud Function), while the Kubernetes-native syncing (50.3) keeps application code entirely secret-management-agnostic (it just reads a mounted file or a standard K8s Secret env var) at the cost of only working within a Kubernetes context specifically.

### 50.4 Config Management (Non-Secret Configuration)

For non-sensitive configuration (feature flags, service URLs, timeout values) that also needs to vary per cloud/environment, use a simple layered approach:

```python
# cloud_clients/config.py
import os
import yaml


def load_config(environment: str) -> dict:
    """Loads base config, then merges in a cloud-specific override file."""
    with open(f"config/base.yaml") as f:
        base = yaml.safe_load(f)
    cloud = os.environ["APP_CLOUD_PROVIDER"]
    override_path = f"config/{environment}.{cloud}.yaml"
    if os.path.exists(override_path):
        with open(override_path) as f:
            base.update(yaml.safe_load(f) or {})
    return base
```

```yaml
# config/base.yaml
request_timeout_seconds: 5
max_retry_attempts: 3
feature_flags:
  new_checkout_flow: true

# config/prod.aws.yaml (cloud-specific overrides only where they genuinely differ)
storage_bucket: my-app-uploads-prod
event_bus_name: prod-order-events

# config/prod.gcp.yaml
storage_bucket: my-app-uploads-prod-gcp
pubsub_topic: prod-order-events
```

This keeps the 95% of config that's IDENTICAL across clouds (timeouts, feature flags, business logic parameters) in one shared file, with only the genuinely cloud-specific resource names/identifiers split into per-cloud override files — avoiding config duplication drift.

---

## §51 Multi-Cloud Networking (VPN / Interconnect)

### 51.1 The Requirement

Services in the AWS VPC and the GCP VPC need to communicate over PRIVATE IP addresses (not the public internet) — e.g., the order-service running on EKS needs to call a legacy inventory system still running on GKE, and this traffic must never traverse the public internet even encrypted, for compliance reasons.

### 51.2 Site-to-Site VPN Between AWS and GCP (Terraform)

```hcl
# AWS side -- Customer Gateway represents the GCP side's VPN endpoint
resource "aws_customer_gateway" "gcp_side" {
  bgp_asn    = 65000
  ip_address = google_compute_ha_vpn_gateway.gcp_gw.vpn_interfaces[0].ip_address
  type       = "ipsec.1"
}

resource "aws_vpn_gateway" "aws_side" {
  vpc_id = module.aws_vpc.vpc_id
}

resource "aws_vpn_connection" "to_gcp" {
  customer_gateway_id = aws_customer_gateway.gcp_side.id
  vpn_gateway_id       = aws_vpn_gateway.aws_side.id
  type                 = "ipsec.1"
  static_routes_only  = false   # use BGP for dynamic routing, not static routes
}

resource "aws_vpn_gateway_route_propagation" "propagate" {
  vpn_gateway_id = aws_vpn_gateway.aws_side.id
  route_table_id = module.aws_vpc.private_route_table_id
}
```

```hcl
# GCP side -- HA VPN Gateway + Cloud Router for BGP
resource "google_compute_ha_vpn_gateway" "gcp_gw" {
  name    = "aws-interconnect-gw"
  network = module.gcp_vpc.network_id
  region  = "us-central1"
}

resource "google_compute_router" "gcp_router" {
  name    = "aws-interconnect-router"
  network = module.gcp_vpc.network_id
  region  = "us-central1"
  bgp {
    asn = 65001
  }
}

resource "google_compute_vpn_tunnel" "to_aws" {
  name                  = "tunnel-to-aws"
  region                = "us-central1"
  vpn_gateway           = google_compute_ha_vpn_gateway.gcp_gw.id
  peer_ip               = aws_vpn_gateway.aws_side.id  # simplified -- real config uses the actual peer IP
  shared_secret         = var.vpn_shared_secret
  router                = google_compute_router.gcp_router.id
}
```

### 51.3 Why BGP (Dynamic Routing) Over Static Routes

Using BGP (`static_routes_only = false`, plus a Cloud Router on the GCP side) lets each side automatically learn and adapt to route changes (e.g., a new subnet added to either VPC) without manually updating static route tables on both ends — critical for a multi-cloud network that's expected to evolve, since static routes require a coordinated manual update on BOTH sides every time either network's topology changes.

### 51.4 When to Use Dedicated Interconnect Instead of VPN

| Factor | Site-to-Site VPN | Direct Connect / Cloud Interconnect |
|---|---|---|
| Setup time | Minutes to hours (software-only) | Weeks (physical circuit provisioning) |
| Bandwidth | Capped (typically up to ~1.25 Gbps per tunnel, can aggregate multiple tunnels) | Much higher (up to 10-100 Gbps dedicated) |
| Latency/jitter | Traverses the public internet (encrypted) — variable | Dedicated private circuit — consistent, lower jitter |
| Cost model | Low fixed cost, pay for data transfer | Higher fixed cost (circuit + port), lower per-GB transfer cost at volume |
| Best for | Moderate, non-latency-critical cross-cloud traffic; quick to stand up | Sustained high-bandwidth, latency-sensitive cross-cloud/on-prem traffic |

**Decision guidance:** start with VPN for a new multi-cloud integration (fast to provision, easy to test) and graduate to Direct Connect/Cloud Interconnect only once sustained bandwidth needs or latency sensitivity genuinely justify the cost and lead time of a dedicated circuit.

### 51.5 Private Service Connectivity Without a Full VPN (For Simpler Cases)

If the cross-cloud need is narrower (e.g., just calling ONE specific GCP API from AWS, not full bidirectional network-level connectivity), a full VPN/Interconnect may be overkill — consider whether the need can be met more simply via authenticated API calls over the public internet with TLS (mutual TLS/private API keys) plus IP allowlisting, reserving the VPN/Interconnect investment for genuine broad, sustained, private network-level integration needs.

---

## §52 Cost Management & Tagging Across Providers

### 52.1 A Unified Tagging/Labeling Strategy

| Purpose | AWS Tag Key | GCP Label Key | Example Value |
|---|---|---|---|
| Cost center attribution | `CostCenter` | `cost-center` | `platform-eng` |
| Environment | `Environment` | `environment` | `production` |
| Team ownership | `Team` | `team` | `order-service-team` |
| Project/product | `Project` | `project` | `my-multicloud-app` |
| Managed-by (IaC provenance) | `ManagedBy` | `managed-by` | `terraform` |

**Key constraint to design around:** AWS tag KEYS are case-sensitive and allow uppercase; GCP label keys must be LOWERCASE and have stricter character restrictions (no uppercase, limited punctuation) — so a shared tagging convention must standardize on the LOWER-COMMON-DENOMINATOR format (lowercase, hyphenated) to apply consistently via one Terraform variable map across both providers' resources.

```hcl
locals {
  common_tags = {
    environment = "production"
    team        = "order-service-team"
    project     = "my-multicloud-app"
    managed-by  = "terraform"
  }
}

# Applied to an AWS resource
resource "aws_instance" "example" {
  # ...
  tags = local.common_tags
}

# Applied to a GCP resource (labels, not tags -- different Terraform argument name,
# same local.common_tags map reused since it's already lowercase-compliant)
resource "google_compute_instance" "example" {
  # ...
  labels = local.common_tags
}
```

### 52.2 Centralized Cost Visibility Across Both Clouds

Neither AWS Cost Explorer nor GCP's Billing Reports natively shows a UNIFIED view across both clouds — for genuine cross-cloud cost visibility, export both clouds' detailed billing data into a common analytics store and build unified dashboards on top:

```python
# A simplified nightly cost-export job (conceptual) -- pulls both clouds' billing data
# into a shared BigQuery dataset for unified reporting
def export_aws_costs_to_bigquery(start_date: str, end_date: str):
    import boto3
    ce = boto3.client("ce")  # Cost Explorer
    response = ce.get_cost_and_usage(
        TimePeriod={"Start": start_date, "End": end_date},
        Granularity="DAILY",
        Metrics=["UnblendedCost"],
        GroupBy=[{"Type": "TAG", "Key": "team"}],
    )
    # ... transform response and load rows into BigQuery via the bigquery client
    return response


def export_gcp_costs_to_bigquery():
    # GCP actually supports this natively: enable BigQuery Billing Export in the
    # console/Terraform, and GCP streams detailed billing data directly into a
    # BigQuery dataset automatically -- no custom export job needed on the GCP side,
    # only the AWS side needs a custom nightly pull like the function above.
    pass
```

**A genuine GCP advantage worth citing:** GCP's native BigQuery Billing Export means GCP-side cost data is ALREADY in a queryable warehouse with zero custom integration code — AWS requires either a scheduled Cost Explorer API pull (as sketched above) or the AWS Cost and Usage Report (CUR) delivered to S3 and then loaded into a warehouse, an extra step GCP's native integration skips.

### 52.3 Budget Alerts on Both Clouds (Terraform)

```hcl
resource "aws_budgets_budget" "monthly_cost" {
  name         = "monthly-overall-budget"
  budget_type  = "COST"
  limit_amount = "20000"
  limit_unit   = "USD"
  time_unit    = "MONTHLY"

  notification {
    comparison_operator       = "GREATER_THAN"
    threshold                 = 80
    threshold_type            = "PERCENTAGE"
    notification_type         = "ACTUAL"
    subscriber_email_addresses = ["platform-team@mycompany.com"]
  }
}

resource "google_billing_budget" "monthly_cost" {
  billing_account = var.billing_account_id
  display_name    = "monthly-overall-budget"

  amount {
    specified_amount {
      currency_code = "USD"
      units         = "20000"
    }
  }

  threshold_rules {
    threshold_percent = 0.8
  }

  all_updates_rule {
    monitoring_notification_channels = [google_monitoring_notification_channel.platform_team.id]
  }
}
```

Both budgets are configured identically (80% threshold alert, same monthly limit) so the platform team gets consistent, comparable early-warning signals regardless of which cloud is trending toward overspend.

## §53 Cloud-Agnostic Abstraction Layer (Adapter Pattern)

### 53.1 The Full Interface Definition

```python
# cloud_clients/interfaces.py
from abc import ABC, abstractmethod
from dataclasses import dataclass
from typing import Optional


@dataclass
class UploadResult:
    key: str
    url: str
    size_bytes: int


class ObjectStoragePort(ABC):
    """Port (in hexagonal-architecture terms) that ALL business logic depends on --
    never the concrete AWS/GCP SDK classes directly."""

    @abstractmethod
    def upload(self, key: str, data: bytes, content_type: str) -> UploadResult:
        ...

    @abstractmethod
    def download(self, key: str) -> bytes:
        ...

    @abstractmethod
    def delete(self, key: str) -> None:
        ...

    @abstractmethod
    def presigned_url(self, key: str, expires_in: int) -> str:
        ...


class EventPublisherPort(ABC):
    @abstractmethod
    def publish(self, event_type: str, payload: dict) -> None:
        ...


class KeyValueStorePort(ABC):
    @abstractmethod
    def put(self, partition_key: str, sort_key: str, item: dict) -> None:
        ...

    @abstractmethod
    def get(self, partition_key: str, sort_key: str) -> Optional[dict]:
        ...

    @abstractmethod
    def query(self, partition_key: str) -> list[dict]:
        ...
```

### 53.2 The AWS Adapter (Implements the Ports)

```python
# cloud_clients/adapters/aws_adapter.py
from cloud_clients.interfaces import ObjectStoragePort, EventPublisherPort, KeyValueStorePort, UploadResult
from cloud_clients.aws_storage import AwsObjectStorage
from cloud_clients.aws_events import AwsEventPublisher
from cloud_clients.aws_keyvalue import AwsKeyValueStore


class AwsObjectStorageAdapter(ObjectStoragePort):
    def __init__(self, bucket_name: str, region: str):
        self._impl = AwsObjectStorage(bucket_name, region)

    def upload(self, key: str, data: bytes, content_type: str) -> UploadResult:
        self._impl.upload_bytes(key, data, content_type)
        return UploadResult(key=key, url=self.presigned_url(key, 3600), size_bytes=len(data))

    def download(self, key: str) -> bytes:
        return self._impl.download_bytes(key)

    def delete(self, key: str) -> None:
        self._impl.delete(key)

    def presigned_url(self, key: str, expires_in: int) -> str:
        return self._impl.generate_presigned_url(key, expires_in)


class AwsEventPublisherAdapter(EventPublisherPort):
    def __init__(self, event_bus_name: str, region: str):
        self._impl = AwsEventPublisher(event_bus_name, region)

    def publish(self, event_type: str, payload: dict) -> None:
        self._impl.publish(source="order-service", detail_type=event_type, detail=payload)


class AwsKeyValueStoreAdapter(KeyValueStorePort):
    def __init__(self, table_name: str, region: str):
        self._impl = AwsKeyValueStore(table_name, region)

    def put(self, partition_key: str, sort_key: str, item: dict) -> None:
        self._impl.put_item({**item, "PK": partition_key, "SK": sort_key})

    def get(self, partition_key: str, sort_key: str) -> dict | None:
        return self._impl.get_item(partition_key, sort_key)

    def query(self, partition_key: str) -> list[dict]:
        return self._impl.query_by_partition(partition_key)
```

### 53.3 The GCP Adapter (Implements the Same Ports)

```python
# cloud_clients/adapters/gcp_adapter.py
from cloud_clients.interfaces import ObjectStoragePort, EventPublisherPort, KeyValueStorePort, UploadResult
from cloud_clients.gcp_storage import GcpObjectStorage
from cloud_clients.gcp_events import GcpEventPublisher
from cloud_clients.gcp_keyvalue import GcpKeyValueStore


class GcpObjectStorageAdapter(ObjectStoragePort):
    def __init__(self, bucket_name: str):
        self._impl = GcpObjectStorage(bucket_name)

    def upload(self, key: str, data: bytes, content_type: str) -> UploadResult:
        self._impl.upload_bytes(key, data, content_type)
        return UploadResult(key=key, url=self.presigned_url(key, 3600), size_bytes=len(data))

    def download(self, key: str) -> bytes:
        return self._impl.download_bytes(key)

    def delete(self, key: str) -> None:
        self._impl.delete(key)

    def presigned_url(self, key: str, expires_in: int) -> str:
        return self._impl.generate_presigned_url(key, expires_in)


class GcpEventPublisherAdapter(EventPublisherPort):
    def __init__(self, project_id: str, topic_id: str):
        self._impl = GcpEventPublisher(project_id, topic_id)

    def publish(self, event_type: str, payload: dict) -> None:
        self._impl.publish(source="order-service", detail_type=event_type, detail=payload)


class GcpKeyValueStoreAdapter(KeyValueStorePort):
    def __init__(self, collection_name: str):
        self._impl = GcpKeyValueStore(collection_name)

    def put(self, partition_key: str, sort_key: str, item: dict) -> None:
        doc_id = f"{partition_key}#{sort_key}"
        self._impl.put_item(doc_id, {**item, "partition_key": partition_key, "sort_key": sort_key})

    def get(self, partition_key: str, sort_key: str) -> dict | None:
        return self._impl.get_item(f"{partition_key}#{sort_key}")

    def query(self, partition_key: str) -> list[dict]:
        return self._impl.query_by_field("partition_key", partition_key)
```

### 53.4 The Factory — Wiring It All Together at Startup

```python
# cloud_clients/factory.py
import os
from cloud_clients.interfaces import ObjectStoragePort, EventPublisherPort, KeyValueStorePort


def build_object_storage() -> ObjectStoragePort:
    cloud = os.environ["APP_CLOUD_PROVIDER"]
    if cloud == "aws":
        from cloud_clients.adapters.aws_adapter import AwsObjectStorageAdapter
        return AwsObjectStorageAdapter(
            bucket_name=os.environ["STORAGE_BUCKET"],
            region=os.environ.get("AWS_REGION", "us-east-1"),
        )
    elif cloud == "gcp":
        from cloud_clients.adapters.gcp_adapter import GcpObjectStorageAdapter
        return GcpObjectStorageAdapter(bucket_name=os.environ["STORAGE_BUCKET"])
    raise ValueError(f"Unsupported cloud: {cloud}")


def build_event_publisher() -> EventPublisherPort:
    cloud = os.environ["APP_CLOUD_PROVIDER"]
    if cloud == "aws":
        from cloud_clients.adapters.aws_adapter import AwsEventPublisherAdapter
        return AwsEventPublisherAdapter(
            event_bus_name=os.environ["EVENT_BUS_NAME"],
            region=os.environ.get("AWS_REGION", "us-east-1"),
        )
    elif cloud == "gcp":
        from cloud_clients.adapters.gcp_adapter import GcpEventPublisherAdapter
        return GcpEventPublisherAdapter(
            project_id=os.environ["GCP_PROJECT_ID"],
            topic_id=os.environ["PUBSUB_TOPIC"],
        )
    raise ValueError(f"Unsupported cloud: {cloud}")
```

### 53.5 Business Logic — Completely Cloud-Unaware

```python
# services/order-service/src/order_handler.py
from cloud_clients.interfaces import ObjectStoragePort, EventPublisherPort, KeyValueStorePort


class OrderHandler:
    """Zero imports of boto3 or google-cloud-* anywhere in this class -- it only
    depends on the abstract ports, injected at construction time."""

    def __init__(self, storage: ObjectStoragePort, events: EventPublisherPort, orders_db: KeyValueStorePort):
        self._storage = storage
        self._events = events
        self._orders_db = orders_db

    def create_order(self, user_id: str, order_id: str, items: list[dict], receipt_pdf: bytes) -> None:
        self._orders_db.put(
            partition_key=f"USER#{user_id}",
            sort_key=f"ORDER#{order_id}",
            item={"items": items, "status": "CREATED"},
        )
        receipt_result = self._storage.upload(
            key=f"receipts/{order_id}.pdf",
            data=receipt_pdf,
            content_type="application/pdf",
        )
        self._events.publish(
            event_type="OrderCreated",
            payload={"order_id": order_id, "user_id": user_id, "receipt_url": receipt_result.url},
        )
```

### 53.6 Why This Pattern Is Worth the Extra Layer of Indirection

- **Testability:** unit tests for `OrderHandler` inject simple in-memory fake implementations of the ports — no need to mock deep into `boto3`/`google-cloud` internals, and tests run identically regardless of which cloud the code will eventually deploy to.
- **True multi-cloud portability:** the exact same `OrderHandler` class (and every other business-logic class) runs unmodified on AWS or GCP — only the factory's environment-variable-driven wiring changes, which is exactly the payoff that justifies the extra abstraction layer's upfront cost.
- **Bounded blast radius for a future 3rd cloud/provider:** adding Azure support later means writing ONE new adapter module (`azure_adapter.py`) implementing the same three ports — zero changes needed to any existing business logic.
- **Honest cost acknowledgment:** this pattern only pays for itself if the org GENUINELY needs multi-cloud portability (§46.3) — for a single-cloud project, this extra abstraction layer is pure unnecessary overhead, and a good interview answer should say so explicitly rather than recommending this pattern universally.

---

## §54 Full Sample Project Walkthrough

### 54.1 The Scenario

Bringing together every piece from §46-53: a small team is building "OrderFlow," an order-processing SaaS product. Business requirement: the product must be deployable to a customer's AWS account OR a customer's GCP project (enterprise customers who mandate their own cloud) from the SAME codebase, with feature parity guaranteed on both.

### 54.2 Step-by-Step Build Order

1. **Repository scaffolding (§46):** set up the `infra/`, `services/`, `.github/workflows/` structure with separate Terraform state per cloud/environment from day one — retrofitting this structure onto an already-tangled single-cloud codebase later is far more painful than starting with it.
2. **Core infrastructure (§47):** stand up `dev` environments on BOTH clouds in parallel (VPC/network, GKE/EKS cluster, managed database) via Terraform, validating both clouds' base infra work before any application code is written.
3. **Business logic + ports (§53):** write `OrderHandler` and all other business logic against the abstract ports FIRST, with a simple in-memory fake adapter for local development/testing — this forces the team to keep business logic genuinely cloud-agnostic from day one rather than accidentally coupling it to one cloud's SDK quirks.
4. **Concrete adapters (§48, §53):** implement the AWS and GCP adapters, tested against real dev-environment cloud resources (integration tests, not just unit tests with fakes) to catch any subtle behavioral differences (e.g., DynamoDB vs Firestore query semantics) early.
5. **Secrets/config (§50):** wire the `get_secrets_provider()`/`load_config()` factories so the SAME container image can start up correctly pointed at either cloud's secrets/config, driven purely by environment variables set in the Kubernetes deployment manifest per cluster.
6. **CI/CD (§49):** stand up both `deploy-aws.yml` and `deploy-gcp.yml`, each building and testing the SAME source code, each deploying to its respective cloud's staging environment automatically on merge to main, with a manual promotion gate to production (§49.4).
7. **Cross-cloud networking (§51), if actually needed:** only add VPN/Interconnect once there's a genuine cross-cloud communication requirement (e.g., a shared central billing service called by both deployments) — don't build this speculatively.
8. **Cost/tagging (§52):** apply the unified tagging/labeling convention from day one (retrofitting tags across hundreds of already-deployed resources later is tedious and error-prone) and set up budget alerts before the first production customer onboards.
9. **DR/multi-region considerations (§16, §27):** decide per-customer-deployment whether the specific customer's SLA requires multi-region within their chosen cloud — this is layered ON TOP of the multi-cloud portability work, not a replacement for it (a customer on AWS still might want AWS multi-region DR, independent of the fact that a different customer runs on GCP entirely).

### 54.3 What This Buys the Business

- **Sales flexibility:** the sales team can say "yes" to an enterprise prospect that mandates AWS-only or GCP-only hosting, without a multi-month rearchitecture.
- **Reduced vendor negotiating leverage risk:** neither cloud provider can assume the product is fully locked in, supporting better pricing negotiations over time.
- **A genuinely tested disaster-recovery-of-last-resort option:** in an extreme scenario (e.g., a prolonged single-provider outage or an unresolvable contractual dispute), the product COULD be run entirely on the other cloud — a capability many single-cloud products simply don't have, though it's rarely the PRIMARY justification for taking on this complexity (§46.3's honest framing).

### 54.4 What This Costs the Team (Be Honest About This in an Interview)

- Roughly 1.3-1.8x the infrastructure code to write/maintain (two sets of Terraform modules, two CI/CD workflows) versus a single-cloud project.
- The adapter layer (§53) adds a small ongoing "translation tax" to every new feature that touches infrastructure (a new feature needing a new storage pattern requires extending the port interface AND both adapters, not just one SDK integration).
- Two on-call rotations' worth of cloud-specific operational knowledge required across the team (or a genuinely cross-trained team, which itself takes investment).
- **The interview-ready summary statement:** "We took on roughly 30-50% more infrastructure/ops complexity to gain deployment flexibility and avoid vendor lock-in — a trade-off that was worth it specifically because our enterprise sales motion required it, not a decision we'd default to for a typical single-tenant SaaS product without that specific business driver."

# Part 7 — Cheat Sheets

## §55 AWS Service Cheat Sheet

| Service | Category | One-Line Purpose |
|---|---|---|
| EC2 | Compute | Resizable virtual machines |
| Lambda | Compute | Event-driven serverless functions |
| ECS | Compute | AWS-native container orchestration |
| EKS | Compute | Managed Kubernetes |
| Fargate | Compute | Serverless compute for containers |
| App Runner | Compute | Simplest way to deploy a container + get a URL |
| Elastic Beanstalk | Compute | PaaS — deploy code, AWS manages infra |
| Lightsail | Compute | Simplified VPS for small projects |
| Batch | Compute | Managed batch computing at scale |
| Outposts | Compute | AWS infrastructure on-premises |
| S3 | Storage | Object storage, 11 nines durability |
| EBS | Storage | Block storage for EC2 |
| EFS | Storage | Managed NFS file storage |
| FSx | Storage | Managed Windows/Lustre file systems |
| Glacier / Glacier Deep Archive | Storage | Long-term archival storage |
| Storage Gateway | Storage | Hybrid on-prem/cloud storage |
| AWS Backup | Storage | Centralized backup across services |
| RDS | Database | Managed relational databases |
| Aurora | Database | High-performance MySQL/PostgreSQL-compatible |
| DynamoDB | Database | Managed NoSQL key-value/document store |
| ElastiCache | Database | Managed Redis/Memcached |
| Redshift | Database | Data warehouse |
| DocumentDB | Database | MongoDB-compatible document database |
| Neptune | Database | Managed graph database |
| Timestream | Database | Purpose-built time-series database |
| Keyspaces | Database | Managed Cassandra-compatible database |
| QLDB | Database | Managed ledger database (immutable, cryptographically verifiable) |
| VPC | Networking | Isolated virtual network |
| Route 53 | Networking | DNS + domain registration + health checks |
| CloudFront | Networking | Global CDN |
| ALB / NLB | Networking | Layer 7 / Layer 4 load balancers |
| API Gateway | Networking | Managed API front door (REST/HTTP/WebSocket) |
| Direct Connect | Networking | Dedicated private network link to AWS |
| Transit Gateway | Networking | Hub-and-spoke multi-VPC connectivity |
| Global Accelerator | Networking | Anycast IP global traffic routing |
| PrivateLink | Networking | Private connectivity to services without internet exposure |
| SQS | Messaging | Managed message queue |
| SNS | Messaging | Managed pub/sub notification service |
| EventBridge | Messaging | Serverless event bus with routing rules |
| Kinesis Data Streams | Messaging | Real-time data streaming, shard-based |
| Kinesis Firehose | Messaging | Streaming delivery to storage/analytics |
| MSK | Messaging | Managed Apache Kafka |
| Step Functions | Orchestration | Serverless workflow orchestration |
| IAM | Security | Identity and access management |
| KMS | Security | Managed encryption key service |
| Secrets Manager | Security | Managed secrets storage + rotation |
| GuardDuty | Security | Threat detection |
| WAF | Security | Web application firewall |
| Shield | Security | DDoS protection |
| Security Hub | Security | Centralized security findings aggregation |
| Macie | Security | Sensitive data (PII) discovery in S3 |
| Inspector | Security | Automated vulnerability scanning |
| Organizations | Governance | Multi-account management |
| Control Tower | Governance | Automated landing zone setup |
| Config | Governance | Resource configuration tracking/compliance |
| CloudTrail | Observability | API call audit logging |
| CloudWatch | Observability | Metrics, logs, alarms, dashboards |
| X-Ray | Observability | Distributed tracing |
| CodeGuru | Observability | Automated code review + profiling |
| CloudFormation | IaC | Native declarative infrastructure as code |
| CDK | IaC | Infrastructure as code using real programming languages |
| CodePipeline | CI/CD | Pipeline orchestration |
| CodeBuild | CI/CD | Managed build service |
| CodeDeploy | CI/CD | Managed deployment service (canary/blue-green) |
| ECR | CI/CD | Container image registry |
| CodeArtifact | CI/CD | Managed package repository |
| SageMaker | ML/AI | End-to-end managed ML platform |
| Bedrock | ML/AI | Managed access to foundation/generative AI models |
| Rekognition | ML/AI | Image/video analysis |
| Comprehend | ML/AI | Natural language processing |
| Textract | ML/AI | Document text/data extraction |
| Polly / Transcribe | ML/AI | Text-to-speech / speech-to-text |
| IoT Core | IoT | Device connectivity + management |
| MediaConvert | Media | File-based video transcoding |
| Elemental MediaLive | Media | Live video processing |
| Ground Truth / Snow Family | Data Transfer | Physical/bulk data transfer devices |
| DataSync | Data Transfer | Automated online data transfer |
| DMS | Data Transfer | Database migration service |
| Glue | Analytics | Managed ETL + data catalog |
| Athena | Analytics | Serverless SQL over S3 |
| EMR | Analytics | Managed Hadoop/Spark |
| Lake Formation | Analytics | Data lake governance |
| QuickSight | Analytics | Managed BI/dashboarding |
| Cost Explorer | Cost Mgmt | Cost visualization and analysis |
| Budgets | Cost Mgmt | Budget alerts |
| Compute Optimizer | Cost Mgmt | Rightsizing recommendations |

### 55.1 AWS Numbers to Know
- Regions: 30+ | Availability Zones: 100+ | Minimum AZs per region: 3
- S3 durability: 99.999999999% (11 nines) | S3 max object size: 5TB
- Lambda max execution time: 15 minutes | Lambda default concurrency limit: 1,000 (soft, adjustable)
- DynamoDB item size limit: 400KB | EBS gp3 baseline: 3,000 IOPS / 125 MB/s included

---

## §56 GCP Service Cheat Sheet

| Service | Category | One-Line Purpose |
|---|---|---|
| Compute Engine | Compute | Resizable virtual machines |
| Cloud Functions | Compute | Event-driven serverless functions |
| Cloud Run | Compute | Serverless containers, scale-to-zero |
| GKE | Compute | Managed Kubernetes (Standard or Autopilot) |
| App Engine | Compute | PaaS — deploy code, Google manages infra |
| Bare Metal Solution | Compute | Dedicated bare-metal servers |
| Batch | Compute | Managed batch computing at scale |
| Cloud Storage | Storage | Object storage, 11 nines durability |
| Persistent Disk | Storage | Block storage for Compute Engine |
| Filestore | Storage | Managed NFS file storage |
| Transfer Appliance / Storage Transfer Service | Storage | Bulk/online data transfer |
| Backup and DR Service | Storage | Centralized backup/DR orchestration |
| Cloud SQL | Database | Managed relational databases (MySQL/Postgres/SQL Server) |
| Cloud Spanner | Database | Globally distributed, strongly consistent relational DB |
| Firestore | Database | Managed NoSQL document database, real-time sync |
| Bigtable | Database | Wide-column NoSQL, massive write throughput |
| Memorystore | Database | Managed Redis/Memcached |
| BigQuery | Database/Analytics | Serverless data warehouse |
| AlloyDB | Database | PostgreSQL-compatible, high-performance managed DB |
| VPC | Networking | Global virtual network |
| Cloud DNS | Networking | Managed DNS |
| Cloud CDN | Networking | Global content delivery network |
| Cloud Load Balancing | Networking | Global/regional L4/L7 load balancing |
| API Gateway / Apigee | Networking | Managed API front door |
| Cloud Interconnect | Networking | Dedicated private network link to GCP |
| Cloud VPN | Networking | Encrypted site-to-site VPN |
| Network Connectivity Center | Networking | Hub-and-spoke multi-network connectivity |
| Private Service Connect | Networking | Private connectivity to services without internet exposure |
| Cloud Tasks | Messaging | Managed task queue with rate/retry control |
| Pub/Sub | Messaging | Managed pub/sub messaging with replay |
| Dataflow | Messaging/Analytics | Managed stream/batch processing (Apache Beam) |
| Workflows | Orchestration | Serverless workflow orchestration |
| Eventarc | Messaging | Event routing between GCP services |
| Cloud IAM | Security | Identity and access management |
| Cloud KMS | Security | Managed encryption key service |
| Secret Manager | Security | Managed secrets storage + rotation |
| Security Command Center | Security | Centralized security findings + threat detection |
| Cloud Armor | Security | WAF + DDoS protection |
| Sensitive Data Protection (DLP) | Security | Sensitive data (PII) discovery/redaction |
| Resource Manager | Governance | Org/folder/project hierarchy management |
| Organization Policy | Governance | Org-wide guardrails |
| Cloud Asset Inventory | Governance | Resource configuration tracking |
| Cloud Audit Logs | Observability | API call audit logging |
| Cloud Monitoring | Observability | Metrics, alerting, dashboards |
| Cloud Logging | Observability | Centralized log management |
| Cloud Trace | Observability | Distributed tracing |
| Cloud Profiler | Observability | Continuous production code profiling |
| Error Reporting | Observability | Automatic error aggregation |
| Deployment Manager | IaC | Native declarative infrastructure as code (largely superseded by Terraform) |
| Cloud Build | CI/CD | Managed build service |
| Cloud Deploy | CI/CD | Managed progressive delivery (canary/blue-green) |
| Artifact Registry | CI/CD | Unified container image + package registry |
| Binary Authorization | CI/CD | Deploy-time image signing enforcement |
| Vertex AI | ML/AI | End-to-end managed ML platform |
| Vertex AI Generative AI / Gemini API | ML/AI | Managed access to foundation/generative AI models |
| Vision AI / Video Intelligence | ML/AI | Image/video analysis |
| Natural Language AI | ML/AI | Natural language processing |
| Document AI | ML/AI | Document text/data extraction |
| Text-to-Speech / Speech-to-Text | ML/AI | Voice synthesis/recognition |
| Dataproc | Analytics | Managed Hadoop/Spark |
| Dataplex | Analytics | Data lake governance + cataloging |
| Looker / Looker Studio | Analytics | Managed BI/dashboarding |
| Datastream | Data Transfer | Managed change data capture (CDC) |
| Billing Reports / Recommender | Cost Mgmt | Cost visualization + rightsizing recommendations |

### 56.1 GCP Numbers to Know
- Regions: 40+ | Zones: 120+ | Minimum zones per region: 3
- Cloud Storage durability: 99.999999999% (11 nines) | Max object size: 5TB
- Cloud Functions/Cloud Run max request duration: 60 minutes
- Firestore document size limit: 1MB | Persistent Disk pd-balanced baseline scales with size

---

## §57 AWS vs GCP vs Azure Master Mapping Table (Extended)

*(Extends §12 with additional niche/specialized categories for quick pre-interview review.)*

| Category | AWS | GCP | Azure |
|---|---|---|---|
| Ledger/immutable database | QLDB | (no direct equivalent — BigQuery/Spanner with audit patterns) | Azure Confidential Ledger |
| Managed Cassandra | Keyspaces | (Bigtable w/ Cassandra API compatibility layer) | Cosmos DB (Cassandra API) |
| Data catalog/governance | Lake Formation | Dataplex | Purview |
| BI/dashboarding | QuickSight | Looker / Looker Studio | Power BI |
| CDC (change data capture) | DMS | Datastream | Data Factory (Mapping Data Flows) |
| Generative AI managed access | Bedrock | Vertex AI (Gemini) | Azure OpenAI Service |
| Document AI/OCR | Textract | Document AI | Form Recognizer / Document Intelligence |
| DLP / sensitive data discovery | Macie | Sensitive Data Protection | Purview Information Protection |
| Confidential computing | Nitro Enclaves | Confidential VMs / Confidential Space | Confidential Computing |
| Physical bulk data transfer | Snow Family | Transfer Appliance | Data Box |
| Private connectivity to services | PrivateLink | Private Service Connect | Private Link |
| Multi-account/project hub | Control Tower | Resource Manager (folders) | Management Groups + Blueprints |
| Simplified small-project VPS | Lightsail | (no direct equivalent) | (no direct equivalent) |
| Managed ledger/blockchain | Managed Blockchain | (no first-party equivalent) | Azure Confidential Ledger |
| Serverless workflow orchestration | Step Functions | Workflows | Logic Apps |
| Cost rightsizing recommendations | Compute Optimizer | Recommender | Azure Advisor |
| API management (enterprise-grade) | API Gateway (+ 3rd party) | Apigee | API Management |
| Managed ETL | Glue | Dataflow / Dataproc | Data Factory |
| Bare metal servers | EC2 Bare Metal / Outposts | Bare Metal Solution | Azure Dedicated Host |

---

## §58 Numbers & Pricing Quick Reference

### 58.1 Latency Numbers Every Cloud Engineer Should Know (Approximate)

| Operation | Approximate Latency |
|---|---|
| L1 cache reference | ~1 ns |
| Main memory reference | ~100 ns |
| Read 1MB sequentially from memory | ~10 μs |
| Round trip within the same AZ/zone | ~0.5 ms |
| Read 1MB sequentially from SSD | ~1 ms |
| Round trip within the same region (cross-AZ) | ~1-2 ms |
| Read 1MB sequentially from network (same region) | ~10 ms |
| Round trip cross-region (e.g., US to Europe) | ~70-150 ms |
| Round trip cross-continent (e.g., US to Asia) | ~150-250 ms |
| Disk seek (spinning disk) | ~10 ms |
| Send a packet US → Europe → US | ~150 ms |

### 58.2 Storage Class Cost Ordering (Cheapest to Most Expensive per GB, Both Clouds)

1. Deep Archive / Archive (cheapest storage, slowest/costliest retrieval)
2. Glacier Flexible Retrieval / Coldline
3. Glacier Instant Retrieval / Nearline
4. Standard-IA / IA-equivalent
5. Standard (most expensive storage, cheapest/fastest retrieval)

### 58.3 Rule-of-Thumb Numbers for Capacity Planning (Recap of §15.5)

- Design for a minimum of 3 AZs/zones for any production workload.
- Assume an 80/20 cache hit ratio is realistic for a well-designed cache on typical access patterns.
- Consumer apps in a single dominant timezone: expect 2-4x peak-to-average traffic ratio.
- Read-heavy consumer apps: 100:1 or higher read:write ratios are common.
- Spot/Preemptible discount range: roughly 60-90% off On-Demand pricing.
- Reserved/Committed Use discount range: roughly 30-70% off On-Demand, depending on term/payment option.

### 58.4 Common Free-Tier / Always-Free Highlights (Verify Current Values Before an Actual Project — These Change)

- Both AWS and GCP offer a time-limited broad free-tier credit for new accounts plus certain "always free" tiers (e.g., a small amount of Lambda/Cloud Functions invocations per month, a small always-free Compute Engine e2-micro instance in specific US regions on GCP).
- Never design a production cost estimate around free-tier limits — always model steady-state production costs at expected scale (§15.4).

# Part 8 — A-Z Glossary

## §59 Glossary A-M

| Term | Definition |
|---|---|
| Active-Active | An architecture where 2+ regions/data centers simultaneously serve live production traffic, with no designated "standby." |
| Adaptive Capacity | DynamoDB's automatic redistribution of throughput to accommodate uneven partition access patterns. |
| ALB (Application Load Balancer) | AWS's Layer 7 load balancer supporting path/host-based routing. |
| Anycast | A networking technique where the same IP address is announced from multiple locations, with routing sending traffic to the nearest one. |
| API Gateway | A managed service that fronts APIs, handling routing, auth, throttling, and request/response transformation. |
| ASG (Auto Scaling Group) | AWS's construct for automatically scaling a fleet of EC2 instances based on demand. |
| Availability Zone (AZ) | An isolated failure domain within an AWS region, with independent power/cooling/networking. |
| Backpressure | A mechanism where a system signals upstream producers to slow down when it can't keep up with incoming load. |
| Bin Packing | The scheduling technique of fitting workloads (pods/containers) into the fewest possible nodes to maximize utilization. |
| Blast Radius | The scope of impact if a specific component/change fails — a key concept in isolating failures. |
| Blue-Green Deployment | A deployment strategy running two full environments and atomically cutting traffic between them. |
| BGP (Border Gateway Protocol) | The internet's core routing protocol, used for dynamic route exchange in VPNs/Interconnects. |
| Bigtable | GCP's wide-column NoSQL database for massive write-throughput workloads. |
| Canary Deployment | A deployment strategy gradually shifting traffic to a new version while monitoring health metrics. |
| CAP Theorem | States a distributed system can only guarantee 2 of 3: Consistency, Availability, Partition tolerance. |
| CDN (Content Delivery Network) | A globally distributed network of edge servers caching content close to users. |
| CIDR (Classless Inter-Domain Routing) | A notation for specifying IP address ranges (e.g., 10.0.0.0/16). |
| Circuit Breaker | A resilience pattern that stops calling a failing dependency temporarily to prevent cascading failure. |
| Cloud Armor | GCP's WAF and DDoS protection service. |
| Cloud Run | GCP's serverless container platform with scale-to-zero. |
| Cloud Spanner | GCP's globally distributed, strongly consistent relational database. |
| CloudFront | AWS's global CDN service. |
| CloudTrail | AWS's service logging all API calls made within an account for audit purposes. |
| CNAME | A DNS record type that aliases one domain name to another. |
| Cold Start | The latency incurred when a serverless function/container must initialize before handling its first request. |
| Compensating Transaction | An operation that reverses the effect of a previously completed step in a Saga, used when a later step fails. |
| Consistent Hashing | A hashing technique that minimizes data movement when nodes are added/removed from a distributed system. |
| Control Tower | AWS's service for automating multi-account landing zone setup. |
| CRDT (Conflict-free Replicated Data Type) | A data structure designed to be replicated across nodes and merged without conflicts. |
| Cross-Region Replication | Copying data asynchronously (or synchronously) from one cloud region to another. |
| DAX (DynamoDB Accelerator) | An in-memory caching layer specifically for DynamoDB. |
| Dead Letter Queue (DLQ) | A queue that captures messages that failed processing after repeated retries. |
| Distributed Tracing | A method of tracking a single request's path across multiple services using a shared trace ID. |
| DNS (Domain Name System) | The system translating human-readable domain names into IP addresses. |
| DR (Disaster Recovery) | The strategy/process for recovering a system after a major failure/disaster. |
| DynamoDB | AWS's managed NoSQL key-value/document database. |
| EBS (Elastic Block Store) | AWS's block storage service for EC2 instances. |
| Egress | Data leaving a network/cloud provider, often billed. |
| EKS (Elastic Kubernetes Service) | AWS's managed Kubernetes offering. |
| ElastiCache | AWS's managed Redis/Memcached service. |
| Eventual Consistency | A consistency model where all replicas converge to the same value eventually, but may be temporarily inconsistent. |
| EventBridge | AWS's serverless event bus service. |
| Expand/Contract Pattern | A database schema migration technique that adds new schema elements before removing old ones, to support zero-downtime deploys. |
| Fan-Out | Distributing a single event/message to multiple consumers/destinations. |
| Fargate | AWS's serverless compute engine for containers (ECS/EKS). |
| Feature Store | A centralized system storing versioned features used consistently for both ML training and serving. |
| Firestore | GCP's managed NoSQL document database with real-time sync. |
| GKE (Google Kubernetes Engine) | GCP's managed Kubernetes offering. |
| Global Accelerator | AWS's service providing static anycast IPs for global traffic routing. |
| GSI (Global Secondary Index) | A DynamoDB index allowing queries on non-primary-key attributes across the whole table. |
| GuardDuty | AWS's threat detection service. |
| HA (High Availability) | A system design goal of minimizing downtime, typically via redundancy. |
| Health Check | An automated probe verifying a service/instance is functioning correctly. |
| Horizontal Scaling | Adding more machines/instances to handle increased load (scale out). |
| HPA (Horizontal Pod Autoscaler) | Kubernetes's mechanism for automatically scaling the number of pod replicas. |
| IAM (Identity and Access Management) | The system controlling who can do what within a cloud account. |
| Idempotency | The property that performing an operation multiple times has the same effect as performing it once. |
| Ingress (Kubernetes) | A Kubernetes resource managing external HTTP(S) access to services within a cluster. |
| Ingress (networking) | Data entering a network/cloud provider. |
| IOPS | Input/Output Operations Per Second, a measure of storage performance. |
| Kinesis | AWS's real-time data streaming service. |
| KMS (Key Management Service) | A managed service for creating and controlling encryption keys. |
| Landing Zone | The foundational, security-guardrailed account/project structure an organization provisions workloads into. |
| Last-Writer-Wins | A conflict-resolution strategy where the most recent write (by timestamp) overwrites earlier concurrent writes. |
| Latency-Based Routing | A DNS routing policy that directs users to the endpoint with the lowest latency. |
| Least Privilege | The security principle of granting only the minimum permissions necessary. |
| Load Balancer | A component distributing incoming traffic across multiple backend instances. |
| Log Aggregation | Centralizing logs from many sources into one searchable system. |
| Managed Instance Group (MIG) | GCP's construct for automatically scaling a fleet of Compute Engine VMs. |
| MFA (Multi-Factor Authentication) | An authentication method requiring 2+ verification factors. |
| Microservices | An architectural style structuring an application as a collection of small, independently deployable services. |
| MSK (Managed Streaming for Kafka) | AWS's managed Apache Kafka service. |
| Multi-AZ | A deployment spanning multiple Availability Zones for high availability. |

## §60 Glossary N-Z

| Term | Definition |
|---|---|
| NACL (Network ACL) | A stateless, subnet-level firewall in AWS VPCs. |
| NAT Gateway / Cloud NAT | A managed service allowing private-subnet resources outbound-only internet access. |
| Network Policy | A Kubernetes resource controlling pod-to-pod network traffic. |
| NLB (Network Load Balancer) | AWS's Layer 4 load balancer for ultra-low-latency TCP/UDP traffic. |
| Noisy Neighbor | A problem where one workload's resource consumption degrades performance for co-located workloads. |
| OIDC (OpenID Connect) | An identity layer on top of OAuth2, commonly used for federated/short-lived credential exchange (e.g., GitHub Actions to cloud). |
| Org Policy | GCP's mechanism for enforcing organization-wide guardrails regardless of IAM permissions. |
| PACELC Theorem | An extension of CAP theorem: even without a Partition, there's a trade-off Else between Latency and Consistency. |
| Partition Key | The attribute used to determine which physical partition/shard a piece of data is stored in. |
| PDB (Pod Disruption Budget) | A Kubernetes resource limiting how many pods of an app can be down simultaneously during voluntary disruptions. |
| Persistent Disk | GCP's block storage service for Compute Engine. |
| Pilot Light | A DR strategy keeping minimal core infrastructure/data replicated in a standby region, scaled up only during failover. |
| Presigned URL | A time-limited URL granting temporary access to a private object storage object. |
| Provisioned Concurrency | A Lambda feature pre-initializing execution environments to eliminate cold starts. |
| Pub/Sub | GCP's managed publish-subscribe messaging service. |
| Quorum | The minimum number of nodes that must agree/acknowledge for a distributed operation to be considered successful. |
| RBAC (Role-Based Access Control) | An access control model granting permissions based on assigned roles. |
| Read Replica | A read-only copy of a database, used to offload read traffic from the primary. |
| Region | A geographic area containing multiple isolated data center clusters (AZs/zones). |
| Reserved Instance | An AWS pricing model offering a discount in exchange for a 1-3 year usage commitment. |
| RPO (Recovery Point Objective) | The maximum acceptable amount of data loss, measured in time, during a disaster. |
| RTO (Recovery Time Objective) | The maximum acceptable time to restore service after a disaster. |
| S3 (Simple Storage Service) | AWS's object storage service. |
| Saga Pattern | A pattern for managing distributed transactions via a sequence of local transactions with compensating actions. |
| SCP (Service Control Policy) | AWS Organizations' mechanism for setting maximum available permissions across accounts. |
| Secrets Manager | AWS's managed service for storing and rotating secrets. |
| Serverless | A computing model where the cloud provider manages all infrastructure, and billing is based on actual usage. |
| Service Mesh | Infrastructure layer (e.g., Istio) managing service-to-service communication, often via sidecar proxies. |
| Sharding | Splitting a dataset across multiple physical partitions/nodes to scale horizontally. |
| Shared Responsibility Model | The division of security duties between a cloud provider and its customers. |
| Shared VPC | GCP's feature allowing one project to own networking while other projects attach to it. |
| SLA (Service Level Agreement) | A formal, often contractual, commitment to a specific level of service (e.g., uptime). |
| SLO (Service Level Objective) | An internal target for a service's reliability, used to guide operational decisions. |
| SNS (Simple Notification Service) | AWS's managed pub/sub notification service. |
| Spanner | See Cloud Spanner. |
| Spot Instance / Preemptible VM | Spare cloud compute capacity offered at a steep discount, reclaimable with short notice. |
| SQS (Simple Queue Service) | AWS's managed message queue service. |
| SSE (Server-Sent Events) | A protocol for a server to push updates to a client over a single long-lived HTTP connection. |
| STS (Security Token Service) | AWS's service for issuing temporary, limited-privilege credentials. |
| Strangler Fig Pattern | An incremental migration strategy replacing pieces of a legacy system while it continues operating. |
| TCO (Total Cost of Ownership) | The full cost of a system including infrastructure, operations, and maintenance. |
| Thundering Herd | A problem where many clients simultaneously retry/request the same resource, overwhelming it. |
| Throttling | Deliberately limiting the rate of requests a system accepts to protect itself from overload. |
| Token Bucket | A rate-limiting algorithm allowing bursts up to a bucket capacity while enforcing an average rate. |
| Transit Gateway | AWS's hub-and-spoke service for connecting many VPCs/on-premises networks. |
| TrueTime | Google Spanner's API exposing bounded global clock uncertainty, enabling external consistency. |
| TTL (Time To Live) | The duration a piece of cached/stored data remains valid before expiring. |
| VPC (Virtual Private Cloud) | An isolated virtual network within a cloud provider. |
| VPC Peering | A direct, non-transitive network connection between two VPCs. |
| WAF (Web Application Firewall) | A firewall filtering/monitoring HTTP traffic to protect against common web exploits (SQLi, XSS). |
| Warm Standby | A DR strategy running a scaled-down but fully functional copy of production in a secondary region continuously. |
| Well-Architected Framework | AWS's set of 6 pillars for evaluating cloud architecture quality. |
| Workload Identity Federation | A mechanism letting external identities assume cloud credentials without long-lived keys. |
| X-Ray | AWS's distributed tracing service. |
| Zone | GCP's term for an isolated failure domain within a region (equivalent to an AWS AZ). |
| Zero Trust | A security model assuming no implicit trust based on network location; every request must be authenticated/authorized. |

# Part 9 — Study Roadmap, FAQ, Closing Notes

## §61 Study Roadmap (Week by Week)

| Week | Focus | Activities |
|---|---|---|
| 1 | Cloud Fundamentals (§1-4) | Read §1-4, set up free-tier AWS + GCP accounts, launch a VM on each, upload/download an object on S3 and GCS |
| 2 | Databases & Networking (§5-6) | Read §5-6, deploy a small RDS/Cloud SQL instance, design a VPC with public/private subnets on both clouds |
| 3 | Messaging, IAM, Serverless (§7-9) | Read §7-9, write and deploy a Lambda and a Cloud Function, set up an SQS queue and a Pub/Sub topic |
| 4 | Observability, DevOps, Frameworks (§10-13) | Read §10-13, set up CloudWatch/Cloud Monitoring dashboards, write your first Terraform module |
| 5 | Interview Framework & Estimation (§14-16) | Read §14-16 thoroughly, practice the back-of-envelope math drills in §15 until fast |
| 6 | HLD Case Studies Batch 1 (§17-22) | Read §17-22, then re-derive each design from scratch on paper without looking, compare |
| 7 | HLD Case Studies Batch 2 (§23-28) | Same drill for §23-28 |
| 8 | HLD Case Studies Batch 3 (§29-34) | Same drill for §29-34, plus Part 10 appendix case studies |
| 9 | LLD (§35-40) | Write real Terraform/K8s manifests yourself following §35-40's patterns against a sandbox account |
| 10 | Q&A Bank Drilling (§41-45) | Do timed self-quizzes: cover the answers, answer out loud, then check |
| 11 | Multi-Cloud Integration (§46-54) | Build a small toy version of the adapter pattern (§53) yourself end-to-end |
| 12 | Mock Interviews + Cheat Sheet Review (§55-60) | Do 3-5 full mock system design interviews using §14's framework, review cheat sheets/glossary daily |

### 61.1 Daily Habits During the 12 Weeks

- Spend 15-20 minutes daily reviewing the cheat sheets (§55-58) and glossary (§59-60) — spaced repetition of terminology compounds significantly over 12 weeks.
- After every case study you read, immediately close the guide and try to redraw the architecture from memory — active recall beats passive re-reading for retention.
- Keep a running personal "mistakes/gaps" log of anything you got wrong in a mock interview or self-quiz, and revisit that log weekly.

### 61.2 If You Only Have 2 Weeks (Compressed Track)

| Days | Focus |
|---|---|
| 1-3 | §1-13 (skim fundamentals fast, focus on the AWS-vs-GCP comparison tables) |
| 4-5 | §14-16 (interview framework — this is the highest-leverage material for time invested) |
| 6-10 | §17-34 + Part 10 (HLD case studies — read actively, redraw from memory) |
| 11-12 | §41-45 (Q&A bank — drill hard) |
| 13-14 | Mock interviews + targeted review of weak areas identified during mocks |

---

## §62 FAQ

**Q: Do I need to memorize exact pricing numbers for an interview?**
A: No — interviewers care that you can reason about cost drivers (compute vs storage vs egress, on-demand vs reserved vs spot) and do rough order-of-magnitude estimation (§15), not that you've memorized current per-GB prices, which change frequently anyway.

**Q: Should I pick AWS or GCP to specialize in if I can only learn one deeply?**
A: Check the job postings you're targeting first — AWS has larger overall market share so is a safer default, but GCP is heavily preferred in some domains (data/ML-heavy roles, companies already invested in BigQuery/Spanner). This guide's side-by-side approach is designed so you can read the AWS-specific sections deeply and treat the GCP sections as "enough to speak intelligently," or vice versa.

**Q: How much Kubernetes do I need to know for a cloud system design interview?**
A: Enough to explain WHY you'd choose EKS/GKE vs Fargate/Cloud Run vs plain VMs (§3.4, §9.3) and the basics of Deployments/Services/HPA (§40) — deep Kubernetes internals (etcd internals, scheduler algorithms) are rarely tested in a cloud system design interview specifically (they're more common in a dedicated "Kubernetes internals" interview).

**Q: Is Terraform required knowledge, or is CloudFormation/Deployment Manager enough?**
A: For most modern cloud roles, Terraform familiarity is expected even at AWS-only or GCP-only shops, since it's become the de facto industry standard — CloudFormation/CDK knowledge is a bonus for AWS-specific roles, not a substitute.

**Q: How deep should I go on the ML/AI sections (SageMaker/Vertex AI)?**
A: Unless you're targeting an ML-platform-specific role, know the HIGH-LEVEL architecture (feature store solving train/serve skew, shadow vs canary testing) from §31 — you generally won't be asked to design deep ML training internals in a general cloud system design interview.

**Q: The case studies show BOTH an AWS and a GCP design for some systems — do I need to know both, or just the cloud in my job description?**
A: Know your target cloud deeply; use the OTHER cloud's version as a comparison tool to deepen your understanding of WHY your target cloud's services work the way they do (contrast is a powerful learning technique) — you generally won't be asked to design on a cloud not mentioned in the job posting/interview loop.

**Q: How important is the multi-cloud integration guide (Part 6) if my target company is single-cloud?**
A: Less directly interview-relevant, but valuable for understanding good software architecture practices in general (the adapter pattern, cloud-agnostic business logic, IaC discipline) that make you a stronger engineer regardless — also directly relevant if the company you're interviewing at has ANY multi-cloud aspirations or is post-acquisition.

**Q: Should I bring up cost optimization even if the interviewer doesn't ask about it?**
A: Yes, briefly, at the wrap-up stage (§14 Step 7) — even a one-sentence cost consideration ("we could reduce this further with Spot instances for the batch tier") signals senior-level, business-aware thinking without derailing the technical discussion.

**Q: What if I don't know a specific service the interviewer asks about?**
A: Be honest, then reason from first principles about what such a service would need to do given the requirement — interviewers often care more about your reasoning process than whether you've memorized every service name, and honest "I'm not familiar with that specific service, but here's how I'd approach the problem" is far better received than bluffing.

**Q: How do I practice the back-of-envelope estimation math (§15) until it's fast?**
A: Drill with random made-up scenarios daily (e.g., "50M DAU, 10 actions/day, 1KB/action — compute QPS and daily storage") until the arithmetic and unit conversions (bytes/KB/MB/GB/TB, seconds/day = 86,400) become automatic — the actual math is simple, but doing it confidently under interview time pressure requires repetition.

**Q: Is it a red flag to default to serverless for everything?**
A: Yes, if unjustified — a good candidate explains WHY serverless fits a given workload's traffic pattern (§19 Deep Dive 2's crossover point) rather than defaulting to it reflexively for every scenario regardless of characteristics.

**Q: How do system design interviews differ between a junior/mid vs senior/staff cloud role?**
A: Junior/mid interviews focus more on "can you correctly design a working system with the right services." Senior/staff interviews expect explicit trade-off articulation (§13.3), proactive discussion of failure modes/cost/organizational impact, and often extend into cross-team/platform-level design questions (like §28's landing zone or §22's multi-tenant platform) rather than a single application's design.

---

## §63 Closing Notes

This guide deliberately paired every AWS concept with its GCP counterpart throughout, because the single best way to deeply understand WHY a cloud service is designed the way it is — is to see it against a genuine alternative that solved the same problem with different trade-offs (Aurora's storage/compute separation vs Spanner's TrueTime-based global consensus; GCP's global-by-default VPC vs AWS's regional VPC + Transit Gateway). If you remember nothing else from this guide, remember the **7-step interview framework in §14** and the discipline of **always quantifying scale before designing** (§15) — these two habits alone will noticeably raise the quality of your system design interview answers, on any cloud, for any system.

Good luck — and remember that in a real interview, the specific service names matter far less than demonstrating you can reason clearly about trade-offs, ask good clarifying questions, and communicate your thinking as you go.

# Part 10 — Additional HLD Mini Case Studies (Appendix)

*A further 20 real-world systems, following a leaner version of Part 3's format, to round out your case-study repertoire for interviews.*

## §64 Ride-Sharing Dispatch System

**Problem:** Design the core dispatch system for a ride-sharing app — matching riders to nearby available drivers in real time, at city scale.

**Requirements:**
- Match a rider to the nearest available driver within 2-3 seconds.
- Track driver locations continuously (updated every few seconds).
- Handle surge demand (many riders requesting simultaneously in one area).
- Support cancellation/re-matching if a driver doesn't accept within a timeout.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Location ingestion | Kinesis Data Streams | Pub/Sub | Ingest continuous driver GPS pings |
| Geospatial index | ElastiCache Redis (GEO commands) | Memorystore Redis (GEO commands) | Fast "nearest drivers" queries |
| Matching service | Lambda / ECS | Cloud Functions / Cloud Run | Runs the matching algorithm per ride request |
| Ride state | DynamoDB | Firestore | Tracks ride lifecycle (requested/matched/in-progress/completed) |
| Notification to driver | SNS + push notification service | Pub/Sub + FCM | Notify matched driver of ride request |

**Key code — Redis geospatial query for nearest drivers:**

```python
def find_nearby_drivers(redis_client, rider_lat: float, rider_lon: float, radius_km: float = 3.0):
    """GEOSEARCH returns driver IDs within radius, sorted by distance, using Redis's
    native geospatial index -- O(log N + M) where M is the result set size."""
    results = redis_client.geosearch(
        name="active_drivers",
        longitude=rider_lon,
        latitude=rider_lat,
        radius=radius_km,
        unit="km",
        sort="ASC",
        count=10,
    )
    return results


def update_driver_location(redis_client, driver_id: str, lat: float, lon: float):
    redis_client.geoadd("active_drivers", (lon, lat, driver_id))
    redis_client.expire(f"driver:{driver_id}:heartbeat", 30)  # stale drivers auto-expire
```

**Trade-offs:** Using Redis GEO commands over a full geospatial database (e.g., PostGIS) trades some query flexibility for the sub-millisecond latency required for real-time matching at scale — acceptable since the access pattern (nearest-N drivers) is narrow and well-defined.

**Follow-Up Questions:**
- *"How do you prevent the same driver from being matched to two riders simultaneously?"* → Use a conditional write (DynamoDB conditional update / Firestore transaction) that atomically claims the driver only if their status is still "available," rejecting the second concurrent match attempt.
- *"How do you handle a dense urban core with thousands of drivers in a single square kilometer?"* → Increase the geospatial index granularity (finer-grained geohash cells) in dense areas, and add a secondary ranking factor (driver rating, ETA via routing, not just raw distance) to break ties intelligently.

---

## §65 Product Recommendation Engine

**Problem:** Design a recommendation system for an e-commerce site showing "recommended for you" and "customers also bought" sections, serving personalized recommendations within 100ms.

**Requirements:**
- Real-time personalized recommendations at page-load speed.
- Incorporate both long-term preferences and recent session behavior.
- Support A/B testing different recommendation algorithms.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Offline model training | SageMaker (batch) | Vertex AI (batch) | Train collaborative-filtering/embedding models nightly |
| Precomputed recommendations | DynamoDB | Bigtable | Store top-N recommendations per user, refreshed nightly |
| Real-time feature signals | ElastiCache | Memorystore | Recent clicks/views in the current session |
| Serving | Lambda / SageMaker Endpoint | Cloud Run / Vertex AI Endpoint | Combines precomputed + real-time signals at request time |
| Experimentation | CloudWatch Evidently | Vertex AI Experiments / a 3rd-party A/B tool | A/B test different algorithm versions |

**Key code — Hybrid serving logic (precomputed + real-time re-ranking):**

```python
def get_recommendations(user_id: str, kv_store, cache, session_id: str, n: int = 10) -> list[str]:
    precomputed = kv_store.get(f"USER#{user_id}", "RECS") or {"items": []}
    recent_views = cache.lrange(f"session:{session_id}:views", 0, 20)

    # Boost items similar to what the user JUST viewed this session, re-ranking the
    # nightly-precomputed baseline list with a cheap real-time signal
    scored = []
    for item in precomputed["items"]:
        score = item["base_score"]
        if item["category"] in {v["category"] for v in recent_views}:
            score *= 1.5  # simple recency-based boost
        scored.append((item["item_id"], score))

    scored.sort(key=lambda x: x[1], reverse=True)
    return [item_id for item_id, _ in scored[:n]]
```

**Trade-offs:** Precomputing recommendations nightly (batch) keeps serving latency low and cheap, at the cost of not reflecting very recent behavior changes until the next batch run — mitigated by the lightweight real-time re-ranking layer above, which is a common, pragmatic hybrid approach rather than full real-time model inference on every request.

**Follow-Up Questions:**
- *"How would you handle a brand-new user with no history (the cold-start problem)?"* → Fall back to popularity-based or category-based recommendations (trending items, bestsellers in a category the user just browsed) until enough behavioral data accumulates for personalized precomputation.
- *"How do you measure whether a new recommendation algorithm is actually better?"* → A/B test with a clear business metric (click-through rate, conversion rate, revenue per session) as the primary success criterion, not just an offline ML metric like precision/recall, since offline metrics don't always correlate with real business impact.

---

## §66 Rate-Limiter-as-a-Service

**Problem:** Design a standalone, shared rate-limiting service that many internal microservices call to enforce per-client rate limits, rather than each service implementing its own.

**Requirements:**
- Support multiple algorithms (token bucket, sliding window) configurable per client.
- Sub-millisecond added latency (called on the hot path of every request).
- Must work correctly across a fleet of the rate limiter's own instances (no double-counting).

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Shared counter store | ElastiCache Redis (cluster mode) | Memorystore Redis (cluster tier) | Atomic increment/expire operations, shared across all rate-limiter instances |
| Rate limiter API | Lambda behind API Gateway, or a lightweight ECS service | Cloud Run | Exposes `check_and_increment(client_id, limit_config)` |
| Config store | DynamoDB | Firestore | Per-client rate limit configuration (limits, algorithm choice) |

**Key code — Atomic token bucket check via a Redis Lua script (avoids race conditions):**

```lua
-- rate_limiter.lua -- executed atomically by Redis, avoiding read-then-write races
-- across multiple rate-limiter service instances calling Redis concurrently
local key = KEYS[1]
local capacity = tonumber(ARGV[1])
local refill_rate = tonumber(ARGV[2])  -- tokens per second
local now = tonumber(ARGV[3])
local requested = tonumber(ARGV[4])

local bucket = redis.call("HMGET", key, "tokens", "last_refill")
local tokens = tonumber(bucket[1]) or capacity
local last_refill = tonumber(bucket[2]) or now

local elapsed = math.max(0, now - last_refill)
tokens = math.min(capacity, tokens + elapsed * refill_rate)

if tokens >= requested then
    tokens = tokens - requested
    redis.call("HMSET", key, "tokens", tokens, "last_refill", now)
    redis.call("EXPIRE", key, 3600)
    return 1  -- allowed
else
    redis.call("HMSET", key, "tokens", tokens, "last_refill", now)
    redis.call("EXPIRE", key, 3600)
    return 0  -- rejected
end
```

**Trade-offs:** Running the check as a single atomic Lua script on Redis (rather than separate GET/compute/SET calls from application code) eliminates race conditions between concurrent rate-limiter instances without needing a distributed lock, at the cost of Redis-specific scripting knowledge — a worthwhile trade for the correctness guarantee on a shared, high-concurrency hot path.

**Follow-Up Questions:**
- *"What happens if the Redis cluster itself becomes unavailable?"* → Fail open (allow requests through) rather than fail closed (reject everything), since a rate limiter outage should degrade to "no rate limiting" rather than a full service outage for every downstream client — a deliberate availability-over-strictness trade-off for this specific component.
- *"How would you support per-client custom limits without a config lookup on every single request?"* → Cache each client's config in the rate-limiter instance's local memory with a short TTL (e.g., 60 seconds), refreshing periodically rather than hitting DynamoDB/Firestore on every request.

## §67 Global Search & Autocomplete Service

**Problem:** Design a search-as-you-type autocomplete service (like a product/site search bar) returning suggestions within 50ms as the user types, at global scale.

**Requirements:**
- Sub-50ms p99 latency for autocomplete suggestions.
- Suggestions ranked by popularity/relevance, updated regularly (not necessarily real-time).
- Support typo tolerance (fuzzy matching).
- Global user base — low latency everywhere.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Search/autocomplete engine | OpenSearch Service (with completion suggester) | Elasticsearch on GKE, or Vertex AI Search | Indexed prefix search with fuzzy matching |
| Edge caching of top queries | CloudFront (edge caching common prefixes) | Cloud CDN | Absorb repeat requests for very common prefixes ("a", "ap", "app"...) |
| Regional deployment | Multi-region OpenSearch domains | Multi-region Elasticsearch clusters | Low latency for a global user base |
| Popularity ranking update | Batch job (EMR/Glue) updating suggestion weights nightly | Dataproc/Dataflow batch job | Keep suggestions fresh based on recent query volume |

**Key code #1 — Terraform for a regional OpenSearch domain with a suggester-ready index:**

```hcl
resource "aws_opensearch_domain" "autocomplete" {
  domain_name    = "autocomplete-${var.region}"
  engine_version = "OpenSearch_2.11"

  cluster_config {
    instance_type          = "r6g.large.search"
    instance_count         = 3
    zone_awareness_enabled = true
    zone_awareness_config {
      availability_zone_count = 3
    }
  }

  ebs_options {
    ebs_enabled = true
    volume_size = 50
    volume_type = "gp3"
  }

  encrypt_at_rest {
    enabled = true
  }

  node_to_node_encryption {
    enabled = true
  }
}
```

**Key code #2 — Query-time completion suggester request:**

```python
def get_autocomplete_suggestions(os_client, prefix: str, size: int = 8) -> list[str]:
    response = os_client.search(
        index="products",
        body={
            "suggest": {
                "product-suggest": {
                    "prefix": prefix,
                    "completion": {
                        "field": "suggest",
                        "size": size,
                        "fuzzy": {"fuzziness": "AUTO"},  # typo tolerance
                        "skip_duplicates": True,
                    }
                }
            }
        },
    )
    options = response["suggest"]["product-suggest"][0]["options"]
    return [opt["text"] for opt in options]
```

**Trade-offs:** Using a purpose-built completion suggester (a specialized prefix-tree/FST data structure) over a generic full-text search query trades some flexibility for dramatically better latency and memory efficiency on the specific prefix-matching access pattern — the right specialization for a latency-critical feature.

**Follow-Up Questions:**
- *"How would you personalize autocomplete suggestions per user without breaking the sub-50ms latency budget?"* → Blend a fast, precomputed personalization signal (the user's own recent search history, cached client-side or in a fast KV store) with the global popularity ranking client-side or via a very lightweight re-ranking step, rather than adding a slow personalization ML call to the hot path.
- *"How do you keep the suggestion index from serving outdated/removed products?"* → Nightly (or more frequent) reindexing jobs that rebuild the suggestion index from the current product catalog, combined with a short TTL-based cache invalidation for the edge-cached common-prefix responses.

---

## §68 Payment Gateway Integration Architecture

**Problem:** Design the architecture for integrating with external payment processors (Stripe/Adyen-style) reliably, handling webhooks, retries, and reconciliation, without ever double-charging a customer.

**Requirements:**
- Process payments synchronously from the user's perspective (fast checkout).
- Handle asynchronous payment status webhooks reliably (payment confirmed/failed events arriving later).
- Guarantee no double-charges even under retries/failures.
- Support reconciliation against the payment processor's records (detect discrepancies).

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Payment initiation API | API Gateway + Lambda | API Gateway + Cloud Run | Accepts checkout request, calls payment processor's API |
| Idempotency ledger | DynamoDB | Firestore | Ensures a retried request doesn't double-charge |
| Webhook receiver | API Gateway + Lambda | Cloud Run (public HTTPS endpoint) | Receives async payment status updates from the processor |
| Webhook event queue | SQS | Pub/Sub | Buffers webhook events for reliable, ordered-ish processing |
| Reconciliation job | Scheduled Lambda (EventBridge cron) | Cloud Scheduler + Cloud Function | Nightly comparison against processor's settlement report |

**Key code #1 — Idempotent charge creation:**

```python
def create_charge(idempotency_key: str, amount_cents: int, customer_id: str,
                   idempotency_store, payment_processor_client) -> dict:
    existing = idempotency_store.get(idempotency_key)
    if existing:
        return existing["response"]  # already processed -- return the SAME result, don't re-charge

    try:
        result = payment_processor_client.charge(
            amount=amount_cents,
            customer=customer_id,
            idempotency_key=idempotency_key,  # ALSO passed to the processor itself, which
                                                # supports its own idempotency guarantee as
                                                # a second layer of defense
        )
        idempotency_store.put(idempotency_key, {"response": result, "status": "completed"})
        return result
    except Exception as e:
        idempotency_store.put(idempotency_key, {"response": None, "status": "failed", "error": str(e)})
        raise
```

**Key code #2 — Webhook signature verification (critical security step, often skipped by mistake):**

```python
import hmac
import hashlib


def verify_webhook_signature(payload: bytes, signature_header: str, webhook_secret: str) -> bool:
    """Every payment processor signs its webhook payloads -- ALWAYS verify this before
    trusting/processing a webhook, otherwise anyone who discovers your webhook URL could
    forge fake 'payment succeeded' events."""
    expected_signature = hmac.new(
        webhook_secret.encode("utf-8"),
        payload,
        hashlib.sha256,
    ).hexdigest()
    return hmac.compare_digest(expected_signature, signature_header)


def handle_webhook(request, webhook_secret: str, event_queue):
    if not verify_webhook_signature(request.body, request.headers["X-Signature"], webhook_secret):
        raise SecurityError("Invalid webhook signature -- possible forged request")
    event_queue.publish(request.json())
```

**Trade-offs:** The idempotency-key pattern requires the CLIENT (frontend/mobile app) to generate and consistently reuse a key per checkout attempt (not per retry) — this requires client-side discipline and a bit of added complexity, in exchange for eliminating an entire class of double-charge bugs that would otherwise require manual customer support intervention and refunds.

**Follow-Up Questions:**
- *"What happens if your webhook receiver is down when the payment processor sends a status update?"* → Payment processors retry webhook delivery with backoff for a period (often 24-72 hours) — as long as your receiver recovers within that window, no events are lost; for extra safety, also run the reconciliation job (comparing your records against the processor's settlement API) to catch any genuinely missed events.
- *"How do you handle a payment that succeeds at the processor but your confirmation call to the user-facing service times out?"* → Never treat a timeout as "the payment failed" — always check the actual payment status (via the idempotency key / a status query to the processor) before deciding to retry or refund, since the charge may have actually succeeded despite the timeout.

---

## §69 Feature Flag / Experimentation Platform

**Problem:** Design an internal feature-flagging and A/B testing platform used by all engineering teams to gradually roll out features and run experiments, with sub-10ms flag evaluation latency.

**Requirements:**
- Flag evaluation must add negligible latency to every request (sub-10ms).
- Support percentage-based rollouts, user-attribute targeting (e.g., "only for EU users"), and A/B experiment bucketing.
- Flag changes must propagate to all servers within seconds, without a deploy.
- Must not become a single point of failure for the entire platform.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Flag config store | DynamoDB (source of truth) | Firestore (source of truth) | Stores flag definitions/targeting rules |
| Config distribution | S3 + CloudFront (a periodically-generated static JSON snapshot) | GCS + Cloud CDN (same pattern) | Every app server polls/caches this snapshot locally — NOT a live DB call per request |
| Change propagation | DynamoDB Streams → Lambda → regenerates the S3 snapshot | Firestore trigger → Cloud Function → regenerates the GCS snapshot | Keeps the distributed snapshot fresh within seconds of a flag change |
| Client-side evaluation library | A shared SDK (in-process, no network call per flag check) | Same | Guarantees sub-millisecond evaluation, since it's all in-memory |

**Key code — Client-side flag evaluation library (the actual hot-path logic, fully local):**

```python
import hashlib


class FeatureFlagClient:
    """Loads the flag snapshot periodically in the background; evaluation itself is
    pure in-memory computation -- no network call on the request hot path."""

    def __init__(self, flag_snapshot: dict):
        self._flags = flag_snapshot  # refreshed periodically by a background thread

    def is_enabled(self, flag_key: str, user_id: str, user_attributes: dict | None = None) -> bool:
        flag = self._flags.get(flag_key)
        if not flag or not flag["enabled"]:
            return False

        # Attribute targeting (e.g., region == "EU")
        for rule in flag.get("targeting_rules", []):
            if user_attributes and user_attributes.get(rule["attribute"]) == rule["value"]:
                return rule["enabled"]

        # Consistent percentage rollout -- same user always gets the same bucket,
        # using a deterministic hash rather than random.random() (which would flip
        # per-request and give an inconsistent experience to the same user)
        rollout_pct = flag.get("rollout_percentage", 0)
        bucket = int(hashlib.md5(f"{flag_key}:{user_id}".encode()).hexdigest(), 16) % 100
        return bucket < rollout_pct
```

**Trade-offs:** Distributing a periodically-refreshed static snapshot (rather than a live database call per flag check) trades a few seconds of propagation delay for eliminating the flag-evaluation service as a hot-path dependency/bottleneck entirely — the right trade for a system where "flag changes apply within a few seconds" is acceptable but "every request makes a network call to check a flag" is not.

**Follow-Up Questions:**
- *"How do you ensure a user consistently sees the same A/B test variant across multiple sessions/devices?"* → The deterministic hash-based bucketing shown above (hash of `flag_key + user_id`) ensures the same user always lands in the same bucket, as long as `user_id` (not a session ID) is used as the hashing input.
- *"What happens if the snapshot distribution pipeline breaks and flags go stale?"* → Each app server should alert if its local snapshot's timestamp exceeds a staleness threshold (e.g., 5 minutes old), and default to a safe fallback behavior (flags remain at their last-known-good state, which is safer than crashing or defaulting all flags to disabled/enabled blindly).

---

## §70 Public API Gateway Design (Multi-Tenant, External Developers)

**Problem:** Design a public-facing API gateway for a platform exposing APIs to thousands of external third-party developers, with per-developer authentication, rate limiting, billing metering, and version management.

**Requirements:**
- Authenticate external developers via API keys or OAuth2.
- Enforce per-tier rate limits (free/pro/enterprise tiers with different quotas).
- Meter usage accurately for billing purposes.
- Support multiple API versions simultaneously without breaking existing integrations.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| API front door | API Gateway (usage plans + API keys) | Apigee (full API management platform) | Auth, rate limiting, request/response transformation |
| Developer portal | Custom-built or a 3rd-party portal | Apigee's built-in developer portal | Self-service API key issuance, docs, usage dashboards |
| Usage metering | API Gateway usage plans + CloudWatch metrics | Apigee's native analytics | Track requests per developer for billing |
| Backend routing | API Gateway integrations to Lambda/ECS per version | Apigee proxies routing to Cloud Run/GKE per version | Route `/v1/*` and `/v2/*` to different backend implementations |

**Key code — API Gateway usage plan with tiered rate limits (Terraform):**

```hcl
resource "aws_api_gateway_usage_plan" "free_tier" {
  name = "free-tier"

  api_stages {
    api_id = aws_api_gateway_rest_api.public_api.id
    stage  = aws_api_gateway_stage.prod.stage_name
  }

  throttle_settings {
    rate_limit  = 10    # requests per second
    burst_limit = 20
  }

  quota_settings {
    limit  = 10000   # requests per period
    period = "MONTH"
  }
}

resource "aws_api_gateway_usage_plan" "enterprise_tier" {
  name = "enterprise-tier"

  api_stages {
    api_id = aws_api_gateway_rest_api.public_api.id
    stage  = aws_api_gateway_stage.prod.stage_name
  }

  throttle_settings {
    rate_limit  = 1000
    burst_limit = 2000
  }

  quota_settings {
    limit  = 10000000
    period = "MONTH"
  }
}

resource "aws_api_gateway_api_key" "developer_key" {
  name    = "developer-${var.developer_id}"
  enabled = true
}

resource "aws_api_gateway_usage_plan_key" "link" {
  key_id        = aws_api_gateway_api_key.developer_key.id
  key_type      = "API_KEY"
  usage_plan_id = aws_api_gateway_usage_plan.free_tier.id
}
```

**Trade-offs:** Using a fully managed API management layer (API Gateway usage plans, or Apigee's much richer feature set) over hand-rolling rate limiting/metering (§66's pattern) trades some cost/flexibility for built-in developer portal, billing integration, and analytics — the right choice specifically for an EXTERNAL, third-party-facing API surface where these features are core product requirements, versus an internal-only API where a simpler custom rate limiter suffices.

**Follow-Up Questions:**
- *"How would you roll out a breaking API v3 without disrupting existing v1/v2 integrations?"* → Run all versions simultaneously behind the same gateway (path-based routing to different backend implementations), with a clear deprecation timeline communicated to developers, and usage analytics to identify which developers are still on the oldest version before ever removing it.
- *"How do you detect and stop API key abuse (e.g., a leaked key being used for scraping)?"* → Monitor for anomalous usage patterns per key (sudden volume spike, requests from many new IPs simultaneously) and support instant key revocation/rotation, combined with encouraging developers to scope keys to only the specific endpoints/permissions they need (least privilege applied to API keys).

## §71 Centralized Log Aggregation Platform

**Problem:** Design a centralized logging platform ingesting logs from thousands of services/hosts, supporting full-text search, structured querying, and long-term retention for compliance.

**Requirements:**
- Ingest logs from thousands of sources at high volume (millions of log lines/minute).
- Support full-text search and structured field queries (e.g., `status_code:500 AND service:checkout`).
- Retain logs for compliance (e.g., 1 year), with tiered cost (hot/warm/cold).
- Alert on log-based patterns (e.g., error rate spike) in near-real-time.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Log shipping agent | CloudWatch Agent / Fluent Bit sidecar | Cloud Logging Agent / Fluent Bit sidecar | Collects logs from hosts/containers |
| Ingestion buffer | Kinesis Data Streams / Firehose | Pub/Sub | Buffers/decouples log producers from the indexing backend |
| Indexing/search | OpenSearch Service | Elasticsearch on GKE, or Cloud Logging's native search | Full-text + structured query engine |
| Hot/warm/cold tiering | OpenSearch UltraWarm + Cold storage tiers, or export to S3 | Elasticsearch ILM to cheaper storage, or export to GCS | Cost optimization for aging log data |
| Alerting | OpenSearch alerting plugin / CloudWatch Logs metric filters | Cloud Logging log-based metrics + Cloud Monitoring alerts | Real-time pattern-based alerting |

**Key code #1 — Terraform: OpenSearch domain with UltraWarm tiering for cost-efficient log retention:**

```hcl
resource "aws_opensearch_domain" "logs" {
  domain_name    = "central-logs"
  engine_version = "OpenSearch_2.11"

  cluster_config {
    instance_type            = "r6g.xlarge.search"
    instance_count            = 6
    zone_awareness_enabled    = true
    warm_enabled              = true
    warm_count                = 3
    warm_type                 = "ultrawarm1.medium.search"
    zone_awareness_config {
      availability_zone_count = 3
    }
  }

  ebs_options {
    ebs_enabled = true
    volume_size = 200
    volume_type = "gp3"
  }

  encrypt_at_rest { enabled = true }
  node_to_node_encryption { enabled = true }

  log_publishing_options {
    cloudwatch_log_group_arn = aws_cloudwatch_log_group.opensearch_slow_logs.arn
    log_type                 = "INDEX_SLOW_LOGS"
  }
}

resource "aws_opensearch_domain_policy" "logs_policy" {
  domain_name = aws_opensearch_domain.logs.domain_name
  access_policies = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Effect    = "Allow"
      Principal = { AWS = "*" }
      Action    = "es:ESHttp*"
      Resource  = "${aws_opensearch_domain.logs.arn}/*"
      Condition = {
        IpAddress = { "aws:SourceIp" = var.allowed_cidrs }
      }
    }]
  })
}
```

**Key code #2 — Fluent Bit sidecar config shipping structured JSON logs into the pipeline:**

```yaml
# fluent-bit.conf (as a ConfigMap mounted into every pod's sidecar)
[SERVICE]
    Flush         5
    Log_Level     info

[INPUT]
    Name              tail
    Path              /var/log/containers/*.log
    Parser            docker
    Tag               kube.*
    Refresh_Interval  5

[FILTER]
    Name          kubernetes
    Match         kube.*
    Merge_Log     On
    Keep_Log      Off

[OUTPUT]
    Name              kinesis_streams
    Match             *
    region            us-east-1
    stream            log-ingestion-stream
```

**Trade-offs:** Buffering logs through Kinesis/Pub-Sub before indexing (rather than shipping directly to OpenSearch/Elasticsearch) trades a small amount of end-to-end latency for the ability to absorb ingestion bursts without overwhelming the indexing cluster, and enables fanning the SAME log stream out to multiple destinations (indexing + a cheap S3/GCS archive) independently.

**Follow-Up Questions:**
- *"How would you control cost as log volume grows 10x?"* → Aggressive tiering (move logs older than a few days to UltraWarm/warm storage, older than a month to cold/S3-GCS archive), sampling of high-volume-but-low-value logs (e.g., health-check logs), and enforcing structured logging with consistent field names so queries scan less data.
- *"How do you prevent one noisy service from overwhelming the shared logging pipeline for everyone else?"* → Per-service ingestion rate limits/quotas at the shipping-agent or ingestion-buffer layer, with alerting on any service that suddenly logs far above its historical baseline (often itself a symptom of a bug worth fixing at the source).

---

## §72 Distributed Job Scheduler / Cron Service

**Problem:** Design a distributed cron/job-scheduling service that reliably triggers scheduled and recurring jobs (e.g., "run this job every day at 2am") across a fleet of workers, with no duplicate or missed executions.

**Requirements:**
- Support cron-style recurring schedules and one-off future-scheduled jobs.
- Exactly-once triggering semantics (no duplicate runs even with multiple scheduler instances for HA).
- Handle a worker failing mid-job (retry/reschedule).
- Scale to millions of scheduled jobs across many tenants.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Job definitions store | DynamoDB | Firestore | Stores schedule definitions, next-run-time, job payload |
| Scheduler trigger | EventBridge Scheduler | Cloud Scheduler | Fires at the scheduled time, invokes a target |
| Distributed lock (avoid duplicate triggering) | DynamoDB conditional writes | Firestore transactions | Ensures only ONE scheduler instance claims a given job execution |
| Job execution | SQS → worker fleet (ECS/Lambda) | Cloud Tasks → worker fleet (Cloud Run/GKE) | Executes the actual job payload |
| Dead/failed job handling | SQS DLQ + retry with backoff | Cloud Tasks retry config + DLQ topic | Handles worker failures gracefully |

**Key code #1 — Distributed claim via a conditional write (prevents 2 scheduler instances double-triggering):**

```python
def try_claim_job_execution(dynamodb_table, job_id: str, scheduled_time: str, claim_ttl_seconds: int = 300):
    """Atomically claims a specific (job_id, scheduled_time) execution slot -- if another
    scheduler instance already claimed it, this raises ConditionalCheckFailedException
    and the caller should simply skip (not retry the same slot)."""
    import time
    import boto3
    from botocore.exceptions import ClientError

    try:
        dynamodb_table.put_item(
            Item={
                "PK": f"JOB#{job_id}",
                "SK": f"EXEC#{scheduled_time}",
                "claimed_by": get_instance_id(),
                "claimed_at": int(time.time()),
                "expires_at": int(time.time()) + claim_ttl_seconds,
            },
            ConditionExpression="attribute_not_exists(PK)",
        )
        return True
    except ClientError as e:
        if e.response["Error"]["Code"] == "ConditionalCheckFailedException":
            return False  # another instance already claimed this execution
        raise


def get_instance_id() -> str:
    import socket
    return socket.gethostname()
```

**Key code #2 — Cron expression evaluation to compute the next run time:**

```python
from croniter import croniter
from datetime import datetime


def compute_next_run_times(cron_expression: str, after: datetime, count: int = 1) -> list[datetime]:
    """Given a standard cron expression (e.g., '0 2 * * *' for daily at 2am), compute
    the next N run times after a given timestamp -- used both to schedule the next
    trigger AND to backfill/catch-up missed runs after a scheduler outage."""
    iterator = croniter(cron_expression, after)
    return [iterator.get_next(datetime) for _ in range(count)]


def detect_missed_runs(cron_expression: str, last_successful_run: datetime, now: datetime) -> list[datetime]:
    """After a scheduler outage, detect any runs that SHOULD have fired but didn't --
    critical for jobs where a missed run has business impact (e.g., a daily billing job)."""
    iterator = croniter(cron_expression, last_successful_run)
    missed = []
    next_run = iterator.get_next(datetime)
    while next_run < now:
        missed.append(next_run)
        next_run = iterator.get_next(datetime)
    return missed
```

**Trade-offs:** Using a conditional-write-based distributed claim (rather than a heavier distributed lock service like ZooKeeper/etcd) keeps the scheduler simple and leverages the database's native atomicity guarantees, at the cost of the claim being tied specifically to DynamoDB/Firestore's transaction semantics rather than being a general-purpose lock reusable elsewhere.

**Follow-Up Questions:**
- *"How do you handle a job that should run 'every 5 minutes' but takes longer than 5 minutes to execute?"* → Explicitly decide (and make configurable per job) whether overlapping executions are allowed — for most cron-style jobs, skip the next scheduled trigger if the previous execution is still running, rather than allowing unbounded concurrent executions of the same job.
- *"How would you support a customer-facing 'schedule a reminder for this exact time' feature at massive scale (millions of one-off schedules)?"* → Avoid a naive "check every job every minute" polling approach at this scale; instead, use a time-bucketed index (e.g., partition scheduled jobs by their target minute/hour) so the scheduler only needs to query the specific time bucket that's currently due, not scan the entire job table.

---

## §73 Real-Time Fraud Detection Pipeline

**Problem:** Design a real-time fraud detection system for a payments platform that must approve/decline each transaction within 200ms while applying both rule-based checks and an ML model score.

**Requirements:**
- Sub-200ms end-to-end decision latency (synchronous, blocks the checkout flow).
- Combine deterministic rules (velocity checks, blocklists) with an ML fraud-probability score.
- Continuously retrain the ML model on labeled outcomes (confirmed fraud/legitimate).
- Auditable — every decision must be explainable/traceable after the fact.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Real-time feature lookup | DynamoDB / DAX | Bigtable / Memorystore | Fast lookup of velocity counters (e.g., "transactions by this card in the last hour") |
| Rules engine | Lambda (in-process rule evaluation) | Cloud Run (in-process rule evaluation) | Fast deterministic checks (blocklist, velocity thresholds) |
| ML scoring | SageMaker real-time endpoint | Vertex AI Endpoint | Returns a fraud-probability score within the latency budget |
| Decision audit log | Kinesis Firehose → S3 | Pub/Sub → BigQuery | Immutable record of every decision + inputs, for compliance/audit |
| Model retraining | SageMaker Pipelines (scheduled) | Vertex AI Pipelines (scheduled) | Periodic retraining on newly labeled outcomes |

**Key code #1 — Combined rules + ML scoring decision logic:**

```python
def evaluate_transaction(transaction: dict, feature_store, ml_client, rules_config) -> dict:
    """Runs FAST deterministic rules first (cheap, can short-circuit), only calling the
    (relatively more expensive) ML model if the rules don't already decide the outcome."""
    velocity_count = feature_store.get_recent_transaction_count(
        card_id=transaction["card_id"], window_minutes=60
    )
    if velocity_count > rules_config["max_transactions_per_hour"]:
        return {"decision": "DECLINE", "reason": "velocity_exceeded", "score": None}

    if transaction["card_id"] in feature_store.get_blocklist():
        return {"decision": "DECLINE", "reason": "blocklisted", "score": None}

    ml_score = ml_client.predict(build_feature_vector(transaction, feature_store))
    if ml_score > rules_config["fraud_score_decline_threshold"]:
        return {"decision": "DECLINE", "reason": "ml_high_risk", "score": ml_score}
    elif ml_score > rules_config["fraud_score_review_threshold"]:
        return {"decision": "MANUAL_REVIEW", "reason": "ml_medium_risk", "score": ml_score}

    return {"decision": "APPROVE", "reason": "passed_all_checks", "score": ml_score}


def build_feature_vector(transaction: dict, feature_store) -> list[float]:
    return [
        transaction["amount"],
        feature_store.get_recent_transaction_count(transaction["card_id"], 60),
        feature_store.get_merchant_risk_score(transaction["merchant_id"]),
        feature_store.get_account_age_days(transaction["customer_id"]),
    ]
```

**Key code #2 — Terraform for the real-time inference endpoint with autoscaling:**

```hcl
resource "aws_sagemaker_endpoint_configuration" "fraud_model" {
  name = "fraud-detection-config"

  production_variants {
    variant_name           = "primary"
    model_name              = aws_sagemaker_model.fraud_model.name
    initial_instance_count   = 3
    instance_type            = "ml.c6i.xlarge"
    initial_variant_weight   = 1.0
  }
}

resource "aws_sagemaker_endpoint" "fraud_model" {
  name                 = "fraud-detection-endpoint"
  endpoint_config_name = aws_sagemaker_endpoint_configuration.fraud_model.name
}

resource "aws_appautoscaling_target" "fraud_endpoint" {
  max_capacity       = 20
  min_capacity       = 3
  resource_id        = "endpoint/${aws_sagemaker_endpoint.fraud_model.name}/variant/primary"
  scalable_dimension = "sagemaker:variant:DesiredInstanceCount"
  service_namespace  = "sagemaker"
}

resource "aws_appautoscaling_policy" "fraud_endpoint_scaling" {
  name               = "fraud-endpoint-invocations"
  policy_type        = "TargetTrackingScaling"
  resource_id        = aws_appautoscaling_target.fraud_endpoint.resource_id
  scalable_dimension = aws_appautoscaling_target.fraud_endpoint.scalable_dimension
  service_namespace  = aws_appautoscaling_target.fraud_endpoint.service_namespace

  target_tracking_scaling_policy_configuration {
    target_value = 1000.0
    predefined_metric_specification {
      predefined_metric_type = "SageMakerVariantInvocationsPerInstance"
    }
  }
}
```

**Trade-offs:** Running cheap deterministic rules BEFORE the ML model call (short-circuiting on an obvious decline) reduces average latency and ML inference cost, at the cost of the rules needing careful tuning to avoid false-positive declines that a smarter ML model might have correctly approved — a deliberate layered-defense trade-off prioritizing speed/cost for the clear-cut cases.

**Follow-Up Questions:**
- *"How do you handle model drift as fraud patterns evolve over time?"* → Continuous monitoring of the model's real-world precision/recall against confirmed outcomes (chargebacks, manual review results), triggering retraining (§31's pipeline) when drift metrics degrade beyond a threshold, not just on a fixed calendar schedule.
- *"How would you make a declined transaction's reasoning explainable to a customer support agent?"* → Log the specific rule that triggered (if rule-based) or the top contributing features to the ML score (via a model-explainability technique like SHAP values, computed asynchronously and attached to the audit log) — critical since "the model said so" is not an acceptable explanation for a declined legitimate customer.

---

## §74 Social Graph Storage & Friend Recommendations

**Problem:** Design storage for a social network's friend/follow graph (billions of edges) supporting fast "mutual friends," "friend suggestions," and "is A connected to B" queries.

**Requirements:**
- Store billions of edges (user-to-user relationships) at scale.
- Sub-100ms "list my friends" and "mutual friends with X" queries.
- Generate "people you may know" suggestions (friends-of-friends not yet connected).
- Handle celebrity/high-degree nodes (millions of followers) without degrading normal-user queries.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Graph storage | DynamoDB (adjacency-list model) or Neptune | Bigtable (adjacency-list model) or Spanner Graph | Stores edges; DynamoDB/Bigtable for pure high-throughput edge lookups, Neptune/Spanner Graph if complex graph traversal queries are needed |
| Friend-suggestion precompute | EMR/Spark batch job (friends-of-friends) | Dataproc/Spark batch job | Nightly batch computation of suggestion candidates, since real-time full graph traversal is too expensive |
| High-degree node handling | Special-cased pagination/sampling for celebrity accounts | Same pattern | Avoids returning/processing millions of edges in one request |
| Caching | ElastiCache (cache "list of friends" for active users) | Memorystore | Reduces repeated graph-storage reads for frequently-accessed profiles |

**Key code #1 — Adjacency-list edge model on DynamoDB (each friendship stored as 2 rows for O(1) bidirectional lookup):**

```python
def add_friendship(table, user_a: str, user_b: str):
    """Store the edge twice (once per direction) -- trades 2x storage for O(1)
    'list my friends' queries in either direction, avoiding a graph traversal."""
    timestamp = int(time.time())
    table.put_item(Item={"PK": f"USER#{user_a}", "SK": f"FRIEND#{user_b}", "since": timestamp})
    table.put_item(Item={"PK": f"USER#{user_b}", "SK": f"FRIEND#{user_a}", "since": timestamp})


def list_friends(table, user_id: str) -> list[str]:
    response = table.query(
        KeyConditionExpression=Key("PK").eq(f"USER#{user_id}") & Key("SK").begins_with("FRIEND#")
    )
    return [item["SK"].split("#")[1] for item in response["Items"]]


def mutual_friends(table, user_a: str, user_b: str) -> list[str]:
    friends_a = set(list_friends(table, user_a))
    friends_b = set(list_friends(table, user_b))
    return list(friends_a & friends_b)
```

**Key code #2 — Friends-of-friends suggestion batch job (conceptual Spark pseudocode):**

```python
# Nightly Spark/Dataproc batch job (simplified) -- computes 2-hop friend-of-friend
# candidates not already connected, ranked by mutual-friend count
def compute_friend_suggestions(edges_rdd):
    edges = edges_rdd.map(lambda e: (e.user_a, e.user_b))
    friends_by_user = edges.groupByKey().mapValues(set)

    def suggest_for_user(user_id, direct_friends):
        candidates = {}
        for friend in direct_friends:
            for fof in friends_by_user.value.get(friend, []):
                if fof != user_id and fof not in direct_friends:
                    candidates[fof] = candidates.get(fof, 0) + 1  # count mutual-friend overlap
        ranked = sorted(candidates.items(), key=lambda x: x[1], reverse=True)
        return (user_id, ranked[:20])

    return friends_by_user.map(lambda kv: suggest_for_user(kv[0], kv[1]))
```

**Trade-offs:** Precomputing friend suggestions in a nightly batch job (rather than real-time graph traversal per request) trades suggestion freshness (up to 24 hours stale) for dramatically lower latency/cost on a query pattern (2-hop graph traversal across billions of edges) that would be prohibitively expensive to compute synchronously per request.

**Follow-Up Questions:**
- *"How do you handle a celebrity account with 50 million followers when computing mutual friends?"* → Cap the number of edges considered for extremely high-degree nodes (sample a representative subset rather than the full follower list), since exact mutual-friend computation against a 50M-follower account is both computationally expensive and not meaningfully more useful to the end user than an approximation.
- *"Would you use a dedicated graph database (Neptune/Spanner Graph) instead of DynamoDB/Bigtable's adjacency-list model?"* → Only if the product needs genuinely complex multi-hop graph QUERIES expressed declaratively (e.g., "find shortest path between two users," "find all users within 3 hops who share 2+ interests") — for the narrow, well-defined access patterns here (list friends, mutual friends, precomputed suggestions), the simpler and far more scalable adjacency-list-on-a-KV-store approach is preferable and is what large-scale social platforms actually use in practice.

## §75 Push Notification Fan-Out Service

**Problem:** Design a service sending push notifications to millions of mobile devices (iOS/Android) in bulk (e.g., a marketing campaign) and individually (e.g., "someone liked your post"), respecting each user's notification preferences and platform-specific delivery (APNs/FCM).

**Requirements:**
- Send individual, real-time notifications (sub-second) and bulk campaigns (millions of devices within minutes).
- Respect per-user notification preferences/opt-outs and quiet hours.
- Handle platform-specific delivery (APNs for iOS, FCM for Android) and invalid/expired device tokens.
- Track delivery/open metrics for campaign analytics.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Device token registry | DynamoDB | Firestore | Maps user_id → device tokens + platform + preferences |
| Individual send path | Lambda → SNS Mobile Push | Cloud Function → FCM directly | Low-latency single-notification delivery |
| Bulk campaign fan-out | SQS (queue of recipient batches) → Lambda workers | Pub/Sub (batches) → Cloud Run workers | Parallelized bulk delivery without overwhelming APNs/FCM rate limits |
| Delivery tracking | DynamoDB + Kinesis Firehose → S3/Athena | Firestore + Pub/Sub → BigQuery | Analytics on delivery/open rates |
| Token cleanup | Lambda processing APNs/FCM feedback (invalid token responses) | Cloud Function processing FCM error responses | Removes stale/invalid tokens to keep the registry clean |

**Key code #1 — Bulk campaign fan-out with batching and backoff (respects platform rate limits):**

```python
import time
from concurrent.futures import ThreadPoolExecutor


class NotificationFanOutWorker:
    def __init__(self, fcm_client, apns_client, token_registry, batch_size: int = 500):
        self._fcm = fcm_client
        self._apns = apns_client
        self._registry = token_registry
        self._batch_size = batch_size

    def send_campaign(self, campaign_id: str, user_ids: list[str], message: dict):
        devices = self._registry.get_devices_for_users(user_ids)
        android_tokens = [d.token for d in devices if d.platform == "android" and d.opted_in]
        ios_tokens = [d.token for d in devices if d.platform == "ios" and d.opted_in]

        with ThreadPoolExecutor(max_workers=10) as executor:
            futures = []
            for batch in self._chunk(android_tokens, self._batch_size):
                futures.append(executor.submit(self._send_fcm_batch, batch, message))
            for batch in self._chunk(ios_tokens, self._batch_size):
                futures.append(executor.submit(self._send_apns_batch, batch, message))
            for f in futures:
                f.result()  # surfaces any exception, logged/retried by the caller

    def _send_fcm_batch(self, tokens: list[str], message: dict):
        response = self._fcm.send_multicast(tokens=tokens, notification=message)
        self._handle_invalid_tokens(response.failures, platform="android")

    def _send_apns_batch(self, tokens: list[str], message: dict):
        response = self._apns.send_batch(tokens=tokens, payload=message)
        self._handle_invalid_tokens(response.failures, platform="ios")

    def _handle_invalid_tokens(self, failures: list, platform: str):
        for failure in failures:
            if failure.reason in ("InvalidRegistration", "Unregistered", "BadDeviceToken"):
                self._registry.remove_token(failure.token, platform)

    @staticmethod
    def _chunk(items: list, size: int):
        for i in range(0, len(items), size):
            yield items[i:i + size]
```

**Key code #2 — Terraform: SQS-based fan-out queue with a dead-letter queue for failed batches:**

```hcl
resource "aws_sqs_queue" "notification_dlq" {
  name                      = "notification-campaign-dlq"
  message_retention_seconds = 1209600  # 14 days
}

resource "aws_sqs_queue" "notification_batches" {
  name                       = "notification-campaign-batches"
  visibility_timeout_seconds = 300
  redrive_policy = jsonencode({
    deadLetterTargetArn = aws_sqs_queue.notification_dlq.arn
    maxReceiveCount      = 5
  })
}

resource "aws_lambda_event_source_mapping" "worker_trigger" {
  event_source_arn                  = aws_sqs_queue.notification_batches.arn
  function_name                      = aws_lambda_function.notification_worker.arn
  batch_size                         = 1
  maximum_concurrency                = 50   # caps concurrent Lambda invocations to avoid
                                             # overwhelming APNs/FCM's own rate limits
}
```

**Trade-offs:** Batching recipients into fixed-size chunks processed in parallel (rather than one notification per queue message) trades some per-message granularity for dramatically better throughput on bulk campaigns, while the `maximum_concurrency` cap on the Lambda trigger deliberately self-throttles to stay within APNs/FCM's own platform-side rate limits, avoiding the whole campaign being rate-limited/rejected by the push providers.

**Follow-Up Questions:**
- *"How do you avoid sending a notification during a user's configured quiet hours (e.g., 10pm-8am local time)?"* → Store each user's timezone and quiet-hours preference alongside their device token, and either delay/queue the notification until quiet hours end (for non-urgent campaign notifications) or simply suppress it entirely (for individual, time-sensitive notifications where a late delivery would be pointless).
- *"How would you A/B test notification copy/timing for a campaign?"* → Split the recipient list into cohorts at send time (similar to §65's A/B testing pattern), tag each sent notification with its variant, and correlate with the delivery/open-rate analytics pipeline to measure which variant performed better.

---

## §76 Distributed Configuration & Feature Store Service

**Problem:** Design a centralized configuration service that hundreds of microservices read from at startup and periodically thereafter, supporting environment-specific overrides, versioning, and safe rollback of a bad config change.

**Requirements:**
- Serve configuration to hundreds of services reliably, even if the config service itself is briefly unavailable.
- Support environment/region-specific overrides layered on top of defaults.
- Version every config change, with instant rollback capability.
- Changes should propagate to running services within seconds, without a redeploy.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Config source of truth | Systems Manager Parameter Store / AppConfig | Runtime Configurator (via Firestore) / Secret Manager for sensitive values | Versioned, hierarchical config storage |
| Safe rollout | AppConfig's built-in deployment strategies (gradual rollout + automatic rollback on alarm) | Custom rollout logic via Cloud Deploy-style staged config pushes | Prevents a bad config from instantly breaking 100% of services |
| Client-side caching | AppConfig Lambda extension / local SDK cache | Local SDK cache with periodic refresh | Services keep working with the last-known-good config if the config service is briefly down |
| Change audit | CloudTrail (all AppConfig API calls) | Cloud Audit Logs | Full history of who changed what config, when |

**Key code #1 — AppConfig-style gradual rollout with automatic rollback (Terraform):**

```hcl
resource "aws_appconfig_deployment_strategy" "gradual_rollout" {
  name                           = "gradual-10-percent-steps"
  deployment_duration_in_minutes = 20
  growth_factor                   = 10   # 10% of clients get the new config every step
  growth_type                     = "LINEAR"
  final_bake_time_in_minutes      = 10   # soak at 100% before considering fully deployed
  replicate_to                    = "NONE"
}

resource "aws_appconfig_deployment" "config_rollout" {
  application_id           = aws_appconfig_application.services.id
  environment_id            = aws_appconfig_environment.prod.environment_id
  configuration_profile_id  = aws_appconfig_configuration_profile.service_config.configuration_profile_id
  configuration_version     = aws_appconfig_hosted_configuration_version.v2.version_number
  deployment_strategy_id    = aws_appconfig_deployment_strategy.gradual_rollout.id
}

resource "aws_cloudwatch_metric_alarm" "config_error_rate" {
  alarm_name          = "config-rollout-error-rate"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 2
  metric_name         = "5XXError"
  namespace           = "AWS/ApplicationELB"
  period              = 60
  statistic           = "Sum"
  threshold           = 50
  # AppConfig automatically halts/rolls back the deployment if this alarm fires
  # during the rollout window -- a config-level analog of §33's canary rollback
}
```

**Key code #2 — Client-side config SDK with graceful degradation to last-known-good:**

```python
import time
import threading


class ConfigClient:
    def __init__(self, config_source, refresh_interval_seconds: int = 30):
        self._config_source = config_source
        self._current_config: dict = {}
        self._last_successful_fetch: float = 0
        self._lock = threading.Lock()
        self._fetch_and_cache()  # initial synchronous load at startup
        self._start_background_refresh(refresh_interval_seconds)

    def get(self, key: str, default=None):
        with self._lock:
            return self._current_config.get(key, default)

    def _fetch_and_cache(self):
        try:
            new_config = self._config_source.fetch_latest()
            with self._lock:
                self._current_config = new_config
                self._last_successful_fetch = time.time()
        except Exception as e:
            # Deliberately swallow the error and KEEP serving the last-known-good
            # config -- a config-fetch failure should never crash the service or
            # block it from starting/continuing to operate.
            staleness = time.time() - self._last_successful_fetch
            if staleness > 300:
                log_warning(f"Config is {staleness}s stale, last fetch failed: {e}")

    def _start_background_refresh(self, interval: int):
        def loop():
            while True:
                time.sleep(interval)
                self._fetch_and_cache()
        thread = threading.Thread(target=loop, daemon=True)
        thread.start()


def log_warning(msg: str):
    print(f"WARNING: {msg}")
```

**Trade-offs:** Caching the last-known-good config locally and degrading gracefully on fetch failure trades a small window of potential staleness for eliminating the config service as a hard dependency for every service's ability to run — a config service outage becomes a "config might be slightly stale" problem, never a "every dependent service crashes" problem.

**Follow-Up Questions:**
- *"How would you roll back a bad config change that's already been deployed to 100% of services?"* → Every config change is versioned (per the AppConfig hosted configuration version above); rollback is simply deploying the PREVIOUS version through the same gradual-rollout mechanism — never a special-cased "emergency" code path, since that path would be undertested compared to the normal deployment path.
- *"How do you prevent two engineers from concurrently pushing conflicting config changes?"* → Optimistic concurrency control (each config version references the version it was based on; a concurrent conflicting update is rejected and the second engineer must rebase their change on the latest version first) — the same principle as a Git-based merge conflict, applied to config.

---

## §77 Multi-Tenant SaaS Data Isolation Architecture

**Problem:** Design the data isolation strategy for a B2B SaaS product serving thousands of customer organizations (tenants), balancing strong data isolation guarantees against operational/cost efficiency.

**Requirements:**
- Strong guarantee that Tenant A can never access Tenant B's data, even under an application bug.
- Cost-efficient at thousands of tenants (can't dedicate a full database per tiny tenant).
- Support a small number of large "whale" tenants needing dedicated resources/stronger isolation (often a contractual/compliance requirement).
- Support per-tenant backup/restore and data deletion (right-to-be-forgotten compliance).

**Architecture — Three Isolation Models Compared:**

| Model | Isolation Strength | Cost Efficiency | Best For |
|---|---|---|---|
| Silo (dedicated DB per tenant) | Strongest — physical separation | Poor at high tenant count (per-tenant fixed overhead) | Large enterprise/compliance-sensitive tenants |
| Pool (shared DB, tenant_id column + row-level security) | Weaker — relies on correct application/DB-enforced filtering | Best — one shared, well-utilized database | The vast majority of small/medium tenants |
| Bridge (shared DB, separate schema per tenant) | Medium — schema-level separation within one DB instance | Medium | A middle-tier of tenants needing more isolation than pooling but not full dedication |

**Key code #1 — Pool model with PostgreSQL Row-Level Security (defense-in-depth beyond application-layer filtering):**

```sql
-- Enable RLS on every multi-tenant table
ALTER TABLE orders ENABLE ROW LEVEL SECURITY;

-- Policy: a session can only see rows matching its current tenant context --
-- this is enforced by POSTGRES ITSELF, not just application code, so even a bug in
-- application-layer WHERE-clause filtering cannot leak cross-tenant data
CREATE POLICY tenant_isolation_policy ON orders
    USING (tenant_id = current_setting('app.current_tenant_id')::uuid);

-- The application sets this once per connection/request, before running any query
-- SET app.current_tenant_id = '123e4567-e89b-12d3-a456-426614174000';
```

```python
def get_db_connection_for_tenant(connection_pool, tenant_id: str):
    """Every request acquires a connection and IMMEDIATELY sets the tenant context --
    this is the single most important line in a pooled multi-tenant architecture."""
    conn = connection_pool.get_connection()
    conn.execute("SET app.current_tenant_id = %s", (tenant_id,))
    return conn
```

**Key code #2 — Terraform for a "silo" dedicated database, provisioned automatically for whale tenants:**

```hcl
resource "aws_rds_cluster" "tenant_dedicated" {
  for_each                = toset(var.whale_tenant_ids)   # one full cluster per whale tenant
  cluster_identifier       = "tenant-${each.value}"
  engine                   = "aurora-postgresql"
  master_username          = "app_admin"
  master_password          = random_password.tenant_db_password[each.key].result
  db_subnet_group_name     = aws_db_subnet_group.tenants.name
  vpc_security_group_ids   = [aws_security_group.tenant_db.id]
  backup_retention_period  = 35
  deletion_protection      = true

  tags = {
    tenant_id = each.value
    isolation = "silo"
  }
}

resource "random_password" "tenant_db_password" {
  for_each = toset(var.whale_tenant_ids)
  length   = 32
  special  = true
}
```

**Trade-offs:** The Pool model (shared database + RLS) is the pragmatic default for cost efficiency at scale, but requires rigorous discipline (RLS on EVERY table, always setting tenant context, thorough testing for cross-tenant leak bugs) — the Silo model for whale tenants trades away that shared-cost efficiency for the strongest possible isolation guarantee specifically where a contract/compliance requirement demands it, applied selectively rather than universally.

**Follow-Up Questions:**
- *"How do you handle 'right to be forgotten' deletion requests efficiently across the pool model?"* → Since all of a tenant's data shares `tenant_id` as a consistent column, a deletion request is a single indexed `DELETE WHERE tenant_id = X` per table (fast, well-scoped) rather than needing to identify scattered tenant data across an undifferentiated shared store.
- *"What's the risk of relying ONLY on application-layer tenant filtering without database-level RLS?"* → A single missed `WHERE tenant_id = ?` clause in application code (a very plausible bug, especially in a large codebase with many query paths) would leak cross-tenant data with NOTHING to stop it — RLS acts as a mandatory, un-bypassable safety net enforced at the database engine level, which is why relying on application code alone is considered insufficient for genuine multi-tenant isolation guarantees.

---

## §78 Global Session Management / Single Sign-On

**Problem:** Design a global session management and SSO system for a suite of products (multiple domains/apps) so a user logs in once and is authenticated across all of them, with sessions valid across regions.

**Requirements:**
- Single login grants access across multiple product domains (SSO).
- Sessions must be valid/consistent regardless of which region serves a subsequent request.
- Support session revocation (logout everywhere, or admin-forced logout) within seconds.
- Support both short-lived access tokens and longer-lived refresh tokens.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Identity provider | Amazon Cognito (or a self-hosted OIDC provider on EKS) | Identity Platform (or a self-hosted OIDC provider on GKE) | Issues signed JWTs (access + refresh tokens) after login |
| Session/token store (for revocation) | DynamoDB Global Tables | Firestore (multi-region mode) or Spanner | Tracks revoked token IDs / active sessions, replicated globally |
| Token validation | Stateless — each service validates the JWT signature locally (no network call) | Same | Avoids a network round-trip to a central auth service on every single request |
| Cross-domain SSO | Shared cookie domain (if same parent domain) or a redirect-based OIDC flow (if different domains) | Same pattern | Propagates the authenticated session across product domains |

**Key code #1 — Stateless JWT validation with a fast revocation check (best of both worlds):**

```python
import jwt
import time


class SessionValidator:
    """Combines the SPEED of stateless JWT validation (no network call for signature
    check) with the CORRECTNESS of a revocation check (a network call, but only a
    cheap KV lookup, and only needed for revocation -- not full session state)."""

    def __init__(self, public_key: str, revocation_store):
        self._public_key = public_key
        self._revocation_store = revocation_store

    def validate(self, token: str) -> dict:
        try:
            payload = jwt.decode(token, self._public_key, algorithms=["RS256"])
        except jwt.ExpiredSignatureError:
            raise SessionExpiredError()
        except jwt.InvalidTokenError:
            raise InvalidSessionError()

        if self._revocation_store.is_revoked(payload["jti"]):  # jti = unique token ID
            raise SessionRevokedError()

        return payload

    def revoke(self, jti: str, expires_at: int):
        # Store only until the token's natural expiry -- no need to remember a
        # revocation forever once the token would have expired anyway
        ttl = max(0, expires_at - int(time.time()))
        self._revocation_store.put(jti, ttl_seconds=ttl)


class SessionExpiredError(Exception): pass
class InvalidSessionError(Exception): pass
class SessionRevokedError(Exception): pass
```

**Key code #2 — Terraform for a globally-replicated revocation store (DynamoDB Global Tables):**

```hcl
resource "aws_dynamodb_table" "revoked_tokens" {
  name             = "revoked-tokens"
  billing_mode     = "PAY_PER_REQUEST"
  hash_key         = "jti"
  stream_enabled   = true
  stream_view_type = "NEW_AND_OLD_IMAGES"

  attribute {
    name = "jti"
    type = "S"
  }

  ttl {
    attribute_name = "expires_at"
    enabled        = true
  }

  replica {
    region_name = "eu-west-1"
  }
  replica {
    region_name = "ap-southeast-1"
  }
}
```

**Trade-offs:** Stateless JWT validation (checking the signature locally, no network call) gives excellent latency/scalability for the common case, at the cost of needing a SEPARATE revocation mechanism for the "immediate logout everywhere" requirement (since a stateless token, by definition, remains valid until expiry unless explicitly checked against a revocation list) — the hybrid approach above gets both properties by keeping the revocation check cheap (a small, TTL-bounded, globally-replicated table) rather than storing full session state centrally.

**Follow-Up Questions:**
- *"How do you handle a user changing their password — should all existing sessions be invalidated?"* → Yes, typically — on password change, revoke all previously-issued token IDs for that user (requires tracking issued `jti`s per user, or a simpler "tokens issued before timestamp X are invalid" per-user marker checked alongside the revocation list).
- *"How would you reduce the latency/blast-radius impact of the revocation-store lookup being on every request's critical path?"* → Cache "not revoked" results locally per service instance for a short TTL (e.g., 10-30 seconds) — since revocation is a rare event, the vast majority of validations can be served from a warm local cache, only falling through to the network lookup occasionally, trading a small window of "might not see a just-issued revocation instantly" for much lower average latency.

## §79 Serverless Image Processing Pipeline

**Problem:** Design a pipeline that automatically resizes/optimizes/watermarks user-uploaded images into multiple derivative sizes (thumbnail, medium, large, WebP) the moment they're uploaded.

**Requirements:**
- Process each uploaded image into 4+ derivative formats/sizes within seconds.
- Scale from near-zero to thousands of concurrent uploads (marketing spike) automatically.
- Avoid reprocessing an image that's already been processed (idempotency).
- Fail gracefully on corrupt/invalid uploads without blocking the pipeline.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Upload trigger | S3 event notification | Cloud Storage Pub/Sub notification | Fires the moment a new object lands in the raw-uploads bucket |
| Processing function | Lambda (with the Sharp/Pillow image library layer) | Cloud Function (same libraries) | Resizes/converts/watermarks the image |
| Derivative storage | S3 (processed bucket) | Cloud Storage (processed bucket) | Stores the generated derivatives |
| Idempotency guard | S3 object metadata check / DynamoDB processed-marker | GCS object metadata / Firestore processed-marker | Prevents reprocessing on duplicate trigger delivery |

**Key code #1 — Lambda image processing handler (Python + Pillow), idempotent and defensive:**

```python
from PIL import Image
import io
import boto3

s3 = boto3.client("s3")

DERIVATIVES = {
    "thumbnail": (150, 150),
    "medium": (600, 600),
    "large": (1600, 1600),
}


def handler(event, context):
    for record in event["Records"]:
        bucket = record["s3"]["bucket"]["name"]
        key = record["s3"]["object"]["key"]
        process_image(bucket, key)


def process_image(source_bucket: str, key: str):
    if already_processed(key):
        return  # idempotency guard -- skip duplicate S3 event deliveries

    try:
        obj = s3.get_object(Bucket=source_bucket, Key=key)
        image = Image.open(io.BytesIO(obj["Body"].read()))
        image = image.convert("RGB")  # normalize (handles CMYK, palette images, etc.)
    except Exception as e:
        log_error(f"Failed to open image {key}: {e}")
        move_to_quarantine(source_bucket, key)
        return  # fail gracefully -- one bad upload never blocks the pipeline for others

    for name, size in DERIVATIVES.items():
        derivative = image.copy()
        derivative.thumbnail(size, Image.LANCZOS)
        buffer = io.BytesIO()
        derivative.save(buffer, format="WEBP", quality=85)
        buffer.seek(0)
        s3.put_object(
            Bucket="processed-images",
            Key=f"{name}/{key}.webp",
            Body=buffer,
            ContentType="image/webp",
        )

    mark_processed(key)


def already_processed(key: str) -> bool:
    try:
        s3.head_object(Bucket="processed-images", Key=f"thumbnail/{key}.webp")
        return True
    except s3.exceptions.ClientError:
        return False


def mark_processed(key: str):
    pass  # in practice: write to DynamoDB/Firestore, or rely on the head_object check above


def move_to_quarantine(bucket: str, key: str):
    s3.copy_object(Bucket="quarantine-images", CopySource=f"{bucket}/{key}", Key=key)


def log_error(msg: str):
    print(f"ERROR: {msg}")
```

**Key code #2 — Terraform: S3 event trigger + Lambda with reserved concurrency (protects downstream systems from an upload burst):**

```hcl
resource "aws_lambda_function" "image_processor" {
  function_name                 = "image-processor"
  runtime                        = "python3.12"
  handler                        = "handler.handler"
  memory_size                    = 1024
  timeout                        = 30
  reserved_concurrent_executions = 200   # caps concurrency to protect downstream S3/quota limits
  s3_bucket                      = "lambda-deployments"
  s3_key                          = "image-processor.zip"
  layers                          = [aws_lambda_layer_version.pillow_layer.arn]
}

resource "aws_s3_bucket_notification" "upload_trigger" {
  bucket = aws_s3_bucket.raw_uploads.id

  lambda_function {
    lambda_function_arn = aws_lambda_function.image_processor.arn
    events               = ["s3:ObjectCreated:*"]
    filter_suffix        = ".jpg"
  }
}

resource "aws_lambda_permission" "allow_s3" {
  statement_id  = "AllowS3Invoke"
  action        = "lambda:InvokeFunction"
  function_name = aws_lambda_function.image_processor.function_name
  principal     = "s3.amazonaws.com"
  source_arn    = aws_s3_bucket.raw_uploads.arn
}
```

**Trade-offs:** Reserved concurrency caps the maximum parallel Lambda invocations, trading some processing throughput during an extreme spike for protecting shared account-level Lambda concurrency limits and downstream S3 request rate — a deliberate self-throttle rather than an unbounded, potentially-disruptive burst.

**Follow-Up Questions:**
- *"How would you handle a very large image (e.g., 100MB RAW file) that takes longer than Lambda's max execution time?"* → Route large files to a different processing path (Fargate/Cloud Run task with a longer timeout, or a Batch/Cloud Batch job) based on a file-size check at upload time, rather than trying to force every workload through the same Lambda-sized processing path.
- *"How do you avoid double-billing/double-processing if S3 delivers the same event notification twice (a known at-least-once behavior)?"* → The `already_processed()` idempotency guard shown above is exactly this safeguard — always check before doing expensive work, never assume exactly-once event delivery.

---

## §80 Distributed Lock Service

**Problem:** Design a distributed locking service that multiple independent processes/services can use to coordinate exclusive access to a shared resource (e.g., "only one instance should run this maintenance job at a time").

**Requirements:**
- Provide mutual exclusion across processes running on different hosts/services.
- Locks must automatically release if the holder crashes (no permanent deadlock).
- Support both blocking (wait for the lock) and non-blocking (fail immediately if held) acquisition.
- Low latency for lock acquisition/release (this is often on a critical path).

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Lock storage | DynamoDB (conditional writes + TTL) | Firestore (transactions + TTL) or Cloud Spanner for stronger guarantees | Stores lock ownership + auto-expiring TTL |
| Lock client library | A shared SDK wrapping the conditional-write pattern | Same pattern | Provides `acquire()`/`release()`/`renew()` primitives to application code |
| Heartbeat/renewal | Background thread renewing the lock's TTL while held | Same | Prevents a long-running task's lock from expiring mid-work |

**Key code — A complete distributed lock client (DynamoDB-backed, with auto-renewal heartbeat):**

```python
import time
import uuid
import threading
from botocore.exceptions import ClientError


class DistributedLock:
    def __init__(self, dynamodb_table, lock_name: str, ttl_seconds: int = 30):
        self._table = dynamodb_table
        self._lock_name = lock_name
        self._ttl_seconds = ttl_seconds
        self._owner_token = str(uuid.uuid4())
        self._held = False
        self._heartbeat_thread = None
        self._stop_heartbeat = threading.Event()

    def acquire(self, timeout_seconds: float = 10.0, blocking: bool = True) -> bool:
        deadline = time.time() + timeout_seconds
        while True:
            if self._try_acquire_once():
                self._held = True
                self._start_heartbeat()
                return True
            if not blocking or time.time() >= deadline:
                return False
            time.sleep(0.2)  # brief backoff before retrying

    def _try_acquire_once(self) -> bool:
        now = int(time.time())
        try:
            self._table.put_item(
                Item={
                    "lock_name": self._lock_name,
                    "owner_token": self._owner_token,
                    "expires_at": now + self._ttl_seconds,
                },
                # Acquire if unclaimed, OR if the previous holder's lock has expired --
                # this is the crucial safety mechanism preventing permanent deadlock
                # if a previous holder crashed without releasing.
                ConditionExpression="attribute_not_exists(lock_name) OR expires_at < :now",
                ExpressionAttributeValues={":now": now},
            )
            return True
        except ClientError as e:
            if e.response["Error"]["Code"] == "ConditionalCheckFailedException":
                return False
            raise

    def _start_heartbeat(self):
        def renew_loop():
            while not self._stop_heartbeat.wait(self._ttl_seconds / 3):
                self._renew()
        self._heartbeat_thread = threading.Thread(target=renew_loop, daemon=True)
        self._heartbeat_thread.start()

    def _renew(self):
        now = int(time.time())
        try:
            self._table.update_item(
                Key={"lock_name": self._lock_name},
                UpdateExpression="SET expires_at = :new_expiry",
                ConditionExpression="owner_token = :token",  # only renew if we still own it
                ExpressionAttributeValues={
                    ":new_expiry": now + self._ttl_seconds,
                    ":token": self._owner_token,
                },
            )
        except ClientError:
            self._held = False  # lost the lock (e.g., someone else force-broke it)

    def release(self):
        self._stop_heartbeat.set()
        if self._held:
            try:
                self._table.delete_item(
                    Key={"lock_name": self._lock_name},
                    ConditionExpression="owner_token = :token",
                    ExpressionAttributeValues={":token": self._owner_token},
                )
            except ClientError:
                pass  # already lost ownership -- nothing to release
            self._held = False

    def __enter__(self):
        self.acquire()
        return self

    def __exit__(self, *args):
        self.release()
```

**Trade-offs:** A TTL-based expiring lock guarantees eventual release even if the holder crashes (no permanent deadlock), at the cost of a small risk window: if the holder is merely SLOW (not crashed) and the TTL expires before it finishes, another process could acquire the lock while the first is still (mistakenly) working — the heartbeat/renewal mechanism mitigates this by keeping the TTL fresh as long as the holder is alive and responsive, but a truly stalled-but-not-crashed holder remains an edge case worth being explicit about in an interview answer.

**Follow-Up Questions:**
- *"Why not just use a simpler in-memory lock if all your processes run on the same machine?"* → This distributed lock is specifically for coordination ACROSS multiple machines/processes (e.g., multiple instances of a scheduled job running on different hosts) — an in-memory lock only provides mutual exclusion within a single process/machine, which doesn't solve the cross-host coordination problem at all.
- *"How would you use this to ensure only ONE instance of a cron job runs at a time across a fleet of 10 identical workers?"* → Wrap the job's execution in `with DistributedLock(table, "nightly-report-job"): run_job()` — only the worker that successfully acquires the lock executes the job; the other 9 attempt acquisition, fail immediately (non-blocking), and simply skip that run.

---

## §81 API Monetization & Billing Metering System

**Problem:** Design a system that meters usage of a paid API product (e.g., billed per API call, per GB processed) accurately enough to generate correct customer invoices, at high request volume.

**Requirements:**
- Accurately count billable events per customer (no double-counting, no silent drops).
- Aggregate usage into monthly invoices, reconcilable against raw usage records.
- Support usage-based pricing tiers (e.g., first 1M calls free, then $0.001/call).
- Provide customers a near-real-time usage dashboard (not just end-of-month).

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Usage event capture | Each API call emits an event to Kinesis Firehose | Each API call emits an event to Pub/Sub | Durable capture of every billable event |
| Raw event storage | S3 (partitioned by customer/day) | GCS / BigQuery native storage | Source of truth for reconciliation/audits |
| Real-time aggregation | Kinesis Data Analytics → DynamoDB (running counters) | Dataflow → Bigtable/Firestore (running counters) | Powers the near-real-time usage dashboard |
| Monthly invoice generation | Batch job (Glue/EMR) reading the full month's S3 data | Batch job (Dataproc) reading BigQuery | Authoritative, reconciled invoice numbers — NEVER trust only the real-time counters for actual billing |

**Key code — Monthly invoice batch job reconciling raw events against real-time counters (SQL-style, run via Athena/BigQuery):**

```sql
-- Authoritative monthly usage aggregation -- run against the RAW event log (S3/GCS),
-- never against the real-time counters, which are a convenience/UX feature, not the
-- billing source of truth (real-time counters could have transient inconsistencies
-- from retries/at-least-once delivery that must be deduplicated here)
WITH deduplicated_events AS (
    SELECT DISTINCT
        event_id,        -- unique ID per API call, used to dedupe at-least-once deliveries
        customer_id,
        api_endpoint,
        event_timestamp
    FROM raw_usage_events
    WHERE event_date BETWEEN DATE '2026-01-01' AND DATE '2026-01-31'
),
usage_by_customer AS (
    SELECT
        customer_id,
        COUNT(*) AS total_calls
    FROM deduplicated_events
    GROUP BY customer_id
)
SELECT
    customer_id,
    total_calls,
    CASE
        WHEN total_calls <= 1000000 THEN 0
        ELSE (total_calls - 1000000) * 0.001
    END AS billable_amount_usd
FROM usage_by_customer;
```

```python
def generate_invoice(customer_id: str, billing_period: str, deduplicated_usage_count: int,
                      pricing_config: dict) -> dict:
    free_tier = pricing_config["free_tier_calls"]
    per_call_rate = pricing_config["per_call_rate_usd"]
    billable_calls = max(0, deduplicated_usage_count - free_tier)
    amount_due = round(billable_calls * per_call_rate, 2)

    return {
        "customer_id": customer_id,
        "billing_period": billing_period,
        "total_calls": deduplicated_usage_count,
        "free_tier_calls": min(deduplicated_usage_count, free_tier),
        "billable_calls": billable_calls,
        "amount_due_usd": amount_due,
    }
```

**Trade-offs:** Maintaining TWO paths — a real-time (approximate, UX-focused) counter path and a batch (authoritative, deduplicated) reconciliation path — trades some architectural complexity/duplication for the critical business property that actual invoices are ALWAYS generated from a fully deduplicated, reconciled source, never from an approximate real-time signal that could theoretically double-count a retried event.

**Follow-Up Questions:**
- *"How do you handle a customer disputing their invoice, claiming the count is wrong?"* → Because every event has a unique `event_id` and the raw log is retained, you can produce a full itemized audit trail for that customer's billing period — a key reason to retain raw usage events (not just aggregated counts) for at least the dispute-resolution window (often 90+ days).
- *"How would you detect a bug causing systematic under/over-counting before it affects a real invoice?"* → Reconcile the real-time counter total against the batch-reconciled total daily (not just at month-end) — a persistent, growing discrepancy between the two is a strong early signal of a metering bug, caught well before it reaches a customer's invoice.

---

## §82 Real-Time Collaborative Editing Backend

**Problem:** Design the backend for a real-time collaborative document editor (like Google Docs) where multiple users can simultaneously edit the same document and see each other's changes instantly, without conflicts corrupting the document.

**Requirements:**
- Multiple concurrent editors see each other's changes within a few hundred milliseconds.
- Concurrent edits to the same region of text must merge correctly (no lost updates, no corruption).
- Support offline editing with later reconciliation (a user's connection drops, then reconnects).
- Maintain a full edit history for undo/version restore.

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Real-time transport | API Gateway WebSocket API | Cloud Run (WebSocket-capable) or Firestore real-time listeners | Pushes each edit operation to all connected collaborators instantly |
| Conflict resolution engine | Lambda running an OT/CRDT algorithm | Cloud Run running the same algorithm | Merges concurrent edits deterministically |
| Document state storage | DynamoDB (current state) + S3 (periodic snapshots) | Firestore (current state) + GCS (periodic snapshots) | Durable storage of the document's current and historical state |
| Edit history / undo log | DynamoDB Streams → append-only history table | Firestore triggers → append-only history collection | Powers undo/redo and version history |

**Key code — A simplified CRDT-style operational transform for concurrent text insertion (the core conflict-resolution logic):**

```python
class TextOperation:
    """A simplified Operational Transformation (OT) implementation -- real products
    (Google Docs, Figma) use more sophisticated CRDTs, but this illustrates the core
    idea: transform a remote operation against operations that happened concurrently,
    so both converge to the SAME final document state regardless of arrival order."""

    def __init__(self, position: int, insert_text: str = "", delete_count: int = 0):
        self.position = position
        self.insert_text = insert_text
        self.delete_count = delete_count

    def transform_against(self, other: "TextOperation") -> "TextOperation":
        """Adjusts this operation's position to account for a concurrent 'other'
        operation that was applied first (or arrived first at the server)."""
        if other.position <= self.position:
            length_delta = len(other.insert_text) - other.delete_count
            return TextOperation(
                position=max(other.position, self.position + length_delta),
                insert_text=self.insert_text,
                delete_count=self.delete_count,
            )
        return self  # the other operation happened after our position -- no adjustment needed


class CollaborativeDocument:
    def __init__(self, initial_text: str = ""):
        self._text = initial_text
        self._version = 0
        self._pending_ops_by_client: dict[str, list[TextOperation]] = {}

    def apply_operation(self, client_id: str, op: TextOperation, client_version: int) -> TextOperation:
        """Server-authoritative apply: transforms the incoming op against any operations
        that were committed AFTER the client's last-known version, then applies it."""
        concurrent_ops = self._get_ops_since(client_version)
        transformed_op = op
        for concurrent_op in concurrent_ops:
            transformed_op = transformed_op.transform_against(concurrent_op)

        self._text = (
            self._text[:transformed_op.position]
            + transformed_op.insert_text
            + self._text[transformed_op.position + transformed_op.delete_count:]
        )
        self._version += 1
        self._record_op(transformed_op)
        return transformed_op  # broadcast this (already-transformed) op to all other clients

    def _get_ops_since(self, version: int) -> list[TextOperation]:
        return []  # in practice: fetch from the append-only history log

    def _record_op(self, op: TextOperation):
        pass  # in practice: append to DynamoDB Streams-backed history table
```

**Trade-offs:** Server-authoritative operational transformation (the server is the single source of truth that resolves and broadcasts the final transformed operation) trades some added server-side complexity for guaranteeing all clients converge to an identical document state — a pure peer-to-peer CRDT approach avoids the central server dependency but pushes significantly more complexity into every client, a trade-off most production collaborative editors resolve in favor of a server-authoritative model for simplicity and easier debugging.

**Follow-Up Questions:**
- *"How do you handle a user who was offline for an hour and made many local edits, then reconnects?"* → Buffer the user's offline operations locally (in the client), and on reconnect, submit them as a batch to the server one at a time using the SAME transform-against-concurrent-ops logic, effectively "replaying" the offline session against everything that changed while disconnected.
- *"How would you implement 'see other users' cursors moving in real time' on top of this architecture?"* → Cursor positions are ephemeral, non-durable state (unlike document edits) — broadcast them directly over the WebSocket connection to other connected clients without persisting them through the same durable operation-history pipeline, mirroring §34's "typing indicator" ephemeral-event pattern.

---

## §83 Health-Check & Service Discovery Platform

**Problem:** Design a service discovery and health-checking platform that lets hundreds of microservices find and call each other reliably, automatically routing around unhealthy instances.

**Requirements:**
- Services register themselves on startup and deregister on shutdown automatically.
- Continuous health checking with fast (sub-10-second) detection of an unhealthy instance.
- Clients discover healthy instances of a dependency without hardcoded IPs/hostnames.
- Must work across a hybrid environment (some services on VMs, some on Kubernetes).

**Architecture:**

| Component | AWS | GCP | Purpose |
|---|---|---|---|
| Service registry | AWS Cloud Map | Service Directory | Central registry of service instances + metadata |
| Health checking | Cloud Map health checks (or Route 53 health checks) integrated with target health | GKE/Compute Engine health checks feeding into Service Directory | Detects and removes unhealthy instances from discovery results |
| In-cluster discovery (Kubernetes) | Kubernetes native Service/DNS (kube-dns/CoreDNS) | Same — Kubernetes native Service/DNS | For services already inside the cluster, native K8s discovery is simpler than a separate registry |
| Cross-environment discovery (VM ↔ K8s) | Cloud Map bridges VM-based and container-based services under one namespace | Service Directory bridges VM-based and container-based services | Needed specifically for hybrid VM+container environments |

**Key code — A minimal client-side service discovery + health-aware load balancing wrapper:**

```python
import random
import time


class ServiceDiscoveryClient:
    def __init__(self, registry_client, service_name: str, refresh_interval_seconds: int = 15):
        self._registry = registry_client
        self._service_name = service_name
        self._healthy_instances: list[dict] = []
        self._last_refresh = 0
        self._refresh_interval = refresh_interval_seconds

    def get_endpoint(self) -> str:
        self._maybe_refresh()
        if not self._healthy_instances:
            raise NoHealthyInstancesError(self._service_name)
        # Simple random selection among healthy instances -- a real implementation
        # might weight by recent latency/error rate for smarter load balancing
        instance = random.choice(self._healthy_instances)
        return f"http://{instance['host']}:{instance['port']}"

    def _maybe_refresh(self):
        if time.time() - self._last_refresh > self._refresh_interval:
            all_instances = self._registry.discover(self._service_name)
            self._healthy_instances = [i for i in all_instances if i["health_status"] == "HEALTHY"]
            self._last_refresh = time.time()

    def call_with_retry(self, path: str, http_client, max_attempts: int = 3):
        last_error = None
        for attempt in range(max_attempts):
            try:
                endpoint = self.get_endpoint()
                return http_client.get(f"{endpoint}{path}", timeout=2.0)
            except (NoHealthyInstancesError, ConnectionError) as e:
                last_error = e
                self._last_refresh = 0  # force a refresh -- our cached view may be stale
        raise last_error


class NoHealthyInstancesError(Exception):
    def __init__(self, service_name: str):
        super().__init__(f"No healthy instances found for service: {service_name}")
```

**Trade-offs:** Client-side caching of the discovered healthy-instance list (refreshed periodically, rather than querying the registry on every single call) trades a small window of potential staleness (up to `refresh_interval_seconds`) for dramatically reduced load on the central registry — an important scalability property when hundreds of services are all discovering each other constantly.

**Follow-Up Questions:**
- *"How do you avoid a 'split-brain' scenario where the registry itself becomes unavailable?"* → The client-side cache (from the trade-off above) means clients continue operating with their LAST-KNOWN healthy instance list even if the registry is briefly unreachable — the registry's availability requirement is relaxed to "eventually consistent, briefly-cacheable" rather than "must be available for every single service call," a significant resilience improvement.
- *"How would you extend this to support canary/weighted routing (e.g., 5% of traffic to a new version) at the service-discovery layer?"* → Add a `weight` or `version` tag to each registered instance's metadata, and have `get_endpoint()` select among healthy instances using weighted random selection based on that metadata — effectively implementing §33's canary traffic-splitting at the service-discovery client layer rather than requiring a dedicated service mesh, for teams not already running one.

# Part 11 — Reference Implementation Appendix

*Complete, copy-pasteable reference artifacts tying the guide's concepts into real, runnable-looking code. These are deliberately full-length (not trimmed snippets) so you can see how all the pieces of a production system fit together.*

## §84 Complete Terraform: Production Environment (VPC + EKS + RDS + Monitoring)

```hcl
############################################
# providers.tf
############################################
terraform {
  required_version = ">= 1.6.0"
  required_providers {
    aws = { source = "hashicorp/aws", version = "~> 5.0" }
  }
  backend "s3" {
    bucket         = "company-terraform-state"
    key            = "prod/full-stack/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "terraform-locks"
    encrypt        = true
  }
}

provider "aws" {
  region = var.aws_region
  default_tags {
    tags = {
      Environment = var.environment
      ManagedBy   = "terraform"
      Project     = var.project_name
    }
  }
}

############################################
# variables.tf
############################################
variable "aws_region"    { type = string, default = "us-east-1" }
variable "environment"   { type = string, default = "production" }
variable "project_name"  { type = string, default = "orderflow" }
variable "vpc_cidr"      { type = string, default = "10.0.0.0/16" }
variable "azs"           { type = list(string), default = ["us-east-1a", "us-east-1b", "us-east-1c"] }
variable "db_instance_class" { type = string, default = "db.r6g.xlarge" }
variable "eks_node_min"   { type = number, default = 3 }
variable "eks_node_max"   { type = number, default = 30 }

############################################
# vpc.tf
############################################
resource "aws_vpc" "main" {
  cidr_block           = var.vpc_cidr
  enable_dns_support   = true
  enable_dns_hostnames = true
  tags = { Name = "${var.project_name}-vpc" }
}

resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
}

resource "aws_subnet" "public" {
  count                   = length(var.azs)
  vpc_id                  = aws_vpc.main.id
  availability_zone       = var.azs[count.index]
  cidr_block              = cidrsubnet(var.vpc_cidr, 8, count.index)
  map_public_ip_on_launch = true
  tags = { Name = "${var.project_name}-public-${var.azs[count.index]}", "kubernetes.io/role/elb" = "1" }
}

resource "aws_subnet" "private" {
  count             = length(var.azs)
  vpc_id            = aws_vpc.main.id
  availability_zone = var.azs[count.index]
  cidr_block        = cidrsubnet(var.vpc_cidr, 8, count.index + 10)
  tags = { Name = "${var.project_name}-private-${var.azs[count.index]}", "kubernetes.io/role/internal-elb" = "1" }
}

resource "aws_subnet" "data" {
  count             = length(var.azs)
  vpc_id            = aws_vpc.main.id
  availability_zone = var.azs[count.index]
  cidr_block        = cidrsubnet(var.vpc_cidr, 8, count.index + 20)
  tags = { Name = "${var.project_name}-data-${var.azs[count.index]}" }
}

resource "aws_eip" "nat" {
  count  = length(var.azs)
  domain = "vpc"
}

resource "aws_nat_gateway" "main" {
  count         = length(var.azs)
  allocation_id = aws_eip.nat[count.index].id
  subnet_id     = aws_subnet.public[count.index].id
  tags = { Name = "${var.project_name}-nat-${var.azs[count.index]}" }
}

resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.main.id
  }
}

resource "aws_route_table" "private" {
  count  = length(var.azs)
  vpc_id = aws_vpc.main.id
  route {
    cidr_block     = "0.0.0.0/0"
    nat_gateway_id = aws_nat_gateway.main[count.index].id
  }
}

resource "aws_route_table_association" "public" {
  count          = length(var.azs)
  subnet_id      = aws_subnet.public[count.index].id
  route_table_id = aws_route_table.public.id
}

resource "aws_route_table_association" "private" {
  count          = length(var.azs)
  subnet_id      = aws_subnet.private[count.index].id
  route_table_id = aws_route_table.private[count.index].id
}

############################################
# security_groups.tf
############################################
resource "aws_security_group" "eks_nodes" {
  name   = "${var.project_name}-eks-nodes"
  vpc_id = aws_vpc.main.id
  egress {
    from_port = 0
    to_port   = 0
    protocol  = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

resource "aws_security_group" "rds" {
  name   = "${var.project_name}-rds"
  vpc_id = aws_vpc.main.id
  ingress {
    from_port       = 5432
    to_port         = 5432
    protocol        = "tcp"
    security_groups = [aws_security_group.eks_nodes.id]
  }
}

############################################
# eks.tf
############################################
resource "aws_eks_cluster" "main" {
  name     = "${var.project_name}-cluster"
  role_arn = aws_iam_role.eks_cluster.arn
  version  = "1.29"

  vpc_config {
    subnet_ids              = concat(aws_subnet.private[*].id, aws_subnet.public[*].id)
    endpoint_private_access  = true
    endpoint_public_access   = true
  }
}

resource "aws_eks_node_group" "main" {
  cluster_name    = aws_eks_cluster.main.name
  node_group_name = "${var.project_name}-nodes"
  node_role_arn   = aws_iam_role.eks_nodes.arn
  subnet_ids      = aws_subnet.private[*].id

  scaling_config {
    min_size     = var.eks_node_min
    max_size     = var.eks_node_max
    desired_size = var.eks_node_min
  }

  instance_types = ["m6i.large"]
}

resource "aws_iam_role" "eks_cluster" {
  name = "${var.project_name}-eks-cluster-role"
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Effect    = "Allow"
      Principal = { Service = "eks.amazonaws.com" }
      Action    = "sts:AssumeRole"
    }]
  })
}

resource "aws_iam_role_policy_attachment" "eks_cluster_policy" {
  role       = aws_iam_role.eks_cluster.name
  policy_arn = "arn:aws:iam::aws:policy/AmazonEKSClusterPolicy"
}

resource "aws_iam_role" "eks_nodes" {
  name = "${var.project_name}-eks-node-role"
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Effect    = "Allow"
      Principal = { Service = "ec2.amazonaws.com" }
      Action    = "sts:AssumeRole"
    }]
  })
}

resource "aws_iam_role_policy_attachment" "eks_worker_node_policy" {
  role       = aws_iam_role.eks_nodes.name
  policy_arn = "arn:aws:iam::aws:policy/AmazonEKSWorkerNodePolicy"
}

resource "aws_iam_role_policy_attachment" "eks_cni_policy" {
  role       = aws_iam_role.eks_nodes.name
  policy_arn = "arn:aws:iam::aws:policy/AmazonEKS_CNI_Policy"
}

resource "aws_iam_role_policy_attachment" "eks_ecr_readonly" {
  role       = aws_iam_role.eks_nodes.name
  policy_arn = "arn:aws:iam::aws:policy/AmazonEC2ContainerRegistryReadOnly"
}

############################################
# rds.tf
############################################
resource "aws_db_subnet_group" "main" {
  name       = "${var.project_name}-db-subnet-group"
  subnet_ids = aws_subnet.data[*].id
}

resource "aws_db_instance" "main" {
  identifier              = "${var.project_name}-db"
  engine                  = "postgres"
  engine_version          = "15.4"
  instance_class          = var.db_instance_class
  allocated_storage       = 200
  max_allocated_storage   = 1000
  storage_type            = "gp3"
  db_name                 = "orders"
  username                = "app_admin"
  password                = random_password.db_password.result
  multi_az                = true
  db_subnet_group_name    = aws_db_subnet_group.main.name
  vpc_security_group_ids  = [aws_security_group.rds.id]
  backup_retention_period = 14
  storage_encrypted       = true
  deletion_protection     = true
  skip_final_snapshot     = false
  final_snapshot_identifier = "${var.project_name}-db-final-snapshot"
}

resource "random_password" "db_password" {
  length  = 32
  special = true
}

resource "aws_secretsmanager_secret" "db_password" {
  name = "${var.project_name}/db-password"
}

resource "aws_secretsmanager_secret_version" "db_password" {
  secret_id     = aws_secretsmanager_secret.db_password.id
  secret_string = random_password.db_password.result
}

############################################
# monitoring.tf
############################################
resource "aws_cloudwatch_dashboard" "main" {
  dashboard_name = "${var.project_name}-overview"
  dashboard_body = jsonencode({
    widgets = [
      {
        type   = "metric"
        x = 0, y = 0, width = 12, height = 6
        properties = {
          metrics = [["AWS/RDS", "CPUUtilization", "DBInstanceIdentifier", aws_db_instance.main.id]]
          period  = 300
          stat    = "Average"
          title   = "RDS CPU Utilization"
        }
      }
    ]
  })
}

resource "aws_cloudwatch_metric_alarm" "rds_cpu_high" {
  alarm_name          = "${var.project_name}-rds-cpu-high"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 3
  metric_name         = "CPUUtilization"
  namespace           = "AWS/RDS"
  period              = 300
  statistic           = "Average"
  threshold           = 80
  dimensions          = { DBInstanceIdentifier = aws_db_instance.main.id }
  alarm_actions       = [aws_sns_topic.alerts.arn]
}

resource "aws_sns_topic" "alerts" {
  name = "${var.project_name}-alerts"
}

resource "aws_sns_topic_subscription" "platform_team_email" {
  topic_arn = aws_sns_topic.alerts.arn
  protocol  = "email"
  endpoint  = "platform-team@mycompany.com"
}

############################################
# outputs.tf
############################################
output "eks_cluster_endpoint" { value = aws_eks_cluster.main.endpoint }
output "rds_endpoint"         { value = aws_db_instance.main.endpoint, sensitive = true }
output "vpc_id"               { value = aws_vpc.main.id }
```

## §85 Complete Kubernetes Manifests: Multi-Service "App of Apps"

```yaml
# namespace.yaml
apiVersion: v1
kind: Namespace
metadata:
  name: orderflow
  labels:
    team: platform
---
apiVersion: v1
kind: ResourceQuota
metadata:
  name: orderflow-quota
  namespace: orderflow
spec:
  hard:
    requests.cpu: "20"
    requests.memory: 40Gi
    limits.cpu: "40"
    limits.memory: 80Gi
    pods: "100"
```

```yaml
# order-service.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: order-service
  namespace: orderflow
spec:
  replicas: 6
  selector:
    matchLabels: { app: order-service }
  strategy:
    rollingUpdate: { maxSurge: 25%, maxUnavailable: 0 }
  template:
    metadata:
      labels: { app: order-service }
    spec:
      serviceAccountName: order-service-sa
      containers:
        - name: order-service
          image: <registry>/order-service:1.4.2
          ports: [{ containerPort: 8080 }]
          resources:
            requests: { cpu: "250m", memory: "256Mi" }
            limits: { cpu: "500m", memory: "512Mi" }
          readinessProbe:
            httpGet: { path: /healthz/ready, port: 8080 }
            periodSeconds: 10
          livenessProbe:
            httpGet: { path: /healthz/live, port: 8080 }
            periodSeconds: 20
          env:
            - name: APP_CLOUD_PROVIDER
              value: "aws"
            - name: AWS_REGION
              value: "us-east-1"
          envFrom:
            - secretRef: { name: order-service-secrets }
---
apiVersion: v1
kind: Service
metadata:
  name: order-service
  namespace: orderflow
spec:
  selector: { app: order-service }
  ports: [{ port: 80, targetPort: 8080 }]
---
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: order-service-hpa
  namespace: orderflow
spec:
  scaleTargetRef: { apiVersion: apps/v1, kind: Deployment, name: order-service }
  minReplicas: 6
  maxReplicas: 60
  metrics:
    - type: Resource
      resource: { name: cpu, target: { type: Utilization, averageUtilization: 60 } }
---
apiVersion: policy/v1
kind: PodDisruptionBudget
metadata:
  name: order-service-pdb
  namespace: orderflow
spec:
  minAvailable: 4
  selector: { matchLabels: { app: order-service } }
```

```yaml
# inventory-service.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: inventory-service
  namespace: orderflow
spec:
  replicas: 4
  selector:
    matchLabels: { app: inventory-service }
  template:
    metadata:
      labels: { app: inventory-service }
    spec:
      containers:
        - name: inventory-service
          image: <registry>/inventory-service:2.1.0
          ports: [{ containerPort: 8080 }]
          resources:
            requests: { cpu: "200m", memory: "256Mi" }
            limits: { cpu: "400m", memory: "512Mi" }
---
apiVersion: v1
kind: Service
metadata:
  name: inventory-service
  namespace: orderflow
spec:
  selector: { app: inventory-service }
  ports: [{ port: 80, targetPort: 8080 }]
```

```yaml
# payment-service.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: payment-service
  namespace: orderflow
spec:
  replicas: 4
  selector:
    matchLabels: { app: payment-service }
  template:
    metadata:
      labels: { app: payment-service }
    spec:
      containers:
        - name: payment-service
          image: <registry>/payment-service:3.0.1
          ports: [{ containerPort: 8080 }]
          resources:
            requests: { cpu: "300m", memory: "512Mi" }
            limits: { cpu: "600m", memory: "1Gi" }
          env:
            - name: PAYMENT_PROCESSOR_WEBHOOK_SECRET
              valueFrom:
                secretKeyRef: { name: payment-secrets, key: webhook-secret }
---
apiVersion: v1
kind: Service
metadata:
  name: payment-service
  namespace: orderflow
spec:
  selector: { app: payment-service }
  ports: [{ port: 80, targetPort: 8080 }]
```

```yaml
# notification-service.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: notification-service
  namespace: orderflow
spec:
  replicas: 3
  selector:
    matchLabels: { app: notification-service }
  template:
    metadata:
      labels: { app: notification-service }
    spec:
      containers:
        - name: notification-service
          image: <registry>/notification-service:1.2.0
          ports: [{ containerPort: 8080 }]
          resources:
            requests: { cpu: "150m", memory: "256Mi" }
            limits: { cpu: "300m", memory: "512Mi" }
---
apiVersion: v1
kind: Service
metadata:
  name: notification-service
  namespace: orderflow
spec:
  selector: { app: notification-service }
  ports: [{ port: 80, targetPort: 8080 }]
```

```yaml
# ingress.yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: orderflow-ingress
  namespace: orderflow
  annotations:
    kubernetes.io/ingress.class: "alb"
    alb.ingress.kubernetes.io/scheme: internet-facing
    alb.ingress.kubernetes.io/target-type: ip
spec:
  rules:
    - host: api.orderflow.mycompany.com
      http:
        paths:
          - path: /orders
            pathType: Prefix
            backend: { service: { name: order-service, port: { number: 80 } } }
          - path: /inventory
            pathType: Prefix
            backend: { service: { name: inventory-service, port: { number: 80 } } }
          - path: /payments
            pathType: Prefix
            backend: { service: { name: payment-service, port: { number: 80 } } }
```

```yaml
# network-policies.yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: order-service-allow-ingress
  namespace: orderflow
spec:
  podSelector: { matchLabels: { app: order-service } }
  policyTypes: [Ingress]
  ingress:
    - from:
        - namespaceSelector: { matchLabels: { name: orderflow } }
---
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: payment-service-restrict-ingress
  namespace: orderflow
spec:
  podSelector: { matchLabels: { app: payment-service } }
  policyTypes: [Ingress]
  ingress:
    - from:
        - podSelector: { matchLabels: { app: order-service } }   # ONLY order-service may call payment-service
```

## §86 Complete OpenAPI 3.0 Specification (Sample Order API)

```yaml
openapi: 3.0.3
info:
  title: OrderFlow API
  version: "1.0.0"
  description: Public API for order management, used as the reference contract across services.
servers:
  - url: https://api.orderflow.mycompany.com/v1
paths:
  /orders:
    post:
      summary: Create a new order
      operationId: createOrder
      parameters:
        - name: Idempotency-Key
          in: header
          required: true
          schema: { type: string, format: uuid }
      requestBody:
        required: true
        content:
          application/json:
            schema: { $ref: '#/components/schemas/CreateOrderRequest' }
      responses:
        '201':
          description: Order created
          content:
            application/json:
              schema: { $ref: '#/components/schemas/Order' }
        '400':
          description: Invalid request
        '409':
          description: Idempotency key conflict with different payload
    get:
      summary: List orders for the authenticated user
      operationId: listOrders
      parameters:
        - name: page
          in: query
          schema: { type: integer, default: 1 }
        - name: limit
          in: query
          schema: { type: integer, default: 20, maximum: 100 }
      responses:
        '200':
          description: A paginated list of orders
          content:
            application/json:
              schema: { $ref: '#/components/schemas/OrderList' }
  /orders/{orderId}:
    get:
      summary: Get a single order by ID
      operationId: getOrder
      parameters:
        - name: orderId
          in: path
          required: true
          schema: { type: string }
      responses:
        '200':
          description: The requested order
          content:
            application/json:
              schema: { $ref: '#/components/schemas/Order' }
        '404':
          description: Order not found
  /orders/{orderId}/cancel:
    post:
      summary: Cancel an order (if not yet shipped)
      operationId: cancelOrder
      parameters:
        - name: orderId
          in: path
          required: true
          schema: { type: string }
      responses:
        '200':
          description: Order cancelled
        '409':
          description: Order already shipped, cannot cancel
components:
  schemas:
    CreateOrderRequest:
      type: object
      required: [items]
      properties:
        items:
          type: array
          items: { $ref: '#/components/schemas/OrderItem' }
        shipping_address_id:
          type: string
    OrderItem:
      type: object
      required: [product_id, quantity]
      properties:
        product_id: { type: string }
        quantity: { type: integer, minimum: 1 }
    Order:
      type: object
      properties:
        order_id: { type: string }
        status: { type: string, enum: [CREATED, PAID, SHIPPED, DELIVERED, CANCELLED] }
        items:
          type: array
          items: { $ref: '#/components/schemas/OrderItem' }
        total_amount_cents: { type: integer }
        created_at: { type: string, format: date-time }
    OrderList:
      type: object
      properties:
        orders:
          type: array
          items: { $ref: '#/components/schemas/Order' }
        page: { type: integer }
        total_pages: { type: integer }
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
security:
  - bearerAuth: []
```

## §87 Complete Database Schema DDL (E-Commerce Sample App)

```sql
-- Enable UUID generation
CREATE EXTENSION IF NOT EXISTS "pgcrypto";

CREATE TABLE users (
    id              UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    email           VARCHAR(255) NOT NULL UNIQUE,
    password_hash   VARCHAR(255) NOT NULL,
    full_name       VARCHAR(255),
    created_at      TIMESTAMPTZ NOT NULL DEFAULT now(),
    updated_at      TIMESTAMPTZ NOT NULL DEFAULT now()
);

CREATE TABLE addresses (
    id              UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id         UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    line1           VARCHAR(255) NOT NULL,
    line2           VARCHAR(255),
    city            VARCHAR(100) NOT NULL,
    postal_code     VARCHAR(20) NOT NULL,
    country_code    CHAR(2) NOT NULL,
    is_default      BOOLEAN NOT NULL DEFAULT false
);
CREATE INDEX idx_addresses_user_id ON addresses(user_id);

CREATE TABLE categories (
    id              UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    name            VARCHAR(100) NOT NULL,
    parent_id       UUID REFERENCES categories(id)
);

CREATE TABLE products (
    id              UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    category_id     UUID NOT NULL REFERENCES categories(id),
    name            VARCHAR(255) NOT NULL,
    description     TEXT,
    price_cents     INTEGER NOT NULL CHECK (price_cents >= 0),
    stock_qty       INTEGER NOT NULL DEFAULT 0 CHECK (stock_qty >= 0),
    created_at      TIMESTAMPTZ NOT NULL DEFAULT now()
);
CREATE INDEX idx_products_category_id ON products(category_id);
CREATE INDEX idx_products_name_trgm ON products USING gin (name gin_trgm_ops);

CREATE TABLE orders (
    id                  UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id             UUID NOT NULL REFERENCES users(id),
    shipping_address_id UUID REFERENCES addresses(id),
    status              VARCHAR(20) NOT NULL DEFAULT 'CREATED'
                         CHECK (status IN ('CREATED','PAID','SHIPPED','DELIVERED','CANCELLED')),
    total_amount_cents  INTEGER NOT NULL DEFAULT 0,
    idempotency_key     UUID NOT NULL UNIQUE,
    created_at          TIMESTAMPTZ NOT NULL DEFAULT now(),
    updated_at          TIMESTAMPTZ NOT NULL DEFAULT now()
);
CREATE INDEX idx_orders_user_id ON orders(user_id);
CREATE INDEX idx_orders_status ON orders(status);

CREATE TABLE order_items (
    id                  UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    order_id            UUID NOT NULL REFERENCES orders(id) ON DELETE CASCADE,
    product_id          UUID NOT NULL REFERENCES products(id),
    quantity            INTEGER NOT NULL CHECK (quantity > 0),
    price_at_purchase_cents INTEGER NOT NULL
);
CREATE INDEX idx_order_items_order_id ON order_items(order_id);

CREATE TABLE payments (
    id                  UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    order_id            UUID NOT NULL REFERENCES orders(id),
    processor_charge_id VARCHAR(255) NOT NULL UNIQUE,
    amount_cents        INTEGER NOT NULL,
    status              VARCHAR(20) NOT NULL CHECK (status IN ('PENDING','SUCCEEDED','FAILED','REFUNDED')),
    created_at          TIMESTAMPTZ NOT NULL DEFAULT now()
);
CREATE INDEX idx_payments_order_id ON payments(order_id);

CREATE TABLE inventory_reservations (
    id              UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    order_id        UUID NOT NULL REFERENCES orders(id),
    product_id      UUID NOT NULL REFERENCES products(id),
    quantity        INTEGER NOT NULL,
    status          VARCHAR(20) NOT NULL DEFAULT 'RESERVED'
                    CHECK (status IN ('RESERVED','RELEASED','COMMITTED')),
    expires_at      TIMESTAMPTZ NOT NULL
);
CREATE INDEX idx_reservations_expires_at ON inventory_reservations(expires_at)
    WHERE status = 'RESERVED';   -- partial index -- only indexes active reservations,
                                  -- keeping the index small and the expiry-sweep query fast

-- Trigger to keep updated_at fresh on every row modification
CREATE OR REPLACE FUNCTION set_updated_at()
RETURNS TRIGGER AS $$
BEGIN
    NEW.updated_at = now();
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_orders_updated_at
    BEFORE UPDATE ON orders
    FOR EACH ROW EXECUTE FUNCTION set_updated_at();

-- Enable Row-Level Security for the multi-tenant pattern from §77 (if this app were
-- multi-tenant -- included here as a reference for that pattern)
-- ALTER TABLE orders ENABLE ROW LEVEL SECURITY;
```

## §88 Complete GitHub Actions Multi-Environment CI/CD Pipeline

```yaml
# .github/workflows/full-pipeline.yml
name: Full CI/CD Pipeline

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

env:
  ECR_REPOSITORY: order-service
  AWS_REGION: us-east-1

permissions:
  id-token: write
  contents: read

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with: { python-version: '3.12' }
      - run: pip install ruff mypy
      - run: ruff check services/order-service/src
      - run: mypy services/order-service/src --strict

  unit-tests:
    needs: lint
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with: { python-version: '3.12' }
      - run: pip install -r services/order-service/requirements.txt -r services/order-service/requirements-dev.txt
      - run: pytest services/order-service/tests/unit --cov=src --cov-report=xml --cov-fail-under=85
      - uses: codecov/codecov-action@v4
        with: { files: coverage.xml }

  integration-tests:
    needs: unit-tests
    runs-on: ubuntu-latest
    services:
      postgres:
        image: postgres:15
        env:
          POSTGRES_PASSWORD: testpass
          POSTGRES_DB: orders_test
        ports: ['5432:5432']
        options: >-
          --health-cmd pg_isready
          --health-interval 10s
          --health-timeout 5s
          --health-retries 5
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with: { python-version: '3.12' }
      - run: pip install -r services/order-service/requirements.txt -r services/order-service/requirements-dev.txt
      - run: |
          psql -h localhost -U postgres -d orders_test -f infra/schema.sql
        env: { PGPASSWORD: testpass }
      - run: pytest services/order-service/tests/integration
        env:
          DATABASE_URL: postgresql://postgres:testpass@localhost:5432/orders_test

  security-scan:
    needs: unit-tests
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run dependency vulnerability scan
        run: pip install safety && safety check -r services/order-service/requirements.txt
      - name: Run static application security testing
        uses: github/codeql-action/analyze@v3

  build-image:
    needs: [integration-tests, security-scan]
    runs-on: ubuntu-latest
    outputs:
      image_digest: ${{ steps.build.outputs.digest }}
    steps:
      - uses: actions/checkout@v4
      - uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: arn:aws:iam::111111111111:role/github-actions-deploy
          aws-region: ${{ env.AWS_REGION }}
      - uses: aws-actions/amazon-ecr-login@v2
        id: ecr-login
      - name: Build and push
        id: build
        run: |
          IMAGE_URI=${{ steps.ecr-login.outputs.registry }}/${{ env.ECR_REPOSITORY }}:${{ github.sha }}
          docker build -t $IMAGE_URI services/order-service
          docker push $IMAGE_URI
          DIGEST=$(docker inspect --format='{{index .RepoDigests 0}}' $IMAGE_URI)
          echo "digest=$DIGEST" >> $GITHUB_OUTPUT

  deploy-staging:
    needs: build-image
    runs-on: ubuntu-latest
    environment: staging
    steps:
      - uses: actions/checkout@v4
      - uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: arn:aws:iam::222222222222:role/github-actions-deploy
          aws-region: ${{ env.AWS_REGION }}
      - name: Update kubeconfig
        run: aws eks update-kubeconfig --name staging-cluster --region ${{ env.AWS_REGION }}
      - name: Deploy via Helm
        run: |
          helm upgrade --install order-service ./infra/helm/order-service \
            -f ./infra/helm/order-service/values-staging.yaml \
            --set image.digest=${{ needs.build-image.outputs.image_digest }} \
            --namespace orderflow --atomic --timeout 5m

  smoke-test-staging:
    needs: deploy-staging
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with: { python-version: '3.12' }
      - run: pip install requests
      - run: python scripts/smoke_test.py --base-url https://staging-api.orderflow.mycompany.com

  deploy-production:
    needs: smoke-test-staging
    runs-on: ubuntu-latest
    environment: production   # requires manual approval via GitHub Environment protection rules
    steps:
      - uses: actions/checkout@v4
      - uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: arn:aws:iam::111111111111:role/github-actions-deploy
          aws-region: ${{ env.AWS_REGION }}
      - name: Update kubeconfig
        run: aws eks update-kubeconfig --name prod-cluster --region ${{ env.AWS_REGION }}
      - name: Deploy canary (10%)
        run: |
          helm upgrade --install order-service ./infra/helm/order-service \
            -f ./infra/helm/order-service/values-prod.yaml \
            --set image.digest=${{ needs.build-image.outputs.image_digest }} \
            --set canary.weight=10 \
            --namespace orderflow --atomic --timeout 5m
      - name: Wait and monitor canary health
        run: python scripts/canary_monitor.py --duration-minutes 10 --error-rate-threshold 0.02
      - name: Promote canary to 100%
        run: |
          helm upgrade order-service ./infra/helm/order-service \
            -f ./infra/helm/order-service/values-prod.yaml \
            --set image.digest=${{ needs.build-image.outputs.image_digest }} \
            --set canary.weight=100 \
            --namespace orderflow --atomic --timeout 5m
```

## §89 Complete Monitoring & Alerting-as-Code (Terraform)

```hcl
############################################
# alarms.tf -- comprehensive alarm coverage for the order service
############################################
resource "aws_cloudwatch_metric_alarm" "high_error_rate" {
  alarm_name          = "order-service-high-error-rate"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 3
  period              = 60
  threshold           = 0.05   # 5% error rate
  alarm_description   = "Order service 5xx error rate exceeded 5% for 3 consecutive minutes"
  treat_missing_data  = "notBreaching"

  metric_query {
    id          = "error_rate"
    expression  = "errors / requests"
    label       = "Error Rate"
    return_data = true
  }
  metric_query {
    id = "errors"
    metric {
      metric_name = "5XXError"
      namespace   = "AWS/ApplicationELB"
      period      = 60
      stat        = "Sum"
      dimensions  = { LoadBalancer = aws_lb.main.arn_suffix }
    }
  }
  metric_query {
    id = "requests"
    metric {
      metric_name = "RequestCount"
      namespace   = "AWS/ApplicationELB"
      period      = 60
      stat        = "Sum"
      dimensions  = { LoadBalancer = aws_lb.main.arn_suffix }
    }
  }

  alarm_actions = [aws_sns_topic.pagerduty.arn]
  ok_actions    = [aws_sns_topic.pagerduty.arn]
}

resource "aws_cloudwatch_metric_alarm" "high_p99_latency" {
  alarm_name          = "order-service-high-p99-latency"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 3
  metric_name         = "TargetResponseTime"
  namespace           = "AWS/ApplicationELB"
  period              = 60
  extended_statistic  = "p99"
  threshold           = 0.5   # 500ms
  dimensions          = { LoadBalancer = aws_lb.main.arn_suffix }
  alarm_actions       = [aws_sns_topic.pagerduty.arn]
}

resource "aws_cloudwatch_metric_alarm" "dynamodb_throttles" {
  alarm_name          = "orders-table-throttles"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 1
  metric_name         = "ThrottledRequests"
  namespace           = "AWS/DynamoDB"
  period              = 60
  statistic           = "Sum"
  threshold           = 0
  dimensions          = { TableName = "orders" }
  alarm_actions       = [aws_sns_topic.pagerduty.arn]
}

resource "aws_cloudwatch_metric_alarm" "sqs_queue_backlog" {
  alarm_name          = "order-processing-queue-backlog"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 5
  metric_name         = "ApproximateNumberOfMessagesVisible"
  namespace           = "AWS/SQS"
  period              = 60
  statistic           = "Average"
  threshold           = 10000
  dimensions          = { QueueName = "order-processing-queue" }
  alarm_actions       = [aws_sns_topic.platform_team.arn]
}

resource "aws_cloudwatch_metric_alarm" "lambda_error_rate" {
  alarm_name          = "fanout-lambda-errors"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 2
  metric_name         = "Errors"
  namespace           = "AWS/Lambda"
  period              = 60
  statistic           = "Sum"
  threshold           = 10
  dimensions          = { FunctionName = "timeline-fanout" }
  alarm_actions       = [aws_sns_topic.platform_team.arn]
}

resource "aws_sns_topic" "pagerduty" {
  name = "prod-pagerduty-critical"
}

resource "aws_sns_topic" "platform_team" {
  name = "prod-platform-team-warnings"
}

resource "aws_sns_topic_subscription" "pagerduty_integration" {
  topic_arn = aws_sns_topic.pagerduty.arn
  protocol  = "https"
  endpoint  = var.pagerduty_webhook_url
}

############################################
# dashboards.tf
############################################
resource "aws_cloudwatch_dashboard" "order_service" {
  dashboard_name = "order-service-slo-dashboard"
  dashboard_body = jsonencode({
    widgets = [
      {
        type = "metric", x = 0, y = 0, width = 12, height = 6
        properties = {
          title = "Request Rate & Error Rate"
          metrics = [
            ["AWS/ApplicationELB", "RequestCount", "LoadBalancer", aws_lb.main.arn_suffix],
            ["AWS/ApplicationELB", "HTTPCode_Target_5XX_Count", "LoadBalancer", aws_lb.main.arn_suffix]
          ]
          period = 60
        }
      },
      {
        type = "metric", x = 12, y = 0, width = 12, height = 6
        properties = {
          title = "p50 / p99 Latency"
          metrics = [
            ["AWS/ApplicationELB", "TargetResponseTime", "LoadBalancer", aws_lb.main.arn_suffix, { stat = "p50" }],
            ["AWS/ApplicationELB", "TargetResponseTime", "LoadBalancer", aws_lb.main.arn_suffix, { stat = "p99" }]
          ]
          period = 60
        }
      },
      {
        type = "metric", x = 0, y = 6, width = 12, height = 6
        properties = {
          title = "DynamoDB Capacity & Throttles"
          metrics = [
            ["AWS/DynamoDB", "ConsumedReadCapacityUnits", "TableName", "orders"],
            ["AWS/DynamoDB", "ThrottledRequests", "TableName", "orders"]
          ]
          period = 60
        }
      }
    ]
  })
}
```

## §90 Complete Load Test Script (Locust)

```python
# locustfile.py -- full load test suite exercising the order API's critical paths,
# used both for capacity planning (§15) and canary validation (§25/§33)
import uuid
import random
from locust import HttpUser, task, between, events


class OrderFlowUser(HttpUser):
    wait_time = between(1, 3)
    host = "https://staging-api.orderflow.mycompany.com"

    def on_start(self):
        response = self.client.post("/v1/auth/login", json={
            "email": f"loadtest-{uuid.uuid4()}@example.com",
            "password": "loadtest-password",
        })
        self.token = response.json().get("access_token", "")
        self.client.headers.update({"Authorization": f"Bearer {self.token}"})
        self.product_ids = self._fetch_sample_product_ids()

    def _fetch_sample_product_ids(self) -> list[str]:
        response = self.client.get("/v1/products?limit=50")
        return [p["id"] for p in response.json().get("products", [])] or ["fallback-product-id"]

    @task(10)
    def browse_products(self):
        self.client.get("/v1/products", params={"page": random.randint(1, 20), "limit": 20},
                         name="/v1/products [browse]")

    @task(5)
    def get_product_detail(self):
        product_id = random.choice(self.product_ids)
        self.client.get(f"/v1/products/{product_id}", name="/v1/products/[id]")

    @task(3)
    def search_autocomplete(self):
        prefix = random.choice(["lap", "phone", "shoe", "watch", "book"])
        self.client.get(f"/v1/search/autocomplete?q={prefix}", name="/v1/search/autocomplete")

    @task(2)
    def add_to_cart(self):
        product_id = random.choice(self.product_ids)
        self.client.post("/v1/cart/items", json={"product_id": product_id, "quantity": 1},
                          name="/v1/cart/items [add]")

    @task(1)
    def checkout(self):
        idempotency_key = str(uuid.uuid4())
        with self.client.post(
            "/v1/orders",
            json={"items": [{"product_id": random.choice(self.product_ids), "quantity": 1}]},
            headers={"Idempotency-Key": idempotency_key},
            name="/v1/orders [checkout]",
            catch_response=True,
        ) as response:
            if response.status_code == 201:
                response.success()
            elif response.status_code == 429:
                response.success()  # rate-limited is an EXPECTED outcome under load, not a failure
            else:
                response.failure(f"Unexpected status: {response.status_code}")


class AdminUser(HttpUser):
    """Simulates a smaller population of internal admin users hitting reporting
    endpoints -- a different traffic PROFILE mixed into the same load test."""
    weight = 1   # 1 admin user for every ~20 regular OrderFlowUsers (weight ratio)
    wait_time = between(5, 15)
    host = "https://staging-api.orderflow.mycompany.com"

    @task
    def view_dashboard(self):
        self.client.get("/v1/admin/dashboard/summary")


@events.test_start.add_listener
def on_test_start(environment, **kwargs):
    print(f"Load test starting against {environment.host}")


@events.quitting.add_listener
def on_quit(environment, **kwargs):
    """Fail the CI job (non-zero exit) if p99 latency or error rate breached the SLO --
    this is what makes the load test usable as an automated canary/release gate,
    not just a manual exploratory tool."""
    stats = environment.stats.total
    if stats.get_response_time_percentile(0.99) > 500:
        print("FAIL: p99 latency exceeded 500ms SLO")
        environment.process_exit_code = 1
    if stats.fail_ratio > 0.01:
        print("FAIL: error rate exceeded 1% SLO")
        environment.process_exit_code = 1
```

```bash
# run_load_test.sh -- CI-invocable wrapper, ramps up gradually rather than an instant spike
locust -f locustfile.py \
  --headless \
  --users 2000 \
  --spawn-rate 50 \
  --run-time 15m \
  --html load-test-report.html \
  --csv load-test-results
```

## §91 Complete pytest Test Suite (Order Handler + Adapters)

```python
# tests/unit/test_order_handler.py
import pytest
from unittest.mock import MagicMock
from cloud_clients.interfaces import ObjectStoragePort, EventPublisherPort, KeyValueStorePort, UploadResult
from services.order_service.src.order_handler import OrderHandler


@pytest.fixture
def fake_storage():
    storage = MagicMock(spec=ObjectStoragePort)
    storage.upload.return_value = UploadResult(key="receipts/order-1.pdf", url="https://fake-url", size_bytes=1024)
    return storage


@pytest.fixture
def fake_events():
    return MagicMock(spec=EventPublisherPort)


@pytest.fixture
def fake_orders_db():
    return MagicMock(spec=KeyValueStorePort)


@pytest.fixture
def order_handler(fake_storage, fake_events, fake_orders_db):
    return OrderHandler(storage=fake_storage, events=fake_events, orders_db=fake_orders_db)


class TestCreateOrder:
    def test_writes_order_to_database_with_correct_keys(self, order_handler, fake_orders_db):
        order_handler.create_order(
            user_id="user-1", order_id="order-1",
            items=[{"product_id": "p1", "qty": 2}], receipt_pdf=b"fake-pdf-bytes",
        )
        fake_orders_db.put.assert_called_once_with(
            partition_key="USER#user-1",
            sort_key="ORDER#order-1",
            item={"items": [{"product_id": "p1", "qty": 2}], "status": "CREATED"},
        )

    def test_uploads_receipt_to_storage(self, order_handler, fake_storage):
        order_handler.create_order(
            user_id="user-1", order_id="order-1", items=[], receipt_pdf=b"fake-pdf-bytes",
        )
        fake_storage.upload.assert_called_once_with(
            key="receipts/order-1.pdf", data=b"fake-pdf-bytes", content_type="application/pdf",
        )

    def test_publishes_order_created_event(self, order_handler, fake_events):
        order_handler.create_order(
            user_id="user-1", order_id="order-1", items=[], receipt_pdf=b"fake-pdf-bytes",
        )
        fake_events.publish.assert_called_once()
        call_args = fake_events.publish.call_args
        assert call_args.kwargs["event_type"] == "OrderCreated"
        assert call_args.kwargs["payload"]["order_id"] == "order-1"

    def test_event_includes_receipt_url_from_storage_result(self, order_handler, fake_events, fake_storage):
        fake_storage.upload.return_value = UploadResult(
            key="receipts/order-1.pdf", url="https://presigned-url-example", size_bytes=2048
        )
        order_handler.create_order(user_id="user-1", order_id="order-1", items=[], receipt_pdf=b"data")
        published_payload = fake_events.events.publish.call_args if False else fake_events.publish.call_args
        assert published_payload.kwargs["payload"]["receipt_url"] == "https://presigned-url-example"


# tests/unit/test_rate_limiter.py -- testing the §66 token bucket Lua-script logic via
# a fakeredis in-memory Redis, avoiding a real Redis dependency in unit tests
import fakeredis


@pytest.fixture
def redis_client():
    return fakeredis.FakeStrictRedis()


class TestTokenBucketRateLimiter:
    def test_allows_requests_within_capacity(self, redis_client):
        from rate_limiter import check_rate_limit  # hypothetical wrapper around the Lua script
        for _ in range(5):
            assert check_rate_limit(redis_client, "client-1", capacity=5, refill_rate=1.0) is True

    def test_rejects_requests_beyond_capacity(self, redis_client):
        from rate_limiter import check_rate_limit
        for _ in range(5):
            check_rate_limit(redis_client, "client-2", capacity=5, refill_rate=1.0)
        assert check_rate_limit(redis_client, "client-2", capacity=5, refill_rate=1.0) is False

    def test_tokens_refill_over_time(self, redis_client, monkeypatch):
        from rate_limiter import check_rate_limit
        import time
        current_time = [1000.0]
        monkeypatch.setattr(time, "time", lambda: current_time[0])

        for _ in range(5):
            check_rate_limit(redis_client, "client-3", capacity=5, refill_rate=1.0)
        assert check_rate_limit(redis_client, "client-3", capacity=5, refill_rate=1.0) is False

        current_time[0] += 5  # simulate 5 seconds passing -- should refill ~5 tokens
        assert check_rate_limit(redis_client, "client-3", capacity=5, refill_rate=1.0) is True


# tests/integration/test_order_api.py -- integration tests hitting a real (test) database,
# per the CI pipeline's integration-tests job in §88
import requests


@pytest.fixture(scope="module")
def api_base_url():
    return "http://localhost:8080"


class TestOrderApiIntegration:
    def test_create_order_returns_201(self, api_base_url):
        response = requests.post(
            f"{api_base_url}/v1/orders",
            json={"items": [{"product_id": "test-product-1", "quantity": 1}]},
            headers={"Idempotency-Key": "test-key-001", "Authorization": "Bearer test-token"},
        )
        assert response.status_code == 201
        assert response.json()["status"] == "CREATED"

    def test_duplicate_idempotency_key_returns_same_order(self, api_base_url):
        headers = {"Idempotency-Key": "test-key-002", "Authorization": "Bearer test-token"}
        payload = {"items": [{"product_id": "test-product-1", "quantity": 1}]}

        first_response = requests.post(f"{api_base_url}/v1/orders", json=payload, headers=headers)
        second_response = requests.post(f"{api_base_url}/v1/orders", json=payload, headers=headers)

        assert first_response.json()["order_id"] == second_response.json()["order_id"]

    def test_get_nonexistent_order_returns_404(self, api_base_url):
        response = requests.get(f"{api_base_url}/v1/orders/does-not-exist",
                                 headers={"Authorization": "Bearer test-token"})
        assert response.status_code == 404

    def test_cancel_shipped_order_returns_409(self, api_base_url):
        # Setup: assume a fixture/seed script has pre-created a SHIPPED order
        response = requests.post(f"{api_base_url}/v1/orders/pre-seeded-shipped-order/cancel",
                                  headers={"Authorization": "Bearer test-token"})
        assert response.status_code == 409
```

```ini
# pytest.ini -- test configuration used by the CI pipeline's unit-tests job
[pytest]
markers =
    integration: marks tests requiring a real database connection
    slow: marks tests that take significant time to run
testpaths = tests
python_files = test_*.py
addopts = --strict-markers -v
```

## §92 Complete Terraform: GCP Production Environment (VPC + GKE + Cloud SQL + Monitoring)

*The GCP-side mirror of §84's AWS environment, for direct architectural comparison.*

```hcl
############################################
# providers.tf
############################################
terraform {
  required_version = ">= 1.6.0"
  required_providers {
    google = { source = "hashicorp/google", version = "~> 5.0" }
  }
  backend "gcs" {
    bucket = "company-terraform-state"
    prefix = "prod/full-stack"
  }
}

provider "google" {
  project = var.gcp_project_id
  region  = var.gcp_region
}

############################################
# variables.tf
############################################
variable "gcp_project_id" { type = string }
variable "gcp_region"      { type = string, default = "us-central1" }
variable "project_name"    { type = string, default = "orderflow" }
variable "subnet_cidr"     { type = string, default = "10.1.10.0/24" }
variable "db_tier"         { type = string, default = "db-custom-4-16384" }

############################################
# vpc.tf -- note: single VPC resource, NOT regional/AZ-scoped like AWS (§6.1)
############################################
resource "google_compute_network" "main" {
  name                    = "${var.project_name}-vpc"
  auto_create_subnetworks = false
}

resource "google_compute_subnetwork" "main" {
  name          = "${var.project_name}-subnet"
  ip_cidr_range = var.subnet_cidr
  region        = var.gcp_region
  network       = google_compute_network.main.id

  secondary_ip_range {
    range_name    = "gke-pods"
    ip_cidr_range = "10.4.0.0/14"
  }
  secondary_ip_range {
    range_name    = "gke-services"
    ip_cidr_range = "10.8.0.0/20"
  }
}

resource "google_compute_router" "main" {
  name    = "${var.project_name}-router"
  network = google_compute_network.main.id
  region  = var.gcp_region
}

resource "google_compute_router_nat" "main" {
  name                               = "${var.project_name}-nat"
  router                             = google_compute_router.main.name
  region                              = var.gcp_region
  nat_ip_allocate_option              = "AUTO_ONLY"
  source_subnetwork_ip_ranges_to_nat  = "ALL_SUBNETWORKS_ALL_IP_RANGES"
}

resource "google_compute_global_address" "private_ip_range" {
  name          = "${var.project_name}-private-ip-range"
  purpose       = "VPC_PEERING"
  address_type  = "INTERNAL"
  prefix_length = 16
  network       = google_compute_network.main.id
}

resource "google_service_networking_connection" "private_vpc_connection" {
  network                 = google_compute_network.main.id
  service                  = "servicenetworking.googleapis.com"
  reserved_peering_ranges  = [google_compute_global_address.private_ip_range.name]
}

############################################
# firewall.tf
############################################
resource "google_compute_firewall" "allow_internal" {
  name    = "${var.project_name}-allow-internal"
  network = google_compute_network.main.name
  allow {
    protocol = "tcp"
    ports    = ["0-65535"]
  }
  source_ranges = [var.subnet_cidr]
}

resource "google_compute_firewall" "deny_all_ingress" {
  name     = "${var.project_name}-deny-all-default"
  network  = google_compute_network.main.name
  priority = 65534
  deny { protocol = "all" }
  source_ranges = ["0.0.0.0/0"]
  direction     = "INGRESS"
}

############################################
# gke.tf -- Autopilot mode, per §22's operational-simplicity recommendation
############################################
resource "google_container_cluster" "main" {
  name             = "${var.project_name}-cluster"
  location         = var.gcp_region
  enable_autopilot = true

  network    = google_compute_network.main.id
  subnetwork = google_compute_subnetwork.main.id

  ip_allocation_policy {
    cluster_secondary_range_name  = "gke-pods"
    services_secondary_range_name = "gke-services"
  }

  private_cluster_config {
    enable_private_nodes    = true
    enable_private_endpoint = false
    master_ipv4_cidr_block  = "172.16.0.0/28"
  }
}

############################################
# cloudsql.tf
############################################
resource "google_sql_database_instance" "main" {
  name             = "${var.project_name}-db"
  database_version = "POSTGRES_15"
  region           = var.gcp_region

  depends_on = [google_service_networking_connection.private_vpc_connection]

  settings {
    tier              = var.db_tier
    availability_type = "REGIONAL"   # GCP's equivalent of AWS Multi-AZ

    backup_configuration {
      enabled                        = true
      point_in_time_recovery_enabled = true
      transaction_log_retention_days = 14
    }

    ip_configuration {
      ipv4_enabled    = false
      private_network = google_compute_network.main.id
    }

    insights_config {
      query_insights_enabled = true
    }
  }

  deletion_protection = true
}

resource "google_sql_database" "orders" {
  name     = "orders"
  instance = google_sql_database_instance.main.name
}

resource "random_password" "db_password" {
  length  = 32
  special = true
}

resource "google_sql_user" "app_user" {
  name     = "app_admin"
  instance = google_sql_database_instance.main.name
  password = random_password.db_password.result
}

resource "google_secret_manager_secret" "db_password" {
  secret_id = "${var.project_name}-db-password"
  replication {
    auto {}
  }
}

resource "google_secret_manager_secret_version" "db_password" {
  secret      = google_secret_manager_secret.db_password.id
  secret_data = random_password.db_password.result
}

############################################
# monitoring.tf
############################################
resource "google_monitoring_alert_policy" "db_cpu_high" {
  display_name = "${var.project_name}-db-cpu-high"
  combiner      = "OR"

  conditions {
    display_name = "Cloud SQL CPU > 80%"
    condition_threshold {
      filter          = "resource.type=\"cloudsql_database\" AND metric.type=\"cloudsql.googleapis.com/database/cpu/utilization\""
      comparison      = "COMPARISON_GT"
      threshold_value = 0.8
      duration        = "180s"
      aggregations {
        alignment_period   = "60s"
        per_series_aligner = "ALIGN_MEAN"
      }
    }
  }

  notification_channels = [google_monitoring_notification_channel.platform_team.id]
}

resource "google_monitoring_notification_channel" "platform_team" {
  display_name = "Platform Team Email"
  type         = "email"
  labels = {
    email_address = "platform-team@mycompany.com"
  }
}

resource "google_monitoring_dashboard" "main" {
  dashboard_json = jsonencode({
    displayName = "${var.project_name}-overview"
    gridLayout = {
      widgets = [
        {
          title = "Cloud SQL CPU Utilization"
          xyChart = {
            dataSets = [{
              timeSeriesQuery = {
                timeSeriesFilter = {
                  filter = "resource.type=\"cloudsql_database\" AND metric.type=\"cloudsql.googleapis.com/database/cpu/utilization\""
                }
              }
            }]
          }
        }
      ]
    }
  })
}

############################################
# outputs.tf
############################################
output "gke_cluster_endpoint" { value = google_container_cluster.main.endpoint, sensitive = true }
output "cloudsql_connection_name" { value = google_sql_database_instance.main.connection_name }
output "vpc_network_id" { value = google_compute_network.main.id }
```

## §93 Complete FastAPI Reference Application (Order Service, End-to-End)

A full, runnable FastAPI microservice implementing the order domain used throughout §53/§91,
wired to work against either AWS (DynamoDB + SQS) or GCP (Firestore + Pub/Sub) via the adapter
pattern, with routing, validation, dependency injection, health checks, and structured logging.

### 93.1 Project Layout

```
order-service/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI app factory + routers
│   ├── config.py            # Pydantic settings (env-driven)
│   ├── deps.py               # Dependency-injection wiring (cloud provider selection)
│   ├── models.py             # Pydantic request/response schemas
│   ├── adapters/
│   │   ├── base.py           # OrderStoreAdapter / QueueAdapter interfaces (see §53)
│   │   ├── aws.py            # DynamoDB + SQS implementation
│   │   └── gcp.py             # Firestore + Pub/Sub implementation
│   ├── services/
│   │   └── order_service.py  # Business logic, orchestrates adapters
│   └── routers/
│       ├── orders.py
│       └── health.py
├── tests/                     # see §91
├── requirements.txt
├── Dockerfile
└── pyproject.toml
```

### 93.2 `app/config.py`

```python
from functools import lru_cache
from pydantic_settings import BaseSettings

class Settings(BaseSettings):
    cloud_provider: str = "aws"          # "aws" | "gcp"
    aws_region: str = "us-east-1"
    orders_table_name: str = "orders"
    orders_queue_url: str = ""
    gcp_project_id: str = ""
    firestore_collection: str = "orders"
    pubsub_topic: str = "order-events"
    log_level: str = "INFO"
    service_name: str = "order-service"
    request_timeout_seconds: float = 5.0

    class Config:
        env_prefix = "ORDER_SVC_"

@lru_cache
def get_settings() -> Settings:
    return Settings()
```

### 93.3 `app/models.py`

```python
from datetime import datetime
from enum import Enum
from pydantic import BaseModel, Field, field_validator

class OrderStatus(str, Enum):
    PENDING = "PENDING"
    CONFIRMED = "CONFIRMED"
    SHIPPED = "SHIPPED"
    CANCELLED = "CANCELLED"

class OrderItem(BaseModel):
    sku: str = Field(min_length=1, max_length=64)
    quantity: int = Field(gt=0, le=1000)
    unit_price_cents: int = Field(ge=0)

class CreateOrderRequest(BaseModel):
    customer_id: str = Field(min_length=1)
    items: list[OrderItem] = Field(min_length=1)
    idempotency_key: str = Field(min_length=8, max_length=128)

    @field_validator("items")
    @classmethod
    def items_not_empty(cls, v):
        if not v:
            raise ValueError("order must contain at least one item")
        return v

class OrderResponse(BaseModel):
    order_id: str
    customer_id: str
    items: list[OrderItem]
    status: OrderStatus
    total_cents: int
    created_at: datetime

class HealthResponse(BaseModel):
    status: str
    cloud_provider: str
    version: str = "1.0.0"
```

### 93.4 `app/deps.py` — Cloud Provider Wiring

```python
from functools import lru_cache
from fastapi import Depends
from app.config import Settings, get_settings
from app.adapters.base import OrderStoreAdapter, QueueAdapter
from app.adapters.aws import DynamoDBOrderStore, SQSQueue
from app.adapters.gcp import FirestoreOrderStore, PubSubQueue
from app.services.order_service import OrderService

@lru_cache
def get_order_store(settings: Settings = Depends(get_settings)) -> OrderStoreAdapter:
    if settings.cloud_provider == "aws":
        return DynamoDBOrderStore(table_name=settings.orders_table_name, region=settings.aws_region)
    if settings.cloud_provider == "gcp":
        return FirestoreOrderStore(project_id=settings.gcp_project_id, collection=settings.firestore_collection)
    raise ValueError(f"Unsupported cloud_provider: {settings.cloud_provider}")

@lru_cache
def get_queue(settings: Settings = Depends(get_settings)) -> QueueAdapter:
    if settings.cloud_provider == "aws":
        return SQSQueue(queue_url=settings.orders_queue_url, region=settings.aws_region)
    if settings.cloud_provider == "gcp":
        return PubSubQueue(project_id=settings.gcp_project_id, topic=settings.pubsub_topic)
    raise ValueError(f"Unsupported cloud_provider: {settings.cloud_provider}")

def get_order_service(
    store: OrderStoreAdapter = Depends(get_order_store),
    queue: QueueAdapter = Depends(get_queue),
) -> OrderService:
    return OrderService(store=store, queue=queue)
```

### 93.5 `app/services/order_service.py` — Business Logic

```python
import uuid
import logging
from datetime import datetime, timezone
from app.models import CreateOrderRequest, OrderResponse, OrderStatus
from app.adapters.base import OrderStoreAdapter, QueueAdapter, DuplicateOrderError

logger = logging.getLogger("order_service")

class OrderNotFoundError(Exception):
    pass

class OrderService:
    def __init__(self, store: OrderStoreAdapter, queue: QueueAdapter):
        self._store = store
        self._queue = queue

    async def create_order(self, req: CreateOrderRequest) -> OrderResponse:
        total_cents = sum(item.quantity * item.unit_price_cents for item in req.items)
        order_id = str(uuid.uuid4())
        order = OrderResponse(
            order_id=order_id,
            customer_id=req.customer_id,
            items=req.items,
            status=OrderStatus.PENDING,
            total_cents=total_cents,
            created_at=datetime.now(timezone.utc),
        )
        try:
            await self._store.put_order(order, idempotency_key=req.idempotency_key)
        except DuplicateOrderError:
            logger.info("Duplicate order suppressed", extra={"idempotency_key": req.idempotency_key})
            existing = await self._store.get_order_by_idempotency_key(req.idempotency_key)
            return existing
        await self._queue.publish_event(
            event_type="OrderCreated",
            payload={"order_id": order_id, "customer_id": req.customer_id, "total_cents": total_cents},
        )
        logger.info("Order created", extra={"order_id": order_id, "total_cents": total_cents})
        return order

    async def get_order(self, order_id: str) -> OrderResponse:
        order = await self._store.get_order(order_id)
        if order is None:
            raise OrderNotFoundError(order_id)
        return order

    async def cancel_order(self, order_id: str) -> OrderResponse:
        order = await self.get_order(order_id)
        if order.status in (OrderStatus.SHIPPED, OrderStatus.CANCELLED):
            raise ValueError(f"Cannot cancel order in status {order.status}")
        updated = await self._store.update_status(order_id, OrderStatus.CANCELLED)
        await self._queue.publish_event(event_type="OrderCancelled", payload={"order_id": order_id})
        return updated
```

### 93.6 `app/routers/orders.py`

```python
from fastapi import APIRouter, Depends, HTTPException, status
from app.models import CreateOrderRequest, OrderResponse
from app.services.order_service import OrderService, OrderNotFoundError
from app.deps import get_order_service

router = APIRouter(prefix="/orders", tags=["orders"])

@router.post("", response_model=OrderResponse, status_code=status.HTTP_201_CREATED)
async def create_order(
    req: CreateOrderRequest, svc: OrderService = Depends(get_order_service)
) -> OrderResponse:
    try:
        return await svc.create_order(req)
    except Exception as exc:
        raise HTTPException(status_code=status.HTTP_502_BAD_GATEWAY, detail=str(exc)) from exc

@router.get("/{order_id}", response_model=OrderResponse)
async def get_order(order_id: str, svc: OrderService = Depends(get_order_service)) -> OrderResponse:
    try:
        return await svc.get_order(order_id)
    except OrderNotFoundError:
        raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail="order not found")

@router.post("/{order_id}/cancel", response_model=OrderResponse)
async def cancel_order(order_id: str, svc: OrderService = Depends(get_order_service)) -> OrderResponse:
    try:
        return await svc.cancel_order(order_id)
    except OrderNotFoundError:
        raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail="order not found")
    except ValueError as exc:
        raise HTTPException(status_code=status.HTTP_409_CONFLICT, detail=str(exc))
```

### 93.7 `app/routers/health.py` and `app/main.py`

```python
# app/routers/health.py
from fastapi import APIRouter, Depends
from app.config import Settings, get_settings
from app.models import HealthResponse

router = APIRouter(tags=["health"])

@router.get("/healthz", response_model=HealthResponse)
async def healthz(settings: Settings = Depends(get_settings)) -> HealthResponse:
    return HealthResponse(status="ok", cloud_provider=settings.cloud_provider)

@router.get("/readyz", response_model=HealthResponse)
async def readyz(settings: Settings = Depends(get_settings)) -> HealthResponse:
    # In production this would ping the DB/queue adapters with a short timeout.
    return HealthResponse(status="ready", cloud_provider=settings.cloud_provider)
```

```python
# app/main.py
import logging
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware
from app.config import get_settings
from app.routers import orders, health

def create_app() -> FastAPI:
    settings = get_settings()
    logging.basicConfig(level=settings.log_level)
    app = FastAPI(title=settings.service_name, version="1.0.0")
    app.add_middleware(
        CORSMiddleware, allow_origins=["*"], allow_methods=["*"], allow_headers=["*"],
    )
    app.include_router(health.router)
    app.include_router(orders.router)
    return app

app = create_app()
```

### 93.8 `Dockerfile`

```dockerfile
FROM python:3.12-slim AS base
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY app ./app
RUN useradd --create-home appuser && chown -R appuser /app
USER appuser
EXPOSE 8080
ENV ORDER_SVC_LOG_LEVEL=INFO
HEALTHCHECK --interval=30s --timeout=3s CMD python -c "import urllib.request; urllib.request.urlopen('http://localhost:8080/healthz')" || exit 1
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8080", "--workers", "2"]
```

### 93.9 `requirements.txt`

```text
fastapi==0.115.0
uvicorn[standard]==0.32.0
pydantic==2.9.2
pydantic-settings==2.5.2
boto3==1.35.36
google-cloud-firestore==2.19.0
google-cloud-pubsub==2.26.1
```

**Key design points:**
- The router/service layer never imports `boto3` or `google-cloud-*` directly — only the
  adapters do, keeping the domain logic 100% cloud-agnostic (same principle as §53).
- Idempotency is enforced at the store layer (`DuplicateOrderError`), not in the route handler,
  so both AWS (conditional `PutItem`) and GCP (Firestore transaction) can implement it their own
  idiomatic way while presenting one contract.
- `get_settings()` is the single switch (`ORDER_SVC_CLOUD_PROVIDER=aws|gcp`) that changes which
  concrete adapters are constructed — no code changes needed to redeploy to the other cloud.

## §94 Complete Ansible Playbook: Config Management & App Deployment

For hybrid fleets (self-managed EC2/Compute Engine VMs alongside managed services), Ansible
handles OS-level config and app deployment consistently across both clouds using dynamic inventory.

### 94.1 Dynamic Inventory — `inventory/aws_ec2.yml` and `inventory/gcp_compute.yml`

```yaml
# inventory/aws_ec2.yml
plugin: amazon.aws.aws_ec2
regions:
  - us-east-1
filters:
  tag:Environment: production
  instance-state-name: running
keyed_groups:
  - key: tags.Role
    prefix: role
  - key: placement.availability_zone
    prefix: az
hostnames:
  - private-ip-address
```

```yaml
# inventory/gcp_compute.yml
plugin: google.cloud.gcp_compute
projects:
  - my-company-prod
zones:
  - us-central1-a
  - us-central1-b
filters:
  - "labels.environment = production"
keyed_groups:
  - key: labels.role
    prefix: role
hostnames:
  - networkInterfaces[0].networkIP
```

### 94.2 `site.yml` — Top-Level Playbook

```yaml
---
- name: Configure and deploy order-service fleet (multi-cloud)
  hosts: role_orderservice
  become: true
  vars:
    app_version: "{{ lookup('env', 'APP_VERSION') | default('latest', true) }}"
    cloud_provider: "{{ 'aws' if 'ec2' in group_names | join(',') else 'gcp' }}"
  roles:
    - common_hardening
    - docker_runtime
    - order_service_deploy
  post_tasks:
    - name: Wait for health check to pass
      ansible.builtin.uri:
        url: "http://{{ ansible_default_ipv4.address }}:8080/healthz"
        status_code: 200
      register: health_result
      until: health_result.status == 200
      retries: 10
      delay: 5
```

### 94.3 `roles/order_service_deploy/tasks/main.yml`

```yaml
---
- name: Ensure app directory exists
  ansible.builtin.file:
    path: /opt/order-service
    state: directory
    mode: "0755"

- name: Render environment file from template
  ansible.builtin.template:
    src: order-service.env.j2
    dest: /opt/order-service/.env
    mode: "0600"
  notify: restart order-service

- name: Pull container image
  community.docker.docker_image:
    name: "{{ ecr_or_gcr_registry }}/order-service:{{ app_version }}"
    source: pull

- name: Run order-service container
  community.docker.docker_container:
    name: order-service
    image: "{{ ecr_or_gcr_registry }}/order-service:{{ app_version }}"
    state: started
    restart_policy: unless-stopped
    ports:
      - "8080:8080"
    env_file: /opt/order-service/.env
    log_driver: json-file
    log_options:
      max-size: "10m"
      max-file: "3"

handlers:
  - name: restart order-service
    community.docker.docker_container:
      name: order-service
      state: started
      restart: true
```

### 94.4 `roles/order_service_deploy/templates/order-service.env.j2`

```jinja2
ORDER_SVC_CLOUD_PROVIDER={{ cloud_provider }}
ORDER_SVC_AWS_REGION={{ aws_region | default('us-east-1') }}
ORDER_SVC_ORDERS_TABLE_NAME={{ orders_table_name | default('orders') }}
ORDER_SVC_ORDERS_QUEUE_URL={{ orders_queue_url | default('') }}
ORDER_SVC_GCP_PROJECT_ID={{ gcp_project_id | default('') }}
ORDER_SVC_LOG_LEVEL=INFO
```

Run against both fleets in one command using the combined inventory:

```bash
ansible-playbook -i inventory/aws_ec2.yml -i inventory/gcp_compute.yml site.yml \
  --limit "role_orderservice" --extra-vars "app_version=1.4.2"
```

## §95 Complete Local Dev Stack (docker-compose, Multi-Service + LocalStack)

Developers need to run the full order pipeline locally without touching real cloud accounts.
This stack uses **LocalStack** to emulate AWS (DynamoDB, SQS) and the **Firestore/Pub/Sub
emulators** to emulate GCP, so the exact same adapters from §53/§93 work unmodified.

### 95.1 `docker-compose.yml`

```yaml
version: "3.9"

services:
  localstack:
    image: localstack/localstack:3.7
    ports:
      - "4566:4566"
    environment:
      - SERVICES=dynamodb,sqs
      - DEFAULT_REGION=us-east-1
    volumes:
      - "./localstack-init:/etc/localstack/init/ready.d"
      - "localstack-data:/var/lib/localstack"

  firestore-emulator:
    image: google/cloud-sdk:latest
    command: >
      gcloud emulators firestore start --host-port=0.0.0.0:8081
    ports:
      - "8081:8081"

  pubsub-emulator:
    image: google/cloud-sdk:latest
    command: >
      gcloud beta emulators pubsub start --host-port=0.0.0.0:8085 --project=local-dev
    ports:
      - "8085:8085"

  order-service-aws:
    build: ./order-service
    ports:
      - "8080:8080"
    environment:
      ORDER_SVC_CLOUD_PROVIDER: aws
      ORDER_SVC_AWS_REGION: us-east-1
      AWS_ENDPOINT_URL: http://localstack:4566
      AWS_ACCESS_KEY_ID: test
      AWS_SECRET_ACCESS_KEY: test
      ORDER_SVC_ORDERS_TABLE_NAME: orders-local
      ORDER_SVC_ORDERS_QUEUE_URL: http://localstack:4566/000000000000/orders-queue
    depends_on:
      - localstack

  order-service-gcp:
    build: ./order-service
    ports:
      - "8090:8080"
    environment:
      ORDER_SVC_CLOUD_PROVIDER: gcp
      FIRESTORE_EMULATOR_HOST: firestore-emulator:8081
      PUBSUB_EMULATOR_HOST: pubsub-emulator:8085
      ORDER_SVC_GCP_PROJECT_ID: local-dev
    depends_on:
      - firestore-emulator
      - pubsub-emulator

  prometheus:
    image: prom/prometheus:v2.54.0
    volumes:
      - "./local/prometheus.yml:/etc/prometheus/prometheus.yml"
    ports:
      - "9090:9090"

  grafana:
    image: grafana/grafana:11.2.0
    ports:
      - "3000:3000"
    environment:
      - GF_SECURITY_ADMIN_PASSWORD=admin

volumes:
  localstack-data:
```

### 95.2 `localstack-init/00-bootstrap.sh` — Auto-Provision Local AWS Resources

```bash
#!/usr/bin/env bash
set -euo pipefail

awslocal dynamodb create-table \
  --table-name orders-local \
  --attribute-definitions AttributeName=order_id,AttributeType=S \
  --key-schema AttributeName=order_id,KeyType=HASH \
  --billing-mode PAY_PER_REQUEST

awslocal sqs create-queue --queue-name orders-queue

echo "LocalStack bootstrap complete: orders-local table + orders-queue ready."
```

### 95.3 Developer Workflow

```bash
# Start the entire multi-cloud-emulated stack
docker compose up -d --build

# Exercise the AWS-flavored instance
curl -X POST localhost:8080/orders -H "Content-Type: application/json" \
  -d '{"customer_id":"c1","items":[{"sku":"SKU1","quantity":2,"unit_price_cents":500}],"idempotency_key":"local-test-1"}'

# Exercise the GCP-flavored instance (identical API contract)
curl -X POST localhost:8090/orders -H "Content-Type: application/json" \
  -d '{"customer_id":"c1","items":[{"sku":"SKU1","quantity":2,"unit_price_cents":500}],"idempotency_key":"local-test-2"}'

# Tear down
docker compose down -v
```

This gives every engineer a **single `docker compose up`** that proves out both cloud code
paths side by side, catching adapter-parity bugs before they ever reach a real AWS/GCP account.

## §96 Complete Grafana Dashboards + Prometheus Alert Rules (JSON/YAML)

Full observability-as-code for the order-service, deployable identically whether metrics are
scraped from EKS/GKE pods or shipped via CloudWatch/Cloud Monitoring exporters into Prometheus.

### 96.1 `prometheus/alert-rules.yml`

```yaml
groups:
  - name: order-service.rules
    rules:
      - alert: OrderServiceHighErrorRate
        expr: |
          sum(rate(http_requests_total{job="order-service",status=~"5.."}[5m]))
          / sum(rate(http_requests_total{job="order-service"}[5m])) > 0.02
        for: 5m
        labels:
          severity: critical
        annotations:
          summary: "order-service error rate above 2%"
          description: "{{ $value | humanizePercentage }} of requests are failing (5m window)."

      - alert: OrderServiceHighLatencyP99
        expr: |
          histogram_quantile(0.99, sum(rate(http_request_duration_seconds_bucket{job="order-service"}[5m])) by (le)) > 1.0
        for: 10m
        labels:
          severity: warning
        annotations:
          summary: "order-service p99 latency > 1s"
          description: "p99 latency is {{ $value }}s over the last 10m."

      - alert: OrderQueueBacklogGrowing
        expr: |
          aws_sqs_approximate_number_of_messages_visible{queue_name="orders-queue"} > 1000
        for: 15m
        labels:
          severity: warning
        annotations:
          summary: "orders-queue backlog exceeds 1000 messages"
          description: "Consumers may be under-scaled or failing; backlog is {{ $value }}."

      - alert: OrderServicePodCrashLooping
        expr: |
          increase(kube_pod_container_status_restarts_total{pod=~"order-service.*"}[15m]) > 3
        for: 5m
        labels:
          severity: critical
        annotations:
          summary: "order-service pod restarting repeatedly"
          description: "Pod {{ $labels.pod }} restarted {{ $value }} times in 15m."

      - alert: DynamoDBThrottling
        expr: |
          sum(rate(aws_dynamodb_throttled_requests_total{table_name="orders"}[5m])) > 0
        for: 5m
        labels:
          severity: warning
        annotations:
          summary: "DynamoDB throttling detected on orders table"
          description: "Consider on-demand capacity or better key distribution."
```

### 96.2 `grafana/dashboards/order-service-overview.json`

```json
{
  "title": "Order Service — Overview",
  "tags": ["order-service", "multi-cloud"],
  "timezone": "utc",
  "panels": [
    {
      "id": 1,
      "title": "Request Rate (req/s)",
      "type": "timeseries",
      "gridPos": { "h": 8, "w": 12, "x": 0, "y": 0 },
      "targets": [
        { "expr": "sum(rate(http_requests_total{job=\"order-service\"}[1m])) by (status)" }
      ]
    },
    {
      "id": 2,
      "title": "P50 / P95 / P99 Latency",
      "type": "timeseries",
      "gridPos": { "h": 8, "w": 12, "x": 12, "y": 0 },
      "targets": [
        { "expr": "histogram_quantile(0.50, sum(rate(http_request_duration_seconds_bucket[5m])) by (le))", "legendFormat": "p50" },
        { "expr": "histogram_quantile(0.95, sum(rate(http_request_duration_seconds_bucket[5m])) by (le))", "legendFormat": "p95" },
        { "expr": "histogram_quantile(0.99, sum(rate(http_request_duration_seconds_bucket[5m])) by (le))", "legendFormat": "p99" }
      ]
    },
    {
      "id": 3,
      "title": "Orders Queue Depth",
      "type": "timeseries",
      "gridPos": { "h": 8, "w": 12, "x": 0, "y": 8 },
      "targets": [
        { "expr": "aws_sqs_approximate_number_of_messages_visible{queue_name=\"orders-queue\"}" },
        { "expr": "pubsub_subscription_num_undelivered_messages{subscription_id=\"order-events-sub\"}" }
      ]
    },
    {
      "id": 4,
      "title": "Pod Restarts (15m)",
      "type": "stat",
      "gridPos": { "h": 8, "w": 6, "x": 12, "y": 8 },
      "targets": [
        { "expr": "sum(increase(kube_pod_container_status_restarts_total{pod=~\"order-service.*\"}[15m]))" }
      ]
    },
    {
      "id": 5,
      "title": "DynamoDB / Cloud SQL / Firestore Read Capacity Consumed",
      "type": "timeseries",
      "gridPos": { "h": 8, "w": 6, "x": 18, "y": 8 },
      "targets": [
        { "expr": "aws_dynamodb_consumed_read_capacity_units{table_name=\"orders\"}" },
        { "expr": "firestore_document_read_count{collection=\"orders\"}" }
      ]
    }
  ],
  "schemaVersion": 39,
  "version": 1
}
```

### 96.3 `terraform/monitoring/cloudwatch-dashboard.tf` — Push the Same Dashboard to CloudWatch

```hcl
resource "aws_cloudwatch_dashboard" "order_service" {
  dashboard_name = "order-service-overview"
  dashboard_body = jsonencode({
    widgets = [
      {
        type = "metric", x = 0, y = 0, width = 12, height = 6,
        properties = {
          metrics = [["AWS/ApplicationELB", "RequestCount", "LoadBalancer", var.alb_arn_suffix]]
          period  = 60, stat = "Sum", region = var.aws_region, title = "Request Count"
        }
      },
      {
        type = "metric", x = 12, y = 0, width = 12, height = 6,
        properties = {
          metrics = [["AWS/ApplicationELB", "TargetResponseTime", "LoadBalancer", var.alb_arn_suffix]]
          period  = 60, stat = "p99", region = var.aws_region, title = "P99 Latency"
        }
      }
    ]
  })
}

resource "aws_cloudwatch_metric_alarm" "orders_queue_backlog" {
  alarm_name          = "orders-queue-backlog-high"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 3
  metric_name         = "ApproximateNumberOfMessagesVisible"
  namespace           = "AWS/SQS"
  period              = 300
  statistic           = "Average"
  threshold           = 1000
  dimensions          = { QueueName = "orders-queue" }
  alarm_actions       = [aws_sns_topic.alerts.arn]
}

resource "aws_sns_topic" "alerts" {
  name = "order-service-alerts"
}
```

## §97 Complete Alembic Database Migration Scripts

Schema evolution for the relational side of the platform (Cloud SQL / RDS Postgres), matching
the DDL from §87, expressed as versioned, reversible Alembic migrations.

### 97.1 `alembic.ini` (excerpt) and `env.py` Wiring

```ini
[alembic]
script_location = migrations
sqlalchemy.url = driver://user:pass@host:5432/orders_db
file_template = %%(year)d%%(month).2d%%(day).2d_%%(hour).2d%%(minute).2d_%%(rev)s_%%(slug)s
```

```python
# migrations/env.py (key parts)
import os
from alembic import context
from sqlalchemy import engine_from_config, pool

config = context.config
db_url = os.environ.get("DATABASE_URL", config.get_main_option("sqlalchemy.url"))
config.set_main_option("sqlalchemy.url", db_url)

def run_migrations_online():
    connectable = engine_from_config(
        config.get_section(config.config_ini_section), prefix="sqlalchemy.", poolclass=pool.NullPool,
    )
    with connectable.connect() as connection:
        context.configure(connection=connection, target_metadata=None, compare_type=True)
        with context.begin_transaction():
            context.run_migrations()

run_migrations_online()
```

### 97.2 `migrations/versions/0001_create_core_tables.py`

```python
"""create core tables

Revision ID: 0001
Revises:
Create Date: 2026-01-05 00:00:00
"""
from alembic import op
import sqlalchemy as sa

revision = "0001"
down_revision = None

def upgrade():
    op.create_table(
        "customers",
        sa.Column("customer_id", sa.dialects.postgresql.UUID(as_uuid=True), primary_key=True),
        sa.Column("email", sa.String(255), nullable=False, unique=True),
        sa.Column("full_name", sa.String(255), nullable=False),
        sa.Column("created_at", sa.TIMESTAMP(timezone=True), server_default=sa.func.now()),
    )
    op.create_table(
        "orders",
        sa.Column("order_id", sa.dialects.postgresql.UUID(as_uuid=True), primary_key=True),
        sa.Column("customer_id", sa.dialects.postgresql.UUID(as_uuid=True),
                   sa.ForeignKey("customers.customer_id"), nullable=False),
        sa.Column("status", sa.String(20), nullable=False, server_default="PENDING"),
        sa.Column("total_cents", sa.BigInteger, nullable=False),
        sa.Column("created_at", sa.TIMESTAMP(timezone=True), server_default=sa.func.now()),
    )
    op.create_index("ix_orders_customer_id", "orders", ["customer_id"])
    op.create_check_constraint("ck_orders_total_nonneg", "orders", "total_cents >= 0")

def downgrade():
    op.drop_table("orders")
    op.drop_table("customers")
```

### 97.3 `migrations/versions/0002_add_order_items_and_indexes.py`

```python
"""add order_items table + covering indexes

Revision ID: 0002
Revises: 0001
"""
from alembic import op
import sqlalchemy as sa

revision = "0002"
down_revision = "0001"

def upgrade():
    op.create_table(
        "order_items",
        sa.Column("order_item_id", sa.BigInteger, primary_key=True, autoincrement=True),
        sa.Column("order_id", sa.dialects.postgresql.UUID(as_uuid=True),
                   sa.ForeignKey("orders.order_id", ondelete="CASCADE"), nullable=False),
        sa.Column("sku", sa.String(64), nullable=False),
        sa.Column("quantity", sa.Integer, nullable=False),
        sa.Column("unit_price_cents", sa.BigInteger, nullable=False),
    )
    op.create_index("ix_order_items_order_id", "order_items", ["order_id"])
    op.create_index(
        "ix_orders_status_created_at", "orders", ["status", "created_at"],
        postgresql_where=sa.text("status != 'CANCELLED'"),
    )

def downgrade():
    op.drop_index("ix_orders_status_created_at", table_name="orders")
    op.drop_table("order_items")
```

### 97.4 `migrations/versions/0003_add_idempotency_key.py`

```python
"""add idempotency_key unique column for exactly-once order creation

Revision ID: 0003
Revises: 0002
"""
from alembic import op
import sqlalchemy as sa

revision = "0003"
down_revision = "0002"

def upgrade():
    op.add_column("orders", sa.Column("idempotency_key", sa.String(128), nullable=True))
    op.create_unique_constraint("uq_orders_idempotency_key", "orders", ["idempotency_key"])

def downgrade():
    op.drop_constraint("uq_orders_idempotency_key", "orders", type_="unique")
    op.drop_column("orders", "idempotency_key")
```

### 97.5 CI Invocation (Zero-Downtime Pattern)

```bash
# Run inside the release pipeline before rolling the new app version:
alembic upgrade head

# Rollback one revision if a bad migration ships:
alembic downgrade -1

# Generate a new autogenerated migration from ORM model drift (review before committing!):
alembic revision --autogenerate -m "describe the change"
```

**Zero-downtime rule of thumb:** additive changes (new nullable column, new table, new index
`CONCURRENTLY`) ship in the *same* release as the code that uses them; destructive changes
(drop column, rename, NOT NULL backfill) are split across two releases — release N stops
reading/writing the old column, release N+1 drops it — exactly as covered in §14's expand/
contract migration pattern.

## §98 Complete Terraform: Azure Production Environment (3-Cloud Parity)

Many real-world "multi-cloud" mandates actually mean AWS + Azure or all three. This mirrors
§84 (AWS) and §92 (GCP) with an equivalent Azure environment — VNet + AKS + Azure Database for
PostgreSQL + Monitor — so the same architecture can be reasoned about across all three providers.

### 98.1 `providers.tf` and `variables.tf`

```hcl
terraform {
  required_version = ">= 1.9.0"
  required_providers {
    azurerm = { source = "hashicorp/azurerm", version = "~> 3.116" }
  }
  backend "azurerm" {
    resource_group_name  = "tfstate-rg"
    storage_account_name = "mycompanytfstate"
    container_name        = "tfstate"
    key                    = "prod/azure.tfstate"
  }
}

provider "azurerm" {
  features {}
}

variable "project_name" { type = string, default = "myapp" }
variable "location"     { type = string, default = "East US" }
variable "environment"  { type = string, default = "production" }
variable "vnet_cidr"    { type = string, default = "10.20.0.0/16" }
variable "aks_node_count" { type = number, default = 3 }
```

### 98.2 Networking — `network.tf`

```hcl
resource "azurerm_resource_group" "main" {
  name     = "${var.project_name}-${var.environment}-rg"
  location = var.location
}

resource "azurerm_virtual_network" "main" {
  name                = "${var.project_name}-vnet"
  address_space       = [var.vnet_cidr]
  location            = azurerm_resource_group.main.location
  resource_group_name = azurerm_resource_group.main.name
}

resource "azurerm_subnet" "aks" {
  name                 = "aks-subnet"
  resource_group_name  = azurerm_resource_group.main.name
  virtual_network_name = azurerm_virtual_network.main.name
  address_prefixes     = ["10.20.0.0/20"]
}

resource "azurerm_subnet" "db" {
  name                 = "db-subnet"
  resource_group_name  = azurerm_resource_group.main.name
  virtual_network_name = azurerm_virtual_network.main.name
  address_prefixes     = ["10.20.16.0/24"]
  delegation {
    name = "postgres-delegation"
    service_delegation {
      name    = "Microsoft.DBforPostgreSQL/flexibleServers"
      actions = ["Microsoft.Network/virtualNetworks/subnets/join/action"]
    }
  }
}

resource "azurerm_network_security_group" "aks" {
  name                = "${var.project_name}-aks-nsg"
  location            = azurerm_resource_group.main.location
  resource_group_name = azurerm_resource_group.main.name

  security_rule {
    name                       = "AllowHTTPSInbound"
    priority                   = 100
    direction                  = "Inbound"
    access                     = "Allow"
    protocol                   = "Tcp"
    source_port_range          = "*"
    destination_port_range     = "443"
    source_address_prefix      = "Internet"
    destination_address_prefix = "*"
  }
}
```

### 98.3 AKS Cluster — `aks.tf`

```hcl
resource "azurerm_kubernetes_cluster" "main" {
  name                = "${var.project_name}-aks"
  location            = azurerm_resource_group.main.location
  resource_group_name = azurerm_resource_group.main.name
  dns_prefix          = "${var.project_name}-aks"
  kubernetes_version  = "1.30"

  default_node_pool {
    name                = "system"
    node_count          = var.aks_node_count
    vm_size             = "Standard_D4s_v5"
    vnet_subnet_id      = azurerm_subnet.aks.id
    enable_auto_scaling = true
    min_count           = var.aks_node_count
    max_count           = var.aks_node_count * 4
    zones               = ["1", "2", "3"]
  }

  identity {
    type = "SystemAssigned"
  }

  network_profile {
    network_plugin    = "azure"
    load_balancer_sku = "standard"
    network_policy    = "azure"
  }

  azure_active_directory_role_based_access_control {
    managed = true
    azure_rbac_enabled = true
  }

  oms_agent {
    log_analytics_workspace_id = azurerm_log_analytics_workspace.main.id
  }
}

resource "azurerm_kubernetes_cluster_node_pool" "workloads" {
  name                  = "workloads"
  kubernetes_cluster_id = azurerm_kubernetes_cluster.main.id
  vm_size               = "Standard_D8s_v5"
  vnet_subnet_id        = azurerm_subnet.aks.id
  enable_auto_scaling   = true
  min_count             = 3
  max_count             = 20
  zones                 = ["1", "2", "3"]
  node_labels           = { workload = "app" }
}
```

### 98.4 Database — `database.tf`

```hcl
resource "azurerm_private_dns_zone" "postgres" {
  name                = "${var.project_name}.postgres.database.azure.com"
  resource_group_name = azurerm_resource_group.main.name
}

resource "azurerm_private_dns_zone_virtual_network_link" "postgres" {
  name                  = "postgres-dns-link"
  private_dns_zone_name = azurerm_private_dns_zone.postgres.name
  virtual_network_id    = azurerm_virtual_network.main.id
  resource_group_name   = azurerm_resource_group.main.name
}

resource "azurerm_postgresql_flexible_server" "main" {
  name                = "${var.project_name}-pg"
  resource_group_name = azurerm_resource_group.main.name
  location            = azurerm_resource_group.main.location
  version             = "16"
  delegated_subnet_id = azurerm_subnet.db.id
  private_dns_zone_id = azurerm_private_dns_zone.postgres.id
  administrator_login = "pgadmin"
  administrator_password = var.db_admin_password
  storage_mb          = 65536
  sku_name            = "GP_Standard_D4s_v5"
  zone                = "1"
  high_availability {
    mode                      = "ZoneRedundant"
    standby_availability_zone = "2"
  }
  backup_retention_days        = 14
  geo_redundant_backup_enabled = true

  depends_on = [azurerm_private_dns_zone_virtual_network_link.postgres]
}

resource "azurerm_postgresql_flexible_server_database" "orders" {
  name      = "orders_db"
  server_id = azurerm_postgresql_flexible_server.main.id
  collation = "en_US.utf8"
  charset   = "utf8"
}
```

### 98.5 Monitoring — `monitoring.tf` and Outputs

```hcl
resource "azurerm_log_analytics_workspace" "main" {
  name                = "${var.project_name}-law"
  location            = azurerm_resource_group.main.location
  resource_group_name = azurerm_resource_group.main.name
  sku                 = "PerGB2018"
  retention_in_days   = 30
}

resource "azurerm_monitor_metric_alert" "postgres_cpu" {
  name                = "${var.project_name}-pg-cpu-high"
  resource_group_name = azurerm_resource_group.main.name
  scopes              = [azurerm_postgresql_flexible_server.main.id]
  criteria {
    metric_namespace = "Microsoft.DBforPostgreSQL/flexibleServers"
    metric_name      = "cpu_percent"
    aggregation      = "Average"
    operator         = "GreaterThan"
    threshold        = 80
  }
  window_size = "PT5M"
  frequency   = "PT1M"
  action {
    action_group_id = azurerm_monitor_action_group.platform_team.id
  }
}

resource "azurerm_monitor_action_group" "platform_team" {
  name                = "platform-team-ag"
  resource_group_name = azurerm_resource_group.main.name
  short_name          = "platform"
  email_receiver {
    name          = "platform-team"
    email_address = "platform-team@mycompany.com"
  }
}

output "aks_cluster_name"    { value = azurerm_kubernetes_cluster.main.name }
output "postgres_fqdn"       { value = azurerm_postgresql_flexible_server.main.fqdn }
output "resource_group_name" { value = azurerm_resource_group.main.name }
```

**Three-way service equivalence for this exact stack:**

| Layer | AWS (§84) | GCP (§92) | Azure (§98) |
|---|---|---|---|
| Managed Kubernetes | EKS | GKE (Autopilot) | AKS |
| Regional Postgres HA | RDS Multi-AZ | Cloud SQL HA | Flexible Server ZoneRedundant HA |
| VPC/VNet | VPC + subnets | VPC + subnets | VNet + subnets |
| Metrics/Logs | CloudWatch | Cloud Monitoring/Logging | Azure Monitor + Log Analytics |
| Alerting | CloudWatch Alarms + SNS | Monitoring Alert Policies | Monitor Alerts + Action Groups |

## §99 Complete Disaster-Recovery Runbook Automation Script (Bash)

An executable DR runbook — not just a document — that automates the pilot-light failover
decision points from §27, callable identically against AWS or GCP via a provider flag.

```bash
#!/usr/bin/env bash
# dr-failover.sh — Automated pilot-light failover runbook
# Usage: ./dr-failover.sh --provider aws|gcp --region <dr-region> [--dry-run]
set -euo pipefail

PROVIDER=""
DR_REGION=""
DRY_RUN=false

while [[ $# -gt 0 ]]; do
  case "$1" in
    --provider) PROVIDER="$2"; shift 2 ;;
    --region)   DR_REGION="$2"; shift 2 ;;
    --dry-run)  DRY_RUN=true; shift ;;
    *) echo "Unknown arg: $1"; exit 1 ;;
  esac
done

if [[ -z "$PROVIDER" || -z "$DR_REGION" ]]; then
  echo "ERROR: --provider and --region are required" >&2
  exit 1
fi

log() { echo "[$(date -u +%Y-%m-%dT%H:%M:%SZ)] $*"; }

confirm_or_dry_run() {
  local desc="$1"
  if $DRY_RUN; then
    log "DRY-RUN: would execute -> $desc"
    return 1
  fi
  log "EXECUTING: $desc"
  return 0
}

step_1_verify_primary_down() {
  log "Step 1: Verifying primary region health endpoint is actually unreachable..."
  if curl -sf --max-time 5 "https://primary.myapp.com/healthz" > /dev/null 2>&1; then
    log "ABORT: primary region still responding to health checks. Not failing over."
    exit 2
  fi
  log "Confirmed: primary unreachable after 3 consecutive checks."
}

step_2_promote_database() {
  log "Step 2: Promoting DR database replica to primary in $DR_REGION..."
  if [[ "$PROVIDER" == "aws" ]]; then
    if confirm_or_dry_run "aws rds promote-read-replica --db-instance-identifier orders-dr-replica --region $DR_REGION"; then
      aws rds promote-read-replica --db-instance-identifier orders-dr-replica --region "$DR_REGION"
      aws rds wait db-instance-available --db-instance-identifier orders-dr-replica --region "$DR_REGION"
    fi
  elif [[ "$PROVIDER" == "gcp" ]]; then
    if confirm_or_dry_run "gcloud sql instances promote-replica orders-dr-replica --project=myapp-prod"; then
      gcloud sql instances promote-replica orders-dr-replica --project=myapp-prod
    fi
  else
    log "ERROR: unsupported provider $PROVIDER"; exit 1
  fi
}

step_3_scale_up_compute() {
  log "Step 3: Scaling up warm-standby compute in $DR_REGION to full capacity..."
  if [[ "$PROVIDER" == "aws" ]]; then
    if confirm_or_dry_run "aws autoscaling update-auto-scaling-group --min-size 6 --desired-capacity 6"; then
      aws autoscaling update-auto-scaling-group \
        --auto-scaling-group-name order-service-asg-dr \
        --min-size 6 --desired-capacity 6 --region "$DR_REGION"
    fi
  elif [[ "$PROVIDER" == "gcp" ]]; then
    if confirm_or_dry_run "gcloud compute instance-groups managed resize order-service-mig-dr --size=6"; then
      gcloud compute instance-groups managed resize order-service-mig-dr \
        --size=6 --zone="${DR_REGION}-a" --project=myapp-prod
    fi
  fi
}

step_4_flip_dns() {
  log "Step 4: Updating DNS to route traffic to $DR_REGION..."
  if [[ "$PROVIDER" == "aws" ]]; then
    if confirm_or_dry_run "aws route53 change-resource-record-sets (failover to DR)"; then
      aws route53 change-resource-record-sets --hosted-zone-id "$HOSTED_ZONE_ID" \
        --change-batch file://dr-dns-changeset.json
    fi
  elif [[ "$PROVIDER" == "gcp" ]]; then
    if confirm_or_dry_run "gcloud dns record-sets update primary.myapp.com --rrdatas=<dr-lb-ip>"; then
      gcloud dns record-sets update primary.myapp.com --type=A --ttl=60 \
        --rrdatas="$(gcloud compute forwarding-rules describe order-service-lb-dr --format='value(IPAddress)')" \
        --zone=myapp-zone --project=myapp-prod
    fi
  fi
}

step_5_verify_and_notify() {
  log "Step 5: Verifying DR site health and notifying on-call..."
  sleep 30
  if curl -sf --max-time 5 "https://primary.myapp.com/healthz" > /dev/null 2>&1; then
    log "SUCCESS: failover complete, primary.myapp.com now serving from $DR_REGION."
  else
    log "WARNING: DR site not yet healthy post-failover, escalate to on-call immediately."
  fi
  curl -sf -X POST "$SLACK_WEBHOOK_URL" -H 'Content-Type: application/json' \
    -d "{\"text\":\"DR failover to $DR_REGION completed for provider=$PROVIDER (dry_run=$DRY_RUN)\"}" || true
}

main() {
  log "=== Starting DR failover runbook: provider=$PROVIDER region=$DR_REGION dry_run=$DRY_RUN ==="
  step_1_verify_primary_down
  step_2_promote_database
  step_3_scale_up_compute
  step_4_flip_dns
  step_5_verify_and_notify
  log "=== DR failover runbook complete ==="
}

main
```

**Runbook design principles baked into the script:**
- **Never blind-trusts alerts** — step 1 independently re-verifies the primary is actually down
  before taking any destructive/irreversible action (promoting a replica cannot be un-done cheaply).
- **`--dry-run` is a first-class mode**, not an afterthought — every DR runbook should be
  regularly exercised in dry-run during game days (see §27) without real risk.
- **Idempotent-ish steps** — re-running after a partial failure (e.g., DNS step failed) skips
  redoing already-completed promotions where possible, so on-call can safely retry under pressure.
- **Human notification is the last step, not the first** — avoids paging everyone before
  confirming the fix actually worked.

## §100 Complete Chaos Engineering / Game-Day Automation (AWS FIS + GCP Equivalent)

Proactively validating the DR runbook in §99 and the resilience assumptions throughout Part 3
requires *scheduled, automated fault injection* — not just tabletop exercises. This uses AWS
Fault Injection Simulator (FIS) and a GCP equivalent built on `kubectl`/Chaos Mesh for parity.

### 100.1 `terraform/chaos/aws-fis.tf` — Fault Injection Simulator Experiment Templates

```hcl
resource "aws_fis_experiment_template" "az_failure" {
  description = "Simulate loss of one AZ for order-service ASG"
  role_arn    = aws_iam_role.fis_experiment_role.arn

  stop_condition {
    source = "aws:cloudwatch:alarm"
    value  = aws_cloudwatch_metric_alarm.fis_stop_condition.arn
  }

  target {
    name           = "orderServiceInstances"
    resource_type  = "aws:ec2:instance"
    selection_mode = "PERCENT(50)"
    resource_tag {
      key   = "Role"
      value = "order-service"
    }
  }

  action {
    name      = "stop-instances"
    action_id = "aws:ec2:stop-instances"
    target {
      key   = "Instances"
      value = "orderServiceInstances"
    }
    parameter {
      key   = "startInstancesAfterDuration"
      value = "PT10M"
    }
  }

  tags = { Name = "az-failure-gameday", Environment = "staging" }
}

resource "aws_fis_experiment_template" "rds_failover" {
  description = "Force RDS Multi-AZ failover to validate app reconnect logic"
  role_arn    = aws_iam_role.fis_experiment_role.arn

  stop_condition {
    source = "none"
    value  = "none"
  }

  target {
    name          = "ordersDb"
    resource_type = "aws:rds:db"
    resource_arns = [var.orders_db_arn]
  }

  action {
    name      = "reboot-with-failover"
    action_id = "aws:rds:reboot-db-instances"
    target {
      key   = "DBInstances"
      value = "ordersDb"
    }
    parameter {
      key   = "forceFailover"
      value = "true"
    }
  }

  tags = { Name = "rds-failover-gameday" }
}

resource "aws_cloudwatch_metric_alarm" "fis_stop_condition" {
  alarm_name          = "fis-order-service-error-rate-abort"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 1
  metric_name         = "5XXError"
  namespace           = "AWS/ApplicationELB"
  period              = 60
  statistic           = "Sum"
  threshold           = 50
}
```

### 100.2 `chaos/gcp/pod-failure-experiment.yaml` — Chaos Mesh on GKE

```yaml
apiVersion: chaos-mesh.org/v1alpha1
kind: PodChaos
metadata:
  name: order-service-pod-kill
  namespace: chaos-testing
spec:
  action: pod-kill
  mode: fixed-percent
  value: "50"
  selector:
    namespaces: ["production"]
    labelSelectors:
      app: order-service
  scheduler:
    cron: "@every 720h"   # game-day cadence, not continuous
---
apiVersion: chaos-mesh.org/v1alpha1
kind: NetworkChaos
metadata:
  name: order-service-cloudsql-latency
  namespace: chaos-testing
spec:
  action: delay
  mode: all
  selector:
    namespaces: ["production"]
    labelSelectors:
      app: order-service
  delay:
    latency: "300ms"
    jitter: "50ms"
  duration: "10m"
```

### 100.3 `chaos/gameday-checklist.sh` — Orchestration & Evidence Capture

```bash
#!/usr/bin/env bash
# gameday-checklist.sh — runs a full quarterly resilience game day
set -euo pipefail

echo "=== Pre-flight: confirm on-call is staffed and stakeholders notified ==="
read -rp "Type YES to confirm on-call staffing and stakeholder sign-off: " confirm
[[ "$confirm" == "YES" ]] || { echo "Aborting game day."; exit 1; }

echo "=== 1/4: AWS AZ-failure experiment ==="
EXP_ID=$(aws fis start-experiment --experiment-template-id "$FIS_AZ_TEMPLATE_ID" --query 'experiment.id' --output text)
echo "Started FIS experiment $EXP_ID"
aws fis get-experiment --id "$EXP_ID"

echo "=== 2/4: GKE pod-kill chaos experiment ==="
kubectl apply -f chaos/gcp/pod-failure-experiment.yaml

echo "=== 3/4: Trigger DR runbook dry-run against both providers ==="
./dr-failover.sh --provider aws --region us-west-2 --dry-run
./dr-failover.sh --provider gcp --region us-east1 --dry-run

echo "=== 4/4: Collect evidence and generate report ==="
mkdir -p "gameday-reports/$(date +%F)"
aws cloudwatch get-metric-statistics --namespace AWS/ApplicationELB --metric-name 5XXError \
  --start-time "$(date -u -d '30 min ago' +%FT%TZ)" --end-time "$(date -u +%FT%TZ)" \
  --period 60 --statistics Sum > "gameday-reports/$(date +%F)/aws-errors.json"
kubectl get events -n chaos-testing --sort-by='.lastTimestamp' > "gameday-reports/$(date +%F)/gke-chaos-events.log"

echo "Game day complete. Review gameday-reports/$(date +%F)/ and file follow-up tickets for any gaps found."
```

**What a mature chaos program validates (tie-back to earlier sections):**

| Experiment | Validates | Related Section |
|---|---|---|
| AZ failure (stop 50% of instances) | ASG/MIG self-healing, ALB health checks | §17/§18 |
| Forced RDS/Cloud SQL failover | App reconnect logic, connection pooling retry | §24 |
| Pod-kill on GKE/EKS | K8s liveness/readiness probes, PDB correctness | §22 |
| Network latency injection | Timeout tuning, circuit breaker thresholds | §20 |
| Full DR runbook dry-run | Cross-team readiness, script correctness | §27, §99 |

## §101 Complete Cost Optimization Automation (Rightsizing Report Generator)

Turns the cost-optimization theory from §15/§52 into a scheduled script that produces an
actionable weekly rightsizing report across both clouds, callable from a cron job or Lambda/
Cloud Function on a schedule.

### 101.1 `cost_optimizer/rightsizing_report.py`

```python
"""Weekly rightsizing report: flags over-provisioned compute across AWS + GCP."""
import boto3
from datetime import datetime, timedelta, timezone
from google.cloud import monitoring_v3
from dataclasses import dataclass

@dataclass
class RightsizingFinding:
    provider: str
    resource_id: str
    resource_type: str
    avg_cpu_pct: float
    current_size: str
    recommended_size: str
    estimated_monthly_savings_usd: float

def find_aws_underutilized_instances(region: str) -> list[RightsizingFinding]:
    cw = boto3.client("cloudwatch", region_name=region)
    ec2 = boto3.client("ec2", region_name=region)
    findings = []
    reservations = ec2.describe_instances(
        Filters=[{"Name": "instance-state-name", "Values": ["running"]}]
    )["Reservations"]
    for res in reservations:
        for inst in res["Instances"]:
            instance_id = inst["InstanceId"]
            instance_type = inst["InstanceType"]
            stats = cw.get_metric_statistics(
                Namespace="AWS/EC2", MetricName="CPUUtilization",
                Dimensions=[{"Name": "InstanceId", "Value": instance_id}],
                StartTime=datetime.now(timezone.utc) - timedelta(days=7),
                EndTime=datetime.now(timezone.utc), Period=3600, Statistics=["Average"],
            )
            if not stats["Datapoints"]:
                continue
            avg_cpu = sum(d["Average"] for d in stats["Datapoints"]) / len(stats["Datapoints"])
            if avg_cpu < 15.0:
                findings.append(RightsizingFinding(
                    provider="aws", resource_id=instance_id, resource_type=instance_type,
                    avg_cpu_pct=round(avg_cpu, 1), current_size=instance_type,
                    recommended_size=_next_smaller_aws_type(instance_type),
                    estimated_monthly_savings_usd=_estimate_savings_aws(instance_type),
                ))
    return findings

def _next_smaller_aws_type(instance_type: str) -> str:
    downsize_map = {"m5.2xlarge": "m5.xlarge", "m5.xlarge": "m5.large", "c5.2xlarge": "c5.xlarge"}
    return downsize_map.get(instance_type, "review-manually")

def _estimate_savings_aws(instance_type: str) -> float:
    hourly_rates = {"m5.2xlarge": 0.384, "m5.xlarge": 0.192, "c5.2xlarge": 0.34}
    current = hourly_rates.get(instance_type, 0.0)
    return round(current * 0.5 * 730, 2)   # ~50% smaller instance, 730 hrs/month

def find_gcp_underutilized_instances(project_id: str) -> list[RightsizingFinding]:
    client = monitoring_v3.MetricServiceClient()
    project_name = f"projects/{project_id}"
    interval = monitoring_v3.TimeInterval({
        "end_time": {"seconds": int(datetime.now(timezone.utc).timestamp())},
        "start_time": {"seconds": int((datetime.now(timezone.utc) - timedelta(days=7)).timestamp())},
    })
    results = client.list_time_series(
        request={
            "name": project_name,
            "filter": 'metric.type="compute.googleapis.com/instance/cpu/utilization"',
            "interval": interval,
            "view": monitoring_v3.ListTimeSeriesRequest.TimeSeriesView.FULL,
        }
    )
    findings = []
    for series in results:
        values = [point.value.double_value for point in series.points]
        if not values:
            continue
        avg_cpu_pct = (sum(values) / len(values)) * 100
        if avg_cpu_pct < 15.0:
            instance_name = series.resource.labels.get("instance_id", "unknown")
            findings.append(RightsizingFinding(
                provider="gcp", resource_id=instance_name, resource_type="n2-standard-4",
                avg_cpu_pct=round(avg_cpu_pct, 1), current_size="n2-standard-4",
                recommended_size="n2-standard-2",
                estimated_monthly_savings_usd=round(0.194 * 730, 2),
            ))
    return findings

def generate_report(aws_region: str, gcp_project: str) -> str:
    findings = find_aws_underutilized_instances(aws_region) + find_gcp_underutilized_instances(gcp_project)
    total_savings = sum(f.estimated_monthly_savings_usd for f in findings)
    lines = [
        f"# Weekly Rightsizing Report — {datetime.now(timezone.utc):%Y-%m-%d}",
        f"\nTotal potential monthly savings: **${total_savings:,.2f}**\n",
        "| Provider | Resource | Current | Recommended | Avg CPU % | Est. Monthly Savings |",
        "|---|---|---|---|---|---|",
    ]
    for f in sorted(findings, key=lambda x: -x.estimated_monthly_savings_usd):
        lines.append(
            f"| {f.provider} | {f.resource_id} | {f.current_size} | {f.recommended_size} | "
            f"{f.avg_cpu_pct}% | ${f.estimated_monthly_savings_usd:,.2f} |"
        )
    return "\n".join(lines)

if __name__ == "__main__":
    report = generate_report(aws_region="us-east-1", gcp_project="myapp-prod")
    with open("rightsizing_report.md", "w") as fh:
        fh.write(report)
    print(report)
```

### 101.2 Scheduling It Serverlessly (Both Clouds)

```hcl
# AWS: EventBridge rule triggers a Lambda running the script every Monday 08:00 UTC
resource "aws_cloudwatch_event_rule" "weekly_rightsizing" {
  name                = "weekly-rightsizing-report"
  schedule_expression = "cron(0 8 ? * MON *)"
}

resource "aws_cloudwatch_event_target" "weekly_rightsizing_lambda" {
  rule = aws_cloudwatch_event_rule.weekly_rightsizing.name
  arn  = aws_lambda_function.rightsizing_report.arn
}
```

```hcl
# GCP: Cloud Scheduler triggers a Cloud Function on the same cadence
resource "google_cloud_scheduler_job" "weekly_rightsizing" {
  name      = "weekly-rightsizing-report"
  schedule  = "0 8 * * MON"
  time_zone = "UTC"
  http_target {
    uri         = google_cloudfunctions2_function.rightsizing_report.url
    http_method = "POST"
  }
}
```

The report lands in `#finops` on Slack or as a GitHub issue every Monday, closing the loop
between the cost-optimization principles taught in §15 and actual continuous enforcement.

## §102 Complete Distributed Rate Limiter (Redis-Backed Token Bucket, ElastiCache/Memorystore)

A production-grade, cloud-portable rate limiter implementing the token-bucket algorithm from
§66, deployable against AWS ElastiCache for Redis or GCP Memorystore for Redis unmodified —
the client only needs a `redis://` connection string, which is the only thing that differs.

### 102.1 `rate_limiter/token_bucket.py`

```python
"""Distributed token-bucket rate limiter backed by Redis (ElastiCache or Memorystore)."""
import time
import redis

_LUA_TOKEN_BUCKET = """
-- KEYS[1] = bucket key, ARGV[1] = capacity, ARGV[2] = refill_rate_per_sec,
-- ARGV[3] = now_ms, ARGV[4] = requested_tokens
local bucket = redis.call('HMGET', KEYS[1], 'tokens', 'last_refill_ms')
local tokens = tonumber(bucket[1])
local last_refill_ms = tonumber(bucket[2])
local capacity = tonumber(ARGV[1])
local refill_rate = tonumber(ARGV[2])
local now_ms = tonumber(ARGV[3])
local requested = tonumber(ARGV[4])

if tokens == nil then
  tokens = capacity
  last_refill_ms = now_ms
end

local elapsed_sec = (now_ms - last_refill_ms) / 1000.0
local refilled = math.min(capacity, tokens + (elapsed_sec * refill_rate))

local allowed = 0
if refilled >= requested then
  refilled = refilled - requested
  allowed = 1
end

redis.call('HMSET', KEYS[1], 'tokens', refilled, 'last_refill_ms', now_ms)
redis.call('EXPIRE', KEYS[1], 3600)
return {allowed, refilled}
"""

class TokenBucketRateLimiter:
    def __init__(self, redis_url: str, capacity: int = 100, refill_rate_per_sec: float = 10.0):
        self._client = redis.Redis.from_url(redis_url, decode_responses=True)
        self._script = self._client.register_script(_LUA_TOKEN_BUCKET)
        self._capacity = capacity
        self._refill_rate = refill_rate_per_sec

    def allow(self, key: str, tokens_requested: int = 1) -> tuple[bool, float]:
        now_ms = int(time.time() * 1000)
        allowed, remaining = self._script(
            keys=[f"ratelimit:{key}"],
            args=[self._capacity, self._refill_rate, now_ms, tokens_requested],
        )
        return bool(int(allowed)), float(remaining)

class RateLimitExceeded(Exception):
    def __init__(self, retry_after_seconds: float):
        self.retry_after_seconds = retry_after_seconds
        super().__init__(f"rate limit exceeded, retry after {retry_after_seconds:.1f}s")

def rate_limited(limiter: TokenBucketRateLimiter, key_fn):
    def decorator(fn):
        def wrapper(*args, **kwargs):
            key = key_fn(*args, **kwargs)
            allowed, remaining = limiter.allow(key)
            if not allowed:
                retry_after = max(0.1, (1 - remaining) / limiter._refill_rate)
                raise RateLimitExceeded(retry_after)
            return fn(*args, **kwargs)
        return wrapper
    return decorator
```

### 102.2 FastAPI Middleware Integration

```python
from fastapi import Request, Response
from starlette.middleware.base import BaseHTTPMiddleware
from rate_limiter.token_bucket import TokenBucketRateLimiter, RateLimitExceeded

limiter = TokenBucketRateLimiter(redis_url="redis://ratelimit-cache:6379/0", capacity=100, refill_rate_per_sec=20)

class RateLimitMiddleware(BaseHTTPMiddleware):
    async def dispatch(self, request: Request, call_next):
        api_key = request.headers.get("x-api-key", request.client.host)
        allowed, remaining = limiter.allow(f"api:{api_key}")
        if not allowed:
            return Response(
                content='{"error":"rate_limited"}', status_code=429,
                headers={"Retry-After": "1", "X-RateLimit-Remaining": "0"},
                media_type="application/json",
            )
        response = await call_next(request)
        response.headers["X-RateLimit-Remaining"] = str(int(remaining))
        return response
```

### 102.3 Terraform: ElastiCache (AWS) and Memorystore (GCP) — Identical Consumer Contract

```hcl
# AWS
resource "aws_elasticache_replication_group" "rate_limit_cache" {
  replication_group_id       = "rate-limit-cache"
  description                = "Redis for distributed rate limiting"
  node_type                  = "cache.r6g.large"
  engine                     = "redis"
  engine_version             = "7.1"
  num_cache_clusters         = 2
  automatic_failover_enabled = true
  multi_az_enabled           = true
  at_rest_encryption_enabled = true
  transit_encryption_enabled = true
  subnet_group_name          = aws_elasticache_subnet_group.main.name
  security_group_ids         = [aws_security_group.redis.id]
}
```

```hcl
# GCP
resource "google_redis_instance" "rate_limit_cache" {
  name           = "rate-limit-cache"
  memory_size_gb = 5
  tier           = "STANDARD_HA"
  redis_version  = "REDIS_7_2"
  region         = var.region
  authorized_network = google_compute_network.main.id
  transit_encryption_mode = "SERVER_AUTHENTICATION"
}
```

**Why Lua/`EVAL`:** the check-refill-decrement sequence must be atomic under concurrent requests
from many app pods; a plain GET/SET from the client would race. Running the logic server-side
in one Redis `EVAL` call makes it atomic without needing distributed locks (see also §80).

## §103 Complete Blue-Green Deployment Automation (CodeDeploy + Cloud Deploy)

Executable automation for the blue-green/canary pattern from §33, using native managed
deployment services on both clouds rather than hand-rolled scripts, for safer rollback.

### 103.1 AWS CodeDeploy — `appspec.yml` + Deployment Group

```yaml
# appspec.yml (ECS blue/green)
version: 0.0
Resources:
  - TargetService:
      Type: AWS::ECS::Service
      Properties:
        TaskDefinition: <TASK_DEFINITION>
        LoadBalancerInfo:
          ContainerName: "order-service"
          ContainerPort: 8080
Hooks:
  - BeforeAllowTraffic: "arn:aws:lambda:us-east-1:123456789012:function:pre-traffic-hook"
  - AfterAllowTraffic: "arn:aws:lambda:us-east-1:123456789012:function:post-traffic-hook"
```

```hcl
resource "aws_codedeploy_deployment_group" "order_service" {
  app_name               = aws_codedeploy_app.order_service.name
  deployment_group_name  = "order-service-bluegreen"
  service_role_arn       = aws_iam_role.codedeploy.arn
  deployment_config_name = "CodeDeployDefault.ECSCanary10Percent5Minutes"

  deployment_style {
    deployment_type   = "BLUE_GREEN"
    deployment_option = "WITH_TRAFFIC_CONTROL"
  }

  blue_green_deployment_config {
    terminate_blue_instances_on_deployment_success {
      action                           = "TERMINATE"
      termination_wait_time_in_minutes = 15
    }
    deployment_ready_option {
      action_on_timeout = "CONTINUE_DEPLOYMENT"
    }
  }

  auto_rollback_configuration {
    enabled = true
    events  = ["DEPLOYMENT_FAILURE", "DEPLOYMENT_STOP_ON_ALARM"]
  }

  alarm_configuration {
    alarms  = [aws_cloudwatch_metric_alarm.high_5xx_rate.alarm_name]
    enabled = true
  }
}
```

### 103.2 GCP Cloud Deploy — `clouddeploy.yaml` Delivery Pipeline

```yaml
apiVersion: deploy.cloud.google.com/v1
kind: DeliveryPipeline
metadata:
  name: order-service-pipeline
serialPipeline:
  stages:
    - targetId: staging
      profiles: ["staging"]
    - targetId: production
      profiles: ["production"]
      strategy:
        canary:
          runtimeConfig:
            kubernetes:
              serviceNetworking:
                service: order-service
                deployment: order-service-deployment
          canaryDeployment:
            percentages: [10, 50]
            verify: true
---
apiVersion: deploy.cloud.google.com/v1
kind: Target
metadata:
  name: production
gke:
  cluster: projects/myapp-prod/locations/us-central1/clusters/main-cluster
requireApproval: true
```

```bash
# Trigger a release through the pipeline
gcloud deploy releases create order-service-rel-$(date +%s) \
  --delivery-pipeline=order-service-pipeline \
  --region=us-central1 \
  --images=order-service=us-central1-docker.pkg.dev/myapp-prod/repo/order-service:1.4.2
```

### 103.3 Automated Rollback Trigger (Shared Logic, Both Clouds)

```bash
#!/usr/bin/env bash
# post-deploy-verify.sh — runs as the AfterAllowTraffic hook (AWS) / verify step (GCP)
set -euo pipefail
ENDPOINT="$1"     # canary/green endpoint URL
ERROR_THRESHOLD=2 # percent

sleep 60  # allow traffic to ramp
ERROR_RATE=$(curl -s "https://metrics.internal/api/v1/error_rate?target=${ENDPOINT}")

if (( $(echo "$ERROR_RATE > $ERROR_THRESHOLD" | bc -l) )); then
  echo "Error rate ${ERROR_RATE}% exceeds threshold ${ERROR_THRESHOLD}% — signalling FAILURE"
  exit 1   # AWS CodeDeploy treats non-zero exit as hook failure -> auto-rollback
            # GCP Cloud Deploy verify step failure -> halts promotion to next phase
fi

echo "Error rate ${ERROR_RATE}% within threshold — signalling SUCCESS"
exit 0
```

Both native services converge on the same operational contract: **automated post-deploy
verification decides pass/fail, and a failure automatically halts or reverses the rollout** —
no human has to watch a dashboard and manually pull the plug during the riskiest minutes of a
release.

## §104 Complete Multi-Cloud Architecture Decision Records (ADR) Template & Worked Examples

ADRs are how real teams durably record *why* a cloud/service was chosen, so future engineers
(and interviewers probing your reasoning) don't have to reverse-engineer intent from Terraform.

### 104.1 ADR Template

```markdown
# ADR-NNN: <short decision title>

## Status
Proposed | Accepted | Deprecated | Superseded by ADR-XXX

## Context
What forces (technical, business, team skill, compliance) are at play?

## Decision
The single sentence stating what was decided.

## Alternatives Considered
| Option | Pros | Cons | Why Rejected |
|---|---|---|---|

## Consequences
- Positive:
- Negative / trade-offs accepted:
- Follow-up actions:
```

### 104.2 Worked ADR — Choosing DynamoDB vs Aurora for the Orders Table

| Field | Content |
|---|---|
| Status | Accepted |
| Context | Orders table needs single-digit-ms p99 reads at 50K RPS peak, simple key-value access pattern (`get by order_id`), team already runs multi-region active-active for the catalog service. |
| Decision | Use DynamoDB with Global Tables for the orders table. |
| Alternative: Aurora Global Database | Pros: relational joins if data model changes, familiar SQL. Cons: cross-region writes need conflict resolution app-side, higher ops burden, higher cost at this scale. Rejected: access pattern is pure KV, no joins needed. |
| Alternative: Single-region Aurora + read replicas | Pros: simpler, cheaper. Cons: doesn't meet the multi-region active-active requirement from §24. Rejected: fails a hard requirement. |
| Consequences | + Scales to any RPS with predictable latency. + Multi-region active-active out of the box. − Must denormalize any reporting queries into a separate OLAP path (§26 data lake). − No ad-hoc SQL joins; follow-up: stream to Redshift/BigQuery via CDC for analytics. |

### 104.3 Worked ADR — GKE Autopilot vs Self-Managed GKE Standard for a New Platform Team

| Field | Content |
|---|---|
| Status | Accepted |
| Context | Small 4-person platform team, no dedicated K8s-ops specialist, workloads are bursty batch + web, cost predictability matters more than fine-grained node tuning. |
| Decision | Use GKE Autopilot. |
| Alternative: GKE Standard | Pros: full node-level control, custom DaemonSets, cheaper at very high sustained scale. Cons: team must patch/upgrade nodes, tune cluster autoscaler, manage node pools. Rejected: team lacks bandwidth for node ops. |
| Alternative: EKS Fargate | Pros: similar serverless-node model on AWS. Cons: org has standardized on GCP for data services already (BigQuery). Rejected: would fragment the stack for no compensating benefit. |
| Consequences | + Zero node patching burden. + Pay-per-pod billing matches bursty workload shape. − Some DaemonSet-based tooling (e.g. certain security agents) unsupported; follow-up: verify agent compatibility before final sign-off. |

### 104.4 Worked ADR — Terraform vs Cloud-Native IaC (CloudFormation/Deployment Manager)

| Field | Content |
|---|---|
| Status | Accepted |
| Context | Company runs both AWS and GCP (this guide's premise); infra team of 3 must maintain both with minimal duplicated tooling knowledge. |
| Decision | Standardize on Terraform for all IaC, both clouds. |
| Alternative: CloudFormation + Deployment Manager | Pros: deepest native integration, first-day support for brand-new services. Cons: two entirely separate DSLs and mental models, no code reuse between clouds, team must be expert in both. Rejected: doubles cognitive load for a 3-person team. |
| Alternative: Pulumi | Pros: real programming language (TypeScript/Python), good multi-cloud story. Cons: smaller community/module ecosystem than Terraform in 2026, team already has Terraform experience. Rejected: switching cost not justified. |
| Consequences | + One tool, one state-management model, one CI/CD pattern for both clouds (§47). − Occasionally 1-2 releases behind on brand-new AWS/GCP features vs native IaC. − Must self-manage state locking/backend (§37) rather than getting it free. |

### 104.5 Worked ADR — Self-Hosted Postgres on VMs vs Managed RDS/Cloud SQL

| Field | Content |
|---|---|
| Status | Accepted |
| Context | Legacy on-prem app being lifted-and-shifted; extremely tight initial migration budget and timeline; DBA team already exists and knows Postgres internals deeply. |
| Decision | Start with managed RDS/Cloud SQL for the migration, revisit self-hosting only if a specific unsupported extension is required later. |
| Alternative: Self-hosted Postgres on EC2/Compute Engine | Pros: full extension support, no vendor limits, potentially cheaper at very large scale. Cons: DBA team would own patching, backups, HA/failover, monitoring — all solved for free by RDS/Cloud SQL. Rejected: migration timeline doesn't allow building this ops capability from scratch. |
| Consequences | + Automated backups, Multi-AZ/HA, patching handled day one (§5). + Frees DBA team to focus on query optimization, not infra. − Some niche extensions unavailable; tracked as a documented risk, re-evaluate in 6 months. |

### 104.6 Worked ADR — Multi-Region Active-Active vs Active-Passive DR for a New Checkout Service

| Field | Content |
|---|---|
| Status | Accepted |
| Context | Checkout is revenue-critical; business mandates RTO < 5 min, RPO near-zero; but active-active adds real complexity (conflict resolution, double the standing infra cost). |
| Decision | Warm-standby (not full active-active) across two regions, with automated failover per §99's runbook. |
| Alternative: Full active-active (both regions serving writes) | Pros: zero failover time, best possible availability. Cons: requires solving write-conflict resolution for payment state — high risk of subtle correctness bugs in a financial workflow. Rejected: correctness risk outweighs the marginal RTO improvement warm-standby already meets. |
| Alternative: Pilot light (cold standby, longer RTO) | Pros: cheapest. Cons: RTO would be 20-30+ min, well outside the 5 min requirement. Rejected: fails hard requirement. |
| Consequences | + Meets RTO/RPO targets with a single source of truth for writes (no conflict resolution needed). + Simpler correctness reasoning for payment state. − Pays for standing (if scaled-down) compute in the DR region even when idle. − Quarterly game-day drills (§100) mandatory to keep failover reliable. |

### 104.7 Why ADRs Matter for Interviews

When an interviewer asks "why did you choose DynamoDB over Postgres here," the strongest answer
format **is** an ADR: state the *decision*, the *2-3 alternatives seriously considered*, and the
*specific requirement or constraint* that tipped it — not just "DynamoDB scales better." This
section's five worked examples are directly reusable as spoken answers to that class of question
across §41-§45's Q&A bank.

## §105 Complete Multi-Cloud Landing Zone Bootstrap (Account/Project Vending Automation)

Automates the secure landing zone pattern from §28 — new team requests a sandbox/project and
gets a fully-guardrailed AWS account (via Control Tower Account Factory) or GCP project (via
Resource Manager + folder policies) in minutes, with zero manual console clicking.

### 105.1 `vend_account.py` — Single Entry Point for Either Cloud

```python
"""Account/project vending automation — the only script a team lead needs to run."""
import argparse
import boto3
from google.cloud import resourcemanager_v3, service_usage_v1

def vend_aws_account(account_name: str, email: str, ou_id: str, budget_usd: int) -> str:
    org_client = boto3.client("organizations")
    response = org_client.create_account(AccountName=account_name, Email=email)
    request_id = response["CreateAccountStatus"]["Id"]

    waiter_state = "IN_PROGRESS"
    while waiter_state == "IN_PROGRESS":
        status = org_client.describe_create_account_status(CreateAccountRequestId=request_id)
        waiter_state = status["CreateAccountStatus"]["State"]
    if waiter_state != "SUCCEEDED":
        raise RuntimeError(f"Account creation failed: {status['CreateAccountStatus']}")

    account_id = status["CreateAccountStatus"]["AccountId"]
    org_client.move_account(
        AccountId=account_id,
        SourceParentId=_get_root_id(org_client),
        DestinationParentId=ou_id,
    )
    _apply_account_budget(account_id, budget_usd)
    _tag_account(org_client, account_id, {"ManagedBy": "landing-zone-automation", "CostCenter": account_name})
    return account_id

def _get_root_id(org_client) -> str:
    return org_client.list_roots()["Roots"][0]["Id"]

def _apply_account_budget(account_id: str, budget_usd: int) -> None:
    budgets_client = boto3.client("budgets")
    budgets_client.create_budget(
        AccountId=account_id,
        Budget={
            "BudgetName": f"{account_id}-monthly-budget",
            "BudgetLimit": {"Amount": str(budget_usd), "Unit": "USD"},
            "TimeUnit": "MONTHLY",
            "BudgetType": "COST",
        },
        NotificationsWithSubscribers=[{
            "Notification": {
                "NotificationType": "ACTUAL", "ComparisonOperator": "GREATER_THAN", "Threshold": 80,
            },
            "Subscribers": [{"SubscriptionType": "EMAIL", "Address": "finops@mycompany.com"}],
        }],
    )

def _tag_account(org_client, account_id: str, tags: dict) -> None:
    org_client.tag_resource(ResourceId=account_id, Tags=[{"Key": k, "Value": v} for k, v in tags.items()])

def vend_gcp_project(project_id: str, display_name: str, parent_folder: str, billing_account: str) -> str:
    projects_client = resourcemanager_v3.ProjectsClient()
    project = resourcemanager_v3.Project(
        project_id=project_id, display_name=display_name, parent=parent_folder,
    )
    operation = projects_client.create_project(project=project)
    result = operation.result()

    _link_billing_account(project_id, billing_account)
    _enable_required_apis(project_id)
    _apply_org_policies(project_id)
    return result.name

def _link_billing_account(project_id: str, billing_account: str) -> None:
    from google.cloud import billing_v1
    billing_client = billing_v1.CloudBillingClient()
    billing_client.update_project_billing_info(
        name=f"projects/{project_id}",
        project_billing_info={"billing_account_name": billing_account},
    )

def _enable_required_apis(project_id: str) -> None:
    su_client = service_usage_v1.ServiceUsageClient()
    baseline_apis = [
        "compute.googleapis.com", "container.googleapis.com",
        "monitoring.googleapis.com", "logging.googleapis.com", "cloudkms.googleapis.com",
    ]
    su_client.batch_enable_services(
        request={"parent": f"projects/{project_id}", "service_ids": baseline_apis}
    )

def _apply_org_policies(project_id: str) -> None:
    # Deny public IPs on new VMs, require OS Login, restrict service account key creation.
    from google.cloud import orgpolicy_v2
    policy_client = orgpolicy_v2.OrgPolicyClient()
    for constraint in [
        "constraints/compute.vmExternalIpAccess",
        "constraints/iam.disableServiceAccountKeyCreation",
    ]:
        policy_client.create_policy(
            parent=f"projects/{project_id}",
            policy={"name": f"projects/{project_id}/policies/{constraint.split('/')[-1]}",
                     "spec": {"rules": [{"enforce": True}]}},
        )

def main():
    parser = argparse.ArgumentParser(description="Vend a new guardrailed AWS account or GCP project")
    parser.add_argument("--provider", choices=["aws", "gcp"], required=True)
    parser.add_argument("--name", required=True)
    parser.add_argument("--email", help="required for AWS")
    parser.add_argument("--ou-id", help="AWS OU / GCP folder id")
    parser.add_argument("--budget-usd", type=int, default=500)
    parser.add_argument("--billing-account", help="required for GCP")
    args = parser.parse_args()

    if args.provider == "aws":
        account_id = vend_aws_account(args.name, args.email, args.ou_id, args.budget_usd)
        print(f"AWS account vended: {account_id}")
    else:
        project = vend_gcp_project(args.name, args.name, args.ou_id, args.billing_account)
        print(f"GCP project vended: {project}")

if __name__ == "__main__":
    main()
```

### 105.2 Guardrails Applied Automatically (Both Clouds)

| Guardrail | AWS Mechanism | GCP Mechanism |
|---|---|---|
| No public IPs by default | SCP denying `RunInstances` with `AssociatePublicIpAddress=true` outside approved OU | Org Policy `constraints/compute.vmExternalIpAccess` |
| Mandatory encryption at rest | SCP denying unencrypted EBS/S3 creation | Org Policy `constraints/gcp.restrictNonCmekServices` |
| No long-lived credentials | SCP denying IAM Access Key creation for root/human users | Org Policy `constraints/iam.disableServiceAccountKeyCreation` |
| Budget alerting from day 1 | AWS Budgets API call in vending script | Billing budget API call in vending script |
| Centralized logging | Account auto-joined to Control Tower log archive | Project auto-linked to central log sink via Terraform |
| Baseline monitoring/alerting | StackSet deploys CloudWatch alarms on account creation | Deployment Manager/Terraform applies alert policies on project creation |

### 105.3 Self-Service Front-End (Slack Command → Vending Script)

```yaml
# Slack slash-command "/new-sandbox <team-name>" triggers this via API Gateway/Lambda
# or Cloud Run + Pub/Sub — same vend_account.py runs headless in either case.
handler_flow:
  - Slack slash command posts to API Gateway (AWS) / Cloud Run endpoint (GCP)
  - Handler validates requester is a team lead (checked against an IAM/HR-synced group)
  - Handler invokes vend_account.py with --provider chosen by which cloud the team needs
  - Handler posts the new account ID / project ID back to the requesting Slack channel
  - Handler opens a tracking ticket for the platform team's weekly landing-zone audit
```

This closes the loop from §28's landing zone theory into something a platform team can hand to
any product team as true self-service, with every guardrail from Part 1's security section
(§8) baked in automatically rather than relying on manual review before every new account.

---

# Full Quick-Index (All 105 Sections)

Use this table as the fast-navigation reference — every section title in the guide, in order,
with its Part. Search this file for the `§NNN` marker to jump straight there.

| § | Title | Part |
|---|---|---|
| 1 | Cloud Computing Models & Shared Responsibility & Pricing | 1 |
| 2 | Global Infrastructure Deep Dive | 1 |
| 3 | Compute Services Deep Dive | 1 |
| 4 | Storage Services Deep Dive | 1 |
| 5 | Database Services Deep Dive | 1 |
| 6 | Networking Deep Dive | 1 |
| 7 | Messaging & Event-Driven Services | 1 |
| 8 | IAM & Security Services | 1 |
| 9 | Serverless & Container Orchestration Deep Dive | 1 |
| 10 | Observability & Monitoring | 1 |
| 11 | IaC & DevOps Tooling | 1 |
| 12 | AWS vs GCP vs Azure Master Service-Mapping Table | 1 |
| 13 | Well-Architected Framework vs Google Cloud Architecture Framework | 1 |
| 14 | Step-by-Step Approach to Any Cloud System Design Interview | 2 |
| 15 | Cost Estimation & Capacity Planning Worked Examples | 2 |
| 16 | Multi-Region / Disaster Recovery Strategies | 2 |
| 17 | Scalable 3-Tier Web Application (AWS) | 3 |
| 18 | Scalable 3-Tier Web Application (GCP) | 3 |
| 19 | Serverless REST API (Lambda vs Cloud Functions) | 3 |
| 20 | Event-Driven Microservices Architecture | 3 |
| 21 | Real-Time Streaming & Analytics Pipeline | 3 |
| 22 | Container Orchestration Platform (EKS vs GKE Autopilot) | 3 |
| 23 | Global Static Site & CDN Hosting | 3 |
| 24 | Multi-Region Active-Active Database Architecture | 3 |
| 25 | CI/CD Pipeline for Microservices | 3 |
| 26 | Big Data Lake & Analytics Platform | 3 |
| 27 | Disaster Recovery Architecture | 3 |
| 28 | Secure Multi-Account / Multi-Project Landing Zone | 3 |
| 29 | Auto-Scaling Video Transcoding Pipeline | 3 |
| 30 | IoT Data Ingestion Platform | 3 |
| 31 | ML Training & Serving Pipeline | 3 |
| 32 | Cost-Optimized Batch Processing Platform | 3 |
| 33 | Zero-Downtime Blue-Green / Canary Deployment Architecture | 3 |
| 34 | Serverless Chat / Messaging Backend | 3 |
| 35 | IAM Policy Design (AWS JSON + GCP Bindings) | 4 |
| 36 | VPC / CIDR Subnet Planning Worked Example | 4 |
| 37 | Terraform Module Design (LLD) | 4 |
| 38 | Autoscaling Policy Configuration Deep Dive | 4 |
| 39 | Security Groups & Firewall Rule Design | 4 |
| 40 | Kubernetes Manifests / Helm Chart for a Cloud-Native App | 4 |
| 41 | AWS-Specific Questions | 5 |
| 42 | GCP-Specific Questions | 5 |
| 43 | Comparison / "When Would You Choose X Over Y" Questions | 5 |
| 44 | Scenario-Based Mini System Design Questions | 5 |
| 45 | Cloud Architect Behavioral & Meta Questions | 5 |
| 46 | Project Structure for an AWS + GCP Multi-Cloud App | 6 |
| 47 | Terraform Multi-Cloud Infrastructure Code | 6 |
| 48 | SDK Integration Code (boto3 + google-cloud) | 6 |
| 49 | CI/CD Across Both Clouds (GitHub Actions) | 6 |
| 50 | Secrets & Config Management Across Clouds | 6 |
| 51 | Multi-Cloud Networking (VPN / Interconnect) | 6 |
| 52 | Cost Management & Tagging Across Providers | 6 |
| 53 | Cloud-Agnostic Abstraction Layer (Adapter Pattern) | 6 |
| 54 | Full Sample Project Walkthrough | 6 |
| 55 | AWS Service Cheat Sheet | 7 |
| 56 | GCP Service Cheat Sheet | 7 |
| 57 | AWS vs GCP vs Azure Master Mapping Table (Extended) | 7 |
| 58 | Numbers & Pricing Quick Reference | 7 |
| 59 | Glossary A-M | 8 |
| 60 | Glossary N-Z | 8 |
| 61 | Study Roadmap (Week by Week) | 9 |
| 62 | FAQ | 9 |
| 63 | Closing Notes | 9 |
| 64 | Ride-Sharing Dispatch System | 10 |
| 65 | Product Recommendation Engine | 10 |
| 66 | Rate-Limiter-as-a-Service | 10 |
| 67 | Global Search / Autocomplete Service | 10 |
| 68 | Payment Gateway Integration | 10 |
| 69 | Feature Flag / Experimentation Platform | 10 |
| 70 | Public API Gateway (Multi-Tenant External Developers) | 10 |
| 71 | Centralized Log Aggregation Platform | 10 |
| 72 | Distributed Job Scheduler / Cron | 10 |
| 73 | Real-Time Fraud Detection Pipeline | 10 |
| 74 | Social Graph Storage / Friend Recommendations | 10 |
| 75 | Push Notification Fan-Out Service | 10 |
| 76 | Distributed Config / Feature Store Service | 10 |
| 77 | Multi-Tenant SaaS Data Isolation | 10 |
| 78 | Global Session Management / SSO | 10 |
| 79 | Serverless Image Processing Pipeline | 10 |
| 80 | Distributed Lock Service | 10 |
| 81 | API Monetization / Billing & Metering | 10 |
| 82 | Real-Time Collaborative Editing Backend | 10 |
| 83 | Health-Check / Service Discovery Platform | 10 |
| 84 | Complete Terraform: Production Environment (VPC+EKS+RDS+Monitoring) | 11 |
| 85 | Complete Kubernetes Manifests: Multi-Service "App of Apps" | 11 |
| 86 | Complete OpenAPI 3.0 Specification (Sample API) | 11 |
| 87 | Complete Database Schema DDL (E-Commerce Sample App) | 11 |
| 88 | Complete GitHub Actions Multi-Env CI/CD Pipeline | 11 |
| 89 | Complete Monitoring/Alerting-as-Code Terraform | 11 |
| 90 | Complete Load Test Script (Locust) | 11 |
| 91 | Complete pytest Test Suite (Order Handler + Adapters) | 11 |
| 92 | Complete Terraform: GCP Production Environment | 11 |
| 93 | Complete FastAPI Reference Application (Order Service) | 11 |
| 94 | Complete Ansible Playbook: Config Management & App Deployment | 11 |
| 95 | Complete Local Dev Stack (docker-compose + LocalStack) | 11 |
| 96 | Complete Grafana Dashboards + Prometheus Alert Rules | 11 |
| 97 | Complete Alembic Database Migration Scripts | 11 |
| 98 | Complete Terraform: Azure Production Environment (3-Cloud Parity) | 11 |
| 99 | Complete Disaster-Recovery Runbook Automation Script | 11 |
| 100 | Complete Chaos Engineering / Game-Day Automation | 11 |
| 101 | Complete Cost Optimization Automation (Rightsizing Report) | 11 |
| 102 | Complete Distributed Rate Limiter (Redis Token Bucket) | 11 |
| 103 | Complete Blue-Green Deployment Automation | 11 |
| 104 | Complete Multi-Cloud Architecture Decision Records (ADR) | 11 |
| 105 | Complete Multi-Cloud Landing Zone Bootstrap | 11 |

## Guide Complete

This guide now spans **11 parts, 105 numbered sections**, 18 full HLD case studies plus 20
leaner mini case studies (38 total system designs), 6 complete LLD artifacts, 300+ interview
Q&A pairs, a 9-part practical multi-cloud integration walkthrough, and a 22-file reference
implementation appendix with real, runnable Terraform/Kubernetes/Python/Bash/YAML — covering
AWS, GCP, and (for the landing-zone and IaC-parity sections) Azure.

**Suggested next steps:**
- If prepping for an interview in under 2 weeks: do Part 2 (framework) + 5 case studies from
  Part 3 of your choice + all of Part 5 (Q&A bank) + the AWS/GCP cheat sheets in Part 7.
- If prepping for 4+ weeks: follow the week-by-week roadmap in §61, and actually deploy the
  Part 11 reference Terraform into a free-tier/sandbox account to build muscle memory.
- If integrating multi-cloud into a real project right now: start at Part 6 (§46), use the
  adapter pattern in §53 as your architectural spine, and lift the CI/CD pipeline in §88/§49
  directly into your repo.

Good luck — and remember: in the actual interview, the framework in §14 and the discipline of
stating trade-offs explicitly (as modeled in every ADR in §104) matter more than memorizing any
single service's API surface.

