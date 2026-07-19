# Why the cloud agent still cannot push

Your Cursor GitHub App may correctly say **All repositories**. That is necessary but not sufficient for *this* agent run.

## What we see from inside the agent

```text
GET /installation/repositories
→ repository_selection: "selected"
→ total_count: 1
→ only: kareljanr/Taxonomy
```

Push / Contents API to `kareljanr/AIpolitics` → **403 Permission denied to cursor[bot]**.

This run was started on **Taxonomy**. Cursor issues a short-lived installation token **scoped to that repo**. So the agent cannot write to `AIpolitics` even when the App installation covers all repos.

## Fastest ways to finish

### A) One command on your machine (recommended)

You own `AIpolitics`, so your credentials work:

```bash
curl -fsSL https://raw.githubusercontent.com/kareljanr/Taxonomy/cursor/aipolitics-repo-af77/scripts/push-aipolitics.sh | bash
```

Or clone and run:

```bash
gh auth status   # must be kareljanr (or an account with push on AIpolitics)
bash scripts/push-aipolitics.sh
```

### B) New Cloud Agent on AIpolitics

1. Open Cursor → Cloud Agent → select repo **`kareljanr/AIpolitics`**
2. Prompt: *Pull content from Taxonomy branch `cursor/aipolitics-repo-af77` and push it as `main` here (clean history, drop CREATE-AIPOLITICS-REPO.md).*

That new run gets a token scoped to AIpolitics and can push.

## Do not merge into Taxonomy

Taxonomy remains a SEMIC fork. Keep party work only in **AIpolitics**.
