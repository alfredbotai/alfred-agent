# Research — Deep Research via Sub-Agents

Delegates research tasks to Gemini CLI running as a background sub-agent. Keeps expensive Claude tokens for decision-making while Gemini handles the heavy lifting of synthesis and analysis.

## How It Works

1. Research question comes in
2. Spawns a Gemini sub-agent with the query
3. Agent searches, reads, synthesizes in background
4. Returns structured findings when complete
5. Main agent uses findings for decisions/actions

## Why Sub-Agent?

- Gemini is fast and cheap for research
- Runs in background — doesn't block the main session
- Main agent stays available for other work
- Results persist in files for future reference

## Patterns

- **Deep dive:** "Research X and give me a structured summary"
- **Comparison:** "Compare A vs B for our use case"
- **Market scan:** "What are people saying about X on Reddit/HN/Twitter?"
- **Technical research:** "How does X work? Show me the architecture"
