# 주간 VOC 분류표와 매장별 개선 리포트 예시

## 1. Overview

이번 주 반복 이슈는 배송 지연과 계산대 대기이며, 강남점은 대기 동선 점검이 필요하다.

## 2. Input files reviewed

- `workspace/in/voc_online_reviews.csv`
- `workspace/in/callcenter_notes.md`
- `workspace/in/store_feedback.md`

## 3. Classification or issue table

| 항목 | 분류 | 근거 | 검토 필요 |
| --- | --- | --- | --- |
| 샘플 1 | 주요 이슈 | 입력 샘플에 반복 언급 | No |
| 샘플 2 | 확인 필요 | 담당자 또는 승인 기준 필요 | human_review_required |

## 4. Items requiring human confirmation

- 매장운영팀장이 긴급도와 담당 부서를 확인하고 민감 표현을 제거한다.

## 5. Recommended next actions

- 담당자가 검토할 항목을 확인합니다.
- 공유 가능한 표현으로 민감 정보를 제거합니다.
- 다음 회의 또는 파일럿 설계서에 반영합니다.

## 6. Review notes

이 파일은 강사용 기대 결과 예시입니다. 실제 교육에서는 `workspace/out/voc-store-report-draft.md`를 새로 생성합니다.
