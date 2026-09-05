# trader.json (Trader → DEV)

Emit on status change so the site empty chair can show idle/working.

```json
{
  "time": "ISO-8601 with offset",
  "event": "trader.updated",
  "status": "idle|working",
  "mode": "paper",
  "live_approve": false,
  "open_ticket": "TICKET id or null",
  "pair": "PAIR or null",
  "note": "short status line"
}
```

- `status` idle = no approved open ticket; working = fill/exit clock running
- `live_approve` stays false until Alex unlocks (currently never)
- Copy to `dev/public/trader.json` for Pages
