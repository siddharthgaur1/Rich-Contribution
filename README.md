# 🎨 Contribution to `rich` (Textualize)

**Library:** [`Textualize/rich`](https://github.com/Textualize/rich) — 56,000+ ⭐ Python library for beautiful terminal output. Used by FastAPI, pip, AWS CLI, and hundreds of other major tools.

**Issue:** [#3817](https://github.com/Textualize/rich/issues/3817) — `CONTRIBUTING.md` instructed new contributors to run `poetry shell` to activate their virtual environment. This command was removed in Poetry 2.0, so every new contributor hit a confusing error on step 1 of the setup guide.

**Fix:** Replaced `poetry shell` with `eval $(poetry env activate)` (the correct command in Poetry 2.0+), and added a note explaining the change and the plugin alternative for developers who prefer the old behaviour.

---

## Files

- `CONTRIBUTING.md` — the fixed contributing guide (submit this as your PR)
- `PR_SUBMISSION_GUIDE.md` — exact steps to fork, branch, commit, and open the PR

## How to Submit the PR

Follow `PR_SUBMISSION_GUIDE.md` exactly. The whole process takes about 15 minutes.

```bash
# 1. Fork Textualize/rich on GitHub, then:
git clone https://github.com/YOUR_USERNAME/rich.git
cd rich

# 2. Create your branch
git checkout -b fix/poetry-shell-contributing-docs

# 3. Replace CONTRIBUTING.md with the fixed version from this repo
cp /path/to/this/CONTRIBUTING.md .

# 4. Add yourself to CONTRIBUTORS.md (find your alphabetical place)

# 5. Commit and push
git add CONTRIBUTING.md CONTRIBUTORS.md
git commit -m "docs: fix deprecated poetry shell command in CONTRIBUTING.md

- Replaces `poetry shell` (removed in Poetry 2.0) with correct
  `eval $(poetry env activate)` command
- Adds note about the Poetry Shell plugin as an alternative
- Fixes #3817"

git push origin fix/poetry-shell-contributing-docs

# 6. Open PR on GitHub → base: Textualize/rich:master
```

## PR Title
```
docs: fix deprecated `poetry shell` command in CONTRIBUTING.md (fixes #3817)
```
