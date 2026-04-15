# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Deno-based skill/plugin for Claude Code's claudikins-kernel system. It is in early stages with minimal functionality.

## Commands

```bash
# Run the main module
deno run main.ts

# Run with file watching (development)
deno task dev

# Run tests
deno test

# Run a specific test file
deno test main_test.ts
```

## Architecture

- **Runtime**: Deno (not Node.js)
- **Dependencies**: JSR-managed via `jsr:@std/assert@1` for testing
- **Entry point**: `main.ts` exports an `add(a, b)` function
- **Tests**: `main_test.ts` uses `@std/assert`

## Deno-Specific Notes

- Use `deno.json` for task configuration and imports
- Use `deno fmt` and `deno lint` for formatting and linting after edits
- JSR imports use the `jsr:` prefix (e.g., `jsr:@std/assert@1`)
- Permissions are granted explicitly at runtime (no `node_modules` or npm)
