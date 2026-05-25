# Smoke Verification: launch-readiness-brief

| Check | Expected | Result |
| --- | --- | --- |
| Output exists | `workspace/out/launch-readiness-brief-draft.md` 또는 `workspace/out/launch-readiness-brief-v1.md`가 있다 | [ ] |
| Input preserved | `workspace/in/` 원본이 수정되지 않았다 | [ ] |
| Required sections | Overview, 표, human_review_required, 다음 액션, Review Notes가 있다 | [ ] |
| Evidence based | 입력에 없는 사실을 확정하지 않았다 | [ ] |
| Sensitive data | 민감정보가 출력되지 않았다 | [ ] |
| Human review | 다음 항목이 검토 필요로 표시되었다: 표시·인증 요구사항 누락, 원가·MOQ 단정, 디자인 피드백과 유통 일정 충돌 미표시 | [ ] |

## Fail 처리

Fail 항목이 있으면 `workspace/out/smoke-result.md`에 원인과 수정 제안을 작성하고 `prompts/05-iterate-fix.md`를 실행합니다.
