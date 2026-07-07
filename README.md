# Flux — an Agentic Operating System for TransFi partnerships

**Live demo →** _https://mikengovn.github.io/flux/_

---

I'm **Michael Ngo**, Head of Growth at [TransFi](https://transfi.com). I built an AI agent application that functions as an **Agentic Operating System**.

The application features an infinite canvas where users can visualize how AI agents plan, decompose, and execute complex tasks in parallel.

The main entry point of the application is a search bar where users can paste the URL of a potential TransFi client. Once a URL is submitted, the underlying AI orchestrator automatically analyzes the business, decomposes the work into specialized subtasks, assigns them to dedicated AI agents, and visualizes the execution process on the infinite canvas. The ultimate goal is to generate a comprehensive sales strategy tailored to the potential client.

For example, if the user submits the following URL:

> [https://www.coindesk.com/business/2026/07/01/french-banking-giant-credit-agricole-rolls-out-euro-stablecoin-eurxt](https://www.coindesk.com/business/2026/07/01/french-banking-giant-credit-agricole-rolls-out-euro-stablecoin-eurxt)

The AI decomposes the work into multiple specialized agents, each responsible for a specific task.

**One AI agent identifies the actual potential client** mentioned in the article rather than the publisher. In this example, the identified client is Crédit Agricole — not CoinDesk.

**Another AI agent generates a visual payment flow diagram** illustrating a proposed collaboration between the downstream customer, the potential client, and TransFi. Since Crédit Agricole is launching the euro-pegged stablecoin EURXT, the proposed flow is:

1. An overseas importer makes a fiat payment.
2. TransFi receives the fiat funds.
3. TransFi converts the fiat into EUR and mints EURXT.
4. TransFi transfers EURXT to the supplier in Europe.
5. Crédit Agricole manages the EURXT ecosystem and related banking services for the supplier.

**Another AI agent identifies the most relevant decision-makers** within the company — C-level executives or Heads of Partnerships — and retrieves their LinkedIn profiles or business email addresses where available.

**The final AI agent prepares a ready-to-send cold outreach email** proposing a strategic partnership with TransFi. The email is concise, persuasive, and personalized, highlighting TransFi's unique value proposition — 250+ alternative payment methods across 70+ countries, serving leading crypto exchanges, banks, and remittance companies globally. It references the proposed payment flow and explains how TransFi can support the client's business.

---

## Try it with these prospects

| URL | What Flux does |
|---|---|
| `https://www.coindesk.com/business/2026/07/01/french-banking-giant-credit-agricole-rolls-out-euro-stablecoin-eurxt` | Filters the publisher, resolves **Crédit Agricole** as the prospect, designs the EURXT fiat-to-stablecoin settlement flow. |
| `https://qtfunded.quanttekel.com/` | Recognizes a **prop-trading platform**; proposes TransFi handles checkout fiat collection and settles USDT to the platform. |
| `https://moretapay.com/` | Recognizes a **stablecoin prefunding & payouts** model; proposes TransFi receives stablecoins, converts to local fiat, and executes QR payouts. |

Or paste any company URL — the app runs a live analysis and generates a bespoke strategy from scratch.

---

## What's inside

- **Infinite canvas** for single-company URLs — orchestrator → 4 specialized agents → deliverable, with pan / pinch-to-zoom.
- **Table view** for round-up articles — one row per prospect, every cell opens a detail panel.
- **Fix Diagram with AI** — describe a change to the payment flow in plain English and the AI regenerates it in place.
- **Contact enrichment** — where a verified email isn't available, Flux always surfaces at least one alternative signal (LinkedIn, press mention, or executive profile page).
- **TransFi product ontology** baked into every prompt — Fiat Collection, E-commerce Checkout, Fiat→Stablecoin Conversion, Redemption, Crypto On/Off-Ramp, Institutional OTC, Crypto Swap, Virtual Accounts, Cross-border Payouts, Treasury.
- **Publisher-vs-subject disambiguation** — news domains (CoinDesk, Bloomberg, Yahoo, odaily, etc.) are filtered out; only the primary subject of the article is treated as the prospect.
- **Ready-to-send cold email** — executive-tone, references the flow by numbered steps, cites TransFi's differentiators, signed by Aarav Menon, Strategic Partnerships.
- **Dark, glassmorphic UI** in TransFi's brand colours; fully responsive down to mobile.

---

## Run locally
Double-click `index.html` — it opens in your browser and works offline.

---

## Credit

Built by **Michael Ngo**, Head of Growth at TransFi.

For questions, corrections, or interest in partnering — reach out on LinkedIn.

## License

MIT — see [LICENSE](./LICENSE).
