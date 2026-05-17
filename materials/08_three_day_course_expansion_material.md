# 08. 3일 과정 확장 자료

> 과정명: 하네스(Harness) · Agent Skills 기반 기업 AI 교육  
> 적용 범위: 비개발자 3일 과정, 개발자 3일 과정, 혼합 3일 과정  
> 목적: 1일 과정에서 만든 초안을 실제 파일럿으로 넘길 수 있는 **설계 패키지** 수준으로 확장한다.

---

# 1. 3일 과정의 위치와 목적

## 1.1 1일 과정과 3일 과정의 차이

| 구분 | 1일 과정 | 3일 과정 |
| --- | --- | --- |
| 핵심 목적 | 공통 언어 정렬과 최소 초안 작성 | 파일럿 설계 패키지 완성 |
| 업무 범위 | 업무 1건 중심 | 후보 3~5건 검토 후 파일럿 1건 선정 |
| Skill 수준 | 초안 | 팀 표준 v1 수준 |
| Workflow 수준 | 기본 흐름 | 승인·예외·재작업 포함 |
| Workspace 수준 | 기본 폴더 규칙 | 버전·보존·민감정보 분리 포함 |
| 검증 수준 | 체크리스트 | 샘플 입력·기대 출력·통과/실패 기준 포함 |
| 개발자 산출물 | 기본 템플릿 | Skill package, Orchestrator, Task, Smoke Test |
| 종료 시 상태 | 내부 논의 가능 | 파일럿 착수 검토 가능 |

---

## 1.2 3일 과정의 핵심 목표

3일 과정은 단순한 AI 교육이 아니라, 특정 팀 또는 부서가 실제 파일럿으로 넘길 수 있는 설계 패키지를 만드는 과정입니다.

3일 과정 종료 시 다음 질문에 답할 수 있어야 합니다.

```text
어떤 업무를 파일럿으로 진행할 것인가?
```

```text
왜 이 업무가 자동화 후보로 적합한가?
```

```text
AI가 어떤 Skill과 Workflow를 기준으로 일해야 하는가?
```

```text
사람은 어디에서 검토하고 승인해야 하는가?
```

```text
어떤 입력 데이터로 검증하고, 어떤 결과가 나오면 성공으로 볼 것인가?
```

```text
리스크가 발생하면 어떻게 중단하거나 되돌릴 것인가?
```

---

# 2. 3일 과정 전체 구조

## 2.1 공통 3일 흐름

| 일차 | 핵심 주제 | 주요 질문 | 산출물 |
| --- | --- | --- | --- |
| Day 1 | 프레이밍과 Skill 정렬 | 어떤 업무를 자동화할 것인가? | 후보 우선순위표, Skill v1 초안 |
| Day 2 | Workflow와 Governance | 어떤 순서와 승인 구조로 운영할 것인가? | Workflow, Workspace, Risk Register |
| Day 3 | 검증과 파일럿 패키징 | 파일럿으로 넘길 준비가 되었는가? | 검증 패키지, 발표 자료, 액션 플랜 |

---

## 2.2 비개발자와 개발자 3일 과정 비교

| 구분 | 비개발자 3일 과정 | 개발자 3일 과정 |
| --- | --- | --- |
| Day 1 | 자동화 후보 3~5건 선정, Skill 템플릿 확정 | Skill package와 `SKILL.md` 계약 작성 |
| Day 2 | 승인·예외 Workflow, `_workspace` 규약, 리스크 정리 | Orchestrator, Task/Sub-agent, 재시도·멱등성 설계 |
| Day 3 | 파일럿 설계서, KPI, 발표, 액션 플랜 | `AGENTS.md`, Smoke Verification, Rollout Checklist |
| 핵심 산출물 | 파일럿 업무 설계 패키지 | 파일럿 기술 설계 패키지 |
| 성공 기준 | 현업·승인자·개발자에게 설명 가능 | 브랜치 또는 PoC 구현으로 전환 가능 |

## 2.3 3일 과정 산출물 추적성 기준

3일 과정의 품질은 문서가 많이 만들어졌는지가 아니라, 현업 산출물이 기술 산출물로 손실 없이 이어지는지로 판단한다.

| 비개발자 산출물 | 개발자 전환 산출물 | 연결 확인 질문 |
| --- | --- | --- |
| 파일럿 업무 선정표 | Business Scenario / Acceptance Criteria | 선택 이유와 제외 범위가 구현 범위로 전환되었는가? |
| Skill v1 초안 | `SKILL.md` | 목적, 입력, 출력, 금지 사항, 예외 처리가 계약 형태로 반영되었는가? |
| Workflow | Orchestrator Skill | 승인·검토·반려·재작업 흐름이 human gate와 failure handling에 반영되었는가? |
| `_workspace` 운영 가이드 | Path Contract / `AGENTS.md` | 원본, 초안, 최종본, 보관 위치가 동일한 경로 규칙으로 쓰이는가? |
| 리스크 레지스터 | Failure Matrix / Security Notes | 리스크별 감지 방법, 중단 조건, 담당자가 기술 문서에 반영되었는가? |
| 검증 체크리스트 | Smoke Verification | 샘플 입력, 기대 출력, 통과/실패 기준이 테스트 항목으로 전환되었는가? |
| 파일럿 설계서 | Rollout Checklist | 성공 기준, 중단 조건, 다음 액션이 파일럿 착수 기준으로 연결되었는가? |

Day 3 최종 리뷰에서는 위 표를 기준으로 연결이 끊긴 항목을 먼저 보완한다.

---

# 3. 비개발자 3일 과정 확장 자료

## 3.1 비개발자 3일 과정 목표

비개발자 3일 과정은 팀 단위 자동화 후보를 선별하고, 선택한 1개 파일럿 업무를 다음 단계로 넘길 수 있도록 설계하는 과정입니다.

최종 산출물:

- 자동화 후보 우선순위 표
- 파일럿 대상 업무 1건 선정 근거
- Skill v1 초안
- 승인·검토 Workflow
- `_workspace` 운영 가이드
- 리스크 레지스터
- 검증 체크리스트
- 파일럿 설계서 1페이지
- 발표 자료 또는 스폰서 보고 초안

---

## 3.2 비개발자 Day 1 — 프레이밍과 Skill 언어 맞추기

### Day 1 목표

- 팀 업무 중 자동화 후보 3~5건을 도출한다.
- 후보를 점수화하여 파일럿 후보를 좁힌다.
- 선택한 업무에 대한 Skill v1 초안을 작성한다.

### Day 1 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | 오리엔테이션 | 3일 과정 목표, 산출물, 평가 기준 공유 | 목표 이해 |
| 09:30–10:30 | 자동화 후보 발굴 | 팀별 후보 3~5건 작성 | 후보 목록 |
| 10:45–12:00 | 우선순위 평가 | 반복성, 규칙성, 데이터 접근성, 리스크 평가 | 우선순위 표 |
| 13:00–14:30 | 파일럿 후보 선정 | 1개 업무 선택, 제외 후보 사유 정리 | 파일럿 후보 선정표 |
| 14:45–16:00 | Skill v1 작성 | 목적, 범위, 입력, 절차, 금지 사항 작성 | Skill v1 초안 |
| 16:00–17:00 | 페어 리뷰 | 타 팀이 읽어도 이해되는지 점검 | 리뷰 코멘트 |

---

### Day 1 실습 A — 자동화 후보 우선순위 표

| 후보 업무 | 반복성 | 규칙성 | 입력 명확성 | 출력 명확성 | 데이터 접근성 | 리스크 | 기대효과 | 총점 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 |  |
|  | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 |  |
|  | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 |  |

점수 해석:

| 항목 | 높은 점수의 의미 |
| --- | --- |
| 반복성 | 자주 발생하여 자동화 효과가 큼 |
| 규칙성 | 처리 기준을 문서화하기 쉬움 |
| 입력 명확성 | 필요한 입력 자료가 분명함 |
| 출력 명확성 | 결과물의 형식이 분명함 |
| 데이터 접근성 | 비식별 샘플 또는 테스트 데이터 준비 가능 |
| 리스크 | 리스크가 낮거나 통제 가능함 |
| 기대효과 | 시간 절감, 오류 감소, 품질 향상 가능성이 큼 |

---

### Day 1 실습 B — 파일럿 후보 선정 근거

| 항목 | 작성 내용 |
| --- | --- |
| 최종 선택 업무 |  |
| 선택 이유 |  |
| 제외한 후보와 이유 |  |
| 파일럿 범위 |  |
| 파일럿에서 제외할 범위 |  |
| 예상 사용자 |  |
| 필요한 샘플 데이터 |  |
| 주요 승인자 |  |
| 예상 리스크 |  |

---

### Day 1 실습 C — Skill v1 초안

```markdown
# Skill v1: [업무명]

## 1. 목적

## 2. 적용 범위

## 3. 사용하지 말아야 하는 경우

## 4. 입력 자료

## 5. 처리 절차

## 6. 금지 사항

## 7. 예외 처리

## 8. 출력 형식

## 9. 사람 검토 지점

## 10. 완료 기준

## 11. 변경 이력
```

Day 1 완료 기준:

- [ ] 후보 업무 3개 이상이 작성되었다.
- [ ] 후보별 점수화 근거가 있다.
- [ ] 파일럿 대상 업무 1건이 선정되었다.
- [ ] 제외한 업무의 사유가 작성되었다.
- [ ] Skill v1 초안에 목적, 입력, 절차, 금지 사항, 출력이 포함되었다.
- [ ] 타 팀 또는 페어 리뷰를 1회 이상 받았다.

---

## 3.3 비개발자 Day 2 — Workflow와 Governance

### Day 2 목표

- 파일럿 업무의 단계, 승인, 예외, 재작업 흐름을 시각화한다.
- `_workspace` 규칙을 팀 운영 수준으로 확장한다.
- 주요 리스크와 완화 방안을 정리한다.

### Day 2 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | Day 1 리캡 | 후보 선정과 Skill 초안 점검 | 보완 목록 |
| 09:30–10:45 | Workflow 설계 | 정상 흐름, 승인 흐름 작성 | Workflow 초안 |
| 11:00–12:00 | 예외 흐름 설계 | 입력 누락, 승인 반려, 품질 미흡 대응 | 예외 경로 |
| 13:00–14:00 | Workspace 운영 규칙 | 폴더, 파일명, 버전, 보존 규칙 작성 | Workspace 가이드 |
| 14:15–15:30 | Risk Register | 리스크, 영향도, 완화 방안 작성 | 리스크 레지스터 |
| 15:45–17:00 | Governance 점검 | 승인자, 검토자, 책임자, 보안 검토 정리 | RACI 간단표 |

---

### Day 2 실습 A — Workflow 상세표

| 단계 | 수행 주체 | 입력 | 처리 내용 | 출력 | 승인/검토 | 다음 단계 |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 사람 / AI |  |  |  |  |  |
| 2 | 사람 / AI |  |  |  |  |  |
| 3 | 사람 / AI |  |  |  |  |  |
| 4 | 사람 / AI |  |  |  |  |  |
| 5 | 사람 / AI |  |  |  |  |  |

---

### Day 2 실습 B — 예외 흐름표

| 예외 상황 | 발생 단계 | 감지 방법 | 처리 방법 | 담당자 | 기록 위치 |
| --- | --- | --- | --- | --- | --- |
| 입력 자료 누락 |  |  |  |  |  |
| AI 결과 품질 미흡 |  |  |  |  |  |
| 승인 반려 |  |  |  |  |  |
| 민감정보 발견 |  |  |  |  |  |
| 최종 저장 오류 |  |  |  |  |  |

---

### Day 2 실습 C — `_workspace` 운영 가이드

```text
_workspace/
  in/        원본 입력 자료, 수정 금지
  work/      AI 초안, 중간 산출물, 검토 전 파일
  out/       승인 완료 최종 산출물
  archive/   완료 패키지, 증적 자료
  tmp/       임시 추출 파일, 작업 후 삭제 또는 정리
```

| 항목 | 규칙 |
| --- | --- |
| 원본 파일 수정 |  |
| 초안 저장 위치 |  |
| 최종본 저장 위치 |  |
| 파일명 규칙 |  |
| 버전 표기 |  |
| 보존 기간 |  |
| 접근 권한 |  |
| 민감정보 포함 파일 처리 |  |
| 임시 파일 삭제 기준 |  |

---

### Day 2 실습 D — RACI 간단표

| 업무 단계 | Responsible 수행 | Accountable 최종 책임 | Consulted 협의 | Informed 공유 |
| --- | --- | --- | --- | --- |
| 입력 자료 준비 |  |  |  |  |
| AI 초안 생성 |  |  |  |  |
| 품질 검토 |  |  |  |  |
| 보안 검토 |  |  |  |  |
| 최종 승인 |  |  |  |  |
| 배포 또는 저장 |  |  |  |  |

---

### Day 2 실습 E — 리스크 레지스터

| 리스크 | 발생 가능성 | 영향도 | 우선순위 | 완화 방안 | 담당자 | 중단 조건 |
| --- | --- | --- | --- | --- | --- | --- |
|  | 높음/중간/낮음 | 높음/중간/낮음 |  |  |  |  |
|  | 높음/중간/낮음 | 높음/중간/낮음 |  |  |  |  |
|  | 높음/중간/낮음 | 높음/중간/낮음 |  |  |  |  |

Day 2 완료 기준:

- [ ] 정상 Workflow가 작성되었다.
- [ ] 예외 흐름이 최소 3개 이상 작성되었다.
- [ ] 사람 승인 또는 검토 지점이 명확하다.
- [ ] `_workspace` 폴더와 파일명 규칙이 작성되었다.
- [ ] 리스크 레지스터가 작성되었다.
- [ ] 담당자와 책임자가 구분되었다.

---

## 3.4 비개발자 Day 3 — 파일럿 설계와 발표

### Day 3 목표

- 파일럿 성공 기준과 중단 조건을 정의한다.
- 검증 체크리스트와 샘플 입력·기대 출력 기준을 작성한다.
- 파일럿 설계 패키지를 발표 가능한 형태로 정리한다.

### Day 3 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–10:00 | KPI와 성공 기준 | 성공, 실패, 중단 조건 정의 | KPI 표 |
| 10:15–12:00 | 검증 패키지 작성 | 샘플 입력, 기대 출력, 통과/실패 기준 | 검증 체크리스트 |
| 13:00–14:30 | 파일럿 설계서 작성 | 1페이지 파일럿 브리프 작성 | 파일럿 설계서 |
| 14:45–15:30 | 발표 준비 | 5분 발표 구성 | 발표 자료 |
| 15:45–16:45 | 발표 및 피드백 | 팀별 발표, 질의응답 | 피드백 |
| 16:45–17:00 | 다음 액션 확정 | 담당자, 일정, 후속 회의 정리 | 액션 플랜 |

---

### Day 3 실습 A — 파일럿 KPI와 중단 조건

| 구분 | 작성 내용 |
| --- | --- |
| 파일럿 목표 |  |
| 성공 기준 |  |
| 최소 통과 기준 |  |
| 중단 조건 |  |
| 검증 대상 샘플 수 |  |
| 검토자 |  |
| 파일럿 기간 |  |
| 보고 대상 |  |

KPI 예시:

| KPI | 측정 방법 | 목표 |
| --- | --- | --- |
| 처리 시간 절감 | 기존 대비 소요 시간 비교 | 30% 절감 |
| 필수 항목 누락률 | 검증 체크리스트 기준 | 5% 이하 |
| 승인 반려율 | 사람 검토 결과 | 20% 이하 |
| 산출물 위치 준수율 | Workspace 규칙 확인 | 100% |
| 민감정보 노출 | 검증 체크리스트 확인 | 0건 |

---

### Day 3 실습 B — 검증 패키지

| 검증 항목 | 입력 샘플 | 기대 결과 | 통과 기준 | 실패 시 조치 |
| --- | --- | --- | --- | --- |
| 필수 항목 포함 |  |  |  |  |
| 원문 왜곡 없음 |  |  |  |  |
| 개인정보 제거 |  |  |  |  |
| 승인 기록 포함 |  |  |  |  |
| 최종 저장 위치 준수 |  |  |  |  |

---

### Day 3 실습 C — 파일럿 설계서 1페이지

```markdown
# 파일럿 설계서

## 1. 파일럿 업무명

## 2. 파일럿 목적

## 3. 대상 업무 범위

## 4. 제외 범위

## 5. 입력 자료

## 6. AI가 수행할 작업

## 7. 사람 검토 및 승인 지점

## 8. 최종 산출물

## 9. Workspace 운영 규칙

## 10. 주요 리스크와 완화 방안

## 11. 성공 기준 / 중단 조건

## 12. 필요한 개발 지원 또는 도구

## 13. 다음 액션과 담당자
```

---

### Day 3 발표 구조

```text
1. 우리가 선택한 파일럿 업무
2. 이 업무가 자동화 후보로 적합한 이유
3. Skill과 Workflow의 핵심 구조
4. 사람 검토와 승인 지점
5. Workspace와 산출물 관리 방식
6. 주요 리스크와 완화 방안
7. 성공 기준과 중단 조건
8. 다음 액션
```

Day 3 완료 기준:

- [ ] 파일럿 설계서 1페이지가 작성되었다.
- [ ] 성공 기준과 중단 조건이 정의되었다.
- [ ] 검증 체크리스트가 작성되었다.
- [ ] 샘플 입력과 기대 출력 기준이 있다.
- [ ] 발표를 통해 피드백을 받았다.
- [ ] 교육 후 담당자와 다음 일정이 정리되었다.

---

# 4. 개발자 3일 과정 확장 자료

## 4.1 개발자 3일 과정 목표

개발자 3일 과정은 1일 과정에서 만든 최소 하네스 구조를 파일럿 수준의 기술 설계 패키지로 확장하는 과정입니다.

최종 산출물:

- Skill package
- Orchestrator Skill
- Task/Sub-agent 설계 문서
- `AGENTS.md`
- Smoke Verification
- 보안·로그 기준
- Rollout Checklist
- 파일럿 브랜치 또는 참조 레포 초안

---

## 4.2 개발자 Day 1 — Skill Package와 계약

### Day 1 목표

- 업무 시나리오를 `SKILL.md` 계약으로 전환한다.
- 단일 Skill이 아니라 최소 2개 Skill과 Orchestrator 구조를 설계한다.
- Skill 간 의존성과 변경 기준을 정리한다.

### Day 1 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | 오리엔테이션 | 기술 산출물 목표 공유 | 작업 범위 |
| 09:30–10:45 | Skill Package 구조 | Skill 분리 기준, 네이밍, 버전 | 폴더 구조 |
| 11:00–12:00 | `SKILL.md` 계약 | 입력·출력·실패 처리 작성 | Main Skill |
| 13:00–14:30 | Supporting Skill 작성 | 보조 Skill 또는 검증 Skill 작성 | Sub Skill |
| 14:45–16:00 | Orchestrator 초안 | Skill 호출 순서와 context passing 작성 | Orchestrator |
| 16:00–17:00 | Skill diff 리뷰 | 변경 기준과 리뷰 체크리스트 작성 | 리뷰 메모 |

---

### Day 1 권장 레포 구조

```text
agent-harness-pilot/
  AGENTS.md
  README.md
  skills/
    meeting-summary/
      SKILL.md
    action-item-extraction/
      SKILL.md
    pii-review/
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
    fixtures/
  docs/
    business-scenario.md
    architecture-notes.md
    task-breakdown.md
    rollout-checklist.md
    security-notes.md
```

---

### Day 1 실습 A — Skill Package 목록

| Skill | 역할 | 입력 | 출력 | 호출 주체 | 버전 |
| --- | --- | --- | --- | --- | --- |
| meeting-summary |  |  |  |  | v0.1 |
| action-item-extraction |  |  |  |  | v0.1 |
| pii-review |  |  |  |  | v0.1 |
| orchestrator |  |  |  |  | v0.1 |

---

### Day 1 실습 B — Skill 변경 영향도

| 변경 항목 | Breaking change 여부 | 영향 받는 Skill/Task | 필요한 조치 |
| --- | --- | --- | --- |
| 입력 파일 형식 변경 | Yes / No |  |  |
| 출력 구조 변경 | Yes / No |  |  |
| 저장 위치 변경 | Yes / No |  |  |
| 실패 상태 라벨 변경 | Yes / No |  |  |
| 검토 기준 변경 | Yes / No |  |  |

Day 1 완료 기준:

- [ ] Skill package 구조가 작성되었다.
- [ ] 최소 2개 Skill과 Orchestrator가 정의되었다.
- [ ] 각 Skill의 입력과 출력이 분명하다.
- [ ] Skill 간 의존성이 정리되었다.
- [ ] 변경 영향도 또는 리뷰 기준이 작성되었다.

---

## 4.3 개발자 Day 2 — Task/Sub-agent 심화

### Day 2 목표

- Workflow를 Task 단위로 분해한다.
- 재시도, 멱등성, 중복 실행 방지 기준을 정의한다.
- Sub-agent가 필요한 경우 역할·도구·컨텍스트 경계를 정한다.

### Day 2 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | Day 1 리뷰 | Skill package 점검 | 보완 목록 |
| 09:30–10:45 | Task 분해 | I/O 기준으로 Task 작성 | Task 목록 |
| 11:00–12:00 | 실패 모드 설계 | 오류 유형과 대응 정책 작성 | Failure matrix |
| 13:00–14:00 | Retry/Idempotency | 재시도와 중복 방지 규칙 작성 | Retry policy |
| 14:15–15:30 | Sub-agent 설계 | 역할 분리, 도구 범위, 컨텍스트 전달 | Sub-agent spec |
| 15:45–17:00 | 안티패턴 리뷰 | 과도한 분해, 무한 위임, 로그 누락 점검 | 리뷰 결과 |

---

### Day 2 실습 A — Task Matrix

| Task ID | Task Name | Input | Output | Success Condition | Failure Mode | Retry Policy | Idempotency | Log Keys |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| T1 |  |  |  |  |  |  |  |  |
| T2 |  |  |  |  |  |  |  |  |
| T3 |  |  |  |  |  |  |  |  |
| T4 |  |  |  |  |  |  |  |  |
| T5 |  |  |  |  |  |  |  |  |

---

### Day 2 실습 B — Failure Matrix

| Failure Type | 발생 위치 | 감지 방법 | 자동 재시도 | 사람 개입 | 로그 키 | 최종 상태 |
| --- | --- | --- | --- | --- | --- | --- |
| input_missing |  |  | No | Yes |  | stopped |
| output_invalid |  |  | Once | Optional |  | retry_or_review |
| pii_detected |  |  | No | Yes |  | review_required |
| approval_rejected |  |  | No | Yes |  | rejected |
| save_failed |  |  | Once | Yes if repeated |  | failed |

---

### Day 2 실습 C — Sub-agent 설계서

```markdown
# Sub-agent Spec: [name]

## 1. Role

## 2. Scope

## 3. Tools allowed

## 4. Tools prohibited

## 5. Input context

## 6. Output contract

## 7. Failure handling

## 8. Parent-agent handoff rule

## 9. Recursion prevention rule

## 10. Log keys
```

Sub-agent 사용 기준:

| 사용할 만한 경우 | 사용하지 말아야 하는 경우 |
| --- | --- |
| 역할이 명확히 분리됨 | 단순 단계 하나를 과도하게 분리 |
| 도구 권한을 제한해야 함 | 같은 컨텍스트를 반복 전달해야 함 |
| 실패 처리가 독립적임 | 부모와 책임 경계가 불명확함 |
| 병렬 처리 가치가 있음 | 순차 처리로 충분함 |

Day 2 완료 기준:

- [ ] Task Matrix가 작성되었다.
- [ ] 각 Task의 I/O와 성공 조건이 있다.
- [ ] Failure Matrix가 작성되었다.
- [ ] Retry와 Stop 기준이 구분되었다.
- [ ] Idempotency 규칙이 포함되었다.
- [ ] Sub-agent 사용 여부와 이유가 정리되었다.

---

## 4.4 개발자 Day 3 — AGENTS.md, 검증, Rollout

### Day 3 목표

- `AGENTS.md`를 저장소 진입점으로 완성한다.
- Smoke Verification을 파일럿 검증 수준으로 확장한다.
- Rollout Checklist와 운영 주의사항을 작성한다.

### Day 3 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–10:00 | `AGENTS.md` 완성 | read-first, workspace, prohibited actions 작성 | AGENTS.md |
| 10:15–12:00 | Smoke Verification | fixture, expected output, failure case 작성 | Smoke Test |
| 13:00–14:00 | Security & Logging | PII, secret, path, log keys 점검 | Security Notes |
| 14:15–15:00 | Rollout Checklist | 모니터링, 승인, 롤백 조건 작성 | Rollout Checklist |
| 15:00–16:30 | 파일럿 발표 | 기술 설계 발표 | 발표 자료 |
| 16:30–17:00 | 다음 스프린트 정리 | owner, backlog, review 일정 | Action Plan |

---

### Day 3 실습 A — Smoke Verification 확장

```markdown
# Smoke Verification: [scenario]

## 1. Golden path

## 2. Input fixtures

## 3. Expected output structure

## 4. Required checks

## 5. Failure cases

## 6. Log keys

## 7. Human review criteria

## 8. Pass/Fail record

## 9. Known limitations
```

Smoke Test에 반드시 포함할 항목:

- [ ] 정상 입력 1건
- [ ] 입력 누락 사례 1건
- [ ] 불명확한 정보 사례 1건
- [ ] 민감정보 포함 사례 1건
- [ ] 승인 누락 사례 1건
- [ ] 출력 구조 검증
- [ ] 저장 경로 검증
- [ ] 로그 키 검증

---

### Day 3 실습 B — Rollout Checklist

| 영역 | 체크 항목 | 완료 |
| --- | --- | --- |
| Scope | 파일럿 업무 범위가 제한되어 있다. | [ ] |
| Data | 비식별 샘플 또는 fixture가 준비되어 있다. | [ ] |
| Skill | Skill package가 작성되어 있다. | [ ] |
| Orchestrator | Human gate와 failure handling이 포함되어 있다. | [ ] |
| Workspace | in/work/out/archive/tmp 규칙이 정의되어 있다. | [ ] |
| Security | PII, secret, log 금지 기준이 있다. | [ ] |
| Verification | Smoke test가 작성되어 있다. | [ ] |
| Monitoring | 로그 키와 확인 방법이 있다. | [ ] |
| Rollback | 잘못된 결과를 무효화하거나 복구하는 절차가 있다. | [ ] |
| Owner | 업무 담당자, 개발 담당자, 승인자가 지정되어 있다. | [ ] |

---

### Day 3 발표 구조 — 개발자

```text
1. 기준 업무 시나리오
2. Skill package 구조
3. Orchestrator 흐름
4. Task와 Sub-agent 설계
5. Failure handling과 Retry 정책
6. AGENTS.md 핵심 규칙
7. Smoke Verification 설계
8. 보안·로그·롤백 기준
9. 다음 스프린트 액션
```

Day 3 완료 기준:

- [ ] Skill package가 정리되었다.
- [ ] Orchestrator와 Task 설계가 연결되어 있다.
- [ ] `AGENTS.md`가 저장소 진입점 역할을 한다.
- [ ] Smoke Verification에 정상/실패 사례가 포함되어 있다.
- [ ] Security Notes와 Rollout Checklist가 작성되었다.
- [ ] 파일럿 브랜치 또는 다음 스프린트로 넘길 액션이 정리되었다.

---

# 5. 혼합 3일 과정 운영안

비개발자와 개발자가 함께 참여하는 경우, 3일 과정은 가장 효과적인 형태가 될 수 있습니다.  
비개발자가 업무 요구사항을 만들고, 개발자가 같은 기간 안에 기술 설계로 전환하기 때문입니다.

---

## 5.1 혼합 3일 권장 흐름

| 일차 | 비개발자 활동 | 개발자 활동 | 연결 산출물 |
| --- | --- | --- | --- |
| Day 1 | 후보 선정, Skill 초안 | Skill package 구조 | 업무 Skill → `SKILL.md` |
| Day 2 | Workflow, Workspace, Risk | Orchestrator, Task, Failure Matrix | Workflow → Orchestrator |
| Day 3 | 검증 기준, 파일럿 브리프 | Smoke Test, Rollout Checklist | 검증 체크리스트 → Smoke Verification |

---

## 5.2 혼합 과정 공동 리뷰 질문

| 연결 지점 | 질문 |
| --- | --- |
| 업무 시나리오 | 개발자가 구현 기준으로 이해할 만큼 구체적인가? |
| Skill | 비개발자 Skill의 금지 사항이 `SKILL.md` Constraints에 반영되었는가? |
| Workflow | 승인·검토 지점이 Orchestrator Human Gate에 반영되었는가? |
| Workspace | 비개발자 폴더 규칙과 개발자 경로 계약이 일치하는가? |
| Risk | 리스크 레지스터가 Failure Matrix에 반영되었는가? |
| Verification | 체크리스트가 Smoke Test의 required checks로 전환되었는가? |
| Security | 민감정보 기준이 Security Notes에 반영되었는가? |

---

## 5.3 공동 산출물 패키지

```text
pilot-package/
  business/
    pilot-brief.md
    skill-v1.md
    workflow.md
    workspace-guide.md
    risk-register.md
    validation-checklist.md
  technical/
    AGENTS.md
    skills/
    docs/task-breakdown.md
    docs/security-notes.md
    tests/smoke/
    rollout-checklist.md
  presentation/
    final-review.md
```

---

# 6. 3일 과정 슬라이드 구성안

## 6.1 비개발자 3일 슬라이드 구성

| No. | 제목 | 핵심 메시지 |
| --- | --- | --- |
| 1 | 3일 과정 소개 | 초안을 파일럿 설계 패키지로 확장한다 |
| 2 | 1일 vs 3일 차이 | 3일 과정은 파일럿 준비가 목표다 |
| 3 | 자동화 후보 우선순위 | 여러 후보 중 적합한 업무를 고른다 |
| 4 | 우선순위 매트릭스 | 반복성, 규칙성, 데이터 접근성, 리스크를 평가한다 |
| 5 | Skill v1 작성 | 업무 매뉴얼을 팀 표준 초안으로 만든다 |
| 6 | Workflow 심화 | 승인·예외·재작업 흐름을 포함한다 |
| 7 | Workspace 운영 규칙 | 버전, 보존, 접근 권한을 포함한다 |
| 8 | Risk Register | 리스크와 완화 방안을 문서화한다 |
| 9 | Governance와 RACI | 수행자, 승인자, 협의자, 공유자를 구분한다 |
| 10 | 검증 패키지 | 샘플 입력과 기대 출력을 정의한다 |
| 11 | 성공 기준과 중단 조건 | 파일럿의 Go/Stop 기준을 정한다 |
| 12 | 파일럿 설계서 | 1페이지로 의사결정자에게 설명한다 |
| 13 | 발표와 피드백 | 파일럿 가능성을 검토한다 |
| 14 | 다음 액션 | 담당자와 후속 일정을 확정한다 |

---

## 6.2 개발자 3일 슬라이드 구성

| No. | 제목 | 핵심 메시지 |
| --- | --- | --- |
| 1 | 개발자 3일 과정 소개 | 최소 하네스를 파일럿 기술 패키지로 확장한다 |
| 2 | Skill Package | 단일 Skill에서 재사용 가능한 Skill 묶음으로 확장한다 |
| 3 | `SKILL.md` 계약 | 입력·출력·실패 기준을 명확히 한다 |
| 4 | Skill 간 의존성 | 변경 영향도와 버전 관리를 고려한다 |
| 5 | Orchestrator 심화 | Context passing과 human gate를 설계한다 |
| 6 | Task Matrix | I/O, success condition, failure mode를 정의한다 |
| 7 | Retry와 Idempotency | 중복 실행과 재시도 위험을 통제한다 |
| 8 | Sub-agent 설계 | 역할·도구·컨텍스트 경계를 제한한다 |
| 9 | Failure Matrix | Stop, Retry, Escalation을 구분한다 |
| 10 | AGENTS.md | 저장소 진입점과 금지 경로를 명시한다 |
| 11 | Smoke Verification | 정상/실패 사례로 하네스를 검증한다 |
| 12 | Security & Logging | PII, secret, path, log 기준을 정한다 |
| 13 | Rollout Checklist | 파일럿 브랜치로 넘길 준비를 점검한다 |
| 14 | 기술 설계 발표 | 구현 가능성과 운영 리스크를 검토한다 |

---

# 7. 3일 과정 완료 기준

## 7.1 비개발자 3일 완료 기준

| 산출물 | 완료 기준 | 확인 |
| --- | --- | --- |
| 후보 우선순위 표 | 후보 3~5건과 점수화 근거 포함 | [ ] |
| 파일럿 후보 선정표 | 선택 이유와 제외 범위 포함 | [ ] |
| Skill v1 | 목적, 범위, 입력, 절차, 금지, 예외, 출력 포함 | [ ] |
| Workflow | 승인, 예외, 재작업, 완료 조건 포함 | [ ] |
| Workspace Guide | 폴더, 파일명, 버전, 보존, 접근 권한 포함 | [ ] |
| Risk Register | 리스크, 영향도, 완화 방안, 중단 조건 포함 | [ ] |
| Validation Checklist | 샘플 입력, 기대 출력, 통과/실패 기준 포함 | [ ] |
| Pilot Brief | 목적, 범위, 성공 기준, 다음 액션 포함 | [ ] |
| 발표 | 팀 또는 스폰서에게 설명 완료 | [ ] |

---

## 7.2 개발자 3일 완료 기준

| 산출물 | 완료 기준 | 확인 |
| --- | --- | --- |
| Skill Package | 최소 2개 Skill과 Orchestrator 포함 | [ ] |
| `SKILL.md` | 입력, 출력, 제약, 실패 처리, 예시 포함 | [ ] |
| Orchestrator | workflow steps, context passing, human gate 포함 | [ ] |
| Task Matrix | I/O, success, failure, retry, log keys 포함 | [ ] |
| Failure Matrix | Retry, Stop, Escalation 구분 | [ ] |
| Sub-agent Spec | 사용 여부와 역할 경계 정의 | [ ] |
| AGENTS.md | read-first, workspace, verification, prohibited actions 포함 | [ ] |
| Smoke Verification | golden path와 failure case 포함 | [ ] |
| Security Notes | PII, secret, path, logging, approval 포함 | [ ] |
| Rollout Checklist | 모니터링, 롤백, owner, 다음 액션 포함 | [ ] |

---

# 8. 3일 과정 강사용 운영 팁

## 8.1 Day 1 운영 팁

- 후보 업무를 너무 많이 확장하지 않게 한다.
- 점수표는 절대적 평가가 아니라 토론 도구로 사용한다.
- 파일럿 후보를 1개로 좁히는 것을 Day 1 안에 완료한다.
- Skill 작성 시 “사용하지 말아야 하는 경우”를 반드시 포함시킨다.

## 8.2 Day 2 운영 팁

- Workflow에서 사람 승인 지점을 빼먹지 않게 한다.
- 예외 흐름은 최소 3개 이상 작성하게 한다.
- Workspace 규칙은 실제 회사 드라이브나 레포 구조와 연결해서 생각하게 한다.
- 개발자 과정에서는 모든 실패를 자동 재시도하지 않도록 지도한다.

## 8.3 Day 3 운영 팁

- 발표 준비 전에 성공 기준과 중단 조건을 반드시 확인한다.
- 발표는 완성도 자랑이 아니라 파일럿 가능성 검토로 운영한다.
- 질문은 “이걸 실제로 다음 주에 파일럿으로 돌릴 수 있는가?”에 집중한다.
- 종료 전에 담당자, 다음 일정, 보완 항목을 반드시 남긴다.

---

# 9. 3일 과정 발표 평가표

| 평가 항목 | 질문 | 점수 0~3 |
| --- | --- | --- |
| 업무 범위 | 파일럿으로 적절히 작고 명확한가? |  |
| 자동화 적합성 | 반복성, 규칙성, 입력·출력이 명확한가? |  |
| Skill 품질 | 업무 절차와 금지 사항이 명확한가? |  |
| Workflow | 승인·예외·재작업 경로가 포함되어 있는가? |  |
| Workspace | 산출물 위치와 파일명 규칙이 명확한가? |  |
| 리스크 | 주요 리스크와 완화 방안이 충분한가? |  |
| 검증 | 샘플 입력과 기대 출력, 통과 기준이 있는가? |  |
| 개발 연결성 | 개발자 산출물 또는 구현 요구사항으로 전환 가능한가? |  |
| 운영 가능성 | 담당자, 승인자, 중단 조건이 정해졌는가? |  |
| 다음 액션 | 후속 일정과 소유자가 명확한가? |  |

총점: ___ / 30

판정:

| 총점 | 판정 | 권장 조치 |
| --- | --- | --- |
| 0~9 | 보완 필요 | 업무 범위와 산출물 재정리 필요 |
| 10~17 | 초안 수준 | 내부 검토 후 보완 필요 |
| 18~24 | 파일럿 후보 | 샘플 데이터와 검증 기준 보완 후 진행 가능 |
| 25~30 | 파일럿 준비 우수 | 파일럿 착수 검토 가능 |

---

# 10. 다음 작업 연결

이 3일 과정 확장 자료 다음에는 다음 항목을 작성합니다.

1. 1주 과정 확장 자료
2. 홍보·제안서 자료 정리
3. 최종 자료 패키징

