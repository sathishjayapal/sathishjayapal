# 🛠️ Sathish Jayapal – Laboratory of Systems & Resilience
 
**Cloud Architect | Event-Driven Systems Builder | Marathon Runner | Learning in Public**
 
I design distributed systems for cloud platforms and explore how **resilience principles** from endurance sports apply to building reliable software. This is my laboratory — where architecture thinking meets code, and theory meets the constraints of running real applications.
 
---
 
## 🎯 Where to Start
 
**If you're interested in:**
 
### 📐 **Event-Driven Systems & Distributed Transactions**
 
→ Start with **[EventsTracker](https://github.com/sathishjayapal/eventstracker)**  
A multi-service event ingestion platform exploring RabbitMQ choreography, ShedLock coordination, and Kubernetes operations. Self-hosted and deployed via a Portainer CI/CD pipeline, running Spring Boot 3.5.7, Java 21, and Spring Cloud Config integration. Recently added: correlation-ID propagation into the new centralized logging service. Built to answer: *How do you handle distributed transactions and race conditions at scale?*
 
### 🏃 **Full-Stack Systems (Backend + Frontend)**
 
→ Start with **[Runs App](https://github.com/sathishjayapal/runs-app)**  
The most complete end-to-end system in the lab: Spring Boot 4.0.1 backend + React 19/TypeScript frontend, Garmin FIT file import, Strava sync, ShedLock-scheduled jobs, RabbitMQ event publishing into the EventsTracker topology, and a full Docker Compose + Testcontainers setup. The clearest single repo to judge how I structure a production-shaped app end to end.
 
### 🏃‍♂️ **Analytics for Distributed Systems (via Running Data)**
 
→ Start with **[Runs AI Analyzer](https://github.com/sathishjayapal/runs-ai-analyzer)** *(Active Development)*  
Using semantic caching (PgVector + Claude API + Ollama embeddings) to analyze running data as a testbed for RAG patterns and real-time anomaly detection. Accepts Garmin payloads, publishes RabbitMQ events into EventTracker topology. Recent work: **async analysis job tracking** (`AnalysisJob` entity with status polling), AI fallback between Anthropic and Ollama, Flyway migrations, Docker CI. Why? Because marathons taught me that **resilience is a system property**, not a component.
 
### 🏗️ **Infrastructure as Code & Kubernetes Ops**
 
→ Start with **[iAC-NikeRuns](https://github.com/sathishjayapal/iAC-NikeRuns)**  
Dual-cloud Terraform codebase provisioning the same microservices ecosystem on both Azure and AWS ACG sandbox — composable modules, a code-status diagram distinguishing active/standalone/legacy paths, and working around real sandbox restrictions (e.g. an SCP blocking `rds:CreateDBInstance`). Learning to go from "eksctl create cluster" to "infrastructure as a git-reviewed system."
 
### 🤖 **Agentic AI for Engineering Workflows**
 
→ Explore **[AI Agent Experiments](https://github.com/sathishjayapal?q=ai-agent&type=source)**  
Auto-triaging stale branches, reconciling Terraform state with live resources, drafting ADRs from commit history. Early-stage exploration of how AI agents can reduce toil.
 
---
 
## 📚 Architecture Deep Dives (Read First, Then Code)
 
I write longer pieces at **[sathishjayapal.me](https://sathishjayapal.me)** (canonical source) and cross-post to [Medium @dotsky](https://dotsky.medium.com).
 
### Featured Posts (Start Here)
 
- **[From eksctl to Terraform: Making Sense of EKS Resources](https://sathishjayapal.me/eksctl-to-terraform-eks-mapping/)**  
How to take an EKS cluster created with `eksctl` and reverse-engineer it into maintainable Terraform modules. The gap between "click-next cloud" and "infrastructure you can version and review."
- **[Designing Scalable Queues for Real-World Workloads](https://sathishjayapal.me/2025/10/24/designing-scalable-queues-for-personal-projects/)**  
Patterns for moving RabbitMQ from hobby projects to resilient production-like setups: dead-lettering, backpressure, observability. This thinking is baked into EventsTracker.
- **[Tackling Distributed Transactions in Microservices](https://dotsky.medium.com/tackling-distributed-transactions)** *(cross-posted)*  
Using ShedLock for distributed task scheduling and avoiding race conditions in Kubernetes. Real constraints. Real solutions.
- **[From Marathon Dreams to Injury Recovery: A Runner's Journey](https://sathishjayapal.me/2025/12/31/from-marathon-dreams-to-injury-recovery-a-runners-journey/)**  
How systems thinking from distributed systems applies to running recovery, feedback loops, and building resilience into training design.
- **[Semantic Caching for Intelligent Running Analysis](https://sathishjayapal.me/2026/02/08/semantic-caching-for-intelligent-running-analysis/)**  
Using PGVector and Claude embeddings to avoid re-analyzing past running data. RAG patterns at personal scale.

**→ [See all posts](https://sathishjayapal.me)**
 
---
 
## 🏗️ What I'm Building Now
 
### EventsTracker — **Self-Hosted, Actively Deployed**
 
A multi-service event ingestion platform with config server integration, deploy profiles, and Kubernetes-native design.
 
- **Why:** To understand how production systems handle distributed transactions, race conditions, and resilience at small scale before enterprise scale.
- **Tech:** Java 21 • Spring Boot 3.5.7 • Spring Cloud Config • RabbitMQ • PostgreSQL/Flyway • Kubernetes • Maven
- **Focus:** Event-driven choreography, ShedLock coordination, zero-trust microservice security, self-hosted deploy pipeline.
- **Status:** Core event ingestion stable; config-server integration tested; deployed via a GitHub Actions → Portainer pipeline to a home-lab VM (not a commercial production environment); runs locally with spring profiles (local/prod).
- **Recent:** Correlation-ID filter wired into the new centralized logging service; `dev-up.sh` consolidated onto shared Postgres/RabbitMQ infra; Run Journal Entry management (CRUD + embedding service).
- **Next:** Zero-downtime deployments, comprehensive observability (metrics/tracing/logging), Kubernetes Helm charts.

→ **[Go to EventsTracker](https://github.com/sathishjayapal/eventstracker)** | **[Read the blog post](https://sathishjayapal.me/tackling-distributed-transactions)**
 
---
 
### Runs App — **Most Complete End-to-End System**
 
The flagship full-stack app in the lab: running-activity tracker with Garmin FIT import, Strava sync, and event publishing into the EventsTracker topology.
 
- **Why:** The clearest single repo to see backend, frontend, scheduling, and messaging working together as one system.
- **Tech:** Java 21 • Spring Boot 4.0.1 • React 19 + TypeScript • Tailwind CSS • RabbitMQ • PostgreSQL/Flyway • Testcontainers
- **Focus:** Garmin FIT SDK ingestion, ShedLock-scheduled import jobs, Spring Security (RBAC), RabbitMQ event publishing.
- **Status:** Actively developed; backend (:8080) and React dev server (:3000) run side by side; CI builds Docker images.
- **Recent:** Docker/Testcontainers version bumps; PostgreSQL env-var handling hardened; ACG/production `.env` support added to `dev-up.sh`.

→ **[Go to Runs App](https://github.com/sathishjayapal/runs-app)**

---
 
### Runs AI Analyzer — **Active Development**
 
A multi-service platform for ingesting Garmin running data, analyzing via Claude API, storing in PgVector, and publishing events.
 
- **Why:** Marathons taught me that resilience is a system property. I'm applying that insight to real-time athletic performance analytics using RAG patterns.
- **Tech:** Java 21 • Spring Boot 4.0.1 • Spring AI 2.0.0-M1 (Claude + Ollama) • PGVector • PostgreSQL • RabbitMQ • OpenAPI/Swagger
- **Focus:** RAG-based semantic caching, async analysis job tracking, EventTracker integration (RabbitMQ topology), AI fallback between Anthropic and Ollama, Garmin payload compatibility.
- **Status:** Core analysis stable; PgVector RAG cache working; EventTracker event publishing integrated; Ollama embeddings live; async `AnalysisJob` tracking with status polling; Docker CI active.
- **Recent:** `AnalysisJob` entity + batch service for async run analysis; Flyway migrations; Run Journal event publishing; Docker build/push CI workflow.
- **Next:** Kubernetes deployment (helm), multi-region event consistency patterns, anomaly detection for injury prevention signals.

→ **[Go to Runs AI Analyzer](https://github.com/sathishjayapal/runs-ai-analyzer)** | **[Read the blog post](https://sathishjayapal.me/semantic-caching-running-analysis)**

---

### MyGithubCleaner (verbose-barnacle) — **Active**

A Spring Boot multi-module app that syncs, manages, and deletes GitHub repositories, integrated with EventTracker via RabbitMQ.

- **Tech:** Java 24 • Spring Boot 3.5.3 • React 19 + TypeScript • RabbitMQ • Spring Cloud Config • Spring Cloud Kubernetes Discovery
- **Focus:** GitHub API integration, repo lifecycle management, event publishing to EventTracker topology.
- **Status:** Actively maintained; recently updated for EventTracker RabbitMQ routing key changes and Java version bump to 24.

→ **[Go to MyGithubCleaner](https://github.com/sathishjayapal/verbose-barnacle)**

---

### DBCleaner — **Active**

A Spring Boot 4 / Java 25 application (scaffolded with Bootify.io) for database cleanup workflows with a Thymeleaf + Node.js dev server frontend and Spring Modulith structure.

- **Tech:** Java 25 • Spring Boot 4.0.6 • Thymeleaf • Testcontainers • Spring Modulith • Docker CI
- **Status:** Past initial scaffold; CI/CD pipeline hardened (Docker Hub tagging, image verification, smoke tests), HikariCP tuning for its external datasource, home page showing live project statistics.

→ **[Go to DBCleaner](https://github.com/sathishjayapal/dbcleaner)**

---

### SathishLogger (sathish-projects-logger) — **Active**

A parameterized, Docker-based centralized logging service deployable once and reusable across all projects. Provides REST APIs for log ingestion, correlation ID tracking, and log aggregation.

- **Tech:** Java 21 • Spring Boot 3.5.9 • Docker Compose • AOP-based correlation tracking • Flyway
- **Status:** Repo renamed to `sathish-projects-logger`; Flyway migration for the `log_entries` schema landed; CI/CD pipeline rebuilt with dynamic image naming, JAR verification, and smoke tests; first consumer (EventsTracker) now sends correlation IDs to it.

→ **[Go to SathishLogger](https://github.com/sathishjayapal/sathish-projects-logger)**

---
 
### iAC-NikeRuns — **Dual-Cloud Terraform, Active**
 
Reverse-engineering cloud-click infrastructure into clean, versioned Terraform modules across Azure and AWS.
 
- **Why:** Too many teams run "cloud click-next" deployments. This is how you move from ad-hoc to reviewable infrastructure.
- **Tech:** Terraform • AWS (EC2, planned EKS/MSK/Aurora) • Azure Container Apps • Kubernetes • Infrastructure as Code
- **Status:** Azure stack composed as one root module; AWS modules applied independently under `aws-modules/`, with a maintained code-status diagram (active/standalone/legacy) since the repo carries multiple approaches to the same ACG sandbox SCP restrictions. Recently extended with database resources for the my-github-cleaner and dbcleaner projects.

→ **[Go to iAC-NikeRuns](https://github.com/sathishjayapal/iAC-NikeRuns)** | **[Read the blog post](https://sathishjayapal.me/eksctl-to-terraform-eks-mapping/)**
 
---
 
### Agentic AI Experiments — **Early Stage**
 
Exploring AI agents to reduce engineering toil:
 
- Auto-triaging stale branches and PRs
- Reconciling Terraform state with live Kubernetes/EKS/AKS resources
- Drafting ADRs and changelogs from commit history

→ **[Browse AI experiments](https://github.com/sathishjayapal?q=ai-agent&type=source)**
 
---
 
## 💻 Technical Comfort Zone
 
**Languages & Frameworks**  
Java (21/24/25) • Spring Boot • Spring Cloud • Spring AI • REST APIs • Event-Driven Architectures
 
**Cloud & Infrastructure**  
AWS (EKS, RDS, S3, ECS) • Azure • Kubernetes • Terraform • Infrastructure as Code • Spring Cloud Config
 
**Data & Patterns**  
PostgreSQL • RabbitMQ/Kafka • Distributed Transactions • PGVector/Semantic Search • Real-Time Analytics • RAG Caching
 
**Architecture Styles**  
Microservices • Event-Driven • Domain-Driven Design • CQRS • Spring Modulith • Zero-Trust Security
 
[![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) [![Spring Boot](https://img.shields.io/badge/SpringBoot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white)](https://img.shields.io/badge/SpringBoot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white) [![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white) [![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white) [![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white) [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white)](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white) [![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white)](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white)
 
---
 
## 🏃‍♂️ Beyond Code
 
**Marathoner:** 9 marathon finishes including the Flying Pig Half Marathon (Cincinnati, May 2026). Now in post-race recovery and planning the next training cycle. Every long run is a lesson in system design — feedback loops, resilience, constraint management, recovery.
 
**Thesis:** The principles that make distributed systems resilient (redundancy, graceful degradation, observability, feedback loops) are the same principles that make training cycles effective. I explore this at the intersection of both domains.
 
**Location:** Madison/Sun Prairie, Wisconsin. Always happy to discuss architecture over South Indian coffee.
 
---
 
## 🌐 Stay Connected
 
📝 **Blog** — [sathishjayapal.me](https://sathishjayapal.me) (canonical source of all posts)  
🔗 **Medium** — [@dotsky](https://dotsky.medium.com) (cross-posted, always with canonical link back)
 
**Interested in collaborating, discussing architecture, or connecting on cloud modernization?**  
→ Open an issue on any repo or reach out at **<contact@sathishjayapal.me>**
 
---
 
## 📊 Recent Activity
 
- **EventsTracker:** Correlation-ID filter feeding the new logging service; deploy-to-Portainer workflow tuned; consolidated onto shared Postgres/RabbitMQ dev infra
- **Runs App:** Docker/Testcontainers hardening; ACG + production `.env` support in `dev-up.sh`; Axios request/response handling enhanced
- **SathishLogger:** Renamed to `sathish-projects-logger`; Flyway migration for `log_entries`; CI/CD pipeline rebuilt with JAR verification and smoke tests
- **DBCleaner:** CI/CD hardened (dynamic image naming, Docker Hub tagging); HikariCP tuning; home page now shows live project stats
- **Runs AI Analyzer:** Async `AnalysisJob` entity + batch service; AI fallback (Anthropic ↔ Ollama); Flyway migrations; Docker CI active
- **MyGithubCleaner:** Java 24 upgrade; EventTracker RabbitMQ routing key alignment; env file consolidation
- **iAC-NikeRuns:** Terraform database resources added for my-github-cleaner and dbcleaner
- **Infrastructure:** consolidated-postgres dev-up scripts extended across projects; ACG sandbox Terraform fixes
- **Running:** Post-Flying Pig (May 2026) recovery; planning next training cycle

---
 
## 📝 How to Use This Space
 
✅ **Learn from the code:** Each project has a detailed README explaining the "why" alongside the "how."  
✅ **Read the architecture posts first:** Blog posts provide context for why code is structured the way it is.  
✅ **Follow the learning journey:** From CKAD exploration → EventsTracker → Kubernetes ops patterns → RAG systems.  
✅ **Engage & discuss:** Open issues for questions, architecture debates, or alternative approaches.  
✅ **Contribute:** Forks, PRs, and improvements welcome.
 
---
 
## 🎓 What This Lab is About
 
This is **not a portfolio of finished products**. It's a **learning laboratory in public**:
 
- Real constraints (Kubernetes, distributed transactions, RAG patterns, Spring AI integration)
- Real decisions (documented in Architecture Decision Records)
- Real friction (MapStruct compilation, reconciling Terraform state, Ollama embedding complexity)
- Real outcomes (blog posts, working applications, operational insights)

The goal is to **show how I think**, not just what I've built.
 
---
 
**Built with ☕ and 🏃. Always learning. Always building. Always honest.**
