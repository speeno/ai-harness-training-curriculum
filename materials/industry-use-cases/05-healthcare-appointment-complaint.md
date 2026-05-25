# 병원 예약 변경·민원 분류

## 1. 가상 기업 프로필

- **기업명:** (가명) 케어링크 병원
- **산업:** 병원·헬스케어 운영
- **조직:** 다과목 외래 병원. 원무, 콜센터, 간호 행정, 진료과 코디네이터가 협업한다.
- **AI 사용 전제:** 비식별 샘플 데이터만 사용하고, 최종 공유 전 사람이 검토한다.

## 2. 해결할 업무 문제

예약 변경 요청과 민원이 혼재되어 긴급도, 담당 부서, 환자 안내 문구 정리가 늦어진다.

## 3. 교육 대상·트랙

비개발 85%(원무·콜센터·간호 행정), 개발 15%(보안 승인된 운영 자동화 담당)

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
| Trigger | 오전·오후 2회, 비식별 처리된 문의 목록 업로드 |
| Input | 예약 변경 요청 목록, 민원 메모, 진료과별 운영 기준 |
| AI 작업 | 예약 변경, 대기, 비용 문의, 응대 민원, 의료진 확인 필요로 분류하고 안내 초안을 작성한다. |
| 사람 검토 | 원무 책임자와 해당 진료과 담당자가 안내 문구와 에스컬레이션 여부를 확인한다. |
| Output | 예약·민원 분류표와 에스컬레이션 메모 |
| Workspace | `labs/05-healthcare/workspace/out/appointment-complaint-triage-draft.md` |
| 리스크 | 의료 조언처럼 보이는 표현, 개인정보·건강정보 노출, 긴급 증상 과소평가 |
| 검증 | `labs/05-healthcare/tests/smoke/appointment-complaint-triage-smoke.md` |

## 7. 실습용 가상 데이터

| 파일 | 설명 |
| --- | --- |
| `appointment_requests.md` | 주 입력 샘플 |
| `complaint_notes.md` | 보조 메모 |
| `department_rules.md` | 기준·계획 자료 |

## 8. 교육 중 산출물

| 기간 | 비개발 대표 산출물 | 개발 대표 산출물 |
| --- | --- | --- |
| 1일 | 업무 시나리오 1p, Skill 초안, Workflow, `_workspace` 규칙 | `SKILL.md` 초안, `AGENTS.md`, Smoke 메모 |
| 3일 | 파일럿 설계서, Skill v1, Risk Register | Orchestrator Skill, Verification, Security 메모 |
| 1주 | Runbook 초안, Roadmap, 포트폴리오 항목 | Runbook, 다 Skill 포트폴리오, Roadmap |

## 9. 구현 시 예상 결과물

- `workspace/out/appointment-complaint-triage-draft.md`: 예약·민원 분류표와 에스컬레이션 메모
- `workspace/out/pilot-design.md`: 3일 과정 파일럿 설계서
- `workspace/out/runbook.md`: 1주 과정 운영 Runbook
- `workspace/out/roadmap.md`: 1주 과정 확산 Roadmap

## 10. 파일럿 확장·조직 표준화

- 진료과별 FAQ 초안
- 반복 민원 개선 리포트
- 예약 대기 관리 브리프

## 11. 리스크·검증·승인

| 리스크 | 대응 |
| --- | --- |
| 의료 조언처럼 보이는 표현 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 개인정보·건강정보 노출 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 긴급 증상 과소평가 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |

## 12. Harness Lab 연결

| 용도 | 경로 |
| --- | --- |
| Lab 루트 | `materials/industry-use-cases/labs/05-healthcare/` |
| Agent 인스트럭션 | `labs/05-healthcare/AGENTS.md` |
| 개발자 Skill | `labs/05-healthcare/skills/appointment-complaint-triage/SKILL.md` |
| 바이브 코딩 가이드 | `labs/05-healthcare/docs/vibe-coding-guide.md` |
| 프롬프트 팩 | `labs/05-healthcare/prompts/00-lab-orientation.md`부터 순서대로 사용 |
| 기대 결과 | `labs/05-healthcare/workspace/out/appointment-complaint-triage-draft.md` |
