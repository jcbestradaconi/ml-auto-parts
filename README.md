# ML Auto Parts Liquidation — Site Setup

## One-time GitHub setup (do this once, ~5 minutes)

Open Terminal (or let Claude Code run these — it can execute them for you once you approve):

```bash
# 1. If you don't have the GitHub CLI: brew install gh
gh auth login                      # log into YOUR GitHub account (browser flow)

# 2. From this website/ folder:
cd "path/to/Auto Parts Sales Project/website"
git init -b main
git add -A
git commit -m "ML Auto Parts site V2"
gh repo create ml-auto-parts --public --source=. --push

# 3. Turn on GitHub Pages:
gh api repos/{owner}/ml-auto-parts/pages -X POST -f "source[branch]=main" -f "source[path]=/" || true
```
If step 3 errors, do it in the browser: repo → Settings → Pages → Source: "Deploy from a branch" → main / root → Save.

Your site will be live at: `https://<your-username>.github.io/ml-auto-parts/`

## After setup
- Paste the live URL into the [WEBSITE URL] spots in "Outreach Emails V1.md".
- Submit the contact form once yourself — FormSubmit emails jcbestradaconi@gmail.com a one-click activation link on first use. Click it or leads won't arrive.
- Photos: shoot each SKU at storage, drop into `images/` with the exact filenames listed in CLAUDE.md. Commit + push and they appear automatically.

## Day-to-day with Claude Code
Open this folder in Claude Code. It reads CLAUDE.md automatically, so it knows the inventory, pricing rules, and deploy process. Just tell it things like "the LX-309s sold out, remove the card and update the stats, then deploy" and it will edit, commit, and push.
