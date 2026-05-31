# Security Policy

This policy applies to all repositories in the **vista-cloud-dev**
organization.

## Scope and context

These tools operate on **VistA** source code and connect to **InterSystems
IRIS** / **YottaDB** instances. They are development tooling — they are **not**
a production EHR, and they ship with **fictitious test data only** (e.g.
`fakedoc1`, `fakenurse1`). Do not file "vulnerability" reports about the sample
patients; they are synthetic by design.

Take particular care with:

- **`irissync push`** — the single write path back into a database. Misuse can
  overwrite routines.
- **Credentials** — PIV/OIDC tokens, mTLS material, and connection secrets are
  passed by file. Never commit them.
- **PHI/PII** — never load real patient or institution data into any instance
  used with these tools. `kids-vc lint` exists to refuse PHI/PII-class data in
  KIDS distributions, but it is a guard, not a guarantee.

## Reporting a vulnerability

**Please do not open a public issue for security problems.**

Use **GitHub Private Vulnerability Reporting** ("Report a vulnerability" under
the *Security* tab of the affected repository) where available. If that is not
available, contact the maintainers privately rather than disclosing publicly.

When reporting, please include:

- the affected repository and version/commit,
- a description of the issue and its impact,
- steps to reproduce (a minimal proof of concept if possible),
- any suggested remediation.

We aim to acknowledge reports within a few days and will coordinate a fix and
disclosure timeline with you. Please give us a reasonable window to remediate
before any public disclosure.

## Supported versions

These projects are under active development and have not yet reached a stable
release line. Security fixes are applied to the default branch (`main`); there
is no back-port guarantee for older tags at this stage.
