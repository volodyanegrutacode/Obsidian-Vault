# Daily Bias Backtest — Verdict Report

**Date:** 2026-07-09
**Tested:** the exact production `getDailyBias` scorer (OpenAlice `dev`, commit `3bb92a06`), replayed bar-by-bar via `scripts/daily-bias-backtest.ts` — no re-implementation, no drift.
**Data:** ~18.6 years of daily bars (2007-11 → 2026-07, n=4,680/symbol after 250-bar warmup) for ^NDX, GC=F, QQQ, GLD. Signal on day T close → evaluated on day T+1 (close-to-close and open-to-close). No look-ahead. Per-day CSVs in this folder.

## The honest verdict up front

**The daily bias score does NOT predict next-day direction. On neither market.** Treat it as a *regime/context descriptor*, not a forecast.

- **^NDX bullish:** 55.8% next-day up vs **55.5% baseline** (the index simply drifts up). +0.3pp is noise.
- **^NDX bearish:** only **45.3%** of bearish days closed down next day — worse than a coin flip. Bearish days actually averaged **+0.13%** next-day return (higher than bullish days' +0.04%). At a 1-day horizon, NDX weakness mean-reverts: the "bearish" state is closer to a contrarian *long* than a short signal.
- **Gold:** same shape, weaker. Bullish 53.7% vs 52.8% baseline; bearish 47.0% hit rate.
- **Naive long/short/flat strategy (no costs):** ^NDX **−17%** total over 18.6y vs buy-and-hold **+1,338%**. Gold −12% vs +393%. Shorting the bearish signal is how you lose money slowly for two decades.
- **"Long unless bearish" filter:** cuts ^NDX max drawdown −51.5% → −38.8%, but costs two-thirds of total return (+539% vs +1,338%) because it steps aside on exactly the days that bounce. Not worth it as an overlay either.
- **Score granularity:** no monotonic relationship. −6 (max-bearish) days on ^NDX were **up 54.4%** of the time. The ±3 threshold isn't miscalibrated — there's simply no next-day signal to calibrate to.
- **Open-to-close variant:** same conclusion (bullish 54.8% vs 54.7% baseline on ^NDX).
- **Robustness:** QQQ mirrors ^NDX and GLD mirrors GC=F almost exactly — the finding is real, not a data quirk.

## Why (and why this was predictable in hindsight)

Every component (EMA stacks, EMA200, RSI, MACD, prior-day break) is a **trend/regime descriptor**. Trend state describes *where you are*, not *what tomorrow does* — and at the 1-day horizon, equity indices are dominated by mean reversion, which points the *opposite* way from a trend signal. The scorer works exactly as designed; the design question ("does trend state predict tomorrow?") just has a negative answer.

## What the tool IS still good for

1. **Context, not prediction.** "We're in an uptrend above EMA200 with expanded vol" is true and useful for framing intraday trades — position sizing (ATR), which setups to prefer, where key levels sit (EMA20/50, prior day H/L). The tool's levels/regime output is the valuable part; the bullish/bearish label should not be traded directionally on its own.
2. **The real test still to run:** Vladimir trades MNQ *intraday* (ORB). The relevant question isn't "does bias predict tomorrow's close" but "**does the ORB strategy perform better on bias-aligned days?**" — a conditional filter test against the existing `workspace/` ORB backtests. That's a different, sharper experiment and could still show real value.
3. **Possible contrarian angle (treat with suspicion):** bearish state on ^NDX = 54.7% up next day, mean +0.13% — a mild mean-reversion long signal. Found in-sample after the fact, so verify out-of-sample before believing it.
4. **Multi-day horizon untested:** trend descriptors may work better at 5–20 day horizons than 1 day. Not tested here.

## Recommendation

- **Do not change the shipped scorer** — as a regime snapshot it's correct and well-guarded.
- **Do not use bias alone as a next-day directional signal.** The numbers above say no.
- Next experiment worth running: condition the QQQ/MNQ ORB backtest on the daily bias state (aligned vs opposed days) — that's where a regime filter can genuinely earn its keep.
- Pair with Kronos (4H ML forecast) for *timing*; use `getDailyBias` for *context and levels*. Log both daily to build the live track record.

## Headline tables

### Next-day close-to-close, hit rate vs baseline

| Symbol | Baseline up | Bullish hit (n) | Bearish hit (n) | Verdict |
|---|---|---|---|---|
| ^NDX | 55.5% | 55.8% (2682) | 45.3% (811) | no edge; bearish inverted |
| QQQ | 55.2% | 56.0% (2670) | 45.6% (822) | confirms ^NDX |
| GC=F | 52.8% | 53.7% (2017) | 47.0% (1202) | no edge |
| GLD | 52.8% | 52.9% (1981) | 46.9% (1238) | confirms GC=F |

### Strategy comparison, 2007-11 → 2026-07 (no costs)

| Symbol | Long/short/flat | Long-unless-bearish | Buy & hold |
|---|---|---|---|
| ^NDX | −17.1% (DD −53.8%) | +538.5% (DD −38.8%) | **+1,338.4%** (DD −51.5%) |
| GC=F | −12.0% (DD −51.4%) | +261.9% (DD −43.4%) | **+392.9%** (DD −44.4%) |

### Regime detail (bullish hit / bearish hit)

| Regime | ^NDX | GC=F |
|---|---|---|
| quiet | 58.2% / — | 56.2% / 41.8% |
| normal | 55.2% / 46.3% | 54.5% / 47.3% |
| expanded | 56.8% / 43.3% | 48.4% / 49.4% |

(Bullish-in-quiet is the least-bad cell on both markets; bearish is below 50% everywhere — i.e., systematically wrong-way at 1-day horizon.)

---
*Methodology: production scorer imported directly from `src/domain/analysis/daily-bias.ts`; yfinance daily bars; first 250 bars warmup; T-close signal vs T+1 return; no transaction costs; full per-day data in the four CSVs alongside this report.*
