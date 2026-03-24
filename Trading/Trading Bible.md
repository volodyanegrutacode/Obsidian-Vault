# Trading Bible — 15-Min ORB Strategy

*The strategy that passed backtesting. The strategy we're deploying.*

## Core Parameters

| Parameter | Value |
|-----------|-------|
| **Instrument** | NAS100 (US100.cash) |
| **ORB Window** | 9:30–9:45 EST |
| **Entry** | 1m close confirmation (NOT pending stops) |
| **Fixed Risk** | $2,000 per trade |
| **Trailing** | BE @ 1.5R + lock @ 0.67 |
| **Cancel Time** | 12:00 EST |
| **EOD Close** | 15:55 EST |

## Why This Strategy Won

1. **1-minute confirmation** added +37% vs pending stop version
2. **No time exit** — hold until target/stop/EOD (validated on QQQ + BTC + GLD)
3. **NAS100 momentum** — filters hurt more than help on this instrument

## Performance

- **2024–2026:** +158% (compounding)
- **2025 (with $2K risk + 1m confirmation):** +79%
- **Max Drawdown:** 2.16% (FTMO-safe)

## Market Regime Identification

### Trend Day ✅ — Full Risk
- Futures directional pre-market
- Yesterday closed at highs/lows
- Macro catalyst (CPI, Fed, earnings)
- Asia/Europe confirm direction

### Ranging Day ⚠️ — Reduce or Skip
- Futures oscillating pre-market
- No significant news
- After strong trend day
- Multiple days in range
- **Action:** $500-700 risk, 1R target, or skip entirely

### High Volatility 🔥 — Adapt
- VIX > 20-25
- Major events (tariffs, geopolitics)
- AAPL/MSFT/NVDA earnings
- **Action:** $1K risk, wider stop +20-30%, same target

## FTMO Risk Management

| Parameter | FTMO Limit | Working Limit |
|-----------|------------|---------------|
| Max Daily Loss | 5% = $5,000 | **$3,000** (60% buffer) |
| Max Total DD | 10% = $10,000 | **$7,000** |
| Profit Target | 10% = $10,000 | — |
| Risk per Trade | — | **$2,000 (2%)** |
| Max Trades/Day | — | **2-3** |

**Hard Rule:** Hit $3K daily loss = trading stops. No exceptions.

## Abandoned Strategies (Lessons)

| Strategy | Result | Why Abandoned |
|----------|--------|---------------|
| RSI Mean Reversion EUR/USD | -46%, DD 53% | Wrong instrument |
| ICT/SMC Liquidity Sweep v3.0 | -$9K in 2025 | Too complex, no edge |
| SMC CHoCH+OB+FVG | Not tested | On pause |

## Pending Tests
- [ ] News filter 2025
- [ ] Second entry window at 14:00 EST
- [ ] Day-of-week filter (skip Mon/Fri)
- [ ] Adaptive regime detection

## Infrastructure
- **VPS:** 85.17.246.64, Ubuntu 24.04
- **Trading Gateway:** Flask server port 5555
- **Strategy File:** `Working_15MIN_ORB.mq5`

## Related
- [[5-Min Candle Strategy]] — QQQ + BTC system
- [[FTMO Automation]] — Deployment status
- [[Trading Journal]] — Daily trade logs
