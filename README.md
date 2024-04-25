## Purpose

To simplify `cargo check`, `cargo check --tests --benches`, `cargo test` for all `camigo`-related
repositories.

## Limitation: symlinks

This Rust workspace does not contain its members (crates). It refers to them through symlinks. So
this needs on OS & filesystem that support symlinks.

You'll need to `git clone` all related repositories into neighbor directories (next to the clone of
this `camigo-workspace`):

- [camigo](https://github.com/peter-kehl/camigo)
- [camigo-helpers](https://github.com/peter-kehl/camigo-helpers)
- [camigo-helpers-tests](https://github.com/peter-kehl/camigo-helpers-tests)

So the directory subtree should look like:

```
|
|-- some-common-immediate-parent
|   |
|   |-- ...
|   |-- camigo-workspace
|   |-- camigo
|   |-- camigo-helpers
|   |-- camigo-helpers-testers
|   |-- ...
```

Then run `cargo check`, `cargo check --tests --benches`, `cargo test`, `cargo bench`... in this
workspace (right under `camigo-workspace/`).

## GIT ergonomics

Suggest you install [mgitstatus](https://github.com/fboender/multi-git-status). Then run the
following in a directory one level above the clones of those repos (e.g.
`some-common-immediate-parent/`): `mgitstatus camigo*`, or `mgitstatus -e camigo*` to exclude ones
that are 'ok'.
