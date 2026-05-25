# 생활용품 통합 신제품 런칭 준비 브리프 Lab

이 lab은 [생활용품 통합 신제품 런칭 준비 브리프](../../07-lifestyle-household-design-to-distribution.md) use case를 Cursor Agent에서 바이브 코딩으로 실행하기 위한 미니 하네스입니다.

## 빠른 시작

1. `AGENTS.md`를 먼저 읽습니다.
2. `prompts/00-lab-orientation.md`를 Agent에 붙여 넣습니다.
3. `prompts/01-scaffold-workspace.md`부터 `04-smoke-verify.md`까지 순서대로 실행합니다.
4. 3일 과정에서는 `prompts/05-iterate-fix.md`, `skills/orchestrator/SKILL.md`, `docs/task-breakdown.md`를 추가로 사용합니다.
5. 1주 과정에서는 `prompts/06-create-runbook.md`와 `prompts/07-create-roadmap.md`로 운영 산출물을 만듭니다.

## 기간별 산출물

| 기간 | 실행 프롬프트 | 기대 출력 |
| --- | --- | --- |
| 1일 | `00`~`04`, `nondev-skill-draft`, `nondev-workflow` | `workspace/out/launch-readiness-brief-draft.md` |
| 3일 | 1일 + `05`, Orchestrator | `workspace/out/launch-readiness-brief-v1.md`, `workspace/out/pilot-design.md` |
| 1주 | 3일 + `06-create-runbook`, `07-create-roadmap` | `workspace/out/runbook.md`, `workspace/out/roadmap.md` |

## 입력 샘플

- `design_feedback.md`
- `pd_spec_notes.md`
- `channel_launch_plan.csv`

## 핵심 주의

Go/No-Go를 자동 확정하지 않는다. 표시·인증·안전 관련 항목은 반드시 human_review_required로 표시한다.
