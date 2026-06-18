# 🎨 Contribution to `rich` (Textualize)

**Library:** [`Textualize/rich`](https://github.com/Textualize/rich) — 56,000+ ⭐ Python library for beautiful terminal output. Used by FastAPI, pip, AWS CLI, and hundreds of other major tools.

**Issue:** [#3817](https://github.com/Textualize/rich/issues/3817) — `CONTRIBUTING.md` instructed new contributors to run `poetry shell` to activate their virtual environment. This command was removed in Poetry 2.0, so every new contributor hit a confusing error on step 1 of the setup guide.

**Fix:** Replaced `poetry shell` with `eval $(poetry env activate)` (the correct command in Poetry 2.0+), and added a note explaining the change and the plugin alternative for developers who prefer the old behaviour.

---

## Files

- `CONTRIBUTING.md` — the fixed contributing guide (submit this as your PR)
- `PR_SUBMISSION_GUIDE.md` — exact steps to fork, branch, commit, and open the PR


## PR Title
```
docs: fix deprecated `poetry shell` command in CONTRIBUTING.md (fixes #3817)
```
