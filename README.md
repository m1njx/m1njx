<div align="center">

# 강민제 · Minje Kang

**데이터 분석과 ML 모델링을 실제 서비스로 연결하는 개발자입니다.**

모델 성능뿐 아니라 데이터 검증, 재현 가능한 실험, 서비스의 안정성을 함께 고민합니다.<br/>
연암공과대학교 스마트소프트웨어과 재학

[![Email](https://img.shields.io/badge/minje7240@naver.com-03C75A?style=flat-square&logo=naver&logoColor=white)](mailto:minje7240@naver.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/민제-강-88566b3bb/)

</div>

## Projects

### WAGLE BASEBALL · 와글베이스볼

**함께 야구 보고, 함께 기억하는 회원 전용 클럽하우스**

KBO 10개 구단 팬을 위한 직관 일정·참석 응답·기록·디지털 티켓북·사진 갤러리 서비스입니다. 개인별 직관 통계와 시즌 회고, AI 야구 어시스턴트를 제공합니다.

- **공동 위키**: 검색·카테고리·문서 간 링크를 지원하고, 버전 기반 편집과 동시 수정 충돌을 처리합니다. 일반 회원에게 편집자 정보를 노출하지 않으며, 관리자는 이력·차이 비교·되돌리기를 관리합니다.
- **비공개 미디어 파이프라인**: 업로드 승인과 이미지 가공 상태를 분리하고, WebP 미리보기·썸네일을 생성합니다. 권한과 게시 조건을 확인한 뒤 서명 URL로 제공하며, 가공 실패 시 원본을 보존하고 재시도할 수 있습니다.
- **인증과 접근 제어**: 비밀번호·WebAuthn 패스키, 역할 기반 권한, PostgreSQL RLS와 Redis 기반 요청 제한을 적용했습니다.

`Next.js` `React` `TypeScript` `Tailwind CSS` `Supabase` `PostgreSQL` `NAVER Cloud Object Storage` `Redis` `WebAuthn` `Playwright`

[서비스](https://waglebaseball.vercel.app) · [저장소 · 비공개](https://github.com/m1njx/our-baseball)<br/>
<sub>서비스 콘텐츠는 회원 인증과 접근 권한이 필요합니다.</sub>

### 나만의 AI 지식 창고

**개인 문서와 수집 정보를 근거로 답하는 RAG 챗봇**

뉴스·검색 결과·PDF·TXT를 다국어 임베딩과 FAISS 검색으로 연결합니다. React와 FastAPI를 분리하고, Streamlit UI에서도 공통 코어를 사용합니다.

- **출처와 최신성**: 답변에 사용한 문서의 출처를 표시하고, 현재 시점의 정보를 묻는 질문에는 오래된 자료를 검색 결과에서 제외합니다. 최근 대화 문맥을 검색과 답변에 반영합니다.
- **지식 관리와 복구**: 문서 업로드·삭제와 배치 임베딩을 지원합니다. 인덱스·문서·메타데이터를 세대 단위로 검증하고 활성 포인터를 원자적으로 전환하며, 손상 시 유효한 세대를 복구합니다.
- **응답과 안정성**: SSE 스트리밍, Gemini → LM Studio → OpenAI 폴백, HMAC 서명 세션, 저장소 잠금, 프롬프트 인젝션 완화와 출력 필터링을 적용했습니다. 제공자 전환은 첫 응답 조각을 보내기 전에 수행합니다.

`Python` `FastAPI` `React` `Vite` `FAISS` `Sentence-Transformers` `Gemini API` `OpenAI API` `LM Studio`

[저장소](https://github.com/m1njx/ai_chat_bot)

## Data & ML

### LG Aimers 9기 · 투구 제구 성공 확률 예측

**5인 팀에서 예측 파이프라인 한 축과 실험·검증 체계 담당**

147만 행의 투구 데이터로 제구 성공 확률을 예측했습니다. LightGBM·XGBoost·CatBoost와 PyTorch MLP를 결합한 **25모델 앙상블**을 구성했습니다.

- **피처와 성능**: as-of 누적 피처 분해로 Public LB **+146.8**을 기록했습니다. 본인 최고 전체 제출 점수는 **1,114.74**, 담당 파이프라인 단독 점수는 **1,032.14**입니다.
- **검증과 재사용**: 시계열 CV·확률 보정·행 독립성 감사를 수행하고, 제출물 검사·행 독립성 검사·블렌드 계산 도구 3종을 분리했습니다.
- **실험 기록**: 채택 31종·기각 17종·보류 4종, 총 **52종 기법**을 코드와 판정 근거로 남겼습니다.

`Python` `Pandas` `NumPy` `SciPy` `scikit-learn` `LightGBM` `XGBoost` `CatBoost` `PyTorch`

[저장소 · 본인 기여 범위](https://github.com/m1njx/aimers-pitch-control)

### 코로나19 초과사망 다차원 분석

**국가데이터 활용대회 · 분석에서 대시보드와 정책 보고서까지**

통계청 MDIS 사망원인통계(2016~2024년, 집계 후 약 123만 행)를 분석하고 고령층 보호를 위한 3단계 정책을 제안했습니다.

- **분석**: 2017~2019년 동월 평균을 기준선으로 2020~2024년 누적 초과사망 **241,923명**을 산출했습니다. 성별·연령·지역별 분석, OLS 회귀와 민감도 분석을 수행했습니다.
- **재현성**: 분석 스크립트·웹 대시보드·PDF 보고서가 동일한 분석 함수를 사용하도록 구성했습니다. 원자료는 공개 저장소에서 제외하고 합성 데이터 기반 테스트와 CI를 마련했습니다.
- **한계 기록**: 확진자 추정 구간, 잔차 자기상관과 정규성 진단, 연령표준화 미적용을 문서에 명시했습니다.

`Python` `Pandas` `SciPy` `statsmodels` `Matplotlib` `ReportLab` `FastAPI` `React`

[저장소](https://github.com/m1njx/public-data)

### 대구 소상공인 AI 상권·창업 입지 추천

**2026 AI Blockchain Challenge in Daegu · 팀 말괄량이코물이**

공공데이터 7종을 통합해 대구 **150개 행정동·118,357개 점포**의 공간 피처를 구축했습니다. 업종과 타깃 고객층에 따라 지역 간 상대적 입지 적합도를 비교하는 **MCDM 추천 서비스**입니다.

- **추천 엔진**: 수요·타깃인구·경쟁·교통·주차·업종밀집도 6개 지표를 평가합니다. 도시철도 94개 역과 버스 3,981개 정류소를 결합해 대중교통 접근성을 계산합니다.
- **설명과 탐색**: 관측·집계 수치에 근거한 추천 사유, Top 5 GIS 지도, 행정동 상세 분석과 CSV 내보내기를 제공합니다.
- **검증**: 저장소에 17개 스위트 **213개 회귀 테스트 통과 기록**을 남겼습니다. 점수는 지역 간 비교 지표이며 실제 매출이나 창업 성공 확률을 예측하지 않습니다.

`Python` `Pandas` `NumPy` `SciPy` `PyArrow` `GeoPandas` `Shapely` `PyProj` `Folium` `Streamlit`

[저장소](https://github.com/m1njx/daegu-commercial-ai)

## Tech Stack

| 분야 | 주요 기술 |
|---|---|
| 데이터 분석 · ML | Python, Pandas, NumPy, SciPy, scikit-learn, PyTorch, LightGBM, XGBoost, CatBoost |
| 공간 데이터 | GeoPandas, Shapely, PyProj, PyArrow, Folium |
| AI · 검색 | Gemini API, OpenAI API, LM Studio, FAISS, Sentence-Transformers, RAG |
| 웹 | React, Next.js, TypeScript, Vite, Tailwind CSS, FastAPI, Streamlit |
| 데이터 · 인프라 · 검증 | PostgreSQL, Supabase, Redis, NAVER Cloud Object Storage, Docker, GCP, Vercel, Playwright |

## Activities & Awards

| 기간 | 활동 | 내용 |
|---|---|---|
| 2026.06 ~ 09 | LG Aimers 9기 | DACON 온라인 해커톤 · 투구 제구 성공 확률 예측 |
| 2026.04 ~ 07 | 국가데이터 활용대회 | 코로나19 초과사망 다차원 분석 및 고령층 보호 정책 제안 |
| 2026.05.09 ~ 05.10 | 구름 AI 해커톤 | **UniBoard · 대상** |
| 2026.03 ~ 현재 | 멋쟁이사자처럼 대학 | 웹 개발 및 AI 서비스 개발 활동 |
