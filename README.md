# Hermes Life Coach Agent

A public Hermes profile distribution for lightweight daily coaching:

- daily scrum / morning check-in
- evening review
- weekly review
- routine design
- journaling prompts
- optional Obsidian vault-backed notes

This is intentionally **not** a research, coding, browser automation, or therapy agent.

## Install

```bash
hermes profile install github.com/SongMarco/hermes-life-coach-agent --alias
```

Then configure your model/provider:

```bash
life-coach setup
# or
hermes -p life-coach setup
```

Run it:

```bash
life-coach chat
# or
hermes -p life-coach chat
```

Update later:

```bash
hermes profile update life-coach
```

## Optional Obsidian setup

If you want notes saved to Obsidian, set these in the installed profile's `.env`:

```env
OBSIDIAN_VAULT_PATH=/absolute/path/to/your/ObsidianVault
LIFE_COACH_FOLDER=Life-Coaching
```

The bundled skill writes notes under folders such as:

```text
Life-Coaching/daily/
Life-Coaching/weekly/
Life-Coaching/reflections/
Life-Coaching/routines/
```

## Cron / scheduled coaching

This repo includes disabled sample cron jobs in `cron/jobs.json`:

- Morning Check-in: `0 9 * * *`
- Evening Review: `30 22 * * *`
- Weekly Review: `0 21 * * 0`

They are disabled by default to avoid surprising users. Enable or recreate them after install:

```bash
life-coach cron
# or create your own:
hermes -p life-coach cron create '0 9 * * *'
```

See [`docs/cron-setup.md`](docs/cron-setup.md).

## What is included

```text
distribution.yaml
SOUL.md
config.yaml
.env.EXAMPLE
skills/life-coaching/obsidian-life-coach/
cron/jobs.json          # disabled samples
docs/cron-setup.md
```

## What is not included

Hermes distributions intentionally do not publish:

- `.env`
- `auth.json`
- memories
- sessions
- logs
- local databases
- personal vault contents

## Safety note

This agent can support reflection and routines, but it is not medical, mental-health, legal, financial, or emergency advice. In urgent crisis or safety situations, contact local emergency services, a licensed professional, or trusted people nearby.

## License

MIT
