# AGENTS.md — Workspace Context

## Project
Hermes Agent workspace — `/workspace`
Connected to Supabase: `ebqupwyyafvnmhakfwet.supabase.co` (project: hermes)

## Key Directories
- `/workspace/.hermes/` — Hermes config, skills, sessions, logs
- `/workspace/.hermes/skills/` — 132 skills (21 categories)
- `/workspace/.hermes/scripts/` — 15 automation scripts
- `/workspace/.hermes/plugins/webstudio/` — WebStudio plugin
- `/workspace/backups/qmd/` — QMD daily backups

## Environment
- Terminal: Docker container
- Main model: gpt-5.5 (OpenAI Codex) — cost $0.95/day cap
- Ollama: localhost:11434 (falls through to OpenRouter)
- QMD: knowledge base, Node v22
- Memory MCP: knowledge graph at mcp-memory.json

## MCP Servers Active
supabase, github, filesystem, playwright, sequential-thinking, memory

## Communication
- Telegram: Антон (ID: 6540715349)
- Language: Russian (preferred), fallback English

## Response Style
- Technical, concise, actionable
- Proactive — don't wait for commands
- Show results (screenshots, diffs, commit hashes, curl output)
- Every task goes through: do → verify → report

## Project Rules
- **Supabase DB**: tables `clients`, `projects`, `project_deliverables`, `project_milestones`. Use `mcp_supabase_execute_sql` for CRUD.
- **Intake pipeline**: client → project (status=intake) → deliverables + milestones. Status flow: intake→planning→design→development→review→delivered→archived.
- **Memory MCP KG**: populated with 10 entities (system, processes, infra, catalog, policy). Update as web studio evolves.
- No destructive commands without verification
- Always check MEMORY.md for context before starting work
- Test after changes, verify before declaring done
- Use delegate_task for parallelizable work
- Run hfinalize before task completion