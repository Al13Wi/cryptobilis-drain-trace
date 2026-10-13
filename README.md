# CryptoBilis drain trace

This is an interactive map of where the money stolen in the **9 October 2026 Ledger / CryptoBilis wallet drain** went. The victims had bought Ledger hardware wallets through the reseller CryptoBilis.

The map was rebuilt from public blockchain data on six chains: TRON, Bitcoin, Ethereum, BNB Chain, Polygon and Solana.

**Live page:** https://al13wi.github.io/cryptobilis-drain-trace/

## Reading the map
- **Lanes and columns.** Each horizontal band is one blockchain, and each column is one more step (hop) away from the victims.
- **Boxes** are wallets. Boxes with a frame are services or exchanges. Dashed boxes are victim totals.
- **Filled boxes** hold funds right now: black means held, hatched means frozen, orange means held *and* freezable by the stablecoin issuer.
- **Lines** are transfers; thicker lines carry more money.
  - **Solid** means confirmed: on-chain, or resolved from a service's own record.
  - **Dashed** means a high-confidence match: timing and exchange rate, or Tornado Cash demixing.
  - **Dotted** means a medium match.
- **Two views.** `groups` is the overview. `wallets` shows every wallet; stacks of identical wallets open when you click them.
- **Direct links.** `#wallets` opens the wallet view. `#find=<address or tx hash>` opens the map focused on that wallet.

## Files
- `index.html`: the page. It contains the map, the key findings, the leads, a searchable table of every traced transfer, and the method notes.
- `data/trace.js`: the map data (wallets, services, transfers, stacks, groups).
- `data/edges.js` and `data/transfers.csv`: every traced transfer.

## Method
Data came only from public explorers and node APIs: mempool.space, TronGrid, Blockscout, and public RPC nodes. Cross-chain swaps were resolved through the public status APIs of Relay, NEAR Intents and LI.FI. THORChain swaps were resolved from the memos written on-chain.

Which wallets belong to the attacker is partly inferred from behaviour; each wallet's details panel states its attribution.

The map's look takes its cue from layered "case file" flow maps: lanes per chain, crossing reduction, and S-curves. It is drawn with plain SVG and has no dependencies.

## Privacy
Victim wallet addresses and their transaction hashes are deliberately not published. Victims appear only as totals per chain.

## Disclaimer
This is independent research, not legal advice, and not a statement by Ledger or any service mentioned. Corrections are welcome via issues.
