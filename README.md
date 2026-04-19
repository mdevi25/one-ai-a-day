# One AI Insight a Day

A free, browser-based AI learning calendar. Every date hides an AI insight — click and see.

**Live site:** [mdevi25.github.io/one-ai-a-day](https://mdevi25.github.io/one-ai-a-day/)

---

## What it is

A single-page microsite built for people who want to learn AI as a habit, not a project. No signup, no email capture, no progress bars. Just a calendar, 120 small insights, and your curiosity.

- **Day 1 of each month** → a Beginner's Journey step (12 foundational concepts across the year)
- **Days 2 through the end of the month** → a themed AI concept card
- **Every four months** the focus shifts to a new theme

### Quarterly themes

| Quarter | Months | Theme |
|---|---|---|
| Q1 | Jan–Mar | Fundamentals — how models work, hallucination, context windows |
| Q2 | Apr–Jun | AI for Product Managers — scoping AI features, technical debt, prioritisation |
| Q3 | Jul–Sep | AI Ethics — bias, explainability, consent |
| Q4 | Oct–Dec | Tools in Practice — Hugging Face, APIs, evaluation, deployment |

120 concept cards + 12 journey steps = **132 insights** across the year.

---

## How to use it

1. Open [the calendar](https://mdevi25.github.io/one-ai-a-day/)
2. Click any date — today or any other day
3. Read the insight that appears (usually under a minute)
4. Come back tomorrow

Deep-link to any insight with `?day=N` or `?day=1&month=M` in the URL.

---

## Tech stack

Intentionally minimal — static HTML, deployed via GitHub Pages. No build step, no framework.

- **One HTML file** (`index.html`) — all CSS, SVG, and JS inline for simplicity and offline portability
- **Plausible Analytics** — privacy-friendly, no cookies
- **CounterAPI** (V1, no account required) — powers the visible visit counter on the left panel
- **Google Fonts** — Playfair Display (display) and DM Sans (body)

### No dependencies beyond those three external services. No npm, no bundler, no server.

---

## Design principles

- **Minimum formatting, maximum clarity** — you should understand what the site does within five seconds of landing
- **Habits compound** — the calendar rhythm is the point; daily short reads beat a one-time long course
- **Accessible by default** — WCAG AA contrast on all text, respects `prefers-reduced-motion`, semantic HTML
- **No dark patterns** — no forced signup, no email capture, no tracking beyond anonymized pageviews

---

## Features

- **Two-column sticky layout** (30 / 70 on desktop, stacks below 860px)
- **Seasonal art bar** above the calendar — 12 month-specific scenes with gentle animations (spring buds, summer sun + ocean, autumn leaves, winter pines, etc.)
- **"Today" button** (calendar-pin icon) — appears only when viewing a month other than the current one
- **Expandable insight panel** below the grid; full-screen overlay available via the Expand button
- **Deep-linkable URLs** — share `?day=5&month=3` to send someone directly to March 5's insight
- **Share button** with clipboard copy and toast confirmation
- **Real visit counter** (accumulates globally, not per-device)
- **Beginner's Journey tag** on Day 1 panels shows step progress (e.g. "Step 3 of 12")

---

## Structure of a concept card

Each of the 120 concept cards contains:
- A **date label** (e.g. "April 6, 2026")
- A **title** (e.g. "Temperature — controlling randomness")
- A **visual diagram** (SVG, rendered inline, themed to the concept)
- A **short caption** explaining the concept in plain English

All rendered from inline JavaScript objects with a consistent schema:

```js
{
  title: 'Temperature',
  svg: function() { return svg('<rect .../>...', 205); },
  cap: '<b>Temperature controls randomness.</b> Production apps typically run between 0.2 and 0.8.'
}
```

---

## Running locally

```bash
git clone https://github.com/mdevi25/one-ai-a-day.git
cd one-ai-a-day
# Open index.html in any browser — no build step
python3 -m http.server 8000  # optional — serves at http://localhost:8000
```

---

## Browser support

Tested on current versions of Chrome, Safari, Firefox, and Edge. Uses modern CSS (Grid, clamp, CSS variables) — no polyfills provided for IE or legacy browsers.

---

## Accessibility

- WCAG AA contrast on all text (hero-legend and visit counter use `#5F5A53` on cream for a 6.44 contrast ratio)
- Keyboard navigation for all interactive elements
- `aria-label` on icon-only buttons
- `prefers-reduced-motion` respected — seasonal animations disable for users who request it
- Semantic HTML (`<nav>`, `<main>`, `<aside>`, `<section>`, `<footer>`, `<details>`)

---

## Privacy

- **No cookies.** Plausible is cookie-free by design.
- **No personal data collected.** The visit counter logs a count, not who you are.
- **No email capture.** No signup flow. No newsletter.
- **Third-party requests:** Plausible (analytics), CounterAPI (visit count), Google Fonts (Playfair + DM Sans). All ignored gracefully if blocked.

---

## Roadmap

Things I'm considering for future quarters:

- Worked examples linked from each concept card
- A tiny "related concepts" cluster under each insight
- Search by keyword across all 132 insights
- Alternate viewing mode (list view rather than calendar view)
- Community contributions for Q5+ (Year 2) concept curation

Open to suggestions. If you have ideas, open an issue or reach me on [LinkedIn](https://www.linkedin.com/in/madhudevi/).

---

## Built with

Designed, curated, and iterated by [Madhu Devi](https://www.linkedin.com/in/madhudevi/). Built with [Claude](https://claude.ai/) across multiple sessions.

---

## License

Content (concept cards, caption text, beginner's journey) © Madhu Devi — all rights reserved.
Code (HTML/CSS/JS structure) available under MIT License — see LICENSE file.

---

## Contact

- **LinkedIn:** [linkedin.com/in/madhudevi](https://www.linkedin.com/in/madhudevi/)
- **Portfolio:** [mdevi25.github.io](https://mdevi25.github.io)
- **Feedback:** Open an issue on this repo or reach out on LinkedIn

*A new AI insight every day. Click, learn, close the tab. Come back tomorrow.*
