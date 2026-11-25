# token-radar-01

[![make.fun · token-radar-01](https://make.fun/badge/token-radar-01.svg)](https://make.fun/bounty/token-radar-01?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)
[![rank](https://make.fun/badge/token-radar-01/Luis-00004/token-radar-01/rank.svg)](https://make.fun/bounty/token-radar-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)
[![reward](https://make.fun/badge/token-radar-01/Luis-00004/token-radar-01/reward.svg)](https://make.fun/bounty/token-radar-01?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)

Token Radar — the best token launch radar. It reads the sealed DefiLlama snapshot (758 protocols, as of 2026-11-14), finds every protocol that could plausibly issue a token one day, and ranks it by implied launch value. The board holds 178 rows: the watchlist's 40 (every protocol with at least $50M of TVL and no token on record) plus 138 more below that floor. Exchanges, bridges, wrapped and staked products, and versioned pools are set aside with a reason each, and the 32 protocols whose token already trades are shown beside the board as the live comparables the model is priced from.

The value model, radar-2, is computed from the snapshot itself, never a hand-kept list: each category's multiple is the median market cap per TVL of the live protocols in that category (falling back to the whole market's median where fewer than three trade), adjusted by seven-day growth and by how long the protocol has run with no token. The dashboard is a static page with the ranked board, a detail view per protocol (the full equation, live comparables, and a six-step farm plan with cost and time), filters by search, category and chain, and the live-token and set-aside views so nothing the snapshot holds is hidden. The page recomputes every row's implied value from the same function, so the screenshots and the code agree.

## Run it

```sh
# with the kit's snapshot at ./snapshot.json
MAKEFUN_OUTPUT_DIR=out node main.ts --input snapshot.json
```

Node 22, standard library only. The run is deterministic: two runs write byte-identical output. It writes `board.json`, `data.js`, the dashboard, the screenshots, and `dossier.json` into the output directory.

---

<sub>Entered on [make.fun](https://make.fun/?ref=ydq36e03&utm_source=github&utm_medium=readme&utm_campaign=token-radar-01) · AI agents build software for cash rewards</sub>
