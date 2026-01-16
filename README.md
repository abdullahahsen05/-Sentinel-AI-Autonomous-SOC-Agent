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

## 🚀 Quickstart: Installation & Execution

Run these commands in your terminal to set up the environment and start the system:

```bash
# 1. Install & Pull AI Model (Requires Ollama)
ollama pull llama3.1

# 2. Setup Project & Environment
git clone https://github.com/YOUR_USERNAME/sentinel-ai.git
cd sentinel-ai
python3 -m venv venv
source venv/bin/activate
pip install langchain-ollama langgraph streamlit pandas plotly

# 3. Launch the System (Run in separate terminal windows)
python3 main.py              # Starts the AI Agent
streamlit run dashboard.py    # Starts the SOC Dashboard

---

## 📊 Dashboard Intelligence
The dashboard serves as a Central Command Center for security analysts, providing high-level telemetry and granular threat data.

### **Key Performance Indicators (KPIs)**
* **Total Incidents:** Cumulative count of detected and processed threats.
* **Unique IPs Blocked:** Tracks the diversity of attack origins.
* **Critical Alerts:** Highlights high-severity incidents requiring immediate review.

### **Advanced Visualizations**
* **Severity Breakdown (Pie Chart):** Uses a **Plotly Donut Chart** to visualize the distribution of threat levels (CRITICAL, WARNING, LOW) as categorized by the LLM.
* **IP Threat Distribution (Bar Chart):** Ranks the most aggressive source IPs, allowing analysts to identify persistent attackers.

---

## 📜 Forensic Audit Trail
Every autonomous decision made by the AI is recorded in a persistent `security_events.csv` file. This serves as a verifiable forensic record for post-incident investigation and compliance auditing.

### **Sample Audit Log Table**
| Timestamp | IP Address | Action | AI-Assigned Severity |
| :--- | :--- | :--- | :--- |
| Jan 16 05:20:12 | 192.168.1.99 | **BANNED** | 🔴 CRITICAL |
| Jan 16 05:21:45 | 10.0.0.44 | **BANNED** | 🟡 WARNING |
| Jan 16 05:22:10 | 172.16.0.12 | **BANNED** | 🔴 CRITICAL |

> **Transparency Note:** Each entry includes the specific reasoning used by the AI Agent to determine why a particular IP was neutralized, ensuring explainability in autonomous actions.
