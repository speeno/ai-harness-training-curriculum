# 04. 개발자 트랙 · 1일 과정 슬라이드 자료

> 과정명: 하네스(Harness) · Agent Skills 기반 기업 AI 교육  
> 트랙: 개발자 1일 핸즈온 랩  
> 권장 시간: 09:00–17:00  
> 대상: 소프트웨어 엔지니어, 플랫폼·DevEx, 데이터·자동화 엔지니어, 내부 도구 개발자  
> 목표: Cursor 기반 하네스에서 **Agent, SKILL.md, Orchestrator, Task/Sub-agent, AGENTS.md, 검증**을 하나의 최소 실행 흐름으로 연결한다.

---

# 1. 슬라이드 전체 구성

| No. | 제목 | 핵심 메시지 | 활동 |
| --- | --- | --- | --- |
| 1 | 개발자 1일 핸즈온 랩 | 오늘은 에이전트 자동화의 최소 하네스를 구성한다 | 소개 |
| 2 | 오늘의 목표 | `SKILL.md`, Orchestrator, Task, `AGENTS.md`, 검증 메모를 만든다 | 목표 공유 |
| 3 | 개발자 트랙의 역할 | 현업 요구사항을 실행 가능하고 검증 가능한 구조로 바꾼다 | 개념 정렬 |
| 4 | 전체 하네스 구조 | Agent, Skill, Orchestrator, Task, Workspace, Verification의 연결 | 구조 설명 |
| 5 | 실습 환경과 기준 레포 | 오늘 사용할 폴더 구조와 작업 흐름을 정한다 | 환경 준비 |
| 6 | Agent 정의 | 에이전트의 목적, 도구 범위, 금지 작업을 정한다 | 설계 |
| 7 | `SKILL.md`란 무엇인가 | 재사용 가능한 지침 단위이자 업무 계약이다 | 강의 |
| 8 | 좋은 `SKILL.md` 구조 | 목적, 트리거, 입력, 절차, 실패 시 행동이 명확해야 한다 | 비교 |
| 9 | 실습 1: `SKILL.md` 초안 작성 | 비개발자 업무 시나리오를 개발자용 Skill로 전환한다 | 작성 실습 |
| 10 | Orchestrator Skill | 여러 Skill과 작업 단계를 조립하는 흐름 제어 문서 | 강의 |
| 11 | 실습 2: Orchestrator 초안 작성 | 하위 단계, 위임 경계, 실패 처리 흐름을 작성한다 | 작성 실습 |
| 12 | Task와 Sub-agent | 언제 작업을 나누고, 언제 별도 에이전트에 위임할지 판단한다 | 강의 |
| 13 | Task 분해 기준 | I/O 계약, 실패 모드, 재시도, 멱등성을 명시한다 | 설계 |
| 14 | 실습 3: Task 분해 노트 작성 | 단일 업무를 3~5개 Task로 분해한다 | 작성 실습 |
| 15 | `AGENTS.md` 포인터 | 저장소 진입점, 금지 경로, 실행 명령을 문서화한다 | 강의 |
| 16 | 실습 4: `AGENTS.md` 초안 작성 | 신규 기여자가 읽을 경로와 실행 명령을 정리한다 | 작성 실습 |
| 17 | 검증 전략 | 결정적 단계는 테스트, 비결정적 단계는 스모크로 확인한다 | 강의 |
| 18 | 실습 5: 스모크 검증 시나리오 작성 | golden path 1건과 기대 로그 키를 정의한다 | 작성 실습 |
| 19 | 보안·로그·운영 주의점 | 시크릿, PII, 경로 노출, 로그 기준을 사전에 정한다 | 점검 |
| 20 | 최종 산출물 리뷰 | 오늘 만든 문서와 코드 스텁을 연결해 본다 | 발표 |
| 21 | 다음 단계 | 3일 과정, 파일럿 브랜치, CI 연계로 확장한다 | 마무리 |

---

# 2. 권장 시간표

| 시간 | 세션 | 주요 내용 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | 오리엔테이션 | 개발자 트랙 목표, 하네스 구조, 오늘의 산출물 | 작업 범위 확인 |
| 09:30–10:45 | `SKILL.md` 구조 | Skill 역할, 트리거, 입력·출력, 실패 처리 | `SKILL.md` 초안 |
| 11:00–12:00 | Orchestrator Skill | 위임 경계, 단계 조립, 실패 흐름 | Orchestrator 초안 |
| 12:00–13:00 | 점심 |  |  |
| 13:00–14:30 | Task / Sub-agent | Task 분해, I/O 계약, 재귀 방지 | Task 분해 노트 |
| 14:45–16:00 | `AGENTS.md` | 저장소 진입점, 명령 포인터, 금지 경로 | `AGENTS.md` 초안 |
| 16:15–17:00 | 검증과 리뷰 | 스모크 시나리오, 로그 키, 최종 발표 | 검증 메모 |

---

# 3. 오늘의 기준 시나리오

개발자 1일 과정에서는 너무 큰 자동화를 만들지 않고, 비개발자 트랙에서 나온 업무 시나리오를 개발자용 하네스 산출물로 전환하는 방식으로 진행한다.

권장 기준 시나리오:

> 회의록 원문을 입력받아 핵심 요약, 결정사항, 액션 아이템을 작성하고, 사람 검토 후 최종 결과를 `_workspace/out`에 저장한다.

이 시나리오는 다음 개발 산출물로 전환된다.

| 비개발자 산출물 | 개발자 산출물 |
| --- | --- |
| 업무 시나리오 | acceptance criteria |
| Skill 초안 | `SKILL.md` |
| Workflow | Orchestrator Skill |
| 사람 검토 지점 | human gate / approval step |
| Workspace 규칙 | file path contract |
| 검증 체크리스트 | smoke test checklist |
| 리스크 레지스터 | failure mode list |

---

# 4. 슬라이드별 상세 원고

---

## Slide 1. 개발자 트랙 · 1일 핸즈온 랩

### 화면 문구

**Agent Skills 기반 최소 하네스 구성하기**

오늘은 다음 요소를 하나의 흐름으로 연결합니다.

- Agent 정의
- `SKILL.md`
- Orchestrator Skill
- Task / Sub-agent 분해
- `AGENTS.md`
- `_workspace` 경로 규칙
- Smoke Verification

### 발표자 메모

오늘 과정은 AI API를 호출하는 단순 예제가 아닙니다.  
핵심은 에이전트가 업무를 수행할 때 어떤 문서를 기준으로 움직이고, 어떤 작업을 나누어 처리하며, 어떤 기준으로 결과를 검증할지 정하는 것입니다.

비개발자 트랙이 업무를 설명 가능한 요구사항으로 정리한다면, 개발자 트랙은 그 요구사항을 실행 가능하고 검증 가능한 하네스로 전환합니다.

---

## Slide 2. 오늘의 목표

### 화면 문구

오늘 하루가 끝나면 다음 산출물을 만듭니다.

1. `SKILL.md` 1개 이상  
2. Orchestrator Skill 초안 1개  
3. Task 분해 노트 1개  
4. `AGENTS.md` 포인터 초안 1개  
5. Smoke Verification 메모 1개  
6. 보안·로그 주의사항 체크리스트

**성공 기준**

작은 업무 1건을 기준으로, 신규 개발자가 읽고 실행 흐름을 이해할 수 있는 최소 하네스를 구성한다.

### 발표자 메모

오늘은 완전한 프로덕션 시스템을 만드는 날이 아닙니다.  
대신 자동화 파일럿으로 확장할 수 있는 최소 구조를 만드는 것이 목표입니다.

문서만 만들고 끝나는 것도 아니고, 코드만 작성하는 것도 아닙니다.  
개발자 트랙에서는 문서와 실행 구조가 연결되어야 합니다.

---

## Slide 3. 개발자 트랙의 역할

### 화면 문구

**핵심 질문**  
에이전트가 안전하게 도구를 쓰고, Skill을 재사용·검증하려면 무엇을 정의해야 하는가?

개발자 트랙의 역할:

- 현업 업무 시나리오를 기술 계약으로 전환한다.
- `SKILL.md`로 재사용 가능한 지침을 만든다.
- Orchestrator로 단계와 위임 경계를 정한다.
- Task와 Sub-agent로 복잡도를 분리한다.
- `AGENTS.md`로 저장소 진입점을 제공한다.
- 검증 스모크와 로그 기준으로 품질을 확인한다.

### 발표자 메모

개발자 트랙에서 가장 중요한 역할은 “AI가 답을 잘하게 만드는 것”이 아닙니다.  
그보다 더 중요한 것은 에이전트가 어떤 경계 안에서, 어떤 입력으로, 어떤 도구를 사용하고, 어떤 결과를 남겨야 하는지 정의하는 것입니다.

즉 개발자는 프롬프트 작성자가 아니라 하네스 설계자에 가깝습니다.

---

## Slide 4. 전체 하네스 구조

### 화면 문구

```text
User Request / Business Scenario
        ↓
Agent Definition
        ↓
SKILL.md
        ↓
Orchestrator Skill
        ↓
Task / Sub-agent
        ↓
_workspace
        ↓
Smoke Verification / Logs
        ↓
Approved Output
```

각 요소의 역할:

| 요소 | 역할 |
| --- | --- |
| Agent Definition | 목적, 도구 범위, 금지 작업 정의 |
| `SKILL.md` | 업무 수행 기준과 절차 정의 |
| Orchestrator | 하위 단계와 위임 순서 정의 |
| Task | 작은 실행 단위로 분해 |
| Sub-agent | 역할이 분리된 전문 실행자 |
| `_workspace` | 입력·작업·출력 파일 계약 |
| Verification | 결과 품질과 로그 기준 확인 |

### 발표자 메모

이 구조에서 중요한 것은 각 요소가 같은 일을 반복하지 않는 것입니다.

Agent Definition은 역할과 도구 범위를 정의합니다.  
`SKILL.md`는 업무 수행 기준을 정의합니다.  
Orchestrator는 흐름과 위임 경계를 정의합니다.  
Task는 실제 실행 단위를 작게 나눕니다.  
`AGENTS.md`는 저장소에서 사람이 무엇을 먼저 읽어야 하는지 안내합니다.

---

## Slide 5. 실습 환경과 기준 레포

### 화면 문구

오늘 사용할 권장 폴더 구조:

```text
agent-harness-lab/
  AGENTS.md
  README.md
  skills/
    meeting-summary/
      SKILL.md
    orchestrator/
      SKILL.md
  workspace/
    in/
    work/
    out/
    archive/
    tmp/
  tests/
    smoke/
      meeting-summary-smoke.md
  docs/
    task-breakdown.md
    security-notes.md
```

오늘의 원칙:

- 완성된 앱보다 기준 구조를 만든다.
- 문서와 실행 경로를 연결한다.
- 모든 결과물은 추후 3일 과정 또는 파일럿 브랜치로 확장 가능해야 한다.

### 발표자 메모

실습 레포는 복잡할 필요가 없습니다.  
중요한 것은 각 파일이 어떤 역할을 하는지 분명해야 한다는 점입니다.

오늘은 최소 구조를 만들고, 그 안에 `SKILL.md`, Orchestrator, Task 설계, `AGENTS.md`, 검증 메모를 배치합니다.

---

## Slide 6. Agent 정의

### 화면 문구

Agent 정의에 포함할 것:

| 항목 | 설명 |
| --- | --- |
| 목적 | 이 에이전트가 해결할 업무 |
| 도구 범위 | 사용할 수 있는 파일, 명령, API |
| 금지 작업 | 접근 금지 경로, 외부 전송, 임의 삭제 등 |
| 출력 원칙 | 결과물 형식과 저장 위치 |
| 실패 시 행동 | 멈춤, 질문, 로그 기록, 사람 승인 요청 |

예시:

```text
이 에이전트는 회의록 요약 업무를 지원한다.
입력은 workspace/in의 원본 파일로 제한한다.
최종 결과는 workspace/out에 Markdown 형식으로 저장한다.
확인되지 않은 정보는 추정하지 않고 “확인 필요”로 표시한다.
```

### 발표자 메모

Agent 정의는 너무 많은 업무를 포함하면 안 됩니다.  
하나의 에이전트가 모든 일을 하게 만들면 유지보수와 검증이 어려워집니다.

개발자 과정에서는 에이전트의 목적, 도구 범위, 금지 작업, 실패 시 행동을 명확히 정의해야 합니다.

---

## Slide 7. `SKILL.md`란 무엇인가

### 화면 문구

`SKILL.md`는 에이전트가 특정 업무를 수행할 때 참고하는 재사용 가능한 지침 단위입니다.

`SKILL.md`는 다음 역할을 합니다.

- 업무 절차를 코드 가까이에 둔다.
- 프롬프트를 개인 지식이 아니라 버전 관리 자산으로 만든다.
- 입력·출력·실패 기준을 명시한다.
- Orchestrator와 Task 설계의 근거가 된다.
- 리뷰와 테스트의 기준이 된다.

### 발표자 메모

`SKILL.md`는 단순 설명 문서가 아닙니다.  
개발자에게는 업무 계약에 가깝습니다.

어떤 입력을 기대하는지, 어떤 출력이 나와야 하는지, 어떤 경우에는 중단해야 하는지 명확히 해야 합니다.  
이 문서가 불명확하면 Orchestrator나 테스트도 불명확해집니다.

---

## Slide 8. 좋은 `SKILL.md` 구조

### 화면 문구

권장 구조:

```markdown
# Skill: Meeting Summary

## Purpose

## When to use

## Inputs

## Output contract

## Procedure

## Constraints

## Failure handling

## Human review

## Examples

## Changelog
```

좋은 `SKILL.md`의 조건:

| 조건 | 설명 |
| --- | --- |
| 목적이 좁다 | 하나의 업무를 명확히 수행한다 |
| 트리거가 있다 | 언제 사용할지 판단 가능하다 |
| 입력이 구체적이다 | 필요한 파일과 데이터가 분명하다 |
| 출력 계약이 있다 | 결과물 구조와 저장 위치가 명확하다 |
| 실패 처리가 있다 | 모호할 때 어떻게 할지 정한다 |
| 예시가 있다 | 정상 입력과 경계 사례를 포함한다 |

### 발표자 메모

좋은 `SKILL.md`는 읽는 사람이 바로 테스트 케이스를 떠올릴 수 있어야 합니다.

예를 들어 입력이 부족한 경우, 민감정보가 포함된 경우, 담당자가 불명확한 경우를 어떻게 처리할지 적혀 있어야 합니다.

---

## Slide 9. 실습 1: `SKILL.md` 초안 작성

### 화면 문구

작성 시간: 45분 / 페어 리뷰: 15분

기준 시나리오:

> 회의록 원문을 입력받아 핵심 요약, 결정사항, 액션 아이템을 Markdown으로 작성한다.

작성 템플릿:

```markdown
# Skill: meeting-summary

## Purpose

## When to use

## Inputs

## Output contract

## Procedure
1.
2.
3.

## Constraints

## Failure handling

## Human review

## Examples

## Changelog
```

리뷰 질문:

- 입력 파일이 명확한가?
- 출력 구조가 테스트 가능하게 정의되었는가?
- 실패 시 행동이 있는가?
- 사람 검토 지점이 있는가?
- 경계 사례가 최소 1개 이상 포함되었는가?

### 발표자 메모

실습에서는 비개발자 Skill 초안을 개발자용 `SKILL.md`로 옮깁니다.

비개발자 문서에는 업무 설명이 많고, 개발자 문서에는 계약과 실패 처리가 더 명확해야 합니다.

---

## Slide 10. Orchestrator Skill

### 화면 문구

Orchestrator Skill은 여러 단계와 Skill을 조립하는 흐름 제어 문서입니다.

역할:

- 어떤 Skill을 어떤 순서로 호출할지 정의
- 단계 간 전달할 컨텍스트 제한
- 실패 시 복구 또는 중단 기준 정의
- 사람 승인 게이트 정의
- 최종 산출물 저장 위치 정의

예시 흐름:

```text
1. 입력 파일 확인
2. meeting-summary Skill 실행
3. action-item-extract 단계 실행
4. human review 요청
5. 승인 시 workspace/out에 저장
6. 실패 시 workspace/work에 상태 기록
```

### 발표자 메모

Orchestrator는 단순히 “이것도 하고 저것도 해”가 아닙니다.  
단계 사이에 어떤 정보를 넘길지, 어떤 정보는 넘기지 않을지, 실패하면 멈출지 재시도할지 정해야 합니다.

---

## Slide 11. 실습 2: Orchestrator 초안 작성

### 화면 문구

작성 시간: 35분 / 공유: 10분

```markdown
# Orchestrator Skill: meeting-summary-flow

## Goal

## Preconditions

## Steps
1. Validate input files
2. Run meeting-summary skill
3. Extract action items
4. Request human review
5. Save approved output

## Context passing rules

## Human gates

## Failure handling

## Output locations
```

작성 포인트:

- 각 단계의 입력과 출력을 분리한다.
- 모든 실패를 재시도하지 않는다.
- 사람 승인 전에는 최종 폴더에 저장하지 않는다.
- 중간 산출물은 `workspace/work`에 둔다.

### 발표자 메모

Orchestrator 작성 시 가장 중요한 것은 “순서”와 “경계”입니다.

특히 사람 검토 전과 후의 상태를 구분해야 합니다.  
승인 전 결과물이 최종 산출물 위치에 들어가면 운영상 혼선이 생길 수 있습니다.

---

## Slide 12. Task와 Sub-agent

### 화면 문구

Task는 작은 실행 단위입니다.  
Sub-agent는 역할이 분리된 전문 실행자입니다.

| 구분 | 사용할 때 | 피해야 할 때 |
| --- | --- | --- |
| Task | 입력·출력이 명확한 작은 단계로 나눌 때 | 단순한 한 문장 작업을 과도하게 쪼갤 때 |
| Sub-agent | 역할, 도구, 컨텍스트가 명확히 분리될 때 | 책임 경계 없이 무한 위임될 때 |

예시:

```text
Task 1: 입력 파일 검증
Task 2: 회의 요약 생성
Task 3: 액션 아이템 추출
Task 4: 민감정보 점검
Task 5: 최종 Markdown 생성
```

### 발표자 메모

Task와 Sub-agent를 쓰는 이유는 복잡도를 낮추기 위해서입니다.  
하지만 너무 많이 나누면 오히려 흐름이 불안정해집니다.

기준은 입력과 출력이 분명한지, 실패했을 때 따로 복구할 가치가 있는지입니다.

---

## Slide 13. Task 분해 기준

### 화면 문구

Task 설계 시 확인할 질문:

| 질문 | 설명 |
| --- | --- |
| 입력은 무엇인가? | 파일, 텍스트, JSON, 메타데이터 |
| 출력은 무엇인가? | 다음 단계가 사용할 수 있는 형태인가? |
| 실패 조건은 무엇인가? | 입력 누락, 형식 오류, 품질 미달 |
| 재시도 가능한가? | 같은 입력으로 반복 실행해도 안전한가? |
| 멱등성이 있는가? | 중복 실행 시 결과가 꼬이지 않는가? |
| 로그로 확인 가능한가? | 성공·실패 판단 키가 있는가? |

Task 카드 템플릿:

```text
Task name:
Input:
Output:
Failure modes:
Retry policy:
Idempotency note:
Log keys:
Owner / reviewer:
```

### 발표자 메모

Task 분해는 구현보다 먼저 설계해야 합니다.

특히 AI가 포함된 작업은 비결정적인 결과가 나올 수 있기 때문에, 성공 여부를 어떻게 판단할지 사전에 정해야 합니다.

---

## Slide 14. 실습 3: Task 분해 노트 작성

### 화면 문구

작성 시간: 35분 / 페어 리뷰: 10분

기준 시나리오를 3~5개 Task로 나눕니다.

| Task | Input | Output | Failure mode | Retry | Log key |
| --- | --- | --- | --- | --- | --- |
| 1 |  |  |  |  |  |
| 2 |  |  |  |  |  |
| 3 |  |  |  |  |  |
| 4 |  |  |  |  |  |
| 5 |  |  |  |  |  |

금지 패턴:

- Task 이름이 너무 추상적임: “처리하기”, “정리하기”
- 입력과 출력이 없음
- 모든 실패를 무조건 재시도함
- Sub-agent가 다시 부모에게 같은 작업을 위임함
- 로그 기준이 없음

### 발표자 메모

이번 실습에서는 실제 코드를 작성하기보다 Task 계약을 명확히 합니다.

각 Task는 다음 Task가 사용할 수 있는 산출물을 만들어야 합니다.  
또한 실패했을 때 멈출지, 재시도할지, 사람에게 넘길지를 구분해야 합니다.

---

## Slide 15. `AGENTS.md` 포인터

### 화면 문구

`AGENTS.md`는 저장소에서 에이전트와 개발자가 먼저 읽어야 할 진입점입니다.

포함할 내용:

- 이 저장소의 목적
- 주요 Skill 위치
- Orchestrator 위치
- 실행 또는 검증 명령
- 금지 경로
- 보안 주의사항
- 작업 전 확인할 문서
- 결과물 저장 위치

예시:

```markdown
# AGENTS.md

## Project purpose

## Read first
- skills/meeting-summary/SKILL.md
- skills/orchestrator/SKILL.md

## Workspace rules
- Do not modify workspace/in originals.
- Save drafts to workspace/work.
- Save approved outputs to workspace/out.

## Commands
- Run smoke checklist: tests/smoke/meeting-summary-smoke.md

## Prohibited actions
- Do not expose PII in logs.
- Do not write final output before human approval.
```

### 발표자 메모

`AGENTS.md`는 저장소의 안내판입니다.

사람 개발자에게도 유용하고, 에이전트에게도 중요합니다.  
어떤 문서를 먼저 읽어야 하는지, 어디에 결과물을 저장해야 하는지, 어떤 경로는 건드리면 안 되는지 알려줍니다.

---

## Slide 16. 실습 4: `AGENTS.md` 초안 작성

### 화면 문구

작성 시간: 30분 / 공유: 10분

```markdown
# AGENTS.md

## Project purpose

## Repository layout

## Read first

## Skills

## Orchestrator

## Workspace rules

## Commands

## Verification

## Security notes

## Prohibited actions
```

체크 질문:

- 신규 기여자가 무엇을 먼저 읽어야 하는가?
- 에이전트가 건드리면 안 되는 경로는 무엇인가?
- 최종 산출물은 어디에 저장해야 하는가?
- 검증 절차는 어디에 있는가?
- 민감정보 처리 기준이 있는가?

### 발표자 메모

`AGENTS.md`는 길 필요가 없습니다.  
중요한 것은 저장소의 진입점과 금지 사항을 명확히 하는 것입니다.

특히 `workspace/in`의 원본 파일을 수정하지 않는 규칙, 승인 전 결과물을 `workspace/out`에 저장하지 않는 규칙을 명시합니다.

---

## Slide 17. 검증 전략

### 화면 문구

AI 에이전트 검증은 두 가지로 나누어 생각합니다.

| 유형 | 검증 방식 | 예시 |
| --- | --- | --- |
| 결정적 단계 | 코드 테스트 | 파일 존재 여부, JSON schema, 경로 규칙 |
| 비결정적 단계 | Smoke checklist | 요약 품질, 필수 항목 포함, 사실 왜곡 여부 |

Smoke Verification에 포함할 것:

- Golden path 입력 1개
- 기대 출력 구조
- 필수 항목 체크
- 실패해야 하는 경계 사례 1개
- 로그에서 확인할 키
- 사람 검토 기준

### 발표자 메모

AI 결과는 완전히 결정적이지 않을 수 있습니다.  
따라서 모든 것을 일반적인 단위 테스트처럼 검증하기는 어렵습니다.

대신 경로, 파일, 스키마처럼 결정적인 부분은 코드 테스트로 확인하고, 요약 품질이나 사실 왜곡 여부처럼 판단이 필요한 부분은 스모크 체크리스트로 확인합니다.

---

## Slide 18. 실습 5: 스모크 검증 시나리오 작성

### 화면 문구

작성 시간: 30분

```markdown
# Smoke Test: meeting-summary

## Scenario

## Input fixture

## Expected output structure

## Required checks
- [ ] Summary exists
- [ ] Decisions are listed
- [ ] Action items include owner and due date
- [ ] Unclear items are marked as “Needs confirmation”
- [ ] No PII is exposed
- [ ] Output is saved to workspace/work before review
- [ ] Final output is saved to workspace/out only after approval

## Failure cases

## Log keys

## Human review criteria
```

로그 키 예시:

```text
task_id
input_file
output_file
status
review_required
approval_status
error_type
```

### 발표자 메모

스모크 검증은 최소한 한 번 실행했을 때 흐름이 정상적으로 돌아가는지 확인하는 기준입니다.

중요한 것은 “좋아 보인다”가 아니라 확인할 항목이 있어야 한다는 점입니다.

---

## Slide 19. 보안·로그·운영 주의점

### 화면 문구

개발자 트랙 최소 보안 체크:

| 영역 | 체크 질문 |
| --- | --- |
| 시크릿 | API key, token이 코드나 로그에 노출되지 않는가? |
| PII | 개인정보가 입력·출력·로그에 남지 않는가? |
| 경로 | 원본 입력 파일을 수정하지 않는가? |
| 로그 | 성공·실패를 추적할 최소 키가 있는가? |
| 승인 | 사람 승인 전 최종 배포되지 않는가? |
| 롤백 | 잘못된 결과를 되돌릴 수 있는가? |
| 권한 | 에이전트가 접근 가능한 범위가 제한되어 있는가? |

### 발표자 메모

개발자 트랙에서는 보안과 로그를 초기에 넣어야 합니다.

나중에 붙이려고 하면 이미 산출물 위치, 로그 구조, 승인 흐름이 굳어져 있어 수정 비용이 커집니다.

오늘은 최소한 시크릿, PII, 경로 수정, 승인 전 배포, 로그 키 정도는 체크합니다.

---

## Slide 20. 최종 산출물 리뷰

### 화면 문구

오늘 완료해야 할 산출물:

- [ ] `skills/meeting-summary/SKILL.md`
- [ ] `skills/orchestrator/SKILL.md`
- [ ] `docs/task-breakdown.md`
- [ ] `AGENTS.md`
- [ ] `tests/smoke/meeting-summary-smoke.md`
- [ ] `docs/security-notes.md`
- [ ] workspace 폴더 구조

리뷰 기준:

| 항목 | 확인 질문 |
| --- | --- |
| Skill | 입력·출력·실패 처리가 명확한가? |
| Orchestrator | 단계와 위임 경계가 명확한가? |
| Task | I/O 계약과 실패 모드가 있는가? |
| AGENTS | 신규 기여자가 읽을 순서가 보이는가? |
| Verification | Golden path와 체크 항목이 있는가? |
| Security | 시크릿·PII·경로 규칙이 반영되었는가? |

### 발표자 메모

마지막에는 코드를 많이 썼는지보다 구조가 연결되어 있는지를 봅니다.

`SKILL.md`에서 정의한 출력이 Orchestrator와 검증 문서에서도 일관되게 사용되는지 확인해야 합니다.

---

## Slide 21. 다음 단계

### 화면 문구

1일 과정 이후 가능한 경로:

1. **3일 개발자 과정 확장**
   - Task·Sub-agent 심화
   - 재시도·멱등성 설계
   - 에이전트 스모크 자동화

2. **비개발자 산출물과 연결**
   - 업무 시나리오를 fixture로 전환
   - 검증 체크리스트를 smoke test로 전환

3. **파일럿 브랜치 생성**
   - 실제 샘플 데이터 적용
   - PR 체크리스트 작성
   - 보안 리뷰 요청

4. **CI / 운영 연계**
   - smoke job 추가
   - 로그 대시보드 설계
   - 롤백 기준 정의

### 발표자 메모

오늘 만든 것은 최소 하네스입니다.

다음 단계에서는 실제 샘플 데이터와 연결하고, CI 또는 내부 검증 절차에 붙이는 작업이 필요합니다.

---

# 5. 실습 산출물 템플릿 요약

## 5.1 `SKILL.md` 템플릿

```markdown
# Skill: [skill-name]

## Purpose

## When to use

## Inputs

## Output contract

## Procedure

## Constraints

## Failure handling

## Human review

## Examples

## Changelog
```

---

## 5.2 Orchestrator Skill 템플릿

```markdown
# Orchestrator Skill: [flow-name]

## Goal

## Preconditions

## Steps

## Context passing rules

## Human gates

## Failure handling

## Output locations
```

---

## 5.3 Task 카드 템플릿

```text
Task name:
Input:
Output:
Failure modes:
Retry policy:
Idempotency note:
Log keys:
Owner / reviewer:
```

---

## 5.4 `AGENTS.md` 템플릿

```markdown
# AGENTS.md

## Project purpose

## Repository layout

## Read first

## Skills

## Orchestrator

## Workspace rules

## Commands

## Verification

## Security notes

## Prohibited actions
```

---

## 5.5 Smoke Verification 템플릿

```markdown
# Smoke Test: [scenario-name]

## Scenario

## Input fixture

## Expected output structure

## Required checks

## Failure cases

## Log keys

## Human review criteria
```

---

# 6. 강사용 진행 팁

## 6.1 오전 운영 팁

- API 호출 구현보다 문서와 계약을 강조한다.
- `SKILL.md`는 프롬프트 파일이 아니라 업무 계약이라는 점을 반복한다.
- 실습 시 입력·출력·실패 처리가 빠지지 않았는지 확인한다.
- 비개발자 산출물이 있다면 반드시 개발자용 문서로 변환해 보게 한다.

## 6.2 오후 운영 팁

- Task를 너무 잘게 쪼개지 않도록 지도한다.
- Sub-agent는 역할과 도구 경계가 명확할 때만 사용하도록 설명한다.
- `AGENTS.md`는 짧더라도 금지 경로와 검증 포인터를 반드시 포함하게 한다.
- 검증은 “정확해 보임”이 아니라 체크 가능한 기준으로 작성하게 한다.

## 6.3 페어 리뷰 방식

각 페어는 서로의 산출물을 보고 아래 질문에 답한다.

| 영역 | 질문 |
| --- | --- |
| Skill | 이 Skill은 하나의 명확한 업무를 다루는가? |
| Input | 필요한 입력과 경로가 명확한가? |
| Output | 출력 구조와 저장 위치가 명확한가? |
| Failure | 실패 시 중단·재시도·사람 검토 기준이 있는가? |
| Orchestrator | 각 단계의 위임 경계가 명확한가? |
| Task | Task별 I/O와 로그 키가 있는가? |
| AGENTS | 신규 기여자가 무엇을 읽어야 하는지 알 수 있는가? |
| Verification | 최소 golden path와 실패 사례가 있는가? |
| Security | 시크릿, PII, 원본 보호 규칙이 있는가? |

---

# 7. 완료 체크리스트

| 항목 | 완료 여부 |
| --- | --- |
| 기준 업무 시나리오가 정해졌는가? | [ ] |
| `SKILL.md` 초안이 작성되었는가? | [ ] |
| `SKILL.md`에 입력·출력·실패 처리가 포함되었는가? | [ ] |
| Orchestrator Skill 초안이 작성되었는가? | [ ] |
| Orchestrator에 사람 승인 게이트가 포함되었는가? | [ ] |
| Task 분해 노트가 작성되었는가? | [ ] |
| 각 Task의 I/O와 실패 모드가 정의되었는가? | [ ] |
| `AGENTS.md` 초안이 작성되었는가? | [ ] |
| `AGENTS.md`에 읽을 문서, 금지 경로, 검증 포인터가 포함되었는가? | [ ] |
| Smoke Verification 메모가 작성되었는가? | [ ] |
| 로그 키가 정의되었는가? | [ ] |
| 시크릿·PII·원본 보호 규칙이 포함되었는가? | [ ] |
| 3일 과정 또는 파일럿으로 넘길 다음 단계가 정리되었는가? | [ ] |

---

# 8. 디자인 방향

- 개발자 대상이므로 폴더 구조, Markdown 템플릿, 흐름도를 적극 사용한다.
- 단, 코드 예제보다 “계약 구조”를 시각화한다.
- 각 슬라이드는 개념 → 예시 → 실습 연결 순서로 구성한다.
- 비개발자 과정과 연결되는 슬라이드에는 “업무 시나리오 → 개발 산출물” 변환표를 넣는다.

권장 시각 요소:

| 슬라이드 | 권장 시각화 |
| --- | --- |
| Slide 4 | 전체 하네스 파이프라인 |
| Slide 5 | 기준 레포 폴더 트리 |
| Slide 8 | `SKILL.md` 구조 카드 |
| Slide 10 | Orchestrator 단계 흐름도 |
| Slide 12 | Task vs Sub-agent 비교표 |
| Slide 14 | Task 카드 표 |
| Slide 15 | `AGENTS.md` 저장소 안내판 이미지 |
| Slide 17 | 결정적 테스트 vs 스모크 검증 비교 |
| Slide 20 | 최종 산출물 체크보드 |

---

# 9. 다음 작업 연결

이 자료 다음에는 다음 항목을 작성한다.

1. 개발자 실습 템플릿
2. 강사용 운영 가이드
3. 평가 체크리스트
4. 3일 과정 확장 자료
5. 1주 과정 확장 자료

