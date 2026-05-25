# Skill: launch-readiness-brief

## 1. Purpose

시즌 SKU 1건의 부서별 산출물을 모아 주간 런칭 준비 브리프를 만든다. 이 업무를 지원합니다. 입력 자료를 읽고 `신제품 런칭 준비 브리프와 부서별 액션 아이템`를 작성하되, 확정 판단이 필요한 항목은 사람 검토 대상으로 분리합니다.

## 2. When to use

Use this skill when:

- `생활용품(디자인~유통 통합)` 업무에서 신제품 런칭 준비 브리프와 부서별 액션 아이템가 필요할 때
- `workspace/in/`에 관련 샘플 데이터가 준비되어 있을 때
- 교육 중 1일·3일·1주 과정 산출물을 만들 때

Do not use this skill when:

- 실제 민감정보가 비식별 처리되지 않은 상태일 때
- 법적·의료·세무·품질 판단을 자동 확정해야 하는 요청일 때
- 입력 없이 일반적인 업계 설명만 요청할 때

## 3. Inputs

| Input | Required | Expected location | Description |
| --- | --- | --- | --- |
| 디자인 시안 피드백 | Yes | `workspace/in/` | 가상 실습 입력 |
| 상품 스펙·샘플 테스트 메모 | Yes | `workspace/in/` | 가상 실습 입력 |
| MOQ·단가 검토표 | Yes | `workspace/in/` | 가상 실습 입력 |
| 채널별 입고·프로모 일정 | Yes | `workspace/in/` | 가상 실습 입력 |

Input rules:

- Do not modify original files in `workspace/in/`.
- If required input is missing, stop and mark the task as `input_missing`.
- If sensitive data is found, mark it as `pii_review_required` and request human review.

## 4. Output contract

The output must be saved as `workspace/out/launch-readiness-brief-draft.md` and include:

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
6. Write the output to `workspace/out/launch-readiness-brief-draft.md`.
7. Run the smoke checklist in `tests/smoke/launch-readiness-brief-smoke.md`.

## 6. Safety and review

Go/No-Go를 자동 확정하지 않는다. 표시·인증·안전 관련 항목은 반드시 human_review_required로 표시한다.

Mark these as `human_review_required`:

- 표시·인증 요구사항 누락
- 원가·MOQ 단정
- 디자인 피드백과 유통 일정 충돌 미표시
