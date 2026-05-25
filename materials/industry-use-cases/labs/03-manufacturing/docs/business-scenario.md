# Business Scenario

## 1. Scenario name

제조 품질 이슈 로그·생산 회의록

## 2. Business goal

라인별 품질 이슈와 회의 결정사항이 분산되어 원인 후보, 조치 담당, 재발 방지 항목 추적이 늦어진다.

## 3. Trigger

일일 생산 회의 후 품질 로그와 회의 메모 업로드

## 4. Input materials

| Input | Source | Required | Notes |
| --- | --- | --- | --- |
| 라인별 품질 이슈 로그 | `workspace/in/` | Yes | 가상 샘플 |
| 생산 회의록 | `workspace/in/` | Yes | 가상 샘플 |
| 설비 점검 메모 | `workspace/in/` | Yes | 가상 샘플 |

## 5. Expected output

품질 이슈 요약과 생산 회의 액션 아이템

## 6. Human review point

품질 책임자가 원인 후보와 재발 방지 조치 표현을 검토한다.

## 7. Workspace rule

- 입력: `workspace/in/`
- 최종 결과: `workspace/out/quality-meeting-brief-draft.md`
- 기대 예시: `workspace/out/examples/quality-meeting-brief-draft.md`

## 8. Main risks

- 원인을 근거 없이 확정
- 안전 이슈 축소
- 납기 영향 과소평가

## 9. Acceptance criteria

- [ ] 입력 원본이 수정되지 않았다.
- [ ] 출력이 지정 경로에 있다.
- [ ] 확인 필요 항목이 별도 표시되었다.
- [ ] 민감정보가 제거되었다.
