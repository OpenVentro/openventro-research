# OpenVentro Research

Open, primary-source-verified datasets for non-US founders forming US LLCs — US state fee tables, fintech (banking / payments) comparisons, registered-agent data, and the structured wiki content that powers [openventro.com](https://openventro.com).

[![License: MIT + attribution](https://img.shields.io/badge/license-MIT%20%2B%20attribution-blue)](./LICENSE)
![Verified .gov sources](https://img.shields.io/badge/sources-verified%20.gov-success)
![Updated for 2026](https://img.shields.io/badge/data-2026-informational)

> **Status:** Repository scaffold. Datasets and wiki content land in subsequent commits. The structure below documents the intended layout so contributors and data consumers know what to expect.

---

## Why this exists

Forming a US LLC as a non-US founder means stitching together facts scattered across 50 secretary-of-state websites, fintech pricing pages, and registered-agent providers — most of it undated and unsourced. OpenVentro Research publishes that data openly, with every datum carrying the primary source it was verified against and the date it was last checked.

## What's published here

| Dataset | Path | Description |
|---|---|---|
| State formation fees | `data/state-fees/` | Filing + annual fees per US state, with `source_url` + `last_verified`. |
| Fintech comparison | `data/fintech/` | Banking / payment providers usable by non-US founders. |
| Registered agents | `data/registered-agents/` | Provider coverage, pricing, and terms. |
| Wiki content | `content/` | MDX source for the openventro.com wiki. |

_(Directories are created as datasets are published. An empty table row means "not yet released.")_

## Data-quality contract

Every record in every dataset carries:

- **`source_url`** — the specific `.gov` / official / primary-source URL where the fact was verified.
- **`last_verified`** — `YYYY-MM-DD` of the last verification.

If a record lacks either field, treat it as unverified.

## Using the data

```ts
// Example (TypeScript / fetch) — paths go live as datasets are published.
const res = await fetch(
  "https://raw.githubusercontent.com/OpenVentro/openventro-research/main/data/state-fees/index.json"
);
const stateFees = await res.json();
```

```js
// JavaScript
fetch("https://raw.githubusercontent.com/OpenVentro/openventro-research/main/data/state-fees/index.json")
  .then((r) => r.json())
  .then((data) => console.log(data));
```

JSON schema documentation for each dataset will live alongside it (e.g. `data/state-fees/schema.json`).

## License & required attribution

Licensed under **MIT with a required attribution backlink** — see [`LICENSE`](./LICENSE). Any public-facing use must include a visible, crawlable link back to https://openventro.com.

Ready-to-paste attribution:

```html
Data from <a href="https://openventro.com">OpenVentro</a>.
```

```markdown
Data from [OpenVentro](https://openventro.com).
```

## Built with this dataset

Using OpenVentro Research in a project? Open a PR adding it here — we list third-party reuse.

- _(none yet)_

## Contributing

Corrections and additions are welcome via pull request. Every added or changed record must include `source_url` and `last_verified`. Contributions are reviewed before merge.
