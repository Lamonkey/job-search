## 2026-04-07 — Sanas Member of Technical Staff (Data Acquisition)

**Gaps filled:** Web crawling infrastructure at scale, audio processing tooling (ffmpeg/librosa/torchaudio/sox), audio data quality filtering (SNR/clipping/codec artifacts), data versioning (DVC)

**Projects designed:**
- AudioForge (Audio Corpus Quality & Versioning Pipeline): Python + librosa + torchaudio + ffmpeg + sox + DVC + S3 + PostgreSQL + Docker — automated (no user feedback)
- WebHarvest (Distributed Web Crawling & Content Extraction Platform): Python + Celery + Redis + BeautifulSoup + trafilatura + S3 + PostgreSQL + Docker — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: AudioForge focused on what audio processing tools solve (turning raw heterogeneous audio into clean, versioned training corpora) rather than mirroring Sanas's accent translation product. Domain used: public speech corpus processing (Common Voice, LibriSpeech) — neutral. WebHarvest focused on what crawling infrastructure solves (discovering, fetching, extracting, cataloging web content at scale with politeness and fault tolerance). Domain used: generic public web content collection. Both extend Jesse's existing Python/AWS/S3/PostgreSQL/Docker stack naturally.

## 2026-04-02 — bet365 Senior Full Stack Engineer

**Gaps filled:** Redux / advanced state management, scale/systems thinking

**Projects designed:**
- LiveBet Dashboard: React + TypeScript + Redux Toolkit + Node.js + WebSocket + PostgreSQL + Docker — rejected (user feedback: don't mirror target company's domain; focus on what the tool solves)
- CalcSheet (Spreadsheet Engine): React + TypeScript + Redux Toolkit — accepted (exercises normalized state, dependency graphs, undo/redo, memoized selectors — genuinely needs Redux)
- QSim (Queue Simulator): TypeScript CLI — accepted (math-based queuing theory simulation, no infra needed — demonstrates systems thinking at scale)

**Feedback:** User strongly prefers projects designed around the problem a tool solves, not projects that mirror the target company's product. Domain-mirroring looks like "you Googled what they do." For scale gaps, pure mathematical simulations (queuing theory, discrete-event simulation) are preferred over fake infrastructure. The queue sim is CLI-only, no dashboard — just math.

## 2026-04-02 — Loudr Agency AI Systems Engineer

**Gaps filled:** Slack bot/integration, CRM/PM tool API integration

**Projects designed:**
- SyncDesk (Cross-Tool Integration Bot): Python + Slack Bolt SDK + HubSpot API + Trello API + Docker Compose + Redis + PostgreSQL — accepted

**Feedback:** No feedback — accepted as designed. Project focused on the integration pattern (connecting disparate tools and surfacing data where teams work) rather than mirroring the agency domain.

## 2026-04-03 — Wipro Developer L3 (Contract)

**Gaps filled:** Ruby, Sinatra

**Projects designed:**
- DevTrail (Developer Work Log API): Ruby + Sinatra + ActiveRecord + PostgreSQL + React + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Sinatra solves (building lightweight modular REST APIs in Ruby) rather than mirroring Wipro's IT services domain. ActiveRecord standalone extends Jesse's existing PostgreSQL knowledge; React frontend extends existing React stack. Architecturally honest — Ruby/Sinatra/PostgreSQL/React is a common real-world pairing.

## 2026-04-03 — WorkWhile Growth Marketing Engineer

**Gaps filled:** Marketing automation platforms (Braze/Iterable/Klaviyo), SMS/email lifecycle automation, Performance ad tech (Pixels, CAPI, GTM), Amplitude analytics

**Projects designed:**
- CampaignFlow (Lifecycle Messaging Platform): Python + FastAPI + PostgreSQL + APScheduler + SendGrid + Twilio + Redis + React — automated (no user feedback)
- ConvertTrack (Server-Side Conversion Attribution API): TypeScript + Node.js + PostgreSQL + Redis + Amplitude HTTP API + Next.js demo storefront — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: projects focused on what the tools solve (lifecycle messaging automation, server-side attribution), not WorkWhile's gig worker domain. CampaignFlow covers Braze/Iterable internals; ConvertTrack covers CAPI + Amplitude instrumentation + GTM-style tag config. Both extend Jesse's existing Python/TypeScript/React/PostgreSQL stack naturally.

## 2026-04-03 — Encord Growth Engineer

**Gaps filled:** Dynamic landing experiences / personalization logic, experimentation infrastructure (feature flags, rigorous A/B testing), referral/sharing/expansion mechanics

**Projects designed:**
- ExperimentKit (Landing Page Personalization & Experimentation Engine): TypeScript + Next.js + Node.js + PostgreSQL + Redis + React — automated (no user feedback)
- ReferralLoop (Viral Referral & Expansion Engine): TypeScript + Node.js + PostgreSQL + Redis + React — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: ExperimentKit focused on what feature flags + experiment management solve (rigorous testing infrastructure) rather than Encord's AI data platform domain; used a generic SaaS marketing site as demo context. ReferralLoop focused on referral attribution and org-expansion mechanics (PLG expansion motion). Both extend Jesse's existing TypeScript/Node.js/PostgreSQL/React/Redis stack naturally. Groups personalization + experimentation into one project (they share the feature flag evaluation layer) and isolates referral mechanics as a separate project.

## 2026-04-03 — Dust Growth Engineer

**Gaps filled:** PostHog event instrumentation, Snowflake data warehouse, Metabase BI dashboards

**Projects designed:**
- FunnelStack (Product Analytics & Growth Data Stack): TypeScript + Next.js + posthog-js + PostHog Node SDK + Snowflake (warehouse export) + Metabase + Python simulator — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what the tools solve (end-to-end growth analytics pipeline from event capture to warehouse to BI dashboards) rather than mirroring Dust's AI OS domain. Domain used: SaaS developer tools analytics — neutral, different from target company. PostHog + Snowflake + Metabase is an architecturally honest pairing (PostHog natively exports to Snowflake; Metabase connects directly to Snowflake). Extends Jesse's existing TypeScript/Next.js stack naturally.

## 2026-04-03 — Juniper Square QA Automation Engineer II

**Gaps filled:** Locust (load/performance testing), GraphQL API testing

**Projects designed:**
- LoadProbe (API Performance & Load Testing Suite): Python + Locust + Pytest + HTTPX + FastAPI target + PostgreSQL + GitHub Actions + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Locust solves (verifying API SLAs under concurrent load) rather than mirroring Juniper Square's private equity/real estate domain. Domain used: task management API (neutral, self-generating data). Grouped Locust + GraphQL API testing + REST validation into one project (they all target the same API). Extends Jesse's existing Python/Pytest/FastAPI/PostgreSQL/GitHub Actions stack naturally.

## 2026-04-03 — FORSHAW Software Developer

**Gaps filled:** Ruby on Rails (service objects, policy-based auth, Rails conventions), GraphQL (graphql-ruby, typed schema, mutations), Sidekiq (background jobs, Redis queue, scheduled work)

**Projects designed:**
- TrackBill (Freelance Invoicing API): Ruby on Rails 8 + graphql-ruby + Sidekiq + Devise/JWT + Pundit + PostgreSQL + Redis + Docker Compose + RSpec — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Rails+GraphQL+Sidekiq solve (structured service-layer API with async processing) rather than mirroring FORSHAW's pest/distribution domain. Domain used: freelance invoicing — neutral, different from target company. Rails+graphql-ruby+Sidekiq+Redis is an architecturally honest pairing (the standard Rails async stack). Extends Jesse's existing Ruby (Sinatra/DevTrail) and PostgreSQL knowledge. Groups Rails, GraphQL, and Sidekiq into one project because they're genuinely co-located in the FORSHAW codebase and belong together architecturally.

## 2026-04-03 — FORSHAW Software Developer (paylocity.md)

**Gaps filled:** Ruby on Rails, GraphQL APIs (JWT auth), Sidekiq, Heroku

**Projects designed:**
- StoreFlow (Rails 8 + GraphQL Order & Inventory API): Ruby on Rails 8 + graphql-ruby + PostgreSQL + Sidekiq + Redis + RSpec + Heroku + GitHub Actions + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Rails + graphql-ruby solve (typed schema, resolver organization, service objects, background job integration) rather than FORSHAW's pest control domain. Domain used: small business supply/catalog management — neutral, different from target company. Rails + GraphQL + Sidekiq + Redis is architecturally honest (graphql-ruby and Sidekiq are the standard Rails ecosystem choices). Heroku added as a bonus gap (JD lists it). Extends Jesse's existing Ruby (DevTrail), PostgreSQL, and RSpec knowledge naturally.

## 2026-04-03 — DoiT Applied AI Engineer

**Gaps filled:** Firestore/Firebase, Google Cloud Platform (Cloud Run, Pub/Sub, IAM), MCP (Model Context Protocol), RAG

**Projects designed:**
- OpsFlow (Internal Task Routing & Async Automation): Next.js + TypeScript + Firestore + Firebase Admin SDK + GCP Cloud Run + GCP Pub/Sub + GCP IAM + Firebase Auth + Docker — automated (no user feedback)
- ContextMCP (MCP Server with RAG-Backed Knowledge Base): TypeScript + @modelcontextprotocol/sdk + OpenAI embeddings API + pgvector + PostgreSQL + Anthropic Claude API + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: OpsFlow focused on what Firebase + GCP solve (real-time Firestore listeners, Pub/Sub async delivery, Cloud Run serverless workers, IAM scoping) rather than DoiT's cloud consulting domain. Domain used: generic internal task routing (neutral). ContextMCP focused on what MCP + RAG solve (connecting AI agents to external data sources via tool use) using public documentation as the corpus. Anthropic Claude API for re-ranking + MCP consumption mirrors the role's primary LLM stack. Both extend Jesse's existing TypeScript/Next.js/PostgreSQL/Docker stack naturally.

## 2026-04-03 — HERE (formerly OpenFin) Mid-Junior DevOps Engineer

**Gaps filled:** GitLab CI/CD (pipeline config, stages, artifacts, rules, Runner admin), PowerShell scripting (multi-platform build automation)

**Projects designed:**
- MultiCI (Cross-Platform Build Pipeline): TypeScript CLI build target + GitLab CI/CD (.gitlab-ci.yml) + GitLab Runner (Linux/Windows/macOS) + Bash + PowerShell + Docker + GitLab Container Registry — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what GitLab CI/CD solves (multi-platform build coordination with platform-specific runners and scripting) rather than mirroring HERE's enterprise browser domain. Domain used: generic CLI tooling (neutral, different from target company). GitLab CI + GitLab Runner + Bash + PowerShell is architecturally honest — multi-platform builds are the exact context where you need both scripting languages together. Extends Jesse's existing GitHub Actions, Node.js/TypeScript, and Docker knowledge; GitLab is the specific gap. Groups GitLab CI and PowerShell into one project because they co-occur naturally in multi-platform build pipelines.

## 2026-04-03 — Gem Software Engineer

**Gaps filled:** GraphQL in TypeScript/Node.js ecosystem (Apollo Server, Apollo Client, DataLoader)

**Projects designed:**
- ReviewHub (Community Media Review Platform): TypeScript + Apollo Server + Apollo Client + React + PostgreSQL + DataLoader + Vitest + Playwright — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Apollo Server/Apollo Client solve (typed GraphQL schema, normalized cache, N+1 prevention) rather than mirroring Gem's recruiting platform domain. Domain used: community media reviews — neutral, completely different from Gem's ATS/CRM recruiting space. TypeScript + Apollo Server + React + Apollo Client + PostgreSQL is architecturally honest (the standard full-stack GraphQL setup in the Node.js ecosystem). Extends Jesse's existing TypeScript/React/Node/PostgreSQL stack naturally. Jesse already has graphql-ruby schema design experience from Rails projects; this project adds the JavaScript-ecosystem-specific patterns (Apollo, DataLoader, Apollo Client cache).

## 2026-04-03 — Place Inc / Full Stack Engineer (Mobile + Ruby on Rails)

**Gaps filled:** EAS (Expo Application Services), TestFlight/Google Play Console mobile release management, Detox E2E testing

**Projects designed:**
- HomeTrack (project_hometrack_rn.md): React Native + Expo + EAS + Detox — accepted as designed (automated run, no user feedback)

**Feedback:** No feedback — automated run. Project groups EAS, mobile release pipeline, and Detox into a single React Native app in the real estate domain (domain-relevant to Place Inc's Brivity products).

## 2026-04-03 — HERE Mid-Junior DevOps Engineer

**Gaps filled:** GitLab CI/CD, PowerShell scripting (multi-platform builds)

**Projects designed:**
- MultiShip (Cross-Platform GitLab CI/CD Release Pipeline): TypeScript CLI + GitLab CI/CD (YAML, stages, jobs, artifacts, rules, needs, runner config) + PowerShell (Windows build scripts, nvm-windows, artifact packaging, Get-FileHash) + Bash (Linux/macOS builds) + S3 (release channel promotion) — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: GitLab CI/CD + PowerShell belong in the same project because multi-platform CI is their natural joint context (Windows job uses PowerShell, Linux/macOS use Bash, both coordinated by GitLab CI YAML). Domain used: cross-platform TypeScript CLI tool — neutral, not mirroring HERE's enterprise browser product; focused on what GitLab CI/CD solves (coordinating parallel platform-specific builds and stage-gated deployments). Extends Jesse's existing TypeScript/Node.js stack naturally.

## 2026-04-03 — Nordstrom Delivery Platform Software Engineer 1

**Gaps filled:** Temporal workflow orchestration

**Projects designed:**
- DeployGate (Deployment Pipeline Orchestration): Go (net/http) + Temporal Go SDK + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Temporal solves (durable execution for long-running, failure-prone deployment processes) rather than mirroring Nordstrom's retail domain. Domain used: generic SaaS deployment pipeline — neutral, completely different from Nordstrom's retail/e-commerce context. Go is a preferred JD skill and pairs naturally with Temporal (Go SDK is the primary Temporal SDK). Temporal is a standalone gap project — not bundled with other gaps since it's the only critical gap for this role.

## 2026-04-06 — Alteryx Software Engineer (Transport, Networking & Connectivity)

**Gaps filled:** Networking fundamentals (HTTP/TLS, DNS, load balancing, proxy behavior), proxy/relay/data-plane service development in Go

**Projects designed:**
- ConnectProbe (Go Connectivity Relay & Health Monitor): Go (net/http, httputil.ReverseProxy, crypto/tls) + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what reverse proxies and connectivity relays solve (TLS termination, health-based routing, connection orchestration, reliability patterns) rather than mirroring Alteryx's analytics/data platform domain. Domain used: generic service connectivity — neutral, focused on networking primitives. Go is the JD's must-have language and pairs naturally with networking services (Go's net/http and crypto/tls are first-class). Groups Go + networking + proxy/relay into one project because they're inseparable for this role — the gap is specifically "Go networking services." Extends Jesse's existing Go knowledge from DeployGate into the networking domain.

## 2026-04-06 — DTN Software Engineer, AI Core Team

**Gaps filled:** Amazon Bedrock AgentCore, Strands Agents SDK

**Projects designed:**
- BedrockAgent (Multi-Step Research Agent on AWS Bedrock AgentCore): Python + Strands Agents SDK + Amazon Bedrock AgentCore + Bedrock Knowledge Bases + OpenSearch Serverless + Bedrock Guardrails + FastAPI + CloudWatch — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Bedrock AgentCore solves (managed agent deployment, session management, observability) and what Strands Agents solves (structured multi-step agent logic with typed tools) rather than mirroring DTN's agriculture/weather/energy domain. Domain used: generic research automation — neutral, completely different from DTN's operational decisioning context. Bedrock AgentCore + Strands Agents + Bedrock Knowledge Bases is architecturally honest — they're AWS's integrated agent stack designed to work together. Python is the primary SDK language for both. Groups both gaps into one project because Strands Agents is the SDK layer on top of Bedrock AgentCore — they're inseparable in practice. Extends Jesse's existing Python/FastAPI/AWS/agentic AI stack naturally.

## 2026-04-06 — Klaviyo Software Engineer II

**Gaps filled:** C, gdb, Linux kernels, Wireshark/libpcap, Splunk

**Unfillable gaps:** Spirent (proprietary network test hardware/software), pyATS (requires Cisco device access)

**Projects designed:**
- NetSieve (C Packet Capture & Network Analysis Pipeline): C + libpcap + Linux kernel module (netfilter) + gdb + Splunk HEC + Wireshark pcap export + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what these tools solve (low-level network capture, protocol dissection, kernel-level packet filtering, log analysis) rather than mirroring Klaviyo's marketing automation domain. C + libpcap + kernel modules + Splunk is an architecturally honest pairing — this is exactly how network monitoring tools work in production. Groups C, gdb, kernels, Wireshark, and Splunk into one project because they all live in the network monitoring/analysis domain. Spirent and pyATS are proprietary/infrastructure-dependent tools that cannot be demonstrated through a buildable project.

## 2026-04-06 — Gray Swan AI Software Engineer

**Gaps filled:** SvelteKit

**Projects designed:**
- AnnotateFlow (Document Annotation Dashboard): SvelteKit + TypeScript + FastAPI + MongoDB + Motor + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what SvelteKit solves (reactive UI, SSR, form actions, store-driven updates) rather than mirroring Gray Swan's AI safety domain. Domain used: document annotation — neutral, different from target company. SvelteKit + FastAPI + MongoDB is architecturally honest — it's the exact stack Gray Swan uses, and these technologies pair naturally (SvelteKit frontend, Python FastAPI backend, MongoDB for document-oriented storage). Extends Jesse's existing TypeScript/React/FastAPI/MongoDB knowledge into the SvelteKit ecosystem.

## 2026-04-07 — Adobe Data Science Engineer

**Gaps filled:** Tableau dashboards, Jupyter notebooks (data analysis workflow), Statistical analysis depth (z-tests, confidence intervals, anomaly detection, power analysis)

**Projects designed:**
- PlatformPulse (Product Usage Analytics & Dashboard Suite): Python + Jupyter + Pandas + NumPy + Matplotlib + PostgreSQL + Tableau Public — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Tableau + notebooks solve (exploratory analysis → dashboard communication workflow for product teams) rather than mirroring Adobe's creative tools domain. Domain used: generic SaaS platform usage analytics — neutral, completely different from Adobe's creative product context. Python + Jupyter + Pandas + PostgreSQL + Tableau is architecturally honest — this is the standard data analytics stack. Groups Tableau, notebooks, and statistics into one project because they're the natural workflow (explore in notebooks → visualize in Tableau → validate with statistics). Extends Jesse's existing Python/SQL/PostgreSQL/dashboard-building experience into the dedicated BI tool ecosystem.

## 2026-04-07 — Cognizant AI/ML Engineer

**Gaps filled:** PySpark, Databricks, Airflow, LlamaIndex, Knowledge graph, AI red teaming libraries

**Projects designed:**
- SparkLens (Distributed Analytics Pipeline): PySpark + Databricks + Airflow + MLlib + Parquet — automated (no user feedback)
- GraphRAG Explorer (Knowledge Graph-Augmented Retrieval): LlamaIndex + Neo4j + FastAPI + React + D3.js — automated (no user feedback)
- Adversarial LLM Lab (AI Red Teaming Suite): Python + Garak + Anthropic/OpenAI APIs + structured evaluation — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: SparkLens focused on what PySpark/Databricks/Airflow solve (distributed data processing + managed Spark + pipeline orchestration) rather than Cognizant's consulting domain. Domain used: transaction analytics — neutral. PySpark + Databricks + Airflow is an architecturally honest pairing (standard enterprise data engineering stack). GraphRAG Explorer focused on what LlamaIndex + knowledge graphs solve (structured entity-relationship retrieval for multi-hop reasoning) — LlamaIndex's KnowledgeGraphIndex makes this a natural pairing. Adversarial LLM Lab focused on what AI red teaming libraries solve (systematic LLM safety testing) — standalone gap because red teaming is its own discipline. All three extend Jesse's existing Python/FastAPI/LLM/RAG stack naturally.

## 2026-04-07 — Baylor College of Medicine Research Assistant I (Epidemiology)

**Gaps filled:** GIS geocoding/tract linkage, R language for analysis, SDOH data integration

**Projects designed:**
- SDOH Geocoder (Social Determinants of Health Spatial Analysis Pipeline): Python + Census Geocoder API + GeoPandas + Shapely + R + tidyverse + sf + ggplot2 + CDC PLACES dataset + TIGER/Line shapefiles + GitHub — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what geocoding → tract linkage → SDOH joins solve (the spatial data integration pipeline used in population health research) rather than mirroring BCM's specific research studies. Domain used: public health / SDOH analytics using freely available CDC PLACES and Census data — directly relevant to the role's domain (population health and outcomes research, SDOH), which is appropriate here because the project needs to feel like academic research data work, not just "GIS practice." ArcGIS Pro is not buildable (proprietary, costly license) — substituted the same spatial operation pattern using GeoPandas/Census TIGER, which demonstrates the same conceptual skill (geocoding, spatial joins, tract-level linkage). R + tidyverse + sf is architecturally honest for public health research analysis (R is the dominant language in epidemiology). Groups R, geocoding, and SDOH data integration into one project because they co-occur in exactly this research workflow.

## 2026-04-07 — Dandelion Health Software Engineer (De-Identification Pipelines)

**Gaps filled:** Clinical data de-identification, HIPAA Safe Harbor rules, biomedical NLP for PHI detection

**Projects designed:**
- PHI De-Identification Pipeline: Python + spaCy + scispaCy + Pandas + PostgreSQL + Parquet + Docker — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what PHI de-identification pipelines solve (HIPAA Safe Harbor compliance, NLP-based PHI detection in clinical notes, structured EMR field anonymization, QA validation) rather than mirroring Dandelion's specific health system partnerships. Data source: MIMIC-III annotations for QA validation + Synthea synthetic records for development — both freely available. Python + spaCy + Pandas is architecturally honest (the standard NLP + data processing stack). Parquet output included because Dandelion explicitly stores datasets as Parquet files. Snowflake/Redshift mentioned in output description to cover the JD's stated data stores. Extends Jesse's existing Python/Pandas/PostgreSQL/Docker stack into the healthcare data domain.

## 2026-04-07 — CU Boulder CubeSat Lab Professional Research Assistant (Embedded SW Engineer)

**Gaps filled:** C/C++ embedded programming, MPLAB X IDE / Microchip development environment, embedded subsystem firmware design, embedded debugging (SW + HW)

**Projects designed:**
- Embedded Subsystem Monitor (PIC32 Sensor Hub with MPLAB X): C + C++ + MPLAB X IDE + XC32 compiler + MPLAB Harmony + PICkit 3 debugger + MPLAB simulator + Python (pyserial host parser) — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Microchip/MPLAB tools solve (interrupt-driven firmware on a PIC32, ISR debugging, peripheral configuration via Harmony) rather than mirroring CU's CubeSat/space domain. Domain used: generic embedded subsystem health monitor (sensor polling, alarm thresholds, UART telemetry) — neutral, different from CubeSat flight software but architecturally analogous. C + C++ + MPLAB X + XC32 + Harmony is the exact Microchip embedded stack (architecturally honest). Python pyserial host parser extends Jesse's existing Python stack naturally. All three critical gaps (C/C++, MPLAB, embedded debugging) grouped into one project because they co-occur naturally in any Microchip-based firmware project.

## 2026-04-07 — NYU Langone MCIT ML Engineer

**Gaps filled:** Healthcare data structures (ICD-10, CPT codes, EHR tables), clinical ML benchmarking (Random Forest, XGBoost, model evaluation metrics), HIPAA-aware pipeline practices, Epic Clarity-style SQL patterns

**Projects designed:**
- ClinicalRisk (Healthcare EHR Analytics & ML Benchmarking Pipeline): Python + Pandas + scikit-learn (Random Forest) + XGBoost + PostgreSQL + SQL + Jinja2 + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what clinical data structures solve (ICD-10/CPT code engineering, EHR table query patterns, HIPAA-aware data handling) rather than mirroring NYU Langone's specific hospital systems. Domain used: CMS Medicare public claims data — freely available, clinically realistic, different from NYULH's specific EHR systems. Random Forest + XGBoost + Logistic Regression benchmarking is architecturally honest — this is the standard ML feasibility study pattern in healthcare AI. Groups clinical data, healthcare ML, and HIPAA awareness into one project because they co-occur in any healthcare analytics pipeline. Extends Jesse's existing Python/Pandas/scikit-learn/PostgreSQL/SQL stack into the clinical data domain.

## 2026-04-07 — SICK Software Engineer I (Machine Vision)

**Gaps filled:** Machine vision / computer vision, image processing (classical + ML-based), deep learning for object detection/inspection

**Projects designed:**
- VisionProbe (Industrial Object Detection & Inspection Pipeline): Python + OpenCV + YOLOv8 (Ultralytics) + FastAPI + React + Pytest + MVTec AD dataset — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what machine vision inspection systems solve (classical deterministic checks + DL flexible detection) rather than mirroring SICK's specific product line. Domain used: industrial surface defect inspection — relevant to SICK's industrial sensor domain but not product-specific. Python + OpenCV + YOLOv8 is architecturally honest (the standard machine vision stack for Python-based CV systems). C++ was identified as a gap but not filled with a separate project — Jesse's Python CV project demonstrates CV algorithm understanding and the role explicitly accepts Python. Extends Jesse's existing Python/FastAPI/React/Pytest stack into the CV domain. Data source: MVTec AD Dataset (free academic dataset) and Open Images V7 (freely downloadable) — no hand-built data required.

## 2026-04-07 — Miratech Google Dialogflow Engineer (Python)

**Gaps filled:** Google Dialogflow CX / CCAI (core platform gap), TTS/STT/SSML (voice channel), LLM playbook feature in Dialogflow CX

**Projects designed:**
- DialogBot (Conversational AI Bot with Google Dialogflow CX and LLM Playbooks): Python + FastAPI + Google Dialogflow CX + LLM Playbook + Cloud Run + GCP IAM + google-cloud-dialogflow-cx + SSML — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Dialogflow CX solves (structured multi-turn state machines with LLM playbook fallback for open-ended intent coverage) rather than mirroring Miratech's consulting domain. Domain used: generic customer support bot — neutral, different from target company's client contexts. Python + FastAPI + Dialogflow CX + Cloud Run is architecturally honest — this is the standard GCP-native webhook fulfillment pattern for CCAI bots. Extends Jesse's existing Python/FastAPI/GCP (Cloud Run, Pub/Sub) stack naturally. Groups Dialogflow CX, LLM playbooks, and SSML into one project because they're inseparable in a real CCAI bot deployment.

## 2026-04-07 — Johnson & Johnson Engineer, Automation Applications (OTTAVA Surgical Robotics)

**Gaps filled:** OPC UA / industrial networking, MQTT IIoT integration, OEE computation, alarm analytics

**Projects designed:**
- IIoT Monitor (OPC UA / MQTT Equipment Telemetry Dashboard): Python + python-opcua + Paho MQTT + TimescaleDB + FastAPI + React + Recharts + Mosquitto + Docker — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what OPC UA + MQTT solve (bridging machine-level OT signals to IT analytics layers) rather than mirroring J&J's surgical robotics product. Domain used: simulated industrial manufacturing cell — neutral, different from J&J's MedTech context. OPC UA + MQTT + TimescaleDB is architecturally honest — this is the standard IIoT monitoring stack for smart manufacturing. Groups OPC UA, MQTT, OEE, and alarm analytics into one project because they're naturally co-located in any equipment monitoring system. Extends Jesse's existing Python/FastAPI/PostgreSQL/React stack naturally; TimescaleDB is PostgreSQL-based so the extension is minimal. Note: PLC (Rockwell/Siemens), physical robotics (ABB/KUKA), machine safety standards (ISO 10218/13849), and medical device validation (IQ/OQ/PQ) are hardware-dependent or regulated-environment gaps that cannot be filled through buildable software projects.

## 2026-04-07 — PubMatic Forward Deployed Engineer

**Gaps filled:** Salesforce CRM API integration, Jira REST API integration

**Projects designed:**
- DealFlow Agent (AI-Powered Salesforce + Jira Workflow Agent): Python + FastAPI + simple-salesforce + atlassian-python-api + Anthropic Claude API + Slack Bolt SDK + PostgreSQL + Redis + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Salesforce + Jira solve (structured CRM and project tracking as enterprise integration targets) rather than mirroring PubMatic's ad tech / programmatic advertising domain. Domain used: generic deal-desk workflow automation — neutral, completely different from PubMatic's publisher monetization context. Salesforce + Jira + Slack + LLM enrichment is architecturally honest — this is the canonical sales ops integration stack, and an AI agent sitting in the middle (CRM trigger → LLM enrichment → Jira task creation → Slack notification) is exactly the FDE delivery pattern the JD describes. Python + FastAPI + simple-salesforce is the standard Salesforce integration approach in Python. Extends Jesse's existing Python/FastAPI/Claude API/PostgreSQL/Docker stack naturally. SyncDesk (HubSpot/Trello) already covered the generic CRM+PM API pattern; DealFlow adds Salesforce and Jira specifically, which the JD names explicitly.

## 2026-04-07 — Radware Security Analyst (ERT / DDoS Mitigation)

**Gaps filled:** Wireshark/tshark (required tool), Kali Linux (required tool), DDoS traffic analysis at L3/L4/L7 (required skill), BGP/OSPF routing context (required knowledge)

**Projects designed:**
- DDoS Traffic Analysis Lab: Python + Scapy + pyshark + tshark + Wireshark + Kali Linux + Bash + Mininet + Quagga (BGP/OSPF simulation) — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Wireshark + DDoS traffic analysis solve (understanding attack signatures at the packet level across L3/L4/L7) rather than mirroring Radware's product. Domain used: public PCAP datasets (CAIDA, CIC-DDoS2019) — neutral, industry-standard security research data. Kali Linux is the natural environment for this work (not a separate gap — it's the platform where these tools run). BGP/OSPF addressed as routing context (RTBH mitigation, IP spoofing enabling amplification) rather than a separate router-configuration project — because Jesse already has SDN topology research that covers routing state manipulation; this project connects the concepts. Groups Wireshark, DDoS L3/L4/L7, Kali, and BGP/OSPF context into one project because they all belong to the same SOC analyst workflow: capture → dissect → classify → mitigate recommendation.

## 2026-04-07 — HiddenLayer Software Engineer (Quality)

**Gaps filled:** Helm-based Kubernetes deployment testing

**Projects designed:**
- HelmGuard (Helm Chart Validation & Kubernetes Deployment Test Suite): Python + Pytest + Helm + kind (Kubernetes-in-Docker) + PyYAML + GitHub Actions — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Helm + kind solve (validating Kubernetes deployment manifests, upgrade paths, and failure modes before production) rather than mirroring HiddenLayer's adversarial AI domain. Domain used: generic Go microservice deployment — neutral, different from target company. Pytest + Helm + kind is architecturally honest — this is the standard Kubernetes deployment testing pattern (helm lint, helm template, kind cluster, kubectl). Extends Jesse's existing Kubernetes (Maple Growth) and Pytest experience naturally. Helm is the critical gap — tested in isolation as a standalone project rather than bundled with other gaps because it's the only critical gap for this role.

## 2026-04-07 — Sanmina Test Engineer (Flying Probe and ICT)

**Gaps filled:** SPC (Statistical Process Control), First Pass Yield (FPY) analysis, defect Pareto analysis, PCBA test data pipeline

**Projects designed:**
- PCB Yield Analytics (SPC & FPY Monitoring Dashboard): Python + NumPy + SciPy + Pandas + FastAPI + React + Recharts + PostgreSQL + Pytest — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what SPC + FPY analytics solve (detecting process drift, prioritizing defects, yield trend monitoring) rather than mirroring Sanmina's EMS manufacturing specifically. Domain used: PCBA ICT test data — appropriate because the role explicitly requires SPC and FPY skills in an electronics manufacturing context; using the same domain makes the project feel intentional. ICT (Keysight 3070), Flying Probe (Takaya), DFT, schematics reading, and electronic component knowledge are hardware-dependent gaps that cannot be filled through buildable software projects — noted but not designed against. Python + NumPy + SciPy is architecturally honest for SPC computation (no specialized SPC library needed — the math is implementable directly). Extends Jesse's existing Python/FastAPI/React/PostgreSQL/Pytest stack into the electronics manufacturing quality domain. Note: This is a stretch role — the core required skills (ICT, Flying Probe, DFT, schematics) are hardware gaps that no software project can realistically bridge. The FPY/SPC project adds the one buildable signal available.

## 2026-04-07 — STC / Software Development Engineer (NASA Edwards AFB)

**Gaps filled:** MATLAB/Simulink, control systems simulation, simulation environments

**Projects designed:**
- MATLAB/Simulink Altitude-Hold PID Controller: MATLAB + Simulink + controls theory — accepted as designed (automated run, no user feedback)

**Feedback:** No feedback — automated run. Designed one project covering MATLAB scripting + Simulink modeling + PID controls + V&V workflow. Domain chosen as aerospace (altitude-hold controller) to match the target role at NASA Edwards.

## 2026-04-07 — Optum/UHG Linux Systems Management Compliance Analyst

**Gaps filled:** Linux/Unix server hardening and administration, Sudo policies / Powerbroker-equivalent PAM, SELinux enforcing mode and policy management, Chef InSpec compliance-as-code, Active Directory authentication on Linux (SSSD/FreeIPA)

**Projects designed:**
- LinuxCompliance (Server Hardening & Compliance Automation Pipeline): Bash + Python + Vagrant + Ubuntu + PAM + SELinux + sudoers + Chef InSpec + SSSD + FreeIPA + GitHub Actions — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what compliance automation solves (turning CIS/NIST control checklists into executable hardening scripts and InSpec profiles that produce audit evidence) rather than mirroring Optum's healthcare IT domain. Domain used: generic enterprise Linux server compliance — neutral, not healthcare-specific. Linux hardening + PAM + SELinux + InSpec is architecturally honest — these co-occur in any enterprise compliance program and there's no natural way to split them into separate projects. SSSD + FreeIPA covers Active Directory authentication on Linux using open-source tooling (FreeIPA is the open-source equivalent of Active Directory, eliminates proprietary dependency). Extends Jesse's existing Bash scripting, Python, AWS/cloud infrastructure, and CI/CD stack naturally. Powerbroker (proprietary) covered as a concept via the equivalent sudo policy design pattern — this is the technically honest approach since Powerbroker wraps and extends sudo.

## 2026-04-07 — Sanmina AI Solutions Analyst

**Gaps filled:** Google Apps Script, Google Gemini API, Google Workspace automation

**Projects designed:**
- WorkspaceAI Toolkit (Google Apps Script + Gemini API suite): Google Apps Script + UrlFetchApp + Gemini 1.5 Pro + HTML Service + PropertiesService + Google Workspace APIs + clasp CLI + Python (google-api-python-client) — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Google Apps Script + Gemini API solve (embedding LLM intelligence directly into Google Workspace tools for knowledge-work automation) rather than mirroring Sanmina's manufacturing domain. Domain used: generic internal knowledge-work automation (Docs summarization, Sheets classification, Gmail drafting) — neutral, completely different from Sanmina's OEM manufacturing context. Google Apps Script + UrlFetchApp + Gemini API is architecturally honest — this is exactly how in-Workspace LLM integrations are built. Groups Apps Script, Gemini API, and Google Workspace automation into one project because they're inseparable in this development pattern. Python companion scripts (google-api-python-client) extend Jesse's existing Python stack naturally for the external API access pattern. Vertex AI not filled as a standalone project — listed in Skills based on GCP/Cloud Run experience; JD marks it "highly desirable" not required.

## 2026-04-07 — S&A Legal Management Services, Automation and Analytics Specialist

**Gaps filled:** n8n, Zapier (workflow automation tools), vLLM (local LLM serving), Tesseract (OCR), SQLite, PyPDF

**Projects designed:**
- LegalWorkflowAutomator (n8n-Based Process Automation): n8n + Docker + PostgreSQL + FastAPI + Python + SQLite — automated (no user feedback)
- LocalAI Doc Processor (vLLM + Tesseract + SQLite OCR Pipeline): Python + vLLM + Tesseract + PyPDF + OpenCV + SQLite + pandas + NumPy + FastAPI — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: LegalWorkflowAutomator focused on what n8n solves (trigger-based multi-service orchestration, comparable to Zapier) and used legal operations as the domain — fits S&A Legal's legal recoveries context without mirroring their specific products. SQLite included as the lightweight tracking database (architecturally appropriate for single-node n8n workflow state). LocalAI Doc Processor focused on what vLLM + Tesseract solve (locally-served LLM inference + OCR for document intelligence) rather than mirroring S&A's operations. UiPath not filled — it is a proprietary enterprise RPA platform that requires licensed software and cannot be realistically demonstrated via a buildable open-source project; n8n covers the same automation orchestration concept with open-source tooling. Zapier covered conceptually via n8n (same trigger-action model, same integration patterns). vLLM + Tesseract + SQLite + PyPDF + pandas + NumPy grouped into one project because they naturally co-occur in a local document intelligence pipeline. Projects extend Jesse's existing Python/FastAPI/Docker/pandas/NumPy stack naturally.

## 2026-04-07 — Aerodyne Industries Electrical Engineer Entry Level (KSC/COMET)

**Gaps filled:** RF telemetry / ground station systems (CCSDS), Unix test scripting

**Projects designed:**
- CCSDS Telemetry Ground Station Parser: Python + struct (binary parsing) + PostgreSQL + bash (Unix pipeline orchestration) + YAML config — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what CCSDS telemetry parsing solves (decoding a spacecraft downlink stream, detecting anomalies, logging engineering values for post-pass analysis) rather than mirroring Aerodyne's specific product or NASA's launch operations. Domain used: spacecraft telemetry ground station tooling — relevant to the C/T engineering group context but focused on the protocol/tool layer, not the customer's mission. CCSDS is the actual NASA standard, making the project credible and domain-honest. Unix bash scripting integrated naturally into the test orchestration layer (not as a separate project — it belongs architecturally with the telemetry pipeline). Extends Jesse's existing Python/PostgreSQL/Docker stack naturally.

## 2026-04-07 — Optum Senior Software Engineer (Python, Kubernetes)

**Gaps filled:** Snowflake (existing FunnelStack project covers it — no new project needed), pytest/TDD at Kubernetes level (existing HelmGuard project covers it)

**Projects designed:**
- No new projects — FunnelStack (Snowflake) and HelmGuard (Kubernetes + pytest) already covered all critical gaps

**Feedback:** Automated run — no user feedback. No new gap-filling projects required. Both critical gaps (Snowflake, pytest/TDD) were covered by existing in-progress projects in personal-infos.

## 2026-04-24 — Jackbox Games Entry-Level Full-Stack Engineer

**Gaps filled:** Vue 3 + NuxtJS 3, HLS live streaming protocol (WebRTC/HLS/RTMP)

**Projects designed:**
- StreamDeck (Live Session Viewer in NuxtJS + HLS): NuxtJS 3 + Vue 3 + TypeScript + hls.js + WebSocket + Go (net/http) + PostgreSQL + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what NuxtJS + HLS solve (SSR-enabled reactive frontend consuming a live media stream) rather than mirroring Jackbox's game shows domain. Domain used: game session telemetry viewer — neutral, different from Jackbox's party games while being contextually relevant (gaming + streaming). NuxtJS + hls.js is architecturally honest — this is the standard browser HLS player integration pattern. Go backend chosen because (a) it's a critical JD skill for Jesse to reinforce and (b) Go's net/http is commonly used to serve HLS segments. Groups Vue/NuxtJS and HLS into one project because a real streaming viewer requires both simultaneously. WebRTC/RTMP covered conceptually through hls.js + segment architecture (HLS is the most buildable of the three protocols; WebRTC and RTMP are noted in the resume as "HLS-based live streaming" but the architecture comment demonstrates awareness of the broader streaming landscape). Extends Jesse's existing Go (ConnectProbe/DeployGate) and TypeScript stack naturally.

## 2026-04-24 — Intrinsic Robotics / Frontend Software Engineer

**Gaps filled:** Three.js/WebGL 3D visualization, gRPC + Protobuf, Bazel build system, service workers / offline-first

**Projects designed:**
- Robot Workcell Viewer: Three.js + TypeScript + React + WebSocket — accepted (automated run)
- HMI Control Panel: React + TypeScript + gRPC-web + Protobuf + Bazel + Service Workers + Go backend — accepted (automated run)

**Feedback:** Automated run — no user feedback available. Grouped gRPC, Bazel, and service workers into one project because they co-occur naturally in a Google-stack HMI codebase. Kept Three.js separate because it covers a distinct visual skill (3D scene graph) that stands alone.

## 2026-04-24 — Defuse Labs Solutions Engineer

**Gaps filled:** Blockchain / NEAR Protocol integration, intent-driven architecture, on-chain SDK development

**Projects designed:**
- NEAR Intent Gateway (Cross-Chain Intent Execution Service): TypeScript + Node.js + @near-js/api + @near-js/providers + NEAR testnet + Jest + REST API — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what NEAR Intents / intent-driven architecture solves (decoupling desired outcomes from execution steps, solver competition, chain abstraction) rather than mirroring Defuse Labs' specific DeFi products. Domain used: generic token swap intent relay — neutral, focused on the architectural pattern rather than any specific liquidity pool. TypeScript + Node.js + @near-js SDK is architecturally honest — NEAR's primary developer SDK is JavaScript/TypeScript-first and this is how partners integrate with NEAR Intents. The solver simulation layer demonstrates understanding of the intent execution model at the conceptual level. Extends Jesse's existing TypeScript/Node.js/REST API/Jest stack naturally into the blockchain domain. Only one project designed because the blockchain gap is the only critical one; all other required skills (TypeScript, Node.js, API troubleshooting, distributed systems, observability) are already covered by Nyquiste experience.

## 2026-04-24 — LM Studio Product Engineer

**Gaps filled:** Swift, Objective-C, C++ (native macOS interop for desktop app development)

**Projects designed:**
- macOS Inference Bridge: Swift + Objective-C++ + C++ + Xcode + SwiftUI + Combine + XCTest — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Swift/ObjC/C++ interop solves (bridging performance-critical C++ code to a Swift UI layer via Objective-C++) rather than mirroring LM Studio's local inference product. Domain used: generic macOS menu bar app with text processing C++ stub — neutral, focused on the interop pattern. Swift + Objective-C++ + C++ is architecturally honest — this is the exact bridging stack used in any macOS app that integrates a C++ backend (game engines, audio/video tools, inference apps). Grouped Swift, ObjC, and C++ into one project because they're inseparable in this interop pattern — you can't demonstrate ObjC bridging without both C++ on one side and Swift on the other. Extends Jesse's existing React/TypeScript/Electron desktop app experience into the native macOS layer. Note: React, TypeScript, and Electron are the primary JD requirements and are already strong — Swift/ObjC/C++ are listed as "relevant experience," not hard requirements, so this project adds signal without being the centerpiece of the application.

## 2026-04-24 — Mightier Software Engineer – Product Engineering

**Gaps filled:** Django (ORM, DRF, admin, multi-tenancy, migrations)

**Projects designed:**
- B2B Account Portal (Django + DRF + PostgreSQL + Redis + AWS Elastic Beanstalk): Django ORM multi-tenant schema, DRF permission classes, admin customization, migrations, Docker Compose, S3 via django-storages — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Django + DRF solve (ORM-backed multi-tenant B2B API with admin panel) rather than mirroring Mightier's children's emotional health product. Domain used: generic B2B SaaS customer management — neutral, different from Mightier's family/health context, but role-relevant (JD explicitly describes building B2B customer management). Django + DRF + PostgreSQL + Redis is architecturally honest (the standard Django B2B SaaS stack). AWS Elastic Beanstalk included because JD calls for AWS. Extends Jesse's existing Python/PostgreSQL/Docker/AWS/React stack naturally. Note: existing project_portfolio_django.md provides minimal Django signal (config/deployment only) — B2B Account Portal adds the application layer (ORM design, DRF, admin, permission model).

## 2026-04-24 — Hagerty Software Engineer II (Digital Sales)

**Gaps filled:** C# / .NET (ASP.NET Core, Entity Framework Core, xUnit), MS SQL Server

**Projects designed:**
- No new project created — project_loan_application_api.md already exists and covers all critical gaps (C# ASP.NET Core + SQL Server + xUnit + React full-stack)

**Feedback:** Automated run — no user feedback. Applied pairing principle: Loan Application API focused on what ASP.NET Core + SQL Server solve (typed service-layer API with relational data modeling and .NET testing patterns) rather than mirroring Hagerty's insurance/automotive domain. Domain used: loan application workflow (financial services — relevant to the domain of financial web applications without copying Hagerty's specific product). C# + ASP.NET Core + Entity Framework Core + SQL Server + xUnit is architecturally honest (the canonical .NET web API stack). Extends Jesse's existing TypeScript/React stack into the .NET ecosystem — the full-stack integration (React frontend + C# API) is the natural bridge.

## 2026-04-24 — Toyota Financial Services Software Engineer (Junior)

**Gaps filled:** AWS Lambda, API Gateway, DynamoDB (serverless triad)

**Projects designed:**
- NotifyWave (Serverless Notification Service): TypeScript + Node.js + AWS Lambda + API Gateway + DynamoDB + SQS + AWS CDK + CloudWatch — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Lambda + API Gateway + DynamoDB solve (event-driven serverless HTTP services with low-latency NoSQL fan-out) rather than mirroring Toyota Financial Services' auto lending domain. Domain used: generic notification subscription service — neutral, focused on the serverless execution model and DynamoDB access patterns. TypeScript + Node.js Lambda is architecturally honest (Lambda's Node.js runtime is the primary TypeScript deployment target). AWS CDK in TypeScript extends Jesse's existing IaC knowledge (Terraform at Maple) into the CDK/CloudFormation family the JD explicitly lists as a bonus. Groups Lambda, API Gateway, and DynamoDB into one project because they're inseparable in the standard AWS serverless web API pattern. Extends Jesse's existing TypeScript/Node.js/AWS (Fargate/S3/SQS) stack naturally into the Lambda-specific execution model.

## 2026-04-25 — Majestic Photobooth Front-End Engineer

**Gaps filled:** Web Bluetooth / BLE hardware integration, Python/PySide6 + QML touchscreen UI

**Projects designed:**
- SensorLink (Web Bluetooth IoT Sensor Dashboard): React + TypeScript + Vite + Web Bluetooth API + Node.js BLE simulator — automated (no user feedback)
- WaitBoard (PySide6 Touchscreen Queue Display): Python + PySide6 + QML + QAbstractListModel + QThread + SQLite — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: SensorLink focused on what the Web Bluetooth API solves (browser-native hardware connectivity, GATT protocol lifecycle) rather than mirroring Majestic's photobooth domain. Domain used: IoT sensor monitoring (temperature/humidity). WaitBoard focused on what PySide6/QML solves (touchscreen-optimized kiosk UI, Qt threading model, declarative layout) rather than a photobooth simulator. Domain used: venue queue display. Both extend Jesse's existing React/TypeScript/Python stack naturally — SensorLink uses Vite + React, WaitBoard uses Python (already in Jesse's stack). React Native gap not treated as critical (already covered by HomeTrack, GamePulse, rn-consent in personal-infos).

## 2026-04-25 — Caesars Digital Web Engineer (React Native)

**Gaps filled:** Turborepo/Nx monorepo tooling, design tokens/theming system

**Projects designed:**
- TableScout (Restaurant Discovery App): Turborepo + React Native + Expo + TypeScript + design tokens + ThemeProvider + Storybook — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: TableScout focuses on what Turborepo and design tokens solve (cross-workspace dependency graphs, typed token layer, theming system) rather than mirroring Caesars Digital's gaming/sports-betting domain. Domain used: restaurant discovery — neutral consumer app. Project extends Jesse's existing React Native/Expo/TypeScript stack by adding the monorepo tooling and token system layers. Two gaps grouped into one coherent project because they naturally belong together (a shared component library in a Turborepo monorepo IS the design system use case).

## 2026-04-25 — Myriad Genetics Software Engineer III (Lab Automation)

**Gaps filled:** Django in lab automation context, LIMS-style scheduling, integration tests with simulated devices

**Projects designed:**
- LabScheduler (Workcell Sample Dispatch & LIMS Workflow Tracker): Django + DRF + PostgreSQL + Celery + React/TypeScript + Pytest (InstrumentSimulator) — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: project focused on what Django + device simulation testing solve (managing concurrent sample workflows, scheduling instrument dispatch, testing the full dispatch loop without physical hardware) rather than mirroring Myriad's specific genomics/cancer screening domain. Domain used: generic biological sample processing (lab automation) — relevant to the role's domain (lab software) but not product-specific. Django + DRF + Celery + PostgreSQL is architecturally honest (the standard Django async task stack). The InstrumentSimulator class pattern mirrors the testing approach described in the JD ("integration tests with real and simulated devices"). All existing critical technical gaps (Python, React, TypeScript, PostgreSQL, testing) are covered by Nyquiste experience; the new project fills Django specifically in a lab-relevant context. Extends Jesse's existing Python/Django (B2B Account Portal)/PostgreSQL/React/Celery stack naturally.

## 2026-04-25 — Impiricus Software Engineer (DevOps)

**Gaps filled:** AWS X-Ray distributed tracing, ECS (as named orchestrator), VPC/security groups/subnets, AWS Secrets Manager

**Projects designed:**
- VPCWatch (ECS + VPC + X-Ray + Secrets Manager + CloudWatch Alarms): Python + FastAPI + Terraform + GitHub Actions — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Domain: generic IT service registry (not mirroring Impiricus's pharma/HCP domain per pairing feedback). All four gaps cohere naturally into one project — ECS/Fargate naturally lives in a VPC, X-Ray traces ECS service requests, Secrets Manager injects credentials at ECS task level via IAM roles. Extends Jesse's existing Terraform + Fargate + Python stack naturally.

## 2026-04-25 — Guidehouse Junior Power Platform Developer (CDC)

**Gaps filled:** Power Apps (Canvas + Model-Driven), Power Automate, PowerFX, Dataverse security roles

**Projects designed:**
- Power Platform Service Request Manager: Power Apps Canvas + Model-Driven + Power Automate (multi-step approval + scheduled flow) + Dataverse (data modeling + security roles) + PowerFX — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Domain: facility service request management (not mirroring CDC/public health domain per prior feedback principle). Power Platform is a single-vendor ecosystem — all components paired naturally together. Jesse's existing TypeScript and workflow automation experience (n8n, queue-based workers) provided natural foundation. Noted this is a stretch application: JD requires 3 years Power Platform experience and US Citizenship contractually.

## 2026-04-25 — AxisCare Mid-Level Software Engineer

**Gaps filled:** PHP (full stack), MySQL

**Projects designed:**
- CareSchedule (PHP/Laravel Caregiver Shift Management API): PHP/Laravel + MySQL + React/TypeScript + PHPUnit + Docker — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Pairing principle applied: Laravel backend paired with React/TypeScript frontend (Jesse's existing stack), home care scheduling domain used to match AxisCare's exact market. MySQL included because the JD specifically names it alongside "or similar." Project extends Jesse's existing React/TypeScript knowledge rather than introducing a second unfamiliar ecosystem.

## 2026-04-25 — Twitch Software Engineer I, Ad Supply Experiences

**Gaps filled:** Golang, AWS Kinesis

**Projects designed:**
- AdStream (Go Ad Event Ingestion & Kinesis Pipeline): Go (Gin) + AWS Kinesis + TypeScript Lambda + DynamoDB + AWS CDK — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: Golang and Kinesis grouped into one project because Go + Kinesis is a natural pairing in AWS streaming architectures (Go SDK for Kinesis is first-class). Domain used: ad event ingestion / frequency capping — directly maps to Twitch Ads ad delivery systems without mirroring the company's exact product. Extends Jesse's existing TypeScript/Lambda/DynamoDB stack naturally (Lambda consumer in TypeScript, only the producer is new Go).

## 2026-04-25 — Acosta Group / AI Platform Engineer, Palantir Foundry

**Gaps filled:** Palantir Foundry / ontology-driven data modeling, retail domain context

**Projects designed:**
- RetailOntology: Python + DuckDB + Streamlit (ontology schema design, object transformation pipelines, analytics over object model, governance dashboard) — auto-accepted (automated run)

**Feedback:** No feedback — automated run, accepted as designed. Note: Palantir Foundry is a closed enterprise platform; project demonstrates the underlying ontology modeling concepts (typed object schemas, relationship links, pipeline-to-object transformation) using open tools.

## 2026-04-25 — eBay Platform Engineer – JavaScript Frameworks

**Gaps filled:** Webpack (custom configuration + Module Federation), Jenkins CI/CD, micro frontend architecture

**Projects designed:**
- ModuleFedHost (Webpack Module Federation shell): React + TypeScript + Webpack 5 + S3 + GitHub Actions — automated (no user feedback)
- JenkinsFlow (Jenkins CI/CD for Node.js): Jenkins + Jenkinsfile + npm ci + Docker + Jenkins Shared Library — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: Webpack Module Federation chosen because it's the canonical Webpack micro frontend pattern directly relevant to eBay's MUSE framework — architecturally honest (Webpack 5 MFP is the tool companies like eBay, Zalando, and DAZN actually use for micro UI). JenkinsFlow extends Jesse's existing CI/CD experience from GitHub Actions and GitLab to Jenkins-native patterns — the mental model transfers, the tooling is new. Domain: self-generating (pipeline targets a minimal TypeScript/Node.js service — the project IS the pipeline). Both projects extend Jesse's existing TypeScript/Node.js/React stack naturally.

## 2026-04-25 — Bandwidth Applied AI Engineer (Corporate IT)

**Gaps filled:** Ansible (configuration management and automation), Artifactory (artifact registry management)

**Projects designed:**
- InfraKit (Ansible + JFrog Artifactory + GitHub Actions): Python FastAPI service as deployment target, Ansible roles for OS/app/secrets, Artifactory Docker + PyPI repos with promotion rules — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Pairing rationale: Ansible and Artifactory are a natural enterprise DevOps pairing — config management + artifact registry are the two halves of the deployment workflow. Both are explicitly required by the JD. Extending Jesse's existing Python/AWS/GitHub Actions stack. Domain used: generic Python microservice (self-generating data) — appropriate for a corporate IT infra role where the toolchain is the point, not any specific product domain.

## 2026-04-25 — Shield AI / Engineer II Ground System Software

**Gaps filled:** GCS software for UAS, MAVLink communication interface, drone mission planning, UAS platform experience

**Projects designed:**
- UAV Ground Control Station — MAVLink Mission Planner: TypeScript + React + Node.js + WebSocket + Mapbox GL + PX4 SITL — accepted (automated run, no user feedback)

**Feedback:** No feedback — automated run. Project extends Jesse's existing TypeScript/React/Mapbox stack into UAS-specific GCS domain. Architecturally honest pairing: TypeScript GCS frontend + Node.js gateway + MAVLink protocol are the same stack used in QGroundControl web implementations.

## 2026-04-27 — BlackRock Full Stack Java Engineer, Aladdin Engineering

**Gaps filled:** Java (Spring Boot, JPA/Hibernate, JUnit 5), design patterns (Repository, Service, DTO), SQL Server-equivalent relational persistence

**Projects designed:**
- AltTrack (Spring Boot + React/TypeScript): Java Spring Boot backend + PostgreSQL + React/TypeScript frontend — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Pairing rationale: Spring Boot + React is the canonical enterprise Java full-stack pairing. React/TypeScript is Jesse's existing strength — pairing it with Spring Boot on the backend lets the project focus on the Java learning while the frontend is solid. Domain used: alternative investments portfolio tracking — mirrors BlackRock Alternatives directly. Data source: self-generated through app UI (trivial seed script). Avoids mirroring BlackRock's exact product (Aladdin) — demonstrates what Spring Boot + JPA solve (layered architecture, ORM, REST), not a BlackRock product clone.
## 2026-04-27 — Karat Community Engineer (BBM)

**Gaps filled:** Discord bot development, newsletter workflow automation

**Projects designed:**
- CommunityKit (Discord Bot + Newsletter Automation for Developer Study Groups): Python + discord.py + Mailchimp API + APScheduler + PostgreSQL + FastAPI + AWS EC2 + Docker + GitHub Actions — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: CommunityKit focused on what Discord bots and newsletter automation solve (scaling community operations for a developer study group program) rather than mirroring Karat's BBM program domain directly. Domain used: generic developer study group community — neutral and extensible. Extends Jesse's existing Python/AWS/PostgreSQL/Docker/FastAPI stack naturally. Discord.py + Mailchimp API grouped into one project because they naturally co-occur in community program tooling (same use case, same operational loop).

## 2026-04-27 — HealthOne LLC Software Developer (JR-88)

**Gaps filled:** T-SQL stored procedures (specific SQL Server requirement)

**Projects designed:**
- No new project created — project_loan_application_api.md already covers all critical C# gaps (ASP.NET Core + LINQ + EF Core + SQL Server + xUnit). Updated existing project to explicitly include a T-SQL stored procedure bullet (reporting queries called via EF Core FromSqlRaw) to cover the stored procedures requirement.

**Feedback:** Automated run — no user feedback. Applied pairing principle: Updating the existing Loan Application API rather than creating a new project is the right call — T-SQL stored procedures are naturally co-located with C# / SQL Server work, not a separate domain. The update adds one honest implementation bullet (stored procedures for reporting aggregations, called via FromSqlRaw) that reflects how stored procs are actually used alongside EF Core. C# / ASP.NET Core / LINQ / SQL Server / T-SQL stored procedures are now all covered by one coherent project.

## 2026-04-27 — Nox Metals Software Engineer

**Gaps filled:** NestJS, Supabase

**Projects designed:**
- SupplyDesk (NestJS + Supabase B2B Order and Quoting Portal): NestJS + Supabase (Auth, PostgreSQL, RLS, Realtime) + React + TypeScript + Jest + supertest — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: SupplyDesk focused on what NestJS + Supabase solve (structured Node.js API with DI/modules/guards + managed PostgreSQL BaaS with auth and realtime) rather than mirroring Nox Metals' aluminum supply chain domain. Domain used: food service distributor order portal — neutral, completely different from Nox's aerospace/defense aluminum domain. NestJS + Supabase is architecturally honest (Supabase's PostgreSQL-backed stack pairs naturally with any Node.js framework; NestJS is the most structured Node.js option). Grouped NestJS and Supabase into one project because they would co-occur in any Nox-style full-stack project — you wouldn't use one without the other in their actual codebase. Extends Jesse's existing TypeScript/Node.js/React/PostgreSQL stack naturally. Note: NestJS and Supabase are the two hard tech gaps; everything else in the JD (TypeScript, Node, React, PostgreSQL, full-stack shipping, AI tools, background jobs) is strongly covered by Nyquiste work experience.

## 2026-04-27 — Elastic AI Engineer (IT Team)

**Gaps filled:** Elasticsearch / Elastic Stack / ESRE, Jina AI (advanced RAG reranking), LangGraph, LangChain, LangSmith

**Projects designed:**
- ElasticRAG (Enterprise Knowledge Base with ESRE + Jina AI): Python + Elasticsearch 8.x + ESRE + Jina AI reranker + pgvector + FastAPI + OpenAI embeddings + Anthropic Claude API + Docker -- automated (no user feedback)
- ITFlow LangGraph Agent (IT Helpdesk Automation): Python + LangGraph + LangChain + LangSmith + Anthropic Claude API + FastAPI + SQLite MemorySaver + Docker -- automated (no user feedback)

**Feedback:** Automated run -- no user feedback. Applied pairing principles: ElasticRAG focused on what ESRE and Jina AI solve (production hybrid retrieval with cross-encoder reranking) rather than mirroring Elastic's own search product. Domain used: IT operations knowledge (Server Fault public data) -- neutral and relevant to the IT team role. ITFlow focused on what LangGraph solves (stateful agent control flow with branching, looping, human-in-the-loop) versus plain chains. Domain: IT helpdesk automation -- directly relevant to the enterprise IT team context without mirroring Elastic's search product. Both extend Jesse's existing Python/FastAPI/Docker/Anthropic stack naturally.

## 2026-04-28 — Marsh AI Engineer (AI Center of Excellence)

**Gaps filled:** Crossplane (Kubernetes-native IaC), LoRA fine-tuning (foundation model adaptation)

**Projects designed:**
- PlatformKit (Crossplane): Crossplane + kind + AWS provider + XRDs + Compositions + Claims + ArgoCD — automated (no user feedback)
- FineTuneLab (LoRA fine-tuning): Python + Hugging Face PEFT + bitsandbytes + transformers + Mistral-7B-Instruct + Alpaca-cleaned dataset — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: PlatformKit focused on what Crossplane solves (self-service Kubernetes-native IaC, platform-team/developer separation, continuous drift reconciliation) rather than Marsh's insurance/risk domain. Domain used: generic developer platform environment provisioning — neutral. Crossplane + kind + ArgoCD is architecturally honest (ArgoCD is the canonical GitOps layer for Crossplane Compositions). FineTuneLab focused on what LoRA fine-tuning solves (parameter-efficient model adaptation, adapter portability, forgetting tradeoffs) rather than insurance domain. Data source: Alpaca-cleaned (freely available on Hugging Face). PEFT + bitsandbytes + transformers + Mistral-7B is the standard efficient fine-tuning stack. Both projects are standalone — no natural pairing between Crossplane and fine-tuning (different domains). Both extend Jesse's existing Python/AWS/Kubernetes/LLM stack naturally.

## 2026-04-28 -- LCG Full Stack Developer / Java Developer

**Gaps filled:** SOAP web services (Spring-WS), Oracle PL/SQL

**Projects designed:**
- PermitBridge (SOAP Web Services + Oracle PL/SQL): Java Spring Boot + Spring-WS + Oracle XE + JAXB + Spring Data JPA + Docker Compose -- automated (no user feedback)

**Feedback:** Automated run -- no user feedback. Applied pairing principle: PermitBridge focused on what Spring-WS + Oracle solve (contract-first SOAP endpoint design, WSDL-driven Java stubs, PL/SQL stored procedures called from Java) rather than mirroring LCG's government contractor domain. Domain used: regulatory permit workflow -- generic government IT pattern, not specific to LCG's clients. Spring Boot + Spring-WS + Oracle XE is architecturally honest -- this is the standard Java enterprise SOAP stack and Oracle is the most common database in government/enterprise Java environments. SOAP and Oracle grouped into one project because they naturally co-occur in J2EE enterprise Java contexts (same codebase, same deployment). Extends Jesse's existing Spring Boot (AltTrack) stack naturally by adding the SOAP layer and Oracle dialect. Oracle XE available free via Oracle Container Registry -- no paid license required for development.

## 2026-04-28 — Axiom Bio Platform Engineer

**Gaps filled:** Ray (distributed ML compute, model serving), MLflow (experiment tracking, model versioning)

**Projects designed:**
- RayInfer (Distributed ML Inference & Evaluation Platform): Python + Ray Core + Ray Serve + MLflow + FastAPI — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: RayInfer focused on what Ray solves (distributed task scheduling, fault-tolerant batch inference, autoscaling model serving) rather than mirroring Axiom's biotech/drug discovery domain. Domain used: NLP benchmarking with public Hugging Face models and GLUE datasets — neutral. Extends Jesse's existing Python/FastAPI/AWS stack naturally. MLflow paired with Ray as the experiment tracking layer, which is the canonical Ray + MLflow pattern.

## 2026-04-28 — Nox Metals Software Engineer

**Gaps filled:** 2D bin packing / nesting algorithms, scheduling heuristics for sheet metal CNC cutting

**Projects designed:**
- NestCut (2D Sheet Nesting Optimizer): TypeScript + NestJS REST API + Jest — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Pairing principle applied: NestCut uses TypeScript + NestJS (extends Jesse's primary stack) rather than a separate language. Domain used: sheet metal nesting for CNC cutting — directly mirrors Nox Metals' WAYNE product domain, which is appropriate here because the goal is demonstrating domain-specific algorithmic understanding, not just tool familiarity.

## 2026-04-28 — MLB Associate Software Engineer (Baseball Data Platform)

**Gaps filled:** Apache Kafka, Google BigQuery

**Projects designed:**
- ClickStream (E-commerce Behavioral Analytics Pipeline): TypeScript/Node.js + Apache Kafka + BigQuery + PostgreSQL + Docker — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied domain principle: did not use baseball as the project domain (per prior feedback: don't mirror target company's domain). Used e-commerce clickstream as the domain since it naturally exercises Kafka's high-throughput event streaming and BigQuery's OLAP querying strengths. Extends Jesse's existing TypeScript/Node.js stack. Pairing is architecturally honest: Kafka + BigQuery is a standard streaming ingestion pattern. Existing projects (OpsFlow, DataBridge, AltTrack) cover GCP, NestJS, and Java/Spring gaps respectively — no new projects needed for those.

## 2026-04-28 — Newton Research Junior Software Engineer (Backend + AI)

**Gaps filled:** LangGraph, RAGAS, sentence-transformers, RQ (Redis Queue)

**Projects designed:**
- DataScout (LangGraph Research Agent with RAGAS Evaluation): Python + LangGraph + RAGAS + sentence-transformers + pgvector + FastAPI + Redis + RQ + Docker Compose — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principles: DataScout focused on what LangGraph and RAGAS solve (stateful agent orchestration and RAG evaluation measurement) rather than mirroring Newton's enterprise data warehouse domain. Domain used: news/research (Wikipedia, arXiv, NewsAPI) — neutral and readily available public APIs. Extends Jesse's existing Python/FastAPI/PostgreSQL/Redis/Docker stack naturally. All four gaps (LangGraph, RAGAS, sentence-transformers, RQ) grouped into one architecturally coherent project since they belong together in a RAG agent evaluation context.

## 2026-04-28 -- Babel Street Knowledge Graph Engineer

**Gaps filled:** Entity resolution / record linkage, ArangoDB graph database

**Projects designed:**
- EntityLinker (Multi-Source Entity Resolution & ArangoDB Knowledge Graph Pipeline): Python + ArangoDB + spaCy + sentence-transformers + datasketch (MinHash LSH) + FastAPI -- automated (no user feedback)

**Feedback:** Automated run -- no user feedback. Applied pairing principle: EntityLinker focused on what entity resolution solves (reconciling entity mentions across heterogeneous sources into a canonical graph) rather than mirroring Babel Street's intelligence/government domain. Domain used: public OpenStreetMap + Wikidata entities -- neutral and freely available. Extends Jesse's existing Python/FastAPI/PostgreSQL stack naturally with ArangoDB as the new graph layer. spaCy added as a lightweight NLP extraction step since it's named explicitly in the JD as a tool the team uses (alongside GLiNER).

## 2026-04-29 — Beijing Network Security Python Backend Developer

**Gaps filled:** PyTorch (training), ONNX / ONNXRuntime (cross-framework inference), TensorRT (GPU inference optimization), Vue 3, Element Plus / ElementUI, Echarts, D3.js, three.js, network-security visualization dashboard

**Projects designed:**
- NetVision (Network Traffic AI Classification + Security Situational Awareness Dashboard): Python + PyTorch + ONNX + ONNXRuntime + TensorRT + FastAPI + ClickHouse + Vue 3 + Element Plus + Echarts + D3.js + three.js + Docker Compose + GitHub Actions — user-requested single bundle (accepted as designed)

**Feedback:** User explicitly asked to bundle all PyTorch / TensorRT / ONNXRuntime / Echarts / D3 / three.js gaps into one large dashboard project, saying "我觉得挺容易". Honored the request because the pairing is genuinely architecturally honest: PyTorch → ONNX → ONNXRuntime / TensorRT is the canonical inference deployment chain, and Vue 3 + Element Plus + Echarts + D3 + three.js is the standard Chinese SOC big-screen visualization stack used by real Chinese network security companies (Sangfor, 360, Qihoo). Domain chosen: network security situational awareness — directly aligns with the JD company's product space. Data source: CIC-IDS2017 / CIC-DDoS2019 (publicly downloadable). Larger than weekend-sized (estimated 2–3 weekends with AI coding tools), flagged this to the user. ClickHouse and FastAPI extend Jesse's existing stack naturally; no cross-ecosystem forcing.

## 2026-05-17 -- Coforma Software Engineer (Evergreen)

**Gaps filled:** WCAG/accessibility, ARIA patterns, axe-core testing

**Projects designed:**
- AccessibleApply (WCAG 2.1 AA intake form): React + TypeScript + ARIA + axe-core + Jest -- automated (no user feedback)

**Feedback:** Automated run -- no user feedback. Applied pairing principle: React + TypeScript is Jesse's existing stack; the project adds ARIA patterns and axe-core accessibility testing on top rather than switching ecosystems. Domain used: government benefits intake form -- directly relevant to Coforma's civic tech work (Veterans claims, medical billing). Self-generated data (form submissions through the app's own UI).

## 2026-05-18 — Taco Bell Software Engineer III (BOH/Restaurant Tech)

**Gaps filled:** Serverless Framework, Postman

**Projects designed:**
- StoreConfig (Serverless Restaurant Config Distribution): TypeScript + Serverless Framework + Lambda + SQS + API Gateway + DynamoDB + S3 + Postman — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Gap analysis found GitLab and CDK already covered by MultiShip/MultiCI and NotifyWave/AdStream projects. Serverless Framework was the only named tool not covered by existing projects. Postman woven into StoreConfig naturally (API documentation collection with environment variables, auth, and test assertions). Domain chosen: restaurant configuration distribution — directly mirrors the BOH Store File Distribution (SFD) pattern in the JD.

## 2026-05-18 — GovWell / Full-Stack Software Engineer

**Gaps filled:** RedwoodJS

**Projects designed:**
- GovPermit: RedwoodJS + React + GraphQL + Prisma + PostgreSQL — automated run (no user feedback)

**Feedback:** Automated scheduled run — no interactive feedback collected.

## 2026-05-19 — A1 UX Engineer

**Gaps filled:** Animation/motion in React frontends (Framer Motion), streaming UI patterns with animated state transitions

**Projects designed:**
- PulseBoard (Animated Real-Time Metrics Dashboard): React + TypeScript + Vite + Framer Motion + SSE + Node.js — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: PulseBoard focused on what animation tooling solves (communicating system state changes through motion, perceived responsiveness, smooth loading states) rather than mirroring A1's AI chat product. Domain used: HTTP metrics monitoring — neutral developer-tooling context. Extends Jesse's existing React/TypeScript/Node.js stack naturally with Framer Motion as the new skill being demonstrated.

## 2026-05-21 — iCapital Network, Software Engineer Growth

**Gaps filled:** Paywalls, in-app upgrade flows, pricing experiments, upgrade funnel instrumentation

**Projects designed:**
- MonetizationKit (Paywall & Upgrade Flow Engine): TypeScript + Next.js + Node.js + Stripe + PostgreSQL + Redis + PostHog — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: MonetizationKit focused on what paywall/upgrade mechanics solve (gating features, driving paid conversions, measuring the upgrade funnel) rather than mirroring iCapital's institutional finance domain. Stack extends Jesse's existing TypeScript/Next.js/Node.js/PostgreSQL stack naturally. Soft and hard paywall distinction added to demonstrate understanding of real-world tradeoffs, not just a single modal. Stripe integration grounds it in production-realistic payment handling.

## 2026-05-21 — Exa Software Engineer, Full Stack

**Gaps filled:** TypeScript API client SDK development (npm-publishable, ergonomic developer-facing client)

**Projects designed:**
- DevAPI SDK (TypeScript API Client SDK): TypeScript + tsup + Vitest + msw — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Gap identified: while Jesse has consent-kit (a website SDK) and NEAR intent gateway SDK helpers, no dedicated npm-publishable TypeScript API client SDK existed. DevAPI SDK fills this directly for the "Shape the Exa API and SDKs" JD requirement. Pairing principle: extended Jesse's existing TypeScript/Node.js stack, focused on what API client SDK design solves (ergonomics, retry, pagination, streaming) rather than mirroring Exa's search domain. Domain used: generic REST API client — neutral, reusable for future roles.

## 2026-05-21 — Manhattan Labs Founding AI Engineer

**Gaps filled:** KYB/AML workflow, sanctions screening (OFAC SDN), beneficial ownership data, corporate registries, regulatory audit trails

**Projects designed:**
- AMLScout (KYB/AML Due Diligence & Sanctions Screening Agent): Python + LangGraph + FastAPI + PostgreSQL (trigram index) + TypeScript + Next.js + D3.js — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Pairing rationale: Python for the LangGraph agent and FastAPI backend (extends Jesse's existing Python stack from Nyquiste), TypeScript/Next.js for the investigation dashboard (extends Nyquiste frontend stack). Domain: KYB/AML compliance directly mirrors the target role. Data sources: OFAC SDN list (public XML from treasury.gov), OpenCorporates API (free tier), SEC EDGAR API (free) — all freely accessible. Architecture is honest: Python AI agent + TypeScript investigation UI is exactly the stack the role uses.

## 2026-05-21 — Spire Global Full-Stack Weather Software Engineer

**Gaps filled:** GRIB2/NetCDF/Zarr (weather data formats), xarray/Dask/Pangeo ecosystem, NWP model familiarity (GFS, HRRR), AWS Step Functions

**Projects designed:**
- WeatherGrid (NWP Forecast Data Pipeline & Weather Visualization Dashboard): Python + cfgrib + xarray + Dask + Zarr + S3 + AWS Step Functions + FastAPI + React + TypeScript + MapLibre GL + Recharts — automated (no user feedback)

**Feedback:** Automated run — no user feedback. Applied pairing principle: WeatherGrid focused on what the Pangeo weather stack solves (making large GRIB2 NWP model outputs queryable and renderable in a browser) rather than mirroring Spire's proprietary satellite constellation data. Domain used: public NOAA GFS + HRRR data from NOMADS HTTP server — freely available, no auth, updated every 6 hours. xarray + Dask + Zarr + cfgrib is architecturally honest — this is the exact Pangeo stack used by weather science teams. AWS Step Functions grouped with the weather pipeline naturally (it orchestrates the GRIB2 download → Dask processing → Zarr → S3 chain). Extends Jesse's existing Python/FastAPI/React/TypeScript/AWS/S3/Mapbox stack naturally. HRRR included alongside GFS to demonstrate awareness of multiple NWP grids (different projection, different resolution, different cycle frequency).

## 2026-05-21 — Paces / Software Engineer Full Stack

**Gaps filled:** None — all critical technical requirements (TypeScript, Python, SQL, full-stack, data-intensive, AI agents) were already covered by work experience and existing projects

**Projects designed:** None — gap-filling not triggered; only domain gaps remain (energy grid, utility companies) which are not demonstrable via buildable projects

**Feedback:** No feedback — automated run, no user interaction

## 2026-06-01 — Baton / Software Engineer

**Gaps filled:** document understanding, intelligent matching for marketplace context

**Projects designed:**
- BizMatch (Business Acquisition Intelligence System): Python + FastAPI + Claude API (structured extraction) + pgvector + PostgreSQL — accepted as designed (automated run)

**Feedback:** No user feedback — automated run. Project designed to bridge JD's explicit "document understanding" and "intelligent matching" requirements with Baton's small business M&A domain.

## 2026-06-01 — Hiring Cafe / Software Engineer

**Gaps filled:** Security and reverse-engineering (preferred)

**Projects designed:**
- No new projects — adversarial_scraping_lab.md already existed and covered the security/reverse-engineering preferred requirement; updated its status from "Not Started" to "In Progress"

**Feedback:** Automated run — no user feedback. No critical technical gaps (Node.js, Python, solid fundamentals all covered). Security/reverse-engineering is "preferred" only. Activated existing adversarial_scraping_lab.md project rather than designing a new one. WebHarvest (In Progress) covers the web crawling domain directly.

## 2026-06-07 — Quest Global AI/ML Engineer (P-119430)

**Gaps filled:** CrewAI (JD listed "LangGraph, CrewAI, or AutoGen" -- Jesse had LangGraph only)

**Projects designed:**
- MarketScout: CrewAI + Python + FastAPI + PostgreSQL + NewsAPI/SEC EDGAR/Wikipedia -- automated (no user feedback)

**Feedback:** Automated run -- no user feedback. Pairing principle applied: CrewAI + Python is the natural stack (CrewAI is Python-native). Domain used: business intelligence / competitive research (neutral, does not mirror Quest Global's aerospace/engineering domain). Extends Jesse's existing Python/FastAPI/PostgreSQL stack. Multi-modal gap noted but not filled -- JD framed it as "knowledge of" alongside agentic, which Jesse has well covered.
