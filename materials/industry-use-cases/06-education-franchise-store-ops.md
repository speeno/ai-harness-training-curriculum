# 교육·프랜차이즈 지점 운영 리포트·교육 자료 표준화

## 1. 가상 기업 프로필

- **기업명:** (가명) 에듀넷 프랜차이즈
- **산업:** 교육·프랜차이즈
- **조직:** 전국 지점을 운영하는 교육 서비스 기업. 본부 운영, 슈퍼바이저, 지점장, 교육 콘텐츠 담당이 협업한다.
- **AI 사용 전제:** 비식별 샘플 데이터만 사용하고, 최종 공유 전 사람이 검토한다.

## 2. 해결할 업무 문제

지점 방문 점검 메모와 교육 자료 개선 요청이 비정형으로 쌓여 본부 공유와 표준화가 느리다.

## 3. 교육 대상·트랙

비개발 80%(본부 운영·슈퍼바이저·지점장), 개발 20%(콘텐츠·운영 도구 담당)

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
| Trigger | 주간 지점 방문 후 점검 메모와 사진 설명 텍스트 업로드 |
| Input | 지점 방문 점검 메모, 교육 자료 개선 요청, 본부 운영 기준 |
| AI 작업 | 시설·상담·수업운영·교재·고객응대로 분류하고 개선 액션과 본부 지원 필요 항목을 정리한다. |
| 사람 검토 | 본부 운영 담당자가 지점 평가 표현과 교육 자료 수정 범위를 확인한다. |
| Output | 지점 운영 리포트와 교육 자료 표준화 초안 |
| Workspace | `labs/06-education-franchise/workspace/out/store-ops-training-report-draft.md` |
| 리스크 | 지점 평가를 단정적으로 표현, 개별 강사·학생 정보 노출, 교육 품질 문제 과장 |
| 검증 | `labs/06-education-franchise/tests/smoke/store-ops-training-report-smoke.md` |

## 7. 실습용 가상 데이터

| 파일 | 설명 |
| --- | --- |
| `visit_notes.md` | 주 입력 샘플 |
| `training_feedback.md` | 보조 메모 |
| `ops_standard.md` | 기준·계획 자료 |

## 8. 교육 중 산출물

| 기간 | 비개발 대표 산출물 | 개발 대표 산출물 |
| --- | --- | --- |
| 1일 | 업무 시나리오 1p, Skill 초안, Workflow, `_workspace` 규칙 | `SKILL.md` 초안, `AGENTS.md`, Smoke 메모 |
| 3일 | 파일럿 설계서, Skill v1, Risk Register | Orchestrator Skill, Verification, Security 메모 |
| 1주 | Runbook 초안, Roadmap, 포트폴리오 항목 | Runbook, 다 Skill 포트폴리오, Roadmap |

## 9. 구현 시 예상 결과물

- `workspace/out/store-ops-training-report-draft.md`: 지점 운영 리포트와 교육 자료 표준화 초안
- `workspace/out/pilot-design.md`: 3일 과정 파일럿 설계서
- `workspace/out/runbook.md`: 1주 과정 운영 Runbook
- `workspace/out/roadmap.md`: 1주 과정 확산 Roadmap

## 10. 파일럿 확장·조직 표준화

- 신규 지점 온보딩 체크리스트
- 교육 자료 변경 이력 관리
- 월간 지점 운영 베스트 프랙티스

## 11. 리스크·검증·승인

| 리스크 | 대응 |
| --- | --- |
| 지점 평가를 단정적으로 표현 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 개별 강사·학생 정보 노출 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 교육 품질 문제 과장 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |

## 12. Harness Lab 연결

| 용도 | 경로 |
| --- | --- |
| Lab 루트 | `materials/industry-use-cases/labs/06-education-franchise/` |
| Agent 인스트럭션 | `labs/06-education-franchise/AGENTS.md` |
| 개발자 Skill | `labs/06-education-franchise/skills/store-ops-training-report/SKILL.md` |
| 바이브 코딩 가이드 | `labs/06-education-franchise/docs/vibe-coding-guide.md` |
| 프롬프트 팩 | `labs/06-education-franchise/prompts/00-lab-orientation.md`부터 순서대로 사용 |
| 기대 결과 | `labs/06-education-franchise/workspace/out/store-ops-training-report-draft.md` |
