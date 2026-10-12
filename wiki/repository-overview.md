# Repository Overview

[Back to wiki](README.md)

## Purpose

TEMPEST, branded T3MP3ST, is a self-hosted framework for coordinating AI agents through authorized security testing. It supplies mission planning, tools, execution controls, and evidence collection around a chosen model or local coding agent.

The application can run in Docker. Its browser interface is called the **War Room**.

## Main Pieces

| Component | Purpose |
|---|---|
| Operator interfaces | A CLI, browser War Room backed by an Express API, MCP server, and TypeScript SDK. |
| Mission orchestration | Targets, rules of engagement, task queues, and specialized operators that carry out parts of an investigation. |
| Arsenal | Built-in tools and external adapters, with parsers that convert tool output into structured findings. |
| Evidence and authority controls | Scope checks, approvals, redaction, provenance, and retesting to support findings with observable evidence. |
| Evaluation infrastructure | Benchmark harnesses, isolated CTF labs, fixtures, and committed results used to reproduce published claims. |

## Implementation

The project uses TypeScript with ESM, npm, ESLint, and Vitest. Runtime code lives mainly in `src/`; `scripts/` contains substantial verification and benchmark logic. `docs/` holds guides and the browser UI.

## Capability Maturity

The documentation presents web testing and CTF workflows as established. Several cloud, mobile, binary, and later-stage operator capabilities remain experimental or scaffolded. A displayed phase or available target category does not establish that every associated capability is implemented.

## Contribution Expectations

Contributions should be focused, include regression coverage for behavior changes, credit adapted work, and pass CI on the exact commit being merged.

## Basis of This Introduction

This overview comes from documentation and selected source files. The walkthrough has not yet run a mission, verified benchmark claims, or checked the deployed Docker image against this checkout.

Sources: [README](../README.md), [Developer Guide](../docs/DEVELOPER_GUIDE.md), [SDK entry point](../src/index.ts), and [Contributing](../CONTRIBUTING.md).
