# Business Scenario

## 1. Scenario name

생활용품 통합 신제품 런칭 준비 브리프

## 2. Business goal

디자인 피드백, 상품 스펙, 샘플 테스트, MOQ·단가, 채널별 입고 일정이 부서별 문서로 흩어져 신제품 Go/No-Go 판단 준비가 늦어진다.

## 3. Trigger

주간 상품개발 회의 전날, 부서별 업데이트 메모 업로드

## 4. Input materials

| Input | Source | Required | Notes |
| --- | --- | --- | --- |
| 디자인 시안 피드백 | `workspace/in/` | Yes | 가상 샘플 |
| 상품 스펙·샘플 테스트 메모 | `workspace/in/` | Yes | 가상 샘플 |
| MOQ·단가 검토표 | `workspace/in/` | Yes | 가상 샘플 |
| 채널별 입고·프로모 일정 | `workspace/in/` | Yes | 가상 샘플 |

## 5. Expected output

신제품 런칭 준비 브리프와 부서별 액션 아이템

## 6. Human review point

PD 리더가 표시·인증·원가·런칭 일정 리스크와 Go/No-Go 표현을 승인한다.

## 7. Workspace rule

- 입력: `workspace/in/`
- 최종 결과: `workspace/out/launch-readiness-brief-draft.md`
- 기대 예시: `workspace/out/examples/launch-readiness-brief-draft.md`

## 8. Main risks

- 표시·인증 요구사항 누락
- 원가·MOQ 단정
- 디자인 피드백과 유통 일정 충돌 미표시

## 9. Acceptance criteria

- [ ] 입력 원본이 수정되지 않았다.
- [ ] 출력이 지정 경로에 있다.
- [ ] 확인 필요 항목이 별도 표시되었다.
- [ ] 민감정보가 제거되었다.
