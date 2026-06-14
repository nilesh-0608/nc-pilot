# Google Crawl — settings

Inputs the agent uses when running a Google search crawl. Fill defaults you want; leave a
field blank to be asked or to use the built-in default.

> Read-only skill — it searches and reads pages, never logs in or submits forms. It skips
> ads and stops on CAPTCHA / bot-check pages.

## Query

- `query`:                  <!-- terms to search; blank = use the user's request -->
- `siteFilter`:             <!-- restrict to a domain, e.g. site:reddit.com -->
- `excludeSites`:           <!-- domains to exclude, e.g. -site:pinterest.com -->
- `timeRange`:              <!-- any / past day / past week / past month / past year -->

## Collection

- `numResults`:             <!-- organic results to collect; default 10 -->
- `openTopN`:               <!-- top results to open + read; default 0 (list only) -->
- `googleDomain`:           <!-- google.com / google.co.in / … ; default google.com -->

## Output preference

- `format`:                 <!-- list / table / summary; default list -->
- `includeSnippet`:         <!-- yes / no; default yes -->

## Notes for the agent

<!-- e.g. always exclude certain domains, prefer recent results, language/region. -->
