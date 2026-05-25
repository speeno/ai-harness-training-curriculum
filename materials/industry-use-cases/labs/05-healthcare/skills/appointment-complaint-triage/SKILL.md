# Skill: appointment-complaint-triage

## 1. Purpose

예약 변경 요청과 민원을 유형별로 분류하고 에스컬레이션 초안을 만든다. 이 업무를 지원합니다. 입력 자료를 읽고 `예약·민원 분류표와 에스컬레이션 메모`를 작성하되, 확정 판단이 필요한 항목은 사람 검토 대상으로 분리합니다.

## 2. When to use

Use this skill when:

- `병원·헬스케어 운영` 업무에서 예약·민원 분류표와 에스컬레이션 메모가 필요할 때
- `workspace/in/`에 관련 샘플 데이터가 준비되어 있을 때
- 교육 중 1일·3일·1주 과정 산출물을 만들 때

Do not use this skill when:

- 실제 민감정보가 비식별 처리되지 않은 상태일 때
- 법적·의료·세무·품질 판단을 자동 확정해야 하는 요청일 때
- 입력 없이 일반적인 업계 설명만 요청할 때

## 3. Inputs

| Input | Required | Expected location | Description |
| --- | --- | --- | --- |
| 예약 변경 요청 목록 | Yes | `workspace/in/` | 가상 실습 입력 |
| 민원 메모 | Yes | `workspace/in/` | 가상 실습 입력 |
| 진료과별 운영 기준 | Yes | `workspace/in/` | 가상 실습 입력 |

Input rules:

- Do not modify original files in `workspace/in/`.
- If required input is missing, stop and mark the task as `input_missing`.
- If sensitive data is found, mark it as `pii_review_required` and request human review.

## 4. Output contract

The output must be saved as `workspace/out/appointment-complaint-triage-draft.md` and include:

1. Overview
2. Input files reviewed
3. Classification or issue table
4. Items requiring human confirmation
5. Recommended next actions
6. Review notes

## 5. Procedure

1. Read `docs/business-scenario.md` and `docs/industry-constraints.md`.
2. Validate that required input files exist in `workspace/in/`.
3. Extract facts only from the input files.
4. Apply the business categories described in the scenario.
5. Separate confirmed facts from hypotheses or review candidates.
6. Write the output to `workspace/out/appointment-complaint-triage-draft.md`.
7. Run the smoke checklist in `tests/smoke/appointment-complaint-triage-smoke.md`.

## 6. Safety and review

의학적 판단을 하지 않는다. 환자 식별 정보는 입력에도 샘플값만 사용하고 출력에서 제거한다.

Mark these as `human_review_required`:

- 의료 조언처럼 보이는 표현
- 개인정보·건강정보 노출
- 긴급 증상 과소평가
