# 강준이의 블로그

동물과 기술, 새롭게 배우는 것들에 관한 이야기를 기록하는 개인 블로그입니다. Jekyll과 [Hacked Jekyll 테마](https://github.com/piazzai/hacked-jekyll)를 사용합니다. 원래 JSON처럼 보이는 한 페이지 소개 테마에 블로그 글 목록과 개별 글 화면을 추가했습니다.

사이트 주소: <https://ddjj11204.github.io>

## Windows에서 로컬로 실행하기

### 준비물

- Windows용 Ruby+Devkit
- Git

RubyInstaller는 [공식 다운로드 페이지](https://rubyinstaller.org/downloads/)에서 받을 수 있습니다. 설치 후 PowerShell을 새로 열어 Ruby가 인식되는지 확인합니다.

```powershell
ruby --version
bundle --version
```

### 미리보기 서버 시작하기

PowerShell에서 저장소 폴더로 이동한 뒤 필요한 패키지를 설치하고 Jekyll을 실행합니다.

```powershell
cd C:\Users\김진주\Documents\ddjj11204.github.io
bundle install
bundle exec jekyll serve
```

서버가 시작되면 브라우저에서 <http://localhost:4000>을 엽니다. 미리보기 중에는 PowerShell 창을 열어 두세요. 서버를 종료하려면 PowerShell에서 `Ctrl+C`를 누릅니다.

## 자기소개 수정하기

홈 화면의 소개와 장래희망은 `_data/json.yml`에서 수정합니다. 목록 항목마다 `key`는 화면에 표시할 이름이고 `value`는 표시할 내용입니다.

## 블로그 글 작성하기

새 글은 `_posts` 폴더에 `연도-월-일-제목.md` 형식으로 만듭니다. 예를 들면 `2026-11-17-동물의-행동.md`입니다.

```markdown
---
layout: post
title: "동물의 행동을 관찰하며"
date: 2026-11-17 12:00:00 +0900
---

여기에 글을 씁니다. 제목은 `#`, 목록은 `-`를 사용해 작성할 수 있습니다.
```

작성한 글은 `/blog/` 목록에 자동으로 나타납니다. 글 목록 페이지는 `blog.md`에서 관리합니다.

## GitHub Pages에 게시하기

저장소의 GitHub Pages 게시 설정에서 **Settings → Pages → Build and deployment → Source → GitHub Actions**를 선택합니다. `.github/workflows/pages.yml`이 `main` 브랜치에 푸시된 사이트를 빌드하고 게시합니다.

변경 사항을 게시하려면 저장소 폴더에서 아래 명령을 실행합니다.

```powershell
git add .
git commit -m "글 또는 사이트 변경 내용"
git push origin main
```

GitHub Actions 탭에서 빌드 및 게시 상태를 확인할 수 있습니다.
