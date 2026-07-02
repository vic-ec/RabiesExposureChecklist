# Animal Bite — Rabies Exposure Checklist

A single-file, offline-capable clinical decision support tool for assessing rabies exposure risk and guiding post-exposure prophylaxis (PEP) decisions, aligned to South African guidelines (Circular H80/2024 and NICD Advisory, June 2024).

> **⚠️ Clinical tool disclaimer**
> This tool supports, but does not replace, clinical judgement. It must be used by trained healthcare personnel in line with current NICD/national guidelines. Always escalate uncertain or high-risk cases to an Infectious Diseases specialist.

## Features

- Step-based exposure assessment (animal, wound category I/II/III, risk-modifying features)
- Category-specific PEP guidance (vaccine ± RIG logic)
- Vaccine schedule calculator (Day 0/3/7/14–28)
- RIG dose calculator (weight-based, HRIG/ERIG)
- Cape Fur Seal outbreak alert with retrospective PEP guidance
- Escalation/contacts panel and pharmacy stock list
- PDF generation — checklist summary + Annexure 2 form
- Runs entirely client-side — no backend, no data transmitted or stored

## Tech stack

Plain HTML/CSS/vanilla JS (no framework or build step), [pdf-lib](https://pdf-lib.js.org/) via CDN for PDF generation, IBM Plex fonts (falls back to system fonts).

## Getting started

No installation needed — clone or download, then open `Animal_Bites___Rabies_Checklist.html` in a modern browser.

## Offline / intranet deployment

Designed for Microsoft-centric healthcare IT environments with restricted internet access. Two resources load from external CDNs by default:

| Resource | Default source | For offline use |
|---|---|---|
| `pdf-lib` | `cdnjs.cloudflare.com` | Host [pdf-lib.min.js](https://unpkg.com/pdf-lib/dist/pdf-lib.min.js) locally and update the `<script src="...">`. |
| IBM Plex fonts | `fonts.googleapis.com` | Host locally, replace `@import` with local `@font-face` rules. |

Fonts degrade gracefully if unavailable; PDF generation requires `pdf-lib` to be reachable (locally or via CDN).

## Repository structure

```
.
└── Animal_Bites___Rabies_Checklist.html   # Complete application
```

## Clinical basis

Circular H80/2024, NICD Rabies Advisory (June 2024), Cape Fur Seal outbreak advisory (active since Dec 2023). If you spot a discrepancy with current guidance, please open an issue.

## Contributing

Open an issue for clinical corrections (reference the relevant guideline) or submit a PR for code changes. Keep the app dependency-free to preserve offline portability.

## License

MIT — see [LICENSE](LICENSE).
