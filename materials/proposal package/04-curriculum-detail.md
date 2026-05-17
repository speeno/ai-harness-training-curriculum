# 세부 커리큘럼

## 1. 전체 커리큘럼 구조

본 교육은 공통 소개 세션 이후, 비개발자 트랙과 개발자 트랙으로 나누어 진행됩니다.

| 구성 | 목적 |
| --- | --- |
| 공통 소개 | 문제의식, 핵심 개념, 교육 산출물 이해 |
| 비개발자 트랙 | 업무 시나리오, Skill, Workflow, Workspace, 검증 기준 작성 |
| 개발자 트랙 | `SKILL.md`, Orchestrator, Task, `AGENTS.md`, Smoke Verification 작성 |
| 발표 및 피드백 | 파일럿 가능성, 보완점, 다음 액션 정리 |

---

## 2. 공통 소개 세션

권장 시간: 20~30분

| 주제 | 내용 |
| --- | --- |
| 문제의식 | 개인별 프롬프트, 산출물 혼선, 승인 누락, 검증 부재 |
| 핵심 전환 | Prompt에서 Skill로 |
| 하네스 구조 | Agent, Skill, Workflow, Workspace, Verification |
| 트랙 구분 | 비개발자 = 요구사항, 개발자 = 실행 구조 |
| 산출물 안내 | 교육 후 남는 문서와 템플릿 |

---

## 3. 비개발자 1일 과정

| 시간 | 세션 | 주요 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | 오리엔테이션 | 과정 목표, 자동화 후보 기준 | 업무 후보 메모 |
| 09:30–10:30 | 하네스 개념 | Skill, Workflow, Workspace 이해 | 공통 개념 이해 |
| 10:45–12:00 | Skill 작성 | 업무 매뉴얼 템플릿 작성 | Skill 초안 |
| 13:00–14:00 | Workflow 설계 | 승인·검토 흐름 작성 | Workflow 초안 |
| 14:15–15:30 | Workspace 설계 | 폴더와 파일명 규칙 작성 | Workspace 규칙 |
| 15:45–16:30 | 시나리오 통합 | 1페이지 시나리오 완성 | 업무 시나리오 |
| 16:30–17:00 | 발표·정리 | 피드백과 다음 액션 | 완료 체크리스트 |

### 주요 산출물

- 업무 후보 1건
- 업무 시나리오 1페이지
- Skill 초안
- Workflow 초안
- Workspace 규칙
- 리스크와 검증 체크리스트

---

## 4. 개발자 1일 과정

| 시간 | 세션 | 주요 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | 오리엔테이션 | 하네스 구조와 목표 설명 | 작업 범위 확인 |
| 09:30–10:45 | `SKILL.md` 구조 | 입력·출력·실패 처리 작성 | Skill 초안 |
| 11:00–12:00 | Orchestrator | 단계와 위임 경계 작성 | Orchestrator 초안 |
| 13:00–14:30 | Task/Sub-agent | I/O, 실패 모드, 멱등성 점검 | Task Breakdown |
| 14:45–16:00 | `AGENTS.md` | 저장소 진입점과 금지 경로 작성 | AGENTS 초안 |
| 16:15–17:00 | 검증과 리뷰 | Smoke Verification 작성 | 검증 메모 |

### 주요 산출물

- `SKILL.md`
- Orchestrator Skill
- Task Breakdown
- `AGENTS.md`
- Smoke Verification
- Security Notes

---

## 5. 비개발자 3일 과정

| 일차 | 주제 | 주요 활동 | 산출물 |
| --- | --- | --- | --- |
| Day 1 | 프레이밍과 Skill 언어 맞추기 | 자동화 후보 3~5건 선정, 우선순위화, Skill v1 작성 | 후보 우선순위 표, Skill v1 |
| Day 2 | Workflow와 Governance | 승인·예외 흐름, Workspace 규약, Risk Register 작성 | Workflow, Workspace Guide, Risk Register |
| Day 3 | 파일럿 설계와 발표 | KPI, 성공·중단 조건, 검증 패키지, 발표 | 파일럿 설계서, 검증 체크리스트, 액션 플랜 |

---

## 6. 개발자 3일 과정

| 일차 | 주제 | 주요 활동 | 산출물 |
| --- | --- | --- | --- |
| Day 1 | Skill Package와 계약 | Skill 분리, `SKILL.md`, Orchestrator 초안 | Skill Package |
| Day 2 | Task/Sub-agent 심화 | Task Matrix, Failure Matrix, Retry/Idempotency 설계 | Task Breakdown, Failure Matrix |
| Day 3 | `AGENTS.md`, 검증, Rollout | Smoke Verification, Security Notes, Rollout Checklist | AGENTS.md, Smoke Test, Rollout Checklist |

---

## 7. 비개발자 1주 과정

| 일차 | 주제 | 주요 활동 | 산출물 |
| --- | --- | --- | --- |
| Day 1 | 전략 정렬 | 조직 목표, 자동화 포트폴리오 | 후보 5건 이상, 포트폴리오 |
| Day 2 | Skill 공학 | Skill 표준, 용어집, 금지 행동 | Skill v1.x, 템플릿 |
| Day 3 | Workflow와 Governance | RACI, SLA, 예외 흐름 | Workflow 패키지, RACI |
| Day 4 | Workspace와 검증 | 보존, 접근 권한, 검증 fixture | Workspace Guide, 검증 패키지 |
| Day 5 | 파일럿 패키지 | 스폰서 브리프, 30/60/90일 로드맵 | 브리프, 로드맵 |

---

## 8. 개발자 1주 과정

| 일차 | 주제 | 주요 활동 | 산출물 |
| --- | --- | --- | --- |
| Day 1 | 하네스 표준과 레포 구조 | 기준 레포, ADR, 브랜치 전략 | 참조 레포, ADR |
| Day 2 | Skill 생명주기 | 버전 정책, Skill Package | Skill 표준, 변경 기준 |
| Day 3 | Task/Sub-agent 아키텍처 | Task Graph, Failure Policy | Orchestrator v1, Task Graph |
| Day 4 | AGENTS.md, 보안, 검증 | Security, Logging, Verification Pipeline | AGENTS.md, 검증 전략 |
| Day 5 | 운영과 로드맵 | Runbook, SLO, 기술 로드맵 | Runbook, SLO Draft, Roadmap |

---

## 9. 혼합 과정 운영안

혼합 과정은 비개발자와 개발자가 같은 파일럿 업무를 기준으로 병렬 작업한 뒤, 매일 연결 리뷰를 진행하는 방식입니다.

| 일차 | 비개발자 활동 | 개발자 활동 | 연결 산출물 |
| --- | --- | --- | --- |
| Day 1 | 후보 선정, Skill 초안 | Skill Package 구조 | 업무 Skill → `SKILL.md` |
| Day 2 | Workflow, Workspace, Risk | Orchestrator, Task, Failure Matrix | Workflow → Orchestrator |
| Day 3 | 검증 기준, 파일럿 브리프 | Smoke Test, Rollout Checklist | 검증 체크리스트 → Smoke Verification |
| 1주 과정 Day 4 | Workspace, 보안, 검증 | AGENTS.md, Security, Regression | 운영 규칙 → 검증 체계 |
| 1주 과정 Day 5 | 스폰서 브리프 | Runbook, SLO, 기술 로드맵 | 공동 파일럿 패키지 |

---

## 10. 강의 방식과 실습 방식

| 방식 | 설명 |
| --- | --- |
| 강의 | 핵심 개념과 사례 설명 |
| 실습 | 템플릿 기반 산출물 작성 |
| 페어 리뷰 | 다른 수강생이 읽어도 이해되는지 확인 |
| 발표 | 파일럿 가능성과 보완점 공유 |
| 강사 피드백 | 업무 범위, 검증 기준, 보안 기준 보완 |
| 후속 액션 정리 | 담당자, 일정, 다음 과정 또는 파일럿 연결 |
