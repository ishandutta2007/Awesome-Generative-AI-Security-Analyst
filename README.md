# Awesome-Generative-AI-Security-Analyst

# Awesome Generative AI Security Analyst

> A curated list of top Generative AI Security Analyst platforms — both SaaS/Hosted commercial solutions and open-source alternatives.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [CrowdStrike Charlotte AI](#crowdstrike-charlotte-ai)
  - [Microsoft Security Copilot](#microsoft-security-copilot)
  - [Google Cloud Security AI Workbench](#google-cloud-security-ai-workbench)
  - [SentinelOne Purple AI](#sentinelone-purple-ai)
  - [Palo Alto Cortex Agi](#palo-alto-cortex-agi)
  - [Splunk AI Assistant](#splunk-ai-assistant)
  - [Recorded Future AI](#recorded-future-ai)
  - [Tenable ExposureAI](#tenable-exposureai)
  - [Wiz AI-SPM Assistant](#wiz-ai-spm-assistant)
  - [Elastic AI Assistant](#elastic-ai-assistant)
- [Open-Source Software](#-open-source-software)
  - [Vigil (DeepTempo)](#vigil-deeptempo)
  - [MANTIS](#mantis)
  - [LanG](#lang)
  - [TinySOC](#tinysoc)
  - [D-GEN-SOC](#d-gen-soc)
  - [Wazuh MCP Agent](#wazuh-mcp-agent)
  - [AllysecLabs Security Intelligence Platform](#allyseclabs-security-intelligence-platform)
  - [Allama](#allama)
  - [blacklight](#blacklight)
  - [Nephilex](#nephilex)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Generative AI security analyst platforms. These are not open-source but are included as reference points for feature comparison.

### CrowdStrike Charlotte AI
Falcon platform-native AI analyst offering agentic detection triage, multi-domain investigation, and Agentic SOAR response. Vendor claims >98% decision accuracy on triage, 70% less manual investigation effort, and 90% faster response. Charlotte AI assembles cross-domain context and dispatches parallel agents across endpoint, identity, cloud, and network. Available as a module with monthly credits on qualifying Falcon subscriptions [citation:12].

### Microsoft Security Copilot
The default choice for Microsoft-centric security estates. Agents run inside Defender, Sentinel, Entra, Intune, and Purview, making coverage strongest on Microsoft-generated alerts. E5/E7 licenses include 400 Security Compute Units (SCUs) per month per 1,000 seats (max 10,000); provisioned SCUs cost $4/hour, overage $6/hour. Focused on triage (phishing), investigation, and identity/data agents [citation:12].

### Google Cloud Security AI Workbench
Google SecOps (SIEM/SOAR) native agent platform. Includes Triage and Investigation Agent, Threat Hunt Agent (preview, Enterprise Plus), and Detection Engineering Agent (preview, YARA-L rule drafting). Threat Hunt Agent is grounded in Google Threat Intelligence, Mandiant expertise, and MITRE ATT&CK. Generally available agents consume Security Tokens (meter introduced July 1, 2026) [citation:12].

### SentinelOne Purple AI
AI security analyst integrated into the Singularity platform, designed to accelerate threat hunting, investigation, and response through natural language queries and automated analysis. Focused on endpoint and XDR telemetry.

### Palo Alto Cortex Agi
AI-driven security operations within Palo Alto's Cortex XSIAM platform. Combines ML-based detection with generative AI assistance for alert triage, investigation, and automated response across endpoint, network, and cloud data sources.

### Splunk AI Assistant
Generative AI layer within Splunk security products, including Splunk Security Cloud and Enterprise Security. Assists with SPL query generation, alert investigation, and threat analysis using natural language interaction.

### Recorded Future AI
AI-powered threat intelligence analysis integrated into the Recorded Future Intelligence Platform. Automates intelligence collection, enrichment, and risk scoring to support security operations and strategic decision-making.

### Tenable ExposureAI
Generative AI capabilities within Tenable One Exposure Management Platform. Assists with vulnerability prioritization, exposure analysis, and remediation guidance using natural language queries.

### Wiz AI-SPM Assistant
AI assistant within Wiz's cloud security platform, focused on cloud-native risk prioritization, misconfiguration analysis, and security posture management guidance.

### Elastic AI Assistant
Generative AI assistant built into Elastic Security. Supports alert triage, investigation, and response workflows with natural language, leveraging Elasticsearch data and integrated threat intelligence.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Generative AI security analyst platforms. All listed projects offer source code you can deploy on your own infrastructure.

### Vigil (DeepTempo)
**Stack:** Python | **License:** Apache 2.0  
An open-source AI SOC built with an LLM-native architecture. Ships with 13 specialized AI agents, 30+ integrations, and 7,200+ detection rules spanning Sigma, Splunk, Elastic, and KQL formats. Includes four production-tested multi-agent workflows: incident response, investigation, threat hunting, and forensic analysis. Designed to work with your own enterprise LLM deployments (local or remote), keeping detection logic transparent and avoiding vendor lock-in [citation:13][citation:14].  
**Best for:** SOC teams that want a pluggable, transparent agentic platform they can extend with their own rules, integrations, and models.

### MANTIS
**Stack:** Python | **License:** Open Source (per repository)  
A multi-agent autonomous threat intelligence system comprising 20 integrated modules. Features a 12-engine detection pipeline with weighted confidence fusion, an autonomous ReAct-based investigation agent, reinforcement learning response orchestration (PPO/DDPG/SAC), a security knowledge graph with PageRank risk propagation, and causal reasoning for root cause analysis. Includes an LLM-powered SOC chat interface and 20 live threat intelligence connectors (VirusTotal, AbuseIPDB, Shodan, MISP, and more). The project comprises 65,000+ lines of Python with 1,200+ passing backend tests. Claims capabilities comparable to commercial platforms like Palo Alto XSOAR and CrowdStrike Falcon [citation:3].  
**Best for:** Teams seeking a comprehensive, research-grade autonomous SOC framework with extensive threat intelligence integrations.

### LanG
**Stack:** LangGraph / Python | **License:** Open Source (per arXiv)  
A governance-aware agentic AI platform for unified security operations. Key contributions include: Unified Incident Context Record with a correlation engine (F1 = 87%), Agentic AI Orchestrator on LangGraph with human-in-the-loop checkpoints, LLM-based Rule Generator producing deployable Snort/Suricata/YARA rules (96.2% acceptance rate), and a Three-Phase Attack Reconstructor (87.5% kill-chain accuracy). Features a two-layer guardrail pipeline (regex + Llama Prompt Guard 2) achieving 98.1% F1 with zero false positives in experiments. Designed for MSSPs with multi-tenant isolation and fully local deployment support .  
**Best for:** Managed security service providers and teams that require governance guardrails and multi-tenant isolation in an open-source agentic platform.

### TinySOC
**Stack:** Python / Gradio / llama.cpp | **License:** MIT  
A fully-local AI SOC analyst designed for solo operators and small MSPs with no dedicated SOC team. Runs 100% locally on CPU via llama.cpp — no cloud API, no data leaves the box. Three-stage design: (1) deterministic baseline learns host profiles and scores log lines, (2) small code model uses token-level perplexity to highlight genuinely novel spans, (3) small (≤4B) instruct model produces structured JSON triage (severity, summary, why, next_action, likely_false_positive). Accepts Linux syslog, Wazuh JSON alerts, and raw Windows events [citation:8].  
**Best for:** Solo security operators and small MSPs who need local, privacy-preserving AI triage without cloud dependencies or enterprise licensing.

### D-GEN-SOC
**Stack:** Python / Wazuh / TheHive | **License:** Research prototype  
A SOC framework combining open-source telemetry (Wazuh), incident coordination (TheHive), and lightweight AI augmentation using Gemini 1.5's free-tier API for alert summarization. In controlled experiments, achieved MTTD of 84.83 seconds and Wazuh → TheHive latency of 29.55 seconds. The AI module creates summary reports stored alongside alerts for human-in-the-loop (HITL) validation. Results demonstrated ~53% MTTD improvement, ~40% MTTR improvement, and 10% false-positive reduction compared to manual baseline [citation:2].  
**Best for:** Small SOC teams wanting a transparent, auditable blueprint for AI augmentation without replacing human authority.

### Wazuh MCP Agent
**Stack:** Python / MCP (Model Context Protocol) | **License:** Open Source (per IEEE paper)  
An AI-assisted incident response workflow integrating Wazuh SIEM with an AI assistant through a Model Context Protocol (MCP) server. The AI uses MCP tools to query the Wazuh manager, enrich alerts, and generate structured incident reports. In Phase 1 (human-in-the-loop), achieved 91.67% detection rate, 1.23 minutes analysis time (-88%), and 222 minutes MTTR (-72%) compared to manual baseline. In Phase 2 (fully automated active-response), achieved 0.15 minutes analysis time, 15.2 minutes MTTR, and 13.9 minutes dwell time with 87.50% precision and 8.33% false-positive rate [citation:4][citation:10].  
**Best for:** Teams already running Wazuh SIEM that want measurable MTTR reduction through MCP-based AI assistance, with an option for fully automated response.

### AllysecLabs Security Intelligence Platform
**Stack:** Python / FastAPI / Streamlit / Wazuh | **License:** Open Source (per GitHub)  
An AI-powered SOC analysis platform built on Wazuh SIEM. Provides natural language security queries, pattern detection, MITRE ATT&CK mapping, and professional report generation. LLM-agnostic architecture supporting local inference (Ollama) for air-gapped environments, Groq (Llama 3.3 70B) for daily queries, and Claude Opus for complex investigations. The project was motivated by enterprise AI security tools being locked behind expensive licensing tiers (Microsoft Security Copilot requires SCUs + M365 E5; Security Onion's AI features are Pro-only) .  
**Best for:** Security analysts who want a practical, extensible AI analysis layer on top of Wazuh without enterprise licensing costs.

### Allama
**Stack:** Python | **License:** Open Source (per GitHub)  
An open-source security automation platform with AI agents for threat detection and response. Integrates with 80+ tool categories including SIEM, EDR, identity providers, and ticketing systems. AI agents process threat data, enrich alerts, contain threats, create cases, and notify responders. Supports externally hosted LLMs and self-hosted models via Ollama. Features durable workflow execution with retries, state persistence, audit logging, and role-based access controls [citation:15].  
**Best for:** SOC teams and MSSPs wanting visual workflow automation combined with AI agents for alert triage and response orchestration.

### blacklight
**Stack:** Bash / Markdown | **License:** GPL v2  
An agentic AI security analyst designed for Linux defensive stacks (LMD, APF, BFD users). Operates as a single bash file + markdown skills, requiring only bash 4.1 + curl. Reads existing logs in place — no SIEM/SOAR/IdP integration required. Designed for $10/month customer margins and auditable in 30 minutes (open source, single file). The project explicitly targets the market segment that platform-first commercial tools like CrowdStrike Charlotte AI structurally cannot serve: OSS Linux hosts running legacy distributions (CentOS 6, RHEL 7, Debian 10) [citation:1].  
**Best for:** Sysadmins managing legacy Linux fleets who want agentic AI security analysis without enterprise platform overhead or per-endpoint licensing.

### Nephilex
**Stack:** Python | **License:** Open Source (per PyPI)  
An AI security engineer focused on **fixing, not just finding** vulnerabilities. Scans repositories, applies deterministic self-verified fixes to a fresh branch, commits them, and optionally opens a PR. Supports multiple AI providers: heuristic (local default), Ollama (local), Anthropic (cloud), and OpenAI (cloud). Includes a first-class LLM and agent security scanner covering OWASP LLM Top 10, live OSV vulnerability data, and deterministic patch generation. Benchmarked against Bandit and Semgrep with transparent scoring scripts available in the repository [citation:5].  
**Best for:** Development and security teams that want automated vulnerability remediation with AI assistance, including LLM/agent security scanning.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Deployment | Best For |
|----------|---------|-------|------------|----------|
| **Vigil** | Apache 2.0 | Python | Self-hosted | Pluggable agentic SOC with own LLM |
| **MANTIS** | Open Source | Python | Self-hosted | Research-grade autonomous SOC |
| **LanG** | Open Source | LangGraph | Self-hosted | MSSP multi-tenant + governance |
| **TinySOC** | MIT | Python/llama.cpp | 100% local CPU | Solo operators, air-gapped |
| **D-GEN-SOC** | Research | Wazuh/TheHive | Self-hosted | Transparent HITL augmentation |
| **Wazuh MCP Agent** | Open Source | MCP | Self-hosted (Wazuh) | Measurable MTTR reduction |
| **AllysecLabs** | Open Source | Python/Wazuh | Self-hosted | Practical Wazuh AI layer |
| **Allama** | Open Source | Python | Self-hosted | Workflow automation + AI agents |
| **blacklight** | GPL v2 | Bash | Single file | Legacy Linux fleets, low margin |
| **Nephilex** | Open Source | Python | CLI / CI-CD | Automated vuln remediation |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Generative AI Security Analyst platform that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
