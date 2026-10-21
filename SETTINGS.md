# 개인정보처리방침 레포지토리 설정 가이드

<p align="center">
  <img src="./512x512.png" alt="앱 아이콘" width="200">
</p>

이 레포지토리는 <b>"Sand Drop Puzzle"</b> 앱의 개인정보처리방침을 제공하는 문서를 포함하고 있습니다.  
앱 사용자들에게 개인정보처리방침을 명확히 안내하기 위해 생성된 저장소입니다.

---

## 링크

<!-- [확인 필요] GitHub Pages 배포 URL을 확정한 뒤 아래 링크를 수정해 주세요. -->

<a href="https://kojaem-app-policies.github.io/SandDropPuzzle-Privacy-Policy">개인정보처리방침</a>

---

## 로컬에서 실행하기

이 사이트는 [Jekyll](https://jekyllrb.com/) 기반입니다. Ruby가 필요합니다.

### 1. 사전 준비

```bash
ruby -v
```

Ruby가 없다면 (macOS):

```bash
brew install ruby
```

### 2. 의존성 설치

```bash
gem install bundler
bundle install
```

### 3. 로컬 서버 실행

```bash
bundle exec jekyll serve
```

또는:

```bash
./script/server
```

### 4. 브라우저에서 확인

**http://127.0.0.1:4000**

서버를 종료하려면 터미널에서 `Ctrl + C`를 누르세요.  
`index.md` 등을 수정하면 저장 후 자동으로 다시 빌드됩니다.

> 참고: `깃 저장소가 아닙니다`, Sass deprecation 경고는 로컬 미리보기에 영향 없습니다.

---

## GitHub Pages로 배포하기

### 1. GitHub에 저장소 만들기

1. [GitHub](https://github.com)에서 새 저장소를 만듭니다.
   - 예시 조직: `kojaem-app-policies`
   - 저장소 이름: `SandDropPuzzle-Privacy-Policy`
2. 로컬 폴더를 git 저장소로 초기화한 뒤 푸시합니다.

```bash
cd /Users/kojaemin/Documents/SandDropPuzzle-Privacy-Policy
git init
git add .
git commit -m "Initial commit: Sand Drop Puzzle 개인정보처리방침"
git branch -M main
git remote add origin https://github.com/kojaem-app-policies/SandDropPuzzle-Privacy-Policy.git
git push -u origin main
```

> 조직/저장소 이름이 다르면 `origin` URL과 아래 Pages URL을 맞춰 주세요.

### 2. Pages 설정

1. GitHub 저장소 → **Settings** → **Pages**
2. **Source**를 **Deploy from a branch**로 선택
3. **Branch**를 `main` / `/ (root)` 로 설정 후 **Save**

Jekyll 테마(`jekyll-theme-cayman`)를 쓰고 있어서, GitHub Pages가 자동으로 빌드·배포합니다.

### 3. 배포 확인

몇 분 후 아래 주소에서 확인할 수 있습니다.

**https://kojaem-app-policies.github.io/SandDropPuzzle-Privacy-Policy/**

배포 상태는 저장소 **Settings → Pages**, 또는 **Actions** 탭에서 확인할 수 있습니다.

### 4. 배포 후 확인 사항

- README의 링크 URL이 실제 Pages 주소와 같은지 확인
- `_config.yml`의 `github.pdf_url` 경로가 저장소 이름과 맞는지 확인  
  (예: `/SandDropPuzzle-Privacy-Policy/assets/downloads/...`)

## PDF 만들기

사이트 헤더의 **Download .PDF** 버튼으로 다운받는 `assets/downloads/privacy_policy_SandDropPuzzle.pdf`를 만드는 방법은 다음과 같습니다.

> `index.md` 내용을 수정했다면 PDF도 다시 만들어 교체하세요.

### 1. 확장 프로그램 설치

VS Code / Cursor에서 [Markdown PDF](https://marketplace.visualstudio.com/items?itemName=yzane.markdown-pdf) (`yzane.markdown-pdf`)를 설치합니다.

### 2. PDF 내보내기

1. `index.md`를 연다
2. 명령 팔레트 열기 (`Cmd + Shift + P` / `Ctrl + Shift + P`)
3. **Markdown PDF: Export (pdf)** 실행
4. 같은 폴더에 `index.pdf`가 생성된다

### 3. 다운로드용 파일로 옮기기

```bash
mv index.pdf assets/downloads/privacy_policy_SandDropPuzzle.pdf
```

이후 변경된 PDF를 커밋·푸시하면 GitHub Pages의 다운로드 링크에도 반영됩니다.
