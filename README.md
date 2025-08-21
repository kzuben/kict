# KICT 교량유지관리 디지털트윈 웹기반 플랫폼

한국건설기술연구원(KICT)의 교량유지관리 디지털트윈 시스템을 위한 웹 기반 플랫폼입니다.

## 📋 개발자 전달 사항

### dist 파일 전달 시 실행 방법
 `dist` 폴더를 전달받은 후, **VS Code의 Live Server를 사용하여 실행**해주세요.

#### Live Server 실행 방법:
1. **VS Code 설치**: https://code.visualstudio.com/
2. **Live Server 확장 프로그램 설치**: VS Code 확장 마켓플레이스에서 "Live Server" 검색 후 설치
3. **dist 폴더 열기**: VS Code에서 `dist` 폴더를 열기
4. **서버 시작**: `index.html` 우클릭 → "Open with Live Server" 선택
5. **브라우저 접속**: 자동으로 브라우저가 열리며 `http://localhost:5500` (또는 다른 포트)에서 실행

#### 주의사항:
- ❌ `index.html`을 직접 더블클릭하면 CSS가 적용되지 않습니다
- ✅ 반드시 Live Server를 통해 웹 서버로 실행해야 합니다
- ✅ 모든 기능이 정상적으로 작동합니다

## 🌐 크로스브라우징 테스트

### 테스트 완료 브라우저
다음 브라우저에서 정상 작동을 확인했습니다:

#### 데스크톱 브라우저:
- ✅ **Chrome** (최신 버전)
- ✅ **Safari** (최신 버전)
- ✅ **Edge** (최신 버전)
- ✅ **Firefox** (최신 버전)
- ✅ **Opera** (최신 버전)
- ✅ **Naver Whale** (최신 버전)

### 호환성 특징:
- **Safari**: SVG 아이콘 렌더링 최적화 적용
- **Material Icons**: 모든 브라우저에서 정상 표시
- **CSS 애니메이션**: 하드웨어 가속 지원
- **JavaScript 기능**: ES6+ 모듈 시스템 지원

### 미지원 환경:
- ❌ **모바일 환경**: 고려하지 않음
- ❌ **태블릿 환경**: 고려하지 않음
- ❌ **반응형 디자인**: 고정형 레이아웃 (1440px 기준)

### 레이아웃 특성:
- **고정형 디자인**: 1440px 기준으로 설계
- **1440px 이하**: 가로 스크롤로 대응
- **1440px 이상**: 중앙 정렬로 표시

## 🚀 주요 기능

- **노후도 평가**: 교량 상태 평가 및 예측 서비스
- **손상 확산 예측**: 손상 확산 모델링
- **실시간 가시화**: 디지털트윈 기술을 활용한 교량 상태 시각화
- **고정형 디자인**: UI/UX 디자인, 고정 및 1440px 이하 스크롤 대응
- **이미지 최적화**: JPG, SVG 파일 자동 최적화로 빠른 로딩 속도
- **컴포넌트 시스템**: 재사용 가능한 Tailwind CSS 컴포넌트 클래스

## 🛠️ 기술 스택

- **Vite**: 빠른 빌드 도구 및 개발 서버
- **HTML5**: 시맨틱 마크업
- **Tailwind CSS**: 유틸리티 우선 CSS 프레임워크
- **JavaScript**: ES6+ 모듈 시스템
- **AOS**: 스크롤 애니메이션 라이브러리
- **Preline**: UI 컴포넌트 라이브러리
- **vite-plugin-imagemin**: 이미지 최적화 플러그인
  - JPG 최적화 (mozjpeg)
  - SVG 최적화 (svgo)
  - PNG 최적화 (pngquant)

## 📦 설치 및 실행

### 1. 의존성 설치
```bash
npm install
```

### 2. 개발 서버 실행
```bash
npm run dev
```
- 로컬 서버가 `http://localhost:3000`에서 실행됩니다
- Hot Module Replacement (HMR) 지원

### 3. 프로덕션 빌드
```bash
npm run build
```
- `dist/` 폴더에 최적화된 파일들이 생성됩니다
- 이미지 파일들이 자동으로 최적화됩니다 (JPG 35% 압축, SVG 5-23% 압축)
- CSS, JS 파일들이 번들링 및 최소화됩니다

### 4. 빌드 미리보기
```bash
npm run preview
```
- 빌드된 파일을 로컬에서 미리볼 수 있습니다

## 🚀 배포 및 실행

### 로컬에서 실행
```bash
# 개발 서버 실행
npm run dev

# 빌드
npm run build

# 빌드된 파일 미리보기
npm run preview
```

### 다른 PC에서 실행
빌드된 파일을 다른 PC에서 실행하려면 웹 서버가 필요합니다.

#### 방법 1: serve 패키지 사용 (추천)
```bash
# 다른 PC에서 실행
npm run serve
# 브라우저에서 http://localhost:3000 접속
```

#### 방법 2: Python 내장 서버
```bash
cd dist
python -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

#### 방법 3: Node.js http-server
```bash
npx http-server dist -p 8080
# 브라우저에서 http://localhost:8080 접속
```

#### 방법 4: Node.js/Python이 없는 경우 (추천)
**A. Live Server 확장 프로그램 사용 (VS Code)**
1. VS Code 설치
2. Live Server 확장 프로그램 설치
3. `dist` 폴더를 VS Code에서 열기
4. `index.html` 우클릭 → "Open with Live Server"

**B. 간단한 배치 파일 사용**
`dist` 폴더에 `start.bat` 파일 생성:
```batch
@echo off
echo KICT 교량유지관리 시스템 시작 중...
echo 브라우저에서 http://localhost:8080 접속하세요
npx http-server . -p 8080 -o
pause
```

**C. 포터블 웹 서버 사용**
- [XAMPP Portable](https://www.apachefriends.org/download.html) 다운로드
- `dist` 폴더를 `htdocs`에 복사
- Apache 시작 후 `http://localhost` 접속

**D. 브라우저 확장 프로그램 사용**
- Chrome: "Web Server for Chrome" 확장 프로그램
- Firefox: "Simple Web Server" 확장 프로그램

### 주의사항
- `file://` 프로토콜로 직접 열면 일부 기능이 제한될 수 있습니다
- 반드시 웹 서버를 통해 `http://` 프로토콜로 접속하세요

## 📁 프로젝트 구조

```
kict_maintenance/
├── src/
│   ├── css/
│   │   └── input.css          # Tailwind CSS 입력 파일 (컴포넌트 클래스 포함)
│   ├── js/
│   │   └── main.js            # 메인 JavaScript 파일
│   └── assets/
│       └── images/            # 원본 이미지 파일들
├── scripts/
│   └── convert-webp.js        # WebP 변환 스크립트 (선택사항)
├── dist/                      # Vite 빌드 결과물 (자동 생성)
│   ├── index.html             # 메인 HTML 파일
│   ├── viewer.html            # 뷰어 HTML 파일
│   └── assets/
│       ├── css/               # 최적화된 CSS 파일들
│       ├── js/                # 번들된 JavaScript 파일들
│       └── images/            # 최적화된 이미지 파일들
├── index.html                 # 메인 HTML 파일
├── viewer.html                # 뷰어 페이지
├── package.json               # 프로젝트 설정 및 의존성
├── vite.config.js             # Vite 설정 (이미지 최적화 포함)
├── tailwind.config.cjs        # Tailwind CSS 설정
├── postcss.config.cjs         # PostCSS 설정
└── README.md                  # 프로젝트 문서
```

## 🖼️ 이미지 최적화

프로젝트는 `vite-plugin-imagemin`을 사용하여 빌드 시 이미지를 자동으로 최적화합니다:

### 최적화 설정
- **JPG 이미지**: mozjpeg으로 80% 품질, 점진적 로딩 (평균 35% 압축)
- **PNG 이미지**: pngquant로 70-90% 품질 범위 (고품질 유지)
- **SVG 이미지**: svgo로 불필요한 요소 제거 (평균 5-23% 압축)
  - viewBox 유지 (반응형 지원)
  - 접근성 요소 (title, desc) 보존

### 최적화 결과 예시
```
원본 → 최적화 후
bg-main.jpg (838KB) → bg-main-YcmmcZDi.jpg (566KB) [35% 압축]
logo-kict.svg (13KB) → logo-kict-B9IdAmd3.svg (10KB) [23% 압축]
```

## 🎨 커스터마이징

### 색상 테마 변경
`tailwind.config.js`에서 KICT 브랜드 색상을 수정할 수 있습니다:

```javascript
colors: {
  'kict': {
    50: '#f0f9ff',
    100: '#e0f2fe',
    // ... 더 많은 색상
  }
}
```

### 컴포넌트 클래스 사용
`src/css/input.css`에 정의된 컴포넌트 클래스들을 사용할 수 있습니다:

```html
<!-- 버튼 컴포넌트 -->
<button class="btn-primary">주요 버튼</button>
<button class="btn-secondary">보조 버튼</button>

<!-- 모달 컴포넌트 -->
<div class="modal-overlay">
  <div class="modal-container">
    <div class="modal-content">
      <div class="modal-header">...</div>
      <div class="modal-body">...</div>
    </div>
  </div>
</div>

<!-- 피처 카드 컴포넌트 -->
<div class="feature-card">
  <img class="feature-icon" src="...">
  <div class="feature-content">
    <p class="feature-label">라벨</p>
    <h3 class="feature-title">제목</h3>
  </div>
</div>
```

### 스타일 추가
`src/css/input.css`에서 커스텀 스타일을 추가할 수 있습니다:

```css
@layer components {
  .custom-button {
    @apply bg-kict-600 hover:bg-kict-700;
  }
}
```

## 📤 배포

### 개발자에게 전달할 파일들
빌드 후 `dist/` 폴더의 모든 내용을 전달합니다.

```
dist/
├── index.html          # 메인 HTML 파일
├── viewer.html         # 뷰어 HTML 파일
└── assets/
    ├── css/            # 최적화된 CSS
    ├── js/             # 번들된 JavaScript
    └── images/         # 최적화된 이미지 파일들
```

### 웹 서버 배포
1. `dist/` 폴더의 모든 파일을 웹 서버에 업로드
2. `index.html`을 메인 페이지로 설정
3. 정적 파일 서빙 설정
