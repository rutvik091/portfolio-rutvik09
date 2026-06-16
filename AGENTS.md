# AGENTS — Portfolio Architecture

## Overview

Pure static site: one `index.html` file with embedded CSS and JS. No framework, no build step, no dependencies to install. Deploys directly to Netlify as a static asset.

## Key Files

```
/
├── index.html        # Entire site — markup, styles, and scripts
├── netlify.toml      # Security headers and cache rules
├── README.md         # User-facing project documentation
└── AGENTS.md         # This file — AI agent context
```

## Architecture Decisions

**Single-file design**: The user explicitly required "HTML, CSS, and JavaScript only." All CSS lives in a `<style>` block and all JS in a `<script>` block at the end of `index.html`. This maximises portability and eliminates any build tooling.

**CSS Custom Properties as design tokens**: All colors, spacing, radii, and transitions are defined under `:root` and `[data-theme="dark"]`. This makes dark mode a single attribute swap on `<html>` and centralises all theme changes.

**IntersectionObserver for everything**: Scroll reveal, active nav link detection, and SGPA counter animation all use `IntersectionObserver` — no scroll event listeners (which would cause jank).

**Font stack**: 
- `Sora` — display/headings (distinctive, geometric, modern)
- `DM Sans` — body text (clean, professional)
- `JetBrains Mono` — code-like labels and stats

## Coding Conventions

- CSS class names use kebab-case (`section-label`, `hero-name-accent`)
- BEM-ish naming: block (`project-card`), element (`project-body`), modifier (`project-btn-primary`)
- JS: vanilla, no libraries. Prefer `const` over `let`. IntersectionObserver over scroll events.
- No comments in CSS/JS unless behaviour is non-obvious

## Customisation Touchpoints

When a future agent needs to update content, all user data is inline in `index.html`:
- **Placeholder phone/email**: grep for `XXXXX` and `your-email`
- **Project links**: all `href="#"` on `<a>` tags inside `.project-links`
- **Social links**: `<a>` tags inside `.social-links-grid`
- **SGPA values**: inside `.sgpa-value` spans (also update hero stats `.hero-stat-num`)
- **Typing phrases**: the `phrases` array in the `<script>` block

## Dark Mode

Theme is toggled by setting `data-theme="dark"` on `<html>`. Persisted in `localStorage` under key `rn-theme`. Falls back to `prefers-color-scheme` media query on first visit.

## Performance Notes

- No JS frameworks loaded
- Fonts loaded with `display=swap` via Google Fonts (preconnect hints in `<head>`)
- Font Awesome loaded from Cloudflare CDN
- Animations use only `transform` and `opacity` (GPU-composited, no layout reflow)
- Background blobs use `filter: blur()` on `position: absolute` elements (not on scroll containers)
