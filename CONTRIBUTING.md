# Contributing Guide

> Guidelines and workflow for contributing to the Inventory Management Dashboard.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Coding Standards](#coding-standards)
- [Commit Conventions](#commit-conventions)
- [Pull Request Process](#pull-request-process)
- [Code Review](#code-review)
- [Testing](#testing)
- [Documentation](#documentation)
- [Issue Reporting](#issue-reporting)

---

## Code of Conduct

This project is committed to providing a welcoming and inclusive experience for everyone. By participating, you agree to:

- Use welcoming and inclusive language
- Respect differing viewpoints and experiences
- Accept constructive criticism gracefully
- Focus on what is best for the community and project
- Show empathy towards other community members

---

## Getting Started

### Prerequisites

- Node.js 18.17+ (LTS recommended)
- npm 9+
- Git 2.30+

### Initial Setup

1. **Fork the repository** (if contributing from a fork)
2. **Clone your fork or the repository**

   ```bash
   git clone <repository-url>
   cd inventory-management
   ```

3. **Install dependencies**

   ```bash
   npm install
   ```

4. **Create a branch for your work**

   ```bash
   git checkout -b feat/your-feature-name
   ```

5. **Start the development server**

   ```bash
   npm run dev
   ```

---

## Development Workflow

### Branch Naming Convention

Use descriptive branch names that follow this pattern:

| Prefix      | Purpose                                     |
| ----------- | ------------------------------------------- |
| `feat/`     | New feature or enhancement                  |
| `fix/`      | Bug fix                                     |
| `refactor/` | Code refactoring without feature changes    |
| `docs/`     | Documentation updates                       |
| `chore/`    | Maintenance tasks, dependencies, tooling    |
| `style/`    | Code style changes (formatting, whitespace) |
| `test/`     | Adding or updating tests                    |

Examples:

- `feat/product-crud`
- `fix/stock-count-validation`
- `docs/api-endpoints`

### Development Cycle

1. **Pull latest changes** from the main branch
2. **Create a feature branch** from `main`
3. **Make your changes** following the coding standards
4. **Run linting** to ensure code quality
5. **Commit your changes** following commit conventions
6. **Push your branch** and open a pull request

---

## Coding Standards

### TypeScript

- **Strict mode** is enabled — avoid using `any` unless absolutely necessary
- Use explicit return types on public functions and components
- Prefer `interface` over `type` for object shapes
- Use `type` for unions, intersections, and utility types
- Use `const` assertions for literal types

### React / Next.js

- Prefer **Server Components** by default; use `"use client"` only when interactivity is needed
- Use the App Router conventions: `page.tsx`, `layout.tsx`, `loading.tsx`, `error.tsx`
- Keep components focused and single-responsibility
- Extract reusable logic into custom hooks
- Use `next/image` for all image assets

### Styling (Tailwind CSS)

- Use Tailwind utility classes directly in JSX
- Extract repeated patterns into reusable components, not custom CSS
- Use CSS variables for design tokens (defined in `globals.css`)
- Avoid inline styles unless dynamically computed

### File Organization

- One component per file, named after the component
- Co-locate tests, stories, and type definitions with their component
- Use barrel exports (`index.ts`) for public module interfaces

### Naming Conventions

| Element            | Convention              | Example               |
| ------------------ | ----------------------- | --------------------- |
| Components         | PascalCase              | `ProductCard.tsx`     |
| Hooks              | camelCase, `use` prefix | `useProducts.ts`      |
| Utilities          | camelCase               | `formatCurrency.ts`   |
| Types/Interfaces   | PascalCase              | `Product.ts`          |
| Files (components) | PascalCase              | `ProductCard.tsx`     |
| Files (utilities)  | camelCase               | `formatCurrency.ts`   |
| Directories        | kebab-case              | `product-management/` |
| CSS classes        | kebab-case              | `btn-primary`         |

---

## Commit Conventions

This project follows the [Conventional Commits](https://www.conventionalcommits.org/) specification.

### Format

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

### Types

| Type       | Usage                                   |
| ---------- | --------------------------------------- |
| `feat`     | A new feature                           |
| `fix`      | A bug fix                               |
| `docs`     | Documentation changes                   |
| `style`    | Code style changes (formatting, etc.)   |
| `refactor` | Code refactoring                        |
| `perf`     | Performance improvements                |
| `test`     | Adding or updating tests                |
| `chore`    | Maintenance, dependencies, build config |
| `ci`       | CI/CD configuration changes             |

### Examples

```
feat(products): add product creation form
fix(inventory): correct stock count calculation
docs(readme): update setup instructions
refactor(api): extract validation logic
chore(deps): upgrade next to 16.2.11
```

---

## Pull Request Process

### Before Submitting

1. Ensure your code builds without errors: `npm run build`
2. Run the linter and fix any issues: `npm run lint`
3. Write or update tests for your changes (when testing is established)
4. Update documentation if your changes affect the API, UI, or workflow
5. Rebase your branch on the latest `main` to resolve conflicts

### PR Template

When opening a pull request, include:

- **Description** — What does this PR do? Why is it needed?
- **Related Issues** — Link to any related issues or tickets
- **Screenshots** — For UI changes, include before/after screenshots
- **Testing** — How were the changes tested?
- **Checklist** — Confirm all items are addressed

### PR Checklist

- [ ] Code follows the project's coding standards
- [ ] Linting passes (`npm run lint`)
- [ ] Build succeeds (`npm run build`)
- [ ] Documentation has been updated
- [ ] No new warnings or errors introduced
- [ ] Changes are backward compatible (or breaking changes are documented)

---

## Code Review

### Review Process

1. At least one maintainer must approve the PR before merging
2. Address all review comments before requesting re-review
3. Keep PRs focused and reasonably sized (aim for < 400 lines changed)
4. Large features should be broken into smaller, incremental PRs

### What Reviewers Look For

- Correctness and completeness of the implementation
- Adherence to coding standards and conventions
- Test coverage and quality
- Performance implications
- Security considerations
- Documentation accuracy

---

## Testing

> Testing infrastructure is not yet established. This section will be updated when the testing strategy is defined.

### Planned Testing Approach

- **Unit Tests** — Vitest for individual functions and utilities
- **Component Tests** — React Testing Library for component behavior
- **Integration Tests** — API route and data flow testing
- **E2E Tests** — Playwright for critical user workflows

---

## Documentation

- Update `PROJECT.md` for any changes to scope, architecture, or decisions
- Update `README.md` for changes to setup, commands, or project overview
- Document new features, components, and API endpoints
- Use JSDoc comments for exported functions and complex logic
- Keep the change log in each document up to date

---

## Issue Reporting

### Bug Reports

When reporting a bug, include:

- **Description** — Clear and concise description of the bug
- **Steps to Reproduce** — Minimal, complete steps to reproduce
- **Expected Behavior** — What should happen
- **Actual Behavior** — What actually happens
- **Environment** — Browser, OS, Node.js version, etc.
- **Screenshots** — If applicable

### Feature Requests

When requesting a feature, include:

- **Problem Statement** — What problem does this solve?
- **Proposed Solution** — How should it work?
- **Alternatives Considered** — Any alternative approaches
- **Additional Context** — Any other relevant information

---

## Change Log

| Date       | Change                             |
| ---------- | ---------------------------------- |
| 2026-07-24 | Initial contributing guide created |
