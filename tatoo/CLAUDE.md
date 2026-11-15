# 잉크장부 작업 안내 (Claude Code용)

타투이스트를 위한 수입·경비 기록과 종합소득세 미리보기 사이트. SK AIGEN 1기 지원 포트폴리오로 사용한다.

## 구조

- `index.html` — 사이트 전체. HTML, CSS, JS가 한 파일에 있다. 빌드 도구 없음.
- `photos/` — FORMOSA TATTOO EXPO 탭에 들어갈 사진. 원본(KakaoTalk_*.jpg)과 웹용 사본(expo-NN.jpg)이 함께 있다.
- `README.md` — 저장소 첫 화면 설명.

탭은 5개: 장부(`#ledger`), 세금 미리보기(`#tax`), 절세 방법(`#saving`), 홈택스 가이드(`#hometax`), FORMOSA TATTOO EXPO(`#expo`).

## 사진 추가하는 법

1. 사진을 `photos/`에 넣는다. 파일명은 영문 소문자와 하이픈만 (`expo-10.jpg`).
2. 한 장이 500KB를 넘으면 가로 1600px 이하로 줄여서 저장한다. 원본은 삭제하지 않는다.
3. `index.html`의 `const PHOTOS=[ ... ]` 배열에 한 줄씩 추가한다.
   `{src:'photos/expo-10.jpg', alt:'사진 설명(스크린리더·SEO용)'}`
4. 손님이나 다른 아티스트 얼굴이 보이는 사진은 동의를 받은 것만 쓴다.

## 디자인 규칙

- 색은 `:root`의 CSS 변수만 쓴다. 다크 모드 값은 `@media (prefers-color-scheme: dark)` 블록에 같이 넣는다.
- 강조색은 스텐실 보라색(`--stencil`) 하나. 납부는 `--pay`, 환급은 `--refund`.
- 글꼴: 제목 Black Han Sans, 본문 IBM Plex Sans KR, 숫자 IBM Plex Mono.
- 휴대폰 폭(약 400px)에서 가로 스크롤이 생기면 안 된다.
- 헤더 하단 선: 1px solid `--line` (기존 대시 선 아님).
- 사진 그리드: 3열 정사각형, gap 3px, `.expo-cell` 버튼 안에 `<img loading="lazy">`.

## 세금 계산 수정 시 주의

- 계산 로직은 `compute()`, `both()`, `BR`(세율표), `simpleExp()`(단순경비율)에 있다.
- 기준은 2025년 귀속 경비율. 2026년 귀속 경비율이 고시되면 `simpleExp()`와 "계산 기준" 목록을 함께 고친다.
- 숫자를 바꾸면 수입 3,000만 원 / 경비 900만 원 / 3.3% 수입 600만 원 예시로 결과가 말이 되는지 확인한다.

## 배포

GitHub Pages: Settings → Pages → Branch `main`, 폴더 `/ (root)`. 몇 분 뒤 `아이디.github.io/저장소이름`으로 열린다.
