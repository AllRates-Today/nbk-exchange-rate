# National Bank of Kazakhstan Exchange Rates API — nbk-exchange-rate

[![npm version](https://img.shields.io/npm/v/nbk-exchange-rate.svg)](https://www.npmjs.com/package/nbk-exchange-rate)
[![license](https://img.shields.io/npm/l/nbk-exchange-rate.svg)](https://github.com/AllRates-Today/nbk-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/nbk-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/KZT today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fnbk%3Fsource%3DUSD%26target%3DKZT&query=%24.rate&label=USD%2FKZT%20published%20by%20National%20Bank%20of%20Kazakhstan&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/nbk/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fnbk%3Fsource%3DUSD%26target%3DKZT&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/nbk/)

**Official National Bank of Kazakhstan (Kazakhstan) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers National Bank of Kazakhstan itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — National Bank of Kazakhstan's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2016** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number National Bank of Kazakhstan itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest National Bank of Kazakhstan table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/nbk?source=USD&target=KZT"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/nbk').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full National Bank of Kazakhstan table, straight from the central bank's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the central bank publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-09** by National Bank of Kazakhstan — 48 rates. Updated 2026-10-09.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AED | KZT | reference | 122.24 |
| AMD | KZT | reference | 1.247 |
| AUD | KZT | reference | 311.7 |
| AZN | KZT | reference | 264.86 |
| BRL | KZT | reference | 89.41 |
| BYN | KZT | reference | 147.02 |
| CAD | KZT | reference | 314.89 |
| CHF | KZT | reference | 538.68 |
| CNY | KZT | reference | 66.98 |
| CZK | KZT | reference | 20.58 |
| DKK | KZT | reference | 67.18 |
| EGP | KZT | reference | 8.58 |
| EUR | KZT | reference | 502.05 |
| GBP | KZT | reference | 592.69 |
| GEL | KZT | reference | 175.03 |
| HKD | KZT | reference | 57.21 |
| HUF | KZT | reference | 1.37 |
| IDR | KZT | reference | 0.02509 |
| ILS | KZT | reference | 145.76 |
| INR | KZT | reference | 4.64 |
| IRR | KZT | reference | 0.000254 |
| JPY | KZT | reference | 2.84 |
| KGS | KZT | reference | 5.13 |
| KRW | KZT | reference | 0.3338 |
| KWD | KZT | reference | 1457.12 |
| MDL | KZT | reference | 25.25 |
| MNT | KZT | reference | 0.1249 |
| MXN | KZT | reference | 24.89 |
| MYR | KZT | reference | 109.82 |
| NOK | KZT | reference | 46.89 |
| OMR | KZT | reference | 1166.17 |
| PKR | KZT | reference | 1.62 |
| PLN | KZT | reference | 114.67 |
| QAR | KZT | reference | 123.17 |
| RON | KZT | reference | 93.98 |
| RUB | KZT | reference | 5.26 |
| SAR | KZT | reference | 119.58 |
| SEK | KZT | reference | 44.8 |
| SGD | KZT | reference | 350.21 |
| THB | KZT | reference | 13.33 |
| TJS | KZT | reference | 48.96 |
| TRY | KZT | reference | 9.12 |
| UAH | KZT | reference | 10 |
| USD | KZT | reference | 448.94 |
| UZS | KZT | reference | 0.038 |
| VND | KZT | reference | 0.01734 |
| XDR | KZT | reference | 607.05 |
| ZAR | KZT | reference | 26.91 |

Source: [Official rates published by NBK, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/nbk/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install nbk-exchange-rate
```

```bash
yarn add nbk-exchange-rate
```

```bash
pnpm add nbk-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/nbk-exchange-rate`](https://www.npmjs.com/package/@allratestoday/nbk-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'nbk-exchange-rate';

const pair = await getRate('USD', 'KZT', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official National Bank of Kazakhstan rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'KZT', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'nbk',
  name: 'National Bank of Kazakhstan',
  rate_date: '2026-10-08',   // National Bank of Kazakhstan's own publication date
  source: 'USD',
  target: 'KZT',
  rate: 447.14,
  rate_type: 'reference',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'nbk-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'nbk',
  name: 'National Bank of Kazakhstan',
  rate_date: '2026-10-08',
  rates: [
    { "base": "USD", "quote": "KZT", "type": "reference", "value": 447.14 },
    // … the rest of the published table (48 currencies vs KZT)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2016 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'nbk-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'KZT' });
```

**Response:**

```javascript
{
  bank: 'nbk',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'nbk-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'KZT', from: '2026-01-01', to: '2026-10-08' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'nbk',
  source: 'USD',
  target: 'KZT',
  from: '2026-01-01',
  to: '2026-10-08',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-08', rate: 447.14, rate_type: 'reference', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

National Bank of Kazakhstan currently publishes rates covering **48 currencies** against the KZT (as of the latest table):

🇦🇪 `AED` · 🇦🇲 `AMD` · 🇦🇺 `AUD` · 🇦🇿 `AZN` · 🇧🇷 `BRL` · 🇧🇾 `BYN` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇳 `CNY` · 🇨🇿 `CZK` · 🇩🇰 `DKK` · 🇪🇬 `EGP` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇬🇪 `GEL` · 🇭🇰 `HKD` · 🇭🇺 `HUF` · 🇮🇩 `IDR` · 🇮🇱 `ILS` · 🇮🇳 `INR` · 🇮🇷 `IRR` · 🇯🇵 `JPY` · 🇰🇬 `KGS` · 🇰🇷 `KRW` · 🇰🇼 `KWD` · 🇲🇩 `MDL` · 🇲🇳 `MNT` · 🇲🇽 `MXN` · 🇲🇾 `MYR` · 🇳🇴 `NOK` · 🇴🇲 `OMR` · 🇵🇰 `PKR` · 🇵🇱 `PLN` · 🇶🇦 `QAR` · 🇷🇴 `RON` · 🇷🇺 `RUB` · 🇸🇦 `SAR` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇹🇭 `THB` · 🇹🇯 `TJS` · 🇹🇷 `TRY` · 🇺🇦 `UAH` · 🇺🇸 `USD` · 🇺🇿 `UZS` · 🇻🇳 `VND` · `XDR` · 🇿🇦 `ZAR`

## 🏛️ Source

The National Bank of Kazakhstan is the central bank of the largest economy in Central Asia. It sets official tenge exchange rates for around 40 currencies each business day, used for accounting, customs and tax valuation across Kazakhstan.

- Publisher's own page: [Daily official market exchange rates](https://nationalbank.kz/en/exchangerates/ezhednevnye-oficialnye-rynochnye-kursy-valyut) · [nationalbank.kz](https://nationalbank.kz)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [National Bank of Kazakhstan rates page](https://allratestoday.com/central-bank-rates-api/nbk/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- National Bank of Kazakhstan quotes **KZT per 1 unit of foreign currency** (e.g. `base: "USD", quote: "KZT"` means KZT per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`reference` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official National Bank of Kazakhstan rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/nbk/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('nbk')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate nbk ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If National Bank of Kazakhstan does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via KZT from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by National Bank of Kazakhstan |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'nbk-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('nbk-exchange-rate');

getRate('USD', 'KZT', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2016 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/nbk.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/nbk/latest.json`

## 🔗 Links

- [National Bank of Kazakhstan rates page](https://allratestoday.com/central-bank-rates-api/nbk/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/nbk-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/nbk-exchange-rate)

## 📜 License

MIT
