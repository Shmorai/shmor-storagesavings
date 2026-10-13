# StorageSavings (storagesavings.shmor.ai)

A Shmor marketplace (shared rules in `../../CLAUDE.md`): its own brand, design and SEO. Self-storage units for home and business. Compare storage sizes, prices and providers near you. Repo: `Shmorai/shmor-storagesavings` (private until launch). Status: **building**.

## Where things are
| What | Where |
|---|---|
| Card on shmor.ai, search keywords, **referral links**, offers, SEO defaults | `shmor-site.json` |
| Pages (1 JSON file = 1 Google landing page) | `content/` (`home.json` = homepage) |
| Design: header, logo, footer | `templates/layout.html` |
| Design: styles | `assets/site.css` (kit defaults; add this site's theme block at the bottom) |
| Generated output (don't edit by hand) | `index.html`, `*/index.html`, `sitemap.xml`, `robots.txt`, `404.html`, `search/` |

## Pages (16)
Home · storage-units (hub) · storage-unit-sizes · business-storage · storage-for-moving · climate-controlled-storage · container-storage · vehicle-storage · student-storage · peer-to-peer-storage (private space from homeowners) · save-on-storage · choosing-a-storage-unit · blog + 3 posts (how-to-pack-a-storage-unit, what-not-to-put-in-storage, container-vs-storage-unit).
"Public and private" = personal/household storage, business storage, and private peer-to-peer space. Top menu (navOrder): Storage units, Size guide, Business storage, Moving, Containers, Save money, Blog.

## Design
"Roll-up door": warm off-white pages #FBFAF7, charcoal #16181D / #24272F hero and bands with a 6px safety-yellow #FACC15 bottom stripe, yellow buttons with charcoal text (hover #EAB308, soft #FEF7D6), amber #8A5A00 links on light backgrounds, Archivo 700/800 headings + Inter body. Logo = charcoal warehouse-with-roll-up-door on a yellow rounded square + "Storage**Savings**" (Savings with a yellow highlighter underline; plain yellow on dark). Favicon = the same mark. Every hero is a photo with a charcoal overlay. Home: guide cards moved up under the benefits row with CSS `order`. Tables go in `<div class="table-wrap">` (scrolls sideways on mobile). Mobile checked at 375px (no horizontal scroll).
**Photos:** free-licence Unsplash images (not Unsplash+), credited, in each page's "image".

## Content rules for this site
No invented prices, "from £x" figures, discounts or provider ratings. Size table is a rough industry guide. Facts used: UK HMRC 6-year company record rule, IRS "keep as long as needed / often 3 years", UK SORN, UK storage VAT at standard rate. Trade bodies cited: SSA (US), SSA UK, FEDESSA.

## Search routing on shmor.ai
Keywords in `shmor-site.json`. Bare "storage" is a keyword, so "cloud storage" also routes here until a tech site claims "cloud storage" with a longer keyword.

## Commands (run here)
```bash
node tools/build.js           # rebuild after ANY change to content/, templates/ or shmor-site.json
node tools/serve.js <port>    # local preview (see the "storagesavings" preview config)
```
After changing `shmor-site.json`, also run `node tools/sync-network.js` in `../../shmor-ai`.

## Referral links
None yet. Candidates: self-storage operators and comparison/booking platforms with affiliate programmes (Awin/CJ/Impact). Paste exact links from the user only.
Add to `shmor-site.json` → `"links"`, list slugs in a page's `"partners"` (or add `"offers"`), rebuild, sync the master, then commit both repos.
