# 회계·세무 증빙 검토·월마감 메모

## 1. 가상 기업 프로필

- **기업명:** (가명) 밸런스파트너스
- **산업:** 회계·세무
- **조직:** 중소기업 고객을 대행하는 회계·세무 법인. 기장 담당, 세무사, 고객 커뮤니케이션 담당이 협업한다.
- **AI 사용 전제:** 비식별 샘플 데이터만 사용하고, 최종 공유 전 사람이 검토한다.

## 2. 해결할 업무 문제

증빙 누락, 계정과목 불일치, 고객 확인 필요 항목이 월말에 한꺼번에 몰려 담당자별 기준 차이가 커진다.

## 3. 교육 대상·트랙

비개발 80%(기장·세무·고객 담당), 개발 20%(사내 문서 자동화 담당)

## 4. 적용 커리큘럼

| 기간 | 권장 활용 | 이유 |
| --- | --- | --- |
| 1일 | 업무 시나리오와 Skill 초안 | 대표 업무 1건을 빠르게 정의하고 검증 기준을 만든다 |
| 3일 | 파일럿 설계와 Orchestrator | 부서 간 입력·검토·승인 흐름을 연결한다 |
| 1주 | Runbook과 Roadmap | 운영 기준, 재사용 Skill, 확장 후보를 조직 표준으로 정리한다 |

## 5. 커리큘럼별 교육 내용

| 기간 | 모듈 | 강조 개념 | 연결 자료 |
| --- | --- | --- | --- |
| 1일 | 후보 업무 선정, Skill 초안, Workflow | 입력·출력·사람 검토 | `03`, `05` |
| 3일 | Risk, Orchestrator, Smoke | 파일럿 전환성 | `07`, `08` |
| 1주 | Runbook, Roadmap, 운영 모델 | 표준화와 확산 | `09`, `10` |

## 6. 적용 프로젝트(파일럿 주제)

| 항목 | 내용 |
| --- | --- |
| Trigger | 매월 25일, 고객사별 증빙 CSV와 담당자 메모 취합 완료 |
| Input | 증빙 목록 CSV, 전월 마감 메모, 고객사 확인 요청 메모 |
| AI 작업 | 증빙 상태를 누락·금액 불일치·계정 후보·고객 확인으로 분류하고 월마감 확인 메모를 작성한다. |
| 사람 검토 | 담당 세무사가 계정 판단과 고객 질의 문구를 확정한다. |
| Output | 월마감 증빙 점검표와 고객 확인 요청 초안 |
| Workspace | `labs/02-accounting/workspace/out/voucher-monthly-close-draft.md` |
| 리스크 | 세무 판단 자동 확정, 민감 금액 외부 노출, 고객에게 단정적 안내 발송 |
| 검증 | `labs/02-accounting/tests/smoke/voucher-monthly-close-smoke.md` |

## 7. 실습용 가상 데이터

| 파일 | 설명 |
| --- | --- |
| `voucher_list.csv` | 주 입력 샘플 |
| `prior_close_notes.md` | 보조 메모 |
| `client_questions.md` | 기준·계획 자료 |

## 8. 교육 중 산출물

| 기간 | 비개발 대표 산출물 | 개발 대표 산출물 |
| --- | --- | --- |
| 1일 | 업무 시나리오 1p, Skill 초안, Workflow, `_workspace` 규칙 | `SKILL.md` 초안, `AGENTS.md`, Smoke 메모 |
| 3일 | 파일럿 설계서, Skill v1, Risk Register | Orchestrator Skill, Verification, Security 메모 |
| 1주 | Runbook 초안, Roadmap, 포트폴리오 항목 | Runbook, 다 Skill 포트폴리오, Roadmap |

## 9. 구현 시 예상 결과물

- `workspace/out/voucher-monthly-close-draft.md`: 월마감 증빙 점검표와 고객 확인 요청 초안
- `workspace/out/pilot-design.md`: 3일 과정 파일럿 설계서
- `workspace/out/runbook.md`: 1주 과정 운영 Runbook
- `workspace/out/roadmap.md`: 1주 과정 확산 Roadmap

## 10. 파일럿 확장·조직 표준화

- 고객사별 월마감 체크리스트
- 반복 누락 유형 교육 자료
- 분기 신고 준비 리스크 브리프

## 11. 리스크·검증·승인

| 리스크 | 대응 |
| --- | --- |
| 세무 판단 자동 확정 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 민감 금액 외부 노출 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 고객에게 단정적 안내 발송 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |

## 12. Harness Lab 연결

| 용도 | 경로 |
| --- | --- |
| Lab 루트 | `materials/industry-use-cases/labs/02-accounting/` |
| Agent 인스트럭션 | `labs/02-accounting/AGENTS.md` |
| 개발자 Skill | `labs/02-accounting/skills/voucher-monthly-close/SKILL.md` |
| 바이브 코딩 가이드 | `labs/02-accounting/docs/vibe-coding-guide.md` |
| 프롬프트 팩 | `labs/02-accounting/prompts/00-lab-orientation.md`부터 순서대로 사용 |
| 기대 결과 | `labs/02-accounting/workspace/out/voucher-monthly-close-draft.md` |
