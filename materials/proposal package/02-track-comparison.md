# 비개발자 트랙과 개발자 트랙 비교

## 1. 두 트랙을 나누는 이유

AI 자동화는 현업의 업무 지식과 개발자의 구현 역량이 함께 필요합니다.

비개발자는 업무 절차, 승인 기준, 예외 상황, 리스크를 가장 잘 알고 있습니다. 개발자는 이를 실행 가능한 에이전트 구조, Skill 문서, Task 설계, 검증 체계로 전환할 수 있습니다.

따라서 이 교육은 비개발자 트랙과 개발자 트랙을 구분하되, 두 트랙의 산출물이 서로 연결되도록 설계합니다.

---

## 2. 비개발자 트랙 개요

### 핵심 질문

```text
우리 팀 업무를 어떤 순서와 규칙으로 자동화할 것인가?
```

### 주요 대상

- 기획
- 운영
- PM
- 행정
- 영업 지원
- 품질
- 컴플라이언스
- 변경 관리
- PMO

### 주요 활동

- 자동화 후보 업무 선정
- 업무 시나리오 작성
- Skill 초안 작성
- 승인·검토 Workflow 설계
- `_workspace` 폴더 규칙 정의
- 리스크와 검증 체크리스트 작성

### 대표 산출물

- 업무 시나리오 1페이지
- Skill 초안 또는 Skill v1.x
- Workflow 다이어그램
- `_workspace` 운영 가이드
- 리스크 레지스터
- 검증 체크리스트
- 파일럿 브리프

---

## 3. 개발자 트랙 개요

### 핵심 질문

```text
에이전트가 안전하게 도구를 쓰고, Skill을 재사용·검증하려면 무엇을 정의해야 하는가?
```

### 주요 대상

- 소프트웨어 엔지니어
- 플랫폼 엔지니어
- DevEx 담당자
- 데이터·자동화 엔지니어
- 내부 도구 개발자
- 아키텍트
- 시니어 엔지니어
- 플랫폼 리드

### 주요 활동

- 에이전트 역할과 도구 범위 정의
- `SKILL.md` 작성
- Orchestrator Skill 작성
- Task/Sub-agent 설계
- `AGENTS.md` 작성
- Smoke Verification 설계
- 보안·로그·롤백 기준 작성

### 대표 산출물

- `SKILL.md`
- Orchestrator Skill
- Task Breakdown
- `AGENTS.md`
- Smoke Verification
- Security Notes
- Rollout Checklist
- Runbook

---

## 4. 핵심 개념별 역할 비교

| 구분 | 비개발자 트랙 | 개발자 트랙 |
| --- | --- | --- |
| 핵심 질문 | 어떤 업무를 어떤 절차와 규칙으로 자동화할 것인가? | 에이전트가 안전하게 도구를 쓰고 Skill을 재사용·검증하려면 무엇을 정의해야 하는가? |
| Skill 의미 | 업무 매뉴얼, SOP, 금지 사항 | `SKILL.md`, 입력·출력 계약, 실패 처리 |
| Workflow 의미 | 승인·검토가 포함된 업무 흐름 | Orchestrator, context passing, human gate |
| Workspace 의미 | 입력·초안·최종본을 나누는 폴더 규칙 | 파일 경로 계약, 원본 보호, audit trail |
| 검증 방식 | 체크리스트, 샘플 입력·기대 출력 | Smoke Test, Regression fixture, Log keys |
| 보안 기준 | 민감정보 처리, 승인 전 배포 금지 | PII, secret, log, external call 제한 |
| 운영 기준 | 담당자, 승인자, 보존 규칙 | Runbook, SLO, Rollback, CI |

---

## 5. 산출물 비교

| 산출물 영역 | 비개발자 산출물 | 개발자 산출물 |
| --- | --- | --- |
| 업무 정의 | 업무 시나리오 | Business Scenario / Acceptance Criteria |
| Skill | Skill 초안 / Skill v1.x | `SKILL.md` |
| Workflow | 승인·검토 Workflow | Orchestrator Skill |
| 작업 분해 | 업무 단계표 | Task Breakdown / Task Graph |
| 작업 공간 | `_workspace` 규칙 | Path Contract / Workspace Rules |
| 리스크 | 리스크 레지스터 | Failure Matrix |
| 검증 | 검증 체크리스트 | Smoke Verification / Regression Fixture |
| 보안 | 민감정보 처리 기준 | Security Notes / Logging Standard |
| 운영 | 파일럿 브리프 | Runbook / Rollout Checklist |

---

## 6. 두 트랙의 연결 구조

| 비개발자 산출물 | 개발자 산출물 |
| --- | --- |
| 업무 시나리오 | Business Scenario / Acceptance Criteria |
| Skill 초안 | `SKILL.md` |
| Workflow | Orchestrator Skill |
| 사람 검토 지점 | Human Gate |
| Workspace 규칙 | Path Contract / `AGENTS.md` Rules |
| 리스크 레지스터 | Failure Matrix |
| 검증 체크리스트 | Smoke Verification |
| 샘플 입력·기대 출력 | Test Fixture |
| 승인자 정보 | Review Gate / Approval Record |
| 금지 데이터 기준 | Security Notes |

---

## 7. 혼합 과정 운영 방식

비개발자와 개발자가 함께 참여하는 혼합 과정에서는 비개발자가 업무 요구사항을 정의하고, 개발자가 이를 기술 산출물로 전환합니다.

| 단계 | 비개발자 활동 | 개발자 활동 | 연결 산출물 |
| --- | --- | --- | --- |
| 업무 선정 | 자동화 후보 선정 | 구현 가능성 검토 | 파일럿 후보 |
| Skill 작성 | 업무 Skill 초안 | `SKILL.md` 작성 | Skill 계약 |
| Workflow 작성 | 승인·검토 흐름 | Orchestrator 설계 | Human Gate |
| 검증 작성 | 체크리스트 | Smoke Test | 검증 기준 |
| 발표 | 업무 가치 설명 | 기술 구현성 설명 | 파일럿 패키지 |

---

## 8. 어떤 조직에 어떤 조합이 적합한가

| 조직 상황 | 추천 조합 |
| --- | --- |
| AI 도입 초기 | 비개발자 1일 + 개발자 1일 |
| 현업 업무 후보는 많지만 정리가 안 된 경우 | 비개발자 3일 |
| 요구사항은 있으나 기술 표준이 없는 경우 | 비개발자 3일 후 개발자 3일 |
| 개발 플랫폼 조직이 표준을 만들고 싶은 경우 | 개발자 1주 |
| 전사 AI 자동화 거버넌스를 준비하는 경우 | 비개발자 1주 + 개발자 1주 |
