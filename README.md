# 📈 AI Trading Floor Simulator Using MCP

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

- **`account_client.py`**: MCP client for accessing account tools and reading account/strategy resources.  
- **`account_server.py`**: MCP server exposing account operations (balances, holdings, buy/sell, strategy updates).  
- **`accounts.py`**: Core account and transaction management, including balances, holdings, and reports.  
- **`app.py`**: Gradio + Plotly web dashboard for visualizing portfolios, transactions, and logs.  
- **`database.py`**: SQLite-backed persistence layer for accounts, transaction logs, and market history.  
- **`market.py`**: Market data integration using Polygon.io API with offline/simulated fallback.  
- **`market_server.py`**: MCP server providing stock price lookup tools.  
- **`push_server.py`**: MCP server for sending push notifications (e.g., Pushover).  
- **`reset.py`**: Script to reset trader accounts with their predefined strategies.  
- **`templates.py`**: Instruction templates for trader agents’ decision-making.  
- **`tracers.py`**: Logging and tracing utilities for agent runs.  
- **`trader_server.py`**: MCP server exposing trader actions and decision-making tools.  
- **`traders.py`**: Trader agent orchestration and strategy execution logic.  
- **`trading_floor.py`**: Main scheduler that automates trading runs at fixed intervals.  
- **`util.py`**: Shared utilities including CSS, JS, and color settings for UI components.  
- **`mcp_params.py`**: Centralized MCP server configuration parameters.  


---

## ⚙️ Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/aidoanto123/ai-trading-floor.git
   cd ai-trading-floor

2. `Install dependencies`
  ~~~bash
  pip install -r requirements.txt
  ~~~

3. `Set environment variables`
  Create a `.env` file in the project root:
  ~~~env
  # Polygon.io API
  POLYGON_API_KEY=your_polygon_api_key
  POLYGON_PLAN=free   # or "paid", "realtime"

  # Push notifications (optional)
  PUSHOVER_USER=your_pushover_user_key
  PUSHOVER_TOKEN=your_pushover_app_token

  # Scheduler
  RUN_EVERY_N_MINUTES=60
  RUN_EVEN_WHEN_MARKET_IS_CLOSED=false
  USE_MANY_MODELS=false

  # AI API Keys (optional, for agent orchestration)
  DEEPSEEK_API_KEY=...
  GOOGLE_API_KEY=...
  GROK_API_KEY=...
  OPENROUTER_API_KEY=...
  ~~~

# `▶️ Usage`

### `Launch the application`
~~~bash
python app.py
~~~

### `Reset trader accounts`
~~~bash
python reset.py
~~~

### `Start automated trading loop`
~~~bash
python trading_floor.py
~~~

---

## 🛠️ Tech Stack

- **Python** – agents, orchestration, servers  
- **Pydantic** – data validation  
- **SQLite** – persistence  
- **Gradio + Plotly** – dashboard  
- **Polygon.io API** – market data  
- **MCP (Model Context Protocol)** – modular servers & clients  



