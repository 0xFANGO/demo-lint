# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

React + TypeScript + Vite starter project with ESLint, Prettier, and Husky git hooks configured.

## Development Commands

```bash
# Start development server with HMR
pnpm dev

# Build for production (runs TypeScript compiler + Vite build)
pnpm build

# Run ESLint on all files
pnpm lint

# Preview production build
pnpm preview
```

## Code Quality Tools

### ESLint Configuration
- Uses flat config format (`eslint.config.js`)
- Configured for TypeScript with `typescript-eslint`
- React Hooks rules enabled via `eslint-plugin-react-hooks`
- React Refresh rules for Vite via `eslint-plugin-react-refresh`
- Custom rule: enforces single quotes

### Prettier
- Configuration in `.prettierrc`
- Automatically formats code

### Git Hooks (Husky)
- **pre-commit**: Runs `lint-staged` to auto-fix ESLint issues on staged files
- **commit-msg**: Validates commit messages using commitlint with conventional commits format

### Commitlint
- Uses `@commitlint/config-conventional`
- Enforces conventional commit format (e.g., `feat:`, `fix:`, `chore:`)

## TypeScript Configuration

Project uses TypeScript project references:
- `tsconfig.json` - Root config with references
- `tsconfig.app.json` - Application code config
- `tsconfig.node.json` - Node/build tooling config

## Architecture

Standard Vite + React setup:
- Entry point: `src/main.tsx`
- Root component: `src/App.tsx`
- Vite config: `vite.config.ts` with React plugin
