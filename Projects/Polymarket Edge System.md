# Polymarket Edge System

**Goal:** Extract alpha from prediction markets by modeling resolution probability better than the crowd.

**Core Principle:** Price = Implied Probability. If our model says 70% and market says 55%, we have edge.

---

## The Three Phases

### Phase 1 — Research (No Money Needed)

**Objective:** Build the edge detection system

**Steps:**
1. Install `py-clob-client` (Polymarket's Python client)
2. Pull historical market data:
   - Politics (elections, legislation)
   - Sports (outcomes, props)
   - Crypto (price predictions, events)
   - Macro (CPI, Fed decisions, GDP)
3. Build scoring model:
   - Resolution probability (our model)
   - Current market price
   - Edge = |our_prob - market_price|
4. Identify which market types are most predictable
5. Create Ford skill: `polymarket-scanner`
   - Scan all active markets
   - Flag biggest price/probability discrepancies
   - Output: watchlist with edge scores

**Deliverable:** Working scanner that flags +EV opportunities

---

### Phase 2 — Paper Trading

**Objective:** Validate edge without capital risk

**Setup:**
- `polymarket-paper-trader` with MCP integration
- Ford as trading agent (receives alerts, makes decisions)
- All decisions logged to Obsidian: `Trading/Polymarket/Paper/YYYY-MM-DD.md`

**Track:**
- Hit rate by market type
- Edge magnitude vs. actual win rate
- Optimal sizing logic
- Kelly criterion application
- Drawdown patterns

**Deliverable:** 100+ paper trades with statistical validation

---

### Phase 3 — Live (Small)

**Objective:** Deploy validated edge with real capital

**Requirements:**
- Polygon wallet (MetaMask or similar) — FREE
- USDC on Polygon — $200-500 initial
- API keys configured

**Rules:**
- Only trade markets where backtest showed edge
- Max 2% risk per position
- Stop if 10% drawdown
- Daily P&L logged automatically

**Scale:**
- Month 1: $200-500
- Month 2+: Add profits, never add fresh capital until 3x initial

---

## Technical Stack

| Component | Tool |
|-----------|------|
| Data API | py-clob-client |
| Wallet | MetaMask (Polygon) |
| Trading Agent | Ford via MCP |
| Logging | Obsidian daily notes |
| Analysis | Python + OpenAlice tools |

### Trading Stack Details

**Official framework (Polymarket/agents):**
- Python, MIT licensed, 2.6k stars
- Integrates market data, RAG (Chroma vector DB), and LLM reasoning → autonomous trading
- ⚠️ Built for OpenAI models — needs OPENAI_API_KEY
- Needs: POLYGON_WALLET_PRIVATE_KEY + USDC funded wallet

**py-clob-client — the building block:**
- `pip install py-clob-client`
- Read-only market data: **no auth needed** (great for research/backtesting)
- Full trading: needs wallet private key
- You're in Netherlands = **not US-restricted ✓**

---

## Backtesting Tools

| Tool | Stars | Language | Best For |
|------|-------|----------|----------|
| **QuantDinger** | 1,046 | Python | Full algo research + live execution |
| **polymarket-paper-trader** | 10 | Python | AI agent paper trading + MCP server |
| **prediction-market-backtesting** | 32 | Rust | Professional-grade Nautilus fork |
| **polymarket-crypto-toolkit** | 55 | Python | Plugin-based strategy testing |

**Best starting point:** `polymarket-paper-trader` — has MCP server support, so Ford can interact with it directly, zero real money risk.

---

## Market Types to Test

**Politics** — Resolution: election results, polling data
- Edge source: Better polling aggregation, early voting data

**Sports** — Resolution: game outcomes, player props
- Edge source: Injury news timing, weather, matchup models

**Crypto** — Resolution: price levels, event outcomes
- Edge source: On-chain data, exchange flows, funding rates

**Macro** — Resolution: CPI, Fed decisions, GDP
- Edge source: Nowcasting models, alternative data

---

## Success Metrics

| Phase | Metric | Target |
|-------|--------|--------|
| 1 | Markets scanned | 1000+ |
| 1 | Edge identified | >5% discrepancy |
| 2 | Paper trades | 100+ |
| 2 | Win rate | >60% |
| 2 | ROI | >20% |
| 3 | Live trades | 50+ |
| 3 | Win rate | >55% (lower variance) |
| 3 | Monthly ROI | >15% |

---

## Risk Management

- Max position: 5% of bankroll
- Max daily loss: 10% of bankroll
- Stop trading if 3 consecutive losses
- Review edge model weekly

---

## First Action

**Today:**
1. Install py-clob-client: `pip install py-clob-client`
2. Pull 30 days of resolved market data
3. Build basic edge scanner
4. Test on 5 active markets

**This Week:**
- Complete Phase 1
- Log 20+ market scans
- Identify 3+ markets with clear edge

---

## Related
- [[Current Active Projects]]
- [[Trading Bible]]
- [[Risk Management Rules]]

---

*Created: March 25, 2026*
*Status: Phase 1 — Research*
