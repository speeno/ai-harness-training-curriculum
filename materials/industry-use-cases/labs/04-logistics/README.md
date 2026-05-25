# 물류 배송 클레임·예외 처리 리포트 Lab

이 lab은 [물류 배송 클레임·예외 처리 리포트](../../04-logistics-claim-exception.md) use case를 Cursor Agent에서 바이브 코딩으로 실행하기 위한 미니 하네스입니다.

## 빠른 시작

1. `AGENTS.md`를 먼저 읽습니다.
2. `prompts/00-lab-orientation.md`를 Agent에 붙여 넣습니다.
3. `prompts/01-scaffold-workspace.md`부터 `04-smoke-verify.md`까지 순서대로 실행합니다.
4. 3일 과정에서는 `prompts/05-iterate-fix.md`, `skills/orchestrator/SKILL.md`, `docs/task-breakdown.md`를 추가로 사용합니다.
5. 1주 과정에서는 `prompts/06-create-runbook.md`와 `prompts/07-create-roadmap.md`로 운영 산출물을 만듭니다.

## 기간별 산출물

| 기간 | 실행 프롬프트 | 기대 출력 |
| --- | --- | --- |
| 1일 | `00`~`04`, `nondev-skill-draft`, `nondev-workflow` | `workspace/out/claim-exception-brief-draft.md` |
| 3일 | 1일 + `05`, Orchestrator | `workspace/out/claim-exception-brief-v1.md`, `workspace/out/pilot-design.md` |
| 1주 | 3일 + `06-create-runbook`, `07-create-roadmap` | `workspace/out/runbook.md`, `workspace/out/roadmap.md` |

## 입력 샘플

- `claims.csv`
- `exceptions.md`
- `sla_notes.md`

## 핵심 주의

보상·책임은 후보로만 표시한다. 기사명·연락처 등 개인 정보는 출력하지 않는다.
