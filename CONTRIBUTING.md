# Contributing to Ninsei Labs

These rules apply to every Ninsei Labs repository, public or private. Each repository's AGENTS.md repeats
them for coding agents and adds its own commands.

## Commit messages

The subject has the form `type(scope): summary`, as in
[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/):

```
fix(gas): measured claim and order-creation gas limits (#114)
feat(escrow): one shared implementation, one clone per order
docs: the denylist section of the guide
```

| Type | For |
|---|---|
| `feat` | new behaviour |
| `fix` | a bug fix |
| `docs` | documentation only |
| `test` | tests only |
| `refactor` | code that changes no behaviour |
| `perf` | the same behaviour, faster or smaller |
| `build` | dependencies, toolchain, packaging, releases |
| `ci` | CI workflows |
| `style` | formatting only |
| `chore` | anything else |
| `revert` | undoing an earlier commit |

- The scope is optional: the part of the repository the change is in, in lower case (`gas`, `escrow`,
  `maker`). Leave it out when the change spans many.
- A breaking change to a published interface adds `!` before the colon (`feat(api)!: ...`), and the body
  says what breaks.
- The summary says what the change does. It starts with a lowercase letter unless it starts with a name,
  and has no full stop at the end. An issue goes at the end as `(#114)`.
- The whole subject is at most 72 characters: GitHub and `git log --oneline` cut longer ones off. The
  detail goes in the body.
- The body, after a blank line, says why, what else the change touches and how it was checked.
- A commit is one logical change. Work-in-progress and fixup commits are squashed into the change they
  belong to before the pull request is merged.

## Pull requests

- The title has the same form as a commit subject.
- The description says what changes, why, and how it was checked.

## Always

- No attribution lines for tools: no `Co-authored-by:` trailer and no "Generated with" line, in commits or
  pull requests. A person who co-wrote a change is named in the body. In another project's repository,
  follow that project's rules.
- Code, commits and pull requests describe the change, not the conversation or the attempts behind it.
- No secrets and no real wallet or account addresses, keys or tokens. Tests use made-up values.

## Security

A vulnerability is reported privately, never in a public issue: see [SECURITY.md](SECURITY.md).

## Responsibility

Much of our code is written with coding agents. The person who merges a change answers for it: they have
read it, can explain it and checked that it does what it says.

## The check

Every repository runs the `house-rules` workflow on pull requests and on pushes to `main`. It reads only
what a change adds: the pull request's title and description and the commit messages. It fails on a commit
subject or pull request title that is not `type(scope): summary` (merge and revert commits made by git or
GitHub pass) and on a `Co-authored-by:` trailer or a "Generated with" line. The other rules are kept by
the people and agents who write and review a change. Its source is
[`.github/workflows/house-rules.yml`](.github/workflows/house-rules.yml) in this repository.
