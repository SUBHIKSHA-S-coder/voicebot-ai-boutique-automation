# VoiceBot AI — Instagram Boutique Query Automation

An AI-powered voice assistant that automates customer query handling for Instagram boutique owners, using speech recognition, rule-based intent detection, and live product catalog integration.

## The Problem

Instagram boutique owners receive 50–200+ DMs and calls daily, spending 10–14 hours manually answering repetitive questions about availability, pricing, sizes, and colors. Delayed responses mean lost sales — over two-thirds of Instagram shoppers buy elsewhere if they don't hear back within an hour, and small boutiques lose a significant share of potential sales to slow replies.

## The Solution

VoiceBot AI automatically answers incoming customer calls, identifies what the customer wants (price check, stock availability, bulk order), and responds using live product data — without human intervention for common queries. Complex or bulk orders are escalated to the owner, and every call is logged for review on an admin dashboard.

## How It Works

1. **Customer calls in** → routed through **Twilio Voice API**
2. **Flask (Python) backend** receives the call and runs:
   - **Voice Call Handler** — manages the call flow and speech-to-text conversion
   - **Rule-Based Intent Engine** — keyword and pattern matching to classify the query (price inquiry, stock check, bulk order, etc.)
   - **Product & Order Service** — fetches live catalog details
   - **Campaign Manager** — handles outbound/follow-up logic
3. **Live Catalog Integration** — product, order, and customer data is pulled in real time from **Google Sheets**, so customers always get up-to-date pricing and availability
4. **Response Automation** — replies are converted back to speech via Text-to-Speech and delivered to the customer
5. **Escalation** — bulk or complex orders are forwarded to the boutique owner
6. **Admin Dashboard (HTML interface)** — displays call logs, customer queries, and escalation cases so the owner can monitor performance
7. **Local Log Storage** — every call is recorded in `call_logs.csv` for tracking

## Tech Stack

| Layer | Technology |
|---|---|
| Voice/Telephony | Twilio Voice API |
| Backend | Python, Flask |
| Intent Detection | Rule-based keyword & pattern matching |
| Speech | Speech-to-Text / Text-to-Speech |
| Data Storage | Google Sheets API (catalog, orders, customers), local CSV (call logs) |
| Admin Interface | HTML dashboard |

## MVP Scope

| Component | Implementation |
|---|---|
| Voice Call Handling | Handles incoming calls via AI voice bot |
| Basic Intent Detection | Supports core queries — price, stock, bulk order |
| Live Product Data | Fetches catalog details from Google Sheets |
| Response Automation | Auto-replies using Text-to-Speech |
| Bulk Order Escalation | Forwards complex orders to the owner |
| Basic Dashboard | Displays call logs and query tracking |

## Impact

- Cuts 10–14 hours/week of manual query handling for boutique owners
- Brings affordable AI automation within reach of micro and small retail businesses
- Reduces miscommunication and returns by keeping product info accurate and real-time

## Project Context

Built as part of **Impact-AI-Thon 2026** (Track: Market and Minds) by Team **QUANTIXA**.

**Team:**
- **Sinega** — AI Engineer (model integration)
- **Jaya Dharshani R J** — Frontend Developer (dashboard + demo UX)
- **Subhiksha S** — Data Engineer (product database, business validation, real-world testing with boutique owners)

## Getting Started

```bash
# Clone the repository
git clone https://github.com/SUBHIKSHA-S-coder/voicebot-ai-boutique-automation.git
cd voicebot-ai-boutique-automation

# Install dependencies
pip install -r requirements.txt

# Set up environment variables (Twilio credentials, Google Sheets API key)
cp .env.example .env

# Run the Flask app
python app.py
```

## License

MIT
