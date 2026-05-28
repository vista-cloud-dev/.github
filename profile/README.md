# vista-cloud-dev

Modernizing **VistA-M development on InterSystems IRIS** — a git-first dev
bridge, a cross-engine `m` CLI / Go toolchain, and the VA modernization strategy
that frames them.

## Start here

- **[workspace](https://github.com/vista-cloud-dev/workspace)** — coordination
  hub: clone-all manifest, new-machine bootstrap, multi-repo sync helper.
- **[docs](https://github.com/vista-cloud-dev/docs)** — the design/strategy
  corpus (specs, ADRs, dependency maps), validated in CI.

## Repos

| Repo | What it is |
|------|------------|
| [docs](https://github.com/vista-cloud-dev/docs) | Design/strategy corpus. |
| [doc-framework](https://github.com/vista-cloud-dev/doc-framework) | Doc-corpus standard + validator. |
| [go-cli-template](https://github.com/vista-cloud-dev/go-cli-template) | Shared Go CLI scaffold. |
| [irissync](https://github.com/vista-cloud-dev/irissync) | IRIS source-sync binary — owner of the IRIS source boundary. |
| [vista-iris](https://github.com/vista-cloud-dev/vista-iris) | VistA-on-IRIS container build. |
| [workspace](https://github.com/vista-cloud-dev/workspace) | Cross-repo scripts + manifest. |

## Shared CI

Go repos call the reusable workflow in this repo:
`uses: vista-cloud-dev/.github/.github/workflows/go-ci.yml@main`.
