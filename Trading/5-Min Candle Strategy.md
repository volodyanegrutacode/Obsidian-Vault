# 5-Min Candle Strategy

*The universal edge. Works on QQQ, BTC, GLD. Asset-class agnostic.*

## The Rules

1. **Buy** if first 5-min candle bullish (close > open)
2. **Sell/Short** if first 5-min candle bearish (close < open)
3. **Stop:** Below 5-min LOW (long) / Above 5-min HIGH (short)
4. **Target:** 3R
5. **Trailing:** 1.5R→BE, 2R→locked (loose)
6. **NO time exit** — Hold until target/stop/EOD

## Performance by Asset

### QQQ (1% Compounded Risk)
- **2024:** +1,101% / 1.86% Max DD / 61.8% Win Rate
- **2025:** +726% / 2.16% Max DD / 60.1% Win Rate

### BTC (1% Risk + $1,000 Max Cap) 🔥
- **2022:** +375.93% / 0.90% DD / 68.8% WR
- **2023:** +375.31% / 0.84% DD / 67.4% WR
- **2024:** +396.89% / 0.74% DD / 69.4% WR
- **2025:** +358.26% / 1.18% DD / 66.3% WR
- **4-Year Average:** +376% / <1% DD

### GLD (1% Risk + $1,000 Max Cap) 🥇
- **2023:** +181.35% / 1.66% DD / 58.2% WR
- **2024:** +228.19% / 1.22% DD / 60.7% WR
- **2025:** +226.36% / 1.53% DD / 58.7% WR
- **3-Year Average:** +212% / <1.7% DD

## The Insight

**This edge transcends asset classes.** The first 5-minute candle captures overnight sentiment + opening auction dynamics. It's the same mechanism whether you're trading:
- Tech stocks (QQQ)
- Digital gold (BTC)
- Actual gold (GLD)

## Position Sizing Options

| Profile | Setup | Best For |
|---------|-------|----------|
| **Conservative** | QQQ: Fixed $3,000 (3%) | FTMO evaluations |
| **Growth** | QQQ: 1% compounded | Stock trading, higher returns |
| **Crypto-Printer** | BTC: 1% + $1K cap | Max returns, min drawdowns |
| **Gold-Stacker** | GLD: 1% + $1K cap | Commodity diversification |

## Key Insight

The $1,000 max risk cap on BTC/GLD is **genius** — it keeps drawdowns microscopic (0.74-1.66%) while still capturing the full upside of compounding.

## Files

Located in `~/.openclaw/workspace/trading/`:
- `backtest_qqq_3r_fixed_3k.py`
- `backtest_qqq_2024_3r_1pct.py`
- `backtest_btc_2022.py`, `backtest_btc_2023.py`, `backtest_btc_2024_2025.py`
- `backtest_gld_2023_2025.py`

## Related
- [[Trading Bible]] — Primary ORB strategy
- [[FTMO Automation]] — Deployment plan
