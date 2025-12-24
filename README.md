# Sourcery Ignore Bug Demo

Minimal reproduction for: `.sourcery.yaml` ignore patterns not applied to PR review character limit.

## Issue

When using Sourcery GitHub App, files listed in the `ignore` section of `.sourcery.yaml` are still counted toward the 150,000 character PR review limit.

## Reproduction

1. This repo has a `.sourcery.yaml` that ignores the `generated/` directory
2. The `generated/` directory contains a large file (>150k chars)
3. Create a PR with changes to both `main.py` and `generated/`
4. Sourcery fails with: "your pull request is larger than the review limit of 150000 diff characters"

## Expected

Ignored files should be excluded from the character count.

