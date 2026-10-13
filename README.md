# CryptoBilis drain trace

This is an interactive map of where the money stolen in the **9 October 2026 Ledger / CryptoBilis wallet drain** went. The victims had bought Ledger hardware wallets through the reseller CryptoBilis.

The map was rebuilt from public blockchain data on six chains: TRON, Bitcoin, Ethereum, BNB Chain, Polygon and Solana.

- `index.html`: the page. It shows a money-flow map you can click through, the key numbers, leads, and a searchable table of every traced transfer.
- `data/graph.js`: the grouped flow graph and the attacker and service addresses in each group.
- `data/edges.js` and `data/transfers.csv`: every traced transfer.

**Method.** Data came only from public explorers and node APIs: mempool.space, TronGrid, Blockscout, and public RPC nodes for Ethereum, BNB Chain, Polygon and Solana. Cross-chain swaps were resolved through the public status APIs of Relay, NEAR Intents and LI.FI. THORChain swaps were resolved from the memos written on-chain.

**Confidence.** Transfers and balances are recorded on-chain. Which wallets belong to the attacker is partly inferred from behaviour; the address lists mark each address as *confirmed* or *inferred*.

**Privacy.** Victim wallet addresses are deliberately not published. Victims appear only as totals for each chain.

**Disclaimer.** This is independent research, not legal advice, and not a statement by Ledger or any service mentioned. Corrections are welcome via issues.
