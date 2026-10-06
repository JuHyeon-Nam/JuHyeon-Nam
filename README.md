# 남주현 | Juhyeon Nam

**Manufacturing AI · Equipment Diagnostics · Robot Automation**

제조 설비와 가공 공정을 이해하고, 센서 데이터를 분석해 진단 모델과 운영 화면으로 연결합니다.
정밀부품 제조와 자동화설비 셋업을 경험했으며, 현재 인하대학교에서 소프트웨어융합공학을 전공하고 한국생산기술연구원에서 현장실습을 진행하고 있습니다.

[Email](mailto:yur3847@naver.com) · [GitHub](https://github.com/JuHyeon-Nam) · [대표 프로젝트](#대표-프로젝트) · [기술 역량](#기술-역량) · [경력·현장실습](#관련-경력과-현장실습) · [학력·교육](#학력과-교육) · [자격·어학](#자격과-어학)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![ROS 2](https://img.shields.io/badge/ROS_2-22314E?style=flat-square&logo=ros&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

| 현재 | 주요 성취 |
|---|---|
| 인하대학교 소프트웨어융합공학 · **2027.02 졸업예정** | 누적 **3.91/4.50** · 전공 **4.00/4.50** |
| KITECH 현장실습 · 로봇 가공·공정 모니터링 | SSAFY AI Challenge **193개 팀 중 1위** · 팀 성과 |

## 대표 프로젝트

| 프로젝트 | 주요 작업·결과 |
|---|---|
| [로봇 상태진단](https://github.com/JuHyeon-Nam/ServiceRobot_AI) | 249개 센서 특징 · 9개 상태 분류 · 3D 관제·정비 이력 |
| [반도체 불량탐지](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection) | 불량 Recall 0.7619 · 검증셋 임계값 선택 · 미탐·오탐 분석 |
| [웨이퍼 분석](https://github.com/JuHyeon-Nam/wafer-ai-analyst) | 4종 소자·74개 측정 · 파일 파싱·특징 추출·대시보드 |
| [재활용품 VQA](https://github.com/JuHyeon-Nam/Recycle_VQA_Challenge) | 193개 팀 중 1위 · 모델 예측 비교·오답 유형 분석 |

### 01. ServiceRobot_AI

**센서 특징 추출부터 고장 분류, 3D 관제와 정비 이력까지 연결한 상태진단 시스템**

[![ServiceRobot_AI 통합 3D 관제 화면](https://raw.githubusercontent.com/JuHyeon-Nam/ServiceRobot_AI/main/assets/twin_workspace.png)](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4)

`Python` `LightGBM` `FastAPI` `WebSocket` `Three.js` `SQLite` `MQTT`

- **문제:** 센서의 순간 변동과 지속 이상을 구분하고, 분류 결과를 작업자가 확인할 수 있는 상태·정비 정보로 전달해야 했습니다.
- **구현:** 30시점 센서 구간에서 통계·변화량·rFFT 등 **249개 특징**을 구성하고 정상 및 8개 고장을 분류했습니다. 학습·추론의 특징 생성을 공통 런타임으로 연결했습니다.
- **시스템:** 자산 선택, 상태·추론 결과 조회, 정비 작업 상태 변경, SQLite 이력 저장과 리포트 흐름을 구현했습니다. 좌표는 시각화에 사용하고 모델 입력에서는 제외했습니다.
- **평가:** AI-Hub 공식 Validation 분할에서 **Accuracy 93.29% / Macro-F1 0.5838**. 정상만 예측하는 기준선의 Accuracy는 약 83%입니다.
- **범위:** 기본 시연은 공개 데이터·리플레이·합성 입력 기반입니다. 가상 FAB 화면과 규칙 기반 위험 점수를 실제 공장 운영 성과나 검증된 미래 고장 확률로 해석하지 않습니다.

[코드·실행 방법](https://github.com/JuHyeon-Nam/ServiceRobot_AI) · [38초 시연](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4) · [모델 카드](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/docs/MODEL_CARD.md) · [구현 설명](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/docs/PORTFOLIO_WALKTHROUGH.md)

### 02. Semiconductor Manufacturing Fault Detection

**불량 미탐과 오탐에 따른 검토 부담을 함께 다룬 제조 센서 분석 프로젝트**

`Python` `pandas` `NumPy` `scikit-learn` `ExtraTrees` `matplotlib`

- **문제:** SECOM 데이터는 1,567개 표본 중 불량이 104개입니다. 전부 정상으로 예측해도 Accuracy가 93.31%여서 정확도만으로 불량 탐지 성능을 판단할 수 없습니다.
- **분석:** 590개 센서의 결측·저분산·상관 구조를 점검하고, 지도학습 모델과 정상 데이터 기반 이상탐지 기준선을 비교했습니다.
- **검증:** 학습·검증·테스트를 분리하고, 임계값은 검증셋에서 선택했습니다. 최종 테스트에서는 불량 Recall·Precision·F2·PR-AUC와 미탐·오탐 수를 함께 기록했습니다.
- **결과:** ExtraTrees, 임계값 0.10에서 **불량 21건 중 16건 탐지**. Recall **0.7619**, Precision **0.1951**, F2 **0.4819**이며 미탐 5건·오탐 66건입니다.
- **판단:** 모델 점수는 엔지니어의 검토 우선순위를 정하는 신호입니다. 익명 센서의 중요도를 물리적 고장 원인으로 단정하거나 양산 검증 성과로 표현하지 않습니다.

[코드·분석 리포트](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection) · [모델 카드](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection/blob/main/reports/model_card.md) · [임계값 비교](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection/blob/main/reports/figures/threshold_tradeoff.png)

<details>
<summary>분석 결과 대시보드</summary>

![SECOM 분석 결과 대시보드](https://raw.githubusercontent.com/JuHyeon-Nam/semiconductor-process-fault-detection/main/reports/figures/result_dashboard.png)

</details>

### 03. Wafer AI Analyst

**전기 측정 파일 파싱부터 소자별 특징 추출과 이상 후보 검토까지 연결한 분석 도구**

`Python` `pandas` `RandomForest` `Streamlit` `Plotly`

- **대상:** diode·resistor·capacitor·NMOS의 CSV·Excel 측정 데이터. **74개 측정, 10,294개 곡선 포인트, 4종 소자**를 분석했습니다.
- **본인 역할:** 파서, 데이터 정규화, ML 분석 흐름과 대시보드 통합을 담당했습니다. 팀원들과 소자 특징·측정 이슈 해석·결과 검토를 협업했습니다.
- **구현:** `measurement → curve → feature` 구조로 정리하고, 규칙 기반 검토와 RandomForest 분류 결과를 곡선·특징·리포트에 연결했습니다.
- **평가 범위:** 실제 특징 분포에서 만든 **9개 합성 결함 시나리오**의 테스트 Accuracy는 **0.9722**, Macro-F1은 **0.9718**입니다. 실제 불량 라벨이나 양산 원인 규명 성능을 검증한 결과는 아닙니다.

[코드·실행 방법](https://github.com/JuHyeon-Nam/wafer-ai-analyst) · [대시보드 화면](https://github.com/JuHyeon-Nam/wafer-ai-analyst/blob/main/docs/assets/dashboard_summary.png)

<details>
<summary>웨이퍼 분석 화면</summary>

![Wafer AI Analyst 분석 화면](https://raw.githubusercontent.com/JuHyeon-Nam/wafer-ai-analyst/main/docs/assets/dashboard_summary.png)

</details>

### 04. Recycle VQA Challenge

**재활용품 이미지와 질문을 함께 해석하는 VQA 과제 · 5인 팀**

`Qwen` `InternVL` `Prediction Comparison` `Error Analysis`

- **팀 성과:** SSAFY AI Challenge **최우수상 / 193개 팀 중 1위**. Private Score **0.97635**, Public Score **0.96452**.
- **본인 역할:** Qwen·InternVL 예측 로그를 비교하고, 개수·위치·재질·분리배출 질문별 오답 패턴을 분석했습니다. 결과를 팀에 공유하고 취약 유형·낮은 신뢰도 문항의 재추론 기준 수립에 기여했습니다.
- **팀 구현:** 선택적 재추론과 객체 재탐색을 결합한 최종 파이프라인입니다. 모델 학습·객체 탐지·전체 통합은 팀 성과이며, 본인의 비교 실험·오답 분석과 구분합니다.

[코드·팀 역할](https://github.com/JuHyeon-Nam/Recycle_VQA_Challenge)

<details>
<summary>추가 프로젝트 · 서비스 흐름과 응답 검증</summary>

### HEOGAON | AI 인허가 사전진단

[저장소](https://github.com/JuHyeon-Nam/HEOGAON) · [시연 영상](https://youtu.be/qiv1yjfYUZQ)

- **팀 성과:** SSAFY × 카카오테크 부트캠프 AI 해커톤에서 **103개 팀 중 본선 6개 팀**에 선발.
- **본인 역할:** 사용자 시나리오 설계와 AI 응답 검증. 필수정보 누락 시 추가 질문으로 전환되는 흐름, 서류·담당 부서·근거 연결, 외부 연결 실패 시 폴백을 검토했습니다.
- **검증:** 카페 창업 등 10개 대표 시나리오를 반복 실행했습니다. 전체 업종·지역의 정확도나 행정기관의 최종 허가를 보장하는 범위는 아닙니다.
- **팀 기술:** FastAPI·Next.js·SQLite·지식그래프. 그래프 구축과 전체 백엔드 구현을 개인 기여로 주장하지 않습니다.

### CARCH | 카드 소비 코치

- **팀 성과:** SSAFY 1학기 프로젝트 **우수상 / 서울 3반 2위**.
- **본인 역할:** Vue 3 기반 카드 메인·소비계획·분석·AI 채팅 UI/UX 구현. 보유 카드 사용 추천과 신규 발급 추천을 구분하고 추천 근거를 화면에 연결했습니다.
- **협업:** 서비스 기획, 테스트와 발표 시나리오 정리에 참여했습니다.

</details>

## 기술 역량

기술은 실제 적용한 프로젝트와 역할을 기준으로 정리했습니다.

| 영역 | 적용 기술 | 사용 범위 |
|---|---|---|
| 데이터·모델 | Python, pandas, NumPy, scikit-learn, LightGBM, ExtraTrees, RandomForest | 센서 전처리·시계열 특징·불균형 평가·임계값 분석 |
| API·저장·연결 | FastAPI, Pydantic, REST API, WebSocket, SQLite, MQTT | 추론 API·상태 전달·정비 이력·텔레메트리 연동 구성 |
| 화면·시각화 | JavaScript, Three.js, Streamlit, Plotly, Vue 3 | 3D 관제·분석 화면·서비스 UI |
| 개발·검증 | Git, GitHub, Docker, Linux, pytest, GitHub Actions, Playwright | 환경 구성·자동 테스트·API/브라우저 검증 구성 |
| 로봇 환경 | ROS 2 Humble, MoveIt 2, RViz2, UR ROS 2 Driver | UR30 가상 계획·실행 환경, 실물 상태 조회·표시 연동 준비 |
| 제조·자동화 | 도면, AutoCAD, Inventor, 선반·밀링·금형, PLC 센서 I/O·인터록 | 제조 현장 작업·설비 셋업·시운전·점검 지원 |

**학업·교육 기반:** C/C++ 기초, SQL, Django·DRF. VQA의 Qwen·InternVL은 비교·분석 역할이며, 팀의 전체 학습 파이프라인 개발과 구분합니다.

## 관련 경력과 현장실습

### 한국생산기술연구원 | 현장실습

**2026.07–현재 · 2026.12 종료 예정**

- 로봇 드릴링·밀링 실험 세팅, 가공 조건·측정 데이터 정리와 홀 형상·표면 상태 비교를 지원하고 있습니다.
- UR30 개발·운용 환경을 구성하며 Docker·ROS 2 기반 가상 계획/실행과 실물 관절 상태 조회·3D 표시 연동을 진행했습니다.
- 현재 관심은 로봇 가공에서 힘·진동·음향 등 센서 신호를 가공 상태와 품질 지표에 연결하는 것입니다.
- **진행 범위:** PC 명령에 의한 실물 이동, 실제 카메라 좌표 보정과 접촉 제어의 완료를 주장하지 않습니다. 현장실습과 석사 재학·학위 취득은 별개의 상태입니다.

### 카일코리아 | 자동화설비 지원

**2023.06–2024.03 · 관련 자동화 업무 기간**

- 자동화설비 설치·셋업·시운전과 유지보수를 지원했습니다.
- 도면·I/O 리스트와 센서 접점·배선·통신 상태를 대조하고, PLC 시퀀스의 동작 순서와 인터록 조건을 점검했습니다.
- 제어 신호와 실제 동작을 비교해 정지·오동작 구간을 좁히고, 조치 후 반복 운전으로 재발 여부를 확인했습니다.

### HRS코리아 | 정밀부품 제조

**2020.01–2021.01**

- 정밀 커넥터의 프레스·사출·조립·검사 공정을 경험했습니다.
- 설비·금형 점검과 세팅을 지원하고, 현미경·측정 도구로 버·변형·형상·치수 편차를 확인했습니다.
- 품질 이상을 검사 결과만으로 보지 않고 금형·소재·설비 조건과 함께 확인하는 기초를 쌓았습니다.

## 학력과 교육

| 기관 | 기간·상태 | 전공·내용 |
|---|---|---|
| **인하대학교** | 2025.03–2027.02 예정 · 편입·재학 | 소프트웨어융합공학 · 누적 **3.91/4.50**, 전공 **4.00/4.50** |
| 국립금오공과대학교 | 2024.03–2025.02 · 이후 인하대 편입 | 전자공학부 반도체시스템전공 교과 이수 |
| 국가평생교육진흥원 학점은행제 | **2024.02 학위 취득** | 경영학사 |
| 수원하이텍고등학교 | 2017.03–2020.01 · 졸업 | 정밀기계과 · 마이스터고 |

인하대 성적은 2026학년도 1학기까지의 확정 성적입니다. 해당 학기 평점 **4.33/4.50**, 우등생으로 기록됐습니다.

| 교육 | 기간 | 내용 |
|---|---|---|
| **SSAFY 15기 AI 트랙 · 1학기 수료** | 2026.01–2026.06 · **925시간** | Python·알고리즘·DB·웹·AI 이론과 프로젝트 |
| KAIT AI반도체 활용·응용 교육 | 2026.05 · 12시간 | AI반도체 활용·응용 |
| Google AI Professional Certificate | 2026.08 수료 | Google·Coursera 온라인 전문 교육 · 학위·국가자격과 구분 |

## 수상과 성취

| 시기 | 성취 | 구분 |
|---|---|---|
| 2026 | SSAFY AI Challenge **최우수상 · 193개 팀 중 1위** | VQA 팀 성과 |
| 2026.06 | SSAFY 1학기 프로젝트 **우수상 · 서울 3반 2위** | CARCH 팀 성과 |
| 2026 | SSAFY × 카카오테크 부트캠프 AI 해커톤 **본선 6개 팀 선발 / 103개 팀** | HEOGAON 팀 성과 · 수상과 구분 |
| 2026-1 | 인하대학교 **우등생 · 학기 평점 4.33/4.50** | 개인 학업 성취 |

## 자격과 어학

| 분야 | 자격 | 취득 |
|---|---|---|
| 데이터 | **데이터분석 준전문가(ADsP)** · 국가공인 | 2025.11 |
| 품질·개선 | **6시그마 Green Belt 프로젝트** · H&C직무인증원 등록민간자격 | 2026.08 |
| 가공·금형 | **금형기능사** | 2019.07 |
| 가공·금형 | **컴퓨터응용선반기능사 · 컴퓨터응용밀링기능사** | 2019.04 |
| 설비 | 승강기기능사 | 2017.12 |
| 정보처리 | 정보처리기능사 · 취득 당시 명칭 | 2016.09 |

<details>
<summary>기타 자격·취득 이력</summary>

| 자격·시험 | 등급·결과 | 취득 |
|---|---|---|
| 컴퓨터활용능력 | 2급 | 2016.08 |
| 워드프로세서 | 단일등급 | 2019.09 |
| 텔레마케팅관리사 | 국가기술자격 | 2023.11 |
| e-Test Professionals | 워드 1급 · 생활기록부 기준 | 2017.12 |
| 매경TEST | 우수 · 과거 취득 이력 | 2023.03 |

</details>

| 어학 | 성적 | 응시 |
|---|---|---|
| **TOEIC Speaking** | **IH · 140/200** | **2026.09.06** |
| OPIc | IM2 | 2026.03.15 |

---

**Contact** · [yur3847@naver.com](mailto:yur3847@naver.com) · [github.com/JuHyeon-Nam](https://github.com/JuHyeon-Nam)

<sub>Updated: 2026.10.07 · 프로젝트별 평가 조건과 개인·팀 기여는 각 저장소에 구분해 기록했습니다.</sub>
