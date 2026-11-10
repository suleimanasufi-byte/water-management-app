# MEMORY.md

## Project
- **Name**: نظام إدارة مشروع المياه (Water Project Management System)
- **Purpose**: Mobile app for managing drinking water projects in Yemen — subscribers, billing, meters, cycles, expenses, reports, offline-first
- **Language**: Arabic, RTL

## User Preferences
- Target audience: Yemen water project operators
- Core operations should work offline-first
- Professional, easy-to-use, fast
- Login/auth functionality should be active and accessible from menus
- New subscriber, invoice, expense, and cycle entry should be accessible from relevant menus and interfaces, not buried
- Prioritize making entry and menus easier and faster
- Light and dark modes should remain clearly readable

## Tech Stack
- **Flutter + Dart**: planned mobile app
- **SQLite / sqflite**: planned local database
- **Material 3**, **RTL**
- **Astro**: current web deliverable
- **Schema.org SoftwareApplication** markup for SEO

## Current Deliverable
- Web landing page, not the Flutter app
- Pages: `src/pages/index.astro`, `src/pages/new-invoice.astro`, `src/pages/new-subscriber.astro`, `src/pages/new-expense.astro`
- Components: `src/components/Header.astro`, `src/components/Footer.astro`
- Auth: `src/components/auth/KleapAuth.tsx` — exports `UserButton`, integrated in Header
- Index section anchors: `#subscribers`, `#invoices`, `#expenses`, `#cycles`
- Offline-related web files: `public/water-offline.js`, `src/layouts/Base.astro`; the script includes browser-cache storage for same-origin pages/resources

## Notes
- Index modal helpers: `openSubModal`, `openInvModal`, `openExpModal`, `openCycleModal`, and corresponding `save*` handlers; keep wired across menus
- Theme button (`theme-btn`, `toggleTheme()`) lives in Header; preserve when editing
- Pages must use the shared `<Header />`; do not duplicate a hardcoded `<header>` in individual pages
- Keep auth integration consistent on new pages
- Focus improvements on entry fields and menu accessibility
- Flutter app build remains pending