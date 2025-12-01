# Repository Guidelines

## Project Structure & Module Organization
Content created for Zenn lives in `articles/` (individual posts) and `books/` (multi-part series). Each Markdown file includes the Zenn front matter block describing title, slug, and publication state. Shared images belong in `images/`; reference them with relative paths so previews and production stay in sync. Project-level tooling and third-party packages are managed through `package.json` and installed into `node_modules/`. Keep experimental assets out of version control—store only ready-to-review drafts.

## Build, Test, and Development Commands
Install dependencies once with `npm install`. Use `npx zenn new:article` or `npx zenn new:book` to scaffold content; both commands prompt for slugs and generate correctly structured files. Run `npx zenn preview` to start the local preview server at `http://localhost:8000` and auto-reload on file changes. When publishing, lint Markdown manually via the preview output and fix any warnings before pushing.

## Coding Style & Naming Conventions
Write Markdown in UTF-8 with spaces for indentation (two spaces inside lists). Favor fenced code blocks with explicit language tags (` ```ts `). Slugs and filenames follow lowercase-kebab-case (`articles/nextjs-preview.md`). Image files mirror the article slug (`images/nextjs-preview/diagram.png`) so assets remain discoverable. Keep prose concise; rely on Zenn shortcodes sparingly and document any custom snippets in the article header comments.

## Testing Guidelines
There is no automated test suite; instead, validate changes by running `npx zenn preview` and clicking through every updated page. Review console output for broken internal links and inspect the browser devtools network tab for missing assets. For books, confirm that navigation order matches the chapter numbering in each `chapters:` front matter array.

## Commit & Pull Request Guidelines
Commits follow the existing imperative, lowercase style (`add article`, `update zenn-cli`). Group related edits—scaffolding plus prose—for easier review, and avoid mixing dependency upgrades with content changes. Pull requests should include a short summary, list the affected articles/books, link related Zenn drafts or issues, and attach screenshots or GIFs demonstrating the local preview when visual assets change. Request review only after `npx zenn preview` has been run cleanly.

## Security & Configuration Notes
API keys or draft-only information must not appear in tracked Markdown. Use `.env` or local shell variables when referencing private endpoints and describe the required setup at the top of the article instead of hardcoding secrets. After running preview servers, shut them down to avoid exposing unpublished drafts on shared machines.
