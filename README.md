# Sathish Jayapal — Systems, Resilience & Learning in Public

**Cloud & Enterprise Architecture | Distributed Systems | Platform Engineering | Applied AI | Marathon Runner**

I build systems to understand them.

My personal projects are a laboratory for exploring the problems that show up in real distributed systems: **retries, event consistency, configuration drift, observability, CI/CD, infrastructure automation, deployment portability, and AI-assisted analysis.**

The running domain gives me real data and real failure modes. The engineering is the point.

---

## 🔭 What I'm Building

Rather than isolated demo applications, these projects increasingly operate as one small distributed system.

| Project                                                                              | What I'm exploring                                                                                                                                           |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **[Runs App](https://github.com/sathishjayapal/runs-app)**                           | My flagship full-stack application. Garmin + Strava data, Spring Boot, React, PostgreSQL, RabbitMQ, scheduling, security and CI/CD.                          |
| **[Runs AI Analyzer](https://github.com/sathishjayapal/runs-ai-analyzer)**           | AI analysis over running data using Spring AI, embeddings, PGVector, semantic caching and asynchronous processing.                                           |
| **[EventsTracker](https://github.com/sathishjayapal/eventstracker)**                 | Event ingestion, RabbitMQ choreography, distributed coordination and operational patterns.                                                                   |
| **[consolidated-postgres](https://github.com/sathishjayapal/consolidated-postgres)** | The orchestration layer for the ecosystem: databases, RabbitMQ, environment configuration and deployments across local, VM and temporary cloud environments. |
| **[iAC-NikeRuns](https://github.com/sathishjayapal/iAC-NikeRuns)**                   | Terraform experiments across AWS and Azure, including EKS Fargate, PostgreSQL/pgvector and adapting architecture to real sandbox constraints.                |

Supporting services include **[SathishLogger](https://github.com/sathishjayapal/sathish-projects-logger)** for centralized logging and correlation IDs.

---

## 🧪 The Interesting Part Isn't the App

A running tracker by itself isn't particularly interesting.

What interests me is what happens when it becomes a system:

```text
Garmin / Strava
       │
       ▼
   Runs App
       │
       ├──── events ────► RabbitMQ ────► EventsTracker
       │
       ├──── analysis ──► Runs AI Analyzer ──► PGVector / AI
       │
       └──── logs ──────► SathishLogger

            │
            ▼
 Shared PostgreSQL + configuration
            │
            ▼
 Docker / Portainer / Cloud Sandboxes
```

That creates opportunities to experiment with the same questions that matter in much larger platforms:

**What happens when a message is delivered twice?**
**How do services share configuration without configuration drift?**
**How much infrastructure should be centralized?**
**How do you trace one request across services?**
**Can the same workload move from a laptop to a VM to the cloud?**
**Where should AI be used — and where shouldn't it?**

---

## 🚀 What Changed Recently

The last few months have been less about adding another application and more about making the ecosystem **operable**.

### CI/CD became a pipeline, not a build script

Runs App now goes through a more complete software-delivery path:

```text
git push
   ↓
TEST
   ↓
STATIC ANALYSIS
   ↓
BUILD IMAGE
   ↓
VULNERABILITY SCAN
   ↓
PUBLISH
```

I've been working through dependency security, automated scanning, Docker image construction, smoke testing and making failures visible instead of simply producing an image.

### The home lab became a deployment target

I moved several services into a Docker/Portainer environment rather than keeping every experiment tied to a cloud account.

That introduced useful problems of its own:

* amd64 vs arm64 container images
* persistent database volumes
* environment and secret management
* service startup ordering
* shared RabbitMQ/PostgreSQL infrastructure
* deployment automation
* moving workloads between local, VM and cloud environments

The objective isn't to pretend a home lab is production.

It's to make the applications **production-shaped enough to learn from operating them**.

### Shared infrastructure exposed configuration drift

Once several Spring Boot projects shared PostgreSQL and messaging infrastructure, inconsistencies that were invisible inside individual repositories became obvious.

That led to `consolidated-postgres`: one place to manage project databases, RabbitMQ, environment mappings, startup verification and temporary cloud environments.

### Observability became part of the architecture

I also introduced a reusable centralized logging service and started propagating correlation IDs between applications.

The next step is completing the observability triangle:

**logs → metrics → distributed traces**

---

## 🧠 Architecture Topics I'm Exploring

My projects tend to orbit a few recurring questions:

**Distributed systems**
Event-driven architecture • RabbitMQ • retries • idempotency • distributed coordination • eventual consistency

**Platform & cloud**
Docker • Kubernetes • Portainer • AWS • Azure • Terraform • deployment portability

**Software delivery**
GitHub Actions • automated testing • static analysis • container scanning • dependency security • CI/CD

**Data & AI**
PostgreSQL • PGVector • RAG • semantic caching • embeddings • Spring AI • Anthropic • Ollama

**Application architecture**
Java • Spring Boot • React • REST APIs • DDD • CQRS • Flyway • Testcontainers

---

## ✍️ Learning in Public

I write about the point where diagrams meet actual implementation.

Recent themes include:

**PostgreSQL configuration drift across multiple Spring Boot projects**
What happens when several independently-developed services slowly develop different assumptions about the same infrastructure.

**Docker + Portainer for a personal server**
Moving a collection of Spring services from cloud-hosted experiments onto portable Docker infrastructure.

**Retry safety and exactly-once thinking**
Exploring ideas such as RIFL and applying distributed-systems research to a real endpoint rather than only reading the paper.

**AI + running data**
Using PGVector, embeddings and LLMs while dealing with temporal context, stale information and the limits of AI recommendations.

📝 **Blog:** [sathishjayapal.com](https://sathishjayapal.com)
🔗 **Medium:** [@dotsky](https://dotsky.medium.com)

---

## 🏃 Why Running?

Running gives me something most software demos don't have:

**A domain I actually care about and continuously generate data for.**

Training data changes over time. Context matters. Bad recommendations have consequences. Imports fail. Data gets duplicated. Devices disagree.

That makes it a surprisingly good laboratory for thinking about software architecture.

I recently came across a principle in Xbox's leadership principles that stayed with me:

> **Clarity is kindness.**

I like the simplicity of it.

Whether I'm writing code, documenting an architecture decision, designing an interface between services, or explaining why something failed, I want clarity to be part of how I work here.

Build things. Understand them. Explain them clearly.

---

## 📍 About Me

I'm based in Wisconsin and work in enterprise/cloud architecture. GitHub is where I keep the hands-on side of that learning: writing code, breaking things, operating them, documenting what went wrong and turning the useful lessons into architecture thinking. I'm less interested in presenting these repositories as polished products than in showing 
**how my thinking changes as the systems become more real**.

**Build → operate → observe → learn → redesign.**

That's the laboratory.
