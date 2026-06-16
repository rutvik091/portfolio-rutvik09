# Rutvik Nayi — Personal Portfolio

A modern, fully responsive single-page personal portfolio website for **Rutvik Nayi**, a B.Sc. Information Technology student at Swarrnim Startup & Innovation University.

## Features

- **Single-page design** with smooth scroll navigation
- **Dark mode toggle** (respects system preference, persists via localStorage)
- **Typing animation** cycling through role descriptions
- **Scroll-reveal animations** on all sections using IntersectionObserver
- **Animated SGPA counters** triggered on scroll
- **Floating hero card** with academic stats
- **Responsive** — mobile-first, tested across breakpoints
- **SEO-friendly** with meta tags and semantic HTML

## Sections

1. Hero — Name, typing tagline, CTA buttons, stats, avatar card
2. About — Bio, highlights grid, info card
3. Education — University details, SGPA cards (9.72 / 9.82 / 9.28)
4. Skills — Programming, Web Dev, Database, Tools
5. Projects — 3 project cards with Live Demo & GitHub buttons
6. Certifications — 2 professional certifications
7. Strengths — 6 core competencies
8. Languages — Gujarati, Hindi, English
9. Contact — Phone, email, location, social links, CTA card
10. Footer

## Technologies

- **HTML5** — semantic markup, accessible ARIA attributes
- **CSS3** — custom properties (design tokens), CSS Grid, Flexbox, animations
- **Vanilla JavaScript** — IntersectionObserver, dark mode, typing effect, counter animations
- **Font Awesome 6** — icons via CDN
- **Google Fonts** — Sora (display) + DM Sans (body) + JetBrains Mono (code)
- **Netlify** — static hosting with security headers via `netlify.toml`

## Running Locally

Simply open `index.html` in any modern browser — no build step required.

Or use the Netlify CLI:
```bash
netlify dev
```

## Customization

Update the placeholder values in `index.html`:
- `your-email@gmail.com` → real email address
- `+91 XXXXX XXXXX` → real phone number
- Project `href="#"` links → real Live Demo and GitHub URLs
- Social link `href="#"` → real GitHub, LinkedIn, Portfolio URLs
