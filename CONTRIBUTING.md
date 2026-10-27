# Contributing to Plinkwick Studios

Thanks for helping make something fun. Our game and website repos are private, so this guide is for
people who have been invited in: collaborators, contractors, and the occasional friend who got
roped into a playtest. If you are a player with a bug or an idea, email
[contact@plinkwickstudios.com](mailto:contact@plinkwickstudios.com) or the game's support address
instead.

Every repo has its own `README.md` and usually an `AGENTS.md`. Those win over this file wherever the
two disagree, because they describe what that code actually does.

## Getting access

1. Ask Keehan for an invite to the [Plinkwick-Studios](https://github.com/Plinkwick-Studios) org.
2. Turn on two-factor authentication on your GitHub account before you accept.
3. You get access per repo through a team, not the whole org. Ask if you need something you cannot see.

## How work flows

- `main` is what ships. The website deploys from `main` on every push, and game releases are cut
  from `main`, so never push straight to it.
- Branch from `main`, name the branch for what it does (`fix/reel-tension`, `feature/trade-up-ui`,
  `release/bloop-1.0.11`), and open a pull request.
- Keep a pull request to one idea. Two small PRs review faster than one big one.
- Fill in the PR template. "What changed", "why", and which checks you ran, with their real output.
- A PR merges when its checks pass and someone other than the author has looked at it.

## Before you open a PR

Each repo has one command that is "the check". Run it and paste the summary in the PR.

| Repo | The check |
|---|---|
| Unity games | `bash Tools/check.sh`, then open the project in Unity, confirm the Console is clean, and press Play |
| Website | `npm run build` (typecheck, then Vite build), then open the page you changed in `npm run dev` |

A passing build does not mean a page looks right or a fish feels good to reel. Say what you actually
looked at, and what you did not.

## House style

These hold across every repo, in code, comments, copy, and commit messages.

- **No em dashes.** Use a hyphen, a comma, or a new sentence.
- **No eyebrow labels**, the small uppercase kicker above a heading.
- **Respect `prefers-reduced-motion`** on anything that moves on the web.
- **Each game has its own style**, but shares the studio's playful tone. Fun and a little silly beats
  corporate.
- **Commit messages** say what changed in the imperative, short first line: `Fix reel tension on
  slow phones`, not `fixed stuff`.

## Art, audio, and generated files

- Some files are made by tools (logos, legal pages, store assets). The repo README says which ones.
  Change the tool's input and rerun it; do not hand-edit the output.
- Do not commit large raw source media (renders, WAV stems, PSDs) unless the repo uses Git LFS for
  them. Ask first.
- Only add art, audio, or fonts you have the rights to use, and note the license next to them.

## Secrets

- Never commit keys, keystores, service account JSON, `.env` files, or tokens. Not even "just for a
  minute". If one lands in a commit, tell Keehan right away so it can be rotated; deleting the commit
  is not enough.
- Credentials live outside the repos and in GitHub Actions secrets. Ask for what you need.

## New dependencies

Ask before adding a package, Unity asset, or npm dependency. Every one is something we have to keep
updated and license-check for every platform we ship on.

## Talking about unreleased games

Anything you see in a private repo is unannounced until it is on
[plinkwickstudios.com](https://plinkwickstudios.com). Please do not post screenshots, names, or
details publicly before then.

## Questions

Open a discussion in the repo, or email [contact@plinkwickstudios.com](mailto:contact@plinkwickstudios.com).
