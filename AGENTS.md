# Agent guide — tool-compile-sexp

S-expression compiler for `Term` arrow graphs — `tool-compile-*`
compiler-backend family member: consumes Handl `Term` arrow terms and
emits s-expression source. Rust 2024.

## Layout

| path | role |
| --- | --- |
| `modules/compile-sexp/` | the crate — `handl-plugin-compile-sexp` (`src/lib.rs`, `compiler.rs`, `config.rs`, `output.rs`) |
| `xtask/` | vendored repo gate |
| `workflows/gate.yaml`, `bupha.toml`, `.cargo/` | CI wiring + `cargo xtask` alias |

## Contract

- Virtual-workspace root `Cargo.toml` (`members = ["modules/compile-sexp"]`);
  `[patch]` tables map `hnl-engine`/`handl-calculus`/`handl-plugin-compile`/
  `hnl-tool-codegen` git deps to sibling checkouts locally.
- Implements the `handl-plugin-compile` backend contract — Term in,
  s-expression text out.

## Verification

```bash
cargo xtask gate   # run at the workspace root
```


<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
