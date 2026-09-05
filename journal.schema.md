# journal.json — log (not one brief)

```json
{
  "paper_book_sol": 1.0,
  "ticket_sol_default": 0.01,
  "ticket_sol_gamble": 0.005,
  "paper_pnl_sol": 0,
  "paper_pnl_usd": 0,
  "live_pnl_sol": 0,
  "live_pnl_usd": 0,
  "entries": [
    {
      "time": "ISO-8601",
      "type": "PASS | WATCH | CALL | CLOSE | BRIEF",
      "names": ["..."],
      "ticket_id": "optional on CALL/CLOSE",
      "lane": "HOLD | GAMBLE | BUILD | null",
      "note": "one line",
      "pnl_sol": null,
      "pnl_usd": null,
      "sol_usd_at_fill": null
    }
  ]
}
```

- Paper book: **1.00 SOL**. Default ticket **0.01 SOL**, GAMBLE **0.005 SOL**.
- P&L display is **SOL + USD**. Mark USD from SOL at fill (`sol_usd_at_fill` / summed `paper_pnl_usd`).
- `pnl_sol` / `pnl_usd` only on CLOSE. Elsewhere null.
- Do not invent wins. paper/live stay 0 until a CLOSE updates them. **Live stays $0** until live unlock.
- Append after every JOURNAL / WATCH / CALL / CLOSE / BRIEF cycle.

## Public lexicon (locked)

- Public word is **skip**, not pass.
- Board: **Skipped** / **Called**
- X: `skipped N · called 0`
- Do **not** say pass on X, site, or public JOURNAL copy.
- Private gate log may still use PASS/KILL internally if needed.
