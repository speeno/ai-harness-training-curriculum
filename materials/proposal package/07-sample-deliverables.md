# 교육 산출물 예시

## 1. 산출물 개요

본 교육은 단순 수강이 아니라 실제 파일럿 또는 조직 표준화 논의에 활용할 수 있는 산출물을 남기는 것을 목표로 합니다.

| 과정 | 대표 산출물 |
| --- | --- |
| 1일 과정 | 업무 시나리오, Skill 초안, Workflow, Workspace 규칙 |
| 3일 과정 | 파일럿 설계서, Skill v1, Risk Register, Smoke Verification |
| 1주 과정 | 자동화 포트폴리오, Skill v1.x, Runbook, Roadmap |

---

## 2. 비개발자 산출물 예시

### 업무 시나리오 1페이지 예시

| 항목 | 예시 |
| --- | --- |
| 업무명 | 주간 회의록 요약 및 액션 아이템 정리 |
| Trigger | 회의 종료 후 회의록 또는 녹취록 저장 |
| Input | 회의록 원문, 참석자 목록, 프로젝트명 |
| AI 작업 | 핵심 논의사항, 결정사항, 액션 아이템 추출 |
| 사람 검토 | 팀장이 담당자와 기한 확인 |
| Output | Markdown 형식의 회의 요약 문서 |
| Workspace | `_workspace/out/2026-05-15_meeting-summary_final.md` |
| 리스크 | 담당자 오인식, 기한 누락, 민감 발언 포함 |
| 검증 | 참석자, 액션 아이템, 기한, 결정사항 확인 |

---

### Skill 초안 예시

```markdown
# Skill: 주간 회의록 요약 및 액션 아이템 정리

## 목적
회의록 원문을 바탕으로 핵심 논의사항, 결정사항, 액션 아이템을 정리하여 팀장이 빠르게 검토하고 공유할 수 있도록 돕는다.

## 입력 자료
- 회의록 원문
- 참석자 목록
- 프로젝트명
- 회의 일자

## 처리 절차
1. 입력 자료가 모두 있는지 확인한다.
2. 핵심 논의사항을 3~5개로 요약한다.
3. 결정사항을 별도 항목으로 정리한다.
4. 액션 아이템을 담당자, 기한, 작업 내용으로 구분한다.
5. 확인이 필요한 불명확한 내용을 별도 표시한다.

## 금지 사항
- 회의록에 없는 내용을 추정해서 추가하지 않는다.
- 담당자가 불명확한 경우 임의로 지정하지 않는다.
- 민감한 개인정보는 최종 공유본에 포함하지 않는다.
```

---

## 3. 개발자 산출물 예시

### 개발자 산출물 구조

```text
agent-harness-lab/
  AGENTS.md
  skills/
    meeting-summary/
      SKILL.md
    orchestrator/
      SKILL.md
  workspace/
    in/
    work/
    out/
  tests/
    smoke/
      meeting-summary-smoke.md
  docs/
    task-breakdown.md
    security-notes.md
```

---

### `SKILL.md` 예시

```markdown
# Skill: meeting-summary

## Purpose
Summarize a meeting transcript and produce a structured Markdown document containing key discussion points, decisions, action items, and items requiring human confirmation.

## Inputs
| Input | Required | Expected location |
| --- | --- | --- |
| Meeting transcript | Yes | `workspace/in/` |
| Attendee list | No | `workspace/in/` |

## Output contract
The output must include:
- Overview
- Key Discussion Points
- Decisions
- Action Items
- Items Requiring Confirmation

## Failure handling
| Failure condition | Required behavior |
| --- | --- |
| Required input missing | Stop and request input |
| Owner unclear | Mark as Needs confirmation |
| PII detected | Request human review |
```

---

## 4. 혼합 과정 산출물 예시

| 비개발자 산출물 | 개발자 산출물 |
| --- | --- |
| 업무 시나리오 | Business Scenario / Acceptance Criteria |
| Skill 초안 | `SKILL.md` |
| Workflow | Orchestrator Skill |
| 사람 검토 지점 | Human Gate |
| Workspace 규칙 | `AGENTS.md` Workspace Rules |
| 리스크 레지스터 | Failure Matrix |
| 검증 체크리스트 | Smoke Verification |
| 샘플 입력·기대 출력 | Test Fixture |

---

## 5. 파일럿 패키지 예시

| 파일 | 설명 |
| --- | --- |
| `pilot-brief.md` | 파일럿 목적, 범위, 기대효과, 성공 기준 |
| `skill-v1.md` | 업무 Skill v1 |
| `workflow.md` | 승인·검토 Workflow |
| `workspace-guide.md` | 산출물 저장 규칙 |
| `risk-register.md` | 주요 리스크와 완화 방안 |
| `validation-checklist.md` | 검증 기준 |
| `AGENTS.md` | 개발자용 저장소 진입점 |
| `smoke-test.md` | 기술 검증 기준 |
| `rollout-checklist.md` | 파일럿 실행 전 점검표 |

---

## 6. 산출물 평가 기준

| 평가 항목 | 확인 질문 |
| --- | --- |
| 업무 명확성 | 어떤 업무인지 한 문장으로 설명되는가? |
| 입력·출력 | 필요한 입력과 결과물이 명확한가? |
| Skill 품질 | 절차, 금지 사항, 예외 처리가 포함되어 있는가? |
| Workflow | 사람 검토와 승인 지점이 있는가? |
| Workspace | 원본, 초안, 최종본 위치가 구분되는가? |
| 리스크 | 주요 실패 상황과 완화 방안이 있는가? |
| 검증 | 통과/실패 기준이 있는가? |
| 개발 연결성 | 개발자 산출물로 전환 가능한가? |
