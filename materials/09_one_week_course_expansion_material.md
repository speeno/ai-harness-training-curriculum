# 09. 1주 과정 확장 자료

> 과정명: 하네스(Harness) · Agent Skills 기반 기업 AI 교육  
> 적용 범위: 비개발자 1주 과정, 개발자 1주 과정, 혼합 1주 과정  
> 목적: 3일 과정의 파일럿 설계 패키지를 조직 표준, 거버넌스, 검증 체계, 운영 모델, 확장 로드맵 수준으로 발전시킨다.

---

# 1. 1주 과정의 위치와 목적

## 1.1 1일·3일·1주 과정의 차이

| 구분 | 1일 과정 | 3일 과정 | 1주 과정 |
| --- | --- | --- | --- |
| 핵심 목적 | 공통 언어와 최소 초안 작성 | 파일럿 설계 패키지 완성 | 조직 표준과 운영 체계 수립 |
| 업무 범위 | 업무 1건 | 후보 3~5건 중 파일럿 1건 | 자동화 포트폴리오와 확장 로드맵 |
| Skill 수준 | 초안 | 팀 표준 v1 | 버전 관리되는 조직 자산 v1.x |
| Workflow 수준 | 기본 승인 흐름 | 승인·예외·재작업 포함 | SLA, RACI, 감사, 에스컬레이션 포함 |
| Workspace 수준 | 기본 폴더 규칙 | 버전·보존·민감정보 분리 | 접근 권한, 보존 기간, 감사 가능성 포함 |
| 검증 수준 | 체크리스트 | 샘플 입력·기대 출력 | 회귀 샘플, 품질 기준, 운영 점검 포함 |
| 개발 수준 | 템플릿 작성 | 기술 설계 패키지 | 참조 구현, CI/검증, 런북, SLO 초안 |
| 종료 시 상태 | 내부 논의 가능 | 파일럿 착수 검토 가능 | 조직 확산과 운영 준비 가능 |

---

## 1.2 1주 과정의 핵심 질문

1주 과정은 다음 질문에 답하기 위한 과정입니다.

```text
우리 조직은 어떤 업무부터 AI 자동화를 적용할 것인가?
```

```text
Skill을 개인 문서가 아니라 버전 관리되는 조직 자산으로 어떻게 운영할 것인가?
```

```text
업무 요구사항과 개발 구현 사이의 전달 손실을 어떻게 줄일 것인가?
```

```text
AI 결과물을 어떤 기준으로 검증하고, 어떤 조건에서 중단할 것인가?
```

```text
보안, 로그, 승인, 롤백, 운영 책임은 어떻게 정의할 것인가?
```

```text
파일럿 이후 다음 분기 또는 다음 스프린트에는 무엇을 확장할 것인가?
```

---

# 2. 1주 과정 전체 구조

## 2.1 공통 5일 흐름

| 일차 | 핵심 주제 | 주요 질문 | 대표 산출물 |
| --- | --- | --- | --- |
| Day 1 | 전략 정렬과 표준 구조 | 왜 이 자동화가 필요한가? | 자동화 포트폴리오, 표준 구조 초안 |
| Day 2 | Skill 생명주기와 템플릿 | Skill을 어떻게 작성·검토·개정할 것인가? | Skill v1.x, 템플릿, 변경 기준 |
| Day 3 | Workflow / Task / Governance | 어떻게 승인·위임·예외 처리를 운영할 것인가? | Workflow 패키지, Task 설계, RACI |
| Day 4 | Workspace / 보안 / 검증 | 어떻게 추적·보존·검증할 것인가? | Workspace 운영 가이드, 검증 패키지, Security Notes |
| Day 5 | 운영·런북·로드맵 | 어떻게 파일럿 이후 확장할 것인가? | 런북, 스폰서 브리프, 로드맵, 최종 발표 |

---

## 2.2 비개발자와 개발자 1주 과정 비교

| 구분 | 비개발자 1주 과정 | 개발자 1주 과정 |
| --- | --- | --- |
| Day 1 | 회사 생산성 목표와 자동화 포트폴리오 | 하네스 표준과 레포 구조 |
| Day 2 | Skill 목차 표준, 용어집, 금지 행동 | Skill 버전, 호환성, 변경 관리 |
| Day 3 | Workflow, 승인, RACI, 예외 흐름 | Task/Sub-agent, 병렬·휴먼게이트 설계 |
| Day 4 | Workspace, 보존, 접근 권한, 검증 | AGENTS.md, 보안, 로그, 테스트 전략 |
| Day 5 | 파일럿 패키지, KPI, 스폰서 브리프 | CI/Smoke, 런북, SLO, 기술 로드맵 |
| 핵심 산출물 | 업무 표준화·거버넌스 패키지 | 참조 구현·검증·운영 패키지 |
| 성공 기준 | 경영·IT·보안과 논의 가능한 자료 | 파일럿 브랜치·운영 검증으로 전환 가능한 자료 |

## 2.3 1주 과정 운영 모델 최소 기준

1주 과정은 교육 산출물 제작에서 끝나지 않고, 파일럿 이후 조직 확산을 위한 운영 모델을 남겨야 한다. 최소 기준은 아래와 같다.

| 운영 영역 | 최소 기준 | 대표 산출물 |
| --- | --- | --- |
| 표준화 | Skill 목차, 용어집, 금지 행동, 변경 이력이 정의되어 있다. | Skill v1.x, Skill 표준 템플릿 |
| 거버넌스 | 승인자, 검토자, 책임자, 공유 대상이 구분되어 있다. | RACI, Governance 메모 |
| 보안 | PII, 시크릿, 외부 전송, 로그 금지 기준이 문서화되어 있다. | Security Checklist, Logging Standard |
| 검증 | 정상·경계·오류·민감정보 사례가 검증 샘플로 준비되어 있다. | Smoke/Regression Fixture |
| 운영 | 장애 확인, 중단, 롤백, 연락망 기준이 있다. | Runbook, Failure Policy |
| 지표 | 파일럿 품질과 운영 안정성을 측정할 지표가 정의되어 있다. | SLO Draft, Dashboard Notes |
| 확산 | 30/60/90일 또는 다음 스프린트·분기 로드맵이 있다. | Roadmap, Sponsor Brief |

위 기준 중 보안, 검증, 운영 항목이 비어 있으면 조직 확산 단계로 넘기지 않고 파일럿 보완 과제로 남긴다.

---

# 3. 비개발자 1주 과정 확장 자료

## 3.1 비개발자 1주 과정 목표

비개발자 1주 과정은 단일 업무 자동화를 넘어, 부서 또는 크로스펑션 팀이 반복적으로 AI 자동화 후보를 발굴하고, Skill과 Workflow를 조직 자산으로 관리할 수 있도록 만드는 과정입니다.

최종 산출물:

- 자동화 포트폴리오 표
- 파일럿 후보 선정 근거
- Skill v1.x
- Skill 목차 표준과 용어집
- Workflow 패키지
- RACI 간단표
- `_workspace` 운영 가이드
- 검증 체크리스트와 샘플 입력·기대 출력
- 리스크 레지스터
- 스폰서 브리프 1페이지
- 30/60/90일 확장 로드맵

---

## 3.2 비개발자 Day 1 — 전략 정렬과 자동화 포트폴리오

### Day 1 목표

- 회사 또는 부서의 생산성 목표를 AI 자동화 후보와 연결한다.
- 자동화 후보 5건 이상을 발굴한다.
- 후보별 우선순위와 파일럿 적합성을 평가한다.

### Day 1 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | 오리엔테이션 | 1주 과정 목표와 최종 산출물 안내 | 목표 이해 |
| 09:30–10:30 | 조직 목표 정렬 | 생산성, 품질, 리스크, 비용 목표 정리 | 목표 맵 |
| 10:45–12:00 | 자동화 후보 발굴 | 부서별 후보 5건 이상 작성 | 후보 목록 |
| 13:00–14:30 | 우선순위 평가 | 빈도, 비용, 규칙성, 데이터 접근성 평가 | 포트폴리오 표 |
| 14:45–16:00 | 파일럿 후보 그룹화 | Quick win, Strategic, Risky, Defer 분류 | 후보 맵 |
| 16:00–17:00 | Day 1 리뷰 | 파일럿 후보 1~2건 선정 | 후보 선정 근거 |

---

### Day 1 실습 A — 조직 목표 맵

| 조직 목표 | 현재 문제 | AI 자동화로 기대하는 변화 | 관련 업무 후보 |
| --- | --- | --- | --- |
| 처리 시간 단축 |  |  |  |
| 품질 일관성 |  |  |  |
| 오류 감소 |  |  |  |
| 승인·검토 체계화 |  |  |  |
| 감사 가능성 확보 |  |  |  |
| 직원 반복 업무 감소 |  |  |  |

---

### Day 1 실습 B — 자동화 포트폴리오 표

| 후보 업무 | 부서 | 반복성 | 비용/시간 | 규칙성 | 데이터 접근성 | 리스크 통제 | 기대효과 | 우선순위 | 분류 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 |  | Quick win / Strategic / Defer |
|  |  | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 |  | Quick win / Strategic / Defer |
|  |  | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 | 1~5 |  | Quick win / Strategic / Defer |

---

### Day 1 완료 기준

- [ ] 조직 또는 부서의 AI 자동화 목표가 정리되었다.
- [ ] 자동화 후보 5건 이상이 작성되었다.
- [ ] 후보별 점수화 근거가 있다.
- [ ] 파일럿 후보 1~2건이 선정되었다.
- [ ] 제외 또는 보류할 후보의 사유가 작성되었다.

---

## 3.3 비개발자 Day 2 — Skill 공학과 표준 템플릿

### Day 2 목표

- Skill을 조직 자산으로 관리하기 위한 목차 표준을 만든다.
- 선택한 파일럿 업무에 대한 Skill v1.x를 작성한다.
- 용어집, 금지 행동, 예외 처리 기준을 포함한다.

### Day 2 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | Day 1 리캡 | 파일럿 후보 확인 | 보완 목록 |
| 09:30–10:45 | Skill 표준 구조 | 목차, 버전, 변경 로그 기준 정리 | Skill 템플릿 |
| 11:00–12:00 | 용어집 작성 | 업무 용어, 금지 표현, 상태 라벨 정리 | 용어집 |
| 13:00–14:30 | Skill v1.x 작성 | 목적, 범위, 입력, 절차, 출력 작성 | Skill 본문 |
| 14:45–15:45 | 예외·금지 행동 | 추정 금지, 개인정보, 승인 전 배포 금지 등 | 금지 행동 목록 |
| 15:45–17:00 | 교차 리뷰 | 다른 팀이 읽어도 실행 가능한지 점검 | 리뷰 코멘트 |

---

### Day 2 실습 A — Skill 표준 템플릿

```markdown
# Skill v1.x: [업무명]

## 1. 목적

## 2. 적용 범위

## 3. 사용하지 말아야 하는 경우

## 4. 용어집

## 5. 입력 자료

## 6. 처리 절차

## 7. 금지 사항

## 8. 예외 처리

## 9. 출력 형식

## 10. 사람 검토 지점

## 11. 완료 기준

## 12. 검증 기준

## 13. 변경 이력
```

---

### Day 2 실습 B — 용어집

| 용어 | 정의 | 사용 예 | 주의 사항 |
| --- | --- | --- | --- |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

---

### Day 2 실습 C — 금지 행동 목록

| 유형 | 금지 행동 | 이유 | 위반 시 조치 |
| --- | --- | --- | --- |
| 사실성 | 확인되지 않은 내용을 사실처럼 단정 |  |  |
| 개인정보 | 민감정보를 그대로 복사 |  |  |
| 승인 | 승인 전 외부 배포 |  |  |
| 보안 | 금지 데이터 입력 |  |  |
| 파일 | 원본 파일 수정 |  |  |
| 표현 | 고객/임원/외부용 부적절 표현 |  |  |

---

### Day 2 완료 기준

- [ ] Skill 표준 목차가 확정되었다.
- [ ] Skill v1.x가 작성되었다.
- [ ] 용어집이 작성되었다.
- [ ] 금지 행동과 예외 처리 기준이 작성되었다.
- [ ] 변경 이력 또는 버전 규칙이 포함되었다.
- [ ] 교차 리뷰를 통해 보완 사항이 정리되었다.

---

## 3.4 비개발자 Day 3 — Workflow, Governance, RACI

### Day 3 목표

- 파일럿 업무의 정상 흐름, 예외 흐름, 승인 흐름을 문서화한다.
- 업무별 책임자, 승인자, 협의자, 공유 대상을 정의한다.
- SLA, 에스컬레이션, 중단 조건을 포함한다.

### Day 3 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | Day 2 리캡 | Skill v1.x 점검 | 보완 목록 |
| 09:30–10:45 | Workflow 심화 | 정상 흐름, 승인 흐름 작성 | Workflow 다이어그램 |
| 11:00–12:00 | 예외·재작업 경로 | 입력 누락, 승인 반려, 품질 미흡 처리 | 예외 흐름표 |
| 13:00–14:00 | RACI 작성 | 수행·책임·협의·공유 역할 정의 | RACI 표 |
| 14:15–15:15 | SLA와 에스컬레이션 | 처리 시간, 지연, 중단 조건 정리 | SLA 초안 |
| 15:30–17:00 | Governance 리뷰 | 승인자·보안·법무 검토 필요성 점검 | Governance 메모 |

---

### Day 3 실습 A — Workflow 패키지

```text
[요청 접수]
   ↓
[입력 자료 확인]
   ↓
[AI 초안 생성]
   ↓
[1차 담당자 검토]
   ↓
[승인자 승인]
   ├─ 승인 → [최종 저장/배포]
   ├─ 수정 요청 → [AI 재작성 또는 사람 수정]
   └─ 반려 → [종료/보류]
```

상세표:

| 단계 | 수행 주체 | 입력 | 처리 내용 | 출력 | 승인/검토 | SLA |
| --- | --- | --- | --- | --- | --- | --- |
| 1 |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |

---

### Day 3 실습 B — RACI 표

| 업무 단계 | Responsible | Accountable | Consulted | Informed |
| --- | --- | --- | --- | --- |
| 입력 자료 준비 |  |  |  |  |
| AI 초안 생성 |  |  |  |  |
| 1차 검토 |  |  |  |  |
| 보안 검토 |  |  |  |  |
| 최종 승인 |  |  |  |  |
| 배포/보관 |  |  |  |  |

---

### Day 3 실습 C — SLA와 에스컬레이션

| 상황 | 기준 시간 | 담당자 | 에스컬레이션 조건 | 조치 |
| --- | --- | --- | --- | --- |
| 입력 자료 미제출 |  |  |  |  |
| AI 초안 생성 실패 |  |  |  |  |
| 검토 지연 |  |  |  |  |
| 승인 반려 |  |  |  |  |
| 민감정보 발견 |  |  |  |  |

---

### Day 3 완료 기준

- [ ] 정상 Workflow와 예외 Workflow가 작성되었다.
- [ ] 사람 승인과 검토 지점이 명확하다.
- [ ] RACI가 작성되었다.
- [ ] SLA 또는 에스컬레이션 기준이 포함되었다.
- [ ] Governance 메모가 작성되었다.

---

## 3.5 비개발자 Day 4 — Workspace, 감사 가능성, 검증

### Day 4 목표

- `_workspace` 운영 가이드를 감사 가능한 수준으로 확장한다.
- 샘플 입력과 기대 출력을 정의한다.
- 검증 체크리스트, 통과/실패 기준, 리스크 레지스터를 완성한다.

### Day 4 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | Day 3 리캡 | Workflow와 RACI 점검 | 보완 목록 |
| 09:30–10:45 | Workspace 운영 | 폴더, 파일명, 보존, 접근 권한 작성 | Workspace 가이드 |
| 11:00–12:00 | 감사 가능성 | 원본 보존, 변경 기록, 승인 증적 정의 | Audit 메모 |
| 13:00–14:00 | 샘플 입력·기대 출력 | 검증용 샘플과 기대 결과 정리 | 검증 fixture 표 |
| 14:15–15:30 | 검증 체크리스트 | 통과/실패 기준 작성 | 검증표 |
| 15:45–17:00 | 리스크 레지스터 | 중단 조건, 완화 방안, 담당자 확정 | 리스크 레지스터 |

---

### Day 4 실습 A — Workspace 운영 가이드

| 항목 | 규칙 | 담당자 | 비고 |
| --- | --- | --- | --- |
| 원본 입력 위치 |  |  |  |
| 작업 중 파일 위치 |  |  |  |
| 최종 산출물 위치 |  |  |  |
| 보관 위치 |  |  |  |
| 임시 파일 처리 |  |  |  |
| 파일명 규칙 |  |  |  |
| 버전 규칙 |  |  |  |
| 보존 기간 |  |  |  |
| 접근 권한 |  |  |  |
| 민감정보 파일 처리 |  |  |  |

---

### Day 4 실습 B — 검증 fixture 표

| 샘플 ID | 입력 유형 | 샘플 설명 | 기대 출력 | 검증 포인트 | 통과 기준 |
| --- | --- | --- | --- | --- | --- |
| S-001 | 정상 |  |  |  |  |
| S-002 | 경계 |  |  |  |  |
| S-003 | 오류 |  |  |  |  |
| S-004 | 민감정보 포함 |  |  |  |  |

---

### Day 4 실습 C — 통과/실패 기준

| 검증 항목 | 통과 기준 | 실패 기준 | 실패 시 조치 |
| --- | --- | --- | --- |
| 필수 항목 포함 |  |  |  |
| 원문 왜곡 없음 |  |  |  |
| 추정 내용 표시 |  |  |  |
| 개인정보 처리 |  |  |  |
| 승인 기록 |  |  |  |
| 저장 위치 |  |  |  |

---

### Day 4 완료 기준

- [ ] Workspace 운영 가이드가 작성되었다.
- [ ] 보존 기간과 접근 권한이 정의되었다.
- [ ] 원본 보존과 승인 증적 기준이 포함되었다.
- [ ] 검증용 샘플 입력이 최소 3종 이상 정의되었다.
- [ ] 통과/실패 기준이 작성되었다.
- [ ] 리스크 레지스터가 완성되었다.

---

## 3.6 비개발자 Day 5 — 파일럿 패키지, 브리프, 로드맵

### Day 5 목표

- 1주 과정 산출물을 하나의 파일럿 패키지로 정리한다.
- 경영·IT·보안 스폰서에게 설명할 수 있는 1페이지 브리프를 작성한다.
- 30/60/90일 확장 로드맵을 만든다.

### Day 5 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–10:00 | 파일럿 패키지 정리 | 산출물 누락 점검 | 패키지 체크리스트 |
| 10:15–12:00 | 스폰서 브리프 작성 | 기대효과, 리스크, 요청사항 정리 | 1페이지 브리프 |
| 13:00–14:00 | 30/60/90일 로드맵 | 후속 일정과 소유자 작성 | 로드맵 |
| 14:15–15:00 | 발표 리허설 | 7분 발표, 5분 Q&A 준비 | 발표 자료 |
| 15:00–16:30 | 최종 발표 | 스폰서 또는 내부 리뷰 | 피드백 |
| 16:30–17:00 | 다음 액션 확정 | 담당자, 일정, 후속 회의 | 액션 플랜 |

---

### Day 5 실습 A — 스폰서 브리프 1페이지

```markdown
# AI 자동화 파일럿 브리프

## 1. 파일럿 업무명

## 2. 추진 배경

## 3. 기대효과

## 4. 대상 업무 범위

## 5. 제외 범위

## 6. 주요 산출물

## 7. 성공 기준

## 8. 주요 리스크와 완화 방안

## 9. 필요한 지원

## 10. 일정과 다음 단계
```

---

### Day 5 실습 B — 30/60/90일 로드맵

| 기간 | 목표 | 주요 작업 | 담당자 | 산출물 |
| --- | --- | --- | --- | --- |
| 30일 | 파일럿 준비 |  |  |  |
| 60일 | 파일럿 실행 |  |  |  |
| 90일 | 평가와 확장 |  |  |  |

---

### Day 5 완료 기준

- [ ] 파일럿 패키지가 하나의 구조로 정리되었다.
- [ ] 스폰서 브리프가 작성되었다.
- [ ] 성공 기준과 중단 조건이 포함되었다.
- [ ] 30/60/90일 로드맵이 작성되었다.
- [ ] 최종 발표와 피드백이 완료되었다.
- [ ] 교육 후 담당자와 다음 일정이 확정되었다.

---

# 4. 개발자 1주 과정 확장 자료

## 4.1 개발자 1주 과정 목표

개발자 1주 과정은 사내 에이전트 하네스 표준을 코드와 문서로 동시에 확립하고, 파일럿 이후 운영까지 고려한 참조 구현과 검증 체계를 만드는 과정입니다.

최종 산출물:

- 참조 구현 레포 또는 브랜치
- Skill package
- Orchestrator Skill
- Task/Sub-agent 설계
- `AGENTS.md`
- Architecture Decision Record
- Smoke/Regression fixture
- CI 또는 로컬 검증 스크립트 초안
- Security Checklist
- Logging Standard
- Runbook
- SLO 초안
- 기술 확장 로드맵

---

## 4.2 개발자 Day 1 — 표준과 레포 구조

### Day 1 목표

- 조직의 에이전트 하네스 표준 구조를 정의한다.
- 모노레포 또는 멀티 레포 환경에서 Skill과 Orchestrator의 위치를 정한다.
- 기본 브랜치 전략과 리뷰 기준을 설정한다.

### Day 1 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | 오리엔테이션 | 1주 기술 산출물과 기준 공유 | 목표 이해 |
| 09:30–10:45 | 하네스 참조 모델 | Agent, Skill, Orchestrator, Task 구조 정리 | 참조 모델 |
| 11:00–12:00 | 레포 구조 설계 | skills, agents, workspace, tests 위치 정의 | 레포 레이아웃 |
| 13:00–14:30 | 브랜치·리뷰 전략 | PR 기준, Skill diff, 검증 요구사항 정의 | 기여 기준 |
| 14:45–16:00 | 기준 레포 생성 | 폴더와 기본 문서 생성 | 참조 브랜치 |
| 16:00–17:00 | 아키텍처 메모 | 주요 결정과 대안 기록 | ADR 초안 |

---

### Day 1 실습 A — 레포 레이아웃

```text
agent-harness-standard/
  AGENTS.md
  README.md
  docs/
    architecture/
      adr-001-harness-structure.md
    governance/
      contribution-guide.md
    security/
      security-checklist.md
    operations/
      runbook.md
  skills/
    [domain-skill]/
      SKILL.md
    orchestrators/
      [flow-name]/
        SKILL.md
  agents/
    [agent-name]/
      agent-definition.md
  workspace-template/
    in/
    work/
    out/
    archive/
    tmp/
  tests/
    fixtures/
    smoke/
    regression/
  scripts/
    validate_workspace.py
    run_smoke.py
```

---

### Day 1 실습 B — ADR 템플릿

```markdown
# ADR-001: Agent Harness Repository Structure

## Status
Proposed / Accepted / Superseded

## Context

## Decision

## Alternatives considered

## Consequences

## Follow-up actions
```

---

### Day 1 완료 기준

- [ ] 기준 레포 구조가 정의되었다.
- [ ] `AGENTS.md`의 위치와 역할이 합의되었다.
- [ ] Skill과 Orchestrator의 폴더 규칙이 정해졌다.
- [ ] 브랜치와 리뷰 기준이 초안으로 작성되었다.
- [ ] ADR 초안이 작성되었다.

---

## 4.3 개발자 Day 2 — Skill 생명주기와 버전 관리

### Day 2 목표

- Skill을 도메인 모듈처럼 관리하기 위한 생명주기 기준을 만든다.
- 버전, 호환성, Breaking Change, Changelog 기준을 정의한다.
- Skill Package를 파일럿 수준으로 작성한다.

### Day 2 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | Day 1 리뷰 | 레포 구조와 ADR 점검 | 보완 목록 |
| 09:30–10:45 | Skill 버전 정책 | v0.x, v1.x, breaking change 기준 | 버전 정책 |
| 11:00–12:00 | Skill 템플릿 표준화 | 공통 목차와 필수 섹션 정의 | Skill 표준 템플릿 |
| 13:00–14:30 | Skill Package 작성 | domain skill, support skill 작성 | Skill package |
| 14:45–15:45 | 변경 영향도 분석 | 입력/출력/경로/상태 라벨 변경 영향 | 영향도 표 |
| 15:45–17:00 | Skill 리뷰 | PR 체크리스트와 리뷰 기준 적용 | 리뷰 결과 |

---

### Day 2 실습 A — Skill 버전 정책

| 버전 유형 | 의미 | 예시 |
| --- | --- | --- |
| v0.x | 실험 또는 교육용 초안 | v0.1 초기 작성 |
| v1.x | 파일럿 또는 팀 표준 사용 가능 | v1.0 파일럿 승인 |
| Minor update | 입력·출력 계약 유지, 설명 보완 | v1.1 예시 추가 |
| Breaking change | 입력·출력·경로·상태 라벨 변경 | v2.0 출력 구조 변경 |

---

### Day 2 실습 B — Skill Review Checklist

| 항목 | 확인 |
| --- | --- |
| 목적이 좁고 명확하다. | [ ] |
| When to use / When not to use가 있다. | [ ] |
| 입력 자료와 위치가 명확하다. | [ ] |
| 출력 계약이 테스트 가능하다. | [ ] |
| 실패 처리와 상태 라벨이 있다. | [ ] |
| Human review 기준이 있다. | [ ] |
| 예시와 경계 사례가 있다. | [ ] |
| Changelog가 작성되었다. | [ ] |
| 보안·개인정보 기준이 포함되었다. | [ ] |

---

### Day 2 완료 기준

- [ ] Skill 버전 정책이 작성되었다.
- [ ] Skill 표준 템플릿이 작성되었다.
- [ ] Skill Package가 작성되었다.
- [ ] 변경 영향도 분석표가 작성되었다.
- [ ] Skill Review Checklist가 작성되었다.

---

## 4.4 개발자 Day 3 — Task/Sub-agent 아키텍처

### Day 3 목표

- Orchestrator와 Task Graph를 파일럿 수준으로 설계한다.
- Sub-agent 사용 기준과 도구 권한 경계를 정의한다.
- 병렬 처리, 휴먼게이트, 실패 복구를 설계한다.

### Day 3 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | Day 2 리뷰 | Skill package 점검 | 보완 목록 |
| 09:30–10:45 | Orchestrator 심화 | 단계, context passing, human gate 설계 | Orchestrator v1 |
| 11:00–12:00 | Task Graph | 순차·병렬·승인 단계 설계 | Task Graph |
| 13:00–14:00 | Sub-agent 권한 | 역할, 도구, 컨텍스트 제한 작성 | Sub-agent spec |
| 14:15–15:15 | 실패 복구 | retry, stop, compensate, escalate 설계 | Failure policy |
| 15:30–17:00 | 아키텍처 리뷰 | 보안·운영 관점 리뷰 | ADR 보완 |

---

### Day 3 실습 A — Task Graph

```text
T1 Validate Input
   ↓
T2 Generate Draft Summary
   ├─ T3 Extract Action Items
   ├─ T4 Detect PII
   ↓
T5 Human Review Gate
   ├─ Approved → T6 Save Final Output
   ├─ Changes Requested → T2 Regenerate Draft
   └─ Rejected → Stop and Archive Draft
```

---

### Day 3 실습 B — Failure Policy

| Failure | Detection | Action | Retry | Human Escalation | Compensation |
| --- | --- | --- | --- | --- | --- |
| input_missing |  | Stop | No | Yes |  |
| output_invalid |  | Retry once | Yes | If repeated |  |
| pii_detected |  | Stop finalization | No | Yes | Mask/remove |
| approval_rejected |  | Stop | No | Yes | Archive draft |
| save_failed |  | Retry save | Once | If repeated | Keep draft |

---

### Day 3 완료 기준

- [ ] Orchestrator v1이 작성되었다.
- [ ] Task Graph가 작성되었다.
- [ ] Sub-agent 사용 기준과 권한 경계가 정리되었다.
- [ ] Failure Policy가 작성되었다.
- [ ] Human Gate와 escalation이 포함되었다.
- [ ] ADR 또는 architecture notes가 보완되었다.

---

## 4.5 개발자 Day 4 — AGENTS.md, 보안, 검증 파이프라인

### Day 4 목표

- `AGENTS.md`를 저장소 표준 진입점으로 완성한다.
- 보안·로그·시크릿·PII 기준을 문서화한다.
- Smoke, Regression, 선택적 CI 검증 흐름을 설계한다.

### Day 4 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–09:30 | Day 3 리뷰 | Task Graph와 Failure Policy 점검 | 보완 목록 |
| 09:30–10:30 | AGENTS.md 표준 | read-first, rules, prohibited actions 작성 | AGENTS.md v1 |
| 10:45–12:00 | Security Checklist | PII, secret, path, external call 기준 작성 | Security Checklist |
| 13:00–14:00 | Logging Standard | 최소 로그 키와 금지 로그 정의 | Logging Standard |
| 14:15–15:30 | Verification Pyramid | smoke, regression, fixture 기준 작성 | 검증 전략 |
| 15:45–17:00 | CI/Local 검증 | 로컬 스크립트 또는 CI 초안 작성 | 검증 파이프라인 초안 |

---

### Day 4 실습 A — Verification Pyramid

```text
Level 1: Static / structure check
- Required files exist
- Required sections in SKILL.md
- Workspace paths exist

Level 2: Smoke check
- Golden path input
- Expected output structure
- Human review gate

Level 3: Regression fixture
- Normal case
- Boundary case
- Error case
- PII case

Level 4: Optional E2E
- Integrated workflow with logs and approval record
```

---

### Day 4 실습 B — Logging Standard

| Log Key | Required | Description | Sensitive? |
| --- | --- | --- | --- |
| task_id | Yes | Task identifier | No |
| scenario_name | Yes | Scenario name | No |
| input_file | Yes | File path only | Check |
| output_file | Yes | File path only | Check |
| status | Yes | success/failure/review_required | No |
| error_type | Yes if failed | Failure type | No |
| approval_status | Yes if reviewed | approved/rejected/changes_requested | No |
| reviewer | Optional | Reviewer role or ID | Check |

Do not log:

- full meeting transcript
- personal identifiers
- credentials or tokens
- unmasked customer data
- confidential document contents

---

### Day 4 완료 기준

- [ ] `AGENTS.md` v1이 작성되었다.
- [ ] Security Checklist가 작성되었다.
- [ ] Logging Standard가 작성되었다.
- [ ] Smoke fixture와 Regression fixture 기준이 정의되었다.
- [ ] 로컬 또는 CI 검증 초안이 작성되었다.
- [ ] 금지 로그와 금지 경로가 명확하다.

---

## 4.6 개발자 Day 5 — 운영, 런북, SLO, 로드맵

### Day 5 목표

- 파일럿 운영을 위한 런북과 롤백 기준을 작성한다.
- SLO 또는 운영 지표 초안을 정의한다.
- 다음 스프린트 또는 다음 분기 확장 로드맵을 작성한다.

### Day 5 시간표

| 시간 | 세션 | 활동 | 산출물 |
| --- | --- | --- | --- |
| 09:00–10:00 | Runbook 작성 | 장애 확인, 롤백, 연락망 정리 | Runbook |
| 10:15–11:00 | SLO 초안 | 성공률, 검토 시간, 실패율 지표 정의 | SLO draft |
| 11:00–12:00 | 운영 대시보드 구상 | 로그 키와 지표 연결 | Dashboard notes |
| 13:00–14:00 | Roadmap | 다음 스프린트, 다음 분기 확장 계획 | 기술 로드맵 |
| 14:15–15:00 | 최종 패키지 점검 | 누락 산출물 확인 | 패키지 체크 |
| 15:00–16:30 | 최종 발표 | 기술 설계와 운영 계획 발표 | 발표 자료 |
| 16:30–17:00 | 다음 액션 | owner, review, backlog 정리 | Action Plan |

---

### Day 5 실습 A — Runbook 템플릿

```markdown
# Runbook: [workflow-name]

## 1. Purpose

## 2. Scope

## 3. Normal operation

## 4. Common failure cases

| Failure | How to detect | Immediate action | Escalation | Recovery |
| --- | --- | --- | --- | --- |
| input_missing |  |  |  |  |
| output_invalid |  |  |  |  |
| pii_detected |  |  |  |  |
| approval_missing |  |  |  |  |
| save_failed |  |  |  |  |

## 5. Rollback procedure

## 6. Contacts

## 7. Logging queries or keys

## 8. Post-incident review notes
```

---

### Day 5 실습 B — SLO 초안

| 지표 | 정의 | 목표 | 측정 방법 |
| --- | --- | --- | --- |
| Smoke pass rate | Smoke Test 통과율 |  |  |
| Human review completion time | 검토 완료까지 걸리는 시간 |  |  |
| Output contract violation rate | 출력 구조 위반 비율 |  |  |
| PII incident count | 민감정보 노출 또는 탐지 건수 | 0 |  |
| Final output path compliance | 최종 산출물 경로 준수율 | 100% |  |
| Retry success rate | 재시도 후 성공 비율 |  |  |

---

### Day 5 실습 C — 기술 로드맵

| 기간 | 목표 | 주요 작업 | 담당자 | 산출물 |
| --- | --- | --- | --- | --- |
| 다음 2주 | 파일럿 브랜치 정리 |  |  |  |
| 다음 1개월 | Smoke 자동화 |  |  |  |
| 다음 분기 | Skill package 확장 |  |  |  |

---

### Day 5 완료 기준

- [ ] Runbook이 작성되었다.
- [ ] Rollback 또는 recovery 절차가 포함되었다.
- [ ] SLO 또는 운영 지표가 정의되었다.
- [ ] 기술 로드맵이 작성되었다.
- [ ] 최종 패키지가 정리되었다.
- [ ] 발표와 피드백이 완료되었다.
- [ ] 다음 스프린트 owner와 backlog가 정리되었다.

---

# 5. 혼합 1주 과정 운영안

혼합 1주 과정은 비개발자와 개발자가 같은 파일럿을 중심으로 병렬 작업한 뒤, 매일 연결 리뷰를 진행하는 방식이 가장 효과적입니다.

---

## 5.1 혼합 1주 권장 운영 흐름

| 일차 | 비개발자 활동 | 개발자 활동 | 공동 리뷰 산출물 |
| --- | --- | --- | --- |
| Day 1 | 자동화 포트폴리오, 파일럿 후보 선정 | 하네스 레포 구조 설계 | 파일럿 후보와 레포 구조 매핑 |
| Day 2 | Skill v1.x, 용어집, 금지 행동 | Skill package, 버전 정책 | Skill 초안 ↔ `SKILL.md` 연결 |
| Day 3 | Workflow, RACI, SLA | Orchestrator, Task Graph | Workflow ↔ Orchestrator 연결 |
| Day 4 | Workspace, 검증, 리스크 | AGENTS.md, Security, Smoke/Regression | 검증 체크리스트 ↔ Test fixture 연결 |
| Day 5 | 스폰서 브리프, 로드맵 | Runbook, SLO, 기술 로드맵 | 공동 파일럿 패키지 발표 |

---

## 5.2 매일 공동 리뷰 질문

### Day 1 리뷰 질문

```text
선정한 파일럿 업무는 기술적으로도 너무 크지 않은가?
```

```text
비개발자가 정의한 입력 자료는 개발자가 fixture로 만들 수 있는가?
```

### Day 2 리뷰 질문

```text
Skill v1.x의 금지 사항이 `SKILL.md` Constraints에 반영되었는가?
```

```text
용어집과 상태 라벨이 개발자 문서에서도 동일하게 쓰이는가?
```

### Day 3 리뷰 질문

```text
RACI의 승인자가 Orchestrator의 human gate로 반영되었는가?
```

```text
예외 흐름이 Failure Policy에 반영되었는가?
```

### Day 4 리뷰 질문

```text
Workspace 운영 규칙이 AGENTS.md와 검증 스크립트 기준과 일치하는가?
```

```text
검증 체크리스트가 Smoke/Regression fixture로 전환되었는가?
```

### Day 5 리뷰 질문

```text
스폰서 브리프의 성공 기준과 개발자 SLO가 충돌하지 않는가?
```

```text
파일럿 이후 30/60/90일 로드맵과 기술 로드맵이 연결되어 있는가?
```

---

## 5.3 혼합 1주 최종 패키지 구조

```text
one-week-pilot-package/
  00-overview/
    sponsor-brief.md
    30-60-90-roadmap.md
  01-business/
    automation-portfolio.md
    skill-v1x.md
    glossary.md
    workflow-package.md
    raci.md
    workspace-guide.md
    validation-checklist.md
    risk-register.md
  02-technical/
    AGENTS.md
    README.md
    skills/
    agents/
    docs/
      architecture/
      security/
      operations/
    tests/
      fixtures/
      smoke/
      regression/
    scripts/
  03-review/
    final-presentation.md
    feedback-log.md
    action-plan.md
```

---

# 6. 1주 과정 슬라이드 구성안

## 6.1 비개발자 1주 슬라이드 구성

| No. | 제목 | 핵심 메시지 |
| --- | --- | --- |
| 1 | 비개발자 1주 과정 소개 | 파일럿을 넘어 조직 운영 모델을 만든다 |
| 2 | 1일·3일·1주 차이 | 1주는 표준·거버넌스·로드맵 중심이다 |
| 3 | 조직 목표와 자동화 포트폴리오 | 후보를 조직 목표와 연결한다 |
| 4 | 우선순위와 파일럿 후보 선정 | Quick win과 Strategic 후보를 구분한다 |
| 5 | Skill을 조직 자산으로 관리하기 | 목차, 버전, 용어집, 변경 이력 |
| 6 | 금지 행동과 예외 처리 | 안전한 자동화를 위한 경계 설정 |
| 7 | Workflow와 RACI | 사람 승인과 책임 구조를 명확히 한다 |
| 8 | SLA와 에스컬레이션 | 지연·반려·오류 상황 대응 기준 |
| 9 | Workspace 운영과 감사 가능성 | 원본, 초안, 최종, 증적을 구분한다 |
| 10 | 검증 패키지 | 샘플 입력, 기대 출력, 통과/실패 기준 |
| 11 | 리스크 레지스터 | 중단 조건과 완화 방안을 정리한다 |
| 12 | 스폰서 브리프 | 의사결정자가 볼 수 있는 1페이지 요약 |
| 13 | 30/60/90일 로드맵 | 파일럿 이후 확장 계획 |
| 14 | 최종 발표 | 조직 확산 가능성을 검토한다 |

---

## 6.2 개발자 1주 슬라이드 구성

| No. | 제목 | 핵심 메시지 |
| --- | --- | --- |
| 1 | 개발자 1주 과정 소개 | 참조 구현과 운영 체계를 만든다 |
| 2 | 하네스 표준과 레포 구조 | 재사용 가능한 기준 레포를 설계한다 |
| 3 | ADR과 아키텍처 결정 | 결정과 대안을 기록한다 |
| 4 | Skill 생명주기 | 버전, 호환성, 변경 영향도를 관리한다 |
| 5 | Skill Package | 도메인 Skill과 지원 Skill을 구성한다 |
| 6 | Orchestrator v1 | Context passing, human gate, failure policy |
| 7 | Task Graph와 Sub-agent | 역할과 도구 권한을 제한한다 |
| 8 | AGENTS.md 표준 | 저장소 진입점과 금지 행동을 정한다 |
| 9 | Security Checklist | PII, secret, path, external call 기준 |
| 10 | Verification Pyramid | static, smoke, regression, E2E 검증 |
| 11 | Logging Standard | 운영 추적 가능한 로그 키 정의 |
| 12 | Runbook과 Rollback | 장애 대응과 복구 절차 |
| 13 | SLO와 운영 지표 | 파일럿 운영 품질을 측정한다 |
| 14 | 기술 로드맵 | 다음 스프린트와 다음 분기 확장 |

---

# 7. 1주 과정 완료 기준

## 7.1 비개발자 1주 완료 기준

| 산출물 | 완료 기준 | 확인 |
| --- | --- | --- |
| 자동화 포트폴리오 | 후보 5건 이상, 점수화 근거 포함 | [ ] |
| 파일럿 후보 선정 | 선택 이유, 제외 범위, 기대효과 포함 | [ ] |
| Skill v1.x | 목적, 범위, 용어집, 입력, 절차, 금지, 예외, 출력, 검증 포함 | [ ] |
| Skill 표준 템플릿 | 다른 업무에도 재사용 가능한 구조 | [ ] |
| Workflow 패키지 | 정상·예외·재작업·승인 흐름 포함 | [ ] |
| RACI | 수행자, 책임자, 협의자, 공유 대상 구분 | [ ] |
| Workspace 운영 가이드 | 폴더, 파일명, 버전, 보존, 접근 권한 포함 | [ ] |
| 검증 패키지 | 샘플 입력, 기대 출력, 통과/실패 기준 포함 | [ ] |
| 리스크 레지스터 | 리스크, 완화 방안, 중단 조건, 담당자 포함 | [ ] |
| 스폰서 브리프 | 목적, 기대효과, 리스크, 요청 사항, 일정 포함 | [ ] |
| 30/60/90일 로드맵 | 파일럿 준비, 실행, 평가·확장 계획 포함 | [ ] |

---

## 7.2 개발자 1주 완료 기준

| 산출물 | 완료 기준 | 확인 |
| --- | --- | --- |
| 기준 레포/브랜치 | 표준 폴더 구조와 주요 문서 포함 | [ ] |
| ADR | 하네스 구조, Skill 위치, 검증 전략 결정 기록 | [ ] |
| Skill Package | domain/support/orchestrator Skill 포함 | [ ] |
| Skill 버전 정책 | v0.x, v1.x, breaking change 기준 포함 | [ ] |
| Orchestrator v1 | context passing, human gate, failure handling 포함 | [ ] |
| Task Graph | 순차/병렬/승인 흐름 포함 | [ ] |
| Sub-agent Spec | 역할, 도구 권한, 컨텍스트 경계 포함 | [ ] |
| AGENTS.md | read-first, workspace, commands, verification, prohibited actions 포함 | [ ] |
| Security Checklist | PII, secret, path, external call, logging 기준 포함 | [ ] |
| Verification Strategy | static, smoke, regression, optional E2E 기준 포함 | [ ] |
| Smoke/Regression Fixture | 정상, 경계, 오류, PII 사례 포함 | [ ] |
| Logging Standard | 필수 로그 키와 금지 로그 정의 | [ ] |
| Runbook | 장애 확인, escalation, rollback, recovery 포함 | [ ] |
| SLO Draft | smoke pass rate, output violation, PII incident 등 지표 포함 | [ ] |
| 기술 로드맵 | 다음 2주, 1개월, 분기 단위 계획 포함 | [ ] |

---

# 8. 1주 과정 발표 평가표

| 평가 항목 | 질문 | 점수 0~3 |
| --- | --- | --- |
| 조직 목표 정렬 | 자동화 후보가 조직 목표와 연결되어 있는가? |  |
| 포트폴리오 품질 | 후보 업무가 충분히 발굴·우선순위화되었는가? |  |
| Skill 표준화 | 다른 업무에도 재사용 가능한 Skill 구조인가? |  |
| Workflow/Governance | 승인, 책임, 예외, SLA가 명확한가? |  |
| Workspace/Audit | 원본·초안·최종·증적 관리가 가능한가? |  |
| 검증 가능성 | 샘플 입력, 기대 출력, 통과/실패 기준이 있는가? |  |
| 보안·리스크 | PII, secret, 승인, 로그, 중단 조건이 포함되어 있는가? |  |
| 기술 구현성 | 개발자 산출물로 실제 PoC 또는 파일럿이 가능한가? |  |
| 운영 준비성 | Runbook, rollback, owner, SLO가 있는가? |  |
| 확장 로드맵 | 다음 스프린트/분기 확장 계획이 현실적인가? |  |

총점: ___ / 30

판정:

| 총점 | 판정 | 권장 조치 |
| --- | --- | --- |
| 0~9 | 재설계 필요 | 업무 범위, Skill, 검증 기준 재정의 필요 |
| 10~17 | 내부 보완 필요 | 파일럿 전 추가 리뷰 필요 |
| 18~24 | 파일럿 준비 가능 | 보안·개발 검토 후 파일럿 착수 가능 |
| 25~30 | 조직 확산 후보 | 파일럿과 병행해 표준화 작업 진행 가능 |

---

# 9. 1주 과정 강사용 운영 팁

## 9.1 Day 1 팁

- 후보를 너무 빨리 하나로 좁히지 말고, 조직 목표와 연결해 충분히 비교한다.
- 점수표는 의사결정 도구이지 정답표가 아니라고 설명한다.
- Quick win과 Strategic 후보를 구분한다.

## 9.2 Day 2 팁

- Skill을 개인 문서가 아니라 버전 관리되는 조직 자산으로 설명한다.
- 용어집과 금지 행동을 반드시 작성하게 한다.
- 변경 이력과 사용하지 말아야 하는 경우를 포함시킨다.

## 9.3 Day 3 팁

- Workflow에서 승인자와 책임자가 빠지지 않게 한다.
- RACI는 복잡하게 만들기보다 주요 단계만 다룬다.
- SLA는 정확한 숫자보다 운영 기준을 합의하는 데 초점을 둔다.

## 9.4 Day 4 팁

- Workspace는 감사와 재현 가능성의 기반이라고 설명한다.
- 검증 샘플은 정상 사례만 만들지 말고 경계·오류 사례를 포함한다.
- 개발자 과정에서는 static, smoke, regression의 차이를 명확히 설명한다.

## 9.5 Day 5 팁

- 최종 발표는 교육 결과 공유가 아니라 파일럿 의사결정 자료로 운영한다.
- 스폰서 브리프는 1페이지를 넘기지 않게 한다.
- 로드맵에는 담당자와 일정이 반드시 포함되어야 한다.

---

# 10. 다음 작업 연결

이 1주 과정 확장 자료 다음에는 다음 항목을 작성합니다.

1. 홍보·제안서 자료 정리
2. 최종 자료 패키징
3. 슬라이드/PDF/DOCX 등 배포 형식 변환

