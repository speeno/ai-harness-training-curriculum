# Business Scenario

## 1. Scenario name

병원 예약 변경·민원 분류

## 2. Business goal

예약 변경 요청과 민원이 혼재되어 긴급도, 담당 부서, 환자 안내 문구 정리가 늦어진다.

## 3. Trigger

오전·오후 2회, 비식별 처리된 문의 목록 업로드

## 4. Input materials

| Input | Source | Required | Notes |
| --- | --- | --- | --- |
| 예약 변경 요청 목록 | `workspace/in/` | Yes | 가상 샘플 |
| 민원 메모 | `workspace/in/` | Yes | 가상 샘플 |
| 진료과별 운영 기준 | `workspace/in/` | Yes | 가상 샘플 |

## 5. Expected output

예약·민원 분류표와 에스컬레이션 메모

## 6. Human review point

원무 책임자와 해당 진료과 담당자가 안내 문구와 에스컬레이션 여부를 확인한다.

## 7. Workspace rule

- 입력: `workspace/in/`
- 최종 결과: `workspace/out/appointment-complaint-triage-draft.md`
- 기대 예시: `workspace/out/examples/appointment-complaint-triage-draft.md`

## 8. Main risks

- 의료 조언처럼 보이는 표현
- 개인정보·건강정보 노출
- 긴급 증상 과소평가

## 9. Acceptance criteria

- [ ] 입력 원본이 수정되지 않았다.
- [ ] 출력이 지정 경로에 있다.
- [ ] 확인 필요 항목이 별도 표시되었다.
- [ ] 민감정보가 제거되었다.
