# 🛡️ Sentinel AI: Autonomous SOC Agent
### *Self-Healing Security Infrastructure using LangGraph and Llama 3.1*

Sentinel AI is an autonomous Security Operations Center (SOC) agent designed to bridge the gap between detection and response. By leveraging **Llama 3.1** and **Agentic Reasoning**, it doesn't just alert—it analyzes, decides, and acts to neutralize threats in real-time.

---

## 🧠 Project Concept
Traditional security systems rely on static threshold rules (e.g., "Block after 5 attempts"). **Sentinel AI** introduces **Reasoning + Acting (ReAct)**:
* **Detection:** Real-time tailing of system authentication logs.
* **Brain:** A LangGraph-orchestrated agent using Llama 3.1 to distinguish between human errors and scripted brute-force attacks.
* **Response:** Autonomous tool-calling to ban malicious IPs and update forensic audit logs.
* **Visibility:** A live Streamlit dashboard providing threat telemetry and severity analytics.



---

## 🛠️ Technology Stack
* **LLM:** Llama 3.1 (8B) / Llama 3.2 via **Ollama**
* **Framework:** LangGraph & LangChain (Agentic Workflows)
* **Frontend:** Streamlit (SOC Dashboard)
* **Visualization:** Plotly Express (Interactive Pie/Bar Charts)
* **Backend:** Python 3.10+ on Ubuntu Linux

---

## 🚀 Quick Start

### 1. Prerequisites
Install [Ollama](https://ollama.ai) and pull the high-performance model:
```bash
ollama pull llama3.1
2. InstallationBashgit clone [https://github.com/YOUR_USERNAME/sentinel-ai.git](https://github.com/YOUR_USERNAME/sentinel-ai.git)
cd sentinel-ai
pip install -r requirements.txt
3. ExecutionRun the Sentinel and the Dashboard in separate terminal windows:Bash# Terminal 1: AI Agent
python3 main.py

# Terminal 2: SOC Dashboard
streamlit run dashboard.py
📊 Dashboard IntelligenceThe dashboard serves as a Command Center, providing:Severity Breakdown: A Plotly Pie Chart categorizing threat levels (Critical, Warning, Low).Threat Distribution: Bar charts tracking the most aggressive attack sources.Incident Metrics: Real-time counters for unique IPs and total threats neutralized.Live Audit Log: A complete history derived from security_events.csv.Note: [Insert Screenshot of your Dashboard here]📜 Forensic Audit TrailEvery autonomous decision is logged in a persistent security_events.csv for post-incident analysis:TimestampIP AddressActionSeverityJan 16 05:20192.168.1.99BANNEDCRITICAL🛡️ DisclaimerThis project is built for educational and portfolio purposes, demonstrating the application of Agentic AI in automated cybersecurity defense.
