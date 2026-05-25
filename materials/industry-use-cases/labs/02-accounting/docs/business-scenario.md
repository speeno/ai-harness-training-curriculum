# Business Scenario

## 1. Scenario name

회계·세무 증빙 검토·월마감 메모

## 2. Business goal

증빙 누락, 계정과목 불일치, 고객 확인 필요 항목이 월말에 한꺼번에 몰려 담당자별 기준 차이가 커진다.

## 3. Trigger

매월 25일, 고객사별 증빙 CSV와 담당자 메모 취합 완료

## 4. Input materials

| Input | Source | Required | Notes |
| --- | --- | --- | --- |
| 증빙 목록 CSV | `workspace/in/` | Yes | 가상 샘플 |
| 전월 마감 메모 | `workspace/in/` | Yes | 가상 샘플 |
| 고객사 확인 요청 메모 | `workspace/in/` | Yes | 가상 샘플 |

## 5. Expected output

월마감 증빙 점검표와 고객 확인 요청 초안

## 6. Human review point

담당 세무사가 계정 판단과 고객 질의 문구를 확정한다.

## 7. Workspace rule

- 입력: `workspace/in/`
- 최종 결과: `workspace/out/voucher-monthly-close-draft.md`
- 기대 예시: `workspace/out/examples/voucher-monthly-close-draft.md`

## 8. Main risks

- 세무 판단 자동 확정
- 민감 금액 외부 노출
- 고객에게 단정적 안내 발송

## 9. Acceptance criteria

- [ ] 입력 원본이 수정되지 않았다.
- [ ] 출력이 지정 경로에 있다.
- [ ] 확인 필요 항목이 별도 표시되었다.
- [ ] 민감정보가 제거되었다.
