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

