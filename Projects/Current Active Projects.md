# Current Active Projects

*What's in flight right now. Updated continuously.*

## 🎯 Primary: FTMO Deployment

**Status:** System built, awaiting live activation

| Task | Status | Blocker |
|------|--------|---------|
| ORB strategy validated | ✅ Complete | — |
| MT5 on VPS | ✅ Deployed | — |
| EA coded | ✅ Complete | — |
| Risk manager | ✅ Complete | — |
| **Live activation** | ⏳ Waiting | US100 range breakout |

**Next Action:** Monitor US100 for clean breakout, then activate

---

## 📊 Trading Infrastructure

**VPS:** 85.17.246.64 (Ubuntu 24.04)
- Trading gateway: Flask on port 5555
- MT5: Deployed
- EA: `Working_15MIN_ORB.mq5`

**Risk Settings:**
- Daily loss limit: $3,000 (hard stop)
- Per trade risk: $2,000
- Max trades/day: 2-3

---

## 📚 Learning

**Linux:** In progress
- Virtual environments: ✅ Mastered
- VPS management: In progress
- Goal: Solid operational competence

---

## 🔄 Pending Tests (Trading)

1. News filter on ORB 2025
2. Second entry window at 14:00 EST
3. Day-of-week filter (Mon/Fri skip)
4. Adaptive regime detection

---

## 📝 Notes

- CDCP Certification: ✅ PASSED (March 3, 2026)
- Strategy validated on QQQ + BTC + GLD
- Multi-strategy portfolio planned for future

---

## 🎲 NEW: Polymarket Prediction Edge System

**Status:** Phase 1 — Research & Setup

**The Edge:** Price/Probability discrepancy in prediction markets. If Ford can model resolution better than the crowd, we extract alpha.

### Phase 1 — Research (No Capital Required)
- [ ] Install py-clob-client
- [ ] Pull historical market data (politics, sports, crypto)
- [ ] Build scoring model: resolution probability vs. current price
- [ ] Identify most predictable market types
- [ ] Create Ford skill for scanning Polymarket markets

### Phase 2 — Paper Trading
- [ ] Set up polymarket-paper-trader with MCP
- [ ] Run Ford as trading agent
- [ ] Log all decisions to Obsidian
- [ ] Track: hit rate, edge per market type, sizing logic

### Phase 3 — Live Deployment
- [ ] Fund Polygon wallet ($200-500 USDC)
- [ ] Trade only markets with validated edge
- [ ] Scale based on backtest results

**Requirements:**
- Polygon wallet (MetaMask) — free
- USDC on Polygon — fund when ready
- OpenAI API key OR adapt to Kimi/Groq

**First Action:** Install py-clob-client, pull data, build market scanner skill

---

---

## 📈 NEW: IBKR Options Data Integration

**Status:** Planning — High Priority

**Why:** Options sentiment (P/C ratio, unusual volume, IV skew) provides edge for ORB timing and Congressional trade confirmation.

### What Options Data Enables:
| Metric | Use Case |
|--------|----------|
| **Put/Call Ratio** | Fear/greed gauge — extreme readings = reversal signals |
| **Unusual Volume** | Smart money detection — Congress + options flow = conviction |
| **IV Skew** | Tail risk pricing — crash hedges or complacency |
| **Max Pain** | Market maker target — where price gravitates |
| **Greeks** | Synthetic positioning — delta = stock exposure |

### Implementation Plan:
1. **Open IBKR Paper Account** — Free, API access
2. **Enable Options Data Feed** — Free real-time quotes
3. **Connect to OpenAlice** — Add IBKR as data source
4. **Build Options Scanner** — Morning briefing: SPY/QQQ P/C, unusual activity
5. **Congressional + Options** — Cross-reference: Congress buys + call volume spike = alert

### Deliverables:
- Options sentiment in morning briefing
- Unusual options flow alerts
- Congressional/options conviction scoring
- ORB timing enhancement (P/C extremes)

**Cost:** Free (IBKR paper + data feed)
**Timeline:** After FTMO live activation

---

## Related
- [[Trading Bible]]
- [[5-Min Candle Strategy]]
- [[Vladimir Negruta]]
- [[Polymarket Edge System]]
- [[IBKR Options Integration]]
