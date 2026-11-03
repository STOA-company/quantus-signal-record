# Quantus AI Traders — forward signal record

Simulated forward record of three rule-based traders (Chip Hunter, Regime Switcher, Gold Bull). **No client orders.** Rules fixed since the 2026-11-05 US close.

- Rules: [RULES.md](RULES.md)
- Records: `records/<trader>.csv`, one row per US trading day, appended at **07:30 KST (22:30 UTC)**, or 08:30 KST if prices are late (actual UTC time written as-is).
- Data: daily prices from EODHD. Chip Hunter's semiconductor regime uses the SOXX ETF series because the SOX index feed has no volume; each row's `source` column states the input used.
- Integrity: rows are append-only (corrections are new rows); `records/SHA256SUMS.log` gets one line per day with the SHA-256 of each file.
- First row: signal date 2026-11-05 close → execution 2026-11-06 open. Record runs 30 calendar days (to 2026-12-05).
- Rehearsal rows: `signals.csv` rows with `record=rehearsal` (signal dates before 2026-11-05) are dry runs of the same rules and are **not** part of the official record. The official record is the `record=official` rows from 2026-11-05.

License: data and documents under CC BY 4.0 ([LICENSE](LICENSE)).

Not investment advice. Simulated results do not guarantee future returns.
