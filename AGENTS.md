# Repository Guidelines

## Project Structure & Module Organization

T3MP3ST is a TypeScript security-testing platform. `src/cli.ts`, `src/server.ts`, and `src/mcp-server.ts` provide CLI, HTTP, and MCP entry points. Feature modules include `src/arsenal/` (tools/parsers), `src/mission/`, `src/evidence/`, and `src/llm/`; shared contracts live in `src/types/`, prompt packs in `src/resources/`. Tests live in `src/__tests__/`; supporting checks in `scripts/`. `docs/` contains guides and UI assets; `docsite/` contains generated documentation. `examples/`, `bench/`, and `ctf/` hold demo missions, benchmarks, and isolated labs. Builds output to `dist/`.

## Build, Test, and Development Commands

Use Node.js >=22.19.0 and install dependencies with `npm ci`.

- `npm run dev`: run the CLI directly from TypeScript.
- `npm run server`: start the local HTTP API and UI.
- `npm run build`: compile TypeScript into `dist/`; `npm start` runs the built CLI.
- `npm run test:pr`: run ESLint, type checking, tests, and diagnostics before requesting review.
- `npm run test:watch`: run Vitest interactively during development.
- `npm run docs:check`: regenerate, build, and verify documentation artifacts.

## Coding Style & Naming Conventions

Follow surrounding TypeScript style: two-space indentation, single quotes, semicolons, camelCase functions/variables, and PascalCase types/classes. Use descriptive kebab-case filenames. Preserve ESM imports with `.js` suffixes and strict typing. Prefer `const`; avoid `any` and non-null assertions. ESLint provides linting; no dedicated formatter is configured.

## Testing Guidelines

Add outcome-oriented regression tests for behavior changes, named `src/__tests__/<feature>.test.ts`. Run focused tests with `npx vitest run src/__tests__/parsers.test.ts`. PRs require at least 50% changed executable-line coverage (`npm run test:pr-coverage`); documentation-only changes may explain why coverage is inapplicable. `npm run test:coverage` enforces 100% per-file coverage for the three configured recon parsing modules. Include risk-specific checks where relevant.

## Commit & Pull Request Guidelines

History follows prefixes such as `feat(arsenal):`, `fix:`, `docs:`, and `chore:`. Use focused branches targeting `main`; published review history must not be force-pushed. Complete `.github/pull_request_template.md`: explain the change, link its issue, credit prior work, record verification, and describe risk/rollback. Follow `CONTRIBUTING.md` and `docs/PULL_REQUEST_DELIVERY.md`; merges require green CI on the exact head. Maintainer courtesy cleanup follows `AGENTS.override.md`.

## Security & Configuration

Configure local keys using `.env.example`; never commit secrets. Preserve scope, approval, redaction, and evidence boundaries. Include contribution receipts for operational changes; report vulnerabilities through `SECURITY.md`.
