# 예약·민원 분류표와 에스컬레이션 메모 예시

## 1. Overview

예약 변경 1건, 응대 민원 1건, 진료과 확인 필요 1건으로 분류되며 의료 판단 문구는 제외한다.

## 2. Input files reviewed

- `workspace/in/appointment_requests.md`
- `workspace/in/complaint_notes.md`
- `workspace/in/department_rules.md`

## 3. Classification or issue table

| 항목 | 분류 | 근거 | 검토 필요 |
| --- | --- | --- | --- |
| 샘플 1 | 주요 이슈 | 입력 샘플에 반복 언급 | No |
| 샘플 2 | 확인 필요 | 담당자 또는 승인 기준 필요 | human_review_required |

## 4. Items requiring human confirmation

- 원무 책임자와 해당 진료과 담당자가 안내 문구와 에스컬레이션 여부를 확인한다.

## 5. Recommended next actions

- 담당자가 검토할 항목을 확인합니다.
- 공유 가능한 표현으로 민감 정보를 제거합니다.
- 다음 회의 또는 파일럿 설계서에 반영합니다.

## 6. Review notes

이 파일은 강사용 기대 결과 예시입니다. 실제 교육에서는 `workspace/out/appointment-complaint-triage-draft.md`를 새로 생성합니다.
