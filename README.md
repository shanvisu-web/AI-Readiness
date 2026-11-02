# CAC 2026 — Council scoring site

Static site (no build step). Deploy folder: `site/`.

- `site/index.html` — member page (reached by the QR code). Members spend 10 points on each of three brownfield questions; responses go to the database through a validated function.
- `site/host.html` — facilitator page (PIN protected): live results, readout, final view, CSV export, clear.

Backend: Supabase project `napizlfntbxnctwmmmdg`, schema `cac2026`, exposed only through the functions
`cac26_submit`, `cac26_results(pin)`, `cac26_final(pin, body)`, `cac26_clear(pin)`. The key embedded in the pages is the public
key; it can do nothing but call those functions.

Render: static site, build command `echo static`, publish path `site`.
