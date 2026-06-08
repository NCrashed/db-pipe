# db-pipe

A pipe-like wrapper around [`sqlite-simple`](https://hackage.haskell.org/package/sqlite-simple).

## What it does

`db-pipe` wraps `sqlite-simple` in a small monadic pipe abstraction.
A long-lived `DBPipeEnv` owns a connection, a transaction handle,
and a couple of STM channels; individual queries run inside a
`DBPipeM` monad that batches `select`, `update`, `insert`, and
`ddl` statements into explicit transactional blocks
(`transactional`, `transactional_`, `commitAll`).

## Where it came from

Originally written by Dmitry Zuykov (voidlizard) inside the
[`hbs2`](https://github.com/NCrashed/hbs2) project. This Hackage
release is published from `github.com/NCrashed/db-pipe` so
downstream projects can depend on it without vendoring.

## License

BSD-3-Clause; see `LICENSE`. Copyright holders are listed in the
cabal file.
