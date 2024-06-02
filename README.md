## Purpose

To simplify `cargo check`, `cargo check --tests --benches`, `cargo test` for all `cami`-related
repositories.

This itself is not a Rust crate (and is not published on crates.io).

## Limitation: symlinks

This Rust workspace does not contain its members (crates). It refers to them through symlinks. So
this needs on OS & filesystem that support symlinks.

You'll need to `git clone` all related repositories into neighbor directories (next to the clone of
this `cami-workspace`):

- [cami](https://github.com/cami-rs/cami)
- [cami-helpers](https://github.com/cami-rs/cami-helpers)
- [cami-helpers-tests](https://github.com/cami-rs/cami-helpers-tests)

So the directory subtree should look like:

```
|
|-- some-common-immediate-parent
|   |
|   |-- ...
|   |-- cami-workspace
|   |-- cami
|   |-- cami-helpers
|   |-- cami-helpers-testers
|   |-- ...
```

Then run `cargo check`, `cargo check --tests --benches`, `cargo test`, `cargo bench`... in this
workspace (right under `cami-workspace/`).

<!--
## GIT ergonomics

Suggest you install [mgitstatus](https://github.com/fboender/multi-git-status). Then run the
following in a directory one level above the clones of those repos (e.g.
`some-common-immediate-parent/`): `mgitstatus cami*`, or `mgitstatus -e cami*` to exclude ones
that are 'ok'.
-->
