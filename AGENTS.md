# Repository Guidelines

## Project Structure & Module Organization
- Single-page site lives in `ProtoMechSystems-Website.html`, which contains markup, inline styles, and pulls Bootstrap 5 and Google Fonts from CDNs.
- If you add images, create an `assets/` directory at the repo root and reference files with relative paths (e.g., `assets/hero.jpg`).
- Keep theme variables in the existing `<style>` block; prefer extending those CSS custom properties over adding scattered color values.

## Build, Test, and Development Commands
- Local preview: `python -m http.server 8000` from the repo root, then open `http://localhost:8000/ProtoMechSystems-Website.html`.
- Browser-only preview also works: open the HTML file directly to verify static rendering if you don’t need routing or fetch calls.
- Formatting (optional but encouraged): `npx prettier --write ProtoMechSystems-Website.html` to normalize spacing before commits.

## Coding Style & Naming Conventions
- HTML/CSS use 2-space indentation; keep attributes on new lines when they don’t fit comfortably.
- Class names are hyphenated (e.g., `hero-title`, `feature-card`); follow existing naming to avoid clashes with Bootstrap.
- Reuse CSS variables in `:root`; prefer `var(--primary)` instead of hard-coded hex values to maintain theme coherence.
- Keep Bootstrap overrides minimal and scoped; place additional styles inside the current `<style>` tag instead of inline `style` attributes.

## Testing Guidelines
- Manual smoke test each change in Chrome and Safari/Edge if possible; verify layout across mobile (375px) and desktop widths.
- Check console for errors and validate links, anchors, and form targets; avoid mixed-content warnings when adding external resources.
- If you add JS, include a brief inline comment for non-obvious logic and test interactions after a hard refresh.

## Commit & Pull Request Guidelines
- Commits: concise, present-tense subject line under ~72 chars (e.g., `Improve hero CTA contrast`). Avoid bundling unrelated changes.
- Pull Requests: summarize what changed, how to verify (commands or steps), and any visual diffs (before/after screenshots) for UI tweaks.
- Link related issues if they exist; call out any trade-offs or follow-ups in the PR description.

## Security & Configuration Tips
- Do not embed secrets or API keys in the HTML; prefer environment-based configuration if dynamic endpoints are introduced later.
- Keep CDN integrity attributes (`integrity`, `crossorigin`) intact when upgrading dependencies to preserve subresource protections.
