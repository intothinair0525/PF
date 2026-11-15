# 포트폴리오 노브 맵 (rpa.html 직접 수정용)

편집 파일: **`D:\knw_portfolio-main\rpa.html`** (RPA 포트폴리오 본문)
메인 허브 페이지는 `index.html`이며, 같은 토큰·컴포넌트를 쓰므로 아래 노브가 그대로 적용됩니다.

> ⚠️ 줄 번호는 **폰트를 `assets/inter-tight.css`로 분리하기 전** 기준이라 현재 파일과 맞지 않습니다.
> 분리로 앞쪽 4줄이 빠지고 문서 골격(doctype·head) 7줄이 들어갔으니, `Ctrl+F`로 셀렉터/문구를 검색하세요.

---

## 0. 시작 — VS Code Live Preview
1. 확장 설치: **Live Preview** (Microsoft)
2. `index.html` 열고 → 우클릭 **"Show Preview"** (또는 `Ctrl+Shift+P` → `Live Preview: Show Preview`)
3. 옆 패널에 뜨고, **저장(Ctrl+S) 시 자동 새로고침**

> ⚠️ 다크/라이트 모드 확인: 미리보기는 OS 테마를 따릅니다.

---

## 1. 색상 (Colors)
**토큰이 4곳에 중복 정의**돼 있습니다. 색을 바꾸려면 **라이트는 2곳, 다크는 2곳 모두** 같이 고쳐야 반영됩니다.

> ⚠️ 같은 4블록이 `index.html`에도 **동일하게** 들어 있습니다. 색을 바꾸면 **두 파일 모두** 고쳐야
> 허브와 포트폴리오의 톤이 어긋나지 않습니다 (= 총 8군데).

| 테마 | 고칠 위치 | 줄 |
|---|---|---|
| 라이트 | `:root { … }` **과** `:root[data-theme="light"]` | ~10, ~29 |
| 다크 | `@media (prefers-color-scheme: dark)` **과** `:root[data-theme="dark"]` | ~24, ~33 |

**토큰 의미**
| 변수 | 쓰임 | 현재(라이트) |
|---|---|---|
| `--bg` | 페이지 배경 | `#F0F2F5` |
| `--surface` / `--surface-2` | 카드/패널 배경 | `#E7EAEE` |
| `--ink` | 본문 기본 글자 | `#181A1D` |
| `--ink-soft` | 보조 글자(설명 한글) | `#3A3E44` |
| `--muted` | 흐린 글자(한글 소제목) | `#5E636B` |
| `--faint` | 가장 흐림(라벨·영문 번역·번호) | `#8A9099` |
| `--line` / `--line-soft` | 구분선 | `#D7DBE0` |

> 예: 배경을 더 밝게 → `:root`와 `:root[data-theme="light"]` 두 곳의 `--bg` 를 같이 변경.

---

## 2. 폰트 (Typography)
| 대상 | 변수/셀렉터 | 줄 | 값 |
|---|---|---|---|
| 제목용 폰트 | `--display` | 19 | `"Inter Tight", …` |
| 본문 폰트 | `--sans` | 20 | `"Noto Sans KR", …` |
| 히어로 대제목 | `.hero h1` `font-size` | 72 | `clamp(2.5rem, 6.2vw, 4.75rem)` |
| 히어로 한글 리드 | `.hero .ko-lead` | 79 | `clamp(1.1rem,2.3vw,1.4rem)` |
| 히어로 설명 | `.hero .desc` | 83 | `1.02rem` |
| 섹션 제목(Work/Approach/Contact) | `.sec-head h2` | 96 | `1.5rem` |
| 프로젝트 제목 | `.proj .ptitle` | 112 | `clamp(1.7rem, 3.6vw, 2.6rem)` |
| 프로젝트 한글 부제 | `.proj .pko` | 116 | `1.02rem` |
| 프로젝트 설명(한/영) | `.proj .pdesc` / `.pdesc .en` | 117/118 | `1rem` / `0.9rem` |
| Approach 인트로 | `.approach .big` | 137 | `clamp(1.1rem,2vw,1.35rem)` |
| 단계 제목 | `.steps .step-title` | 150 | `1.2rem` |
| 단계 설명(한/영) | `.steps .step-desc` / `.en` | 154/156 | `0.98rem` / `0.86rem` |

> `clamp(최소, 가변, 최대)` — 글자 크기를 바꾸려면 보통 **세 번째 값(최대)**을 조정하면 됩니다.

---

## 3. 간격 (Spacing)
| 대상 | 셀렉터 · 속성 | 줄 | 현재 |
|---|---|---|---|
| 프로젝트 항목 세로 여백 | `.proj` `padding` | ~102 | `42px 0` |
| 프로젝트 제목↔설명 | `.proj .pdesc` `margin` | 117 | `20px 0 0` |
| 설명 한글↔영문 | `.proj .pdesc .en` `margin-top` | 118 | `9px` |
| 기간/리소스 줄 위 여백 | `.proj-stats` `margin-top` | 119 | `14px` |
| 단계 제목↔본문 | `.steps .step-desc` `margin-top` | 154 | `15px` |
| 단계 한글↔영문 | `.steps .step-desc .en` `margin-top` | 156 | `5px` |
| 섹션 제목 위 여백 | `.sec-head` `padding` | ~95 | `86px 0 14px` |
| 푸터 여백 | `footer` `padding` | 163 | `72px 0 80px` |

---

## 4. 텍스트 콘텐츠 위치
| 내용 | 줄 |
|---|---|
| 브라우저 탭 제목 | 1 (`<title>`) |
| 이름·역할 (상단) | 190 (`.eyebrow`) |
| 히어로 대제목(영문) | 191 (`<h1>`) |
| 히어로 한글 리드 | 192 (`.ko-lead`) |
| 히어로 설명(한/영) | 193~ (`.desc`) |
| **섹션 제목** Selected Work / Approach / Contact | 208 / 309 / 369 |
| **Daum Cafe Editor** 제목 / 한글 / (설명·기간은 바로 아래) | 216 / 217 |
| **QA Evaluation** 제목 / 한글 | 234 / 235 |
| **Community Trend** 제목 / 한글 | 252 / 253 |
| **Ops Report** 제목 / 한글 | 270 / 271 |
| **CKEditor Uploader** 제목 / 한글 | 288 / 289 |
| Approach 인트로(한/영) | 311~ |
| 단계 제목 Define/Design/Build/Verify/Ship | 320 / 329 / 338 / 347 / 356 |
| 이메일 / GitHub 링크 | 373 / 374 |
| 비공개 안내 문구(한/영) | 376~ |

> 각 프로젝트: `pko`(한글 부제) 바로 **아래 3줄**이 `proj-stats`(기간·리소스), 그 다음이 `pdesc`(설명 한/영)입니다.

---

## 5. 자주 쓰는 빠른 조정
| 하고 싶은 것 | 어디를 |
|---|---|
| 배경색 변경 | `--bg` (라이트 2곳 / 다크 2곳) |
| 전체 글자색 톤 | `--ink`, `--muted`, `--faint` |
| 특정 제목만 키우기/줄이기 | 해당 셀렉터 `font-size` |
| 줄 간격(섹션/항목) | 해당 `margin` / `padding` |
| 한 구절 안 끊기게 | 그 구절을 `<span class="nw">…</span>` 로 감싸기 |
| 특정 위치 강제 줄바꿈 | `<br>` 삽입 |

---

## 6. 반영(배포) 방법 — 중요
- **로컬 미리보기**: 저장만 하면 Live Preview에 즉시 반영. ✅ 여기까진 혼자 가능.
  - ⚠️ 폰트가 상대경로 CSS로 분리됐으니 **Live Preview(HTTP)로 열어야** 제목 폰트가 제대로 보입니다.
    파일을 더블클릭해 `file://`로 열면 폴백 폰트로 보일 수 있습니다.
- **실제 반영**: 아래 3줄이면 끝. 1~2분 후 <https://intothinair0525.github.io/PF/> 에 올라갑니다.
  ```
  git add -A
  git commit -m "수정 내용"
  git push
  ```
  첫 `git push`에서 GitHub 로그인 창이 뜨면 **intothinair0525 계정**으로 로그인하세요.

> 즉, **디자인 실험은 Live Preview로 빠르게**, 마음에 들면 **커밋·푸시** — 이 흐름을 추천합니다.
