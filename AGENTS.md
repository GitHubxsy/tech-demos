# AGENTS.md

Working agreement for cloud agents in this repository.

## What this repo is

This is one sticky Bun monorepo for daily public tech demos. Never create a new GitHub repository for a demo. Do not rename this repo or change its visibility.

## Where a demo lives

Each demo lives only under `apps/<kebab-slug>/` and must be self-contained. From that directory, `bun install && bun run dev` works.

For a given demo, cloud agents may only add or update files under `apps/<kebab-slug>/`. A root change is allowed only when a workspace later strictly requires it. Prefer no root workspace wiring.

Leave `apps/` empty of demo apps until a demo pull request adds one.

## Before building a demo

Follow `skills/project-planning/` and write `apps/<kebab-slug>/PLAN.md` before building the demo.

## Bun

Bun is the runtime, package manager, and script runner.

Every app must have `bunfig.toml` with:

```toml
[install]
minimumReleaseAge = 259200
```

Create or preserve that file before any `bun install` or `bun add`.

## UI demos

For UI demos, default to shadcn/ui with a minimalist preset. Start from an official `bunx create-*` scaffold. Do not hand-roll the project skeleton.

## Demo pull requests

Every demo pull request must attach both of the following. This is not optional.

- At least one screenshot of the running app.
- At least one video of the running app.

## Preview deploys

Preview deploys use one Cloudflare Pages project for the whole monorepo, with a path per `apps/<slug>/`. Do not create one Pages project per app.

The repository uses these GitHub secrets:

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`

Do not invent those values. Do not commit tokens, account ids, or env files that contain them. Add a workflow or Pages config only when it is clearly a placeholder with no secrets.

## Scout ledger

`tracking/seen-bookmarks.json` is the scout ledger.

Never re-propose an id already listed there, whether it sits in `proposed`, `skipped`, or `built`.

Each record is an object with `id`, `title`, `url`, and `date`, stored in one of those three arrays.
