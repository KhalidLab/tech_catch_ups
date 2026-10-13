# SBCB Tech Catch-ups

A lightweight, searchable knowledge base for our weekly informal software/computing catch-ups. The site is built with **Material for MkDocs** and deployed to **GitHub Pages** with GitHub Actions.

## What goes here?

Each meeting gets one Markdown file under [`docs/meetings/`](docs/meetings/). Notes should briefly capture:

- the video, talk, demo, or resource we watched/discussed;
- the main points from the discussion;
- useful technical takeaways and advice;
- links to documentation, papers, repositories, wikis, or follow-up material;
- relevant tags so the archive remains easy to search and browse.

## Repository layout

```text
.
├── .github/workflows/deploy.yml  # Build and deploy GitHub Pages
├── docs/
│   ├── index.md                  # Site home page
│   ├── tags.md                   # Generated tag index
│   └── meetings/
│       ├── .nav.yml              # spec for mkdocs-awesome-nav
│       ├── index.md              # Meeting archive landing page
│       ├── TEMPLATE.md           # Copy this for a new meeting
│       └── 2026-10-08-example.md # Example meeting note
├── .gitignore
├── CONTRIBUTING.md               # Contribution conventions
├── mkdocs.yml                    # MkDocs configuration
└── requirements.txt              # Python dependencies
```

## Add a new meeting

1. Copy `docs/meetings/TEMPLATE.md` to a file named `YYYY-MM-DD-short-topic.md`.

2. Fill in the front matter and replace the placeholder sections.

3. Choose tags from the tag vocabulary in [`docs/index.md`](docs/index.md). Add a new tag only when it represents a genuinely reusable topic.

4. Preview locally and submit your change through the normal Git/GitHub workflow.

Example:

```bash
cp docs/meetings/TEMPLATE.md docs/meetings/2026-10-15-python-profiling.md
```

## Run locally

Python 3.11+ is recommended.

```bash
python -m venv .venv
source .venv/bin/activate          # Windows: .venv\\Scripts\\activate
python -m pip install -r requirements.txt
mkdocs serve
```

Open the local URL printed by MkDocs (normally `http://127.0.0.1:8000/`).

To run the same strict build used in CI:

```bash
mkdocs build --strict
```

## Publish with GitHub Pages

The workflow in `.github/workflows/deploy.yml` builds the site on pushes to `main` and deploys the generated `site/` directory with GitHub Pages Actions.

After pushing the repository to GitHub:

1. Open **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions**.
3. Push to `main` (or run the workflow manually from the Actions tab).

## Editing conventions

- Keep notes concise and useful rather than attempting verbatim minutes.
- Prefer durable, primary links such as official documentation and project repositories.
- Use descriptive link text rather than raw URLs where possible.
- Use the existing tag vocabulary consistently.
- **Do not include confidential, personal, or otherwise non-shareable discussion in a public repository.**

## GenAI use disclosure

The starting templates and structure for this repository were generated using ChatGPT 5.6 (https://chatgpt.com, EDU Licence, Medium effort mode). Starting from that template, the repository is edited, updated and curated by humans.
