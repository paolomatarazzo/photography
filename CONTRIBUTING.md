# Contributing

This repo runs docs-as-code: every guide is a plain-text Markdown file, tracked in Git, and changed through pull requests — the same workflow you'd use for source code. If you've contributed to a software project before, you already know this flow.

## Getting Set Up

1. **Clone the repository.**

   ```bash
   git clone https://github.com/<your-org>/your-photography-docs-portfolio.git
   cd your-photography-docs-portfolio
   ```

2. **Create a feature branch off `main`.** Branch names should follow `docs/<short-description>`:

   ```bash
   git checkout -b docs/your-change-description
   ```

3. **Make your edit.** Every file in `docs/` is standard GitHub-Flavored Markdown (GFM). No build step, no static site generator required to preview — GitHub renders it natively, and most editors (VS Code, Obsidian, etc.) render it live.

4. **Commit with a descriptive message.**

   ```bash
   git add docs/your-file.md
   git commit -m "docs: clarify EXIF DateTimeOriginal vs DateTimeDigitized behavior"
   ```

5. **Push and open a pull request.**

   ```bash
   git push -u origin docs/your-change-description
   ```

   Opening the PR against `main` on GitHub will automatically populate the description with [`.github/pull_request_template.md`](.github/pull_request_template.md) — fill it out completely. PRs missing validation steps or cross-feature impact notes will be sent back for revision.

## Style Guidelines

- **Treat every guide as an operational runbook, not a blog post.** Assume the reader is executing this once, under time pressure, on data they cannot regenerate if it goes wrong.
- **Use GitHub-native alert blocks** (`> [!NOTE]`, `> [!WARNING]`, `> [!TIP]`, `> [!IMPORTANT]`) for anything safety- or data-integrity-critical. Don't bury a warning in prose.
- **Prefer tables over paragraphs** when comparing options, tools, or before/after states.
- **State prerequisites explicitly** at the top of any procedural doc — software versions, backup requirements, assumed knowledge.
- **No unexplained jargon.** If a term is specific to a tool (e.g., "Metadata Save State" in Lightroom), define it on first use.
- **Every claim about tool behavior should be verifiable.** If you tested it yourself, say so. If you're documenting from vendor docs, link the source.

## Review Standard

A PR is mergeable when a reader with no prior context could follow the guide end-to-end, once, without needing to ask a follow-up question. That's the bar — not "technically correct," but "unambiguous under execution."

## Reporting a Documentation Bug

If you find a step that's wrong, outdated, or dangerous (e.g., an operation that isn't actually non-destructive), open an issue immediately rather than a PR — factual errors in a data-mitigation guide should be flagged and pulled from trust before they're fixed, not silently patched.
