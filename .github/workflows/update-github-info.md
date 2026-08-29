---
name: update-github-info
description: Draft GitHub website updates for Mona's GitHub Info site from official GitHub sources and open a pull request for review.
'on':
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
tools:
  edit:
  web-fetch:
'safe-outputs':
  'create-pull-request':
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
network:
  allowed:
    - github.blog
    - github.com
---

# Update Mona's GitHub Info website

Review the repository context before making changes:

- Read `notes/mona-notes.md`.
- Read repository guidance or reference files with GitHub repository API tools instead of terminal, CLI, or sandboxed commands.
- Read external public guidance with the web-fetch tool.

Use the latest official GitHub sources to inform the update:

- Web fetch https://github.blog/latest/
- Web fetch https://github.blog/changelog/

Search for the most relevant updates and summarize them in a way that matches Mona's site and audience.

Update `site/content/github-info.md` with concise, practical changes that reflect the latest GitHub Blog and GitHub Changelog updates while staying aligned with the repository's existing content and tone.

When preparing the patch:

- Keep the writing clear and useful for readers of the site.
- Highlight meaningful product, policy, or platform changes.
- Include source context when content comes from the GitHub Blog or GitHub Changelog.
- Preserve the site's current structure and voice.
- Do not write directly to `main`; rely on `safe-outputs` with `create-pull-request` to propose the change.

Open a pull request for Mona to review. Use a pull request title that clearly references Mona or the GitHub Info site, and keep the change ready for review rather than pushing directly to the default branch.
