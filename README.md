## Purpose

To simplify `cargo check`, `cargo check --tests --benches`, `cargo test` for all `camigo`-related
repositories.

This may work well only on OS's & filesystems that support symlinks.

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

Then run `cargo check`, `cargo check --tests --benches`, `cargo test`... in this workspace
(`camigo-workspace`).
