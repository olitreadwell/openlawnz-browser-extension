# openlawnz/openlawnz-browser-extension context
> refreshed 2026-09-06 | upstream default: master @ 3f70e59

## Identity & policies
- upstream: openlawnz/openlawnz-browser-extension, default branch master, primary language JavaScript (plain content script, no build, no package.json)
- English-first: yes (all docs, issues, and maintainer conversation in English)
- CLA/DCO: CONTRIBUTING.md is a "Contributors Agreement" granting OpenLaw NZ an exclusive copyright licence — a contributor agreement (CLA-like). No CLA bot. Flag for Oli to sign before promoting upstream.
- AI-assisted PR policy: unstated (no AI policy found in repo or org; openlawnz/.github absent)
- signed commits required: no (no branch protection)
- PR template: none (no .github/PULL_REQUEST_TEMPLATE.md, no root template, no org default)
- external tracker: github

## Conventions (verified from merged PRs)
- branch naming: no strong pattern (PR #6 head `claude/edge-extension-support-oJifO`, PR #5 head `master`). Fall back to `type/desc`.
- commit style: plain imperative, no Conventional Commits
- test command: none (no test suite, no CI, no package.json)
- CI checks: none (no .github/workflows)

## Maintainer picture
- active maintainer: flagpoonage (James Kiesel). Recent merged PRs: #6 (Edge support, 2026-05-23), #5 (MV3, 2025-03-18). Slow cadence but responsive to PRs.
- areas actively worked: manifest/browser support (Edge, MV3)

## Issue-area health
- open issues: #3 (2019, "Breaks on Te Ture Whenua Maori act", no maintainer engagement), #4 (2020, "firefox support?", no maintainer engagement). Neither is maintainer-engaged or actionable as a small pick.
- no labels, no assignees, no accepted/approved signals

## Gap ledger (dedupe — READ FIRST, never re-pick)
- 2026-09-06 self-found gap (GraphQL escaping) — pr-opened — formatQuery interpolates title/section into a GraphQL string literal without escaping; a title containing a double quote produces a Syntax Error from the OpenLaw API (verified live). Deduped: no upstream issue/PR covers it. Fork PR #1 (olitreadwell/openlawnz-browser-extension/pull/1), branch fix/escape-graphql-title.

## Mined gaps (discovered, not yet attempted)
- 2026-09-06 clean-code/robustness: formatQuery does not escape `\` or `"` in legislationTitle/section before interpolation. Repro: title `Te "Ture" Whenua Maori Act 1993` -> API returns `Syntax Error: Expected ":", found String`. Expected: query stays valid. Proposed fix: escape backslash and double-quote in both interpolated values. Dedupe: no upstream issue/PR. status: attempted
