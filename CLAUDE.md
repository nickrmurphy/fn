# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

- `bun install` - Install dependencies
- `bun run index.ts` - Run the main entry point  
- `bun test` - Run all tests
- `bun test lib/[module].test.ts` - Run specific module tests (e.g., `bun test lib/option.test.ts`)
- `bun run check` - Run linting and formatting checks with auto-fix

## Architecture

This is a functional programming utility library with three core modules:

- **Option** (`lib/option.ts`) - Handles nullable values with tagged union types `Some<T>` and `None`
- **Result** (`lib/result.ts`) - Type-safe error handling with `Ok<T>` and `Err<E>` 
- **Chain** (`lib/chain.ts`) - Method chaining utility with `pipe`, `tap`, and `get` operations

The library uses tagged union patterns for type safety and exports all utilities from `index.ts`. Test files are co-located with source files in the `lib/` directory.

## Development Notes

- Uses Bun runtime exclusively (not Node.js)
- ESM-only project with strict TypeScript configuration
- Tests use `bun:test` framework, not vitest
- Code style: tabs for indentation, double quotes, Biome formatting
- TypeScript target is ESNext with bundler module resolution