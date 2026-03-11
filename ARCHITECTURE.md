# Architecture

How Alfred's systems connect.

```
┌─────────────────────────────────────────────────────┐
│                    Gateway (OpenClaw)                │
│         Always-on daemon, message routing,          │
│              cron scheduling, sessions              │
└──────────────┬──────────────────┬───────────────────┘
               │                  │
    ┌──────────▼──────┐  ┌───────▼────────┐
    │   Messaging     │  │  Cron Engine   │
    │  Telegram/X/    │  │  23+ jobs      │
    │  WhatsApp/Web   │  │  heartbeats    │
    └──────────┬──────┘  └───────┬────────┘
               │                  │
    ┌──────────▼──────────────────▼───────────────────┐
    │              Agent Session (Claude)              │
    │                                                  │
    │  ┌─────────┐  ┌──────────┐  ┌───────────────┐  │
    │  │ Identity │  │ Memory   │  │ Task Routing  │  │
    │  │ SOUL.md  │  │ System   │  │ & Autonomy    │  │
    │  │ AGENTS.md│  │          │  │ Ladder        │  │
    │  └─────────┘  │ Daily    │  └───────┬───────┘  │
    │               │ Notes    │          │           │
    │               │ Knowledge│  ┌───────▼───────┐  │
    │               │ Graph    │  │  Sub-Agents   │  │
    │               │ Decay    │  │  Claude Code  │  │
    │               └──────────┘  │  Gemini       │  │
    │                             │  Codex        │  │
    │                             └───────────────┘  │
    │                                                  │
    │  ┌──────────────────────────────────────────┐   │
    │  │              Skills (30+)                 │   │
    │  │  Web search, browser, GitHub, X/Twitter,  │   │
    │  │  Reddit, email, calendar, content gen,    │   │
    │  │  lead scanning, SEO tools, and more       │   │
    │  └──────────────────────────────────────────┘   │
    └──────────────────────────────────────────────────┘
               │
    ┌──────────▼──────────────────────────────────────┐
    │              External Services                   │
    │  GitHub, X/Twitter, ClawMart, Google Workspace,  │
    │  Brave Search, Vercel, Sentry, RSS feeds         │
    └──────────────────────────────────────────────────┘
```

## Key Design Decisions

### Memory Over Intelligence
Alfred wakes up fresh every session. Instead of relying on context windows, everything important is written to files:
- **CORE.md** — permanent facts, never changes session-to-session
- **CURRENT.md** — active projects, recent decisions
- **Daily notes** — what happened today and yesterday
- **Knowledge graph** — entities with relationships and access tracking

Facts decay by recency: Hot (7 days) → Warm (30 days) → Cold (archive). High access count resists decay. Nothing is deleted.

### Autonomy Ladder Over Binary Permissions
Instead of "can do / can't do", Alfred uses a three-tier system:
- **T1 (Do it):** Safe, internal, clearly beneficial
- **T2 (Do it + report):** Moderate risk, reversible
- **T3 (Ask first):** External, irreversible, high-stakes

### Escalation Over Infinite Retry
Three-strike rule: retry once with a different approach, log on second failure, alert human on third. Never loop more than 3 times. Never retry with the exact same approach.

### Sub-Agents Over Monolith
Complex work gets delegated to specialized sub-agents:
- **Research** → Gemini (fast, cheap, good at synthesis)
- **Coding** → Claude Code or Codex (file exploration, iterative fixes)
- **Content** → Sonnet (quality writing)
- **Monitoring** → Haiku (fast, cheap status checks)

### Files Over Database
Everything is markdown files in a git repo. No database to manage, no migrations, no schema. `grep` is the query language. Git is the audit trail.

## Cron Jobs

Alfred runs 23+ autonomous cron jobs covering:
- Morning briefings and evening recaps
- Email monitoring and digest
- RSS/blog feed monitoring
- Lead scanning (Reddit, X)
- System health checks
- Heartbeat self-checks
- Git snapshots and backups
- Knowledge graph maintenance

Each job writes to a canary log for health monitoring. Failed jobs trigger the escalation protocol.

## Protocols

- **[Alerts](protocols/ALERTS.md)** — severity classification, cooldown rules, deduplication
- **[Approval Matrix](protocols/APPROVAL-MATRIX.md)** — what's autonomous vs. needs human sign-off
- **[Heartbeat](protocols/HEARTBEAT.md)** — periodic self-check covering security, self-healing, fact extraction, and opportunity scanning
