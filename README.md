# Not Dave's Problem

A single-page retirement countdown for **David Mangicaro**, hosted at [notdavesproblem.party](https://notdavesproblem.party).

The hero shows remaining time until the **Retirement Instant** (start of January 1, 2027, America/New_York), rotating through countdown views with fade transitions. After that instant, the site switches to a celebratory retired state. **Number Facts** are deferred until an HTTPS-capable trivia source is chosen ([ADR 0003](./docs/adr/0003-defer-number-facts.md)).

## Stack

- [SvelteKit](https://svelte.dev/docs/kit) with `@sveltejs/adapter-static` (Cloudflare Pages / static hosting)
- [Tailwind CSS](https://tailwindcss.com/) + [DaisyUI](https://daisyui.com/) **sunset** theme

## Domain language

Shared vocabulary lives in [`CONTEXT.md`](./CONTEXT.md). Architecture decisions live in [`docs/adr/`](./docs/adr/).

## Develop

```sh
npm install
npm run dev
```

## Build / preview

```sh
npm run build
npm run preview
```

## Deploy (Cloudflare Pages)

Deploys use **Cloudflare Pages ↔ GitHub** (not GitHub Actions). See [ADR 0004](./docs/adr/0004-cloudflare-pages-github.md).

### Create / connect the project

1. In the [Cloudflare dashboard](https://dash.cloudflare.com/) go to **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
2. Authorize GitHub and select **`brandonluttrell/NotDavesProblem`**.
3. Use these build settings:

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Framework preset | None (or SvelteKit if offered — then override output dir) |
| Build command | `npm run build` |
| Build output directory | `build` |
| Root directory | `/` (repo root) |

4. Under **Environment variables** (Production and Preview), set:

| Variable | Value |
| --- | --- |
| `NODE_VERSION` | `22` |

5. Save and deploy. Confirm the first production build succeeds.

### Branches

- **Production:** pushes / merges to `main` update the live site.
- **Previews:** pull requests get Cloudflare preview URLs (enable preview deployments / preview branches in **Settings → Builds → Branch control** if not on by default).

### Custom domain: notdavesproblem.party

1. In the Pages project go to **Custom domains** → **Set up a domain**.
2. Add **`notdavesproblem.party`** (and `www` if you want it) and follow Cloudflare’s activation steps.
3. Keep DNS for that hostname on Cloudflare (proxied) so the Pages custom domain can complete. If the zone is already on Cloudflare, accept the record Cloudflare proposes; if DNS is elsewhere, point the domain at Cloudflare first or add the CNAME Cloudflare shows.

After activation, https://notdavesproblem.party should serve the latest `main` deploy.

## Out of scope (v1)

About sections, guestbook, gallery, and other tribute extras — see [ADR 0002](./docs/adr/0002-v1-single-page-hero.md).
