# 물류 배송 클레임·예외 처리 리포트

## 1. 가상 기업 프로필

- **기업명:** (가명) 넥스트로지스
- **산업:** 물류
- **조직:** B2B 물류 운영사. 고객지원, 배차, 창고, 현장 기사 관리, 정산 담당이 협업한다.
- **AI 사용 전제:** 비식별 샘플 데이터만 사용하고, 최종 공유 전 사람이 검토한다.

## 2. 해결할 업무 문제

배송 지연·파손·주소 오류 같은 예외가 여러 채널로 들어와 우선순위와 에스컬레이션 기준이 흔들린다.

## 3. 교육 대상·트랙

비개발 75%(고객지원·배차·창고), 개발 25%(운영 시스템 담당)

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
| Trigger | 매일 17시, 당일 클레임 목록과 미처리 예외 목록 취합 |
| Input | 클레임 접수 CSV, 미처리 배송 예외 목록, 고객사 SLA 메모 |
| AI 작업 | 파손·지연·오배송·주소오류·고객부재로 분류하고 SLA 영향과 우선 처리 대상을 표시한다. |
| 사람 검토 | 운영 매니저가 보상·책임 표현과 고객 안내 문구를 승인한다. |
| Output | 일일 예외 처리 브리프와 고객 안내 초안 |
| Workspace | `labs/04-logistics/workspace/out/claim-exception-brief-draft.md` |
| 리스크 | 보상 책임 단정, 기사 개인 정보 노출, SLA 위반 판단 오류 |
| 검증 | `labs/04-logistics/tests/smoke/claim-exception-brief-smoke.md` |

## 7. 실습용 가상 데이터

| 파일 | 설명 |
| --- | --- |
| `claims.csv` | 주 입력 샘플 |
| `exceptions.md` | 보조 메모 |
| `sla_notes.md` | 기준·계획 자료 |

## 8. 교육 중 산출물

| 기간 | 비개발 대표 산출물 | 개발 대표 산출물 |
| --- | --- | --- |
| 1일 | 업무 시나리오 1p, Skill 초안, Workflow, `_workspace` 규칙 | `SKILL.md` 초안, `AGENTS.md`, Smoke 메모 |
| 3일 | 파일럿 설계서, Skill v1, Risk Register | Orchestrator Skill, Verification, Security 메모 |
| 1주 | Runbook 초안, Roadmap, 포트폴리오 항목 | Runbook, 다 Skill 포트폴리오, Roadmap |

## 9. 구현 시 예상 결과물

- `workspace/out/claim-exception-brief-draft.md`: 일일 예외 처리 브리프와 고객 안내 초안
- `workspace/out/pilot-design.md`: 3일 과정 파일럿 설계서
- `workspace/out/runbook.md`: 1주 과정 운영 Runbook
- `workspace/out/roadmap.md`: 1주 과정 확산 Roadmap

## 10. 파일럿 확장·조직 표준화

- 고객사별 SLA 리스크 리포트
- 반복 주소 오류 정리
- 정산 이슈 사전 점검

## 11. 리스크·검증·승인

| 리스크 | 대응 |
| --- | --- |
| 보상 책임 단정 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 기사 개인 정보 노출 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| SLA 위반 판단 오류 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |

## 12. Harness Lab 연결

| 용도 | 경로 |
| --- | --- |
| Lab 루트 | `materials/industry-use-cases/labs/04-logistics/` |
| Agent 인스트럭션 | `labs/04-logistics/AGENTS.md` |
| 개발자 Skill | `labs/04-logistics/skills/claim-exception-brief/SKILL.md` |
| 바이브 코딩 가이드 | `labs/04-logistics/docs/vibe-coding-guide.md` |
| 프롬프트 팩 | `labs/04-logistics/prompts/00-lab-orientation.md`부터 순서대로 사용 |
| 기대 결과 | `labs/04-logistics/workspace/out/claim-exception-brief-draft.md` |
