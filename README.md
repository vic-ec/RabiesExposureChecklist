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

Plain HTML/CSS/vanilla JS (no framework or build step). [pdf-lib](https://pdf-lib.js.org/) v1.17.1 is bundled inline in `index.html` for PDF generation, and the UI uses the system font stack — so the app has no external dependencies at runtime.

## Getting started

No installation needed — clone or download, then open `index.html` in a modern browser.

## Offline / intranet deployment

Designed for Microsoft-centric healthcare IT environments with restricted internet access. `index.html` makes **no network requests at all** — every dependency is embedded in the file:

| Resource | How it ships |
|---|---|
| `pdf-lib` v1.17.1 | Bundled inline in the `<head>` of `index.html`. |
| Annexure 2 form template | Embedded as base64 in the page script. |
| Fonts | System UI font stack — nothing to download. |

Copy the single file anywhere — a network share, a USB stick, an intranet web server, or a local folder opened via `file://` — and every feature, PDF generation included, works with the network switched off.

To upgrade pdf-lib, replace the bundled `<script>` block in the `<head>` with a newer `pdf-lib.min.js` (strip its trailing `//# sourceMappingURL=` comment, which points at a `.map` file that is not shipped).

## Repository structure

```
.
└── index.html   # Complete application (pdf-lib bundled inline)
```

## Clinical basis

Circular H80/2024, NICD Rabies Advisory (June 2024), Cape Fur Seal outbreak advisory (active since Dec 2023). If you spot a discrepancy with current guidance, please open an issue.

## Contributing

Open an issue for clinical corrections (reference the relevant guideline) or submit a PR for code changes. Keep the app dependency-free to preserve offline portability.

## License

Creative Commons BY-NC 4.0. Free to use and share with attribution; commercial use, resale, or profit from this material is not permitted.
