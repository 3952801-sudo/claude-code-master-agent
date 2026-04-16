# Master Agent — Multi-Role Development Orchestrator for Claude Code

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://docs.anthropic.com/en/docs/claude-code)
[![Roles](https://img.shields.io/badge/Roles-9%20permanent%20%2B%20∞%20dynamic-green)]()
[![Rules](https://img.shields.io/badge/Rules-100%20mandatory-red)]()

> One AI. Nine specialists. Zero excuses.

**Master Agent** is a Claude Code skill that transforms a single AI conversation into a coordinated team of 9 permanent roles + unlimited dynamic experts. Instead of giving Claude vague instructions and hoping for the best, you get a structured development pipeline with mandatory audits, quality gates, and a sarcastic team lead who's seen it all.

---

## Demo

```
You: /master-agent
Agent: Boss, what are we doing?
       1. New task — throw it, I'll break it down
       2. Continue current — I'll pick up where we left off
       3. Show plan — status and backlog

You: Add RBAC — admin, manager, viewer roles

Agent: ╔══════════════════════════════════════════╗
       ║  TASK: RBAC system (3 roles)             ║
       ╠══════════════════════════════════════════╣
       ║  Type: new feature                       ║
       ║  Competencies: auth, DB, API, UI         ║
       ║  Brigade:                                ║
       ║    Analyst → Architect → DBA → Backend   ║
       ║    → Frontend → QA → TechWriter          ║
       ║    → 🔒 Auditor                          ║
       ║  Gates: after Architect, after Auditor    ║
       ║  Risks: existing session invalidation     ║
       ╚══════════════════════════════════════════╝
       Proceed?

You: just do it

       ⚡ Analyst → sonnet — requirements breakdown
       ══════════════════════════════════════
       📋 ANALYST — RBAC Requirements
       ══════════════════════════════════════
       USER STORIES:
       - US-1: As admin, I want to manage all users...
       - US-2: As manager, I want to see only my clients...
       ✅ RESULT: 3 roles, 12 permissions, ownership matrix
       ══════════════════════════════════════

       ⚡ Architect → opus — system design
       ══════════════════════════════════════
       🏗️ ARCHITECT — RBAC Architecture
       ...

       ⚡ Backend → sonnet — API implementation
       ⚡ Frontend → sonnet — UI role guards
       ⚡ QA → sonnet — 47 tests (red → green)

       ⚡ Auditor → opus — independent security review
       ══════════════════════════════════════
       🔒 AUDIT REPORT
       Files reviewed: 23 | Issues: 2 medium, 1 low
       VERDICT: ✅ PASS WITH NOTES
       ══════════════════════════════════════

       📊 DELIVERY REPORT
       ══════════════════════════════════════
       Task: RBAC (admin/manager/viewer)
       Brigade: 7 roles, 0 dynamic experts
       Tests: 47 passed, 0 failed
       Audit: PASS WITH NOTES
       Token routing: 62% sonnet, 38% opus
       ══════════════════════════════════════
```

---

## What It Does

When you say `/master-agent`, Claude becomes a **Senior Architect with 20 years of experience** who:

1. **Analyzes** your task and assembles the right team
2. **Orchestrates** 9 specialized roles in the right order
3. **Routes** subtasks to optimal models (haiku/sonnet/opus) to save tokens
4. **Enforces** a 10-step deployment pipeline with mandatory security audit
5. **Delivers** a structured report with audit results

No role is skipped. No shortcut is taken. The Auditor always has the final word.

## The Brigade

| # | Role | What They Do |
|---|------|-------------|
| 1 | **Architect** | System design, stack, API contracts, architectural decisions |
| 2 | **Analyst** | Requirements, user stories, business rules, prioritization |
| 3 | **Backend** | Server logic, API, integrations, database queries |
| 4 | **Frontend** | UI components, state, UX, accessibility, responsiveness |
| 5 | **QA** | Test strategy, unit/integration/e2e, regression, automation |
| 6 | **DevOps** | Docker, CI/CD, deploy, monitoring, infrastructure |
| 7 | **DBA** | Schema design, migrations, indexes, query optimization |
| 8 | **TechWriter** | README, API docs, changelog, user guides |
| 9 | **Auditor** | Independent security & quality audit. **Never skipped.** |

Plus **unlimited dynamic experts** generated on-the-fly: CFO, Legal, ML Engineer, UX Designer, Industry Specialist — whatever the task demands.

## Key Features

### Smart Model Router
Not everything needs Opus. Master Agent automatically routes each subtask to the right model:

| Level | Model | When |
|-------|-------|------|
| L1 | `haiku` | File search, grep, reading, formatting |
| L2 | `sonnet` | Single-file fixes, one component, simple endpoints |
| L3 | `opus` | Architecture, multi-file changes, business logic, audit |

**Result:** 40-60% token savings on typical tasks without quality loss.

### 10-Step Deploy Pipeline
Every change goes through ALL 10 steps. No exceptions.

```
 1. Tests (red)    — prove the bug exists
 2. Code           — minimal implementation
 3. Tests (green)  — all tests pass (new + regression)
 4. Build          — no errors
 5. Lint + Types   — zero errors
 6. Security       — no critical/high vulnerabilities
 7. Env            — no missing variables
 8. Migrations     — nothing pending
 9. 9-Agent Audit  — all roles review in parallel
10. Deploy         — with explicit approval
```

### 100 Mandatory Rules
Each of the 10 roles follows 10 strict rules. Not guidelines — **rules**:

| Role | Example Rule |
|------|-------------|
| **Master Agent** | "Understand the task first, assign second. 10 min of analysis saves 10 hours of rework" |
| **Architect** | "Design for deletion. A good module can be removed with one `rm -rf`" |
| **Analyst** | "Don't confuse solution and problem. Client says 'button', the problem is 'can't find the action'" |
| **Backend** | "Validate at entry, once. Schema validation at API level, trust downstream" |
| **Frontend** | "Loading, Error, Empty — three mandatory states. No exceptions" |
| **QA** | "Red -> green. First a test that FAILS, then the fix" |
| **DevOps** | "Test backups by restoring. Untested backup = no backup" |
| **DBA** | "N+1 is a mortal sin. JOIN or include. Always" |
| **TechWriter** | "Outdated docs are worse than no docs. Update or delete" |
| **Auditor** | "Input = enemy. Sanitize, validate, escape" |

Full list in [`brigade-rules.md`](skills/master-agent/references/brigade-rules.md).

### 10 Standard Workflows

| # | Workflow | Trigger |
|---|----------|---------|
| WF-1 | New project from scratch | "create project", "new app" |
| WF-2 | New feature | "add feature", "build this" |
| WF-3 | Bug fix | "broken", "not working" |
| WF-4 | Refactoring | "refactor", "tech debt" |
| WF-5 | Code review | "review", "check this" |
| WF-6 | Documentation / proposal | "docs", "write specs" |
| WF-7 | Analytics / research | "analyze", "compare options" |
| WF-8 | External API integration | "integrate", "connect API" |
| WF-9 | Migration / upgrade | "upgrade", "migrate to" |
| WF-10 | Emergency hotfix | "prod is down", "urgent" |

### Dynamic Expert Generation
Need a CFO for financial modeling? A legal expert for GDPR? An energy engineer for solar calculations? Master Agent generates them on-the-fly with proper briefing, structured output, and automatic context collapse after they finish. Up to 3 dynamic experts simultaneously.

### Hybrid Decision Mode
- **Autonomous:** tech choices, naming, file structure, tests, minor bugs
- **Gate (asks you):** architecture, business logic, approach selection, deleting code

---

## Installation

### Option A: As a Plugin (recommended)

```bash
git clone https://github.com/3952801-sudo/claude-code-master-agent.git
```

Add to your Claude Code `settings.json` (see [plugin docs](https://docs.anthropic.com/en/docs/claude-code/skills)):

```json
{
  "plugins": [
    {
      "path": "/path/to/claude-code-master-agent"
    }
  ]
}
```

### Option B: Copy into Project

Copy the skill directly into your project's `.claude/skills/` directory:

```bash
cp -r skills/master-agent /your-project/.claude/skills/
```

Then use `/master-agent` in any Claude Code session within that project.

---

## Usage

### Start a session
```
/master-agent
```

Master Agent will ask what you're doing:
1. **New task** — describe it, get a plan
2. **Continue** — picks up from `ACTIVE_TASK.md`
3. **Show plan** — see status and backlog

### Emergency commands

| Command | What happens |
|---------|-------------|
| `stop` | Immediate halt, status report |
| `just do it` | Skip current gate, work autonomously |
| `show plan` | Current progress |
| `add expert [who]` | Generate and connect specialist |
| `audit now` | Run intermediate audit |
| `everything through opus` | Disable model routing (expensive but reliable) |
| `save tokens` | Aggressive haiku/sonnet routing |

---

## Session Persistence

Master Agent maintains two files for cross-session continuity:

- **`ACTIVE_TASK.md`** — current task progress, context, next steps
- **`BACKLOG.md`** — task queue and completed items

These are updated automatically during work. When you start a new session, Master Agent reads them to resume exactly where you left off.

---

## Project Structure

```
claude-code-master-agent/
├── README.md                          # You are here
├── LICENSE                            # MIT License
└── skills/
    └── master-agent/
        ├── SKILL.md                   # Main orchestrator prompt
        └── references/
            ├── core-roles.md          # 9 permanent role definitions
            ├── role-generator.md      # Dynamic expert generation system
            ├── workflows.md           # 10 standard workflows (WF-1..WF-10)
            └── brigade-rules.md       # 100 mandatory rules (10 per role)
```

## Customization

### Adding project-specific rules

Create a `references/project-rules.md` in the skill directory with your project's conventions. Master Agent will incorporate them automatically.

### Adjusting the character

The Master Agent's sarcastic personality is defined in `SKILL.md` under "Master Agent Character". Tone it down or amp it up — it's just a prompt section. Want a polite butler instead of a cynical architect? Go for it.

### Disabling model routing

If you prefer all tasks to run on one model, tell Master Agent:
```
everything through opus
```
Or modify the Smart Router section in `SKILL.md`.

---

## Battle-Tested

This skill was forged over 40+ production sessions building real SaaS products (CRM, SCADA, commercial proposal generators):

- **9-agent parallel audits** caught bugs that unit tests missed — dead RBAC code that passed 26 unit tests but had never been migrated to the actual database
- **"Red test first" rule** prevented dozens of false-positive "fixes" where the code changed but nothing actually got better
- **Smart routing** saved ~50% tokens on average without quality degradation — haiku handles grep just fine
- **Dynamic experts** (energy engineers, financial analysts, tariff specialists) provided domain accuracy that generic prompts couldn't match
- **Session persistence** via ACTIVE_TASK.md allowed picking up complex multi-day tasks without losing context

---

## Philosophy

> "Architect proposes microservices for a todo list. I propose Architect takes a vacation."

Master Agent believes in:
- **Pragmatism over methodology.** Common sense beats any framework
- **Mandatory audits.** The Auditor is sacred — you can cut any role, never the Auditor
- **Red-green testing.** No fix counts without a failing test first
- **Context economy.** Don't load what you don't need. Tokens aren't free
- **Visible progress.** The Client always knows what's done and what's next

---

## Contributing

Found a bug? Want to add a workflow? PRs welcome.

Please follow the existing style:
- English for code and file content
- Keep role definitions focused and actionable
- Test your changes on a real project before submitting

## License

MIT — see [LICENSE](LICENSE)

---

*Built by developers who got tired of babysitting AI through every commit.*
