# Ganeum — Recommendation Command System

Ganeum, in Korean 가늠, is a small instruction skill for an AI assistant. It finishes the current request first, then proposes only the next valid actions for the active goal.

Public package version 0.1.0, prepared 2026-11-05. Its principles are based on RCS version 2.3.2. This repository is not the author's private canon document, and the private Drive canon is not required to use this package.

## 한국어 빠른 시작 · Codex

가늠은 지금 요청을 마친 뒤, 목표에 도움이 되는 다음 행동을 최대 세 개까지 추천합니다. 해 볼 일이 하나면 1번만 나오고, 목표를 달성하면 추천도 끝납니다.

1. 가늠을 써 볼 프로젝트의 루트에서 아래 명령을 실행하세요. Git이 필요합니다.

   ```sh
   git clone https://github.com/aldol2678/ganeum-skill.git .agents/skills/ganeum
   ```

2. 같은 프로젝트에서 새 Codex 대화를 열고 다음처럼 요청하세요.

   > $ganeum 동네 책교환 모임을 준비하고 있어. 토요일 오후 2시, 시립도서관 앞에서 만나고 각자 책 한 권을 가져와. 초대 문구와 당일 준비 목록이 필요해. 지금은 할 일만 추천해 줘. 내가 번호를 고르면 그때 골라서 작성해 줘.

3. 가늠이 추천한 행동을 번호로 고르세요. 아래는 대화의 한 예입니다. 실제 순서와 개수는 상황에 따라 달라집니다.

   | 입력 | 예시 응답 |
   | --- | --- |
   | 위의 첫 요청 | 1. 초대 문구 초안 쓰기 · 위험도 낮음. 2. 당일 준비 목록 만들기 · 위험도 낮음. |
   | `1` | “토요일 오후 2시, 시립도서관 앞에서 책 한 권씩 바꿔 읽어요. 교환하고 싶은 책 한 권을 가져오세요!” |
   | `0` | 초대 문구는 준비됐어요. 1. 당일 준비 목록 만들기 · 위험도 낮음. |

`0`만 보내면 현재 상황에 맞춰 추천을 갱신합니다. 이제 `1`은 최신 목록의 1번을 가리킵니다. 초안 작성과 실제 초대 발송은 각각 별도의 행동입니다.

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

For Codex, follow the project-local setup above. For other agent hosts, check how their loader discovers `SKILL.md` and verify the skill in that host.

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
