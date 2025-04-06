# Chrome Extension Side panel Boilerplate

## 🧰 기술 스택 및 주요 라이브러리 소개

이 프로젝트는 **Chrome Extension Side Panel**을 위한 모던 프론트엔드 보일러플레이트입니다. 다음과 같은 주요 기술과 라이브러리를 활용하여 개발되었습니다:

## 📁 프로젝트 구조 안내

이 프로젝트는 React 기반으로 구성된 보일러플레이트이며, 컴포넌트의 명확한 분리와 재사용성을 고려한 구조로 설계되어 있습니다. 아래는 주요 폴더 및 그 역할에 대한 설명입니다.

```
├─components
│  ├─common
│  │  ├─footer             // 공통 푸터 컴포넌트
│  │  ├─header             // 공통 헤더 컴포넌트
│  │  └─layout             // 페이지 레이아웃 관련 컴포넌트
│  ├─error
│  │  └─errorFallback      // 에러 바운더리에서 사용할 에러 UI
│  └─ui
│      └─button            // 프로젝트 전역에서 사용할 커스텀 버튼 컴포넌트
├─helpers
│  └─cn                   // 클래스 네임 유틸리티 (ex: classNames, clsx 등)
├─pages
│  ├─home                 // 홈 페이지
│  └─login                // 로그인 페이지
└─providers
    ├─chrome              // 크롬 환경 관련 provider (ex: 확장 프로그램 연동 등)
    ├─overlay             // 오버레이 상태 관리 provider
    ├─react-query         // React Query 설정 및 context provider
    └─theme               // 다크/라이트 테마 관련 context provider
```

## 📌 주요 특징

- **컴포넌트 분리**: `common`, `error`, `ui`로 나누어 재사용성과 유지보수성을 높였습니다.
- **Provider 관리**: 외부 라이브러리와 전역 상태들을 `providers` 폴더에서 통합 관리합니다.
- **페이지 중심 구조**: `pages` 폴더를 통해 각 화면 단위의 컴포넌트를 구분합니다.
- **유틸리티 헬퍼**: 클래스 네임을 효율적으로 처리하기 위한 헬퍼 함수 포함.

## 🚀 사용 목적

이 보일러플레이트는 빠르게 확장 가능한 프론트엔드 프로젝트의 기반을 제공하며, 팀 단위 협업에서도 명확한 역할 분담이 가능하도록 구조화되어 있습니다.


### ⚛️ React & 관련 라이브러리

| 패키지 | 설명 |
|--------|------|
| **react**, **react-dom** | UI 개발의 핵심 프레임워크. 컴포넌트 기반 구조를 통해 재사용성과 유지보수성을 높입니다. |
| **react-router-dom** | SPA(Single Page Application)를 위한 라우팅 라이브러리. 버전 7 사용. |
| **react-hook-form** | 가볍고 직관적인 폼 관리 라이브러리. |
| **react-error-boundary** | 오류 발생 시 fallback UI를 제공하는 라이브러리. |
| **@tanstack/react-query** | 서버 상태 관리 라이브러리. 비동기 데이터 캐싱 및 fetching을 효율적으로 관리. |
| **@tanstack/react-query-devtools** | React Query 개발자 도구. |

---

### 🎨 스타일링 및 UI

| 패키지 | 설명 |
|--------|------|
| **tailwindcss** | 유틸리티 기반 CSS 프레임워크. 빠른 스타일링을 가능하게 합니다. |
| **tailwind-merge** | Tailwind 클래스 병합 시 충돌 방지 및 최적화를 위한 유틸리티. |
| **clsx**, **class-variance-authority** | 조건부 클래스명을 쉽게 조합할 수 있도록 도와주는 유틸리티. |
| **styled-components** | CSS-in-JS 방식의 스타일링을 위한 라이브러리. 필요에 따라 Tailwind와 함께 사용 가능. |
| **lucide-react** | 아이콘 컴포넌트 라이브러리. 가볍고 커스터마이징이 쉬운 SVG 아이콘을 제공합니다. |
| **@toss/use-overlay** | 오버레이(모달, 팝업 등)를 위한 React Hook 라이브러리. |

---

### 🌐 API 통신 및 유틸리티

| 패키지 | 설명 |
|--------|------|
| **axios** | Promise 기반 HTTP 클라이언트. REST API와의 통신을 단순화합니다. |
| **qs** | 쿼리 문자열 파싱과 직렬화를 도와주는 유틸리티. |
| **nanoid** | 짧고 충돌 없는 고유 ID 생성기. |
| **eventemitter3** | 컴포넌트 간 이벤트 기반 통신을 위한 lightweight 이벤트 emitter. |
| **dotenv** | `.env` 파일을 통해 환경 변수를 로딩합니다. 크롬 익스텐션에서도 활용 가능. |

---

### 🛠️ 개발 환경 및 빌드 도구

| 패키지 | 설명 |
|--------|------|
| **webpack**, **webpack-cli**, **webpack-dev-server** | 모듈 번들러. 개발 및 프로덕션 빌드를 담당합니다. |
| **html-webpack-plugin** | HTML 템플릿을 자동으로 생성하고 스크립트를 주입합니다. |
| **ts-loader** | TypeScript 파일을 webpack과 함께 사용할 수 있도록 합니다. |
| **rimraf** | Unix 기반의 `rm -rf` 명령어와 유사한 cross-platform 디렉토리 삭제 도구. |
| **copy-webpack-plugin** | 정적 파일을 dist 폴더로 복사. |
| **terser-webpack-plugin** | 프로덕션 빌드 시 JavaScript 압축 및 최적화. |
| **postcss**, **postcss-loader**, **autoprefixer** | Tailwind와 함께 사용되는 CSS 전처리기. 자동 벤더 프리픽스 추가. |
| **style-loader**, **css-loader** | CSS를 JS 번들에 포함시키기 위한 로더. |

---

### 📐 타입스크립트 및 타입 관리

| 패키지 | 설명 |
|--------|------|
| **typescript** | 정적 타입을 부여하여 코드 안정성을 확보합니다. |
| **@types/\*** | TypeScript를 위한 타입 정의 패키지. |
| **@types/chrome** | 크롬 익스텐션 개발 시 필요한 chrome API 타입 정의. |

---

### 🔍 코드 품질 및 린팅

| 패키지 | 설명 |
|--------|------|
| **eslint**, **prettier** | 코드 스타일 및 포맷팅을 자동으로 관리. |
| **eslint-config-airbnb**, **eslint-config-airbnb-typescript** | Airbnb의 스타일 가이드를 기반으로 한 린팅 설정. |
| **eslint-plugin-react**, **eslint-plugin-react-hooks** | React 프로젝트 전용 린팅 플러그인. |
| **eslint-plugin-jsx-a11y** | JSX 접근성 체크를 위한 플러그인. |
| **eslint-plugin-simple-import-sort** | import 정렬을 자동화. |
| **eslint-plugin-unused-imports** | 사용하지 않는 import를 자동 제거. |
| **eslint-config-prettier**, **eslint-plugin-prettier** | Prettier와 ESLint의 충돌 방지 및 통합. |

---

### ✅ 기타 도구

| 패키지 | 설명 |
|--------|------|
| **lint-staged** | Git 커밋 시 변경된 파일에만 lint를 적용합니다. |
| **patch-package** | node_modules의 특정 패키지를 직접 수정하고 패치 저장. |
| **postinstall-postinstall** | 일부 환경에서 postinstall 스크립트 실행을 보장. |
| **@svgr/webpack** | SVG를 React 컴포넌트로 쉽게 변환해주는 로더. |
| **file-loader** | 정적 파일을 처리하는 webpack 로더. |

---


좋아요! 아래는 **TSLint**와 **ESLint**의 주요 차이점과 핵심 내용들, 그리고 **Prettier와의 연동** 포인트까지 한글로 정리한 문서용 요약입니다. `README.md`에 넣기 적합하게 마크다운 형식으로 정리해드릴게요.

---

## 🔧 코드 린팅 및 포맷팅 설정 요약

이 프로젝트는 **ESLint + TypeScript + Prettier** 조합으로 린팅과 포맷팅을 설정하고 있습니다. 아래에 각 도구들의 핵심 내용과 역할, 그리고 연동 방식에 대해 설명합니다.

---

### ✅ ESLint

> ESLint는 코드 품질과 스타일을 **정적 분석**하는 도구입니다.

#### 📌 주요 역할
- 코드에서 **버그 가능성** 탐지
- **코드 일관성** 유지
- **팀 개발에서 공통 코드 스타일** 강제

#### 📦 주요 플러그인 및 설정
- `eslint-config-airbnb`: Airbnb의 코드 스타일 가이드 적용
- `eslint-config-next`: Next.js 전용 린트 규칙
- `eslint-plugin-prettier`: Prettier와 ESLint 통합
- `eslint-plugin-simple-import-sort`: import 정렬 자동화
- `eslint-plugin-unused-imports`: 사용되지 않는 import 제거
- `@typescript-eslint`: TypeScript 지원을 위한 ESLint 플러그인

#### 🔍 주요 규칙 설명
- `@typescript-eslint/no-unused-vars`: 미사용 변수 경고 (단, `_`로 시작하는 경우는 허용)
- `@typescript-eslint/explicit-function-return-type`: 함수의 반환 타입 명시 요구
- `simple-import-sort/imports`: import 순서 자동 정렬
- `unused-imports/no-unused-imports`: 사용하지 않는 import 제거
- `no-param-reassign`: 함수 파라미터 직접 수정 방지
- `react-hooks/rules-of-hooks`: React Hooks 규칙 강제
- `jsx-a11y/label-has-associated-control`: 접근성(a11y) 관련 라벨 규칙

---

### 🧹 Prettier

> Prettier는 **코드 스타일 포맷터**로, 코드 형식을 자동으로 정리해주는 역할을 합니다.

#### 📌 ESLint와의 연동 포인트
- `plugin:prettier/recommended`: ESLint 설정에서 Prettier를 **마지막에 확장**하여 스타일 충돌 방지
- `prettier/prettier` 룰 사용: ESLint에서 Prettier 오류를 린트 에러로 인식하게 함
  ```jsonc
  "prettier/prettier": [
    "error",
    { "singleQuote": true, "endOfLine": "auto" }
  ]
  ```
- `@typescript-eslint/comma-dangle` 등 **Prettier와 충돌 가능한 룰은 끄거나 조정**함

#### 💡 역할 분담
| 역할            | ESLint                          | Prettier                    |
|----------------|----------------------------------|-----------------------------|
| 문법 검사       | ✅                               | ❌                          |
| 코드 포맷       | 일부 가능 (비효율적)             | ✅                          |
| 버그/오류 탐지 | ✅ (정적 분석 기반)              | ❌                          |
| 타입 검사       | ✅ (TypeScript 플러그인 필요)     | ❌                          |

---

### 📁 디렉토리 및 파일 적용 범위

#### ✅ 포함(`include`)
- `**/*.ts`, `**/*.tsx`, `types/*.d.ts`, `next-env.d.ts`

#### 🚫 제외(`exclude`)
- `node_modules`, `out`, `cypress`, `next.config.js`, `commitlint.config.js`

---

### 🔍 참고 규칙: 자동 무시되는 변수
```ts
// 다음과 같은 변수는 린트 에러가 발생하지 않음
const _unused = 1;
function handler(_event: Event) {}
```

---

### 📚 기타 참고 사항

- `react/react-in-jsx-scope`: React 17 이상에서는 JSX 사용 시 import 불필요하므로 비활성화
- `_app.tsx` 등에서의 props 스프레드 허용을 위해 `react/jsx-props-no-spreading` 비활성화
- `@next/next/no-img-element`: Next.js `next/image` 미사용 시 끄는 것이 일반적















## 실행 및 빌드 방법

> `Manifest v3`: Chrome의 최신 확장 프로그램 아키텍처를 기반으로 제작되었습니다.

더 많은 정보는 [developer.chrome.com](https://developer.chrome.com/docs/extensions)에서 확인할 수 있습니다.

팝업 확장 보일러플레이트는 [github.com/Mineru98/Chrome-Extension-SidePanel-Boilerplate](https://github.com/Mineru98/Chrome-Extension-SidePanel-Boilerplate)에서 확인하세요.

### 설치 방법

1. **레포지토리 클론하기**
    ```bash
    git clone https://github.com/Mineru98/Chrome-Extension-SidePanel-Boilerplate
    cd Chrome-Extension-SidePanel-Boilerplate
    ```
    또는
    ```
    <> Code / Github Desktop으로 열기 / 클론하기 / VS Code에서 열기
    ```

2. **의존성 설치**
    ```bash
    npm install
    ```

3. **웹 서버 시작**
    ```bash
    npm run dev
    ```

4. **확장 프로그램 빌드**
    ```bash
    npm run build
    ```

5. **Chrome에 확장 프로그램 로드하기**
    - Chrome을 열고 `chrome://extensions/`로 이동합니다.
    - 오른쪽 상단의 "**개발자 모드**"를 활성화합니다.
    - "압축 해제된 확장 프로그램 로드"를 클릭하고 프로젝트 디렉토리 내의 `dist` 폴더를 선택합니다.

6. **개발 시작**
    ```bash
    npm run start
    ```
    변경사항이 생기면 확장 프로그램이 자동으로 다시 로드됩니다.

> 문제가 있다면 `issue`에 남겨주시고, 유용하셨다면 *스타*를 눌러주세요!
