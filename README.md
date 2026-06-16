# Keepiluv-Agent 포트폴리오 📁

이 디렉토리는 **Keepiluv-Agent 프로젝트 소개 페이지**와 관련 자료들을 담고 있습니다.

---

## 📄 파일 목록

### 웹 페이지
- **`keepiluv-agent-portfolio.html`** - 프로젝트 포트폴리오 메인 페이지
  - 프로젝트 개요
  - LLM Wiki 소개
  - 12개 Agent 설명
  - Reusable Skills 목록
  - 프로젝트 성과

### 이미지 자료

#### Hero 섹션
- **`hero-character-main.png`** (2.3MB) - 메인 히어로 캐릭터 이미지

#### 대체 캐릭터 (미사용)
- `hero-character-1.png` (933KB)
- `hero-character-2.png` (922KB)

#### 섹션별 캐릭터
- **`overview-character.png`** (2.3MB) - 개요 섹션 캐릭터
- **`wiki-character.png`** (1.5MB) - Wiki 섹션 캐릭터

---

## 🌐 포트폴리오 페이지 보기

### 로컬에서 보기
```bash
open portfolio/keepiluv-agent-portfolio.html
```

또는 파일 탐색기에서 `keepiluv-agent-portfolio.html`을 더블클릭하세요.

### 웹에 배포하기

#### GitHub Pages
1. GitHub 저장소 Settings → Pages
2. Source: Deploy from a branch
3. Branch: `main` / `portfolio` 폴더 선택
4. Save

배포 후 URL: `https://chanho0908.github.io/Keepiluv-Agent/portfolio/keepiluv-agent-portfolio.html`

#### Vercel (권장)
```bash
# Vercel CLI 설치
npm i -g vercel

# 배포
vercel --prod
```

Vercel은 자동으로 빌드하고 HTTPS URL을 제공합니다.

---

## 🎨 디자인 시스템

### 컬러 팔레트 (Spotify-inspired)
- **Primary Green**: `#1ed760` - Spotify Green
- **Dark Background**: `#121212` - Near Black
- **Surface**: `#181818` - Dark Surface
- **Text**: `#ffffff` / `#c5c5c5` - WCAG AAA 준수

### 타이포그래피
- **본문 폰트**: Inter (Google Fonts)
- **코드 폰트**: JetBrains Mono, Fira Code

### 접근성
- WCAG AA/AAA 색상 대비 준수
- Keyboard Navigation 지원
- Screen Reader 최적화
- `prefers-reduced-motion` 대응

---

## 🔧 수정하기

### HTML 수정
```bash
# 에디터로 열기
code portfolio/keepiluv-agent-portfolio.html

# 또는 vim
vim portfolio/keepiluv-agent-portfolio.html
```

### 이미지 교체
1. 새 이미지를 `portfolio/` 디렉토리에 추가
2. HTML에서 `<img src="파일명.png">` 부분 수정
3. 브라우저에서 새로고침하여 확인

### SEO 메타태그 수정
HTML `<head>` 섹션에서 다음 항목 수정:
- `<meta property="og:title">` - 공유 시 제목
- `<meta property="og:description">` - 공유 시 설명
- `<meta property="og:image">` - 공유 시 썸네일 (설정 필요)

---

## 📊 성과 수치 업데이트

HTML 파일의 Stats 섹션에서 `data-target` 값을 수정:

```html
<span class="stat-number" data-target="12">0</span>  <!-- Agent 수 -->
<span class="stat-number" data-target="60">0</span>  <!-- 도메인 용어 -->
<span class="stat-number" data-target="16">0</span>  <!-- Wiki 문서 -->
<span class="stat-number" data-target="8">0</span>   <!-- Skill 수 -->
```

---

## 🔗 관련 링크

- **[프로젝트 메인 README](../README.md)** - 프로젝트 전체 소개
- **[Wiki 홈](../wiki/README.md)** - 지식 베이스
- **[CLAUDE.md](../CLAUDE.md)** - AI Agent 작업 가이드

---

**제작**: AI Agent와 사람의 협업 🤖🤝👨‍💻

**최종 업데이트**: 2026-06-16
