# Business Scenario

## 1. Scenario name

교육·프랜차이즈 지점 운영 리포트·교육 자료 표준화

## 2. Business goal

지점 방문 점검 메모와 교육 자료 개선 요청이 비정형으로 쌓여 본부 공유와 표준화가 느리다.

## 3. Trigger

주간 지점 방문 후 점검 메모와 사진 설명 텍스트 업로드

## 4. Input materials

| Input | Source | Required | Notes |
| --- | --- | --- | --- |
| 지점 방문 점검 메모 | `workspace/in/` | Yes | 가상 샘플 |
| 교육 자료 개선 요청 | `workspace/in/` | Yes | 가상 샘플 |
| 본부 운영 기준 | `workspace/in/` | Yes | 가상 샘플 |

## 5. Expected output

지점 운영 리포트와 교육 자료 표준화 초안

## 6. Human review point

본부 운영 담당자가 지점 평가 표현과 교육 자료 수정 범위를 확인한다.

## 7. Workspace rule

- 입력: `workspace/in/`
- 최종 결과: `workspace/out/store-ops-training-report-draft.md`
- 기대 예시: `workspace/out/examples/store-ops-training-report-draft.md`

## 8. Main risks

- 지점 평가를 단정적으로 표현
- 개별 강사·학생 정보 노출
- 교육 품질 문제 과장

## 9. Acceptance criteria

- [ ] 입력 원본이 수정되지 않았다.
- [ ] 출력이 지정 경로에 있다.
- [ ] 확인 필요 항목이 별도 표시되었다.
- [ ] 민감정보가 제거되었다.
