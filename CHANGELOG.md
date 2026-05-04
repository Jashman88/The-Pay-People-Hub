# Changelog

## 2026-05-04
- Embedded Brand Guidelines PDF on Helpful Documents page (relative-path reference, not base64 — keeps `index.html` from bloating)
- Removed search bar at the top of the Helpful Documents page
- Moved Brand Guidelines + Quick Links blocks below the Pinned banner inside the docs library
- Removed 10 untitled placeholder docs from the doc library
- Office Experience page: replaced both floor plan images with new versions (Lifts pin/icon added, lighter cyan markers, Bathrooms iconography); page renamed from "The Pay-Hub" → "Office Experience"
- Removed the standalone middle PDF block from the Office Experience page
- Renamed every reference of "Pay-Hub" / "The Pay-Hub" → "High Street HQ" across hero text, headings, and the New Starters Key Contacts card
- Pay Blue (#3066C9) made dominant across the chrome: header now Pay-Blue gradient, tab nav solid Pay Blue, brighter active state on tabs
- Brand secondary updated to #183263 (PANTONE 108-16) — applied to dark blue gradient stops, panel chrome, and headings

## 2026-05-01
- Built simplified single-file HTML from `Pay-People-Hub-Baked-2026-04-28.html`
- Stripped sign-in overlay, sign-in modal, admin panel, edit-mode banner, "Save snapshot" floating button
- Removed the Leaders and Perks tabs entirely
- Stripped the white-square P logo SVG from the header (replaced with a clean `pay·com·au` text wordmark) and from the home/careers hero banners
- Combined three org charts (AU/US/Offshore) into a single 🏢 Org Chart tab with clickable region sub-tabs
- Cross-AU show: clicking "📌 Show in AU" on a US/Offshore card now defaults to Ed Alder when no parent is set, and cascades the manager's full team as ghost cards on the AU chart
- Added collapse buttons to global teams that appear on the AU chart
- AU search now resolves cross-linked US/Offshore people (was AU-only before)
- Replaced home page content with a clean Pay-Blue-gradient hero banner and removed the Quick Links cards (and their heading)
- New Starters page: kept the welcome banner with confetti; deleted "Helpful Doca", "Org Charts", and "All things Pay-Hub" quick-link cards
- Updated Team stat: "183+ people" → "245+ people"
- US org chart populated from the Rippling PDF (PayRewards root with 11 people across Sales, Compliance, Operations & CS); cross-linked up to Ed Alder
- All US org locations set to "USA" (was "Remote" / "Uptown, Dallas")
- Aalia Hassan + Lori Breitzke department set to Operations, team "Legal and Compliance"
- All references of `pay.com.au` → `Pay.com.au` capitalised in visible text (email contexts kept lowercase)
- All `hub` (lowercase) → `Hub` capitalised
- Tab order set to: Home → Org Chart → New Starters → Helpful Documents → Office Experience → Careers
- Click-to-zoom lightbox added for all image blocks (Escape / click-outside / ✕ button to close)
- Pay-Hub Map images cropped (sides + extra top/bottom padding); modern card outline (rounded corners, brand-blue tinted shadow)

## 2026-04-28
- Original baked snapshot from the live People-Hub
