# MEMORY.md

## Project
- **Name**: نظام إدارة مشروع المياه (Water Project Management System)
- **Purpose**: Mobile app for managing drinking water projects in Yemen — subscribers, billing, meters, cycles, expenses, reports, offline-first
- **Language**: Arabic, RTL

## User Preferences
- Target audience: Yemen water project operators
- Must work offline-first for all core operations
- Professional, easy-to-use, fast
- Expects login/auth functionality active and accessible from menus
- New entry inputs (subscriber, invoice, expense, cycle) must be available from all relevant menus and interfaces — not buried
- User prioritizes **facilitating entry inputs and menus** (top improvement priority) — make them easier and faster
- Light and dark modes should have clear, appropriately readable colors when switching between them

## Tech Stack
- **Flutter + Dart** (mobile app — pending build)
- **SQLite / sqflite** (local DB)
- **Material 3**, **RTL** layout
- **Astro** (current deliverable: web landing page)
- **Schema.org SoftwareApplication** markup for SEO

## Current Deliverable
- Web landing page (not the Flutter app)
- Pages: `src/pages/index.astro`, `src/pages/new-invoice.astro`, `src/pages/new-subscriber.astro`, `src/pages/new-expense.astro`
- Components: `src/components/Header.astro`, `src/components/Footer.astro`
- Auth: `src/components/auth/KleapAuth.tsx` — exports `UserButton` integrated in Header for login/menu access
- Section anchors on index: `#subscribers`, `#invoices`, `#expenses`, `#cycles`

## Notes
- Modal helpers in index.astro: `openSubModal`, `openInvModal`, `openExpModal`, `openCycleModal`, plus `save*` handlers — keep all wired up across menus
- Theme button (`theme-btn`, `toggleTheme()`) lives in Header; preserve when editing
- **Header rule**: pages must use the shared `<Header />` component ONLY — never duplicate a hardcoded `<header>` block in a page (causes duplicate navigation bars when both render and drift). Remove any hardcoded `<header>` from individual pages
- Keep auth integration consistent when adding new pages
- Focus improvements on input fields & menu accessibility — reduce friction to add subscriber/invoice/expense/cycle
- Flutter app build remains the next pending task