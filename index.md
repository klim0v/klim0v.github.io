## Portfolio

[comment]: <> (_[Download CV]&#40;/pdf/sample_presentation.pdf&#41;_)

---

### Experience

_December 2024 — Currently_

<img alt="NuConstruct" src="https://raw.githubusercontent.com/klim0v/klim0v.github.io/master/images/nuconstruct.svg" width="125" height="36">

[NuConstruct](https://nuconstruct.xyz/), Remote, UK

Leading MEV team on Ethereum, operating since 2020.

**Lead Blockchain Engineer (Ethereum)**

**_Skills_**: _Go, [go-ethereum](https://github.com/ethereum/go-ethereum), [MEV-Boost](https://github.com/flashbots/mev-boost/pull/855) / PBS, [TEE / Intel TDX](https://blog.ata.network/verifiable-private-and-decentralized-orderflow-processing-with-automata-linux-and-tool-daf0c345e73c), [Kurtosis](https://github.com/ethpandaops/ethereum-package), Kubernetes, Prometheus / Grafana._

Lead engineer on **[TOOL](https://docs.tool.limo/c8ce8e8aadf1/)** (Trustless Orderflow Operations Layer) — an extensive fork of go-ethereum that turns Ethereum's monolithic 12-second block-building pipeline into a decentralised, TEE-attested P2P network producing 1-second pre-confirmations on mainnet. The product addresses the centralisation and privacy gaps of today's MEV-Boost supply chain: instead of a few opaque builders gatekeeping orderflow, any operator can compete privately while still committing to common, hardware-verified execution logic.

- **Sub-slot consensus & leader election** — designed and shipped the protocol primitive that lets the network agree on one builder per 1-second sub-slot, so wallets and dApps see sub-second pre-confirmations instead of waiting a full slot.
- **Commitments & pre-confirmed-state pipeline** — pre-executed transaction bundles propagate across the network with their resulting state diffs, so reads (nonce, balance, receipt, simulation) return the already-committed value before the validator seals the block.
- **MEV-Boost-compatible relay** — built the relay / builder coordination layer that drives the standard validator registration / `getHeader` / `getPayload` flow and regenerates the payload envelope incrementally as new sub-slots arrive, so the validator always seals the most valuable block available right up to the deadline.
- **TEE-secured P2P transport** — mutual remote attestation gates every peer connection, so only genuine TOOL enclaves join the orderflow overlay. Integrated with [Automata Linux](https://blog.ata.network/verifiable-private-and-decentralized-orderflow-processing-with-automata-linux-and-tool-daf0c345e73c) (Intel TDX) for verifiable measurement of the shared execution container — proving the common logic is correct without exposing operators' private strategies.
- **Close collaboration with the Prysm consensus-client team** to surface and discuss several EL ↔ CL behaviours that deviated from spec — important context for an efficient, spec-compliant builder ↔ CL integration. Public discussions: [#15541](https://github.com/OffchainLabs/prysm/pull/15541), [#15548](https://github.com/OffchainLabs/prysm/pull/15548), [#15871](https://github.com/OffchainLabs/prysm/pull/15871). Also authored mev-boost [#855](https://github.com/flashbots/mev-boost/pull/855) — a concurrent version-negotiation race that could cause a missed slot.
- **Testing & operations** — multi-client integration harness on top of [Kurtosis](https://github.com/ethpandaops/ethereum-package) + Kubernetes: ephemeral devnets across all major EL × CL client pairs with full MEV-Boost relay flows. Observability via Prometheus & Grafana.

---

_April 2024 — March 2025_

<img width="62" height="71" alt="EVAA" src="https://github.com/user-attachments/assets/131638e4-f653-49d6-8086-ed7d214a5e2f" />

[EVAA Protocol](https://evaaprotocol.com/), Remote

The first decentralized lending protocol on TON.

**Lending Protocol Liquidator & Go SDK Author**

**_Skills_**: _Go, [evaa-go-sdk](https://github.com/evaafi/evaa-go-sdk), TON / TVM, FunC, [tonutils-go](https://github.com/xssnick/tonutils-go), [Hornet](https://github.com/iotaledger/hornet) ([IOTA](https://iota.org/)), ADNL / DHT / Overlay P2P, DEX routing._

- **Authored EVAA's official Go SDK** — [`evaafi/evaa-go-sdk`](https://github.com/evaafi/evaa-go-sdk), the team's open-source integration layer (config, asset, price, principal, transaction). Published on [pkg.go.dev](https://pkg.go.dev/github.com/evaafi/evaa-go-sdk).
- **Production liquidator bot in Go** that held the leading position on EVAA mainnet for an extended period against active competitors. _"His programming skills in Go and deep blockchain understanding helped him be the leading liquidator for a long time."_ — public recommendation from a competitor.
- **Custom P2P crawlers and connectors to best-in-class upstream nodes**, used to cut end-to-end inclusion latency for price-driven liquidations:
  - **TON** — ADNL / DHT / Overlay crawler that discovers and maintains direct P2P sessions with RPC-grade validator nodes, bypassing the public lite-server bottleneck.
  - **IOTA** — forked the [Hornet](https://github.com/iotaledger/hornet) IOTA full-node (Go) and tuned its peering layer for a privileged P2P link to the network's price-feed initiator + node-side pre-filtering of irrelevant transactions. The bot reacts at network speed, not at API-poll speed.
- Adapted the bot through EVAA's v2 protocol upgrade — one-shot bad-debt liquidation, reserve factor, custom-payload chaining into DeDust swaps.

---

_November 2022 — December 2024_

![ANKR](https://raw.githubusercontent.com/klim0v/klim0v.github.io/master/images/ankr-logo.png)

[Ankr](https://www.ankr.com/), Remote, United States

All-in-one Web3 development hub with high-performance RPC connections to 45+ blockchains.

**Blockchain Engineer (Backend)**

**_Skills_**: _Go, PostgreSQL, Kafka, ClickHouse, Redis, gRPC, Stripe, Grafana / Prometheus._

- **Premium plan billing** — shipped the per-API-credit Pay-as-You-Go model and the recurring "Deal" subscription, with Stripe (one-time + recurring USD card payments) plus on-chain USDT / USDC payment flows.
- **User-manager domain** — JWT-scoped private endpoints (`rpc.ankr.com/<chain>/<JWT>`), Projects, Team Accounts with role-based access (administration / finance / development), identity via MetaMask, Google, GitHub.
- **Usage-statistics pipeline** — Kafka ingest → ClickHouse aggregation → PostgreSQL transactional state → Redis hot paths, powering per-project request / latency / cost dashboards in Grafana + Prometheus.

---

_September 2019 — November 2022_

![Minter](https://raw.githubusercontent.com/klim0v/klim0v.github.io/master/images/minter-logo.png)

[Minter](https://www.minter.network/) ([GitHub](https://github.com/MinterTeam)), Remote, UK

Layer-1 DeFi blockchain on the Tendermint engine — DPoS, in-core AMM with order book, ETH / BSC bridges.

**Lead Golang Blockchain Core Developer**

**_Skills_**: _Go, [Tendermint](https://github.com/tendermint/tm-db/blob/v0.6.3/CHANGELOG.md#changelog), Cosmos SDK, [IAVL+](https://github.com/cosmos/iavl/blob/v0.14.3/CHANGELOG.md#0143-november-23-2020), [minter-go-node](https://github.com/MinterTeam/minter-go-node), gRPC, [grpc-gateway](https://github.com/MinterTeam/node-grpc-gateway), [minter-go-sdk](https://pkg.go.dev/mod/github.com/MinterTeam/minter-go-sdk/v2), Kubernetes._

- **Lead developer of [minter-go-node](https://github.com/MinterTeam/minter-go-node)** — owned Tendermint integration, IAVL+ state tree, transaction execution and Minter 2's in-core AMM with Order Book.
- **Owned [node-grpc-gateway](https://github.com/MinterTeam/node-grpc-gateway)** — single Protobuf source compiled into gRPC + REST + WebSocket + Swagger surfaces — and the official [minter-go-sdk (v2)](https://github.com/MinterTeam/minter-go-sdk).
- **Upstream fixes shipped with `@klim0v` attribution**:
  - [cosmos/iavl #324](https://github.com/cosmos/iavl/pull/324) — orphan-node cleanup and new `DeleteVersionsRange` API (released in [v0.14.3](https://github.com/cosmos/iavl/blob/v0.14.3/CHANGELOG.md)).
  - [tendermint/tm-db #134](https://github.com/tendermint/tm-db/pull/134) — bounded GoLevelDB iterator, measurable IAVL-pruning speedup (released in [v0.6.3](https://github.com/tendermint/tm-db/blob/v0.6.3/CHANGELOG.md)).
  - [btcsuite/btcutil #161](https://github.com/btcsuite/btcutil/pull/161) — BIP-32 leading-zero `ser256(p)` derivation fix.
- Spoke about Minter at [Minter Demo Day 2019](https://youtu.be/7bZREmkcpiY) and [other conferences](https://www.youtube.com/watch?v=hUx6rZLD_ok).

---

### Additional Experience (2016 – 2019)

| Period | Company | Role | Stack |
| :-- | :-- | :-- | :-- |
| Nov 2018 – Sep 2019 | [Dr.Cash](https://dr.cash/), Moscow | Golang Backend Developer | Go, gRPC, NATS, ClickHouse, PostgreSQL, Kubernetes / Helm |
| Jul 2018 – Nov 2018 | [Wormsoft](https://wormsoft.ru/), Moscow | Golang / PHP Backend Developer | Go (Buffalo / Revel), PHP (Yii2), MySQL, Docker |
| Oct 2017 – Jun 2018 | [Vitbiomed](http://vitbiomed.ru/), Moscow | Fullstack Developer | PHP (Laravel), MySQL, jQuery, Docker |
| Dec 2016 – Sep 2017 | [Darvin Studio](https://www.darvin-studio.ru/) / [Be on TOP](https://www.beontop.ae/), Vladimir | Fullstack JS / PHP Developer | PHP (Symfony, [in-house CMS](https://github.com/DarvinStudio)), MySQL, jQuery |

---

### Education / Training

- 2020, [Golang Course Teacher, Netology](https://youtu.be/wTbH3FpxI0o)
- 2020, The Process Communication Model
- 2017, [Vladimir State University](https://www.vlsu.ru/) — B.Sc., Applied Mathematics & Computer Science, [Institute of Applied Mathematics, Physics and Computer Science](http://ipmfi.vlsu.ru/)

---

### Recognition

- **TON Smart Challenge #2** — 1st place out of 181 (FunC, gas-optimised smart contracts)
- **TON Smart Challenge #5** & **TON Tact Challenge** — participant

---

### Blogs

- [Medium](https://medium.com/@klim0v)
- [Habr](https://habr.com/ru/users/klim0v/) — featured: ["Полный набор gRPC, RESTful JSON API, WS и Swagger из одного proto файла"](https://habr.com/ru/articles/496574/) ([English version on Level Up Coding](https://levelup.gitconnected.com/tools-for-implementing-a-golang-api-server-with-auto-generated-code-and-documentation-694262e3866c))

---

### Conferences

- 2020, [GolangConf / Ontico](https://golangconf.ru/2020/abstracts/6761) — [video](https://www.youtube.com/watch?v=Q9x1FVPDGu4)
- 2019, [Minter Demo Day](https://youtu.be/7bZREmkcpiY)

---

### Contacts

- [Telegram](https://t.me/klmff)
- [E-mail](mailto:crazyuser704@gmail.com)
- [LinkedIn](https://www.linkedin.com/in/klim0v/)
- [X.com](https://x.com/0xGoDev)

---
