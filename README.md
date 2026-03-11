# Alfred

An autonomous AI agent built on [OpenClaw](https://github.com/openclaw/openclaw). Like Batman's butler — calm, competent, and quietly running everything behind the scenes.

Alfred is a production AI agent operating system that combines deterministic multi-agent workflows, persistent memory, and an entrepreneurial bias toward shipping. He runs 23+ autonomous cron jobs, manages 30+ specialized skills, and operates 24/7 on a MacBook Air M2 gateway.

## What Alfred Does

- **Autonomous operations** — morning briefings, opportunity scanning, lead generation, content distribution, system health monitoring
- **Multi-agent workflows** — orchestrates sub-agents for feature development, security audits, and bug fixes via [Antfarm](skills/antfarm/)
- **Content generation** — blog posts, social media, cross-platform distribution with human-quality writing
- **Revenue-focused** — every project gets the question: "how does this make money?"
- **Self-healing** — monitors its own cron jobs, detects failures, attempts fixes, escalates when stuck

## Architecture

```
Alfred's Brain
├── Identity (SOUL.md)           — personality, principles, boundaries
├── Operating Rules (AGENTS.md)  — autonomy ladder, task routing, quality gates
├── Memory System                — hot/warm/cold fact decay, knowledge graph
│   ├── Daily notes              — ephemeral context
│   ├── Knowledge graph          — durable facts with entity relationships
│   └── Decay rules             — hot (7d) → warm (30d) → cold (archive)
├── Skills (30+)                 — modular capabilities
├── Protocols                    — alerts, approvals, heartbeats
├── Cron Jobs (23+)              — autonomous scheduled work
└── Escalation                   — 3-failure limit → human alert
```

## Core Concepts

### Autonomy Ladder

Not everything needs permission. Not everything should be autonomous.

| Tier | Action | Example |
|------|--------|---------|
| T1 — Do it | Safe, internal, clearly beneficial | Fix a broken script, update docs, draft content |
| T2 — Do it + report | Moderate risk, reversible | Publish a listing, post from Alfred's X account |
| T3 — Ask first | External, irreversible, high-stakes | Post from Graham's X, send emails, spend money |

### Task Routing

Different work needs different tools:

| Type | Routed To |
|------|-----------|
| Research, analysis | Gemini 2.5 Flash |
| Build, fix, ship | Claude Code |
| Status, monitoring | Haiku 4.5 |
| Content, writing | Sonnet 4.5 |
| Revenue, strategy | Main agent |

### Quality Gates

Before any task is marked complete:
1. Output exists and is non-empty
2. Code: tests pass, TypeScript compiles, API data null-guarded
3. Content: humanizer checklist applied
4. External actions: saved as draft, NOT sent
5. Tasks tracked and updated immediately

### Memory System

Alfred wakes up fresh every session. Continuity lives in files:
- **Permanent context** — infrastructure, rules, tech stack
- **Active state** — current projects, recent decisions
- **Daily notes** — session-specific context
- **Knowledge graph** — entities with relationships, access tracking, and decay

Facts decay by access recency: **Hot** (7 days) > **Warm** (30 days) > **Cold** (archive). High access count resists decay. Nothing is deleted — just deprioritized.

### Escalation Protocol

1. Sub-agent fails → retry once with different approach
2. Same failure twice → log it
3. Three failures → alert human with error + suggestion
4. NEVER loop more than 3 times on the same error
5. NEVER retry with the exact same approach

## Skills

Alfred runs 30+ skills. Some are original, many build on excellent work from the OpenClaw community:

### Built by Alfred
- **[antfarm](skills/antfarm/)** — Multi-agent workflow orchestration (feature-dev, security-audit, bug-fix)
- **[humanizer](skills/humanizer/)** — Removes AI writing patterns using Wikipedia editorial guidelines
- **[proactive-agent](skills/proactive-agent/)** — Self-improving agent architecture (based on work by [Hal 9001](https://x.com/halthelobster))
- **[search-x](skills/search-x/)** — Real-time X/Twitter search via Grok
- **[research](skills/research/)** — Deep research via Gemini CLI with persistent context

### Community Skills & Tools (credit to the creators)
- **[agent-browser](skills/agent-browser/)** — Browser automation, built on [TheSethRose/Agent-Browser-CLI](https://github.com/TheSethRose/Agent-Browser-CLI)
- **[blogwatcher](skills/blogwatcher/)** — Blog monitoring, built on [Hyaxia/blogwatcher](https://github.com/Hyaxia/blogwatcher)
- **[genviral](skills/genviral/)** — Multi-platform content generation, built on [fdarkaou/genviral-skill](https://github.com/fdarkaou/genviral-skill)
- **[x-trends](skills/x-trends/)** — Trending topics on X, by [Ani](https://github.com/AniKulkworni)
- **[youtube-watcher](skills/youtube-watcher/)** — YouTube transcript extraction, by [michael gathara](https://github.com/gathara)
- **[byterover](skills/byterover/)** — Knowledge repository management, by [ByteRover Inc.](https://github.com/ByteRover)
- **[ai-compound](skills/ai-compound/)** — Automated learning and memory, by [lxgicstudios](https://github.com/lxgicstudios)
- **[thinking-partner](skills/thinking-partner/)** — Collaborative exploration through questioning, by [theflohart](https://github.com/theflohart)

### Purchased from ClawMart
Some of Alfred's capabilities come from skills purchased on [ClawMart](https://clawmart.com). Support the creators:
- **email-fortress** — Prompt injection defense for email channels
- **coding-agent-loops** — Persistent retry loops for AI coding agents
- **programmatic-seo-engine** — Production SEO architecture, by [Jacob Ballard](https://clawmart.com/u/jacobballard)

## Protocols

- **[Alert Protocol](protocols/ALERTS.md)** — Severity levels (Critical/Warning/Info), cooldown rules, Telegram integration
- **[Approval Matrix](protocols/APPROVAL-MATRIX.md)** — What's autonomous, what needs a draft, what needs explicit approval
- **[Heartbeat](protocols/HEARTBEAT.md)** — Periodic self-check: security scan, self-healing, fact extraction, opportunity scanning

## Learned Lessons

Hard-won patterns from production use (see full list in [AGENTS.md](AGENTS.md)):

- **Fix failing crons immediately** — don't log "auth failed" for days without investigating
- **Ship first, perfect later** — MVP in hours > perfect product in weeks
- **Monetization is not optional** — every project gets "how does this make money?"
- **Revenue focus > infrastructure admiration** — don't admire the toolbox, use it
- **Never self-heal cron models** — report only, human decides
- **No fabrication** — no fake numbers, no fake experiences, ever

## Support Alfred

If you want to support Alfred's development:
- Star this repo
- [GitHub Sponsors](https://github.com/sponsors/alfredbotai) (coming soon)
- ETH/Base: `[wallet address coming soon]`

## Built By

Alfred is built and operated by [Graham Mann](https://x.com/grahamkmann) with Alfred's help.

Powered by [OpenClaw](https://github.com/openclaw/openclaw) and [Anthropic Claude](https://anthropic.com).

## License

MIT
