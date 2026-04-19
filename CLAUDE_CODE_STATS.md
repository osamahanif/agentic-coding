# Two Years of Shipping. Three Months with Claude Code.

From a standing start on **2026-01-06**, I shipped **648 Claude-Code-attributed commits in 102 calendar days** — **54.8% of every commit I authored in that window**, totaling **279,695 lines added and 89,178 lines deleted across 4,086 files**. Peak day: 105 commits. Longest streak: 13 consecutive shipping days.

## Summary

| Metric | Value |
|---|---:|
| Window analyzed | 2024-04-19 → 2026-04-19 (24 months) |
| Total commits I authored | 1,219 |
| Claude Code commits | 648 |
| CC share, full 24-month window | 53.2% |
| CC share, since CC adoption (2026-01-06) | 54.8% |
| First CC commit | 2026-01-06 |
| Last CC commit | 2026-04-16 |
| Distinct repos touched with CC | 2 |
| Insertions via CC | 279,695 |
| Deletions via CC | 89,178 |
| Files touched via CC | 4,086 |
| Active CC days | 58 |
| Longest consecutive-day streak | 13 |
| Avg CC commits per active day | 11.2 |

Detection logic: a commit counts as Claude Code if its message contains any of `Co-Authored-By: Claude <noreply@anthropic.com>`, `Generated with Claude Code`, the 🤖 emoji, or a `Co-Authored-By: Claude` trailer. Bot commits (dependabot, renovate, github-actions, vercel) and merge commits are excluded.

## Per-repo breakdown

| Repo | Total commits | CC commits | Primary language | Purpose |
|---|---:|---:|---|---|
| primary-saas (private) | 1,181 | 647 | TypeScript | Production SaaS web app — full-stack Next.js + Supabase |
| agent-session-archive (private) | 30 | 1 | Markdown | Personal session logs, decisions, and research artifacts |
| second-brain (local) | 7 | 0 | Markdown | Personal knowledge base scaffold |
| gstack (OSS fork) | 1 | 0 | TypeScript | Headless browser tooling — upstream contribution |

99.8% of CC commits live in a single production codebase. The other CC commit landed in my session archive.

## Language breakdown (files touched in CC commits)

```
TypeScript  ████████████████████████████████████████████████████████████  3,373  ( 82.5% )
Markdown    █████                                                          292  (  7.1% )
JSON        █                                                               82  (  2.0% )
SQL         █                                                               60  (  1.5% )
Python      ▌                                                               53  (  1.3% )
YAML        ▌                                                               40  (  1.0% )
JavaScript  ▎                                                               24  (  0.6% )
CSS         ▏                                                               16  (  0.4% )
Shell       ▏                                                               13  (  0.3% )
HTML        ·                                                                5  (  0.1% )
```

## Notable work (top 5 CC commits by diff size)

All from the production SaaS repo. Hashes preserved for verification.

1. **`3c5d442a` · 2026-01-09 · +66,770 / −191** — Migrate UI primitives to design tokens (multi-ticket refactor across the component library).
2. **`28d1c698` · 2026-01-26 · +453 / −21,474** — Remove dead code: legacy V1 AI system, unused dependencies, miscellaneous cleanup.
3. **`ce773118` · 2026-01-27 · +0 / −10,130** — Delete legacy V1 quiz-builder components after the V2 cutover.
4. **`cd45c16e` · 2026-03-13 · +7,757 / −52** — Add Supabase baseline migration and generated database types.
5. **`c259da9b` · 2026-03-17 · +5,896 / −4,522** — Regenerate Supabase baseline from remote via `pg_dump` and reconcile drift.

These are not typo fixes. They are large-scope architectural moves: design-system migration, dead-code excision, schema baselining. Each shipped to a live production codebase with paying users.

## Skipped (confidentiality)

0 repos. No Microsoft-hosted remotes were detected in the scan. Repo display names have been anonymized for public sharing per a personal confidentiality policy.

## Methodology

- Scanned every git repo under `~`, `~/Developer`, `~/Documents`, `~/.hermes`, `~/.openclaw` (9 repos found, 4 with my commits in the 24-month window).
- Filtered commits by author email matching my known identities, excluding merges and bot accounts.
- Computed per-commit shortstats; aggregated by Claude Code attribution markers.
- Stripped any commit message containing what looked like a secret before including it. None matched.
- This report itself was assembled by Claude Code, end-to-end, in a single session.

## Closing

Adoption was binary, not gradual: zero CC commits in 2025, then 648 in the first 102 days of 2026. The pattern that shows up in the data — large refactors, schema migrations, dead-code removal — is the kind of work I had been deferring for months because the coordination cost was too high. With Claude Code, those tickets stopped being scary. They became Tuesday.
