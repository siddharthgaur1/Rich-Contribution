# How to submit this PR to Textualize/rich

## What this fixes
Issue #3817 (open since Aug 2025): CONTRIBUTING.md tells contributors to run
`poetry shell` to activate the virtual environment — but that command was
removed from Poetry's default install in v2.0.0. Every new contributor who
tries to follow the guide hits this error immediately.

**Two exact changes made:**
1. Added `eval $(poetry env activate)` as the correct activation command
2. Added a Note block explaining the breaking change and the plugin alternative
3. Replaced the broken `poetry shell` fallback hint at the bottom with the correct command

---

## Step-by-step: Fork → Fix → PR

### Step 1: Fork the repo
Go to https://github.com/Textualize/rich and click **Fork** (top right).
This creates your own copy at https://github.com/siddharthgaur1/rich

### Step 2: Clone your fork locally
```bash
git clone https://github.com/siddharthgaur1/rich.git
cd rich
```

### Step 3: Create a branch (NEVER work directly on master)
```bash
git checkout -b fix/poetry-shell-contributing-docs
```

### Step 4: Replace CONTRIBUTING.md
Copy the CONTRIBUTING.md file I gave you and paste it into your cloned repo,
replacing the existing one. Or make these two targeted changes manually:

**Change 1** — Replace this block (around line 30):
```
# BEFORE
poetry install

```

The rest of this guide assumes you're inside the virtual environment.
If you're having difficulty running any of the commands that follow,
ensure you're inside the virtual environment by running `poetry shell`.
```

With this:
```
# AFTER
poetry install
```

To activate the virtual environment, run:

```
eval $(poetry env activate)
```

> **Note:** `poetry shell` was removed as a default command in Poetry 2.0.
> Use `poetry env activate` (recommended) or install the shell plugin with
> `poetry self add poetry-plugin-shell` if you prefer the old behaviour.

The rest of this guide assumes you're inside the virtual environment.
If you're having difficulty running any of the commands that follow,
ensure you're inside the virtual environment by running `eval $(poetry env activate)`.
```

### Step 5: Update CONTRIBUTORS.md
Open CONTRIBUTORS.md in the repo and add your name at the bottom:
```
Siddharth Gaur
```

### Step 6: Commit
```bash
git add CONTRIBUTING.md CONTRIBUTORS.md
git commit -m "Fix deprecated poetry shell command in CONTRIBUTING.md

poetry shell was removed from Poetry's default install in v2.0.0.
Replace with `eval $(poetry env activate)` and add a Note block
explaining the change and the plugin alternative.

Fixes #3817"
```

### Step 7: Push
```bash
git push origin fix/poetry-shell-contributing-docs
```

### Step 8: Open the PR
1. Go to https://github.com/Textualize/rich
2. You'll see a yellow banner saying "Compare & pull request" — click it
3. Set base: `master`, compare: your branch

**PR Title:**
```
Fix deprecated `poetry shell` command in CONTRIBUTING.md
```

**PR Description (copy-paste this exactly):**
```
## Summary
Fixes #3817

`CONTRIBUTING.md` instructs contributors to run `poetry shell` to activate
the virtual environment. Since Poetry 2.0.0, this command is no longer
installed by default, causing every new contributor to hit an error
immediately when following the setup guide.

## Changes
- Replace `poetry shell` with `eval $(poetry env activate)` (the current
  recommended approach per Poetry docs)
- Add a Note block explaining the breaking change and the plugin alternative
  (`poetry self add poetry-plugin-shell`) for users who prefer the old flow
- Replace the fallback hint at the bottom of Prerequisites with the
  corrected command

## Testing
Documentation-only change. No code modified.
```

4. Check the checklist items that apply (documentation change, no new tests needed)
5. Click **Create Pull Request**

---

## What happens next

The maintainers typically reply within a few days to a few weeks.
You might get a small review comment asking for a tweak — just make the
change, `git commit --amend`, and `git push --force origin your-branch`.

Once merged, you'll appear in the rich CONTRIBUTORS.md and your GitHub
profile will show a contribution to a 56k-star Python library.

---

## Why this PR will likely get merged

- It fixes a confirmed, reproducible bug (verified by 2+ separate issues: #3634, #3817)
- Documentation-only = zero risk of breaking anything
- The existing PR #3818 has been open since August 2025 with no merge —
  the maintainers clearly want this fixed but haven't gotten to it
- Your fix is more complete: it adds the Note block explaining *why*,
  which is more helpful than just swapping the command
```
