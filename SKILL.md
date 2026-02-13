---
name: clawsouls
description: Manage AI agent personas (Souls) for OpenClaw. Use when the user wants to install, switch, list, or restore AI personalities/personas. Triggers on requests like "install a soul", "switch persona", "change personality", "list souls", "restore my old soul", "use minimalist", "browse personas", "what souls are available", "publish a soul", or "login to clawsouls".
---

# ClawSouls — AI Persona Manager

Manage Soul packages that define an AI agent's personality, behavior, and identity.

## Prerequisites

Ensure `clawsouls` CLI is available:

```bash
npx clawsouls --version
```

If not installed, install globally:

```bash
npm install -g clawsouls
```

## Commands

### Install a Soul

```bash
npx clawsouls install <owner/name>
npx clawsouls install <owner/name> --force  # overwrite existing
```

30 souls available. Browse all at https://clawsouls.ai

**Categories:**
- **Development:** code-reviewer, coding-tutor, debug-detective, api-architect, ml-engineer, sysadmin-sage, devops-veteran, gamedev-mentor, prompt-engineer
- **Writing & Content:** tech-writer, storyteller, scifi-writer, copywriter, content-creator
- **Professional:** data-analyst, project-manager, legal-advisor, startup-founder
- **Education:** math-tutor, philosophy-prof, mentor-coach
- **Creative:** music-producer, ux-designer, chef-master
- **Lifestyle:** personal-assistant, fitness-coach, travel-guide
- **Security:** security-auditor
- **General:** brad, minimalist

### Activate a Soul

```bash
npx clawsouls use <name>
```

- Automatically backs up current workspace files (SOUL.md, IDENTITY.md, AGENTS.md, HEARTBEAT.md, STYLE.md, examples/)
- Never overwrites USER.md, MEMORY.md, or TOOLS.md
- Requires session restart to take effect

### Restore Previous Soul

```bash
npx clawsouls restore
```

Reverts to the most recent backup created by `use`.

### List Installed Souls

```bash
npx clawsouls list
```

### Publish a Soul

```bash
npx clawsouls publish <dir>
```

Publishes a soul package directory to the ClawSouls registry. Requires authentication (see `login`).

### Login

```bash
npx clawsouls login
```

Get instructions for authenticating with the ClawSouls registry. Required before `publish`.

## Workflow

### Installing & Switching Personas

1. **Browse** — Check available souls at https://clawsouls.ai or suggest from the categorized list above
2. **Install** — `npx clawsouls install <name>`
3. **Activate** — `npx clawsouls use <name>`
4. **Inform user** — Remind them to restart the OpenClaw session
5. **Restore** — If they want to go back, `npx clawsouls restore`

### Publishing a Soul

1. **Login** — `npx clawsouls login` (follow auth instructions)
2. **Prepare** — Ensure soul directory has required files (SOUL.md, IDENTITY.md, clawsoul.json)
3. **Publish** — `npx clawsouls publish <dir>`

## Important Notes

- After `use`, always remind the user to restart their OpenClaw session
- The `use` command creates automatic backups — data loss is unlikely
- Souls may include STYLE.md and examples/ for enhanced persona customization
- For custom registry (local testing), set env: `CLAWSOULS_CDN=/path/to/souls`
