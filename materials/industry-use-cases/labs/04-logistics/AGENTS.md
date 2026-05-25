# AGENTS.md

## 목적

이 lab은 `물류` 산업의 `배송 클레임을 유형·긴급도·담당 부서로 분류하고 일일 예외 처리 브리프를 만든다.` 업무를 Cursor Agent로 실행해 검토 가능한 산출물을 만드는 교육용 하네스입니다.

## 먼저 읽을 파일

1. `docs/business-scenario.md`
2. `docs/industry-constraints.md`
3. `skills/claim-exception-brief/SKILL.md`
4. `prompts/00-lab-orientation.md`

## 작업 규칙

- `workspace/in/` 파일은 수정하지 않습니다.
- 중간 작업은 필요하면 `workspace/work/`에 두고, 최종 결과는 `workspace/out/`에 작성합니다.
- 입력에 없는 사실은 만들지 않습니다.
- 최종 판단, 승인, 법적·의료·세무·품질 판단은 `human_review_required`로 표시합니다.
- 민감정보가 보이면 산출물 생성을 멈추고 검토 필요 상태를 기록합니다.

## 변경 이력

| 날짜 | 변경 내용 | 대상 | 사유 |
| --- | --- | --- | --- |
| 2026-05-25 | 초기 lab 구성 | 전체 | 산업별 교육 실습 |
