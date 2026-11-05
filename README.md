# Ganeum — Recommendation Command System

Ganeum, in Korean 가늠, is a small instruction skill for an AI assistant. It finishes the current request first, then proposes only the next valid actions for the active goal.

Public package version 0.1.0, prepared 2026-11-05. Its principles are based on RCS version 2.3.2. This repository is not the author's private canon document, and the private Drive canon is not required to use this package.

## What it does

- Proposes zero to three next actions, ordered by priority, after the current request is complete.

- Keeps the current goal first, checks unverified premises before high-impact work, and never invents a task only to fill the list.

- Separates ownership: Ganeum owns What, First, and Priority. Other roles own How, With what, Change Impact, Execution Contract, meta judgement, and Transport, and Ganeum only renders their calculated results.

- Shows a risk level on every recommendation. A risk mark is information, not approval. Selecting a recommendation approves only that recommendation's stated range.

- Uses a four-level Adaptive Renderer, marked in Korean in the title: 추천명령어[간단] for simple, 추천명령어[기본] for basic, 추천명령어[상세] for detailed, and 추천명령어[전문가] for expert.

- Supports number selection from the most recent valid set, and bare `0` as activation or refresh only when the whole message is exactly `0`. It is never an OFF toggle, and it never updates a project document, index, canon, registry, or external state by itself.

## What it does not do

- It does not execute actions by itself, grant new permissions, or expand an approval scope.

- It does not choose a model, tool, reasoning level, or execution environment. Those choices belong to the With what role, and Ganeum shows them only when they are RESOLVED.

- It does not require the author's private systems. The Korean role names 갈피, 채비, 갈비, 매김, 결 MTE, 관절, and 공관 are optional role labels. When no such system exists, their results are unavailable, not invented.

## Use

This package was verified as a Muse custom skill in the author's workspace, where `SKILL.md` sits beside `skill.yaml` and `references/fallback-contract.md`.

To try it with another agent host, load `SKILL.md` through that host's skill loader. Other hosts and their skill formats were not verified for this package, so do not claim a host-specific install path until it has been tested there.

## Files

- `SKILL.md`: the public skill contract.

- `skill.yaml`: name, title, description, and prompt inclusion for a Muse-style custom skill.

- `references/fallback-contract.md`: the minimum safe contract, used only when `SKILL.md` cannot be checked.

## Version and origin

- Public package: 0.1.0, 2026-11-05.

- Principles basis: RCS 2.3.2, including separation of Invocation Need detection from MTE Core execution, and FrameProposal handled only as a Goal Revision Candidate.

- The version 2.3.3 candidate was not adopted and is not included.

## License

MIT License. See LICENSE.
