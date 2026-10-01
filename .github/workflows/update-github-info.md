---
name: update-github-info
on:
  schedule: daily
  workflow_dispatch:

permissions:
  contents: read
  pull-requests: read

tools:
  edit:
  web-fetch:

network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com

safe-outputs:
  create-pull-request:
    draft: true
---

# Update GitHub Info

Read `notes/mona-notes.md` and `site/content/github-info.md` first. Use the notes as editorial guidance and preserve the page's focus and existing useful content.

Use `web-fetch` to read all of these sources:

- https://github.blog/latest/
- https://github.blog/changelog/
- https://awesome-copilot.github.com/workflows/

Select only recent, useful developments that help developers learn GitHub faster. Keep any update short and practical, verify details against the fetched pages, and identify the relevant GitHub Blog or Changelog source in the content. Update `site/content/github-info.md` only when there is a worthwhile change; avoid duplicating existing material.

If you make a change, propose it through the configured `create-pull-request` safe output as one draft pull request for Mona to review. Include a concise title and explain the selected updates and their official sources in the pull request description. Do not write directly to the default branch or use any other write mechanism. If there is no worthwhile update, make no changes and do not open a pull request.