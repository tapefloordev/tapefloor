# journal.json — log (not one brief)

```json
{
  "paper_book_sol": 0.959529,
  "paper_pnl_sol": -0.040471,
  "paper_pnl_usd": 0,
  "live_pnl_sol": 0,
  "live_pnl_usd": 0,
  "size_rule": "size=4% book_now; risk=1% at -25% stop; book_now=1+sum(paper_pnl_sol)",
  "entries": [
    {
      "time": "ISO-8601",
      "date_mt": "YYYY-MM-DD (America/Denver) — required on CLOSE for 23:00 card",
      "type": "PASS | SKIP | WATCH | OPEN | DRAFT | CALL | CLOSE | BRIEF",
      "names": ["..."],
      "ticket_id": "optional on OPEN/CALL/CLOSE",
      "lane": "HOLD | GAMBLE | BUILD | null",
      "note": "one line",
      "pnl_sol": null,
      "pnl_usd": null,
      "book_after": null,
      "sol_usd_at_fill": null
    }
  ]
}
```

- Compound book: `book_now = 1 + sum(paper_pnl_sol)`. Size = 4% of book_now. Risk = 1% at −25% stop.
- `pnl_sol` / `pnl_usd` only on CLOSE. Elsewhere null.
- On every **CLOSE**: write `date_mt`, `pnl_sol`, `pnl_usd`, and **`book_after`** (`= 1 + cumulative paper_pnl_sol after this CLOSE`) so DEV can draw the equity line.
- Paper fills use type **OPEN**. **CALL** = posted CALL-DRAFT only.
- Do not invent wins. Live stays $0 until live unlock.
- Append after every JOURNAL / WATCH / CALL / CLOSE / BRIEF cycle.

## Public lexicon (locked)

- Public word is **skip**, not pass.
- Board: **Skipped** / **Called**
- Do **not** say pass on X, site, or public JOURNAL copy.
