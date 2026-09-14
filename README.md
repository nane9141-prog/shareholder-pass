# 주주PASS — 전자주주총회 주주 화면 데모

주주가 보는 쪽 화면을 정적 HTML 로 만든 시연물이다. 빌드 과정이 없고,
파일을 그대로 열면 동작한다.

| 파일 | 화면 |
|---|---|
| `index.html` | 주주총회 찾기 — 기업 목록과 진행 상태 |
| `company.html` | 기업 상세 — 의안 목록·자료·사전 행사 |
| `live.html` | 생중계 — 실시간 의안 진행과 표결 |

`assets/` 에 브랜드 로고(`logo-pass.svg`), 메인 배너, 기업 로고 15종이 들어 있다.
기업 로고는 `index.html` 의 `COMPANIES[].img` 키와 `assets/logo-<키>.png` 가 짝을 이룬다.

운영자 쪽 화면은 [conexus-demo](https://github.com/nane9141-prog/conexus-demo) 에 있다.
