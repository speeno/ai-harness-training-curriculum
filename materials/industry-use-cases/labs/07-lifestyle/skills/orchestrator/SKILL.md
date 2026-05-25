# Skill: orchestrator-launch-readiness-brief

## 1. Purpose

`launch-readiness-brief` lab의 3일·1주 과정을 조율합니다. 입력 확인, Skill 실행, Smoke 검증, 파일럿 설계, Runbook·Roadmap 작성을 순서대로 연결합니다.

## 2. Workflow

1. `docs/business-scenario.md`와 `docs/industry-constraints.md`를 읽습니다.
2. `workspace/in/` 입력을 확인합니다.
3. `skills/launch-readiness-brief/SKILL.md`로 `workspace/out/launch-readiness-brief-draft.md`를 만듭니다.
4. `tests/smoke/launch-readiness-brief-smoke.md`로 결과를 검증합니다.
5. 실패 항목이 있으면 Skill 또는 산출물을 수정합니다.
6. 3일 과정이면 `workspace/out/pilot-design.md`를 만듭니다.
7. 1주 과정이면 `workspace/out/runbook.md`와 `workspace/out/roadmap.md`를 만듭니다.

## 3. Output rules

- 최종 산출물은 `workspace/out/`에 저장합니다.
- 중간 판단은 삭제하지 말고 검토 메모에 남깁니다.
- 승인 필요 항목은 `human_review_required`로 표시합니다.

## 4. Test scenario

정상 흐름: 모든 입력 샘플을 읽고 `launch-readiness-brief-draft.md`를 생성한 뒤 Smoke 체크리스트를 통과합니다.

오류 흐름: 필수 입력이 없으면 산출물을 만들지 않고 누락 파일 목록을 작성합니다.
