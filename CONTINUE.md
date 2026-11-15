# 다른 PC에서 이어서 작업하기

이 저장소(`intothinair0525/PF`)만 있으면 어느 PC에서든 포트폴리오를 이어서 편집할 수 있습니다.

## 저장소 / 파일
- 저장소: `https://github.com/intothinair0525/PF`
- 공개 주소: `https://intothinair0525.github.io/PF/` (GitHub Pages, `main` 브랜치 루트)
- 편집 대상:
  - **`index.html`** — 메인 허브 (두 작업물 진입점)
  - **`rpa.html`** — 업무 자동화 포트폴리오 본문
  - `assets/inter-tight.css` — 제목용 폰트 (base64 내장, 두 페이지 공용 · **손대지 말 것**)
- 참고: **`KNOBS.md`** — 색·폰트·간격·텍스트 위치 노브 맵

## 관련 코드 저장소 (NEANIO, 전부 private · 정제본)
사내 프로젝트를 민감정보(비밀키·내부 도메인·시트 ID·회사/게임명·라이선스 바이너리) 제거 후 올린 코드 저장소. 로컬 정제본은 `D:\portfolio-code\`.
- `NEANIO/daum-cafe-editor` — Daum 카페 에디터 자동 서식 (Chrome MV3)
- `NEANIO/cs-report-collector` — 운영툴 신고내역 취합 (확장 + Apps Script)
- `NEANIO/community-trend-collector` — 커뮤니티 동향 취합 RPA (Playwright + Sheets)
- `NEANIO/ckeditor-image-uploader` — CKEditor 이미지 다중 업로드 (Chrome MV3)
- `NEANIO/qa-eval-aggregator` — QA 평가 데이터 취합 (**개요 README만**; 소스는 개인정보 때문에 비공개)

## 새 PC 세팅 (5분)
1. **Git** 설치 → `https://git-scm.com`
2. **VS Code** 설치 + 확장 **Live Preview**(Microsoft)
3. 저장소 클론:
   ```
   git clone https://github.com/intothinair0525/PF.git
   ```
4. **GitHub 인증**: 첫 `git push` 시 로그인 창이 뜸 → **intothinair0525 계정**으로 로그인.
   - 또는 새 **Personal Access Token**(fine-grained, Contents: Read/Write) 발급해 사용.
   - ⚠️ 이전 대화에서 공유했던 토큰은 **폐기(revoke)** 하고 새로 발급하세요.

## 편집 → 반영 흐름
1. 고칠 파일(`index.html` 또는 `rpa.html`) 열고 → 우클릭 **Show Preview** (저장 시 즉시 반영)
   - 폰트가 상대경로 CSS로 분리돼 있으니 **Live Preview(HTTP)로 열어야** 제목 폰트가 제대로 보입니다.
2. 수정 후 저장소에 올리기:
   ```
   git add -A
   git commit -m "수정 내용"
   git push
   ```
3. 1~2분 후 `https://intothinair0525.github.io/PF/` 에 반영됩니다.

## 포맷 전 백업 체크리스트 (이 저장소 밖)
이 저장소는 포트폴리오 페이지만 담습니다. 아래는 **로컬에만 있으니 따로 백업**하세요(외장하드/클라우드):
- `D:\02_개인_프로젝트\` (weverse 등 개인 프로젝트 — git 없음)
- `D:\03_디자인\`, `D:\04_개인자료\` (디자인 작업물·사진)
- `D:\포트폴리오\ATF-case-studies\` 등 포트폴리오 보조 자료
- (사내 ATF 프로젝트는 회사 git `itzel-knw`에 있음)
