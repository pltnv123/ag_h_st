# AGENTS.md — Workspace Context

## Project
Hermes Agent workspace — `/workspace`
Connected to Supabase: `ebqupwyyafvnmhakfwet.supabase.co` (project: hermes)

## Key Directories
- `/workspace/.hermes/` — Hermes config, skills, sessions, logs
- `/workspace/.hermes/skills/` — **143 skills (36 categories)**
- `/workspace/.hermes/scripts/` — **32 automation scripts**
- `/workspace/.hermes/plugins/webstudio/` — WebStudio plugin
- `/workspace/backups/qmd/` — QMD daily backups
- `/workspace/bin/` — **40+ utility binaries (hfinalize, qmd, hstatus, etc.)**

## Environment
- Terminal: Docker container (Linux 6.8.0 x86_64)
- CPU: **2 × Intel Xeon E5-2670 v2 @ 2.50GHz**
- RAM: **6GB (4.5GB avail)**
- Disk: **59GB (29GB used, 50%)**
- Main model: **gpt-5.5 (OpenAI Codex)** — cost $0.95/day cap
- **Node v20.20.2** (system), **npm 10.8**
- **Python 3.11.15**
- Ollama: localhost:11434 (falls through to OpenRouter)
- QMD: 904 indexed docs, 1599 vectors, AST chunking (6 languages)
- Supabase: PostgreSQL 17.6.1, ACTIVE_HEALTHY

## MCP Servers Active (6)
supabase, github, filesystem, playwright, sequential-thinking, memory

## Cron Jobs — 10 active
- Watchdog (every 30m), Full health (every 4h), Cost monitor (every 2h)
- Config secret audit (every 12h), QMD auto-embed (every 6h), QMD backup (daily)
- Session pruner (weekly), Skill updates (weekly), Nightly auto-heal, MCP smoke (daily)

## Communication
- Telegram: Антон (ID: 6540715349)
- Language: Russian (preferred), fallback English

## Response Style
- Technical, concise, actionable
- Proactive — don't wait for commands
- Show results (screenshots, diffs, commit hashes, curl output)
- Uses MCP tools (github, supabase, filesystem) as primary source of truth
- Every task goes through: do → verify → report

## Project Rules
- No destructive commands without verification
- Always check MEMORY.md for context before starting work
- Test after changes, verify before declaring done
- Use delegate_task for parallelizable work
- Run hfinalize before task completion
