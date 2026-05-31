# Contributing to vista-cloud-dev

Thanks for your interest. This file holds the org-wide defaults; an individual
repository may add its own `CONTRIBUTING.md` with specifics that take
precedence.

## Getting set up

1. Clone the whole org with the coordination hub:
   [`workspace`](https://github.com/vista-cloud-dev/workspace) — run
   `./bootstrap.sh` to clone every repo and check out the right branches.
2. Read [`docs`](https://github.com/vista-cloud-dev/docs) for the *why* — the
   modernization strategy, the `m-cli` spec, and the toolchain dependency map.

## Ground rules

- **Discuss first for anything non-trivial.** Open an issue describing the
  problem before a large PR, so we can agree on the approach.
- **Keep changes focused.** One logical change per pull request.
- **Match the surrounding code.** These repos share conventions (the `clikit`
  CLI grammar, the doc-framework document standard, the m-cli M style); follow
  the idiom already in the file you are editing.

## Tests are required

Both toolchains are **test-first**:

- **Go repos** — `make test` (and `make lint`) must pass; new behavior needs new
  tests. CI runs lint + race tests + the `schema` contract + a cross-compile
  matrix via the shared workflow.
- **M repos** — write the `*TST.m` test first, confirm it fails, then implement.
  Tests run through `m test` against `^STDASSERT`; keep per-module coverage at
  or above the documented gate (`m coverage --min-percent=85`).

Run the repo's `make check` (or equivalent) before opening a PR.

## Pull requests

- Target `main` unless the repo's README says otherwise.
- Fill out the pull request template.
- Ensure CI is green. Reviews focus on correctness, the public contract
  (command grammar / JSON envelope / exit codes), and test coverage.

## Licensing of contributions

By contributing, you agree your contributions are licensed under
**Apache-2.0** (the org default; see [`LICENSE`](LICENSE) and [`NOTICE`](NOTICE)).
The only exceptions are the deliberately isolated ones noted in `NOTICE` (the
MIT VS Code extensions and the AGPL-derived embedded grammar artifact in
`m-parse`). Do not introduce new third-party code under copyleft licenses into
an otherwise Apache-2.0 repository without flagging it in the PR.

## Code of conduct

Participation is governed by our [Code of Conduct](CODE_OF_CONDUCT.md).
