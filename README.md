> [!NOTE]
> **This skill lives in the main collection: [milad-ahmd/agent-skills](https://github.com/milad-ahmd/agent-skills/tree/main/skills/e2e-flow-tester)**. Please ⭐ star it there; that's where updates land first.
> Docs: **https://milad-ahmd.github.io/agent-skills/skills/e2e-flow-tester/** · Claude Code: `/plugin install all-skills --marketplace milad-ahmd/agent-skills`

<div align="center">

# 🎭 e2e-flow-tester

**Find your app's critical user flows and write Playwright end-to-end tests for them. An Agent Skill for Claude Code, Cline, Cursor, Codex and other AI coding agents.**

[![License: MIT](https://img.shields.io/github/license/milad-ahmd/e2e-flow-tester)](LICENSE)
[![Stars](https://img.shields.io/github/stars/milad-ahmd/e2e-flow-tester?style=social)](https://github.com/milad-ahmd/e2e-flow-tester)
![Category](https://img.shields.io/badge/category-Testing%20&%20Quality-blue)
![Works with](https://img.shields.io/badge/works%20with-Claude%20Code%20%7C%20Cline%20%7C%20Cursor%20%7C%20Codex-8A2BE2)

[Install](#-install) · [Usage](#-usage) · [How it works](skills/e2e-flow-tester/SKILL.md) · [All skills](https://github.com/milad-ahmd/agent-skills)

</div>

> Part of **[agent-skills](https://github.com/milad-ahmd/agent-skills)**, a growing collection of practical skills for AI coding agents.

## 📦 Install

**One command (installs the whole collection):**

```bash
curl -fsSL https://raw.githubusercontent.com/milad-ahmd/agent-skills/main/install.sh | bash -s -- e2e-flow-tester
```

**Manually (Claude Code):**

```bash
git clone https://github.com/milad-ahmd/e2e-flow-tester /tmp/e2e-flow-tester
mkdir -p ~/.claude/skills && cp -r /tmp/e2e-flow-tester/skills/e2e-flow-tester ~/.claude/skills/
```

**Per project:** copy `skills/e2e-flow-tester` into `<project>/.claude/skills/`.
**Any other agent:** paste [`SKILL.md`](skills/e2e-flow-tester/SKILL.md) into your rules or system prompt.

## 💬 Usage

Just ask your agent:

```text
Write e2e tests for our signup and checkout flows
Set up Playwright for this Next.js app
```

The full workflow, rules and output format are in [`SKILL.md`](skills/e2e-flow-tester/SKILL.md).

## 🔎 Sample output

`find_flows.py` is plain Python 3 with no dependencies. Real output on the small Next.js fixture that ships with it:

```text
$ python3 find_flows.py fixtures/next-app

Scanned fixtures/next-app
Frameworks: next-app

Critical flow candidates, score >= 5 (1)
    9  /login                           [login]  app/(auth)/login/page.tsx
       name matches 'login'; has a form (email, password inputs)

Other pages (3)
    0  /                                app/page.tsx
    0  /docs/:slug*                     app/docs/[...slug]/page.tsx
    0  /projects/:id                    app/projects/[id]/page.tsx

API endpoints (1)
  GET,POST /api/projects                    app/api/projects/route.ts

Existing e2e setup
  Playwright config playwright.config.ts: baseURL http://localhost:3000, testDir ./e2e, webServer npm run dev, storageState no, projects chromium
  Spec files: e2e/ (1)
  Dependency: @playwright/test 1.48.2
  Script test:e2e: playwright test
  CI: .github/workflows/e2e.yml mentions playwright
  Dev server: dev (next dev); package manager: npm; files with data-testid-style attributes: 1
```

It reads Next.js, React Router, Remix, SvelteKit, Nuxt, Vue Router, Angular, Django, Rails, Laravel and Express/Fastify/Koa/Hono. Scores are a starting list for you and the agent to agree on, not a verdict.

## 🧩 More skills

See the full collection: **[milad-ahmd/agent-skills](https://github.com/milad-ahmd/agent-skills)**.

## 🤝 Contributing

This repo is a read-only mirror. Please open issues and PRs in **[milad-ahmd/agent-skills](https://github.com/milad-ahmd/agent-skills)**.

## 📄 License

[MIT](LICENSE) © Milad Ahmadi

<div align="center">

**If this skill saved you time, a ⭐ helps others find it.**

</div>
