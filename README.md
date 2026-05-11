<div align="center">

# Pratyush Mohanty

**Full-Stack Engineer · AI Systems Architect · LLM Integration Specialist**

[![Portfolio](https://img.shields.io/badge/🌐%20Portfolio-pratyushmohanty.vercel.app-6366f1?style=for-the-badge)](https://pratyushmohanty.vercel.app/)
[![GitHub](https://img.shields.io/badge/GitHub-Pratyush426-24292e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pratyush426)
[![Profile Views](https://komarev.com/ghpvc/?username=Pratyush426&style=for-the-badge&color=6366f1&label=Profile+Views)](https://github.com/Pratyush426)

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=6366F1&center=true&vCenter=true&width=700&lines=Building+production-grade+AI+systems;Multi-Agent+Frameworks+%7C+RAG+%7C+LLM+Orchestration;Event-Driven+Backends+%7C+Microservices;Full-Stack+TypeScript+%2B+Python+%7C+Shipping+%F0%9F%9A%80" alt="Typing SVG" />

</div>

---

> I architect **production-grade AI systems** — from novel multi-agent frameworks with emergent specialization to RAG-powered compliance engines and event-driven full-stack platforms.  
> I care about **clean architecture**, **testable code**, **vendor flexibility**, and **shipping things that actually work at scale**.

---

<div align="center">
<img src="https://user-images.githubusercontent.com/74038190/225813708-98b745f2-7d22-48cf-9150-083f1b00d6c9.gif" width="480" />
</div>

---

## 🚀 Featured Projects

> *Four systems that demonstrate depth across AI orchestration, backend architecture, and full-stack engineering.*

---

### 🤖 [ClawSwarm AI](https://github.com/Pratyush426/clawswarnam) — *Novel Multi-Agent LLM Framework with Emergent Role Specialization*

[![Live Demo](https://img.shields.io/badge/Live_Demo-clawswarnam.vercel.app-6366f1?style=for-the-badge&logo=vercel&logoColor=white)](https://clawswarnam.vercel.app)
[![Repo](https://img.shields.io/badge/Source_Code-24292e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pratyush426/clawswarnam)

**The problem with every existing multi-agent framework (CrewAI, AutoGen, LangGraph, MetaGPT): roles must be hardcoded at initialization.** If a task needs heavy coding but your team was configured for writing, the pipeline bottlenecks. ClawSwarm fixes this at a fundamental level.

**Core Innovation — Emergent Role Specialization:**
Agents start completely identical ("blank slates"). Through competitive task performance scored by an impartial LLM-as-judge, each agent's 6-dimensional skill vector diverges via Exponential Moving Average (EMA) updates — organically growing into Researchers, Coders, Critics, or Generalists based purely on results, not configuration.

```
User Task Input
      │
      ▼
 Orchestration Engine
 ┌──────────────┐    ┌──────────────────┐
 │Task Decomposer│───▶│ Task Classifier  │
 └──────────────┘    └──────────────────┘
          │
          ▼
 ┌─────────────────────────────────────┐
 │  Epsilon-Greedy Router              │
 │  80% exploit known strengths        │
 │  20% explore → prevent role-locking │
 └─────────────────────────────────────┘
          │
   ┌──────┴──────┬──────────────┐
   ▼             ▼              ▼
Agent-1        Agent-2        Agent-N
sv[0.87]      sv[0.61]       sv[0.42]
Specialist    Emerging       Generalist
   │             │              │
   └──────┬──────┘              │
          ▼                    │
   LLM Scorer (Judge) ◀────────┘
          │
          ▼
   Skill Vector EMA Update → Role Label Emergence
          │
          ▼
   Leader Election (10s) ←── Fault Detector (2s heartbeat)
          │
          ▼
   WebSocket Broadcast → React/D3.js Live Dashboard
```

**What sets it apart vs. the industry:**

| | CrewAI | AutoGen | LangGraph | **ClawSwarm AI** |
|---|---|---|---|---|
| Role Assignment | Hardcoded | Hardcoded | Hardcoded nodes | **Emergent (runtime)** |
| Dynamic Routing | None | Conversational | Graph-based rigid | **Epsilon-Greedy** |
| Fault Tolerance | Breaks pipeline | Moderate | Good | **Zero-downtime (2s)** |
| Agent Learning | None | Minimal | None | **EMA Skill Vectors** |
| Improves with use | ❌ | ❌ | ❌ | **✅** |

**Architecture highlights:**
- **Epsilon-Greedy routing** balances exploitation of known strengths with exploration — prevents premature role-locking
- **Zero-downtime fault tolerance**: 2s heartbeat checks, automatic task reassignment, leaderless recovery
- **Live D3.js swarm visualization**: Real-time topology of agent skill vectors and task routing
- **LLM-as-Judge scoring**: Objective, impartial evaluation of every subtask output

`Python` `FastAPI` `asyncio` `Redis pub/sub` `Anthropic Claude` `Groq (Llama 3 fallback)` `React` `D3.js` `Docker`

---

### 📊 [NexusAI](https://github.com/Pratyush426/NexusAI) — *AI-Powered Job Application Tracking System*

[![Live Demo](https://img.shields.io/badge/Live_Demo-nexasai.vercel.app-6366f1?style=for-the-badge&logo=vercel&logoColor=white)](https://nexasai.vercel.app/)
[![Repo](https://img.shields.io/badge/Source_Code-24292e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pratyush426/NexusAI)

**Job seekers lose hours managing scattered emails and spreadsheets.** NexusAI replaces all of that with a single Gmail sync and an AI pipeline that extracts, classifies, and visualizes your entire job search — automatically.

**System Architecture — Event-Driven Pipeline:**

```
Gmail API → OAuth Sync
    │
    ▼
Express API  ──────▶  BullMQ Queue (Redis)
    │                      │
    │                      ▼
    │              Worker Service (Node.js)
    │                      │
    │              ┌───────┴────────┐
    │              │  AI Engine     │
    │              │  RegEx (fast)  │
    │              │  + Gemini LLM  │  ← Hybrid Classification
    │              │  (accurate)    │
    │              └───────┬────────┘
    │                      │
    │                      ▼
    │              MongoDB (Mongoose)
    │                      │
    └──────────────────────▼
                    React Dashboard
                  (TanStack Query / Recharts)
```

**Engineering decisions that matter:**
- **Async processing**: Email parsing + LLM inference (2–5s/email) offloaded to BullMQ workers — zero request timeouts, UI stays instant
- **Hybrid classification**: RegEx for speed on obvious patterns, Gemini LLM for nuanced state detection (Interview Invite vs. Soft Rejection vs. Ghosted)
- **JSON-native pipeline**: Gmail API → LLM → MongoDB → React, no rigid schema migrations

**Features:** One-click Gmail OAuth sync · AI extraction of Company/Role/Status · Real-time pipeline health dashboard · Acceptance rate analytics · Framer Motion UI

`React 18` `TypeScript` `Vite` `Node.js` `Express` `MongoDB` `BullMQ` `Redis` `Gemini 1.5 Flash` `Groq` `Shadcn/ui` `TanStack Query` `Recharts`

---

### 🔐 [Pramanik AI](https://github.com/Pratyush426/pramanik) — *RAG-Powered SOC 2 Compliance Engine*

[![Repo](https://img.shields.io/badge/Source_Code-24292e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pratyush426/pramanik)

**SOC 2 compliance is a $50K+ consultant engagement for most SaaS startups.** Pramanik AI makes it self-serve — a multi-modal RAG system with 7 specialized operating modes that guides engineering teams through the entire compliance lifecycle.

**7 Operating Modes, one engine:**

| Mode | What it does |
|---|---|
| 🔍 **Gap Analysis** | Scans AWS config against 35+ SOC 2 controls, scores 0–100%, lists critical failures with fix steps |
| 📄 **Policy Generator** | Generates full policy documents (Incident Response, Access Control, etc.) tailored to your stack |
| 👻 **Ghost Audit** | Role-plays as a Big 4 auditor — adversarial challenge questions before the real audit hits |
| 🤝 **Vendor Inheritance** | Maps which controls your vendors (AWS, Stripe, GitHub, Datadog) already cover for you |
| 💥 **Breach Playbook** | Hour-by-hour incident response for specific scenarios (S3 exposure, compromised EC2, etc.) |
| 🛣️ **PathFinder** | Phased compliance roadmap from your current score to target, with timelines and budgets |
| 💬 **Compliance Chatbot** | Real-time RAG chatbot answering SOC 2 questions with context from your infrastructure |

**Architecture:**

```
FastAPI Application (main.py)
       │
       ├── Pramanik AI Engine (pramanik_ai.py) — RAG orchestration, 7 mode implementations
       │       │
       │       ├── SOC 2 Knowledge Base (35+ controls, severity mappings, benchmarks)
       │       └── CES Algorithm — risk vectorization for remediation prioritization
       │
       ├── AI Service Layer
       │       ├── Deepseek (NVIDIA API) — primary RAG
       │       ├── AWS Bedrock — primary LLM
       │       └── Groq — automatic failover
       │
       ├── Database Layer (Supabase) — scan history, evidence tracking
       └── React Frontend — 7-mode UI, real-time chat, PDF export
```

**Engineering highlights:**
- **Multi-provider failover**: Deepseek → AWS Bedrock → Groq, automatic with no user-visible downtime
- **Compliance Risk Vectorization (CES)**: Proprietary algorithm prioritizing remediation by business impact
- **Framework crosswalk**: SOC 2 controls mapped to ISO 27001 and HIPAA for dual compliance scoring
- **Evidence chain tracking**: Every finding linked to specific control IDs and remediation steps

`Python` `FastAPI` `Deepseek (NVIDIA API)` `AWS Bedrock` `Groq` `Supabase` `React` `RAG` `Pydantic`

---

### 🩺 [HealTrip](https://github.com/Pratyush426/HealTrip) — *AI-Powered Medical Tourism Platform (Microservices)*

[![Repo](https://img.shields.io/badge/Source_Code-24292e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pratyush426/HealTrip)

**End-to-end medical tourism: from symptom diagnosis to hospital booking, flights, hotels, and visa letter generation — all in one platform.** Built on a decoupled microservices architecture with three independent Python ML engines behind a Node.js gateway.

**System Architecture:**

```
React Frontend (React 19 + Three.js + GSAP)
          │
          ▼
Node.js API Gateway (Express.js)
   ├── Auth Middleware (Clerk)
   ├── HealAI Chat Controller  ──▶  Groq / OpenAI (LLM)
   ├── Booking & Payment Controller  ──▶  Stripe + Razorpay
   └── ML Proxy Router
          │
          ├──▶  Hospitals ML Service (FastAPI :8001)
          │       └── scikit-learn similarity matching
          │           PDF NLP → specialty detection
          │
          ├──▶  Flights ML Service (FastAPI :8002)
          │       └── dynamic pricing + logistics optimization
          │
          └──▶  Hotels ML Service (FastAPI :8000)
                  └── accommodation matching by proximity & cost

Persistence: MongoDB Atlas · Cloudinary (PDF/media) · Docker Compose
```

**What's technically interesting:**
- **Medical PDF Analysis**: NLP extracts active conditions and required specialties from uploaded reports, seeding the hospital ML matching algorithm
- **Continuous session memory**: HealAI chatbot maintains health context across the 6-step booking wizard
- **Automated visa letter generation**: PDFKit generates professional medical visa request letters from treatment details; multi-country support (India, USA, Canada, UK, Thailand, Germany, Turkey)
- **Dual payment integration**: Stripe (international) + Razorpay (domestic INR) in a unified checkout flow
- **Containerized with Docker Compose**: All 4 services (React/Node/3× Python ML) orchestrated and production-deployable to any VPS

`React 19` `Node.js` `Express` `Python` `FastAPI` `scikit-learn` `MongoDB Atlas` `Groq` `OpenAI` `Clerk Auth` `Stripe` `Razorpay` `Docker` `Three.js` `GSAP`

---

## 🛠️ Tech Stack

<div align="center">

### Languages
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

### Frontend
![React](https://img.shields.io/badge/React_18/19-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-EF008F?style=for-the-badge&logo=framer&logoColor=white)
![Shadcn/ui](https://img.shields.io/badge/Shadcn%2Fui-000000?style=for-the-badge&logo=shadcnui&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-000000?style=for-the-badge&logo=threedotjs&logoColor=white)

### Backend & Infrastructure
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![BullMQ](https://img.shields.io/badge/BullMQ-FF4040?style=for-the-badge&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

### Databases
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)

### AI / ML
![Anthropic](https://img.shields.io/badge/Anthropic_Claude-6B46C1?style=for-the-badge&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-F54A00?style=for-the-badge&logoColor=white)
![AWS Bedrock](https://img.shields.io/badge/AWS_Bedrock-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic_v2-E92063?style=for-the-badge&logo=pydantic&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)

### DevOps
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=for-the-badge&logo=render&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)

</div>

---

## 📦 Other Projects

| Project | Description | Stack |
|---------|-------------|-------|
| **[BetterFeedback](https://github.com/Pratyush426/BetterFeedback)** | Intelligent customer feedback analyzer — AI categorization (Bugs/Features/Pain Points), sentiment scoring via Gemini, Pydantic v2 validation, 22 tests in ~0.14s | Python · Flask · Pydantic v2 · React · Vite · SQLite |
| **text_to_verilog** | LLM-powered hardware description language generation from natural language | Python · LLM |
| **research-qa** | Intelligent document Q&A with semantic search | Python · NLP |
| **[Portfolio](https://pratyushmohanty.vercel.app/)** | Personal portfolio with smooth animations | React · JS · Framer Motion |

---

## 📊 GitHub Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=Pratyush426&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=6366f1&icon_color=6366f1&text_color=c9d1d9" width="49%" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Pratyush426&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=6366f1&text_color=c9d1d9" width="49%" />

<img src="https://github-readme-streak-stats.herokuapp.com/?user=Pratyush426&theme=tokyonight&hide_border=true&background=0d1117&ring=6366f1&fire=6366f1&currStreakLabel=6366f1" width="70%" />

</div>

---

## 🧠 Engineering Principles

| Principle | Practice |
|-----------|----------|
| 🏗️ **Architecture first** | Design for scale, fault tolerance, and vendor flexibility before writing line one |
| ⚡ **Async by default** | Background queues (BullMQ/Redis), WebSockets, non-blocking pipelines |
| ✅ **Testing is a feature** | Automated from day one — never retrofitted |
| 🔒 **Type safety everywhere** | TypeScript end-to-end + Pydantic v2 on Python services |
| 🔌 **Vendor flexibility** | Swappable AI providers with automatic failover — zero hard lock-ins |
| 🚢 **Ship and iterate** | Real products deployed to real users, then refined |
| 📝 **Document the why** | Architecture decisions, tradeoffs, and failure modes documented alongside code |

---

## 🌱 Currently Exploring

```
🤖  Multi-agent reasoning patterns & advanced LLM orchestration
📡  Real-time streaming architectures & event-driven systems
🔐  Security, auth, and compliance automation at scale
⚙️  Infrastructure-as-code & DevOps automation
🧪  Evaluation frameworks for LLM output quality
```

---

## 📬 Let's Connect

<div align="center">

[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-Visit_Site-6366f1?style=for-the-badge)](https://pratyushmohanty.vercel.app/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-24292e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pratyush426)

**Open to software engineering roles, AI/LLM system design discussions, and collaborations.**  
Reach out via GitHub or through my portfolio.

---

*Always building something that shouldn't exist yet.* ⚡

</div>
