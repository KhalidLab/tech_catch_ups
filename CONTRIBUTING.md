# Contributing meeting notes

Contributions are intentionally lightweight: one Markdown file per meeting, using the shared template and tag vocabulary.

## Add a meeting

1. Copy `docs/meetings/TEMPLATE.md` to `docs/meetings/YYYY-MM-DD-short-topic.md`.
2. Replace all placeholders and keep the summary concise.
3. Select a small number of tags already defined in `mkdocs.yml`.
4. Run `mkdocs build --strict` before opening a pull request.

## Add a new tag

Only add a tag when an existing one does not adequately describe a recurring topic. Add the exact same spelling to:

- `plugins.tags.tags_allowed` in `mkdocs.yml`; and
- the appropriate category on `docs/index.md`.

This keeps the tag vocabulary controlled and prevents near-duplicate tags.

## Content guidelines

- Capture useful takeaways and advice rather than verbatim minutes.
- Prefer official documentation, repositories, papers, and stable references.
- Give links short descriptions so readers know why they are useful.
- **Do not publish confidential information, personal data, access credentials, or internal-only links in a public repository.**
