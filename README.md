# 🚀 AUTOMATA MB Platform  
## AI-Powered Well Log Interpretation System

![Architecture](https://img.shields.io/badge/Architecture-Microservices-blue)
![Backend](https://img.shields.io/badge/Backend-Django%20DRF-green)
![Frontend](https://img.shields.io/badge/Frontend-Plotly%20Dash-orange)
![AI](https://img.shields.io/badge/AI-LLM%20Powered-purple)
![Live Demo](https://img.shields.io/badge/demo-available-brightgreen)

A modular AI-driven well log interpretation platform that unifies **data processing**, **intelligent analysis**, and **interactive visualization** into a single integrated environment. Designed for geoscientists and drilling engineers, it accelerates decision-making by combining microservice scalability with LLM-powered insights.

🔗 **Live Demo**: (https://welllogdash.pythonanywhere.com/)  
📘 **API Documentation**: [https://autamatawelllog.pythonanywhere.com/api/docs/]  
---

## 📚 Table of Contents

- [Key Features](#key-features)
- [System Architecture & Flow](#system-architecture--flow)
- [Services Overview](#services-overview)
- [AI Agent Integration](#ai-agent-integration)
- [Sample Data](#sample-data)
- [Why This Approach?](#why-this-approach)
- [Contact](#contact)

---

## ✨ Key Features

- **AI-Powered Interpretation** – Leverage LLMs (via Groq, OpenAI, etc.) to analyze well logs and provide contextual insights.
- **Modular Microservices** – Independently deployable services for visualization, business logic, and AI.
- **Interactive Dashboards** – Built with Plotly Dash, allowing users to explore well data, visualize logs, and trigger AI analysis.
- **RESTful API** – Well-documented Django REST Framework API for data orchestration and integration.
- **Scalable Architecture** – Docker Compose orchestration enables easy scaling of individual components.
- **Demo-Ready** – Sample well log data included for immediate exploration.

---

## 🏗 System Architecture & Flow

The platform follows a clean, layered architecture where each service has a distinct responsibility. The data flows seamlessly from user interaction to AI-powered insight.

### High-Level Flow
<img width="3113" height="3208" alt="deepseek_mermaid_20260303_571abe" src="https://github.com/user-attachments/assets/d1f2be76-787f-4d89-9fe4-221202da45e7" />

## Flow Explanation:

- User (geoscientist/engineer) interacts with the Dash Dashboard (frontend) to select a well and depth interval, then requests an interpretation.

- Dash sends the request to the DRF API (backend) via REST call.

- DRF API retrieves relevant well data from its internal database and forwards the request along with context to the Core AI Chat Agent.

- AI Agent constructs an appropriate prompt and calls an LLM Provider (e.g., Groq, OpenAI) with the contextual data.

- LLM Provider returns the interpretation (text analysis) to the AI Agent.

- AI Agent sends the result back to the DRF API.

- DRF API returns the result to Dash.

- Dash displays the insight to the user.

### Detailed Component Interaction

1. **User Interaction** – The geoscientist selects a well, depth interval, and requests interpretation via the Dash dashboard.
2. **API Orchestration** – The DRF API receives the request, retrieves relevant well log data from its database, and forwards it to the AI Agent.
3. **AI Processing** – The Core AI Chat Agent uses a prompt engineered for well log analysis, sends the data to an LLM (e.g., Groq, OpenAI), and receives a human-readable interpretation.
4. **Response Delivery** – The AI response is sent back to the DRF API, which may enrich it with additional metadata, and finally displays it on the Dash dashboard.

---

## 📦 Services Overview

| Service | Port | Technology | Responsibility |
|---------|------|------------|----------------|
| **Dash Visualization** | `8009` | Plotly Dash | Interactive frontend for well log browsing and analysis requests |
| **DRF API** | `8000` | Django REST Framework | Business logic, data aggregation, and AI service orchestration |
| **Core AI Chat Agent** | `8010` | Python + LangChain | LLM integration, prompt management, and interpretation generation |

All services are containerized and communicate via internal networking, ensuring separation of concerns and easy scalability.

---

## 🔐 AI Agent Integration

The DRF service communicates with the AI Chat Agent using a secure API key. The agent is designed to be **provider-agnostic**, meaning it can switch between different LLM backends (Groq, OpenAI, DeepSeek, Ollama) without modifying core application code.

**Key capabilities of the AI Agent:**
- **Dynamic prompt templates** tailored to well log interpretation.
- **Contextual memory** to maintain conversation history across requests.
- **Multi‑tenant isolation** (if deployed for multiple clients).
- **Fallback mechanisms** for LLM provider outages.

---

## 🗄 Sample Data

To make exploration immediate, the platform comes preloaded with **anonymized well log datasets**. These include:

- Gamma Ray (GR)
- Resistivity (LLD, LLS)
- Neutron Porosity (NPHI)
- Density (RHOB)
- Sonic (DT)

Users can select different wells and depth intervals to see how the AI interprets real-world formations.

*Download Sample data files are available here *
https://drive.google.com/file/d/1M9GsFAcx2rdFoqZaUoA3FA4sA-bsk93t/view?usp=sharing

---

## 💡 Why This Approach?

- **Microservices** allow independent development, testing, and scaling of each layer.
- **AI abstraction** future-proofs the system against new LLM providers.
- **Dash frontend** provides a rich, interactive experience without complex JavaScript frameworks.
- **Docker Compose** simplifies local development and deployment, while the architecture remains cloud-ready.

---

## 📬 Contact

**Maxy Silaen**  
Senior Python Backend Engineer & AI Consultant

- 🔗 [LinkedIn](https://linkedin.com/in/maxy-silaen-99ab0658)  
- 💻 [GitHub](https://github.com/maxyadamsilaen)  
- 📧 maxyadamsilaen1207@gmail.com

---

⭐ *If you'd like to discuss how this architecture can be adapted to your specific well log interpretation or industrial AI needs, feel free to reach out.*
