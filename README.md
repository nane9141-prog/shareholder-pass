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

## 현장 제어와의 연동

`live.html` 은 conexus 의 **주주총회 현장 제어**가 내보낸 상태를 그대로 따라간다.
서버는 쓰지 않고 `localStorage` 두 칸을 같이 본다.

| 칸 | 담는 것 |
|---|---|
| `cx.live` | 현재 의안, 표결 단계, 남은 시간, 송출 중인 질의·발언 |
| `cx.clock` | 경과 시계, 영상 재생 위치와 보낸 시각 |

`localStorage` 는 출처(origin)별로 나뉘므로 **두 화면이 같은 호스트에서 열려 있어야**
한다. 같은 GitHub Pages 계정(`<id>.github.io/conexus-demo` 와 `.../shareholder-pass`)
이나 같은 로컬 서버에서 열면 그대로 맞물린다.

영상은 보낸 시각 이후 흐른 만큼을 더해 위치를 맞추고, 1.5초 넘게 벌어질 때만
따라잡는다. 브라우저가 소리 있는 자동재생을 막으므로 처음에는 음소거로 시작하고,
화면의 **소리 켜기**로 켠다.

운영자 쪽 화면은 [conexus-demo](https://github.com/nane9141-prog/conexus-demo) 에 있다.
