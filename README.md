# SpendWise Dashboard

**Live site:** [https://YOUR-USERNAME.github.io/SPENDWISE-DASHBOARD/](https://thunderous-sunshine-89dc53.netlify.app/) *(update this link after publishing to GitHub Pages)*

## What this project is

SpendWise is a personal budgeting dashboard concept. It gives someone a
single screen to see their account balance, how much they've spent this
month against their budget, and a breakdown of spending by category
(Food, Transport, Rent, Entertainment, Savings, Utilities).

## What's built so far

This week's milestone is a static, responsive dashboard **shell** built with
HTML and modern CSS (Grid + Flexbox). It's realistic-looking, fully
responsive content and layout — but everything on the page is currently
static/hard-coded. No JavaScript functionality yet.

## What's on the page

- **Sidebar / Navigation** — brand logo, five nav links (Dashboard,
  Transactions, Reports, Budgets, Settings) with an active state, and a user
  profile chip at the bottom.
- **Header** — page title and subtitle, a search box, an "Add Expense"
  button, and a user avatar.
- **Summary strip** — three quick stats (Total Balance, Monthly Spend,
  Monthly Budget).
- **Six category cards** — Food, Transport, Rent, Entertainment, Savings, and
  Utilities, each showing an icon, a trend badge (up/down/flat), the amount
  spent, and the budget it's measured against.

## How it's built

### 1. Layout: CSS Grid + Flexbox
- **CSS Grid** drives the page-level layout: `.dashboard` is a
  two-column grid (`var(--sidebar-width) 1fr`) splitting the sidebar from the
  main content, and `.cards-grid` is a 3-column grid that places the six
  category cards.
- **Flexbox** handles everything nested inside those regions: the header's
  title/search/button/avatar row, the sidebar's logo/nav-list/user-chip
  column, the nav links themselves (icon + label), the summary strip, and the
  internal layout of each card (icon row, label, amount, sub-text).
- No absolute positioning is used anywhere in the layout.

### 2. Theme via CSS custom properties
All colors are defined once on `:root` and reused throughout the stylesheet:
- `--color-brand` — deep navy, used for the sidebar and header avatar.
- `--color-accent` — teal, used for the active nav item and primary button.
- `--color-surface` / `--color-surface-card` — page background vs. white card
  surfaces.
- `--color-text` / `--color-text-secondary` — primary and muted text.
- Supporting variables (`--color-success`, `--color-danger`,
  `--color-neutral`) drive the up/down/flat trend badges on each card.

Typography follows the same pattern as previous weeks: **Poppins** for
headings/amounts, **Inter** for body text and labels.

### 3. Responsiveness
A single media query at `max-width: 768px`:
- Collapses `.dashboard` from a two-column grid to one column.
- Turns the sidebar from a vertical column into a horizontal, wrapping bar
  so it doesn't dominate the screen on mobile.
- Stacks the header's title and actions instead of spreading them
  side-by-side.
- Collapses `.cards-grid` to a single column so cards stack vertically.

Verified using Chrome DevTools' Device Toolbar at common mobile widths
(375px, 414px) and at the 768px breakpoint itself.

## Files

- `index.html` — dashboard markup (sidebar, header, summary strip, cards).
- `style.css` — theme variables, Grid/Flexbox layout, and the responsive
  media query.
- `README.md` — this file.

## What's coming next

This is a shell only — no JavaScript, no live data yet. **JavaScript
functionality starts next week**, and will likely include:

- Making the search box actually filter transactions/cards.
- Wiring up the "+ Add Expense" button to add a real entry.
- Calculating the summary strip (balance, monthly spend) from real data
  instead of hard-coded numbers.
- Possibly persisting data with `localStorage`.

## Testing

The layout was checked responsively using Chrome DevTools' Device Toolbar
at common mobile widths (375px, 414px) and at the 768px breakpoint, and it
was also opened on a real phone and reviewed for readability. It was shared
with another person for feedback before submission.

## Feedback received

*(Fill this in with the actual feedback you got and what, if anything, you
changed as a result — e.g. "A classmate pointed out the search box was too
narrow on tablet width, so I adjusted the media query.")*
