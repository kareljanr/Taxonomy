# Create the AIpolitics GitHub repository

The Cursor cloud agent **cannot** create a new GitHub repository under `kareljanr` — the GitHub App token only has access to the existing Taxonomy fork.

Do this once (about one minute), then reply in the agent chat that the repo exists:

## 1. Create the empty repo

Open this link (pre-filled name):

https://github.com/new?name=AIpolitics&description=Source+of+truth+for+Ghent+political+party+%2F+smart+liberal+movement+work&visibility=public

| Field | Value |
|-------|--------|
| Owner | `kareljanr` |
| Repository name | `AIpolitics` |
| Visibility | Public (recommended) or Private |
| Initialize | **Do not** add README, .gitignore, or license |

Create repository.

## 2. Grant Cursor access

If you use Cursor Cloud Agents on this repo:

1. GitHub → Settings → Applications → **Cursor** (GitHub App), or accept the Cursor install prompt
2. Grant access to **AIpolitics** (all repos, or select this one)

## 3. Tell the agent

Reply with something like: **AIpolitics is created — please push.**

The agent will push the prepared content (vision, programme, naming, workflow docs) to `main` on `https://github.com/kareljanr/AIpolitics`.

## Manual push (optional)

If you prefer to push yourself from this branch after creating the empty repo:

```bash
# from a clean clone of this content, or after checking out cursor/aipolitics-repo-af77
git remote add aipolitics https://github.com/kareljanr/AIpolitics.git
git push -u aipolitics HEAD:main
```

Then set `main` as the default branch on GitHub if needed.
