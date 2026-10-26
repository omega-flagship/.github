# Agents in omega-flagship: what your agent can do, and how its work flows

## The tool

An agent acts on GitHub through `gh-app`, which lets it work as its own GitHub App, `<name>[bot]`, with no stored token: https://github.com/nunet/github-app (a read-only mirror of the NuNet project where it is developed; the README has the install and the four settings). Questions and proposals about the tool: an issue on that repository.

## Your agent's identity

Each member of the Omega Flagship HitSquad gets one GitHub App in the `omega-flagship` org, named `<github-handle>-agent-1`, installed on all repositories of the org. Everything the agent does appears as `<github-handle>-agent-1[bot]`, never as you. The app's only credential is a private key; you generate it yourself on the app's page, it downloads to your machine and never passes through anyone else. Keep it in `pass` or an equivalent store. If it leaks, generate a new key on the app's page and delete the old one; that is the whole recovery. Never put a key or a token on a command line, in a chat, a commit, a ticket or an `.env` file; `gh-app exec <command>` hands the one-hour token to the child process and prints nothing.

## What the app can do, and cannot

| Can (read and write) | Read only | Cannot |
|---|---|---|
| repository contents: branches, commits, files | deployments | change or add workflow files under `.github/workflows` |
| pull requests, reviews, comments | repository metadata | read or set secrets and variables |
| issues, labels, comments | org members | change org or repository settings, rulesets, runners |
| Actions runs: trigger, cancel, re-run | | push to a protected `main` |
| checks and commit statuses | | be assigned an issue (GitHub assigns to user accounts only) |

Workflow files are changed by people, or by the QA and tech-lead agents, which hold that permission.

## How your agent's work flows

The org's guidelines, [CONTRIBUTING.md](CONTRIBUTING.md), apply to agents exactly as to people. In short:

1. Every piece of work is an issue, in the repository concerned; plans and designs are issues too. An issue an agent holds is assigned to you and carries a `Holder:` line naming the agent.
2. One branch per issue from `main`, named `fix/…`, `feat/…`, `docs/…`, `chore/…`; Conventional Commits prefixes.
3. Changes reach `main` by pull request. The pull request names its issue (`Closes #n`), says what the diff does and whether it contains generated code. Reviews are written on the pull request; a QA pass precedes the merge.
4. Mail between agents is a notification; the issue is the record. Every message about a task links its issue.
5. Repositories mirrored from GitLab (`nostr-relay`, `nostr-mailbox`, `github-app`) are merged on GitLab; their GitHub `main` is a copy. Both ways in work: a merge request on GitLab is the direct one; a pull request here is accepted too, and the tech-lead agent carries it over (fetches the branch, pushes it to GitLab, opens the merge request there). After the merge the mirror brings `main` back and GitHub marks the pull request merged. Issues may be opened on either side.

## Where to ask

About these rules or the org: an issue in [omega-flagship/.github](https://github.com/omega-flagship/.github/issues). About the tool: an issue on [nunet/github-app](https://github.com/nunet/github-app/issues). About your own app or key: the team lead.

---

*Drafted with AI assistance by the team's tech-lead agent on the team lead's instruction; approved by the team lead. Proposals to change it: an issue in this repository.*
