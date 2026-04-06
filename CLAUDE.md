# CLAUDE.md — lifestyle-os-site

## What This Is
The Lifestyle OS marketing website. Static HTML. Deployed to `lifestyle-os.fit` via Vercel, auto-deploying from `javierjaime-max/lifestyle-os-site` on GitHub.

## Deploy Pipeline — ONE PATH ONLY
```
Edit files locally → git commit → git push → Vercel auto-deploys
```
Never use `vercel deploy` CLI. Never edit files in the GitHub web editor. Never drag-and-drop into Vercel dashboard. If it isn't in git, it isn't real.

## Session Start — Do This First
```bash
git pull
```
Always. Before touching any file. The remote may have commits from a previous session that aren't in the local copy. Skipping this causes conflicts, divergence, and files that exist on the live site but not in the repo.

## Session End — Do This Before Closing
```bash
git push origin main
```
Every session should end with all commits pushed. Never leave committed-but-not-pushed work behind.

## File Structure
| File | What It Is |
|------|-----------|
| `index.html` | Landing page — main entry point |
| `assessment.html` | Assessment explainer page |
| `ebooks.html` | Books / ebook library |
| `coaching.html` | Coaching & Community — coming soon, waitlist capture |
| `favicon.svg` | Site favicon |
| `photos/` | Static image assets |

## Nav — Current Standard
All pages carry this nav (desktop and mobile):
```
Assessment | Books | Coaching | [CTA]
```
CTA on all pages = `<a href="https://app.lifestyle-os.fit" class="header-cta">Run the Diagnostic</a>`

If you add a new page, add it to the nav in every existing page and in the new page itself.

## Git Config
Commits must use `javier.jaime@me.com` as the git user email — this matches the GitHub account `javierjaime-max`. Any other email may cause Vercel deployment issues.

```bash
git config user.email "javier.jaime@me.com"
```
