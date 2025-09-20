# 📈 AI Trading Floor Simulator

An experimental **AI-driven stock trading simulation** where autonomous trader agents manage portfolios using distinct strategies.  
This project blends **LLM-powered decision-making**, **real market data**, **persistent accounts**, and a **Gradio dashboard** for monitoring.  

---

## 🚀 Features

- **Trader Agents**  
  Each agent simulates the style of a famous investor:  
  - **Warren** → Value investing (Warren Buffett–style)  
  - **George** → Aggressive macro trading (George Soros–style)  
  - **Ray** → Risk-parity diversification (Ray Dalio–style)  
  - **Cathie** → Disruptive innovation & crypto (Cathie Wood–style)  

- **Account Management**  
  - Create accounts with balances, holdings, and strategies  
  - Deposit / withdraw cash  
  - Buy & sell equities with rationale logging  
  - Track portfolio value & profit/loss over time  

- **Market Data Integration**  
  - Pulls live/delayed stock data via **Polygon.io API**  
  - Fallback to cached or simulated data when offline  

- **Persistence**  
  - **SQLite database** for accounts, logs, and market history  

- **Web Dashboard**  
  - Built with **Gradio + Plotly**  
  - Displays portfolios, holdings, transaction history, and logs  

- **MCP Servers & Clients**  
  - `account_server.py` / `account_client.py` → account operations & resources  
  - `market_server.py` → stock price lookup  
  - `push_server.py` → push notifications  
  - `trader_server.py` → trader decision-making tools  

- **Automation**  
  - Scheduler runs agents at fixed intervals (`RUN_EVERY_N_MINUTES`)  
  - Supports multiple AI models via environment variables  

---

## 📂 Project Structure


---

## ⚙️ Setup

### 1. Clone the repository
```bash
git clone https://github.com/your-username/ai-trading-floor.git
cd ai-trading-floor

## 2. Install dependencies
```bash
pip install -r requirements.txt

