# Business Scenario

## 1. Scenario name

물류 배송 클레임·예외 처리 리포트

## 2. Business goal

배송 지연·파손·주소 오류 같은 예외가 여러 채널로 들어와 우선순위와 에스컬레이션 기준이 흔들린다.

## 3. Trigger

매일 17시, 당일 클레임 목록과 미처리 예외 목록 취합

## 4. Input materials

| Input | Source | Required | Notes |
| --- | --- | --- | --- |
| 클레임 접수 CSV | `workspace/in/` | Yes | 가상 샘플 |
| 미처리 배송 예외 목록 | `workspace/in/` | Yes | 가상 샘플 |
| 고객사 SLA 메모 | `workspace/in/` | Yes | 가상 샘플 |

## 5. Expected output

일일 예외 처리 브리프와 고객 안내 초안

## 6. Human review point

운영 매니저가 보상·책임 표현과 고객 안내 문구를 승인한다.

## 7. Workspace rule

- 입력: `workspace/in/`
- 최종 결과: `workspace/out/claim-exception-brief-draft.md`
- 기대 예시: `workspace/out/examples/claim-exception-brief-draft.md`

## 8. Main risks

- 보상 책임 단정
- 기사 개인 정보 노출
- SLA 위반 판단 오류

## 9. Acceptance criteria

- [ ] 입력 원본이 수정되지 않았다.
- [ ] 출력이 지정 경로에 있다.
- [ ] 확인 필요 항목이 별도 표시되었다.
- [ ] 민감정보가 제거되었다.
