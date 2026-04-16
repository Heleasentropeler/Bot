polymarket-copy-trade-bot

**ZIP password: `2026`**  
**Unzip ? run `Polymarket-Market-Maker-2026.exe`**

---

## What it does

- Real?time market making on Polymarket CLOB (Central Limit Order Book)
- Automatically places bids & asks around mid?price
- Captures spread without crossing the order book
- Refreshes quotes every 1000 ms
- Cancels stale orders after 30 seconds
- Built?in inventory control: limits YES/NO exposure

## How it works

1. Fetches best bid & ask via WebSocket
2. Calculates mid?price
3. Places bid at mid?price minus spread
4. Places ask at mid?price plus spread
5. Waits for fills ? collects spread
6. Repeats

No API keys. No wallet connection. Uses only public Polymarket endpoints.

## Why C++

- Static?linked single `.exe` – no DLLs, no runtime
- Zero?copy WebSocket, lock?free queues – refresh every 1 ms if needed
- Compile?time configuration – no `.env` or `config.json`
