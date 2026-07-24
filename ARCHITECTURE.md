# Architecture Overview

> Technical architecture and design decisions for the Inventory Management Dashboard.

---

## Architecture Principles

- **Feature-based organization** — Code is grouped by domain feature (products, inventory, reports, etc.) as the application grows, keeping related components, hooks, and utilities co-located.
- **App Router conventions** — Uses Next.js App Router for routing, layouts, loading states, and error boundaries.
- **Server Components by default** — Leverage React Server Components for data fetching and rendering where possible, minimizing client-side JavaScript.
- **TypeScript throughout** — Full type coverage across the codebase for safety and developer experience.
- **Progressive enhancement** — Start simple; add complexity (state management, caching, authentication) only when requirements are concrete.

---

## Technology Stack

| Layer           | Technology                      | Purpose                                        |
| --------------- | ------------------------------- | ---------------------------------------------- |
| Framework       | Next.js 16.2.11                 | Full-stack React framework with SSR/SSR        |
| Rendering       | App Router                      | File-based routing, layouts, server components |
| Language        | TypeScript 5                    | Type safety, tooling, IDE support              |
| UI Library      | React 19.2.4                    | Component-based UI architecture                |
| Styling         | Tailwind CSS 4                  | Utility-first CSS, design system primitives    |
| Linting         | ESLint 9 + `eslint-config-next` | Code quality and consistency                   |
| Package Manager | npm                             | Dependency management                          |

---

## Directory Structure

```
inventory-management/
├── app/                          # Next.js App Router
│   ├── layout.tsx                # Root layout (fonts, metadata, global providers)
│   ├── page.tsx                  # Home / dashboard route
│   ├── globals.css               # Global styles + Tailwind theme
│   ├── (auth)/                   # Auth-related routes (future)
│   ├── (dashboard)/              # Dashboard routes (future)
│   │   ├── layout.tsx            # Shared dashboard layout
│   │   ├── page.tsx              # Dashboard home
│   │   ├── products/             # Product management feature (future)
│   │   ├── inventory/            # Stock management feature (future)
│   │   └── reports/              # Reporting feature (future)
│   └── api/                      # API route handlers (future)
├── components/                   # Shared UI components (future)
│   ├── ui/                       # Primitive UI components (buttons, inputs, cards)
│   └── features/                 # Feature-specific components (future)
├── lib/                          # Core utilities and shared logic (future)
│   ├── db/                       # Database client and schema (future)
│   ├── auth/                     # Authentication utilities (future)
│   └── utils/                    # General utility functions (future)
├── public/                       # Static assets
├── types/                        # Shared TypeScript type definitions (future)
└── docs/                         # Documentation (future)
```

> Current structure is minimal. Directories marked "(future)" represent planned organization as features are implemented.

---

## Routing Architecture

The App Router provides the following routing capabilities:

| Route Pattern          | Purpose                       | Status   |
| ---------------------- | ----------------------------- | -------- |
| `/`                    | Dashboard home / landing      | Scaffold |
| `/products`            | Product list and management   | Planned  |
| `/products/[id]`       | Individual product details    | Planned  |
| `/inventory`           | Stock overview                | Planned  |
| `/inventory/movements` | Stock adjustment history      | Planned  |
| `/reports`             | Reporting dashboard           | Planned  |
| `/settings`            | User and application settings | Planned  |
| `/api/*`               | REST API endpoints            | Planned  |

---

## Data Flow

```
Browser Request
      │
      ▼
Next.js Server
      │
      ├── Server Components (data fetching, rendering)
      │         │
      │         ▼
      │    Data Layer (DB / API / Cache)
      │
      └── Client Components (interactivity, state)
                │
                ▼
           User Actions → API Routes → Data Layer → Response
```

---

## State Management Strategy

| State Type   | Approach                                    |
| ------------ | ------------------------------------------- |
| Server State | Server Components with async data fetching  |
| URL State    | Search params, route segments               |
| Form State   | React `useActionState` / controlled inputs  |
| Client State | React hooks (`useState`, `useReducer`)      |
| Global State | React Context (minimal, for auth/ui themes) |

> No external state management library is introduced until concrete requirements justify the need.

---

## Styling Architecture

- **Tailwind CSS 4** provides utility classes for rapid UI development
- **CSS variables** define the design token system (`--color-background`, `--font-sans`, etc.)
- **Geist font** from Vercel via `next/font` for optimized typography
- **Dark mode** support via `prefers-color-scheme` media query (to be made toggleable)

---

## Security Considerations

- **Authentication**: To be determined — likely NextAuth.js or a custom JWT solution
- **Authorization**: Role-based access control (RBAC) for different user types
- **API Security**: Input validation, rate limiting, CSRF protection
- **Data Validation**: Zod schemas for runtime type checking

---

## Performance Considerations

- **Server Components** for data-heavy pages to minimize client JS
- **Streaming** with Suspense boundaries for progressive loading
- **Image optimization** via `next/image` for static assets
- **Route prefetching** via Next.js Link component
- **Code splitting** at route level via App Router

---

## Future Architecture Decisions

The following decisions are deferred until concrete requirements are established:

1. **Persistence Layer** — Database choice (PostgreSQL, SQLite, etc.) and ORM (Prisma, Drizzle, etc.)
2. **Authentication Provider** — NextAuth.js, Clerk, or custom solution
3. **Hosting Environment** — Vercel, self-hosted, or alternative
4. **Testing Strategy** — Framework (Vitest, Playwright, etc.) and coverage targets
5. **CI/CD Pipeline** — GitHub Actions or alternative
6. **Monitoring & Logging** — Error tracking, performance monitoring

---

## Change Log

| Date       | Change                                |
| ---------- | ------------------------------------- |
| 2026-07-24 | Initial architecture document created |
