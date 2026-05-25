# Business Scenario

## 1. Scenario name

유통 고객 VOC 분류·매장 주간 리포트

## 2. Business goal

온라인몰 리뷰, 고객센터 상담 메모, 매장 VOC가 채널별로 흩어져 주간 매장 개선 포인트가 늦게 정리된다.

## 3. Trigger

매주 금요일 15시, 고객센터·온라인몰·매장 VOC 샘플 취합 완료

## 4. Input materials

| Input | Source | Required | Notes |
| --- | --- | --- | --- |
| 고객센터 상담 메모 | `workspace/in/` | Yes | 가상 샘플 |
| 온라인몰 리뷰 CSV | `workspace/in/` | Yes | 가상 샘플 |
| 매장별 개선 요청 메모 | `workspace/in/` | Yes | 가상 샘플 |
| 지난주 조치 현황 | `workspace/in/` | Yes | 가상 샘플 |

## 5. Expected output

주간 VOC 분류표와 매장별 개선 리포트

## 6. Human review point

매장운영팀장이 긴급도와 담당 부서를 확인하고 민감 표현을 제거한다.

## 7. Workspace rule

- 입력: `workspace/in/`
- 최종 결과: `workspace/out/voc-store-report-draft.md`
- 기대 예시: `workspace/out/examples/voc-store-report-draft.md`

## 8. Main risks

- 고객 개인정보 노출
- 불만 표현을 사실처럼 단정
- 매장 귀책을 과도하게 판단

## 9. Acceptance criteria

- [ ] 입력 원본이 수정되지 않았다.
- [ ] 출력이 지정 경로에 있다.
- [ ] 확인 필요 항목이 별도 표시되었다.
- [ ] 민감정보가 제거되었다.
