# Velvet status page template

A ready-to-fork [Upptime](https://upptime.js.org) + [Velvet](https://github.com/phranck/velvet) status page: serverless uptime monitoring with a polished, dark front-end. No server required.

## Quick start

1. Click **Use this template** and create your repository.
2. Edit [`.upptimerc.yml`](.upptimerc.yml): set `owner` / `repo`, your `sites`, and the `velvet` block (colours, layout, icons). Each field is commented inline.
3. Add a `GH_PAT` secret (classic PAT with `repo` + `workflow` scopes) — Upptime needs it to commit monitoring data and deploy.
4. Set **GitHub Pages** source to **GitHub Actions** (Settings → Pages → Build and deployment → Source). For a custom domain, set `status-website.cname` in `.upptimerc.yml` — Velvet writes the `CNAME` for you.
5. Push. The Upptime workflows start monitoring; the **Velvet** workflow builds and deploys the front-end via the official Pages deployment.
6. If Upptime's **Static Site CI** / **Setup CI** workflows push a stock page, disable them — Velvet's Pages-Actions deploy replaces it.

## What you get

- Selectable uptime history (24h / 7d / 30d / 90d / 1yr) with a configurable first-visit default (`velvet.defaultRange`), Phosphor duotone icons, an indigo-by-default dark theme — all themeable from `.upptimerc.yml`.
- One grouped card or one card per service (`velvet.layout`); each card's open state and the selected range persist across reloads, plus an expand/collapse-all control beside the range selector.
- Optional per-service IPv4 / IPv6 monitoring (via Globalping) — both protocols folded into one card with status pills.
- Incidents and maintenance windows from GitHub Issues, fetched live, plus an Atom/RSS feed (`/incidents.atom`) behind a Subscribe button.
- One-click maintenance banners (the **Maintenance switch** workflow / issue templates), plus optional CI-driven deploy banners (**Deploy announce** — your app dispatches `deploy_start`/`deploy_end` with a `STATUS_DISPATCH_TOKEN`). Both open a `maintenance` issue that shows live on the page.
- A workflow that strips Upptime's hardcoded emoji from incident issue titles.

## Configuration

Every field of `.upptimerc.yml` is explained in the **[Velvet configuration reference](https://github.com/phranck/velvet/blob/main/CONFIGURATION.md)** — all `sites` check options, the `status-website` identity fields, and the full `velvet` appearance block (layout, colours, fonts, icons), plus which stock Upptime fields Velvet ignores.

The front-end and its GitHub Action live in [phranck/velvet](https://github.com/phranck/velvet). Monitoring is powered by [Upptime](https://github.com/upptime/upptime).

## License

This repository has been published under the [MIT](https://layered.mit-license.org) license.
