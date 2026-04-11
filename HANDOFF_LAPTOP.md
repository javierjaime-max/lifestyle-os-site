# Handoff from Mobile Session — 2026-04-11

## Context
This comes from a Claude Code mobile session working in `lifestyle-os-site`. The goal is to build a content pipeline that connects the Neo4j Brain to both mobile (phone) and laptop workflows — capture ideas anywhere, publish anywhere.

## The Vision

### Two-way content pipeline
```
Phone (ideas/capture) ──> Neo4j AuraDB Brain <── Laptop (deeper work)
                                │
                                ▼
                          Instagram publish
                         (from phone or laptop)
```

### What the user wants to do:
1. **Capture from phone** — jot down social content ideas or raw content on mobile and feed them into the Brain
2. **Capture from laptop** — same thing, deeper editing and pipeline work
3. **Publish to Instagram from phone** — push content from the Brain to IG directly from mobile
4. **Either location, same Brain** — phone and laptop both read/write to the same Neo4j AuraDB

## What We Know

### The "Brain"
- **Neo4j AuraDB** (cloud-hosted graph database) serves as the Lifestyle OS "Brain"
- Social media content gets ingested into it
- Pipeline code lives locally on the laptop — not yet in any git repo
- AuraDB is cloud-hosted, so both phone and laptop can reach it with the right API layer

### Lifestyle OS Ecosystem (GitHub: javierjaime-max)
| Repo | Role |
|------|------|
| `lifestyle-os-site` | Static marketing site (lifestyle-os.fit, Vercel) |
| `lifestyle-os-app` | Diagnostic app (Supabase + Lovable + Claude API) |
| `lifestyleosapp` | Diagnostic app (TypeScript) |
| `ccft-study-app` | CCFT study app |
| `crossfit-otl` | CrossFit OTL gym site |
| `lifestyle-os` | Archived |
| `lifestyles` | Archived |

None of these repos currently contain any Neo4j or pipeline code.

## What Needs to Happen

### Phase 1 — Get existing code into git
1. **Find the local pipeline code** — scripts, configs, .env files, anything that talks to Neo4j AuraDB or processes social media content
2. **Decide where it goes** — new repo (e.g., `lifestyle-os-brain`)? inside an existing one?
3. **Get it into git** — init, commit, push (keep secrets like AuraDB credentials out of the repo — use .env + .gitignore)
4. **Document the pipeline** in a CLAUDE.md so future sessions understand the architecture

### Phase 2 — Mobile capture
- Need an API or lightweight interface the phone can hit to push ideas/content into AuraDB
- Options: simple API endpoint (Vercel serverless? Supabase edge function?), a mobile-friendly web form, or Claude Code mobile feeding a script
- Must be fast and frictionless — phone capture needs to feel like jotting a note

### Phase 3 — Instagram publishing
- Instagram Graph API for publishing (requires Facebook Business account + IG Professional account)
- Content goes: Brain -> format/review -> publish to IG
- Needs to work from phone — either a web UI trigger or an API call Claude Code mobile can make

## Questions to Ask
- Where on this machine does the pipeline code live?
- What language/stack is it? (Python scripts? Node? Cypher queries?)
- What's the shape of the graph? (What are the nodes and relationships in the Brain?)
- Are there AuraDB connection credentials that need to be secured?
- Is there already a Facebook/IG Business account set up for API access?
- What does "content" look like? (text posts, carousels, reels, stories?)
- Should this be its own repo (e.g., `lifestyle-os-brain`) or live inside an existing one?

## Git Config Reminder
Per ecosystem rules, commits must use:
```bash
git config user.email "javier.jaime@me.com"
```

---
*Generated from Claude Code mobile session. Delete this file after the laptop session picks it up.*
