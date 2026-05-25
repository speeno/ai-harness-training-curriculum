# Smoke Verification: voc-store-report

| Check | Expected | Result |
| --- | --- | --- |
| Output exists | `workspace/out/voc-store-report-draft.md` 또는 `workspace/out/voc-store-report-v1.md`가 있다 | [ ] |
| Input preserved | `workspace/in/` 원본이 수정되지 않았다 | [ ] |
| Required sections | Overview, 표, human_review_required, 다음 액션, Review Notes가 있다 | [ ] |
| Evidence based | 입력에 없는 사실을 확정하지 않았다 | [ ] |
| Sensitive data | 민감정보가 출력되지 않았다 | [ ] |
| Human review | 다음 항목이 검토 필요로 표시되었다: 고객 개인정보 노출, 불만 표현을 사실처럼 단정, 매장 귀책을 과도하게 판단 | [ ] |

## Fail 처리

Fail 항목이 있으면 `workspace/out/smoke-result.md`에 원인과 수정 제안을 작성하고 `prompts/05-iterate-fix.md`를 실행합니다.
