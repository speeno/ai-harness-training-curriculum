# 유통 고객 VOC 분류·매장 주간 리포트

## 1. 가상 기업 프로필

- **기업명:** (가명) 리테일코리아
- **산업:** 유통
- **조직:** 고객센터, 매장운영팀, 온라인몰 운영, 지역 매니저, 데이터 담당자가 함께 일하는 중견 유통사
- **AI 사용 전제:** 비식별 샘플 데이터만 사용하고, 최종 공유 전 사람이 검토한다.

## 2. 해결할 업무 문제

온라인몰 리뷰, 고객센터 상담 메모, 매장 VOC가 채널별로 흩어져 주간 매장 개선 포인트가 늦게 정리된다.

## 3. 교육 대상·트랙

비개발 70%(고객센터·매장운영·지역 매니저), 개발 30%(데이터·운영 자동화 담당)

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
| Trigger | 매주 금요일 15시, 고객센터·온라인몰·매장 VOC 샘플 취합 완료 |
| Input | 고객센터 상담 메모, 온라인몰 리뷰 CSV, 매장별 개선 요청 메모, 지난주 조치 현황 |
| AI 작업 | VOC를 배송·상품·응대·가격·매장환경으로 분류하고 반복 이슈, 긴급 이슈, 담당 부서를 표시한다. |
| 사람 검토 | 매장운영팀장이 긴급도와 담당 부서를 확인하고 민감 표현을 제거한다. |
| Output | 주간 VOC 분류표와 매장별 개선 리포트 |
| Workspace | `labs/01-retail/workspace/out/voc-store-report-draft.md` |
| 리스크 | 고객 개인정보 노출, 불만 표현을 사실처럼 단정, 매장 귀책을 과도하게 판단 |
| 검증 | `labs/01-retail/tests/smoke/voc-store-report-smoke.md` |

## 7. 실습용 가상 데이터

| 파일 | 설명 |
| --- | --- |
| `voc_online_reviews.csv` | 주 입력 샘플 |
| `callcenter_notes.md` | 보조 메모 |
| `store_feedback.md` | 기준·계획 자료 |

## 8. 교육 중 산출물

| 기간 | 비개발 대표 산출물 | 개발 대표 산출물 |
| --- | --- | --- |
| 1일 | 업무 시나리오 1p, Skill 초안, Workflow, `_workspace` 규칙 | `SKILL.md` 초안, `AGENTS.md`, Smoke 메모 |
| 3일 | 파일럿 설계서, Skill v1, Risk Register | Orchestrator Skill, Verification, Security 메모 |
| 1주 | Runbook 초안, Roadmap, 포트폴리오 항목 | Runbook, 다 Skill 포트폴리오, Roadmap |

## 9. 구현 시 예상 결과물

- `workspace/out/voc-store-report-draft.md`: 주간 VOC 분류표와 매장별 개선 리포트
- `workspace/out/pilot-design.md`: 3일 과정 파일럿 설계서
- `workspace/out/runbook.md`: 1주 과정 운영 Runbook
- `workspace/out/roadmap.md`: 1주 과정 확산 Roadmap

## 10. 파일럿 확장·조직 표준화

- 월간 카테고리별 VOC 트렌드
- 매장 교육 자료 자동 초안
- 상품 MD 개선 요청 브리프

## 11. 리스크·검증·승인

| 리스크 | 대응 |
| --- | --- |
| 고객 개인정보 노출 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 불만 표현을 사실처럼 단정 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |
| 매장 귀책을 과도하게 판단 | Skill과 Smoke에서 확인하고 사람 검토 항목으로 표시 |

## 12. Harness Lab 연결

| 용도 | 경로 |
| --- | --- |
| Lab 루트 | `materials/industry-use-cases/labs/01-retail/` |
| Agent 인스트럭션 | `labs/01-retail/AGENTS.md` |
| 개발자 Skill | `labs/01-retail/skills/voc-store-report/SKILL.md` |
| 바이브 코딩 가이드 | `labs/01-retail/docs/vibe-coding-guide.md` |
| 프롬프트 팩 | `labs/01-retail/prompts/00-lab-orientation.md`부터 순서대로 사용 |
| 기대 결과 | `labs/01-retail/workspace/out/voc-store-report-draft.md` |
