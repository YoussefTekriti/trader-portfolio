# trader-portfolio: context for Claude

Owner: Youssef (Riyadh, UTC+3). Writing style: plain language, no em dashes, no mid-dot separators.

## What this is
Youssef's personal setup for the trader-skill pack (github.com/Jakeschincariol/trader-skill, MIT), with the skills in `.claude/skills/`.

## Decisions so far
- Budget: $20, paper mode, 10% cash buffer, 25% cap per stock, min order $1 (see `trader/config.json`).
- Broker: Amana. There is no Amana connector, so Claude only proposes orders and Youssef places them by hand. Never place or claim to place an order.
- Holdings and watchlist start empty (`trader/holdings.json`, `trader/watchlist.json`). Update them when he reports a trade or adds a ticker.
- A cloud scheduled task, "Trading pre-market brief", runs weekdays at 4:15pm Riyadh, before the US open, which is 5:30pm Riyadh now and 4:30pm during US daylight saving. It covers news, Congress trades and passing order proposals, and appends a line to `trader/brief-log.md`.

## Known limitation
Claude's cloud sandbox (and the desktop app's sandbox) block sec.gov, data.sec.gov, disclosures-clerk.house.gov and Yahoo Finance, so the cloud brief uses web search instead of the Python data scripts. Copycat (13F) cannot run there.
Running locally in Claude Code on his Mac, the scripts should reach those sites directly. Verify first with:
`python3 .claude/skills/trader-alerts/alerts.py clock` and `python3 .claude/skills/trader-pelosi/ptr.py --help`.
The SEC scripts need `sec_user_agent` in `trader/config.json` set to a real name and email. Ask Youssef which email to use; do not guess one.

## Open items
- Confirm the old scheduled task in the Claude desktop app was deleted.
- Pick tickers for the watchlist.
