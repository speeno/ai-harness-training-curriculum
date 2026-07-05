# PPT to CMS 매핑 (Harness 코스)

본 문서는 제안서 패키지의 PDF 기본 교육자료를 AcademiQ 코스 CMS 레슨과 일관되게 매핑하기 위한 기준 문서이다.

## 1) PDF 기본 자료 매핑

| PDF 파일 | 페이지 | 적용 코스(slug) | CMS 모듈/레슨(목표) | CMS 소스 파일 |
| --- | --- | --- | --- | --- |
| `3.공통교육PPT/하네스_Agent_Skills_공통교육_소개.pdf` | 13 | `harness-nondev-1d`, `harness-dev-1d`, `harness-nondev-3d`, `harness-dev-3d`, `harness-nondev-1w`, `harness-dev-1w` | `M0 공통 오프닝` / `공통 교육 소개 (PPT)` | `materials/01_overall_training_intro_material.md` |
| `4.비개발자1일교육PPT/하네스_Agent_Skills_비개발자_1일_교육.pdf` | 19 | `harness-nondev-1d` | `M1 비개발자 1일 핵심 세션` / `비개발자 1일 슬라이드` | `materials/02_non_developer_1_day_slides_recreated.md` |
| `5.개발자1일교육PPT/하네스_Agent_Skills_개발자_1일_교육.pdf` | 21 | `harness-dev-1d` | `M1 개발자 1일 핵심 세션` / `개발자 1일 슬라이드` | `materials/04_developer_1_day_slide_material.md` |
| `6.3일교육소개PPT/하네스_Agent_Skills_3일_교육_소개.pdf` | 15 | `harness-nondev-3d`, `harness-dev-3d` | `M1 3일 과정 소개` / `3일 과정 소개 (공통)` | `materials/proposal package/03-course-options-1day-3day-1week.md` |
| `7.1주과정소개PPT/하네스_Agent_Skills_1주_과정_소개.pdf` | 15 | `harness-nondev-1w`, `harness-dev-1w` | `M1 1주 과정 소개` / `1주 과정 소개 (공통)` | `materials/proposal package/03-course-options-1day-3day-1week.md` |

## 2) 기존 자료와 차이점(diff 요약)

| 항목 | 기존 | 변경 |
| --- | --- | --- |
| 공통 오프닝 | `materials/01_overall_training_intro_material.md` 단일 장문 설명 | 동일 파일을 공통 정본으로 고정하고 6개 코스 M0에 동일 반영 |
| 1일 비개발/개발 | 이미 슬라이드형 md 존재 | 기존 파일 유지 + PDF 정본 동기화 메모 추가 |
| 3일 소개 | `materials/08_three_day_course_expansion_material.md` 중심 | 소개 레슨은 `materials/proposal package/03-course-options-1day-3day-1week.md`, 심화 레슨은 `materials/08_three_day_course_expansion_material.md`로 분리 |
| 1주 소개 | `materials/09_one_week_course_expansion_material.md` 중심 | 소개 레슨은 `materials/proposal package/03-course-options-1day-3day-1week.md`, 심화 레슨은 `materials/09_one_week_course_expansion_material.md`로 분리 |
| 3일/1주 dev·nondev 공유 | 일부 코스에서 소스 불일치 | 동일 `sourcePath`를 강제해 공통 소개 레슨 일치 |

## 3) 운영 규칙

1. 3일/1주 소개 레슨은 dev/nondev 모두 같은 소스를 사용한다.
2. 확장 장문본(`08_*_expansion`, `09_*_expansion`)은 Day별 심화 레슨으로 분리해 사용한다.
3. PDF가 개정되면 우선 본 매핑 문서를 갱신한 뒤, 연결된 md와 `manifest.yaml`을 순차 업데이트한다.
