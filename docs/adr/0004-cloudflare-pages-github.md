# Deploy via Cloudflare Pages GitHub integration

Production deploys come from Cloudflare Pages connected to the GitHub repo, not from a GitHub Actions deploy workflow. Cloudflare runs `npm run build` and publishes the static `build/` output on pushes to `main`. Pull requests get Cloudflare preview deployments. The production hostname is **notdavesproblem.party** (Cloudflare custom domain on the Pages project). GitHub Actions was rejected to keep the pipeline simpler for a static site.
