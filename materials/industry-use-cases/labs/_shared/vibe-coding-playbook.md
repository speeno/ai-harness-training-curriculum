# 바이브 코딩 공통 플레이북

이 플레이북은 산업별 lab을 Cursor Agent로 실행해 실제 업무 산출물을 만드는 공통 절차입니다. 각 lab은 `AGENTS.md`, `docs/`, `skills/`, `prompts/`, `workspace/`, `tests/smoke/`, `nondev/` 구조를 갖습니다.

## 1. 시작 전 확인

- 실제 고객·환자·직원·거래처 정보는 사용하지 않습니다.
- `workspace/in/` 원본은 수정하지 않습니다.
- 최종 공유 전에는 반드시 사람이 검토합니다.
- 판단 확정이 필요한 항목은 `human_review_required`로 표시합니다.

## 2. Cursor Agent 실행 순서

1. lab의 `README.md`를 읽어 기간(1일·3일·1주)과 트랙(비개발·개발)을 고릅니다.
2. `AGENTS.md`를 Agent에게 먼저 읽게 합니다.
3. `prompts/00-lab-orientation.md`를 붙여 넣어 컨텍스트를 고정합니다.
4. `prompts/01-scaffold-workspace.md`로 입력·출력 경로를 확인합니다.
5. `prompts/02-refine-skill.md`로 업종 Skill을 현재 샘플에 맞게 보강합니다.
6. `prompts/03-run-output.md`로 `workspace/out/`에 실제 산출물을 생성합니다.
7. `prompts/04-smoke-verify.md`로 검증하고, 실패하면 `prompts/05-iterate-fix.md`로 수정합니다.
8. 1주 과정은 `prompts/06-create-runbook.md`와 `prompts/07-create-roadmap.md`로 운영 산출물을 추가합니다.

## 3. 기간별 확장

| 기간 | 핵심 활동 | 산출물 |
| --- | --- | --- |
| 1일 | 단일 업무 시나리오와 Skill 초안 작성 | `workspace/out/{task}-draft.md` |
| 3일 | 파일럿 설계, Risk, Orchestrator, Smoke 확인 | `workspace/out/{task}-v1.md`, `workspace/out/pilot-design.md` |
| 1주 | 운영 모델, Runbook, Roadmap, 다 Skill 포트폴리오 | `workspace/out/runbook.md`, `workspace/out/roadmap.md` |

## 4. 실패 시 처리

- 입력이 부족하면 산출물을 추정하지 말고 누락 목록을 먼저 씁니다.
- 민감 정보가 보이면 처리를 중단하고 `pii_review_required`를 표시합니다.
- 결과가 검증 체크리스트를 통과하지 못하면 Skill의 절차나 출력 계약을 수정합니다.
