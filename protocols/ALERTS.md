# Alert Protocol

## Severity Levels

### CRITICAL — Immediate alert, any time
- Production system down
- Security incident detected
- Data loss risk

### WARNING — Alert during waking hours only
- Cron job failed 2+ consecutive times
- Disk usage > 85%
- Multiple API errors in 1 hour

### INFO — Log only, include in daily digest
- Cron completed successfully
- Health check passed
- Routine maintenance done

## Cooldown Rules
- Same alert (by key): suppress for 30 minutes
- Same category: suppress for 15 minutes
- Track cooldowns in a state file to prevent alert storms

## Format
```
[SEVERITY] Job: {name}
Status: {FAILED/WARNING}
Error: {one-line summary}
Action needed: {yes/no}
Detail: {path to log file}
```
