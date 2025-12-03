# Contributor Guide

Welcome! This guide explains how to contribute to the CMS User Guide using mdBook.

## How mdBook Works
- All content lives in the `src/` directory as Markdown files.
- The book structure is defined in `src/SUMMARY.md`.
- When you push changes to the `main` branch, the book is automatically rebuilt and published to GitHub Pages.

## How to Add or Edit Content

### Add a New Chapter/Page
1. Create a new Markdown file in `src/` (e.g., `src/New_Chapter.md`).
2. Add a link to your new file in `src/SUMMARY.md`:
   ```
   - [New Chapter](./New_Chapter.md)
   ```
3. Commit and push your changes to `main`.

### Edit Existing Content
- Edit the relevant Markdown file in `src/`.
- Commit and push your changes.

### Organize Chapters
- Use `src/SUMMARY.md` to set the order and hierarchy of chapters.
- Indent chapters under parents for nesting.

### Preview Locally (Optional)
1. Install mdBook (if not already):
   - macOS: `brew install mdbook`
   - Linux: `cargo install mdbook`
   - Windows: Download from [mdBook releases](https://github.com/rust-lang/mdBook/releases)
2. Run `mdbook serve` in the repo directory.
3. Open `http://localhost:3000` in your browser.

## Best Practices
- Always update `src/SUMMARY.md` when adding/removing/reordering chapters.
- Use clear filenames and titles.
- Preview locally before pushing.
- Commit related changes together.

## Need Help?
- Open an issue or ask in the repository discussions.

Thank you for contributing!

## Useful Links

- **Markdown Reference:**
  - [Markdown Guide (Comprehensive)](https://www.markdownguide.org/)
  - [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
  - [mdBook User Guide](https://rust-lang.github.io/mdBook/)
- **Markdown Editors:**
  - [Typora](https://typora.io/) — Live preview, cross-platform
  - [Mark Text](https://marktext.app/) — Free, open-source, cross-platform
  - [Obsidian](https://obsidian.md/) — Powerful knowledge base, free for personal use
  - [VS Code](https://code.visualstudio.com/) — With built-in Markdown preview
- **Other Tools:**
  - [Dillinger](https://dillinger.io/) — Online Markdown editor
  - [StackEdit](https://stackedit.io/) — Online Markdown editor with cloud sync