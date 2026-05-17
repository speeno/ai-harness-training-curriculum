# 05. 개발자 트랙 · 1일 과정 실습 템플릿

> 과정명: 하네스(Harness) · Agent Skills 기반 기업 AI 교육  
> 트랙: 개발자 1일 핸즈온 랩  
> 목적: 작은 업무 시나리오 1건을 기준으로 `SKILL.md`, Orchestrator, Task 분해, `AGENTS.md`, Smoke Verification, 보안 메모를 작성한다.

---

# 0. 템플릿 사용 방법

이 문서는 개발자 1일 과정에서 바로 사용할 수 있는 실습 템플릿 모음입니다.

수강생은 아래 순서대로 파일을 작성합니다.

1. 기준 업무 시나리오 확인
2. 레포 폴더 구조 생성
3. `SKILL.md` 작성
4. Orchestrator Skill 작성
5. Task 분해 노트 작성
6. `AGENTS.md` 작성
7. Smoke Verification 작성
8. 보안·로그 메모 작성
9. 최종 리뷰 체크리스트 작성

---

# 1. 권장 실습 레포 구조

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
      .gitkeep
    work/
      .gitkeep
    out/
      .gitkeep
    archive/
      .gitkeep
    tmp/
      .gitkeep
  tests/
    smoke/
      meeting-summary-smoke.md
  docs/
    business-scenario.md
    task-breakdown.md
    security-notes.md
    review-checklist.md
```

---

# 2. 기준 업무 시나리오 템플릿

파일 위치 예시:

```text
docs/business-scenario.md
```

```markdown
# Business Scenario

## 1. Scenario name


## 2. Business goal


## 3. Trigger


## 4. Input materials

| Input | Source | Required | Notes |
| --- | --- | --- | --- |
|  |  | Yes / No |  |
|  |  | Yes / No |  |

## 5. Expected output


## 6. Human review point


## 7. Workspace rule


## 8. Main risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
|  |  |  |
|  |  |  |

## 9. Acceptance criteria

- [ ]
- [ ]
- [ ]

## 10. Notes


```

---

# 3. `SKILL.md` 템플릿

파일 위치 예시:

```text
skills/meeting-summary/SKILL.md
```

```markdown
# Skill: meeting-summary

## 1. Purpose

Describe the specific business task this skill supports.

Example:

This skill summarizes a meeting transcript and produces a structured Markdown document containing key discussion points, decisions, action items, and items requiring human confirmation.

## 2. When to use

Use this skill when:

-
-
-

Do not use this skill when:

-
-
-

## 3. Inputs

| Input | Required | Expected location | Description |
| --- | --- | --- | --- |
| Meeting transcript | Yes | `workspace/in/` | Original meeting transcript or notes |
| Attendee list | No | `workspace/in/` | List of participants, if available |
| Project metadata | No | `workspace/in/` | Project name, meeting date, team name |

Input rules:

- Do not modify original files in `workspace/in/`.
- If required input is missing, stop and mark the task as `input_missing`.
- If sensitive data is found, mark it as `pii_review_required` and request human review.

## 4. Output contract

The output must be a Markdown file with the following structure:

```markdown
# Meeting Summary

## 1. Overview

## 2. Key Discussion Points

## 3. Decisions

## 4. Action Items

| Owner | Action | Due date | Confidence | Notes |
| --- | --- | --- | --- | --- |

## 5. Items Requiring Confirmation

## 6. Review Notes
```

Output location rules:

- Draft output must be saved to `workspace/work/`.
- Final output must be saved to `workspace/out/` only after human approval.
- Temporary extraction files must be saved to `workspace/tmp/` and removed or archived according to project policy.

## 5. Procedure

1. Validate that required input files exist in `workspace/in/`.
2. Read the meeting transcript without modifying the original file.
3. Extract key discussion points.
4. Identify explicit decisions.
5. Extract action items with owner, task, due date, and confidence.
6. Mark unclear owners, missing due dates, or ambiguous decisions as `Needs confirmation`.
7. Check whether sensitive or personally identifiable information appears in the output.
8. Save the draft output to `workspace/work/`.
9. Request human review before moving or copying any result to `workspace/out/`.

## 6. Constraints

- Do not invent decisions that are not present in the input.
- Do not assign an owner if the owner is unclear.
- Do not infer a due date unless explicitly stated.
- Do not expose sensitive personal data in output or logs.
- Do not overwrite original files.
- Do not save unapproved drafts to `workspace/out/`.

## 7. Failure handling

| Failure condition | Required behavior | Status label |
| --- | --- | --- |
| Required input file missing | Stop and request input | `input_missing` |
| Input file unreadable | Stop and log file path only | `input_unreadable` |
| Owner or due date unclear | Mark as confirmation required | `needs_confirmation` |
| Sensitive data detected | Request human review | `pii_review_required` |
| Output contract cannot be satisfied | Save partial draft and flag review | `output_incomplete` |

## 8. Human review

Human review is required before final output is saved to `workspace/out/`.

Reviewer should check:

- [ ] Summary reflects the original transcript.
- [ ] Decisions are explicitly supported by the input.
- [ ] Action items include correct owner and due date where available.
- [ ] Unclear items are marked as `Needs confirmation`.
- [ ] No sensitive data is exposed.
- [ ] Final file name follows the project naming rule.

## 9. Examples

### Example input

```text
Meeting transcript: [sample transcript path]
Attendee list: [sample attendee list path]
```

### Example output

```markdown
# Meeting Summary

## 1. Overview

...

## 4. Action Items

| Owner | Action | Due date | Confidence | Notes |
| --- | --- | --- | --- | --- |
| Kim | Send revised proposal | 2026-05-20 | High | Explicitly stated |
| Needs confirmation | Confirm budget owner | Not specified | Low | Owner unclear |
```

## 10. Changelog

| Version | Date | Change |
| --- | --- | --- |
| v0.1 | YYYY-MM-DD | Initial draft |
```

---

# 4. Orchestrator Skill 템플릿

파일 위치 예시:

```text
skills/orchestrator/SKILL.md
```

```markdown
# Orchestrator Skill: meeting-summary-flow

## 1. Goal

Coordinate the end-to-end meeting summary workflow from input validation to human review and approved output storage.

## 2. Preconditions

- [ ] Required input files are placed in `workspace/in/`.
- [ ] `skills/meeting-summary/SKILL.md` exists.
- [ ] Workspace folders exist: `in`, `work`, `out`, `archive`, `tmp`.
- [ ] Human reviewer is identified.
- [ ] Sensitive data handling rule is known.

## 3. Workflow steps

| Step | Name | Skill / Task | Input | Output | Next step |
| --- | --- | --- | --- | --- | --- |
| 1 | Validate input | Task | `workspace/in/` | validation status | Step 2 or stop |
| 2 | Generate draft summary | `meeting-summary` | transcript | draft Markdown | Step 3 |
| 3 | Extract review flags | Task | draft Markdown | review notes | Step 4 |
| 4 | Request human review | Human gate | draft + review notes | approval status | Step 5 or Step 2 |
| 5 | Save approved output | Task | approved draft | final Markdown | End |

## 4. Context passing rules

- Pass only required input file paths and structured notes between steps.
- Do not pass full sensitive content to logs.
- Do not pass temporary extraction files to final output unless explicitly needed.
- Do not move files from `workspace/work/` to `workspace/out/` without approval.

## 5. Human gates

| Gate | Trigger | Reviewer | Required decision |
| --- | --- | --- | --- |
| Review draft | Draft summary generated |  | Approve / Request changes / Reject |
| PII review | Sensitive data detected |  | Mask / Remove / Approve exception |

## 6. Failure handling

| Failure | Behavior | Retry? | Escalation |
| --- | --- | --- | --- |
| Missing input | Stop and request input | No | Requester |
| Draft quality insufficient | Return to summary step | Yes, once | Reviewer |
| PII detected | Stop finalization | No | Security / reviewer |
| Approval rejected | Keep draft in `workspace/work/` | No | Owner |
| Output save failed | Retry save operation | Yes, once | Developer |

## 7. Output locations

| Output type | Location | Rule |
| --- | --- | --- |
| Original input | `workspace/in/` | Read-only |
| Draft | `workspace/work/` | Before review |
| Temporary files | `workspace/tmp/` | Clean up or archive |
| Approved final | `workspace/out/` | After approval only |
| Completed package | `workspace/archive/` | Optional |

## 8. Completion criteria

- [ ] Final output exists in `workspace/out/`.
- [ ] Human approval is recorded.
- [ ] Draft remains traceable in `workspace/work/` or archive.
- [ ] No sensitive data appears in logs.
- [ ] Smoke checklist passes.

## 9. Changelog

| Version | Date | Change |
| --- | --- | --- |
| v0.1 | YYYY-MM-DD | Initial draft |
```

---

# 5. Task 분해 노트 템플릿

파일 위치 예시:

```text
docs/task-breakdown.md
```

```markdown
# Task Breakdown: meeting-summary-flow

## 1. Overview

This document breaks the workflow into small tasks with explicit input, output, failure mode, retry policy, and log keys.

## 2. Task list

| Task ID | Task name | Purpose | Owner |
| --- | --- | --- | --- |
| T1 | Validate input files | Ensure required input exists |  |
| T2 | Generate meeting summary draft | Create structured draft |  |
| T3 | Extract review flags | Identify unclear or risky items |  |
| T4 | Human review gate | Confirm quality and approval |  |
| T5 | Save approved output | Store final result |  |

---

## 3. Task cards

### Task T1 — Validate input files

| Field | Description |
| --- | --- |
| Input | `workspace/in/` file list |
| Output | validation result |
| Success condition | Required transcript exists and is readable |
| Failure modes | missing file, unreadable file, unsupported format |
| Retry policy | No retry for missing file; one retry for transient read error |
| Idempotency note | Safe to run multiple times; does not modify files |
| Log keys | `task_id`, `input_file`, `status`, `error_type` |
| Human escalation | Request missing file from owner |

### Task T2 — Generate meeting summary draft

| Field | Description |
| --- | --- |
| Input | Validated transcript file path |
| Output | Draft Markdown in `workspace/work/` |
| Success condition | Draft contains overview, discussion points, decisions, action items |
| Failure modes | low quality summary, missing required sections, model error |
| Retry policy | Retry once with stricter output contract |
| Idempotency note | New draft version must not overwrite prior draft |
| Log keys | `task_id`, `draft_file`, `status`, `retry_count` |
| Human escalation | Reviewer checks if second attempt fails |

### Task T3 — Extract review flags

| Field | Description |
| --- | --- |
| Input | Draft Markdown |
| Output | Review notes or confirmation flags |
| Success condition | Unclear owner, missing due date, ambiguous decision are marked |
| Failure modes | no flags produced, false negative, malformed notes |
| Retry policy | Retry once if output format is invalid |
| Idempotency note | Safe if output file is versioned |
| Log keys | `task_id`, `flag_count`, `status` |
| Human escalation | Reviewer validates flags |

### Task T4 — Human review gate

| Field | Description |
| --- | --- |
| Input | Draft Markdown and review notes |
| Output | approval status |
| Success condition | Reviewer chooses approve, request changes, or reject |
| Failure modes | no reviewer assigned, approval not recorded |
| Retry policy | No automatic retry |
| Idempotency note | Approval record must be append-only |
| Log keys | `task_id`, `reviewer`, `approval_status`, `review_timestamp` |
| Human escalation | Workflow owner |

### Task T5 — Save approved output

| Field | Description |
| --- | --- |
| Input | Approved draft |
| Output | Final Markdown in `workspace/out/` |
| Success condition | Final file saved with correct file name |
| Failure modes | write failure, naming conflict, approval missing |
| Retry policy | Retry once for write failure; stop if approval missing |
| Idempotency note | Do not overwrite final file without version increment |
| Log keys | `task_id`, `output_file`, `status`, `approval_status` |
| Human escalation | Developer or workflow owner |

---

## 4. Anti-pattern check

- [ ] Task name is not vague, such as “process” or “handle”.
- [ ] Each task has input and output.
- [ ] Each task has at least one failure mode.
- [ ] Retry policy is not “retry everything”.
- [ ] Idempotency is considered.
- [ ] Log keys are defined.
- [ ] Human escalation is defined where needed.
```

---

# 6. `AGENTS.md` 템플릿

파일 위치 예시:

```text
AGENTS.md
```

```markdown
# AGENTS.md

## 1. Project purpose

This repository contains a minimal agent harness lab for converting a business workflow into reusable Agent Skills, an orchestrator flow, task definitions, workspace rules, and smoke verification.

## 2. Repository layout

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
    business-scenario.md
    task-breakdown.md
    security-notes.md
    review-checklist.md
```

## 3. Read first

Before modifying this repository, read the following files in order:

1. `docs/business-scenario.md`
2. `skills/meeting-summary/SKILL.md`
3. `skills/orchestrator/SKILL.md`
4. `docs/task-breakdown.md`
5. `tests/smoke/meeting-summary-smoke.md`
6. `docs/security-notes.md`

## 4. Skills

| Skill | Location | Purpose |
| --- | --- | --- |
| meeting-summary | `skills/meeting-summary/SKILL.md` | Summarize meeting transcript and extract action items |
| meeting-summary-flow | `skills/orchestrator/SKILL.md` | Coordinate input validation, summary draft, human review, and final output |

## 5. Workspace rules

- Do not modify files in `workspace/in/`.
- Save intermediate drafts to `workspace/work/`.
- Save final approved outputs to `workspace/out/` only after human approval.
- Use `workspace/tmp/` only for temporary files.
- Use `workspace/archive/` for completed packages or retained evidence.

## 6. File naming convention

Recommended pattern:

```text
YYYY-MM-DD_[scenario]_[status]_v[version].[extension]
```

Examples:

```text
2026-05-15_meeting-summary_draft_v0.1.md
2026-05-15_meeting-summary_review_v0.2.md
2026-05-15_meeting-summary_final_v1.0.md
```

## 7. Verification

Use the smoke checklist:

```text
tests/smoke/meeting-summary-smoke.md
```

Minimum verification before finalization:

- [ ] Required input exists.
- [ ] Draft follows output contract.
- [ ] Human review is recorded.
- [ ] Final output is saved to `workspace/out/` only after approval.
- [ ] No sensitive data appears in output or logs.

## 8. Security notes

- Do not write API keys, tokens, or secrets to repository files.
- Do not log full sensitive content.
- Do not expose personally identifiable information in output files.
- Do not send company data to unapproved external systems.
- If sensitive data is detected, stop finalization and request review.

## 9. Prohibited actions

Agents and contributors must not:

- Modify original files in `workspace/in/`.
- Overwrite final files without version increment.
- Save unapproved drafts to `workspace/out/`.
- Delete audit-relevant files without explicit approval.
- Invent facts, decisions, owners, or due dates not supported by input.
- Continue execution when required input is missing.

## 10. Commands

If this lab is implemented with scripts, document commands here.

```bash
# Example placeholders
python scripts/run_smoke.py
python scripts/validate_workspace.py
```

## 11. Human review

Human review is required before any output is treated as final.

Reviewer must confirm:

- Summary accuracy
- Decision accuracy
- Action item owner and due date
- Sensitive data handling
- File location and naming

## 12. Change log

| Version | Date | Change |
| --- | --- | --- |
| v0.1 | YYYY-MM-DD | Initial AGENTS.md draft |
```

---

# 7. Smoke Verification 템플릿

파일 위치 예시:

```text
tests/smoke/meeting-summary-smoke.md
```

```markdown
# Smoke Test: meeting-summary

## 1. Scenario

Generate a meeting summary draft from a sample meeting transcript, request human review, and save the approved final output to `workspace/out/`.

## 2. Input fixture

| Fixture | Location | Description |
| --- | --- | --- |
| Sample transcript | `workspace/in/sample_meeting_transcript.txt` | Meeting transcript for smoke test |
| Attendee list | `workspace/in/sample_attendees.csv` | Optional attendee list |

## 3. Expected output structure

The draft output must contain:

- [ ] `# Meeting Summary`
- [ ] `## 1. Overview`
- [ ] `## 2. Key Discussion Points`
- [ ] `## 3. Decisions`
- [ ] `## 4. Action Items`
- [ ] `## 5. Items Requiring Confirmation`
- [ ] `## 6. Review Notes`

## 4. Required checks

| Check | Pass condition | Result |
| --- | --- | --- |
| Input exists | Required input file is present | [ ] |
| Draft saved correctly | Draft is saved to `workspace/work/` | [ ] |
| Output structure valid | Required sections are present | [ ] |
| Action items structured | Owner, action, due date, confidence, notes columns exist | [ ] |
| Unclear items marked | Ambiguous items are marked as `Needs confirmation` | [ ] |
| No invented facts | Decisions and actions are supported by input | [ ] |
| PII handled | Sensitive data is removed or flagged | [ ] |
| Human review recorded | Approval or change request is recorded | [ ] |
| Final saved correctly | Approved final output is saved to `workspace/out/` | [ ] |

## 5. Failure cases

| Failure case | Expected behavior | Result |
| --- | --- | --- |
| Missing transcript | Stop with `input_missing` | [ ] |
| Unclear owner | Mark as `Needs confirmation` | [ ] |
| Missing due date | Mark due date as `Not specified` | [ ] |
| PII detected | Stop finalization and request review | [ ] |
| No approval | Do not save to `workspace/out/` | [ ] |

## 6. Log keys

The workflow should produce or preserve the following log keys where applicable:

```text
task_id
scenario_name
input_file
output_file
status
error_type
retry_count
review_required
reviewer
approval_status
approval_timestamp
```

## 7. Human review criteria

Reviewer confirms:

- [ ] Summary reflects the input transcript.
- [ ] Decisions are explicitly supported by the input.
- [ ] Action item owners are correct or marked as unclear.
- [ ] Due dates are correct or marked as not specified.
- [ ] Sensitive data is not exposed.
- [ ] Final output follows naming convention.

## 8. Smoke test result

| Item | Result |
| --- | --- |
| Date |  |
| Tester |  |
| Scenario |  |
| Pass / Fail |  |
| Notes |  |
```

---

# 8. 보안·로그 메모 템플릿

파일 위치 예시:

```text
docs/security-notes.md
```

```markdown
# Security and Logging Notes

## 1. Data classification

| Data type | Appears in scenario? | Handling rule |
| --- | --- | --- |
| Personal data | Yes / No |  |
| Company confidential data | Yes / No |  |
| Customer data | Yes / No |  |
| Credentials / secrets | Yes / No |  |
| Public data | Yes / No |  |

## 2. Sensitive data rules

- Do not expose sensitive data in logs.
- Do not copy sensitive data to final output unless explicitly approved.
- Mask or remove personal identifiers where possible.
- Stop finalization if sensitive data is detected and review is required.

Scenario-specific rules:

```text
1.
2.
3.
```

## 3. Secret handling

| Secret type | Allowed location | Prohibited location | Notes |
| --- | --- | --- | --- |
| API key | Environment variable / vault | Repository files |  |
| Token | Environment variable / vault | Logs |  |
| Password | Secret manager | Workspace files |  |

## 4. Path protection

| Path | Rule |
| --- | --- |
| `workspace/in/` | Read-only original input |
| `workspace/work/` | Draft and intermediate output |
| `workspace/out/` | Approved final output only |
| `workspace/archive/` | Completed package or evidence |
| `workspace/tmp/` | Temporary files only |

## 5. Logging standard

Minimum log keys:

```text
task_id
scenario_name
input_file
output_file
status
error_type
review_required
approval_status
```

Do not log:

- Full transcript content
- Personal identifiers
- API keys or tokens
- Unmasked customer information

## 6. Approval and audit

Human approval should record:

| Field | Description |
| --- | --- |
| Reviewer | Person or role approving output |
| Approval status | Approved / changes requested / rejected |
| Approval timestamp | Date and time |
| Notes | Review notes or conditions |

## 7. Rollback / recovery note

If an incorrect output is generated:

1. Do not delete the file immediately.
2. Move or mark the file as invalid according to policy.
3. Record the reason for invalidation.
4. Regenerate from the original input in `workspace/in/`.
5. Require human review before replacing final output.
```

---

# 9. 리뷰 체크리스트 템플릿

파일 위치 예시:

```text
docs/review-checklist.md
```

```markdown
# Developer Lab Review Checklist

## 1. Scenario

- [ ] Business scenario is documented.
- [ ] Trigger is clear.
- [ ] Input materials are defined.
- [ ] Expected output is defined.
- [ ] Human review point is defined.

## 2. Skill

- [ ] `SKILL.md` exists.
- [ ] Purpose is narrow and clear.
- [ ] When-to-use and when-not-to-use are defined.
- [ ] Inputs are concrete.
- [ ] Output contract is testable.
- [ ] Procedure is step-by-step.
- [ ] Constraints are explicit.
- [ ] Failure handling is included.
- [ ] Human review criteria are included.
- [ ] Example input/output is included.

## 3. Orchestrator

- [ ] Orchestrator Skill exists.
- [ ] Preconditions are defined.
- [ ] Workflow steps are ordered.
- [ ] Context passing rules are defined.
- [ ] Human gates are included.
- [ ] Failure handling is defined.
- [ ] Output locations are defined.

## 4. Task breakdown

- [ ] Task breakdown document exists.
- [ ] Each Task has input and output.
- [ ] Each Task has success condition.
- [ ] Each Task has failure modes.
- [ ] Retry policy is defined.
- [ ] Idempotency is considered.
- [ ] Log keys are defined.
- [ ] Human escalation is defined where needed.

## 5. AGENTS.md

- [ ] `AGENTS.md` exists at repository root.
- [ ] Project purpose is defined.
- [ ] Repository layout is documented.
- [ ] Read-first order is defined.
- [ ] Skill locations are listed.
- [ ] Workspace rules are defined.
- [ ] Verification pointer is included.
- [ ] Security notes are included.
- [ ] Prohibited actions are included.

## 6. Smoke verification

- [ ] Smoke test document exists.
- [ ] Input fixture is defined.
- [ ] Expected output structure is defined.
- [ ] Required checks are listed.
- [ ] Failure cases are included.
- [ ] Log keys are listed.
- [ ] Human review criteria are included.

## 7. Security and operations

- [ ] Sensitive data handling is defined.
- [ ] Secret handling is defined.
- [ ] Path protection rules are defined.
- [ ] Logging standard is defined.
- [ ] Approval record requirement is defined.
- [ ] Rollback or recovery note is included.

## 8. Final review result

| Item | Result |
| --- | --- |
| Reviewer |  |
| Date |  |
| Pass / Needs revision |  |
| Main revision items |  |
```

---

# 10. README 템플릿

파일 위치 예시:

```text
README.md
```

```markdown
# Agent Harness Lab

## Overview

This lab demonstrates a minimal agent harness structure for converting a business workflow into reusable Agent Skills, an orchestrator flow, task definitions, workspace rules, and smoke verification.

## Scenario

The default scenario is meeting summary automation:

1. Read a meeting transcript from `workspace/in/`.
2. Generate a structured summary draft.
3. Extract decisions and action items.
4. Request human review.
5. Save approved final output to `workspace/out/`.

## Repository layout

```text
agent-harness-lab/
  AGENTS.md
  README.md
  skills/
  workspace/
  tests/
  docs/
```

## Key files

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Repository entry point and agent rules |
| `skills/meeting-summary/SKILL.md` | Main business skill |
| `skills/orchestrator/SKILL.md` | Workflow orchestration skill |
| `docs/task-breakdown.md` | Task design notes |
| `tests/smoke/meeting-summary-smoke.md` | Smoke verification checklist |
| `docs/security-notes.md` | Security and logging notes |

## How to use this lab

1. Read `AGENTS.md`.
2. Review the business scenario.
3. Fill in or revise `SKILL.md`.
4. Define orchestration flow.
5. Complete task breakdown.
6. Run or review smoke verification.
7. Confirm security and logging rules.

## Completion criteria

- [ ] Skill is documented.
- [ ] Orchestrator is documented.
- [ ] Task breakdown is complete.
- [ ] AGENTS.md is complete.
- [ ] Smoke checklist is complete.
- [ ] Security notes are complete.
```

---

# 11. 샘플 입력 데이터 템플릿

파일 위치 예시:

```text
workspace/in/sample_meeting_transcript.txt
```

```text
Meeting: Weekly Project Sync
Date: YYYY-MM-DD
Participants: [Name 1], [Name 2], [Name 3]

Transcript:

[09:00] Name 1: ...
[09:05] Name 2: ...
[09:10] Name 3: ...

Decisions mentioned:
-

Potential action items:
-

Open questions:
-
```

파일 위치 예시:

```text
workspace/in/sample_attendees.csv
```

```csv
name,role,team
Name 1,Project Lead,Team A
Name 2,Designer,Team B
Name 3,Engineer,Team C
```

---

# 12. 최종 제출 패키지 구조

교육 종료 시 아래 구조를 제출하거나 공유합니다.

```text
agent-harness-lab/
  AGENTS.md                         # completed
  README.md                         # completed
  skills/
    meeting-summary/
      SKILL.md                      # completed
    orchestrator/
      SKILL.md                      # completed
  workspace/
    in/
      sample_meeting_transcript.txt # sample only
      sample_attendees.csv          # optional
    work/
    out/
    archive/
    tmp/
  tests/
    smoke/
      meeting-summary-smoke.md      # completed
  docs/
    business-scenario.md            # completed
    task-breakdown.md               # completed
    security-notes.md               # completed
    review-checklist.md             # completed
```

---

# 13. 교육 중 빠른 점검표

| 시간대 | 점검 항목 | 완료 |
| --- | --- | --- |
| 오전 10:45 | 기준 시나리오와 레포 구조가 준비되었는가? | [ ] |
| 오전 12:00 | `SKILL.md` 초안이 작성되었는가? | [ ] |
| 오후 14:00 | Orchestrator와 Task 초안이 작성되었는가? | [ ] |
| 오후 15:30 | `AGENTS.md` 초안이 작성되었는가? | [ ] |
| 오후 16:30 | Smoke Verification과 보안 메모가 작성되었는가? | [ ] |
| 종료 전 | 최종 리뷰 체크리스트가 완료되었는가? | [ ] |

---

# 14. 실습 완료 기준

개발자 1일 과정 실습은 아래 조건을 만족하면 완료로 봅니다.  
각 항목은 교육 종료 전 수강생 또는 강사가 직접 체크합니다.

---

## 14.1 필수 완료 항목

| 구분 | 완료 기준 | 확인 |
| --- | --- | --- |
| 기준 시나리오 | `docs/business-scenario.md`에 업무 목적, Trigger, Input, Output, Human review point가 작성되어 있다. | [ ] |
| 레포 구조 | `skills/`, `workspace/`, `tests/smoke/`, `docs/` 폴더 구조가 생성되어 있다. | [ ] |
| Main Skill | `skills/meeting-summary/SKILL.md`가 작성되어 있다. | [ ] |
| Skill 입력 | `SKILL.md`에 필요한 입력 자료와 입력 위치가 명확히 정의되어 있다. | [ ] |
| Skill 출력 | `SKILL.md`에 출력 구조와 저장 위치가 명확히 정의되어 있다. | [ ] |
| Skill 절차 | `SKILL.md`에 단계별 처리 절차가 작성되어 있다. | [ ] |
| Skill 제약 | `SKILL.md`에 금지 사항, 보안 주의사항, 추정 금지 기준이 포함되어 있다. | [ ] |
| 실패 처리 | `SKILL.md`에 입력 누락, 정보 불명확, PII 발견 등 실패 상황별 행동이 정의되어 있다. | [ ] |
| Human Review | 사람 검토가 필요한 시점과 검토 기준이 정의되어 있다. | [ ] |
| Orchestrator | `skills/orchestrator/SKILL.md`가 작성되어 있다. | [ ] |
| Workflow | Orchestrator에 입력 확인 → Skill 실행 → 검토 → 승인 → 최종 저장 흐름이 포함되어 있다. | [ ] |
| Context Passing | 단계 간 전달할 정보와 전달하지 말아야 할 정보가 정의되어 있다. | [ ] |
| Human Gate | 승인 전에는 최종 산출물을 `workspace/out/`에 저장하지 않는 규칙이 포함되어 있다. | [ ] |
| Task Breakdown | `docs/task-breakdown.md`가 작성되어 있다. | [ ] |
| Task I/O | 각 Task의 Input, Output, Success condition이 작성되어 있다. | [ ] |
| Failure Mode | 각 Task의 Failure mode와 Retry policy가 작성되어 있다. | [ ] |
| Idempotency | 중복 실행 시 파일 덮어쓰기나 상태 꼬임을 방지하는 규칙이 작성되어 있다. | [ ] |
| Log Keys | 각 Task 또는 Workflow에서 확인할 로그 키가 정의되어 있다. | [ ] |
| AGENTS.md | 저장소 루트에 `AGENTS.md`가 작성되어 있다. | [ ] |
| Read-first Order | `AGENTS.md`에 처음 읽어야 할 문서 순서가 정의되어 있다. | [ ] |
| Workspace Rules | `AGENTS.md`에 `workspace/in`, `work`, `out`, `archive`, `tmp` 사용 규칙이 작성되어 있다. | [ ] |
| Prohibited Actions | 원본 수정 금지, 승인 전 최종 저장 금지, PII 로그 노출 금지 등 금지 행동이 작성되어 있다. | [ ] |
| Smoke Test | `tests/smoke/meeting-summary-smoke.md`가 작성되어 있다. | [ ] |
| Golden Path | Smoke Test에 정상 입력 1건과 기대 출력 구조가 포함되어 있다. | [ ] |
| Failure Case | Smoke Test에 실패해야 하는 경계 사례가 최소 1개 이상 포함되어 있다. | [ ] |
| Security Notes | `docs/security-notes.md`에 시크릿, PII, 경로 보호, 로그 기준이 작성되어 있다. | [ ] |
| Review Checklist | `docs/review-checklist.md`가 작성되어 있다. | [ ] |

---

## 14.2 최소 통과 기준

시간이 부족한 경우에도 아래 항목은 반드시 완료되어야 합니다.

| 필수 항목 | 확인 |
| --- | --- |
| 업무 시나리오 1건이 문서화되어 있다. | [ ] |
| `SKILL.md`에 Purpose, Inputs, Output contract, Procedure, Constraints, Failure handling이 포함되어 있다. | [ ] |
| Orchestrator Skill에 사람 승인 게이트가 포함되어 있다. | [ ] |
| Task 분해 노트에 최소 3개 Task의 Input, Output, Failure mode가 작성되어 있다. | [ ] |
| `AGENTS.md`에 Read-first 문서, Workspace rules, Prohibited actions가 포함되어 있다. | [ ] |
| Smoke Verification에 정상 사례 1개와 실패 사례 1개가 포함되어 있다. | [ ] |
| 보안 메모에 PII 또는 민감정보 처리 기준이 포함되어 있다. | [ ] |

---

## 14.3 우수 산출물 기준

아래 항목까지 포함되면 3일 과정 또는 실제 파일럿으로 확장하기 좋은 수준으로 봅니다.

| 우수 기준 | 확인 |
| --- | --- |
| 비개발자 업무 시나리오와 개발자 산출물이 1:1로 연결되어 있다. | [ ] |
| `SKILL.md`에 정상 예시와 경계 사례가 모두 포함되어 있다. | [ ] |
| Orchestrator에 실패 시 재시도, 중단, 사람 검토 요청 기준이 구분되어 있다. | [ ] |
| Task별 Retry policy와 Idempotency note가 구체적으로 작성되어 있다. | [ ] |
| 로그 키가 실제 운영 모니터링에 사용할 수 있는 수준으로 정의되어 있다. | [ ] |
| Smoke Verification이 체크리스트뿐 아니라 실행 절차까지 포함한다. | [ ] |
| 보안 메모에 시크릿, PII, 로그, 파일 경로, 승인 기록 기준이 모두 포함되어 있다. | [ ] |
| 최종 제출 패키지 구조가 다른 개발자에게 인계 가능한 수준으로 정리되어 있다. | [ ] |

---

## 14.4 최종 확인 문장

교육 종료 시 수강생은 아래 문장을 기준으로 자신의 산출물을 점검합니다.

```text
나는 하나의 업무 시나리오를 기준으로,
에이전트가 참고할 Skill,
단계를 조립하는 Orchestrator,
작업을 나누는 Task 설계,
저장소 진입점인 AGENTS.md,
검증을 위한 Smoke Test,
보안·로그 기준을 작성했다.

이 산출물은 이후 3일 과정, 파일럿 브랜치, 또는 현업 요구사항 검토로 이어질 수 있다.
```

