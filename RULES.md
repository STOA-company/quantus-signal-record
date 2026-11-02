# Rules (fixed 2026-11-05)
Common: decide on the US close, execute at the next US open. Cost 0.15% one-way × total weight changed. Adjusted daily prices.

**Chip Hunter** — SOX index: 15 price channels (std-band and median-band, windows 120/60, 90/50, 50/25 × 5 entry/exit multipliers) give trend ∈ [0,1]. Volume-weighted MACD 12/26/9 regime on the last 200 bars. If directional confidence > 0.02 and regime score > 0.4: e = trend × (8 + leverage exposure), else e = trend; e clipped to [1.00, 1.75]. Weights: SMH = 2 − e, USD = e − 1 (e > 1), else SMH 100%.

**Regime Switcher** — month-end. mom(x) = mean of 1/3/6/12-month returns. If mom(TIP) ≤ 0 → best of {BIL, IEF} 100%; elif mom(SPY) > 0 → SPY 100%; else best of {BIL, IEF} 100%.

**Gold Bull** — daily. If SMA50(GLD) > SMA200(GLD) → GLD 100%; else BIL 100%.

Starting state (2026-10-30 close): Chip SMH 25% + USD 75% · Regime SPY 100% · Gold BIL 100%.
