# External Action Approval Matrix

Nothing external without approval. Confirm before deletions. Security changes require explicit approval.

## Categories

### 1) AUTO (no extra approval)
Safe internal actions that do not leave the machine and are reversible/non-destructive.

Examples:
- Reading/searching local files
- Drafting content locally
- Health/reliability checks
- Creating internal reports and summaries

### 2) DRAFT (prepare, do not send)
Actions that produce outbound-ready artifacts but do not execute external side effects.

Examples:
- Draft social media post text in file
- Draft customer email in markdown
- Draft outreach messages and lead lists
- Draft account/security change plan (commands not executed)

### 3) EXPLICIT APPROVAL (must be confirmed first)
Any irreversible, externally visible, or security-sensitive action.

Examples:
- **Social media posts/replies/deletes/likes** (actual API action)
- **Customer emails** send/reply/forward
- **Outreach sends** (any platform)
- **Account/security changes** (keys, auth, permissions, config)
- **Deletions** (files/data/messages/records), even recoverable

## Quick Decision Rule
If an action is external, destructive, or changes security posture: require explicit approval.
If not, keep work in auto/draft mode.
