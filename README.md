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
