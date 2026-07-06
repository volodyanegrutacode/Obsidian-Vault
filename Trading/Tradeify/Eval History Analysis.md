# 🔬 Eval History Analysis — the receipts

> **Why this note exists:** proof that the edge is real and the leak is behavioral, drawn from **43 real trades across 10 sessions** of the 2026 evals (May–June). When doubt or impatience shows up, re-read this. The numbers already settled the argument.

## The headline — the edge is real
| Metric | Value |
|---|---|
| Win rate | **33%** (14 wins / 29 losses) |
| Avg win | **+$1,551** |
| Avg loss | **−$291** |
| **Payoff ratio** | **5.3 : 1** |
| Net across sample | **+$13,266** |

A 33% win rate that still prints money is *only* possible with a big payoff ratio. I lose small and win big — **when I let a trade work.** This is not a strategy problem.

## Where all the damage came from
8 of 10 sessions were green. **100% of the loss came from 2 days** — 05-15 and 06-05:

| Date | Trades | Result | Signature |
|---|---|---|---|
| 2026-05-14 | 1 | +$993 | green |
| **2026-05-15** | 5 | **−$2,026** | **RED — 0 winners, all stop-outs** |
| 2026-05-18 | 5 | +$3,046 | 4 straight losers → +$4,426 |
| 2026-05-19 | 5 | +$5,488 | green |
| 2026-05-20 | 4 | +$2,210 | green |
| 2026-05-21 | 1 | +$764 | green |
| 2026-05-22 | 5 | +$2,773 | green |
| 2026-06-03 | 4 | +$1,089 | green |
| 2026-06-04 | 7 | +$963 | green |
| **2026-06-05** | 6 | **−$2,034** | **RED — 0 winners, all stop-outs** |

## The diagnosis — confirmed, not guessed
Both red days share one fingerprint that **never appears on a single green day**:

- **Stop-outs in under 20 seconds.** 05-15 ended on a 16s stop. 06-05 ended on a **9-second** then a **5-second** stop (−$509, −$259). A full stop hit that fast = I entered *into* a move already reversing = **I chased**, and I was **overleveraged** (big dollar loss, tiny time).
- **Back-loaded collapse.** The fast/biggest stops come *last*, after I'm already −$1,200+ down. That's the capitulation phase — no longer trading setups, just firing at the screen.
- **Pausing didn't save me.** On 06-05 I waited 10 minutes mid-tilt and still spiraled. Slowing down is not the fix. **Not trading is.**

## The insight that dictates the whole playbook
> I **cannot risk-manage my way out of this** with a loss limit, because my green and red days are statistical twins until the winner lands. On 05-18 I took **4 straight losses before a +$4,426** made the day. Any "stop after N losers / stop at −$X" rule that catches the red days also kills my comeback days.
>
> **Therefore the only lever is entry quality + fixed size — not a brake applied after the fact.** Fixed $200 risk removes the overleverage tool I tilt with. That is *why* $200 matters more than any daily-loss rule.

## What this proves for the plan
1. **Fixed $200/trade** kills the overleverage → the instant-stop spiral can't happen. ➜ [[Playbook]] §1
2. **Sub-20-second stop-out = hard kill-switch.** Zero false positives in the data. If it happens: platform off, log the emotion. ➜ [[Playbook]] §8
3. **Accept the slow.** ~20 trading days is fine. The impatience is the disease; the calendar is free.

*Related: [[Dashboard]] · [[Playbook]] · [[Trade Log]] · [[tradeify-funding-journey]]*
*Source data + scripts: `~/workspace/tradeify/analyze_evals.py`, `redday_sequences.py`*
