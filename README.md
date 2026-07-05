# Flux — an Agentic Operating System for TransFi partnerships

**Live demo →** _replace this with your GitHub Pages URL once published (see [Publish](#publish-on-github-pages-in-3-clicks) below)_

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
| `https://bitcoinfoundation.org/news/nft/best-web3-games/` | Detects a **round-up article**; switches to the table view and generates a bespoke strategy for each of Sky Mavis, The Sandbox, and Immutable. |

Or paste any company URL — the app runs a live Anthropic-powered web analysis and generates a bespoke strategy from scratch.

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

## Publish on GitHub Pages in 3 clicks

The whole app is a single self-contained `index.html` file — no build step, no server. Ideal for GitHub Pages.

1. **Create a public GitHub repo** (e.g. `flux`) and upload the contents of this folder (`index.html`, `README.md`, `LICENSE`).
2. **Settings → Pages** → set _Source_ to **`main` branch / (root)** → **Save**.
3. Wait ~30 seconds. Your live URL will be **`https://<your-username>.github.io/<repo-name>/`**. Share it.

That's it. No secrets, no keys, nothing to configure.

### Or with the command line

```bash
gh repo create flux --public --source . --push
gh api -X POST repos/:owner/flux/pages -f 'source[branch]=main' -f 'source[path]=/'
```

---

## Run locally

No install required. Either:

```bash
# Option A: just open the file
open index.html

# Option B: serve on a local port (some browsers restrict fetches on file://)
python3 -m http.server 8000
# then visit http://localhost:8000
```

---

## How the AI calls work

Flux sends prompts directly to Anthropic's `/v1/messages` endpoint (`claude-sonnet-4-6`) using the browser's `fetch`. No API key is embedded — the app is designed to run inside Anthropic-hosted environments (e.g. Claude.ai artifacts) that authenticate the request server-side, and to gracefully fall back to a curated / offline blueprint when the live API is unreachable. This keeps the demo shareable without exposing credentials.

If you fork Flux to run it as an authenticated tool of your own, wire the API key at your proxy layer — never hard-code it into `index.html`.

---

## Credit

Built by **Michael Ngo**, Head of Growth at TransFi.

For questions, corrections, or interest in partnering — reach out on LinkedIn.

## License

MIT — see [LICENSE](./LICENSE).
