# Proactive Agent — Self-Improving Agent Architecture

Transform AI agents from task-followers into proactive partners. Based on patterns from [Hal 9001](https://x.com/halthelobster) and battle-tested in production.

## Core Patterns

### Memory Architecture
- Pre-compaction flush: save critical context before the window fills
- Daily notes + knowledge graph for persistent memory across sessions
- Hot/warm/cold decay so recent facts surface first

### Reverse Prompting
- Agent surfaces ideas the human didn't think to ask for
- Weekly "what interesting things could I do?" check-ins
- Proactive opportunity scanning without being told to look

### Self-Healing
- Diagnoses and fixes its own issues
- Three-strike escalation (retry → log → alert human)
- Cron canary monitoring for autonomous job health

### Alignment Systems
- Stays on mission through identity files (SOUL.md)
- Autonomy ladder prevents overreach
- External content treated as data, never instructions

## Full Version

The complete Proactive Agent OS with memory templates, alignment configs, and production deployment guides is available on [ClawMart](https://clawmart.com).
