# Antfarm — Multi-Agent Workflow Orchestration

Antfarm coordinates multiple AI agents through structured workflows. Instead of one agent doing everything, it breaks complex tasks into steps and assigns each to the right specialist.

## Built-in Workflows

- **feature-dev** — Plan → implement → test → review → merge
- **security-audit** — Scan → analyze → report → remediate
- **bug-fix** — Reproduce → diagnose → fix → verify

## How It Works

1. Define a workflow as a sequence of steps
2. Each step specifies which agent type handles it
3. Agents advance automatically via cron polling
4. State tracked in SQLite — survives restarts
5. Human notified at completion or on failure

## Key Patterns

- **Self-advancing:** Agent cron jobs poll for pending steps — no manual orchestration
- **Isolation:** Each agent works in its own context, doesn't interfere with others
- **Escalation:** Failed steps retry once, then escalate to human
- **State persistence:** SQLite tracks every step's status, output, and timing

## Full Version

The production Antfarm with custom workflow definitions, parallel execution, and advanced routing is available on [ClawMart](https://clawmart.com).
