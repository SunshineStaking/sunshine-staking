<p align="center">
  <img src="images/logo_sunshine.png" alt="Sunshine Staking" width="520">
</p>

<h1 align="center">Sunshine Staking</h1>

<p align="center">
  Sunshine Staking ☀️ is a control center that adapts native Solana staking to
  your financial habits.
</p>

<p align="center">
  <a href="../sunshine-staking-app">App</a>
  &middot;
  <a href="../sunshine-staking-app/tree/main/frontend">Frontend</a>
  &middot;
  <a href="../sunshine-staking-app/tree/main/backend">Backend</a>
  &middot;
  <a href="../sunshine-staking-app/tree/main/indexer">Indexer</a>
</p>

---

## What It Does

Sunshine Staking replaces inconvenient epochs with 1-click profit locking for
convenient periods, such as week or month. It brings aggregated analytics for
profitability and validator performance into one place, then makes group
redelegation more efficient and almost click-through.

## Architecture

```text
sunshine-staking-app/
|-- frontend/   Next.js app with wallet connection and staking UI
|-- backend/    Express API for Solana RPC, transaction builders, and data reads
|-- indexer/    Reward indexing worker for tracked stake accounts
`-- postgres    Local database used by the backend and indexer
```

The frontend never receives private keys from the backend. Staking endpoints
build unsigned or partially signed transactions, the connected wallet signs
client-side, and the backend confirms the submitted signature.