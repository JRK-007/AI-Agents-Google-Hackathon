# SupplyChain-Eye: Multi-Agent Supply Chain Optimizer  
### Built with Google Agent Development Kit (ADK)

This repository contains our complete submission for the **Kaggle Agents Intensive – Capstone Project**.  
It showcases a production-grade **multi-agent AI system** built using **Google ADK** to optimize real-world supply chain workflows using:

- Multi-agent orchestration (Sequential, Parallel & Loop patterns)
- Session state + long-term memory
- Tool integrations (Google Search, MCP Database, Code Execution)
- LRO (Long Running Operations) approval mechanism
- Agent-to-Agent (A2A) federated communication
- Persisted sessions with SQLite databases
- Full debugging & observability

---

# 📂 Repository Structure

### **Core Project Files**
| File | Description |
|------|-------------|
| [`Agentic_AI.ipynb`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/Agentic_AI.ipynb) | Main notebook containing complete multi-agent implementation. |
| [`LICENSE`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/LICENSE) | Open-source license. |
| `README.md` | (This file) Project documentation. |

---

### **Supporting Runtime Files (Required for Agent Execution)**

| File | Purpose |
|------|---------|
| [`mock_agent_card.json`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/mock_agent_card.json) | Required for A2A Remote Supplier Agent communication. |
| [`supply_chain_adk.db`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/supply_chain_adk.db) | ADK session state storage. |
| [`supply_chain_obs.db`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/supply_chain_obs.db) | Observability + logs + ADK event history. |
| [`supply_chain_ultimate.db`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/supply_chain_ultimate.db) | Final consolidated state DB used during agent execution. |

These files must remain in the repository root, as the ADK automatically loads them.

---

# 🎯 1. Project Overview

**SupplyChain-Eye** is a fully functional **multi-agent AI orchestration system** designed to analyze, optimize, and refine supply chain routes.  
It demonstrates:

- Supplier risk assessment & mitigation  
- Budget and cost management  
- Market disruption analysis (via Google Search)  
- Route performance evaluation  
- Alternative supplier lookup via MCP Toolset  
- Iterative reporting with critique loops  
- Cross-organization A2A communication (multi-agent federation)  

The system leverages **Gemini 2.5 Flash Lite** for all LLM reasoning tasks.

---

# 🧠 2. Core Features

## ✔ Multi-Agent Architecture
The pipeline uses **10 specialized LlmAgents**:

- **Data Intake**
- **Strategic Analyst (Memory Retrieval)**
- **Budget Manager (Session State)**
- **Market Research (Web Search Tool)**
- **Route Analyzer**
- **Risk Management (Session State)**
- **Optimization Agent (MCP Query)**
- **Approval Agent (LRO)**
- **Reporting Agent**
- **Critic Agent (Loop Exit)**

---

## ✔ ADK Patterns Implemented

| Pattern | Description | Usage |
|--------|-------------|-------|
| **SequentialAgent** | Ordered workflow execution | Main supply chain pipeline |
| **ParallelAgent** | Simultaneous reasoning | Market + Route analysis |
| **LoopAgent** | Iterative improvement cycles | Reporting ↔ Critic |
| **Memory System** | Long-term recall | Supplier history |
| **Session State** | Persisted variables | Budget, risk scores |
| **LRO** | Human approval pauses | High-cost route adjustments |

---

## ✔ Tools Integrated
- `FunctionTool` – Custom Python functions for risk/budget updates  
- `google_search` – External disruption monitoring  
- `BuiltInCodeExecutor` – Secure code execution  
- `McpToolset` – Supplier DB communication  
- `load_memory`, `preload_memory` – Memory agents  
- `AgentTool` – A2A federated agent communication  

---

