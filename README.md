📈 Capital.com Python Trading ClientA lightweight, efficient Python wrapper for the Capital.com REST and WebSocket APIs. This tool allows traders to automate market searches, execute trades, and stream real-time price data with minimal overhead.🚀 Key FeaturesSession Management: Automatic authentication and CST/X-SECURITY-TOKEN handling.Market Data: Search for instruments (EPICs) and retrieve market details.Order Execution: Place market orders with configurable risk management (Stop Loss/Take Profit).Live Streaming: Real-time price updates via WebSockets with built-in keepalive (pinging).Asynchronous Support: Threaded WebSocket handling to prevent session timeouts.🛠 Tech StackLanguage: Python 3.8+Libraries:requests: For REST API communication.websocket-client: For real-time data streaming.python-dotenv: For secure environment variable management.📦 Installation & Setup1. Clone the repositoryBashgit clone https://github.com/your-username/capital-trading-bot.git
cd capital-trading-bot
2. Install dependenciesBashpip install -r requirements.txt
(Ensure your requirements.txt contains: requests, websocket-client, and python-dotenv)3. Configure Environment VariablesCreate a .env file in the root directory and add your credentials. Never commit this file to GitHub.Code snippetCAPITAL_BASE_URL=https://demo-api-capital.backend-capital.com
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
📋 API Functionality OverviewMethodDescriptionlogin()Authenticates and retrieves security tokens.ping()Keeps the REST session active.search_markets(term)Finds instrument EPICs based on a search string.place_market_order()Executes a trade with optional Stop/Profit distances.stream_quotes()Opens a WebSocket for live price action.⚠️ DisclaimerTrading involves significant risk. This software is provided "as is" for educational and developer purposes. The authors are not responsible for financial losses incurred through the use of this code. Always test your strategies thoroughly on a Demo Account before moving to Live trading.👤 Credits & ReleasesDeveloper: Your Name/AliasAPI Documentation: Capital.com API Reference
