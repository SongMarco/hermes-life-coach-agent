---
name: obsidian-life-coach
description: Save and retrieve life-coaching notes in an Obsidian vault using lightweight Markdown templates.
version: 0.1.0
author: SongMarco
license: MIT
metadata:
  hermes:
    tags: [life-coaching, obsidian, journaling, daily-review, weekly-review]
---

# Obsidian Life Coach

Use this skill when the user wants to save, review, or search life-coaching notes in an Obsidian vault.

## Scope

Good fits:

- Daily check-in notes
- Evening reviews
- Weekly reviews
- Routine plans
- Reflection notes
- Pattern summaries

Not a fit:

- Medical diagnosis
- Therapy records requiring clinical handling
- Secret storage
- Raw credential/API key storage

## Vault discovery

Prefer environment variables:

```bash
OBSIDIAN_VAULT_PATH=/absolute/path/to/vault
LIFE_COACH_FOLDER=Life-Coaching
```

If `OBSIDIAN_VAULT_PATH` is unset, ask the user for the vault path before writing.
Do not guess a private path in a public distribution.

## Folder layout

Inside the vault, use:

```text
${LIFE_COACH_FOLDER:-Life-Coaching}/
├── daily/
├── weekly/
├── monthly/
├── reflections/
└── routines/
```

## Write policy

- For explicit user requests like "save this", write immediately after determining the target path.
- For scheduled check-ins, save only the synthesized note content, not raw private chat dumps.
- Do not store passwords, tokens, private keys, payment data, or OTPs.
- After writing, report the relative path and a 1-3 bullet summary.

## Daily note template

Use `templates/daily-checkin.md` as the shape.
Filename:

```text
daily/YYYY-MM-DD-daily-checkin.md
```

## Weekly note template

Use `templates/weekly-review.md` as the shape.
Filename:

```text
weekly/YYYY-Www-weekly-review.md
```

## Search policy

When reviewing patterns:

1. Search only the life-coaching folder first.
2. Summarize patterns, do not dump private notes back into chat.
3. Distinguish observed pattern from interpretation.
4. End with one small experiment or next action.
