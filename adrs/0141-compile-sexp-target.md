# ADR-0141: `compile-sexp` target

## Context

[ADR-0114](../0114-handl-compile-plugin-architecture.md) states the compile
port (`Compiler` / `CompilerRegistry`). S-expression emission over `Term`
arrow graphs is one target, not platform machinery.

## Decision

`sexp` owns the S-expression compiler: `handl-plugin-compile-sexp` (target
`sexp`) — here as `modules/compile-sexp`.

`host` keeps the port and the registry seam.

## Consequences

- The `sexp` target name is preserved (repo ≠ target).
- Like the other `Term`-reading targets, it depends on the `Term` shape fixed
  by `term`, not on a specific consumer.

## Status

Accepted — extracted in ADR-0128 Phase 7.
