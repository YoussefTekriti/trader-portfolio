# trader-portfolio

Personal state for the daily trading brief, built on the trader-skill pack by Jake Schincariol (MIT, see .claude/skills/LICENSE-trader-skill).

## Files
- `trader/config.json`: budget ($20), 10% cash buffer, 25% cap per stock, paper mode on. Orders are placed by hand in Amana.
- `trader/holdings.json`: what you own. Update it after each trade.
- `trader/watchlist.json`: extra tickers to watch.
- `trader/brief-log.md`: one line per daily brief.

## Daily brief (weekdays, before the US open)
1. Headlines and SEC filings for holdings and watchlist.
2. New Congress trade disclosures touching those tickers.
3. Proposed orders, checked by trader-budget and trader-risk. Nothing is executed: you decide and place the trade in Amana.

Not financial advice.
