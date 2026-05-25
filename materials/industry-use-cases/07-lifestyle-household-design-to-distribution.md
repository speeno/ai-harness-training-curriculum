# 생활용품 통합 신제품 런칭 준비 브리프

## 1. 가상 기업 프로필

- **기업명:** (가명) 라이프앤홈
- **산업:** 생활용품(디자인~유통 통합)
- **조직:** 생활용품을 디자인, 설계, 상품개발, 국내·온라인 유통까지 수행하는 수직 통합 기업. 디자인팀, PD, 품질·원가, 유통, 마케팅이 협업한다.
- **AI 사용 전제:** 비식별 샘플 데이터만 사용하고, 최종 공유 전 사람이 검토한다.

## 2. 해결할 업무 문제

디자인 피드백, 상품 스펙, 샘플 테스트, MOQ·단가, 채널별 입고 일정이 부서별 문서로 흩어져 신제품 Go/No-Go 판단 준비가 늦어진다.

## 3. 교육 대상·트랙

비개발 70%(디자인·PD·마케팅·유통), 개발 30%(상품 데이터·업무 자동화 담당)

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
| Trigger | 주간 상품개발 회의 전날, 부서별 업데이트 메모 업로드 |
| Input | 디자인 시안 피드백, 상품 스펙·샘플 테스트 메모, MOQ·단가 검토표, 채널별 입고·프로모 일정 |
| AI 작업 | 디자인·스펙·품질·원가·유통 준비 상태를 통합하고 의사결정 필요 항목과 담당 부서를 표시한다. |
| 사람 검토 | PD 리더가 표시·인증·원가·런칭 일정 리스크와 Go/No-Go 표현을 승인한다. |
| Output | 신제품 런칭 준비 브리프와 부서별 액션 아이템 |
| Workspace | `labs/07-lifestyle/workspace/out/launch-readiness-brief-draft.md` |
| 리스크 | 표시·인증 요구사항 누락, 원가·MOQ 단정, 디자인 피드백과 유통 일정 충돌 미표시 |
| 검증 | `labs/07-lifestyle/tests/smoke/launch-readiness-brief-smoke.md` |

## 7. 실습용 가상 데이터

| 파일 | 설명 |
| --- | --- |
| `design_feedback.md` | 주 입력 샘플 |
| `pd_spec_notes.md` | 보조 메모 |
| `channel_launch_plan.csv` | 기준·계획 자료 |

## 8. 교육 중 산출물

| 기간 | 비개발 대표 산출물 | 개발 대표 산출물 |
| --- | --- | --- |
| 1일 | 업무 시나리오 1p, Skill 초안, Workflow, `_workspace` 규칙 | `SKILL.md` 초안, `AGENTS.md`, Smoke 메모 |
| 3일 | 파일럿 설계서, Skill v1, Risk Register | Orchestrator Skill, Verification, Security 메모 |
| 1주 | Runbook 초안, Roadmap, 포트폴리오 항목 | Runbook, 다 Skill 포트폴리오, Roadmap |

## 9. 구현 시 예상 결과물

- `workspace/out/launch-readiness-brief-draft.md`: 신제품 런칭 준비 브리프와 부서별 액션 아이템
- `workspace/out/pilot-design.md`: 3일 과정 파일럿 설계서
- `workspace/out/runbook.md`: 1주 과정 운영 Runbook
- `workspace/out/roadmap.md`: 1주 과정 확산 Roadmap

## 10. 파일럿 확장·조직 표준화

- 패키징·라벨 검수
- 리테일 바이어 제안서 초안
- 클레임·회수 대응 브리프

## 11. 리스크·검증·승인

| 리스크 | 대응 |
| --- | --- |
| 표시·인증 요구사항 누락 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 원가·MOQ 단정 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 디자인 피드백과 유통 일정 충돌 미표시 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |

## 12. Harness Lab 연결

| 용도 | 경로 |
| --- | --- |
| Lab 루트 | `materials/industry-use-cases/labs/07-lifestyle/` |
| Agent 인스트럭션 | `labs/07-lifestyle/AGENTS.md` |
| 개발자 Skill | `labs/07-lifestyle/skills/launch-readiness-brief/SKILL.md` |
| 바이브 코딩 가이드 | `labs/07-lifestyle/docs/vibe-coding-guide.md` |
| 프롬프트 팩 | `labs/07-lifestyle/prompts/00-lab-orientation.md`부터 순서대로 사용 |
| 기대 결과 | `labs/07-lifestyle/workspace/out/launch-readiness-brief-draft.md` |
