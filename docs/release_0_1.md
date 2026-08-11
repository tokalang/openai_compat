# `official/openai_compat` 0.1.1 release gate

Status: complete on 2026-08-11

`v0.1.0` is retained as a non-registry source snapshot. Its archive was made
with `git archive`, which does not satisfy Toka's package-root archive layout.
It has no catalog record and must not be installed. `v0.1.1` is the first
registry-eligible standalone release; there is no earlier monorepo archive or
catalog record to preserve.

## Release evidence

1. `package.tk` names version `0.1.1`, identity `official/openai_compat`, and
   the Apache-2.0 license.
2. `TOKA_ROOT=/path/to/toka python3 tests/qualify_package.py` passed from a
   clean standalone checkout. The
   [`Package qualification` workflow](https://github.com/tokalang/openai_compat/actions/runs/31458132229)
   passed on Linux x64 and macOS arm64.
3. `toka publish` created
   [`openai_compat-0.1.1.tar.gz`](https://github.com/tokalang/openai_compat/releases/download/v0.1.1/openai_compat-0.1.1.tar.gz)
   from the immutable [`v0.1.1`](https://github.com/tokalang/openai_compat/releases/tag/v0.1.1)
   tag. Its downloaded SHA-256 is
   `8c3d139e0a4147f0f6bfcc73da623a5eeac670543af86468350c27fb5c13a457`.
4. The static registry entry names that exact archive URL, digest, source
   repository, and tag.
5. A fresh consumer resolved `official/openai_compat@0.1.1` from the public
   registry, then repeated `toka fetch` and `toka build` with `TOKA_OFFLINE=1`.

The published catalog version and release asset are immutable. Any correction
after release requires a new SemVer version.
