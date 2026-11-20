# compile-sexp

S-expression compiler for `Term` arrow graphs — part of the `compile-*`
compiler-backend family: consumes Handl `Term` arrow terms and emits
s-expression source.

The crate lives in `modules/compile-sexp` inside this workspace.

## Development

```bash
cargo xtask gate        # fmt --check → clippy -D warnings → test → doc
```

`cargo xtask` wraps the repo's `xtask/` crate (`fmt`, `clippy`, `test`, `doc`,
`check`, `gate`); `ci.sh` is the gate entry. Deps resolve from git, so no
sibling checkouts are needed; a plain clone test-runs as-is.

## License

MIT.
