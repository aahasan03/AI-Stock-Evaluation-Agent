# AI Stock Evaluation Agent

An AI agent built with Python and the OpenAI function calling API that automates stock evaluation. It pulls live and historical financial data through yfinance, scores a stock against a set of value investing criteria, and generates a stakeholder readable buy, hold, or sell recommendation.

## What it does

The agent uses OpenAI's function calling to orchestrate four tools:

- Fetches the current stock price
- Fetches the 5 year average closing price
- Fetches key financial metrics (P/E, PEG, ROE, P/B, D/E)
- Evaluates a buy decision against a set of threshold criteria (P/E, PEG, ROE, D/E)

The evaluation thresholds are standard value investing heuristics I set myself (for example P/E under 25, PEG under 1.5), not model generated values. Users can accept these defaults or enter their own thresholds when running the script.

## How to run it

1. Clone this repo
2. Install dependencies: `pip install -r requirements.txt`
3. Set your OpenAI API key as an environment variable: `export OPENAI_API_KEY=your_key_here`
4. Run the notebook or script and enter one or more ticker symbols when prompted

## Example output

```
Analyzing AAPL...
Agent Verdict for AAPL:
Based on the evaluation, AAPL is currently rated with a "HOLD / NEUTRAL" recommendation.
- P/E Ratio: 36.09 (target: <= 25.0)
- PEG Ratio: 2.48 (target: <= 1.5)
- Return on Equity (ROE): 148.75% (target: >= 15.00%)
- Debt-to-Equity Ratio: 78.44 (target: <= 150.0)
```

## Limitations

- The same P/E and PEG thresholds are applied across all sectors and are not sector adjusted
- Error handling is minimal and intended for a personal project, not production use

## Disclaimer
This project is for educational purposes only and does not constitute financial advice.

This project is for educational purposes only and does not constitute financial advice.
