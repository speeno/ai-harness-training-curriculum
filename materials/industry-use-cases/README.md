# 산업별 가상 Use Case와 Harness Lab

이 폴더는 비IT 기업의 산업별 업무를 하네스(Harness)·Agent Skills 교육에 바로 연결하기 위한 자료입니다. 각 산업은 두 종류의 산출물을 가집니다.

1. **Use case 문서**: 제안·강의에서 사용할 산업별 시나리오, 커리큘럼, 예상 결과물.
2. **Harness Lab 키트**: Cursor Agent에서 바이브 코딩으로 실제 결과물을 만들 수 있는 인스트럭션, Skill, 프롬프트, 샘플 데이터, 검증 자료.

## 사용 순서

1. 아래 표에서 산업과 파일럿 업무를 고릅니다.
2. use case 문서로 교육 목적과 적용 범위를 설명합니다.
3. 연결된 lab 폴더의 `README.md`와 `AGENTS.md`를 읽습니다.
4. `prompts/00`부터 순서대로 Cursor Agent에 붙여 넣어 `workspace/out/` 산출물을 생성합니다.
5. `tests/smoke/`와 `nondev/verification-checklist.md`로 결과를 검증합니다.

## 산업별 매트릭스

| # | 산업 문서 | Lab | 파일럿 업무 | 1일 기대 산출물 |
| --- | --- | --- | --- | --- |
| 01 | [유통](01-retail-voc-store-report.md) | [labs/01-retail](labs/01-retail/) | 채널별 VOC를 유형·긴급도·매장 영향으로 분류하고 주간 매장 이슈 리포트를 만든다. | `voc-store-report-draft.md` |
| 02 | [회계·세무](02-accounting-voucher-monthly-close.md) | [labs/02-accounting](labs/02-accounting/) | 월마감 전 증빙 목록을 검토해 누락·불일치·고객 확인 필요 항목을 정리한다. | `voucher-monthly-close-draft.md` |
| 03 | [제조](03-manufacturing-quality-meeting.md) | [labs/03-manufacturing](labs/03-manufacturing/) | 품질 이슈 로그와 생산 회의 메모를 통합해 조치 항목과 확인 필요 사항을 정리한다. | `quality-meeting-brief-draft.md` |
| 04 | [물류](04-logistics-claim-exception.md) | [labs/04-logistics](labs/04-logistics/) | 배송 클레임을 유형·긴급도·담당 부서로 분류하고 일일 예외 처리 브리프를 만든다. | `claim-exception-brief-draft.md` |
| 05 | [병원·헬스케어 운영](05-healthcare-appointment-complaint.md) | [labs/05-healthcare](labs/05-healthcare/) | 예약 변경 요청과 민원을 유형별로 분류하고 에스컬레이션 초안을 만든다. | `appointment-complaint-triage-draft.md` |
| 06 | [교육·프랜차이즈](06-education-franchise-store-ops.md) | [labs/06-education-franchise](labs/06-education-franchise/) | 지점 방문 점검 메모를 정리해 운영 리포트와 교육 자료 개선 초안을 만든다. | `store-ops-training-report-draft.md` |
| 07 | [생활용품(디자인~유통 통합)](07-lifestyle-household-design-to-distribution.md) | [labs/07-lifestyle](labs/07-lifestyle/) | 시즌 SKU 1건의 부서별 산출물을 모아 주간 런칭 준비 브리프를 만든다. | `launch-readiness-brief-draft.md` |

## 커리큘럼별 활용

| 기간 | 비개발 트랙 | 개발 트랙 | 대표 출력 |
| --- | --- | --- | --- |
| 1일 | `nondev/skill-draft.md`, `nondev/workflow.md`, `nondev/verification-checklist.md` 작성 | `skills/{task}/SKILL.md`와 `AGENTS.md` 이해 | 업무 초안 리포트 |
| 3일 | Risk와 파일럿 설계까지 확장 | `skills/orchestrator/SKILL.md`, `tests/smoke/`로 검증 | 파일럿 설계서, v1 결과물 |
| 1주 | Runbook·Roadmap으로 운영화 | 다 Skill 포트폴리오와 운영 검증 | Runbook, Roadmap |

## 공통 자료

- [labs/_shared/vibe-coding-playbook.md](labs/_shared/vibe-coding-playbook.md)
- [labs/_shared/prompt-template.md](labs/_shared/prompt-template.md)
- [labs/_shared/nondev-skill-template.md](labs/_shared/nondev-skill-template.md)
- [labs/_shared/verification-template.md](labs/_shared/verification-template.md)

## 기존 자료 연결

- 전체 흐름: [../01_overall_training_intro_material.md](../01_overall_training_intro_material.md)
- 비개발 워크북: [../03_non_developer_1_day_workbook_complete.md](../03_non_developer_1_day_workbook_complete.md)
- 개발자 실습 템플릿: [../05_developer_1_day_practice_templates.md](../05_developer_1_day_practice_templates.md)
- 평가 체크리스트: [../07_evaluation_checklist.md](../07_evaluation_checklist.md)
