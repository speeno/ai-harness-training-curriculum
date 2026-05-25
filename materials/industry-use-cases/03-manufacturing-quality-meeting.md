# 제조 품질 이슈 로그·생산 회의록

## 1. 가상 기업 프로필

- **기업명:** (가명) 프리시전 MFG
- **산업:** 제조
- **조직:** 생활·산업 부품을 생산하는 제조사. 생산, 품질, 설비, 구매, 영업 납기 담당이 협업한다.
- **AI 사용 전제:** 비식별 샘플 데이터만 사용하고, 최종 공유 전 사람이 검토한다.

## 2. 해결할 업무 문제

라인별 품질 이슈와 회의 결정사항이 분산되어 원인 후보, 조치 담당, 재발 방지 항목 추적이 늦어진다.

## 3. 교육 대상·트랙

비개발 65%(생산·품질·설비), 개발 35%(MES·데이터 담당)

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
| Trigger | 일일 생산 회의 후 품질 로그와 회의 메모 업로드 |
| Input | 라인별 품질 이슈 로그, 생산 회의록, 설비 점검 메모 |
| AI 작업 | 불량 유형, 영향 라인, 원인 후보, 담당자, 기한, 확인 필요 항목을 구조화한다. |
| 사람 검토 | 품질 책임자가 원인 후보와 재발 방지 조치 표현을 검토한다. |
| Output | 품질 이슈 요약과 생산 회의 액션 아이템 |
| Workspace | `labs/03-manufacturing/workspace/out/quality-meeting-brief-draft.md` |
| 리스크 | 원인을 근거 없이 확정, 안전 이슈 축소, 납기 영향 과소평가 |
| 검증 | `labs/03-manufacturing/tests/smoke/quality-meeting-brief-smoke.md` |

## 7. 실습용 가상 데이터

| 파일 | 설명 |
| --- | --- |
| `quality_log.csv` | 주 입력 샘플 |
| `production_meeting.md` | 보조 메모 |
| `maintenance_notes.md` | 기준·계획 자료 |

## 8. 교육 중 산출물

| 기간 | 비개발 대표 산출물 | 개발 대표 산출물 |
| --- | --- | --- |
| 1일 | 업무 시나리오 1p, Skill 초안, Workflow, `_workspace` 규칙 | `SKILL.md` 초안, `AGENTS.md`, Smoke 메모 |
| 3일 | 파일럿 설계서, Skill v1, Risk Register | Orchestrator Skill, Verification, Security 메모 |
| 1주 | Runbook 초안, Roadmap, 포트폴리오 항목 | Runbook, 다 Skill 포트폴리오, Roadmap |

## 9. 구현 시 예상 결과물

- `workspace/out/quality-meeting-brief-draft.md`: 품질 이슈 요약과 생산 회의 액션 아이템
- `workspace/out/pilot-design.md`: 3일 과정 파일럿 설계서
- `workspace/out/runbook.md`: 1주 과정 운영 Runbook
- `workspace/out/roadmap.md`: 1주 과정 확산 Roadmap

## 10. 파일럿 확장·조직 표준화

- 주간 재발 이슈 트렌드
- 설비 점검 우선순위 브리프
- 고객 납기 영향 보고 초안

## 11. 리스크·검증·승인

| 리스크 | 대응 |
| --- | --- |
| 원인을 근거 없이 확정 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 안전 이슈 축소 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 납기 영향 과소평가 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |

## 12. Harness Lab 연결

| 용도 | 경로 |
| --- | --- |
| Lab 루트 | `materials/industry-use-cases/labs/03-manufacturing/` |
| Agent 인스트럭션 | `labs/03-manufacturing/AGENTS.md` |
| 개발자 Skill | `labs/03-manufacturing/skills/quality-meeting-brief/SKILL.md` |
| 바이브 코딩 가이드 | `labs/03-manufacturing/docs/vibe-coding-guide.md` |
| 프롬프트 팩 | `labs/03-manufacturing/prompts/00-lab-orientation.md`부터 순서대로 사용 |
| 기대 결과 | `labs/03-manufacturing/workspace/out/quality-meeting-brief-draft.md` |
