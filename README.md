# Velvet status page template

A ready-to-fork [Upptime](https://upptime.js.org) + [Velvet](https://github.com/phranck/velvet) status page: serverless uptime monitoring with a polished, dark front-end. No server, no database — just a GitHub repository.

<p align="center">
  <img src="https://raw.githubusercontent.com/phranck/velvet/main/docs/screenshot.png" alt="Velvet status page" width="820">
</p>

## Setup

Four steps, all in the GitHub web UI — no local tools, no build to run.

1. **Create your repository.** Click **Use this template → Create a new repository** at the top of this page.

2. **Add the `GH_PAT` secret.** Create a [classic Personal Access Token](https://github.com/settings/tokens/new) with the **`repo`** and **`workflow`** scopes. Then, in your new repository, open **Settings → Secrets and variables → Actions → New repository secret**, name it exactly `GH_PAT`, and paste the token. _(Upptime uses it to commit monitoring data and to deploy the page.)_

3. **Turn on Pages.** Open **Settings → Pages → Build and deployment** and set **Source** to **GitHub Actions**.

4. **Edit [`.upptimerc.yml`](.upptimerc.yml) and commit.** Set `owner` / `repo` to your new repository, list the `sites` you want to monitor, and adjust the `velvet` block (name, colours, layout, icons). Every field is commented inline.

That last commit starts everything: Upptime begins monitoring your `sites`, and Velvet builds and deploys the page. Within a few minutes it is live at `https://<owner>.github.io/<repo>/`.

> **Custom domain?** Set `status-website.cname` in `.upptimerc.yml` — Velvet writes the `CNAME` file for you on every deploy.
>
> **Seeing a plain Upptime page instead of Velvet?** Open the **Actions** tab and disable a **Static Site CI** workflow if one appears — Velvet deploys through Pages Actions and doesn't need it.

## What you get

- Selectable uptime history (24h / 7d / 30d / 90d / 1yr) with a configurable first-visit default (`velvet.defaultRange`), Phosphor duotone icons, an indigo-by-default dark theme — all themeable from `.upptimerc.yml`.
- One grouped card or one card per service (`velvet.layout`); each card's open state and the selected range persist across reloads, plus an expand/collapse-all control beside the range selector.
- Optional per-service IPv4 / IPv6 monitoring (via Globalping) — both protocols folded into one card with status pills.
- Incidents and maintenance windows from GitHub Issues, fetched live, plus an Atom/RSS feed (`/incidents.atom`) behind a Subscribe button.
- One-click maintenance banners (the **Maintenance switch** workflow / issue templates), plus optional CI-driven deploy banners (**Deploy announce** — your app dispatches `deploy_start` / `deploy_end` with a `STATUS_DISPATCH_TOKEN`). Both open a `maintenance` issue that shows live on the page.
- A workflow that strips Upptime's hardcoded emoji from incident issue titles.

## Configuration

Every field of `.upptimerc.yml` is explained in the **[Velvet configuration reference](https://github.com/phranck/velvet/blob/main/CONFIGURATION.md)** — all `sites` check options, the `status-website` identity fields, and the full `velvet` appearance block (layout, colours, fonts, icons), plus which stock Upptime fields Velvet ignores.

The front-end and its GitHub Action live in [phranck/velvet](https://github.com/phranck/velvet). Monitoring is powered by [Upptime](https://github.com/upptime/upptime).

## License

This repository has been published under the [MIT](https://layered.mit-license.org) license.
