# 포트폴리오 별도 저장소 분리 및 GitHub Pages 배포 가이드 📦

이 문서는 `portfolio/` 디렉토리를 **별도 GitHub 저장소**로 분리하고, **GitHub Pages**로 배포하는 전체 과정을 안내합니다.

---

## 🎯 목표

- `portfolio/` 디렉토리를 독립 저장소로 분리
- GitHub Pages로 웹사이트 배포
- `https://chanho0908.github.io/keepiluv-agent-portfolio/` URL로 접근 가능하게 설정

---

## 📋 단계별 가이드

### 1단계: 새 GitHub 저장소 생성

#### GitHub 웹사이트에서 생성
1. [GitHub](https://github.com)에 로그인
2. 우측 상단 `+` → `New repository` 클릭
3. 저장소 설정:
   - **Repository name**: `keepiluv-agent-portfolio`
   - **Description**: `Keepiluv-Agent 프로젝트 포트폴리오 웹사이트`
   - **Visibility**: `Public` (GitHub Pages는 Public 저장소 필요)
   - **Initialize**: 체크 해제 (README, .gitignore, license 모두 체크 안 함)
4. `Create repository` 클릭

---

### 2단계: 포트폴리오 파일 복사 및 초기화

#### 로컬에서 작업
```bash
# 1. 포트폴리오 저장소 디렉토리 생성
cd ~/Documents/Android
mkdir keepiluv-agent-portfolio
cd keepiluv-agent-portfolio

# 2. Git 초기화
git init
git branch -M main

# 3. 기존 portfolio 폴더의 파일들 복사
cp -r ../Keepiluv-Agent/portfolio/* .

# 4. HTML 파일명을 index.html로 변경 (GitHub Pages 기본 페이지)
mv keepiluv-agent-portfolio.html index.html

# 5. 파일 확인
ls -la
```

**예상 파일 목록:**
```
.
├── index.html                  # 메인 페이지 (이름 변경됨)
├── README.md                   # 포트폴리오 가이드
├── DEPLOYMENT.md              # 이 파일
├── hero-character-main.png
├── hero-character-1.png
├── hero-character-2.png
├── overview-character.png
└── wiki-character.png
```

---

### 3단계: Git 커밋 및 푸시

```bash
# 1. 모든 파일 스테이징
git add .

# 2. 첫 커밋
git commit -m "🎉 Initial commit: Keepiluv-Agent portfolio website

- Add portfolio landing page (index.html)
- Add character images for hero, overview, wiki sections
- Add README and deployment guide"

# 3. 원격 저장소 연결
git remote add origin https://github.com/chanho0908/keepiluv-agent-portfolio.git

# 4. 푸시
git push -u origin main
```

---

### 4단계: GitHub Pages 설정

#### GitHub 웹사이트에서 설정
1. 저장소 페이지 접속: `https://github.com/chanho0908/keepiluv-agent-portfolio`
2. `Settings` 탭 클릭
3. 왼쪽 메뉴에서 `Pages` 클릭
4. **Source** 섹션:
   - Branch: `main` 선택
   - Folder: `/ (root)` 선택
   - `Save` 클릭
5. 배포 완료 대기 (1~2분 소요)

#### 배포 확인
- 페이지 상단에 녹색 박스로 URL 표시:
  ```
  ✅ Your site is live at https://chanho0908.github.io/keepiluv-agent-portfolio/
  ```
- 클릭해서 페이지 확인

---

### 5단계: 메인 저장소 업데이트

#### Keepiluv-Agent 저장소의 README.md 업데이트

기존 로컬 경로 링크를 GitHub Pages URL로 변경:

```markdown
<!-- 변경 전 -->
**📁 프로젝트 소개**: [포트폴리오 페이지](portfolio/keepiluv-agent-portfolio.html)

<!-- 변경 후 -->
**📁 프로젝트 소개**: [포트폴리오 페이지](https://chanho0908.github.io/keepiluv-agent-portfolio/)
```

"처음에는 무엇을 보면 되나요?" 테이블도 업데이트:

```markdown
| **프로젝트 전체 소개 (비개발자용)** | **[포트폴리오 페이지](https://chanho0908.github.io/keepiluv-agent-portfolio/)** |
```

---

### 6단계: portfolio/ 디렉토리 정리 (선택사항)

별도 저장소로 분리했으므로, 메인 저장소의 `portfolio/` 디렉토리 처리 방법:

#### 옵션 A: 완전 삭제
```bash
cd ~/Documents/Android/Keepiluv-Agent
git rm -r portfolio/
git commit -m "📦 Move portfolio to separate repository

Portfolio is now maintained at:
https://github.com/chanho0908/keepiluv-agent-portfolio

Live site:
https://chanho0908.github.io/keepiluv-agent-portfolio/"
```

#### 옵션 B: 링크 파일로 교체
```bash
# portfolio/ 디렉토리 삭제 후 README만 남기기
cd ~/Documents/Android/Keepiluv-Agent
rm -rf portfolio/*
cat > portfolio/README.md << 'EOF'
# Portfolio 이동 안내

포트폴리오는 별도 저장소로 분리되었습니다.

## 🔗 새 위치

- **저장소**: https://github.com/chanho0908/keepiluv-agent-portfolio
- **웹사이트**: https://chanho0908.github.io/keepiluv-agent-portfolio/

수정이 필요하면 위 저장소에서 작업해주세요.
EOF

git add portfolio/README.md
git commit -m "📝 Add portfolio redirect notice"
```

---

## ✅ 최종 확인 체크리스트

- [ ] 새 저장소 `keepiluv-agent-portfolio` 생성됨
- [ ] 포트폴리오 파일이 새 저장소에 푸시됨
- [ ] GitHub Pages 설정 완료
- [ ] `https://chanho0908.github.io/keepiluv-agent-portfolio/` 접속 확인
- [ ] 이미지가 모두 정상적으로 표시됨
- [ ] Sticky Navigation, 애니메이션 등 기능 작동 확인
- [ ] 메인 저장소 README.md의 링크 업데이트됨
- [ ] 메인 저장소의 `portfolio/` 디렉토리 정리 완료

---

## 🔧 추가 설정 (선택사항)

### Custom Domain 설정
자신의 도메인을 연결하려면:

1. 도메인 구매 (예: `yourname.com`)
2. DNS 설정:
   ```
   Type: CNAME
   Name: portfolio (또는 원하는 서브도메인)
   Value: chanho0908.github.io
   ```
3. GitHub Pages 설정 → Custom domain에 `portfolio.yourname.com` 입력
4. `Enforce HTTPS` 체크

### Google Analytics 추가
방문자 추적을 원한다면 `index.html`의 `</head>` 전에 추가:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### SEO 개선
`index.html`에 Open Graph 이미지 추가:

```html
<meta property="og:image" content="https://chanho0908.github.io/keepiluv-agent-portfolio/hero-character-main.png">
```

---

## 🚨 문제 해결

### 페이지가 404 에러
- GitHub Pages 설정에서 Branch가 `main`이고 폴더가 `/ (root)`인지 확인
- 배포 완료까지 1~2분 대기
- Actions 탭에서 `pages-build-deployment` 워크플로우 상태 확인

### 이미지가 안 보임
- 이미지 파일명이 `index.html`에서 참조하는 이름과 정확히 일치하는지 확인
- 대소문자 구분 (GitHub Pages는 대소문자를 구분함)
- 브라우저 캐시 삭제 후 다시 시도

### CSS/JavaScript 작동 안 함
- 브라우저 개발자 도구(F12) → Console 탭에서 에러 확인
- 외부 리소스(폰트, CDN) 로드 실패 여부 확인

---

## 📚 참고 자료

- [GitHub Pages 공식 문서](https://docs.github.com/en/pages)
- [GitHub Pages 커스텀 도메인 설정](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [Markdown 가이드](https://guides.github.com/features/mastering-markdown/)

---

**작성일**: 2026-06-16
**최종 업데이트**: 2026-06-16
