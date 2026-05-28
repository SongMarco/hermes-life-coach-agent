# Cron Setup

The distribution ships disabled sample schedules so installation does not start messaging you unexpectedly.

Recommended schedules:

| Job | Cron | Purpose |
| --- | --- | --- |
| Morning Check-in | `0 9 * * *` | Plan the day |
| Evening Review | `30 22 * * *` | Close the day |
| Weekly Review | `0 21 * * 0` | Review patterns and choose next week priorities |

Enable or recreate jobs from your installed profile:

```bash
hermes -p life-coach cron list --all
hermes -p life-coach cron edit life-coach-morning-checkin
```

If your Hermes version does not preserve bundled disabled cron jobs during install, recreate them manually:

```bash
hermes -p life-coach cron create '0 9 * * *'
hermes -p life-coach cron create '30 22 * * *'
hermes -p life-coach cron create '0 21 * * 0'
```

Use the prompts from `cron/jobs.json`.

Delivery depends on your gateway platform. For Discord/Telegram/Slack, configure the gateway after install:

```bash
hermes -p life-coach gateway setup
hermes -p life-coach gateway start
```
