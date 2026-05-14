# 📈 Capital.com Python Trading Client

A lightweight, efficient Python wrapper for the **Capital.com REST and WebSocket APIs**. This tool allows traders to automate market searches, execute trades, and stream real-time price data with minimal overhead.

---

## 🚀 Key Features

* **Session Management**: Automatic authentication and `CST` / `X-SECURITY-TOKEN` handling.
* **Market Data**: Search for instruments (EPICs) and retrieve detailed market information.
* **Order Execution**: Place market orders with configurable risk management (Stop Loss / Take Profit).
* **Live Streaming**: Real-time price updates via WebSockets with a built-in keepalive (pinging) system.
* **Asynchronous Support**: Threaded WebSocket handling to prevent session timeouts while processing data.

---

## 🛠 Tech Stack

* **Language**: Python 3.8+
* **Core Libraries**:
    * `requests`: For REST API communication.
    * `websocket-client`: For real-time data streaming.
    * `python-dotenv`: For secure environment variable management.

---

## 📦 Installation & Setup

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/capital-trading-bot.git](https://github.com/your-username/capital-trading-bot.git)
cd capital-trading-bot
2. Install DependenciesEnsure you have a requirements.txt file, then run:Bashpip install -r requirements.txt
Note: Requirements should include requests, websocket-client, and python-dotenv.3. Configure Environment VariablesCreate a .env file in the root directory. Important: Add this file to your .gitignore to keep your credentials safe.Code snippetCAPITAL_BASE_URL=[https://demo-api-capital.backend-capital.com](https://demo-api-capital.backend-capital.com)
CAPITAL_API_KEY=your_api_key_here
CAPITAL_IDENTIFIER=your_email_or_id
CAPITAL_API_PASSWORD=your_password
🖥 Usage ExampleRunning the capital_quickstart.py script will authenticate your session, search for Bitcoin (BTC) markets, stream live prices for 20 seconds, and place a demo market order.Pythonfrom capital_quickstart import CapitalClient

# Initialize Client
cap = CapitalClient(BASE_URL, API_KEY, IDENTIFIER, API_PASS)
cap.login()

# Stream Live Quotes
def handle_quote(quote):
    print(f"Price Update: {quote['epic']} | Bid: {quote['bid']} | Ask: {quote['ofr']}")

cap.stream_quotes(["BITCOIN"], handle_quote, run_seconds=20)
📋 API Functionality OverviewMethodDescriptionlogin()Authenticates and retrieves security tokens (CST & SEC).ping()Keeps the REST session active to avoid timeouts.search_markets(term)Finds instrument EPICs based on a search string.place_market_order()Executes a trade with optional Stop/Profit distances.stream_quotes()Opens a persistent WebSocket for live price action.
