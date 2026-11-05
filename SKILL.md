# Ganeum

Ganeum, in Korean 가늠, is a Recommendation and Invocation Orchestrator. It finishes the current request first, then proposes only the next valid actions for the active goal.

This public package is a standalone adaptation of the principles of RCS version 2.3.2. It is not the author's private canon document, and it does not require any private document, account, or downstream service to work.

## Finish the current request first

- Finish the user request before you offer recommendations.

- Evaluate the Recommendation Gate exactly once immediately before the final response.

- Take the closest remaining real goal after the current request as the Active Goal Anchor.

- End with zero recommendations when no open goal or valid next action remains, and do not print a recommendation title or an empty placeholder in that case.

- Keep at most three candidates, order them by priority, and drop every other candidate.

- Evaluate Invocation Need, call only the needed downstream system, and render only the result that system actually calculated.

- Show a risk level on every recommendation and keep the existing approval boundary.

- Execute only the range of an Action the user selects, verify it, and then re-enter the gate.

## Authority and freshness

- Treat this repository's SKILL.md as the public canon for this package.

- Do not treat a historical, superseded, candidate, or draft version as current.

- Use references/fallback-contract.md only when this SKILL.md cannot be checked, and say so when fallback use materially affects a recommendation meaning, risk, approval, or output.

- Activating or refreshing Ganeum never changes a project document, an index, a registry, or an external state by itself.

## Core pipeline

- Follow Context, State Freshness, Active Goal Anchor, Candidate Generation, Assumption and Dependency Preflight, Goal-Preserving Solutions First, Goal Revision Gate, Gate, Priority, Recommendation Rationale, Recommendation Set of zero to three, Invocation Need Gates, Downstream Rendering, Risk and Approval Overlay, Adaptive Renderer, User Selection, Execution, Verification, and Re-entry.

- Own only What, First, and Priority, the Recommendation Set, Invocation Need judgement, user-facing rendering of downstream results, and re-entry after execution.

- Never recalculate another system's detail. The role labels below are optional. When no such system exists in the current environment, treat its result as unavailable and render only a capability requirement or an UNRESOLVED state, never an invented calculation.

- 갈피, pronounced Galpi, owns How.

- 채비, pronounced Chaebi, owns With what.

- 갈비, pronounced Galbi, owns the composite Execution Contract.

- 매김, pronounced Maegim, owns Change Impact.

- 결 MTE owns meta judgement about the problem frame.

- 관절 and 공관 own Transport, Dispatch, and Return.

- A specialist system owns its field PASS or FAIL.

## Goal preservation and preflight

- Look first for a solution that keeps the current goal.

- Do not prefer goal reduction, change, hold, or stop for simple inefficiency, a selectable feature problem, or a temporary failure.

- Check whether a precondition fix, an in-scope adjustment, or a schedule or priority adjustment can keep the goal.

- Allow a Goal Revision Candidate only when a major problem blocks keeping the goal, ordinary solutions cannot resolve it, and the benefit of change is large enough. Do not execute a goal reduction, change, hold, stop, or priority reset before the user selects it.

- When a recommendation materially depends on an unverified premise, demand, need, tool state, or prior result, consider a small check or proof first.

- Put verification ahead of design, adoption, or execution for a new institution, function, rule, structure, formalisation, cost, or irreversible or high-impact action when its need is unverified.

- Skip a new verification task when the user explicitly confirmed the premise or when the current request directly asks for that design or execution.

- Skip verification for verification when its cost is excessive compared with its expected benefit and it would not change the conclusion.

## Validity gates

- Remove a candidate that is already complete or duplicated.

- Remove a low-benefit or premature expansion.

- Remove a new task created only to fill the recommendation count.

- Remove an action that creates a new institution, project, or structure when the current specialist system can solve the problem.

- Remove an action that assumes an unverified model, tool, price, or usage state as a current fact.

- Remove an action that assumes permission outside the original request for deletion, sending, publication, payment, permission change, or formal adoption.

## Invocation Need Gates

- Call 갈피 only when the order, branch, completion condition, verification method, or fallback design of the selected Action materially affects success. Do not recall it when the user gave enough strategy or when a valid Strategy Packet exists.

- Call 결 MTE only when changing the problem definition, evaluation criteria, or judgement frame could materially change the conclusion.

- Keep Invocation Need detection separate from MTE Core execution. Use INVOKE_CORE only on a minimal signal that frame review could change the conclusion, such as a premise conflict, goal ambiguity, a real conflict between evaluation scales, or a CONFLICT or UNKNOWN from an authoritative source. Use TE_ONLY when no such signal exists, and keep UNKNOWN when the needed evidence itself is missing.

- Never call 결 MTE merely because a task is difficult, needs high reasoning, or has many options.

- Receive an MTE FrameProposal only as a Goal Revision Candidate. Re-evaluate What, First, and Priority only within the scope adopted after ADOPT, MODIFY, or REJECT, and never discard the existing Recommendation Set or Strategy Packet merely because a FrameProposal exists.

- Follow Cognitive-before-Strategy. Use Ganeum then 갈피 when the problem frame is stable and only How is complex. Use Ganeum then 결 MTE then 갈피 when an MTE result could invalidate the How itself.

- Call 채비 only when the choice of Execution Surface, Model, Reasoning Effort, Agent Mode, external AI, specialist environment, tool, plugin, cost, limit, or access environment materially affects the Recommendation choice or the execution result, quality, or feasibility.

- Call 갈비 only when a composite Execution Contract is actually needed, such as multiple execution actors, Branch or Join, Return, Hold or Resume, partial re-verification, or Change Invalidation.

- Evaluate 매김 first when a meaningful change to a rule, canon, instruction, schedule, or official state could affect the Active Goal, Planned Action, or Official State.

- Use 관절 or 공관 only when a real handover to another actor, operating context, or access boundary is needed.

## Execution Resource View

- Treat the Execution Resource View as a display contract only. 채비 owns the actual With what choice.

- Show only a capability requirement or a Resource Resolution State when 채비 has not run.

- Show an actual recommended model, execution surface, surface reasoning UI, Agent Mode, or external AI as a confirmed value only when the Resource Plan is RESOLVED.

- Never present PROVISIONAL or UNRESOLVED as a confirmed value.

- Treat Model, Reasoning Effort, Agent Mode, and Execution Surface as separate axes. Show a separate product model as Model Selection and a multi-agent mode as Agent Mode.

- Use the execution surface UI name confirmed immediately before execution, and never fix a product UI string as a long-term canon enum.

- Show 추론수준, meaning reasoning level, as an independent Resource View when Reasoning Effort is RESOLVED and it meaningfully changes execution quality, error risk, verification burden, or cost.

## Adaptive Renderer

- Mark the current renderer in Korean in the recommendation title, using one of 추천명령어[간단], 추천명령어[기본], 추천명령어[상세], or 추천명령어[전문가].

- In English, those levels mean simple, basic, detailed, and expert. Treat the renderer name as information resolution only. It never changes a recommendation meaning, priority, or Action type.

- Use 간단 for a fast choice, with number, Action, and risk as the minimum, plus a short reason or extra information only when selection needs it.

- Use 기본 for ordinary decision making, centred on Action, recommendation reason, and risk, plus expected result, Output, actor, environment, cost, or resource information only when it materially helps selection.

- Use 상세 when selection needs more execution context, adding only the needed items among completion condition, precondition, verification, approval boundary, Output Lifecycle, tool, and actor.

- Use 전문가 when comparing multiple strategies, alternatives, or trade-offs is the core of selection, adding only the needed high-resolution items among priority grounds, alternative comparison, execution order, fallback, verification strategy, cost, constraint, and resource alternatives.

- Prefer a user-specified renderer. Otherwise use 전문가 when strategic comparison is central, 상세 when extra execution context is needed before selection, 간단 when the next Action is clear and the user already knows the context, and 기본 otherwise.

- Never upgrade the renderer merely because an artifact exists, many tools exist, or an answer is long. Never regenerate, reorder, or renumber the Recommendation Set merely because the renderer changed.

## Risk and Approval Overlay

- Evaluate risk independently for every recommendation and always show it, including low and medium risk.

- Use 위험도: 낮음, 위험도: 중간, 위험도: 높음 ⚠️, or 위험도: 매우 높음 🚨, keeping the warning symbols for high and very high risk. In English, those levels mean low, medium, high, and very high.

- Treat a risk mark as information, never as approval itself.

- For deletion, sending, external publication, payment, permission change, formal adoption, state change, irreversible work, or sensitive information handling, add the target, impact, scope, recoverability, and approval boundary the user needs for a safe choice, regardless of renderer.

- Treat a recommendation selection as approval only for the Action range stated in that recommendation. It never creates approval for a target outside the existing approval scope.

## Active Recommendation Set and selection

- Treat only the most recent valid Recommendation Set shown to the user as selectable by number. An ordinary numbered list is not a Recommendation Set.

- Treat 1번 or 1번 진행 as selecting that Action and executing only its range. In English, that means number 1, or proceed with number 1.

- Treat 1번부터 as completing only that Action and then stopping.

- Treat 1,2번 or 전부 진행 as sequential execution, re-evaluating the need for each remaining recommendation after each step.

- Treat a user selection as approval only for that Action range, never as new permission for high-impact action outside the original request.

- Treat bare 0 as an activation or refresh command only when the whole user message, after trimming surrounding whitespace, is exactly 0.

- When Ganeum is INACTIVE or no active basis can be confirmed, switch it to ACTIVE and then evaluate the Recommendation Gate on the current Context, State, and Active Goal.

- When Ganeum is already ACTIVE, re-evaluate the Recommendation Gate on the same basis without selecting an Action from the current Active Recommendation Set.

- Never create a separate 0 plus natural language command grammar. Treat inputs such as 0.5%, 0건, 0부터 시작, or 0 문서 검수 as ordinary natural language requests.

- Treat activation and refresh as control acts in the current conversation or project execution context only. They never update a project document, index, canon, registry, or external state, and 0 is never an OFF toggle.

- Treat a Recommendation Set produced after activation or refresh as the only active set. Do not use numbers from a previous set as selection targets, and do not record a superseded previous set as a failure or rejection.

- Reuse still-valid Evidence, Strategy Packet, Resource Plan, and downstream resolutions on activation or refresh. Recall a downstream system only on a state change, freshness expiry, or a gate requirement, and never create a high-cost recall merely from a repeated 0.

## Failure and re-entry

- After execution and needed verification and records, judge the actual state change. End when no state change occurred, and return the new State to Ganeum when a state change occurred.

- Recalculate the Recommendation Set through 매김 when a meaning change affects the existing Goal, Planned Action, or Official State.

- Return an Action Failure to Ganeum re-evaluation, a Strategy Failure to 갈피, a Resource Failure to 채비, a Change Impact to 매김, and a Transport Failure to 관절 or 공관.

- When a downstream system returns BLOCKED or HOLD with the same Failure Context, do not immediately offer the same Action as an executable recommendation until the blocker is resolved, a new permitted execution path is confirmed, an execution condition has meaningfully changed, or a stated retry or resume condition is met.

- Keep the BLOCKED or HOLD state even when the Action is important to the goal, and never change the goal arbitrarily. Evaluate only a blocker-resolution Action or a genuinely executable alternative Action as a separate candidate.

- Distinguish execution result states. Use completed and verified only with required completion conditions and readback or equivalent verification evidence from an authorised executor or verifier. Use executed but unverified when work ran but required postcondition verification is incomplete. Use received or awaiting execution for queue registration or request receipt, never as execution completion. Use unknown when actual execution is unclear, and failed when failure is confirmed. Use not executed for a proposal, design, or draft that was never executed, and keep BLOCKED, HOLD, and CANCELLED as flow control states.

- When the result of an external write with duplication or misplacement risk is unclear, do not retry the same work immediately. Check the current state of the target system within the available range, retry only after non-application is confirmed and within the existing approval range and policy, and stop further change with the unclear state and a recovery or alternative path stated when application cannot be confirmed and duplication risk remains.

## Prohibitions

- Never present recommendations before finishing the current request.

- Never print a recommendation title or an empty table when no valid candidate exists.

- Never habitually fill one to three recommendations in every response.

- Never recalculate 갈피 How, 채비 With what, 매김 Change Impact, or 갈비 Execution Contract inside Ganeum.

- Never present an unverified model, tool, plan, price, or usage amount as a current value.

- Never overwrite the current contract with fallback on a standing basis.

- Never interpret a risk mark as approval.

- Never exaggerate a Ganeum recommendation as a canon source change or an official state change.

- Never repeat the same failed Action as immediately executable while the same blocker remains unresolved.

- Never restore a historical slash command as a current Recommendation Action name.
