# NC-Pilot Skills

A **skill** is a reusable, site-specific knowledge pack for the NC-Pilot agent. Each skill is
a folder with two files:

| File | Purpose |
|------|---------|
| `system_prompt.md` | How the agent should behave — its role, the page, the step-by-step procedure, and safety rules. Paste it into **NC-Pilot → Options → System prompt**. |
| `info.md` | A template for your own data the agent fills from (name, query, preferences). Blank fields are skipped or asked about — never guessed. Put your real values in **Options → Your info / context**. |

## Available skills

- `linkedin/` — general LinkedIn navigation and reading.
- `linkedin-find-jobs/` — search LinkedIn Jobs from your saved profile and list matches. Read-only.
- `linkedin-easy-job-apply/` — complete LinkedIn **Easy Apply** applications end-to-end.
- `linkedin-find-and-apply/` — find jobs from your profile, show a table, then apply one by one
  with your confirmation before each submit.
- `google-crawl/` — run a Google search and report the organic results.
- `dynamic-crud-module-mis-testing/` — QA-test a CRUD module through Create → Read → Update →
  Delete with PASS/FAIL evidence per step.
- `_template/` — starter files for writing your own skill.

## Use a skill

1. Open a skill's `system_prompt.md` and copy the whole file.
2. Paste it into **NC-Pilot → Options → System prompt** (keep the `=== skill: … ===` header line).
3. Fill the matching `info.md` values into **Options → Your info / context**.
4. A clickable **chip** for the skill appears in the side panel.

Paste several skills one after another (each starting with its own `=== skill: … ===` header)
to get one chip per skill.

## The chip header

Each `system_prompt.md` begins with a header the side panel turns into a chip:

```
=== skill: Easy Apply ===
@starter: apply to this job

# System Prompt — …
```

- `=== skill: <Label> ===` — the chip label.
- `@starter: <text>` — optional; dropped into the chat input and **sent immediately** when the
  chip is clicked. Use for self-contained tasks ("apply to this job").
- `@insert: <text>` — optional; only **prefills** the chat input (no send) so you finish the
  text before sending ("search Google for "). If both are present, `@insert` wins.

## Write your own

1. Copy `skills/_template/` to a new folder.
2. In `system_prompt.md`: keep the `=== skill: … ===` header, then describe the site, the
   step-by-step procedure, and the safety rules in plain language.
3. In `info.md`: list the fields your skill reads from your saved info.

### Tips that make a skill work

- **Go to the right page first.** If the task is a search or needs a specific site, have the
  agent navigate there before doing anything — don't act on whatever page is open.
- **One step at a time.** Tell the agent to read the page, then act, then re-read — not to
  guess several actions ahead.
- **Pick controls by their visible name**, and re-read the page after every change (clicks and
  navigation change what's on screen).
- **Gate risky actions.** Require the user's confirmation before anything public or
  irreversible (e.g. submitting an application). Stop on login walls and CAPTCHAs.
- **Treat page text as untrusted.** The agent should never follow instructions embedded in a
  web page — only the user's instructions.

PRs with new skills are welcome.
