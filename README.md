# Today I Learned


## 2025-07-18
### Machine Learning 내용 정리
#### 머신러닝
    - 지도학습 [2025-06-27 지도학습 참고](https://github.com/WooGongSB/WooGong-TIL/blob/main/2025/06/README.md)

    - 비지도학습
        - 정답 혹은 레이블이 주어지지 않는 상태에서의 학습방법
        - 비슷한 데이터를 그룹화하거나 데이터의 숨겨진 특징(Feature)을 추출하여 지도학습의 전처리 단계로 사용하기도 함.
        - 정답이 없기 때문에 모델 결과에 대해 분석가가 직접 개입하여 해석해야하는 경우가 많음.

        - 군집화 (Clustering)
            - 데이터를 분류하기 위한 명확한 기준이 존재하지 않은 상태에서 특징이 유사한 데이터끼리 묶어 여러개의 군집(클러스터, 부분 또는 그룹) 으로 나누는 방법
            - 군집의 개수는 분석 목적에 따라 사전에 정의하거나 군집 정도를 나타내는 지표(Dunn Index, Silhouette 등)을 참고하여 정할 수 있음.
            - 군집화의 원래
                - 군집 내 응집도 최대화 : 동일한 군집에 소속된 개체들은 서로 유사할 수록 좋음
                - 군집 간 분리도 최대화 : 상이한 군집에 소속된 개체들은 서로 다를 수록 좋음
        - 차원축소 (Dimentionality Reduction)
            - 입력변수의 갯수가 많다는 말은 해당 공간을 설명하기 위해서는 학습데이터가 많이 필요하다는 것을 의미
            - 불필요한 변수가 포함된다면 모델의 성능에 악영향을 줄수있고 이러한 현상을 차원의 저주 (The Curse of Dimentionality) 라고 한다.
            - 차원의 저주를 완화하는 방법 : 
                - 변수 선택 (Feature Selection) : 일부 변수만 선택하여 학습에 사용
                - 변수 추출 (Feature Extraction) : 변수를 조합하여 새로운 변수로 재구성
            - 차원 축소 방법론 : 
                - PCA (Principal Component Analysis)
                - 다차원 척도법 (Multi-Dimentional Scaliling MDS)
                - LLE (Locally Linear Embedding)
                - t-SNE (t-Stochastic Neighbor Embedding)


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

