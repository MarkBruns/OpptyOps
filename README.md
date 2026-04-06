# Opportunity Discovery and Pursuit Engine

*This OpptyOps repo is a work-in-progress fork* so ***you probably want to [go directly to @Santifer's original](https://github.com/santifer/career-ops).***  

## **Project Vision**

The core purpose of an Opportunity Discovery and Pursuit Engine is the relationship itself: to discover high-value opportunities efficiently, pursue them with focus, bring them to successful closure, and sustain them over time. Technology is merely the means to that end. AI, multi-agent systems, and agentic workflows are not the point — they exist only to get the job done and then step aside.

OpptyOps is conceived as a pragmatic, no-frills multi-toolkit. It will not prioritize polish, at least not initially and possibly not ever. Instead, it is an open-source evolution and deliberate study of both [the development process behind Santifer’s Career-Ops system](https://santifer.io/career-ops-system) and the original repository (https://github.com/santifer/career-ops), along with its forks and related projects.

The goal is to build a lightweight, extensible open source toolkit for a pragamatic Partner Relationship Management (PRM) / CRM platform that be modified/extended to fully automate different opportunity lifecycles. Opportunities extend well beyond traditional job search to include startup founding, venture philanthropy, special-projects staffing, volunteer coordination, and any creative, scientific, or artistic collaboration that requires meaningful commitment of talent and resources.

The system is designed to run continuously on low-resource local hardware such as a Raspberry Pi or Mac Mini M4. It employs lightweight multi-agent orchestration, file- and Markdown-first memory, and small specialized large language models. Core capabilities include autonomous prospecting and data ingestion, multi-dimensional opportunity qualification, persistent CRM-style tracking, and on-demand generation of the documents essential to discussion and accelerated negotiation — resumes, cover letters, statements of work, proposals, and pitch decks.

As a monorepo, OpptyOps deliberately avoids reinventing existing solutions. For any given task it surfaces 3–4 proven, practical approaches (CLI tools, Python, Rust, Go, Chroma, dashboards, etc.) so developers and users can select the simplest and most effective path for their needs.


---

## General Vision For UNDERSTANDING How An Opportunity Operations System Might Work

The first step will be using and developing the Career Ops system in order to better undertand how we might put together a 10-step Playbook, even though we have some ideas for what this might entail.

The currently propsed playbook is deliberately sequential yet modular—complete steps 1–3 first (they take ~1–2 days), then parallelize framework experiments in Step 4–5. The purpose of doing is is to **thoroughly study [Santifer's process for building his Career-Ops system](https://santifer.io/career-ops-system)**, including its [open-source GitHub repo](https://github.com/santifer/career-ops).

My personal intent is a weensy bit more aspirational than just study.  At first, I plan to add trial approaches based on [different agentic approaches](https://x.com/i/grok/share/a2a7103986ad4eb2a87eed64722e393e) such as [Hermes](https://github.com/NousResearch/hermes-agent), [Open Claw](https://github.com/openclaw/openclaw), et al as well as weaving in things like [Chroma](https://docs.trychroma.com/docs/overview/introduction) ... as well as prospecting approaches based on something for agentic workflows that would be like [**Robert Scobel**'s AI Topic **Aligned News** Exlorer for X](https://alignednews.com/how-it-works), because X is more than just a data store ... X is mainly about PEOPLE.  

Since it **represent INFORMED judgment about which knowledgeable experts are actually the most important in moving the DISCIPLINES involved in AI**, [Aligned News for AI](https://alignednews.com/) is built on 63 hand-curated X lists, which index 100,000+ accounts and the interactions amongst those moving the field. In every sweep of data collection, an XPlugin pulls 3,000–7,000 new posts from the priority lists. The importance of the proven and efficient XPlugin interface [written in C++] between the MySQL server and its clients, stems from how it efficiently modernizes legacy systems and bridges different development workflows. Every post is indexed to a [Weaviate vector database](https://docs.weaviate.io/weaviate) with full metadata: text, author, engagement metrics, and timestamp. Seen/unseen tracking ensures only new posts are processed so that the automated distillation processing happens on a relatively small set of very high quality data:

- **Signal detection** ... the system applies 100+ signal keywords across all posts: “launching,” “acquired,” “SOTA,” “breakthrough,” “accepting,” “breaking,” and more. Posts containing multiple signal keywords get priority scoring.
- **Semantic search* ... after raw keyword scanning, targeted semantic searches surface signals that keywords miss. This is where the hidden gems get found — the low-engagement post from a high-signal author that reveals a trend before anyone else notices.
- **Cross-list pattern detection** ... when a signal appears in 3+ different lists simultaneously, it gets flagged for highest priority. The cross-list amplifier tells you when something is genuinely spreading through the community.
- **Editorial synthesis** ... the AI reads all signals, applies Robert’s editorial judgment, and generates structured content with context — connecting separate stories that illuminate each other, explaining why a low-engagement post matters more than its metrics suggest.
- **Publication** ... content is written to [the Supabase database](https://supabase.com/). The site carries a live timestamp. All sections are regenerated with fresh content from the sweep.

It is the remarkably efficient picture of what's happening in AI that Aligned News presents that inspires some rather grandiose expectations of what we can think about when applied to the task of almost effortlessly improving one's set of opportunities. The point is to use the best of different proven and efficient technologies, as Scobel has done, to generalize an what is a fine agentic system for job search into one with much more ambitious, generally broad ideas about finding the highest and best use of our time, in work, in creative pursuits, in LIFE ... thus an extensible, open source toolkit for building ***“Opportunity Discovery And Pursuit Engines”*** ... *and maybe along the way, we can find better name, than* **OpptyOps!* 

---

## **10-step Playbook For PRACTICALLY DEVELOPING An Opportunity Operations System

What's given below is of a highly proforma nature. The overall structure is purpose-built for these stated goals: deep understanding, potential rebuilding, and expansion beyond job search (e.g., to startup founding evaluation, venture philanthropy scouting, or any domain requiring continual opportunity scanning, personalized evaluation, artifact generation, and human-in-the-loop action).

In its current form, this playbook explicitly incorporates exploration of lightweight multi-agent frameworks (OpenClaw, MemU, memsearch, BearClaw, 4-layer file-based architectures, Git-native patterns, CrewAI/LightAgent hybrids, Hermes/Icarus-Daedalus, etc.), file/Markdown-first memory systems, Chroma + small specialized LLMs, and edge-hardware deployment (Raspberry Pi, Mac Mini M4, etc.). The emphasis is on low-resource, human-readable, Git-syncable, cross-session persistence that echoes the Icarus Memory Protocol’s ultra-minimal fabric tiering.

### Step 1: Clone, Run, and Document the Original System (Immersion Phase)
- Clone `https://github.com/santifer/career-ops`, follow `docs/SETUP.md` exactly, configure `profile.yml`, `portals.yml`, and your `cv.md`.
- Execute every mode (`/career-ops`, `scan`, `batch`, `pdf`, `apply`, `pipeline`, etc.) on 20–50 real opportunities. Capture screenshots, logs, outputs, and timing.
- Create a personal “CareerOps Anatomy Notebook” (Markdown + Obsidian) mapping: 14 modes → data flows → file artifacts (TSV trackers, reports/, output/, jds/) → Playwright scraping → Claude Code orchestration → HITL gates.
- **Why?** You cannot generalize what you haven’t run end-to-end. This reveals the file-based “memory” (no vector DB, just Markdown/TSV/YAML) and the conductor-worker batch pattern that already aligns with Icarus-Daedalus critique loops.

### Step 2: Reverse-Engineer Core Abstractions & Pain Points (Dissection Phase)
- Identify the 5 universal primitives that make Career-Ops powerful:
  1. Opportunity Ingestion (URL/JD scanner).
  2. Multi-dimensional Evaluation (10 weighted criteria → A-F score).
  3. Personalized Artifact Generation (resume/PDF per opportunity).
  4. Persistent Tracking & Deduplication (file-based history).
  5. HITL Orchestration + Action Loops (apply, negotiate, contact).
- Catalog limitations: Claude Code dependency, Node/Playwright heaviness on edge devices, lack of true long-term cross-session memory evolution, single-LLM reliance.
- Map these primitives to your broader use cases (e.g., “startup pitch deck” instead of “resume,” “philanthropy impact score” instead of “role match”).
- **Output:** A reusable “Opportunity Engine Blueprint” diagram (Mermaid or draw.io) showing what is domain-agnostic vs. job-specific.

### Step 3: Abstract into a Domain-Agnostic Framework (Generalization Design Phase)
- Define the general problem as: “Continual, low-resource discovery + evaluation + personalization + pursuit of high-signal opportunities in any domain.”
- Create a canonical 6-layer architecture (inspired by Career-Ops but extensible):
  1. Scanner Layer (APIs, web scraping, RSS, tweets, LinkedIn).
  2. Memory Layer (file/MD-first, tiered hot/warm/cold per Icarus Protocol).
  3. Evaluator Layer (small specialized LLMs or role-based agents).
  4. Generator Layer (personalized artifacts: pitch decks, grant proposals, etc.).
  5. Orchestrator Layer (conductor + critic loops).
  6. Action/HITL Layer (calendar, email, Git commits, etc.).
- Document success metrics (e.g., signal-to-noise ratio, hours saved, opportunity quality score).

### Step 4: Inventory & Benchmark Alternative Multi-Agent & Memory Frameworks (Alternatives Audit Phase)
- Systematically compare the alternatives you listed against Career-Ops primitives:
  - **File/MD-first champions**: OpenClaw (RPi-native, MEMORY.md + SOUL.md, direct agent-to-agent messaging), MemU (hierarchical MD folders, autonomous organize/retrieve, no forced embeddings), memsearch (Markdown source-of-truth), BearClaw (JSON + MD sessions), 4-layer file architectures, Git-native DiffMem.
  - **Role/critique-loop fits**: CrewAI (easy creator + critic crews), LightAgent (mem0 + ToT + self-learning), Hermes/Icarus-Daedalus (native persistent memory + plugin model).
  - **Heavier but useful**: AutoGen/LangGraph (reflection patterns, file-backed checkpoints possible).
- Score each on: Raspberry Pi / Mac Mini M4 compatibility, token efficiency, human readability, Git sync, cross-platform recall, and ease of replacing Claude Code with small LLMs.
- **Deliverable:** A comparison matrix (Markdown table) + short proof-of-concept fork of 2–3 top candidates (e.g., OpenClaw + MemU).

### Step 5: Choose & Prototype Memory + Small-LLM Stack (Lightweight Foundation Phase)
- Prioritize your stated preference: Chroma (optional lightweight vector layer) + small specialized models (e.g., Phi-3, Gemma-2, or quantized Llama-3.1-8B) hosted locally via Ollama/LM Studio on Pi/M4.
- Implement or adapt the Icarus Memory Protocol (50-line bash/Python fabric tier) as the single source of truth.
- Add MemU or memsearch for hierarchical MD auto-organization and dual-mode retrieval (keyword + LLM).
- Test continual 24/7 operation: cron + headless agents scraping Indeed API, X/Twitter (via x_keyword_search patterns), LinkedIn (where possible), company RSS, etc.
- Validate: runs on <4 GB RAM, survives reboots, human-editable via Obsidian/Git.

### Step 6: Rebuild the Evaluator & Generator Layers with New Frameworks (Core Engine Rebuild Phase)
- Port the 10-dimension scoring and archetype detection into role-based agents (e.g., Researcher + Critic + Personalizer in OpenClaw or CrewAI).
- Replace Claude-specific modes with pluggable skills (Hermes-style) or LightSwarm agents.
- Generalize artifact generation: use templates + small LLM prompting for startup one-pagers, philanthropy proposals, etc.
- Introduce creator-critic loops explicitly (mirroring Icarus-Daedalus) for self-review of evaluations.

### Step 7: Integrate Continual Scanning & Cross-Session Collaboration (Always-On Phase)
- Build a lightweight scanner daemon (Playwright or simpler requests + RSS) that feeds opportunities into the fabric memory tier.
- Add agent-to-agent handoffs (e.g., Scanner → Evaluator → Generator) via Markdown refs or OpenClaw messaging.
- Enable cross-device sync (Git pull/push or simple rsync) so a Pi runs 24/7 scanning while your M4 does heavy personalization.
- Add simple triggers: new tweet/LinkedIn post → opportunity candidate → auto-evaluation.

### Step 8: Add Domain-Specific Modules & HITL Interfaces (Expansion Phase)
- Create pluggable “Opportunity Domains”:
  - Job Search (original Career-Ops).
  - Startup Foundation (evaluate founders, traction, market, cap table).
  - Venture Philanthropy (impact scoring, alignment with your values, grant readiness).
- Build minimal HITL dashboards (reuse or adapt the Go TUI, or simple web UI via BearClaw).
- Include negotiation/outreach generators for each domain.

### Step 9: Iterate, Measure, and Harden (Validation & Self-Improvement Phase)
- Run parallel A/B tests: original Career-Ops vs. your generalized version on the same opportunity set.
- Track quantitative metrics (opportunities processed/day, false-positive rate, edge-hardware uptime) and qualitative (your review time saved).
- Implement self-improvement: agents periodically review past decisions and update their own Markdown skill files or profile (Hermes/MemU style).
- Add resilience: retry logic, rate-limit handling, Git-backed versioning of memory.

### Step 10: Document, Open-Source, and Evolve the Generalized System (Legacy & Community Phase)
- Produce a “Generalized Opportunity Engine” repo with clear setup for Pi/M4, full Markdown-based memory protocol, and domain modules.
- Write a case-study mirror of santifer.io/career-ops-system but for your generalized version.
- Release under MIT, invite community extensions (new domains, new small models, new frameworks).
- Schedule quarterly “memory audits” where you (or a curator agent) prune/reorganize the fabric tiers.

**Expected Outcome After 10 Steps**  
You will have a production-grade, edge-deployable, continually running opportunity engine that is lighter than the original Career-Ops, more general-purpose, and fully aligned with the file-first, low-infra, Icarus-Daedalus philosophy you admire. It will run 24/7 on minimal hardware, use small specialized models where possible, and scale to any opportunity domain while keeping everything human-readable and Git-syncable.

---

[Santifer's AI-powered job search pipeline was built](https://santifer.io/career-ops-system) on Claude Code. Evaluate offers, generate tailored CVs, scan portals, and track everything -- powered by AI agents.

![Claude Code](https://img.shields.io/badge/Claude_Code-000?style=flat&logo=anthropic&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat&logo=playwright&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)

---

<p align="center">
  <img src="docs/demo.gif" alt="Career-Ops Demo" width="800">
</p>

## What Is This

Career-Ops turns Claude Code into a full job search command center. Instead of manually tracking applications in a spreadsheet, you get an AI-powered pipeline that:

- **Evaluates offers** with a structured A-F scoring system (10 weighted dimensions)
- **Generates tailored PDFs** -- ATS-optimized CVs customized per job description
- **Scans portals** automatically (Greenhouse, Ashby, Lever, company pages)
- **Processes in batch** -- evaluate 10+ offers in parallel with sub-agents
- **Tracks everything** in a single source of truth with integrity checks

> **Important: This is NOT a spray-and-pray tool.** Career-ops is a filter -- it helps you find the few offers worth your time out of hundreds. The system strongly recommends against applying to anything scoring below 4.0/5. Your time is valuable, and so is the recruiter's. Always review before submitting.

Career-ops is agentic: Claude Code navigates career pages with Playwright, evaluates fit by reasoning about your CV vs the job description (not keyword matching), and adapts your resume per listing.

> **Heads up: the first evaluations won't be great.** The system doesn't know you yet. Feed it context -- your CV, your career story, your proof points, your preferences, what you're good at, what you want to avoid. The more you nurture it, the better it gets. Think of it as onboarding a new recruiter: the first week they need to learn about you, then they become invaluable.

Built by someone who used it to evaluate 740+ job offers, generate 100+ tailored CVs, and land a Head of Applied AI role. [Read the full case study](https://santifer.io/career-ops-system).

## Features

| Feature | Description |
|---------|-------------|
| **Auto-Pipeline** | Paste a URL, get a full evaluation + PDF + tracker entry |
| **6-Block Evaluation** | Role summary, CV match, level strategy, comp research, personalization, interview prep (STAR+R) |
| **Interview Story Bank** | Accumulates STAR+Reflection stories across evaluations -- 5-10 master stories that answer any behavioral question |
| **Negotiation Scripts** | Salary negotiation frameworks, geographic discount pushback, competing offer leverage |
| **ATS PDF Generation** | Keyword-injected CVs with Space Grotesk + DM Sans design |
| **Portal Scanner** | 45+ companies pre-configured (Anthropic, OpenAI, ElevenLabs, Retool, n8n...) + custom queries across Ashby, Greenhouse, Lever, Wellfound |
| **Batch Processing** | Parallel evaluation with `claude -p` workers |
| **Dashboard TUI** | Terminal UI to browse, filter, and sort your pipeline |
| **Human-in-the-Loop** | AI evaluates and recommends, you decide and act. The system never submits an application -- you always have the final call |
| **Pipeline Integrity** | Automated merge, dedup, status normalization, health checks |

## Quick Start

```bash
# 1. Clone and install
git clone https://github.com/santifer/career-ops.git
cd career-ops && npm install
npx playwright install chromium   # Required for PDF generation

# 2. Configure
cp config/profile.example.yml config/profile.yml  # Edit with your details
cp templates/portals.example.yml portals.yml       # Customize companies

# 3. Add your CV
# Create cv.md in the project root with your CV in markdown

# 4. Personalize with Claude
claude   # Open Claude Code in this directory

# Then ask Claude to adapt the system to you:
# "Change the archetypes to backend engineering roles"
# "Translate the modes to English"
# "Add these 5 companies to portals.yml"
# "Update my profile with this CV I'm pasting"

# 5. Start using
# Paste a job URL or run /career-ops
```

> **The system is designed to be customized by Claude itself.** Modes, archetypes, scoring weights, negotiation scripts -- just ask Claude to change them. It reads the same files it uses, so it knows exactly what to edit.

See [docs/SETUP.md](docs/SETUP.md) for the full setup guide.

## Usage

Career-ops is a single slash command with multiple modes:

```
/career-ops                → Show all available commands
/career-ops {paste a JD}   → Full auto-pipeline (evaluate + PDF + tracker)
/career-ops scan           → Scan portals for new offers
/career-ops pdf            → Generate ATS-optimized CV
/career-ops batch          → Batch evaluate multiple offers
/career-ops tracker        → View application status
/career-ops apply          → Fill application forms with AI
/career-ops pipeline       → Process pending URLs
/career-ops contacto       → LinkedIn outreach message
/career-ops deep           → Deep company research
/career-ops training       → Evaluate a course/cert
/career-ops project        → Evaluate a portfolio project
```

Or just paste a job URL or description directly -- career-ops auto-detects it and runs the full pipeline.

## How It Works

```
You paste a job URL or description
        │
        ▼
┌──────────────────┐
│  Archetype       │  Classifies: LLMOps / Agentic / PM / SA / FDE / Transformation
│  Detection       │
└────────┬─────────┘
         │
┌────────▼─────────┐
│  A-F Evaluation   │  Match, gaps, comp research, STAR stories
│  (reads cv.md)    │
└────────┬─────────┘
         │
    ┌────┼────┐
    ▼    ▼    ▼
 Report  PDF  Tracker
  .md   .pdf   .tsv
```

## Pre-configured Portals

The scanner comes with **45+ companies** ready to scan and **19 search queries** across major job boards. Copy `templates/portals.example.yml` to `portals.yml` and add your own:

**AI Labs:** Anthropic, OpenAI, Mistral, Cohere, LangChain, Pinecone
**Voice AI:** ElevenLabs, PolyAI, Parloa, Hume AI, Deepgram, Vapi, Bland AI
**AI Platforms:** Retool, Airtable, Vercel, Temporal, Glean, Arize AI
**Contact Center:** Ada, LivePerson, Sierra, Decagon, Talkdesk, Genesys
**Enterprise:** Salesforce, Twilio, Gong, Dialpad
**LLMOps:** Langfuse, Weights & Biases, Lindy, Cognigy, Speechmatics
**Automation:** n8n, Zapier, Make.com
**European:** Factorial, Attio, Tinybird, Clarity AI, Travelperk

**Job boards searched:** Ashby, Greenhouse, Lever, Wellfound, Workable, RemoteFront

## Dashboard TUI

The built-in terminal dashboard lets you browse your pipeline visually:

```bash
cd dashboard
go build -o career-dashboard .
./career-dashboard
```

Features: 6 filter tabs, 4 sort modes, grouped/flat view, lazy-loaded previews, inline status changes.

## Project Structure

```
career-ops/
├── CLAUDE.md                    # Agent instructions
├── cv.md                        # Your CV (create this)
├── article-digest.md            # Your proof points (optional)
├── config/
│   └── profile.example.yml      # Template for your profile
├── modes/                       # 14 skill modes
│   ├── _shared.md               # Shared context (customize this)
│   ├── oferta.md                # Single evaluation
│   ├── pdf.md                   # PDF generation
│   ├── scan.md                  # Portal scanner
│   ├── batch.md                 # Batch processing
│   └── ...
├── templates/
│   ├── cv-template.html         # ATS-optimized CV template
│   ├── portals.example.yml      # Scanner config template
│   └── states.yml               # Canonical statuses
├── batch/
│   ├── batch-prompt.md          # Self-contained worker prompt
│   └── batch-runner.sh          # Orchestrator script
├── dashboard/                   # Go TUI pipeline viewer
├── data/                        # Your tracking data (gitignored)
├── reports/                     # Evaluation reports (gitignored)
├── output/                      # Generated PDFs (gitignored)
├── fonts/                       # Space Grotesk + DM Sans
├── docs/                        # Setup, customization, architecture
└── examples/                    # Sample CV, report, proof points
```

## Tech Stack

![Claude Code](https://img.shields.io/badge/Claude_Code-000?style=flat&logo=anthropic&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat&logo=playwright&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white)
![Bubble Tea](https://img.shields.io/badge/Bubble_Tea-FF75B5?style=flat&logo=go&logoColor=white)

- **Agent**: Claude Code with custom skills and modes
- **PDF**: Playwright/Puppeteer + HTML template
- **Scanner**: Playwright + Greenhouse API + WebSearch
- **Dashboard**: Go + Bubble Tea + Lipgloss (Catppuccin Mocha theme)
- **Data**: Markdown tables + YAML config + TSV batch files

## Also Open Source

- **[cv-santiago](https://github.com/santifer/cv-santiago)** -- The portfolio website (santifer.io) with AI chatbot, LLMOps dashboard, and case studies. If you need a portfolio to showcase alongside your job search, fork it and make it yours.

## About the Author

I'm Santiago -- Head of Applied AI, former founder (built and sold a business that still runs with my name on it). I built career-ops to manage my own job search. It worked: I used it to land my current role.

My portfolio and other open source projects → [santifer.io](https://santifer.io)

☕ [Buy me a coffee](https://buymeacoffee.com/santifer) if career-ops helped your job search.

## License

MIT

---

# :es: Version en Español

## Que es esto

Career-Ops convierte Claude Code en un centro de mando de busqueda de empleo. En vez de trackear aplicaciones en un spreadsheet, tienes un pipeline AI que:

- **Evalua ofertas** con scoring estructurado A-F (10 dimensiones ponderadas)
- **Genera PDFs personalizados** -- CVs ATS-optimizados por oferta
- **Escanea portales** automaticamente (Greenhouse, Ashby, Lever, webs de empresas)
- **Procesa en batch** -- evalua 10+ ofertas en paralelo con sub-agentes
- **Trackea todo** en una fuente de verdad unica con checks de integridad

> **Importante: Esto NO es para spamear empresas.** Career-ops es un filtro -- te ayuda a encontrar las pocas ofertas que merecen tu tiempo entre cientos. El sistema recomienda encarecidamente no aplicar a nada por debajo de 4.0/5. Tu tiempo es valioso, y el del recruiter tambien. Siempre revisa antes de enviar.

> **Aviso: las primeras evaluaciones no seran buenas.** El sistema no te conoce todavia. Dale contexto -- tu CV, tu historia profesional, tus proof points, tus preferencias, en que eres bueno, que quieres evitar. Cuanto mas lo nutras, mejor filtra. Piensa en ello como hacer onboarding a un recruiter nuevo: la primera semana necesita conocerte, luego se vuelve invaluable.

Construido por alguien que lo uso para evaluar 740+ ofertas, generar 100+ CVs personalizados, y conseguir un rol de Head of Applied AI. [Lee el case study completo](https://santifer.io/career-ops).

## Inicio rapido

```bash
# 1. Clonar
git clone https://github.com/santifer/career-ops.git
cd career-ops && npm install

# 2. Configurar
cp config/profile.example.yml config/profile.yml  # Editar con tus datos
cp templates/portals.example.yml portals.yml       # Personalizar empresas

# 3. Añadir tu CV
# Crear cv.md en la raiz del proyecto con tu CV en markdown

# 4. Personalizar con Claude
claude   # Abrir Claude Code en este directorio

# Pidele a Claude que adapte el sistema a ti:
# "Cambia los arquetipos a roles de backend"
# "Traduce los modes a ingles"
# "Añade estas empresas a portals.yml"
# "Actualiza mi perfil con este CV que te pego"

# 5. Usar
# Pega una URL de oferta o ejecuta /career-ops
```

> **El sistema esta diseñado para que Claude lo personalice.** Modes, arquetipos, scoring, scripts de negociacion -- solo pidelo. Claude lee los mismos archivos que usa, asi que sabe exactamente que editar.

Guia completa en [docs/SETUP.md](docs/SETUP.md).

## Portales incluidos

El scanner viene con **45+ empresas** pre-configuradas y **19 queries** en los principales portales de empleo. Copia `templates/portals.example.yml` a `portals.yml` y añade las tuyas:

**AI Labs:** Anthropic, OpenAI, Mistral, Cohere, LangChain, Pinecone
**Voice AI:** ElevenLabs, PolyAI, Parloa, Hume AI, Deepgram, Vapi, Bland AI
**Plataformas AI:** Retool, Airtable, Vercel, Temporal, Glean, Arize AI
**Contact Center:** Ada, LivePerson, Sierra, Decagon, Talkdesk, Genesys
**Enterprise:** Salesforce, Twilio, Gong, Dialpad
**LLMOps:** Langfuse, Weights & Biases, Lindy, Cognigy, Speechmatics
**Automatizacion:** n8n, Zapier, Make.com
**Europa:** Factorial, Attio, Tinybird, Clarity AI, Travelperk

**Portales de empleo:** Ashby, Greenhouse, Lever, Wellfound, Workable, RemoteFront

## Uso

Career-ops es un unico slash command con multiples modos:

```
/career-ops                → Mostrar todos los comandos
/career-ops {pega un JD}   → Pipeline completo (evaluar + PDF + tracker)
/career-ops scan           → Escanear portales
/career-ops pdf            → Generar CV ATS-optimizado
/career-ops batch          → Evaluar ofertas en batch
/career-ops tracker        → Ver estado de aplicaciones
/career-ops apply          → Rellenar formularios con IA
/career-ops pipeline       → Procesar URLs pendientes
/career-ops contacto       → Mensaje LinkedIn outreach
/career-ops deep           → Research profundo de empresa
```

O simplemente pega una URL o descripcion de oferta -- career-ops la detecta y ejecuta el pipeline completo.

## Tambien Open Source

- **[cv-santiago](https://github.com/santifer/cv-santiago)** -- El portfolio (santifer.io) con chatbot IA, dashboard LLMOps y case studies. Si necesitas un portfolio para acompañar tu busqueda de empleo, echale un vistazo.

## Documentacion

- [SETUP.md](docs/SETUP.md) -- Guia de instalacion
- [CUSTOMIZATION.md](docs/CUSTOMIZATION.md) -- Como personalizar
- [ARCHITECTURE.md](docs/ARCHITECTURE.md) -- Como funciona el sistema

☕ [Invitame a un cafe](https://buymeacoffee.com/santifer) si career-ops te ayudo en tu busqueda.

## Let's Connect

[![Website](https://img.shields.io/badge/santifer.io-000?style=for-the-badge&logo=safari&logoColor=white)](https://santifer.io)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/santifer)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:hola@santifer.io)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy_Me_a_Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/santifer)
