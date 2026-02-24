# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is an Nx monorepo workspace (`@org/source`) configured for publishing TypeScript libraries. The `packages/` directory is where all library packages live. It is currently empty — packages are generated via Nx generators.

Nx Cloud is configured for remote caching and distributed task execution (`nxCloudId` in `nx.json`).

## Common Commands

```sh
# Install dependencies
npm ci

# Generate a new publishable library
npx nx g @nx/js:lib packages/<name> --publishable --importPath=@org/<name>

# Build a specific package
npx nx build <project-name>

# Run all lint, test, build, and typecheck across all projects
npx nx run-many -t lint test build typecheck

# Run a single target for a specific project
npx nx <target> <project-name>

# Run tests for a single project
npx nx test <project-name>

# Typecheck a project
npx nx typecheck <project-name>

# Check code formatting
npx nx format:check

# Fix code formatting
npx nx format:write

# Sync TypeScript project references
npx nx sync

# Visualize project graph
npx nx graph

# Version and release packages
npx nx release
npx nx release --dry-run
```

## Architecture

- **Monorepo tool**: Nx 22 with the `@nx/js/typescript` plugin, which auto-infers `build`, `typecheck`, `build-deps`, and `watch-deps` targets from `tsconfig.lib.json` files in each package.
- **Package location**: All libraries live under `packages/` and are referenced via npm workspaces (`"workspaces": ["packages/*"]`).
- **TypeScript**: Strict mode with `nodenext` module resolution, `es2022` target, and `emitDeclarationOnly`. The custom condition `@org/source` is set in `tsconfig.base.json` for package exports resolution during development.
- **Project references**: `tsconfig.json` at the root uses TypeScript project references. Nx keeps these in sync automatically when running `build` or `typecheck`. Run `npx nx sync` to update them manually.
- **CI**: GitHub Actions runs `lint test build typecheck e2e-ci` via `npx nx run-many`, with Nx Cloud distributing tasks across 3 agents.

## Adding a New Package

1. Generate: `npx nx g @nx/js:lib packages/<name> --publishable --importPath=@org/<name>`
2. The generator creates `packages/<name>/` with `src/`, `tsconfig.lib.json`, `project.json`, and `package.json`.
3. Nx will infer build/typecheck targets automatically from the tsconfig.
