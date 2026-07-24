# Inventory Management Dashboard

> Living project document. Update this file whenever the product scope, architecture, data model, workflow, or delivery status changes. Verified facts describe the repository as it exists; proposed items require confirmation before implementation.

## Project Snapshot

- **Purpose:** Build an inventory management dashboard.
- **Current stage:** Initial application scaffold.
- **Implemented product functionality:** None. The current home page and metadata are the default Next.js starter content.
- **Last reviewed:** 2026-07-24.

## Current Technology

| Area | Choice |
| --- | --- |
| Framework | Next.js 16.2.11 with the App Router |
| Language | TypeScript |
| UI | React 19.2.4, Tailwind CSS 4 |
| Linting | ESLint 9 with `eslint-config-next` |
| Package manager | npm (`package-lock.json` is committed) |

## Repository Map

| Path | Responsibility |
| --- | --- |
| `app/layout.tsx` | Root layout, global fonts, and document metadata |
| `app/page.tsx` | Current home route; still starter content |
| `app/globals.css` | Global styles and Tailwind theme variables |
| `public/` | Static assets; currently starter assets only |
| `package.json` | Dependencies and project commands |
| `AGENTS.md` | Instructions for agents working with this Next.js version |

## Local Development

```bash
npm run dev
npm run lint
npm run build
npm run start
```

The development server runs at `http://localhost:3000` by default.

## Product Scope

The repository name establishes an inventory management dashboard, but detailed requirements have not yet been defined. The following areas are expected candidates, not committed functionality:

- Dashboard metrics and operational summaries
- Product and stock-level management
- Inventory adjustments and movement history
- Low-stock alerts and replenishment workflows
- Search, filtering, and reporting
- User roles and access control

## Open Decisions

- Define the initial users and the core workflows they must complete.
- Choose a persistence layer and hosting environment.
- Define the product, inventory, supplier, location, and transaction data models.
- Decide authentication, authorization, and audit-log requirements.
- Establish testing strategy, CI, and deployment process.
- Replace the starter page, assets, and metadata with product-specific content.

## Architecture Status

No API routes, database integration, authentication, domain model, reusable feature components, or automated tests have been added. Until requirements are set, keep the implementation simple and organize new code by feature as the application grows.

## Change Log

| Date | Change |
| --- | --- |
| 2026-07-24 | Created this living project document from the initial repository state. |
