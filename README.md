# SupplyChain-Eye: Multi-Agent Supply Chain Optimizer  
### Built with Google Agent Development Kit (ADK)

This repository contains our complete submission for the **Kaggle Agents Intensive – Capstone Project**.  
It showcases a production-grade **multi-agent system** for optimizing supply chain logistics using **Google ADK**, including:

- Multi-agent orchestration (Sequential, Parallel, Loop patterns)  
- Session state & long-term memory  
- Tool integrations (Google Search, MCP DB, Code Execution, A2A protocol)  
- Long-Running Operations (LRO)  
- Agent-to-Agent federated architecture  
- Full logging & persistable sessions  

---

# 📂 Repository Structure

### **Core Files**

| File | Purpose |
|------|---------|
| [`Agentic_AI.ipynb`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/Agentic_AI.ipynb) | Main notebook containing the entire multi-agent implementation. |
| [`LICENSE`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/LICENSE) | Open-source license. |
| `README.md` | Project documentation (this file). |

---

### **Supporting System Files (for ADK Session, A2A, Memory, MCP)**

| File | Description |
|------|-------------|
| [`mock_agent_card.json`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/mock_agent_card.json) | Mock Agent Card used by RemoteA2aAgent for federated A2A communication. |
| [`supply_chain_adk.db`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/supply_chain_adk.db) | ADK session database (session state). |
| [`supply_chain_obs.db`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/supply_chain_obs.db) | Observability + logging persistent DB. |
| [`supply_chain_ultimate.db`](https://github.com/JRK-007/AI-Agents-Google-Hackathon/blob/main/supply_chain_ultimate.db) | Final consolidated DB storing all persistent workflow state. |

---

# 🎯 1. Project Overview

**SupplyChain-Eye** is a multi-agent AI system designed to streamline and optimize supply chain route decisions.  
It uses **structured agent composition** (Sequential → Parallel → Loop patterns), integrates real-time search, interacts with a supplier MCP database, maintains state, and performs iterative report refinement.

The system demonstrates:

- Supplier risk assessment  
- Budget tracking & approvals  
- Market disruption search  
- Route performance analysis  
- A2A federated supplier communication  
- Multi-round report refinement  
- Memory-enhanced decision making  

All agents run on **Gemini 2.5 Flash-Lite**.

---

# 🧠 2. Core Features

## ✔ Multi-Agent Architecture  
The system uses **10 LlmAgents**, each performing distinct roles:

- **StrategicAnalyst** – Uses long-term memory  
- **DataIntake** – Parses user-input route  
- **BudgetManager** – Manages cumulative budget via session state  
- **MarketResearch** – Web searches using Google Search Tool  
- **RouteAnalyzer** – Internal logistics analysis  
- **RiskManagement** – Updates supplier risk  
- **Optimization** – MCP DB lookups for alternative suppliers  
- **Approval** – Uses LRO to pause execution for high-cost changes  
- **Reporting** – Generates summary reports  
- **Critic** – Evaluates & improves report in loop mode  

---

## ✔ Agent Patterns Implemented

| Pattern | Description | Where Used |
|--------|-------------|------------|
| **SequentialAgent** | Executes agents in a defined order | Main Supply Chain Pipeline |
| **ParallelAgent** | Runs MarketResearch & RouteAnalyzer simultaneously | `ParallelAnalysisTeam` |
| **LoopAgent** | Iterative report refinement | `RefinementLoop` |
| **Memory System** | Long-term recall | `StrategicAnalyst` |
| **Session State** | Maintains budget & risk | BudgetManager & RiskManagement |
| **LRO (Long-Running Op)** | Pauses for manual approvals | `Approval` agent |

---

## ✔ Tools Used

- **FunctionTool** – Budget updates, risk updates, approval logic  
- **google_search** – External disruptions  
- **BuiltInCodeExecutor** – Executes code securely  
- **McpToolset** – Supplier database querying  
- **load_memory / preload_memory** – Memory interaction  
- **AgentTool** – A2A communication wrapper  

---

# 🏗 3. System Architecture

### 🚀 **End-to-End Workflow**

