# NC-Pilot — Skills

**NC-Pilot** is a chat-driven browser automation agent for Chrome/Edge. Bring your own model:
local **Ollama**, **OpenAI**, or **Anthropic** — your keys, your machine, no middleman server.

This repository holds the public **skills library** and documentation. A *skill* is a reusable,
site-specific knowledge pack you paste into the extension — no code, just text the agent uses.

## Recommended model

For local **Ollama**, use **`qwen2.5:7b`** or larger — it reliably plans and completes
multi-step browser tasks. Small models (`qwen2.5:3b`, `gemma`, `phi`) are unreliable for
automation. `ollama pull qwen2.5:7b`. OpenAI/Anthropic models work well too.

## Install NC-Pilot

- **Chrome Web Store** — coming soon.
- The extension stores everything locally (settings, keys, your profile data). See
  [PRIVACY.md](PRIVACY.md) for exactly what is sent to your chosen model provider and nothing else.

## What's a skill?

Each folder under [`skills/`](skills/) contains:

| File | Purpose |
|---|---|
| `system_prompt.md` | The skill itself — paste into **Options → System prompt**. |
| `info.md` | Template for your data (profile, preferences) — fill it into **Options → Your info**. |

Paste several skills one after another; the side panel shows one clickable chip per skill.

## Available skills

- **`linkedin-easy-job-apply/`** — complete LinkedIn **Easy Apply** applications end-to-end,
  filling forms from your saved profile. Final submit always asks your confirmation.
- **`linkedin-find-jobs/`** — search LinkedIn Jobs from your saved profile (title, keywords,
  location) and list the matches. Read-only — it finds and lists, it does not apply.
- **`linkedin-find-and-apply/`** — find jobs from your profile, show a table, then apply one by
  one with your confirmation before each submit.
- **`google-crawl/`** — run a Google search and report the organic results (title + URL).
- **`linkedin/`** — general LinkedIn navigation and reading.
- **`dynamic-crud-module-mis-testing/`** — QA-test a CRUD module through Create → Read →
  Update → Delete with PASS/FAIL evidence per step.
- **`_template/`** — starter files for writing your own.

## Writing your own skill

1. Copy `skills/_template/`.
2. Describe the site, the step-by-step procedure, and the safety rules in `system_prompt.md`
   (plain language — see [`skills/README.md`](skills/README.md) for tips).
3. List the fields your skill reads from your saved info in `info.md`.
4. Paste it into **Options → System prompt** — a chip appears in the side panel.

PRs with new skills are welcome.

## License

MIT — see [LICENSE](LICENSE).
