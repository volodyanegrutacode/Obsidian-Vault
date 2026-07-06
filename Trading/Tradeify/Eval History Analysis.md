# 🔬 Eval History Analysis — the receipts

> **Why this note exists:** proof of what's real and what's the leak, from my **full Tradezella history: 355 fills → 286 real positions, Apr 2025 → Jun 2026** (~48 trading days, all accounts incl. the competition). When doubt or impatience shows up, re-read this. The numbers already settled the argument.
>
> ⚠️ *Total net below (+$25,401) is from a hand-parsed paste — cross-check against Tradezella's lifetime P&L. Data + scripts: `~/workspace/tradeify/full_analysis.py`, `all_trades_raw.txt`.*

## The headline — I am a net-profitable trader
**Total net across everything: +$25,401** over 15 months. The edge is real and durable. The job is not "find an edge," it's "stop handing it back."

## 🎯 THE MAIN CONCLUSION — size is the disaster amplifier
My tilt behavior is roughly **constant**. What scales the damage is **contract size**. Worst single day, by the size I was trading at the time:

| Size regime | Worst day |
|---|---|
| 5-lot (Apr '25) | −$2,298 |
| 10-lot (2026 evals) | −$2,092 |
| **20-lot (competition)** | **−$5,288** |

Same behavior, 2.5× the crater. **The fixed-$200 rule isn't there to stop me tilting — it's there to make tilting survivable.** Give myself 20-lot room and I *will* eventually have a −$5k day. This is proven across 15 months, not a theory.

Supporting test — *revenge-sizing is only mild on average* (size after a loss 10.8 lots vs after a win 9.5; peak size on red vs green days ~equal at 9.1 vs 9.3). So I don't systematically balloon size — but when the account *lets* me (competition, no cap), one tilt session becomes a catastrophe. **The cap removes the failure mode.**

## By account / period
| Period | Net | Win% | Payoff | Note |
|---|---|---|---|---|
| Apr–Jun '25 evals | −$1,469 | 38% | 1.4 | early, no edge yet |
| Oct '25 eval | +$1,052 | 32% | 2.6 | |
| Nov '25 (pre-comp) | +$4,132 | 50% | 2.9 | |
| **Nov '25 COMPETITION** | +$2,934 | 28% | 2.8 | 18 lots avg · +$8,838 best day · **−$5,288 worst** |
| Jan–Mar '26 evals | **−$3,081** | 18% | 0.6 | ⚠️ **worst stretch ever** |
| **May–Jun '26 (50k evals)** | **+$20,836** | 48% | 2.0 | the bulk of the profit |

## Other confirmed findings
- **The competition proves I can win aggressive** (+$2,934 net, one +$8,838 day) — but at −$5k daily variance. For *funded survival* that variance is the enemy, not the edge. Different game (see [[Dashboard]]).
- **Jan–Mar '26 was a real disaster** (0.6 payoff, 18% win rate — losing more per loss than making per win). The anti-pattern. Its signature trade: 23 Mar held **9h 44m for −$1,445**, a 2-lot bag-hold — the exact opposite of my edge (cut fast, let winners run).
- **Tilt fingerprint (from the 2026 evals):** stop-outs in **under 20 seconds** appear *only* on blow-up days, never on a green day. Zero false positives. ➜ hard kill-switch, [[Playbook]] §8.
- **Damage is back-loaded** — the worst/fastest stops come after already −$1,200+ down (capitulation phase). Pausing didn't help (10-min gap on 06-05, still spiraled). Slowing down ≠ fix; *not trading* is.

## What this dictates
1. **Fixed $200/trade (~4–5 MNQ)** — the size cap that mechanically removes the −$5k-day failure mode. ➜ [[Playbook]] §1
2. **Same size winning or losing**, define stop first then size. ➜ [[Playbook]] §1
3. **Sub-20s stop-out = platform off, log the emotion.** ➜ [[Playbook]] §8
4. **Accept the slow (~20 days).** The impatience is the disease; the calendar is free.

*Related: [[Dashboard]] · [[Playbook]] · [[Trade Log]]*
