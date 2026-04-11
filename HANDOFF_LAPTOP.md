# Handoff from Mobile Session — 2026-04-11

## Context
This comes from a Claude Code mobile session working in `lifestyle-os-site`. The goal is to get the local Neo4j pipeline code into a git repo so it's tracked and part of the Lifestyle OS ecosystem.

## What We Know

### The "Brain"
- **Neo4j AuraDB** (cloud-hosted graph database) serves as the Lifestyle OS "Brain"
- Social media content gets ingested into it
- Pipeline code lives locally on this machine — not yet in any git repo

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
1. **Find the local pipeline code** — scripts, configs, .env files, anything that talks to Neo4j AuraDB or processes social media content
2. **Decide where it goes** — new repo? inside an existing one?
3. **Get it into git** — init, commit, push (keep secrets like AuraDB credentials out of the repo — use .env + .gitignore)
4. **Document the pipeline** in a CLAUDE.md so future sessions understand the architecture

## Questions to Ask
- Where on this machine does the pipeline code live?
- What language/stack is it? (Python scripts? Node? Cypher queries?)
- What social media platforms does it pull from?
- What's the shape of the graph? (What are the nodes and relationships?)
- Are there AuraDB connection credentials that need to be secured?
- Should this be its own repo (e.g., `lifestyle-os-brain`) or live inside an existing one?

## Git Config Reminder
Per ecosystem rules, commits must use:
```bash
git config user.email "javier.jaime@me.com"
```

---
*Generated from Claude Code mobile session. Delete this file after the laptop session picks it up.*
