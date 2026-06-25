# ML Auto Parts Liquidation — Website Repo

## What this is
Single-page static catalog site (index.html) for liquidating Mark Levine's auto parts inventory. Owner/operator: JC Estrada (jcbestradaconi@gmail.com). Hosted on GitHub Pages. Built June 2026.

## Hard rules
1. **Verified SKUs only.** The catalog lists ONLY items whose model numbers were cross-reference verified against published part numbers. Do not add inventory items without a confirmed cross-reference. Currently excluded as unverified: GTX6 coolant sensors, SW13372 MAP sensors, SW-015113 turn signal switches, S-S49538 CPS sensors, S-019149C VSS, no-model items, door handles, W9009-AMBK headlights, ATO-35 fuses (qty pending physical check).
2. **Pricing is locked to the master sheet** ("ML Auto Parts - Pricing & Inventory V3.xlsx" in the parent project folder — this is the current single source of truth; always check for a newer Vn before relying on it): retail ≈ 15% under market comps; 50+ units = 40% off retail; full-SKU lot = 50% off retail. If pricing changes, change the spreadsheet first, then mirror here. The "Full Inventory" tab holds the full-scope audit view: Section 1 = identified & sellable (on the site), Section 2 = TBD/unconfirmed (model # pending — surfaced on the site only as the aggregate "verification pending" note), Section 3 = zero-count reference items.
3. **No stock photos from retailers** (copyright + buyer trust). Product cards show SVG category icons until real photos exist. To add real photos: drop JPGs into `images/` named exactly: f536e.jpg, sw-ds96-5.jpg, sw-ds97-5.jpg, sw-ds97.jpg, sw-hs99.jpg, s-f172.jpg, sw-ds96.jpg, s-a905161b.jpg, pu-lx309.jpg, tps198.jpg, b9004.jpg. The cards pick them up automatically (img with onerror fallback to icon).
4. **Single file.** Keep all CSS/JS inline in index.html. No build step, no frameworks.
4b. **catalog.pdf must stay in the repo root.** Outreach emails link to `<site-url>/catalog.pdf` (the one-sheeter). If the one-sheeter is regenerated in the parent folder, copy the new version here as catalog.pdf and deploy.
5. Contact form posts via Formspree (form ID mbdekvow) to jcbestradaconi@gmail.com. The FIRST form submission triggers a confirmation email to JC — he must click it once to activate. Spam filtering / captcha are managed in the Formspree dashboard, not in the form markup.

## Deploy
GitHub Pages serves from main branch root. To ship any change:
```
git add -A && git commit -m "<what changed>" && git push
```
Pages redeploys automatically in ~1 minute. There is no other deploy step.

## Inventory quick reference (qty / retail / 50+ / lot)
F-536 E 24V flasher: 1,576 / $9.99 / $5.99 / $5.00 · SW-DS96-5: 1,200 / $8.99 / $5.39 / $4.50 · SW-DS97-5: 600 / $9.99 / $5.99 / $5.00 · SW-DS97: 200 / same · SW-HS99: 200 / $12.99 / $7.79 / $6.50 · S-F172: 167 / $12.99 / $7.79 / $6.50 · SW-DS96: 100 / $8.99 / $5.39 / $4.50 · S-A905161B: 89 / $16.99 / $10.19 / $8.50 · pu-LX309: 54 / $24.99 / $14.99 / $12.50 · TPS198: 51 / $19.99 / $11.99 / $10.00 · B9004: 37 / $6.99 / $4.19 / $3.50

When quantities sell down, update both the card badge and the hero stats (4,200+ figure).
