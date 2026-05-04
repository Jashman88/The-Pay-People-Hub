# Pay People Hub

A self-contained, single-file team hub for **pay.com.au** — built as one HTML page with embedded data, no backend required.

Open `index.html` in a browser (or deploy via GitHub Pages) and you have:

- 🏠 **Home** — welcome banner, founded/team/location stats, "Our Strategy on the Page" PDF, Our Values cards, About Us, company calendar
- 🏢 **Org Chart** — a single tab with three clickable region sub-tabs (🇦🇺 AU · 🇺🇸 US · 🌏 Offshore), drag-to-reorder, search, expand/collapse, zoom, JSON import/export
- 🌟 **New Starters** — gradient welcome banner with confetti, onboarding text, key contacts, founders, induction pack
- 📁 **Helpful Documents** — Brand Guidelines PDF embedded inline, quick links, and the searchable doc library with pinned items
- 💼 **Careers** — live Employment Hero job board feed (with local iframe fallback in `Pay-Intranet_files/`)
- 🏤 **Office Experience** — High Street HQ map (Level 3 + Level 4 floor plans, click to enlarge), office events calendar, brand callout

## Quick start

```bash
# Clone the repo
git clone <your-repo-url>
cd <repo>

# Open in your default browser
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

To deploy on **GitHub Pages**: push the repo, then in Settings → Pages choose `main` branch / `/root`. The page goes live at `https://<user>.github.io/<repo>/`.

## How it works

Everything is one HTML file. Page content lives in a long base64-encoded `localStorage` snapshot embedded in `<script id="pph-baked-data">` near the top of `index.html`. On load it hydrates `localStorage`; the page then reads from there. Edits a user makes in the browser persist in their own `localStorage` until the file is opened again (re-baked snapshot wins on every page load).

### Brand palette

Colours are CSS variables on `:root`. Both core brand colours come from the pay.com.au brand book:

| Variable | Hex | PANTONE | Usage |
|----------|-----|---------|-------|
| `--bm` (brand mid) | `#3066C9` | 2386 C | **Pay Blue** — header gradient, tab nav, search bar, primary buttons, headings, links |
| `--bd` (brand dark) | `#183263` | 108-16 | Secondary navy — used as gradient anchor on the hero, panel-dark fills, deep contrast |
| `--bl` (brand light) | `#DCE7F8` | — | Pay Blue 10% tint — hover backgrounds, soft panel fills |
| `--ba` (brand accent) | `#6E94DC` | — | Pay Blue 60% mix — active borders, focus rings |

### File layout

```
.
├── index.html                          # The whole app (~6.7 MB — embedded snapshot)
├── Brand Guidelines - July 2025.pdf    # Embedded inline on the Helpful Documents page
├── Pay-Intranet_files/                 # Local iframe fallback for the Careers tab's Employment Hero embed
└── README.md
```

### Editing content

The page has an internal block editor that's been intentionally hidden in this build (the admin/edit-mode UI was stripped). To make persistent edits to baked content (org cards, headings, page blocks, etc.) you currently need to:

1. Open `index.html`, edit in the browser (changes save to your local `localStorage`)
2. Or, decompress the `pay_blocks` LZ-string blob in `index.html`, edit the JSON, and re-compress

The decompression flow is documented in the helper scripts that built this snapshot — see snapshot history below.

## Development notes

- **No build step.** It's a single HTML file. Open it.
- **No external dependencies at runtime** beyond the embedded `LZString` library that lives inside the file itself.
- The page works completely offline once loaded; the only network calls are the optional Employment Hero iframe and any user-edited document URLs.

## Snapshot history

Major milestones:

- **2026-04-28** — Original baked file (`Pay-People-Hub-Baked-2026-04-28.html`, ~6.0 MB)
- **2026-05-01** — Stripped to 5 main tabs, combined org charts, new starter welcome banner with confetti, removed admin/sign-in
- **2026-05-04** — Brand Guidelines PDF embed, Pay Blue made prominent across the chrome, US org from Rippling, "Pay-Hub" → "High Street HQ" rename, click-to-zoom lightbox

## Licence

Internal use — pay.com.au only.
