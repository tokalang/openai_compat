# `official/openai_compat` 0.1.1 release gate

Status: pending first registry-eligible standalone public release

`v0.1.0` is retained as a non-registry source snapshot. Its archive was made
with `git archive`, which does not satisfy Toka's package-root archive layout.
It has no catalog record and must not be installed. `v0.1.1` is the first
registry-eligible standalone release; there is no earlier monorepo archive or
catalog record to preserve.

## Required evidence

Before publishing the tag and release asset:

1. `package.tk` names version `0.1.1`, identity `official/openai_compat`, and
   the Apache-2.0 license.
2. `TOKA_ROOT=/path/to/toka python3 tests/qualify_package.py` passes from a
   clean standalone checkout.
3. The `Package qualification` workflow passes on Linux x64 and macOS arm64.
4. `toka publish` creates `openai_compat-0.1.1.tar.gz` from the immutable
   `v0.1.1` tag, and its downloaded SHA-256 digest is recorded.
5. The static registry entry names that exact archive URL, digest, source
   repository, and tag.
6. A fresh consumer resolves `official/openai_compat@0.1.0` from the public
   registry, then repeats `toka fetch` and `toka build` with `TOKA_OFFLINE=1`.

The published catalog version and release asset are immutable. Any correction
after release requires a new SemVer version.
