# TrenchyTools

**One API key to launch and trade memecoins.** No RPC node, no Jito client, no IPFS keys.

Launch and trade on **pump.fun** and **PumpSwap** (Solana) and **pons** (Robinhood Chain) through a single HTTP API. The API builds unsigned transactions; your code signs them locally, so keys never leave your machine.

**[Website](https://trenchy.tools)** · **[Docs](https://trenchy.tools/docs)** · **[API spec](https://trenchy.tools/openapi.json)** · **[Agent instructions](https://api.trenchy.tools/AGENTS.md)** · **[X](https://x.com/trenchytools)**

## Start in 60 seconds

```bash
# 1. get a key (one call, no account)
curl "https://api.trenchy.tools/api/create-api-key?label=my-agent"

# 2. check the key
curl -H "x-api-key: ***" "https://api.trenchy.tools/api/me"

# 3. live capabilities: chains, launchpads, operations
curl -H "x-api-key: ***" "https://api.trenchy.tools/api/chains"
```

Then follow **[AGENTS.md](https://api.trenchy.tools/AGENTS.md)** — it is written for coding agents: every endpoint, field and error code, plus the launch and bundle flows.

## What you get

- **Launch**: `create` on pump.fun and pons, with dev buy, optional Jito bundle (up to 16 buyers), vanity mints
- **Trade**: buy/sell with `pool: "auto"` (follows the coin from curve to AMM), sells accept `"100%"`
- **Bundles**: launch + buyers in one block, Jito tip on the first transaction
- **Live data**: `subscribeNewToken`, `subscribeTokenTrade`, `subscribeMigration` over websocket

## Starters

| Repo | What |
|---|---|
| [pumpfun-starter](https://github.com/Trenchy-Tools/pumpfun-starter) | Solana: wallets, bundled launches, snipers, timed sells |
| [pons-starter](https://github.com/Trenchy-Tools/pons-starter) | Robinhood Chain: launches and trading (curve → Uniswap v4) |
| [wallet-mover](https://github.com/Trenchy-Tools/wallet-mover) | create, fund, split and consolidate wallets across chains |

Live demos: [pumpfun.trenchy.tools](https://pumpfun.trenchy.tools) · [pons.trenchy.tools](https://pons.trenchy.tools) · [mover.trenchy.tools](https://mover.trenchy.tools)

## Use it from an agent

```
openclaw skills install trenchytools
```

Or paste this into any coding agent:

> Read https://api.trenchy.tools/AGENTS.md and https://trenchy.tools/openapi.json, then build me a pump.fun bot that buys a coin when it launches and sells half at 2x. Save every wallet you create to a file before funding it.
