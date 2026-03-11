# Humanizer — Remove AI Writing Patterns

Detects and removes signs of AI-generated writing based on Wikipedia's comprehensive editorial guidelines. Makes text sound like it was written by a person with opinions, not a language model.

## What It Catches

- Inflated symbolism ("serves as a testament to")
- Promotional language and superlatives
- Em dash overuse
- Forced rule of three
- AI vocabulary (delve, pivotal, tapestry, multifaceted)
- "It's not just X, it's Y" constructions
- Negative parallelisms ("not merely... but rather")
- Excessive conjunctive phrases
- Vague attributions ("many experts say")

## How It Works

Two-pass system:
1. **Detection pass** — identifies AI patterns in the text
2. **Rewrite pass** — replaces flagged patterns with natural alternatives

## Full Version

The production Humanizer with configurable rule sets, batch processing, and integration with content pipelines is available on [ClawMart](https://clawmart.com).
