# Setup Guide

> Detailed setup and configuration guide for the Inventory Management Dashboard.

---

## Prerequisites

Ensure the following are installed on your development machine:

| Requirement | Minimum Version | Installation Guide                                    |
| ----------- | --------------- | ----------------------------------------------------- |
| **Node.js** | 18.17+ (LTS)    | [nodejs.org](https://nodejs.org/)                     |
| **npm**     | 9+              | Included with Node.js                                 |
| **Git**     | 2.30+           | [git-scm.com](https://git-scm.com/)                   |
| **Editor**  | Any             | [VS Code](https://code.visualstudio.com/) recommended |

---

## Quick Start

### 1. Clone the Repository

```bash
git clone <repository-url>
cd inventory-management
```

### 2. Install Dependencies

```bash
npm install
```

This installs all production and development dependencies defined in `package.json`.

### 3. Start the Development Server

```bash
npm run dev
```

The application will be available at [http://localhost:3000](http://localhost:3000).

The development server supports:

- **Hot Module Replacement (HMR)** — Changes to React components are reflected instantly
- **Fast Refresh** — Preserves component state during edits
- **TypeScript type checking** — Errors appear in the terminal and browser overlay

---

## Available Commands

| Command         | Description                                          |
| --------------- | ---------------------------------------------------- |
| `npm run dev`   | Start the development server with HMR                |
| `npm run build` | Build the application for production                 |
| `npm run start` | Start the production server (requires `build` first) |
| `npm run lint`  | Run ESLint across the codebase                       |

---

## Project Configuration Files

| File                 | Purpose                                                   |
| -------------------- | --------------------------------------------------------- |
| `next.config.ts`     | Next.js configuration (image domains, redirects, headers) |
| `tsconfig.json`      | TypeScript compiler options and path aliases              |
| `eslint.config.mjs`  | ESLint rules and plugins                                  |
| `postcss.config.mjs` | PostCSS configuration for Tailwind CSS processing         |
| `tailwind.config.ts` | Tailwind CSS theme customization (future)                 |

### Path Aliases

TypeScript is configured with the `@` path alias mapping to the project root:

```typescript
// Instead of:
import { Button } from "../../../components/ui/Button";

// Use:
import { Button } from "@/components/ui/Button";
```

---

## Environment Variables

Create a `.env.local` file in the project root for local environment variables:

```bash
# .env.local

# Application
NEXT_PUBLIC_APP_URL=http://localhost:3000

# Database (future)
# DATABASE_URL=postgresql://user:password@localhost:5432/inventory

# Authentication (future)
# AUTH_SECRET=your-secret-key
# AUTH_URL=http://localhost:3000
```

> Environment variables prefixed with `NEXT_PUBLIC_` are exposed to the browser. All others are server-side only.

---

## Editor Setup

### VS Code (Recommended)

Install the following extensions for the best development experience:

- **Tailwind CSS IntelliSense** — Autocomplete, hover previews, and linting for Tailwind
- **ESLint** — Inline linting and auto-fix on save
- **Prettier** — Code formatting (optional, project may use ESLint for formatting)

### Recommended VS Code Settings

Create `.vscode/settings.json` in the project root:

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  },
  "typescript.tsdk": "node_modules/typescript/lib",
  "typescript.enablePromptUseWorkspaceTsdk": true,
  "tailwindCSS.experimental.classRegex": [],
  "files.associations": {
    "*.css": "tailwindcss"
  }
}
```

---

## Browser Support

The application targets modern browsers:

- Chrome 100+
- Firefox 100+
- Safari 15+
- Edge 100+

---

## Troubleshooting

### Common Issues

| Issue                         | Solution                                             |
| ----------------------------- | ---------------------------------------------------- |
| `npm install` fails           | Clear npm cache: `npm cache clean --force` and retry |
| Port 3000 is in use           | Kill the process or use `npm run dev -- -p 3001`     |
| TypeScript errors after pull  | Run `npm install` to update dependencies             |
| Tailwind classes not applying | Ensure `@import "tailwindcss"` is in `globals.css`   |
| ESLint errors on save         | Check `eslint.config.mjs` for rule configuration     |

### Getting Help

- Check the [Next.js documentation](https://nextjs.org/docs)
- Review [PROJECT.md](./PROJECT.md) for project-specific decisions
- Open an issue in the repository

---

## Production Build

### Build the Application

```bash
npm run build
```

The output is generated in the `.next` directory.

### Start the Production Server

```bash
npm run start
```

### Deployment

The application can be deployed to:

- **Vercel** (recommended) — Zero-config deployment for Next.js
- **Self-hosted** — Node.js server with the production build
- **Docker** — Containerized deployment (future)

---

## Change Log

| Date       | Change                      |
| ---------- | --------------------------- |
| 2026-07-24 | Initial setup guide created |
