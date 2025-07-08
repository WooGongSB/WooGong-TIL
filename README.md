# Today I Learned


## 2025-07-08

### Recommended Folder Structure for a React + TypeScript Project
```
my-project/
├── public/                 # Static files (index.html, favicon, etc.)
├── src/                    # Main source code
│   ├── assets/             # Static resources (images, fonts, styles)
│   │   ├── images/
│   │   ├── icons/
│   │   ├── fonts/
│   │   └── styles/
│   ├── components/         # Reusable UI components
│   │   ├── Button.tsx
│   │   ├── Header.tsx
│   │   └── Footer.tsx
│   ├── pages/              # Page-level components (routing targets)
│   │   ├── Home/
│   │   │   ├── Home.tsx
│   │   │   ├── Home.module.css
│   │   │   └── Home.types.ts
│   │   ├── About/
│   │   └── Contact/
│   ├── store/              # State management (Redux, Zustand, etc.)
│   │   ├── index.ts
│   │   └── slices/
│   │       ├── userSlice.ts
│   │       └── productSlice.ts
│   ├── hooks/              # Custom React hooks
│   │   └── useAuth.ts
│   ├── utils/              # Utility functions
│   │   └── formatDate.ts
│   ├── types/              # Global type definitions
│   │   ├── api/
│   │   ├── models/
│   │   └── common/
│   ├── models/             # Business/domain logic (optional)
│   └── index.tsx           # App entry point
├── tests/                  # Unit/integration tests
├── dist/                   # Build output
├── node_modules/           # Dependencies
├── package.json
├── tsconfig.json
└── README.md
```
React와 TypeScript 프로젝트에서 폴더 구조를 잘 설계하는 것은 유지보수성과 확장성에 매우 중요합니다. 

#### 주요 특징과 이유
- src/: 모든 소스 코드를 한 곳에 모아 관리합니다.
- components/: 여러 페이지에서 재사용하는 UI 컴포넌트를 모아둡니다.
- pages/: 라우팅 단위가 되는 페이지 컴포넌트를 폴더별로 분리해 관리합니다. 각 페이지 내에 컴포넌트, 스타일, 타입 정의를 함께 둬서 모듈화합니다.
- store/: Redux나 Zustand 같은 상태관리 라이브러리 관련 코드를 모아둡니다. 슬라이스별로 세분화해 관리하기 편리합니다.
- hooks/: 커스텀 훅을 별도 폴더로 분리해 재사용성을 높입니다.
- utils/: 날짜 포맷팅, API 호출 함수 등 범용 함수들을 모아둡니다.
- types/: 전역 타입이나 API 응답 타입, 데이터 모델 타입을 체계적으로 관리합니다.
- assets/: 이미지, 아이콘, 폰트, CSS/SCSS 등 정적 리소스를 분리해 관리합니다.
- tests/: 테스트 코드를 별도로 관리해 테스트 유지보수가 쉽도록 합니다.

#### 왜 이렇게 구성할까?
- 확장성: 프로젝트가 커져도 폴더별 역할이 명확해 유지보수가 쉽습니다.
- 모듈화: 페이지별, 기능별로 코드를 분리해 협업에 유리합니다.
- 재사용성: 공통 컴포넌트와 훅을 분리해 중복 코드를 줄입니다.
- 가독성: 타입 정의와 스타일을 컴포넌트나 페이지 폴더 안에 두어 관련 파일을 한눈에 찾기 쉽습니다.

#### 프로젝트의 규모가 작은경우는?
작은 프로젝트라면 src/ 내에 components/, pages/, utils/ 정도만 두고 시작해도 충분합니다. 프로젝트가 커질수록 위 구조처럼 세분화하는 것이 좋습니다.

필요하면 실제 예시 코드와 함께 폴더별 역할, 네이밍 규칙도 알려드릴 수 있습니다. 궁금한 점 있으면 언제든 질문해 주세요!

#### 요약
- .tsx 파일은 React 컴포넌트용, .ts 파일은 일반 TS 코드용
- src/ 폴더 아래에 components/, pages/, store/, hooks/, utils/, types/, assets/ 폴더를 둠
- 각 폴더는 역할별로 코드와 리소스를 분리해 관리
- 확장성과 유지보수를 고려한 구조가 중요

---
## [2025-06](https://github.com/WooGongSB/WooGong-TIL/blob/main/2025/06/README.md)