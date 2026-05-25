# 공통 프롬프트 템플릿

## 목적

{이 프롬프트가 수행할 일}

## 전제 파일

- `AGENTS.md`
- `docs/business-scenario.md`
- `skills/{task}/SKILL.md`
- `workspace/in/`

## Agent에게 줄 지시문

아래 파일을 읽고 지시를 수행하세요. 원본 입력은 수정하지 말고 결과는 지정된 `workspace/out/` 경로에 저장하세요.

## 기대 출력

- `{output_path}`

## 금지 사항

- 입력에 없는 사실을 만들어내지 마세요.
- 개인정보·민감정보를 최종 산출물에 포함하지 마세요.
- 사람 승인 없이 최종 판단을 확정하지 마세요.
