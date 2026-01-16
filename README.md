# 🛡️ Sentinel AI: Autonomous SOC Agent

### 📌 Project Overview
This project demonstrates the deployment of an **Autonomous Security Operations Center (SOC) Agent**. Using **LangGraph** and **Llama 3.1**, the system monitors system authentication logs in real-time, leverages LLM reasoning to identify brute-force attacks, and autonomously executes firewall actions to neutralize threats.



---

### 🛠️ Architecture
* **AI Engine:** Llama 3.1 (8B) via Ollama (Local LLM).
* **Orchestration:** LangGraph (Stateful ReAct Agent).
* **Dashboard:** Streamlit & Plotly (Real-time Telemetry).
* **Traffic Flow:** Attacker (Failed Logins) -> `auth.log` -> **Sentinel AI Agent** -> Python `ban_ip` Tool -> `security_events.csv` -> Dashboard UI.

---

### ⚙️ Configuration Highlights

#### 1. Agentic Reasoning (ReAct Pattern)
Unlike static security rules, Sentinel AI uses a **Reasoning + Acting** loop. It analyzes the context of a log entry (targeted usernames, frequency, and IP reputation) before deciding whether to trigger a block, significantly reducing false positives.

#### 2. Autonomous Tool Calling
The agent is equipped with a custom Python toolset. When a threat is confirmed, the LLM autonomously generates parameters to call `action_ban_ip()`, which updates the local security policy and logs the event for forensic review.

---

### 🛡️ Attack Simulation & Defense

#### **Scenario 1: Brute-Force SSH Attack**
* **Attack:** Simulated a rapid-fire failed login attempt targeting `root` and `admin` accounts.
* **Outcome:** The AI Agent detected the pattern, identified it as a "High Severity Brute Force" attempt, and autonomously banned the IP.
* **Log Verification:** The agent logged: *"Multiple failed attempts on sensitive accounts from a single source detected."*

#### **Scenario 2: Multi-Vector Threat Detection**
* **Defense:** Tested the agent's ability to handle multiple unique attacker IPs simultaneously.
* **Result:** The Streamlit dashboard successfully tracked unique "Attacker Origins" and updated the **Severity Breakdown** chart in real-time.

---

### 📸 Proof of Concept

#### 1. Sentinel AI Dashboard (Real-time Analytics)
<img width="1918" height="1078" alt="dashboard" src="https://github.com/user-attachments/assets/b2dcbe63-18cf-46e3-88d4-9b5b8b23f9e3" />
*(Overview of real-time incident metrics, IP distribution bar charts, and threat severity pie charts.)*

#### 2. AI Agent Reasoning (Terminal)
<img width="1905" height="831" alt="threats" src="https://github.com/user-attachments/assets/95498f90-339a-419f-91e1-56a6c819eaa4" />
*(Screenshot showing the LLM's thought process: "Analyzing logs... Brute force detected... Banning IP.")*

#### 3. Forensic Audit Trail
<img width="747" height="196" alt="logs banning" src="https://github.com/user-attachments/assets/f657f060-9005-4946-a52f-581db3da37bc" />
| Timestamp | IP Address | Action | AI Severity |
| :--- | :--- | :--- | :--- |
| Jan 16 05:20 | 192.168.1.99 | **BANNED** | 🔴 CRITICAL |
| Jan 16 05:21 | 10.0.0.44 | **BANNED** | 🟡 WARNING |

---

### 🚀 Key Takeaways
* **Agentic Workflows:** Practical experience building stateful AI agents using **LangGraph**.
* **LLM Integration:** Implementing local LLMs (Llama 3.1) for specialized cybersecurity tasks.
* **Threat Intelligence:** Developing a real-time data pipeline from raw logs to interactive visual analytics.

---

### 🛡️ Disclaimer
*This project is built for educational and portfolio purposes. Always ensure proper authorization before running security tools on production systems.*
