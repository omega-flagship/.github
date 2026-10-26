# Contributing to omega-flagship

This organisation is the working space of the SingularityNET Omega Flagship HitSquad. It is not an open community project like [`singnet/Omega`](https://github.com/singnet/Omega): a small team, people and software agents side by side, reorganising the OmegaHive handover into its own repositories. These guidelines are about one thing: anyone with access can see what is being done, by whom, and why, without having been in the conversation where it was decided. The same rules hold for people and for agents.

## Every piece of work is an issue

Work starts as a GitHub issue, before anyone writes code or documents. The issue says what is to be done, what "done" looks like, and who holds it.

Where it goes:

- in the repository the work changes;
- work that spans repositories, or is about the team itself: the organisation's `.github` repository (public) or `.github-private` (members only);
- work whose code lives elsewhere, for example the NuNet tools on GitLab that this organisation uses: the organisation's copy of that repository, with the issue linking the merge request there. If that copy is archived or takes no issues (as [`nostr-relay`](https://github.com/omega-flagship/nostr-relay) is today), the issue goes in `.github-private`, still linking the merge request.

`.github` and the public repositories can be read by anyone. Hostnames, addresses, key and token names, and logs from the team's machines go in `.github-private`, and so does evidence that contains them.

## The work is done on the issue

Progress, questions, review results and decisions are written on the issue, as comments and labels. A decision taken anywhere else, in a chat, a call or a message between agents, is written back to the issue, or it did not happen as far as the record goes. The issue closes when the pull request that resolves it is merged. Work that has no pull request (a test run, a deploy, a review) closes with a comment that links the evidence: the run, the deploy log, the review.

## Plans and designs are issues too

Anyone who intends to build, rebuild or change a shared piece opens an issue first that explains the plan and the design, so the team can discuss it, design it together or take it to implementation. An idea that lives only in one head, or in one agent's memory, is not a plan the team can act on.

## Larger work: epics and sub-issues

A goal that takes more than one task is an **epic**: one issue for the goal, carrying the design discussion, broken down into GitHub **sub-issues**, one per task, each assigned. Planning, design and breakdown all happen in that tree, in the open.

## Branches, commits and pull requests

- One branch per issue, from `main`, named by kind and subject: `fix/…`, `feat/…`, `docs/…`, `chore/…`.
- Commit messages follow the [Conventional Commits](https://www.conventionalcommits.org/) prefixes used in `singnet/Omega` (`feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`, `perf:`).
- Changes reach `main` by pull request. Every pull request names the issue it resolves (`Closes #n`), describes what the diff does, and says whether it contains generated code. Reviews are written on the pull request.
- How to set up, build and test is each repository's own `README`. The `Omega` repository here is a fork of `singnet/Omega` and follows its upstream [contributing guide](https://github.com/singnet/Omega/blob/main/CONTRIBUTING.md) for code conventions and tests.
- Public repositories are under Apache-2.0; see each repository's `LICENSE`.

## Agents

Software agents contribute under their own GitHub identity (a GitHub App, `<name>[bot]`), never under a person's account, so that every commit, issue and comment says who made it. An agent's work is marked as such where a reader might otherwise take it for a person's considered judgment. GitHub assigns issues to user accounts only, so an issue an agent holds is assigned to the team member responsible for it and carries a `Holder:` line naming the agent; that line says who really holds it. Agents follow these rules exactly as people do: a message between agents is a notification, the issue is the record, and every message about a task links its issue. What an agent can and cannot do here, and how its work flows, is [AGENTS.md](AGENTS.md).

## Where to ask

Open an issue in the repository concerned. For questions about the organisation itself, open one in `.github`. If you are outside the team and want to contribute, start with an issue describing what you propose; the team answers there.

---

*Drafted with AI assistance by the team's tech-lead agent on the team lead's instruction; approved by the team lead. Proposals to change it: an issue in this repository.*
