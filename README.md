# tech-demos

Sticky Bun monorepo for daily public tech demos. Add the next demo here. Do not create a separate GitHub repository for a demo.

## How a new app lands

1. Read [AGENTS.md](AGENTS.md). Before building, follow [skills/project-planning/SKILL.md](skills/project-planning/SKILL.md) and write `apps/<kebab-slug>/PLAN.md`.
2. Put the demo only under `apps/<kebab-slug>/`. It must be self-contained: from that directory, `bun install && bun run dev` works.

## Preview deploys

One Cloudflare Pages project serves the whole monorepo. Each demo is published at a path for `apps/<slug>/`, not as its own Pages project.

GitHub Actions uses these repository secrets. Values are not stored in this repo:

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`
