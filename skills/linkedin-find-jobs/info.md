# LinkedIn Job Finder — search profile

The fields this skill searches from. Put these into **Options → Your info / context** (the same
place all skills read your data). Fill what you want; leave the rest blank. You can also just
type a query in chat (e.g. "find react jobs in pune") and it will use that instead.

> Stored locally with the extension. This skill is read-only — it finds and lists jobs, it
> never applies, messages, or logs in.

## Job search

- `targetJobTitle`:          <!-- main role, e.g. Full Stack Engineer -->
- `titleKeywords`:           <!-- comma-separated alternates; any match counts, e.g. React Developer, Frontend Engineer -->
- `locationFilter`:          <!-- city / Remote / country, e.g. Mumbai -->
- `excludeKeywords`:         <!-- skip listings whose title contains these, e.g. Senior, Lead, Intern -->
- `easyApplyOnly`:           <!-- yes = only show Easy Apply listings; blank = all -->

## Notes for the agent

<!-- e.g. "prefer remote", "only past week", companies to avoid. -->
