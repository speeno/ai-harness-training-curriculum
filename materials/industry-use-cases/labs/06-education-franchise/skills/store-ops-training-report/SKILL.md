# Skill: store-ops-training-report

## 1. Purpose

지점 방문 점검 메모를 정리해 운영 리포트와 교육 자료 개선 초안을 만든다. 이 업무를 지원합니다. 입력 자료를 읽고 `지점 운영 리포트와 교육 자료 표준화 초안`를 작성하되, 확정 판단이 필요한 항목은 사람 검토 대상으로 분리합니다.

## 2. When to use

Use this skill when:

- `교육·프랜차이즈` 업무에서 지점 운영 리포트와 교육 자료 표준화 초안가 필요할 때
- `workspace/in/`에 관련 샘플 데이터가 준비되어 있을 때
- 교육 중 1일·3일·1주 과정 산출물을 만들 때

Do not use this skill when:

- 실제 민감정보가 비식별 처리되지 않은 상태일 때
- 법적·의료·세무·품질 판단을 자동 확정해야 하는 요청일 때
- 입력 없이 일반적인 업계 설명만 요청할 때

## 3. Inputs

| Input | Required | Expected location | Description |
| --- | --- | --- | --- |
| 지점 방문 점검 메모 | Yes | `workspace/in/` | 가상 실습 입력 |
| 교육 자료 개선 요청 | Yes | `workspace/in/` | 가상 실습 입력 |
| 본부 운영 기준 | Yes | `workspace/in/` | 가상 실습 입력 |

Input rules:

- Do not modify original files in `workspace/in/`.
- If required input is missing, stop and mark the task as `input_missing`.
- If sensitive data is found, mark it as `pii_review_required` and request human review.

## 4. Output contract

The output must be saved as `workspace/out/store-ops-training-report-draft.md` and include:

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
6. Write the output to `workspace/out/store-ops-training-report-draft.md`.
7. Run the smoke checklist in `tests/smoke/store-ops-training-report-smoke.md`.

## 6. Safety and review

개인명·학생 정보는 사용하지 않는다. 지점 평가는 관찰 사실과 개선 후보를 구분한다.

Mark these as `human_review_required`:

- 지점 평가를 단정적으로 표현
- 개별 강사·학생 정보 노출
- 교육 품질 문제 과장
