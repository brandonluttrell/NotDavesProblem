# Cloudflare static hosting

The site is a static export for Cloudflare Pages (or equivalent static hosting). SvelteKit uses `adapter-static` so there is no server runtime at the edge; client-side logic handles the live countdown. Number Facts are deferred (see ADR 0003); when reintroduced they must not rely on broken browser calls to Numbers API HTTPS.
