# connorwithhonorai.com

## ⚠️ THIS REPO IS A MIRROR. IT IS NOT THE PUBLISH SOURCE.

**Canonical source: `D:\My Drive\connorwithhonorai\`** (Kain; Drive-synced, reachable from any box)

connorwithhonorai.com is served by **Cloudflare Pages via direct upload**, not by a git integration.
Pushing to this repo publishes **nothing**. This repo exists as an offsite backup and a diffable history.

### Deploy (from the canonical source, not from here)

```powershell
cd "D:\My Drive\connorwithhonorai"
$env:CLOUDFLARE_ACCOUNT_ID="8d19fd09c66903840c347da43306673e"
npx wrangler pages deploy . --project-name=connorwithhonorai --branch=main --commit-dirty=true
```

CF Pages project `connorwithhonorai`, personal account `8d19fd09c66903840c347da43306673e`.
Custom domain CNAMEs to `connorwithhonorai.pages.dev`.
(`connorwithhonorai.netlify.app` is a dormant leftover. Ignore it.)

### Re-sync this mirror after publishing

```powershell
robocopy "D:\My Drive\connorwithhonorai" "$HOME\dev\connorwithhonorai" /MIR /XD ".git" ".wrangler" /XF ".gitignore"
cd "$HOME\dev\connorwithhonorai"; git add -A; git commit -m "Mirror live site"; git push
```

### History of this warning

On 2026-07-18 this repo was **18 posts behind live** (3 vs 21), last touched 2026-06-26, with commits
named "Netlify sync backup". A session assumed it was canonical, wrote a post here, and pushed. Nothing
published. Had anyone wired this repo to a deploy in that state, it would have **deleted 18 live articles**.

Before trusting any local folder for any of Connor's domains: fetch the live `/blog/` index, count the
post links, compare to the local directory. If they disagree, the local dir is not the publish surface.

### Publishing checklist (4 files, all required, in the canonical source)

1. `blog/<slug>/index.html` — schema stack is `Article` + `Person` + `BreadcrumbList` + `VideoObject` + `FAQPage`
2. `blog/index.html` — add the card HTML **and** the entry in the `Blog` → `blogPost[]` array
3. `sitemap.xml` — add the `<url>` block
4. `llms.txt` — add the bullet above `## Related sites`

Per-post OG images live at `/blog/<slug>/og.png` (1200x630).
