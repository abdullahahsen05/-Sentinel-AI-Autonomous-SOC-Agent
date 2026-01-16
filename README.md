🛡️ Sentinel AI: Autonomous SOC Agent
Sentinel AI is a localized, AI-powered Security Operations Center (SOC) agent. It leverages Llama 3.1 (via Ollama) and LangGraph to autonomously monitor system logs, reason about security threats, and execute firewall actions to neutralize attackers in real-time.

🧠 The "Agentic" Difference
Unlike traditional security tools that rely on static "If/Then" rules, Sentinel AI utilizes a ReAct (Reasoning + Acting) pattern:

Perception: Monitors logs_simulation.log for suspicious entries (e.g., Failed SSH logins).

Reasoning: The Llama 3.1 LLM analyzes the log context to distinguish between a user mistake and a coordinated brute-force attack.

Action: The agent autonomously triggers the action_ban_ip tool to update the system blocklist.

Telemetry: Real-time data is piped into a Streamlit dashboard for human oversight.

🛠️ Tech Stack
AI Orchestration: LangGraph (Stateful Multi-Agent Framework)

Local LLM: Llama 3.1 (via Ollama)

Dashboard: Streamlit & Plotly (Real-time analytics)

Backend: Python 3.10+

Environment: Ubuntu Linux

📊 Dashboard Preview
Real-time Incident Counter: Tracks total threats neutralized.

Severity Breakdown: AI-categorized threat levels (Low, Medium, Critical) visualized via Plotly Pie Charts.

IP Distribution: Bar charts showing the most aggressive attack origins.

Forensic Audit Log: A complete history stored in security_events.csv.

🚀 Installation & Setup
1. Prerequisites
Ubuntu/Linux

Ollama installed (ollama pull llama3.1)

2. Environment Setup
Bash

# Clone the repository
git clone https://github.com/YOUR_USERNAME/sentinel-ai.git
cd sentinel-ai

# Setup Virtual Environment
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
3. Running the System
Start the Sentinel Brain:

Bash

python3 main.py
Launch the Dashboard:

Bash

streamlit run dashboard.py
Simulate an Attack:

Bash

echo "Jan 16 05:00:00 Failed password for root from 192.168.1.99" >> logs_simulation.log
📜 Forensic Logging
All actions taken by the AI are recorded in security_events.csv with the following format: Timestamp, IP Address, Action, Severity

🛡️ Disclaimer
This project is intended for educational and portfolio purposes. Always ensure proper authorization before running security tools on production systems.
