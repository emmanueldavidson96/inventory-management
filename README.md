# Inventory Management Dashboard

A modern, full-featured inventory management dashboard built with **Next.js 16**, **React 19**, and **Tailwind CSS 4**. This application provides a comprehensive solution for tracking products, managing stock levels, monitoring inventory movements, and generating operational insights.

> **Current Stage:** Initial application scaffold. The project is in early development with the default Next.js starter content on the home page. See [PROJECT.md](./PROJECT.md) for the living project document.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Available Scripts](#available-scripts)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- **Dashboard Metrics** — Real-time operational summaries and KPIs
- **Product Management** — CRUD operations for products with categories, SKUs, and attributes
- **Stock Control** — Track inventory levels across multiple locations
- **Inventory Movements** — Record and view stock adjustments, transfers, and history
- **Low-Stock Alerts** — Automated notifications for replenishment needs
- **Search & Filtering** — Powerful search and filter capabilities across all data
- **Reporting** — Generate and export inventory reports
- **User Roles & Access Control** — Role-based permissions for secure operations

> ⚠️ Feature list represents planned scope. Implementation is in progress.

---

## Tech Stack

| Area                | Technology                                                |
| ------------------- | --------------------------------------------------------- |
| **Framework**       | [Next.js](https://nextjs.org/) 16.2.11 (App Router)       |
| **Language**        | [TypeScript](https://www.typescriptlang.org/) 5           |
| **UI Library**      | [React](https://react.dev/) 19.2.4                        |
| **Styling**         | [Tailwind CSS](https://tailwindcss.com/) 4                |
| **Linting**         | [ESLint](https://eslint.org/) 9 with `eslint-config-next` |
| **Package Manager** | npm                                                       |

---

## Getting Started

### Prerequisites

- **Node.js** 18.17 or later (LTS recommended)
- **npm** (included with Node.js)

### Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd inventory-management
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Start the development server**

   ```bash
   npm run dev
   ```

4. **Open the application**

   Navigate to [http://localhost:3000](http://localhost:3000) in your browser.

---

## Project Structure

```
inventory-management/
├── app/                    # Next.js App Router pages and layouts
│   ├── favicon.ico         # Browser tab icon
│   ├── globals.css         # Global styles and Tailwind theme variables
│   ├── layout.tsx          # Root layout with fonts and metadata
│   └── page.tsx            # Home page (currently starter content)
├── public/                 # Static assets (images, icons, etc.)
│   ├── file.svg
│   ├── globe.svg
│   ├── next.svg
│   ├── vercel.svg
│   └── window.svg
├── .gitignore              # Git ignore rules
├── AGENTS.md               # Instructions for AI agents working with this project
├── CLAUDE.md               # Claude-specific agent configuration
├── eslint.config.mjs       # ESLint configuration
├── next.config.ts          # Next.js configuration
├── package.json            # Dependencies and scripts
├── postcss.config.mjs      # PostCSS configuration (Tailwind)
├── PROJECT.md              # Living project document (scope, decisions, status)
├── README.md               # This file
└── tsconfig.json           # TypeScript configuration
```

---

## Available Scripts

| Command         | Description                               |
| --------------- | ----------------------------------------- |
| `npm run dev`   | Start the development server on port 3000 |
| `npm run build` | Build the application for production      |
| `npm run start` | Start the production server               |
| `npm run lint`  | Run ESLint to check code quality          |

---

## Documentation

| Document                             | Description                                            |
| ------------------------------------ | ------------------------------------------------------ |
| [PROJECT.md](./PROJECT.md)           | Living project document — scope, decisions, and status |
| [AGENTS.md](./AGENTS.md)             | Guidelines for AI agents working with this codebase    |
| [ARCHITECTURE.md](./ARCHITECTURE.md) | Technical architecture and design decisions            |
| [SETUP.md](./SETUP.md)               | Detailed setup and configuration guide                 |
| [CONTRIBUTING.md](./CONTRIBUTING.md) | Contribution guidelines and workflow                   |

---

## Contributing

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

---

## License

This project is private and proprietary. All rights reserved.
