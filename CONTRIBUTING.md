# Contributing to Seventh Sense

Thanks for contributing. This is an active hackathon project moving fast —
please keep changes focused and reviewable.

## Branch naming

Use `feature/<module-name>` for new work, e.g. `feature/watch-ingestion`,
`feature/scoring-engine`. Use `fix/<short-description>` for bug fixes.

## Commit messages

Use short, imperative-mood summaries, e.g.:

```
feat: add stillness-duration feature extraction
fix: correct lux normalization in rb3 context frame
docs: expand device fallback plan
```

Do not include AI/LLM assistant attribution trailers or footers in commit
messages.

## Opening a pull request

1. Branch from `develop`, not `main`.
2. Keep PRs scoped to a single module or concern where possible.
3. Fill out the PR template (what changed, testing done, checklist).
4. Reference the relevant `docs/` page if your change affects behavior
   described there.

## Code of Conduct

By participating in this project you agree to abide by our
[Code of Conduct](CODE_OF_CONDUCT.md).
