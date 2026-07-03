# Alchohalt — marketing site

The public landing page for **Alchohalt**, a calm, private alcohol tracker.
Single self-contained `index.html` (inline CSS + a few lines of inline JS for the
theme toggle) — no build step, no framework, no external requests, no analytics.

- **Live:** https://zcg321.github.io/alchohalt-site/
- **Custom domain (when purchased):** `alchohalt.app` — see *Custom domain* below.
- **Legal policies** live in the separate [`alchohalt-legal`](https://github.com/Zcg321/alchohalt-legal)
  repo and are linked from the footer. Kept separate on purpose: those URLs are
  already referenced by the app-store submission, so this marketing site doesn't
  disturb them.

## Design / accessibility
- Mobile-first, responsive, dark + light themes (respects `prefers-color-scheme`,
  with a manual toggle persisted in `localStorage`).
- WCAG 2.1 AA: semantic landmarks, one `h1` + ordered headings, keyboard focus
  styles, skip link, `aria` labels on controls, decorative SVGs `aria-hidden`,
  `prefers-reduced-motion` honored.
- Loads fast on 3G: one file, system fonts, inline SVG icons — no image/font/JS
  downloads.

## Copy accuracy
Every user-facing claim was verified against the actual v1 shipping build
(`.env.production` default posture) and the Launch-Readiness reconciliation docs.
The page intentionally does **not** claim features that are OFF or unshipped in v1
(e.g. Night Shield, at-rest encryption / vault, biometric lock, cloud sync,
end-to-end-encrypted backup, live in-app purchase). Keep it that way — if a claim
changes, re-verify against the build before publishing.

## Custom domain (`alchohalt.app`)
Not wired yet. To activate **after** `alchohalt.app` DNS is on Cloudflare:
1. In Cloudflare DNS, add the GitHub Pages records (four `A` records to GitHub's
   Pages IPs) and set the repo's **Settings → Pages → Custom domain** to
   `alchohalt.app`.
2. **Then** add a `CNAME` file at the repo root containing exactly `alchohalt.app`.
3. Enable **Enforce HTTPS**.

> ⚠️ Do not add the `CNAME` file before the DNS records exist — GitHub Pages will
> redirect the working `zcg321.github.io/alchohalt-site/` URL to a domain that doesn't
> resolve yet and the site goes dark. DNS first, then `CNAME`. That's why the file
> isn't committed.

Full owner runbook: `C:\Alchohalt\docs\ops\alchohalt-app-domain-register-runbook.md`.
