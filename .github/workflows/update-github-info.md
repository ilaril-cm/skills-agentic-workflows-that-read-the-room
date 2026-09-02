---
name: update-github-info
description: Draft GitHub Info website updates from the GitHub Blog and GitHub Changelog, then open a pull request for Mona to review.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use public guidance and repository source references as follows:
- Read external public guidance with `web-fetch`.
- Read repository guidance or reference files with GitHub repository API tools instead of terminal, CLI, or sandboxed commands.
- Prefer official sources from the GitHub Blog and GitHub Changelog.

Use these sources:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Update `site/content/github-info.md` with concise, practical updates that reflect the latest GitHub Blog and GitHub Changelog coverage while staying aligned with Mona's editorial goals.

When a change comes from the GitHub Blog or GitHub Changelog, mention the source in the page copy. Keep the writing short, useful, and developer-focused.

Open a pull request for Mona to review using `safe-outputs` with `create-pull-request`. Do not write directly to `main`.
