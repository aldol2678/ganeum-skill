# Ganeum fallback contract

Authority: LOCAL SAFE FALLBACK ONLY. NON-CANONICAL.

Use condition: Use this contract only when the public SKILL.md in this repository cannot be checked.

Supersession rule: As soon as SKILL.md is checked, that file takes priority and this fallback is disabled.

Historical note: A historical contract is a historical reference only. It never replaces this fallback and never applies as a runtime rule.

## Minimum invariants

- Finish the current user request before offering recommendations.

- Evaluate the Recommendation Gate exactly once immediately before the final response.

- Zero recommendations is normal when no valid next Action exists.

- Never create a new task only to fill the recommendation count.

- Prefer a solution that preserves the current open goal over changing the goal.

- Prefer a small verification over a structural change, formalisation, cost, or irreversible action when it depends on an unverified premise, unless the user confirmed the premise or directly requested that action.

- Ganeum owns only What, First, and Priority. 갈피 owns How, 채비 owns With what, and 매김 owns Change Impact.

- When an actual resource value is needed but no 채비 result exists, show only a capability requirement or an UNRESOLVED state, and never guess a model, tool, reasoning level, or Agent Mode.

- Show a risk level on every recommendation.

- Treat a recommendation selection as approval only for the stated Action range. It never creates permission for deletion, sending, publication, payment, permission change, or formal adoption outside the existing approval scope.

- Treat artifact creation, saving, formal adoption, and external publication or sending as different states.

- Never repeat a BLOCKED or HOLD Action as immediately executable while the same Failure Context remains unchanged.

## Minimum renderer contract

- Prefer a user-specified renderer.

- 간단: number, Action, and risk, plus a reason or minimum information only when selection needs it.

- 기본: Action, recommendation reason, and risk, plus other fields only when they help selection.

- 상세: add only the completion condition, precondition, verification, approval boundary, Output Lifecycle, or other information actually needed for selection.

- 전문가: add priority grounds, alternatives, fallback, verification, cost, or constraints only when alternative or trade-off comparison is central to selection.

- Renderer resolution never changes an Action meaning or priority.

## Safety boundary

- Never use HISTORICAL, SUPERSEDED, CANDIDATE, or DRAFT as CURRENT.

- Never estimate a changing model, tool, price, limit, or product UI.

- Never claim that fallback replaces the detailed contract of SKILL.md.
