# Velvet status page template

A ready-to-fork [Upptime](https://upptime.js.org) + [Velvet](https://github.com/phranck/velvet) status page: serverless uptime monitoring with a polished, dark front-end. No server required.

## Quick start

1. Click **Use this template** and create your repository.
2. Edit [`.upptimerc.yml`](.upptimerc.yml): set `owner` / `repo`, your `sites`, and the `velvet` block (accent colour, icons).
3. Add a `GH_PAT` secret (classic PAT with `repo` + `workflow` scopes) — Upptime needs it to commit monitoring data and deploy.
4. Push. The Upptime workflows start monitoring; the **Velvet** workflow builds and deploys the front-end to the `gh-pages` branch.
5. Enable **GitHub Pages** from the `gh-pages` branch. For a custom domain, set `status-website.cname` in `.upptimerc.yml` — Velvet writes the `CNAME` for you.
6. If a **Static Site CI** workflow shows up, disable it — Velvet replaces Upptime's stock page.

## What you get

- 90-day uptime bars, Phosphor duotone icons, an indigo-by-default dark theme — all themeable from `.upptimerc.yml`.
- Incidents and maintenance windows sourced from GitHub Issues, fetched live.

The front-end and its GitHub Action live in [phranck/velvet](https://github.com/phranck/velvet). Monitoring is powered by [Upptime](https://github.com/upptime/upptime).

## License

This repository has been published under the [MIT](https://mit-license.org) license.
