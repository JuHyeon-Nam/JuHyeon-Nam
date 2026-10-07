# Manufacturing AI & Robotics

**센서 데이터에서 진단 모델, 작업자가 확인하는 화면까지.**

정밀 제조와 자동화설비 경험을 바탕으로 제조 데이터 분석, 설비 상태진단, 로봇 가공을 다룹니다.
소프트웨어를 전공하며 로봇 가공 연구 현장실습과 데이터·서비스 프로젝트를 이어가고 있습니다.

[프로젝트](#프로젝트) · [기술 역량](#기술-역량) · [제조·자동화 경험](#제조자동화-경험) · [학습과 자격](#학습과-자격)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![ROS 2](https://img.shields.io/badge/ROS_2-22314E?style=flat-square&logo=ros&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## 프로젝트

| 분야 | 프로젝트 |
|---|---|
| 설비 진단·관제 | [ServiceRobot_AI](https://github.com/JuHyeon-Nam/ServiceRobot_AI) · 센서 특징 → 고장 분류 → 3D 관제·정비 이력 |
| 반도체 데이터 | [Fault Detection](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection) · 불량 탐지·임계값·미탐/오탐 분석 |
| 측정 분석 | [Wafer AI Analyst](https://github.com/JuHyeon-Nam/wafer-ai-analyst) · 측정 파일 → 소자 특징 → 이상 후보 검토 |
| 멀티모달 AI | [Recycle VQA](https://github.com/JuHyeon-Nam/Recycle_VQA_Challenge) · 모델 비교·오답 분석·재추론 기준 |
| AI 서비스 검증 | [HEOGAON](https://github.com/JuHyeon-Nam/HEOGAON) · 인허가 사전진단·사용자 시나리오 검증 |
| 서비스 화면 | CARCH · 카드 소비 코치·추천 근거·AI 채팅 UI |

### 01. ServiceRobot_AI

**센서 특징 추출부터 고장 분류, 3D 관제와 정비 이력까지 연결한 상태진단 시스템**

[![ServiceRobot_AI 실제 관제 실행 화면](https://raw.githubusercontent.com/JuHyeon-Nam/JuHyeon-Nam/main/phm-running.png)](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4)

<sub>실제 앱 실행 화면 · AGV 선택·배터리 이상 시연·센서 추이 · 공개 데이터·리플레이·합성 입력 기반</sub>

`Python` `LightGBM` `FastAPI` `WebSocket` `Three.js` `SQLite` `MQTT`

- **구현:** 30시점 센서 구간에서 통계·변화량·rFFT 등 **249개 특징**을 구성해 정상 및 8개 고장을 분류합니다. 학습과 추론은 특징 생성 런타임을 공유합니다.
- **운영 흐름:** 자산 선택, 상태·추론 결과 조회, 정비 작업 상태 변경, SQLite 이력 저장과 리포트를 연결했습니다. 좌표는 시각화에만 사용합니다.
- **평가:** 공식 Validation 분할에서 **Accuracy 93.29% / Macro-F1 0.5838**. 정상만 예측하는 기준선 Accuracy는 약 83%입니다.
- **검증 범위:** 가상 FAB와 규칙 기반 위험 점수는 시연 기능이며, 실제 공장 운영 성과나 미래 고장 확률을 검증한 결과는 아닙니다.

[코드·실행](https://github.com/JuHyeon-Nam/ServiceRobot_AI) · [38초 시연](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4) · [모델 카드](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/docs/MODEL_CARD.md)

### 02. Semiconductor Fault Detection

**불량 탐지율뿐 아니라 미탐과 오탐의 검토 부담까지 함께 평가한 제조 센서 분석**

[![반도체 모델 비교 리포트 실제 화면](https://raw.githubusercontent.com/JuHyeon-Nam/JuHyeon-Nam/main/secom-report.png)](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection)

<sub>실제 HTML 분석 리포트의 모델 비교 표 캡처 · SECOM 공개 데이터의 평가 결과</sub>

`Python` `pandas` `NumPy` `scikit-learn` `ExtraTrees`

- **분석:** 1,567개 표본·590개 센서의 결측·저분산·상관 구조를 점검하고 지도학습과 이상탐지 기준선을 비교했습니다.
- **검증:** 학습·검증·테스트 분리, 검증셋에서 임계값 선택, 테스트에서 불량 Recall·Precision·F2·PR-AUC와 미탐·오탐을 기록했습니다.
- **결과:** 임계값 0.10에서 **불량 21건 중 16건 탐지**. Recall **0.7619**, Precision **0.1951**, F2 **0.4819**, 미탐 5건·오탐 66건입니다.
- **활용 범위:** 검토 우선순위를 정하는 분석 신호입니다. 익명 센서 중요도를 물리적 원인으로 단정하거나 양산 검증 성과로 해석하지 않습니다.

[코드·리포트](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection) · [모델 카드](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection/blob/main/reports/model_card.md) · [임계값 비교](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection/blob/main/reports/figures/threshold_tradeoff.png)

### 03. Wafer AI Analyst

**전기 측정 파일을 소자별 특징과 이상 후보 검토 화면으로 연결하는 분석 도구**

[![Wafer AI Analyst 분석 결과 화면](https://raw.githubusercontent.com/JuHyeon-Nam/wafer-ai-analyst/main/docs/assets/dashboard_summary.png)](https://github.com/JuHyeon-Nam/wafer-ai-analyst)

<sub>기존 분석 결과 시각화 · 소자별 검토 상태와 이상 후보</sub>

`Python` `pandas` `RandomForest` `Streamlit` `Plotly`

- **대상:** diode·resistor·capacitor·NMOS의 측정 파일. **74개 측정·10,294개 곡선 포인트·4종 소자**를 분석했습니다.
- **본인 역할:** 파서, 데이터 정규화, ML 분석 흐름과 대시보드 통합. 소자 특징과 측정 이슈 해석은 팀원들과 협업했습니다.
- **구조:** `measurement → curve → feature`로 정리해 규칙 기반 검토와 모델 결과를 곡선·특징·리포트에 연결했습니다.
- **평가 범위:** **9개 합성 결함 시나리오** 테스트에서 Accuracy **0.9722**, Macro-F1 **0.9718**. 실제 불량 라벨이나 양산 원인 규명 성능을 검증한 결과는 아닙니다.

[코드·실행](https://github.com/JuHyeon-Nam/wafer-ai-analyst) · [특징 테이블](https://github.com/JuHyeon-Nam/wafer-ai-analyst/blob/main/docs/assets/feature_table_preview.png)

### 04. Recycle VQA Challenge

**재활용품 이미지와 질문을 함께 해석하는 멀티모달 AI 과제**

[![Recycle VQA 팀 최우수상 수상식 원본 사진](https://raw.githubusercontent.com/JuHyeon-Nam/Recycle_VQA_Challenge/master/assets/award_ceremony.jpg)](https://github.com/JuHyeon-Nam/Recycle_VQA_Challenge)

<sub>AI 챌린지 최우수상 수상식 · 팀 성과</sub>

`Qwen` `InternVL` `Prediction Comparison` `Error Analysis`

- **팀 성과:** 5인 팀으로 **193개 팀 중 1위·최우수상**. Private Score **0.97635**, Public Score **0.96452**.
- **본인 역할:** 모델 예측 로그 비교, 개수·위치·재질·분리배출 질문별 오답 분석, 취약 유형과 낮은 신뢰도 문항의 재추론 기준 수립 기여.
- **팀 구현:** 선택적 재추론·객체 재탐색을 결합한 최종 파이프라인. 전체 학습·객체 탐지·통합은 팀 성과와 구분합니다.

[코드·팀 역할](https://github.com/JuHyeon-Nam/Recycle_VQA_Challenge)

### 05. HEOGAON

**자연어 창업 계획을 확인 항목·준비 서류·담당 부서로 연결하는 AI 인허가 사전진단**

<table>
<tr><th>조건 확인·진단</th><th>서류 준비·진행 순서</th></tr>
<tr>
<td><a href="https://github.com/JuHyeon-Nam/HEOGAON"><img src="https://raw.githubusercontent.com/JuHyeon-Nam/JuHyeon-Nam/main/heogaon-diagnosis-app.png" width="360" alt="HEOGAON 실제 앱 진단 화면"></a></td>
<td><a href="https://github.com/JuHyeon-Nam/HEOGAON"><img src="https://raw.githubusercontent.com/JuHyeon-Nam/JuHyeon-Nam/main/heogaon-documents-app.png" width="360" alt="HEOGAON 실제 앱 서류 준비 화면"></a></td>
</tr>
</table>

<sub>원래 앱의 실제 실행 캡처 · 앱에 포함된 개발용 예시 시나리오 사용 · 외부 API 실시간 판단 결과가 아님</sub>

`User Scenarios` `Response Validation` `FastAPI` `Next.js` `SQLite`

- **팀 성과:** AI 해커톤 **103개 팀 중 본선 6개 팀** 선발.
- **본인 역할:** 사용자 시나리오 설계와 AI 응답 검증. 누락 정보 추가 질문, 서류·담당 부서·근거 연결, 외부 연결 실패 시 폴백을 확인했습니다.
- **검증:** 카페 창업 등 10개 대표 시나리오 반복 실행. 전체 업종·지역의 정확도나 행정기관의 최종 허가를 보장하지 않습니다.
- **팀 구조:** FastAPI·Next.js·SQLite·지식그래프. 전체 백엔드·그래프 구현을 개인 기여로 주장하지 않습니다.

[코드·역할](https://github.com/JuHyeon-Nam/HEOGAON) · [실제 시연 영상](https://youtu.be/qiv1yjfYUZQ)

### 06. CARCH

**보유 카드 활용과 신규 카드 추천을 구분하는 카드 소비 코치**

`Vue 3` `UI/UX` `Recommendation Flow` `AI Chat`

- **본인 역할:** 카드 메인·소비계획·분석·AI 채팅 UI/UX 구현. 보유 카드 사용 추천과 신규 발급 추천을 구분하고 추천 근거를 화면에 연결했습니다.
- **협업·성과:** 서비스 기획, 테스트와 발표 시나리오에 참여. 교육 과정 프로젝트 우수상·반 내 2위는 팀 성과입니다.

## 기술 역량

| 영역 | 적용 기술·경험 |
|---|---|
| 데이터·모델 | Python, pandas, NumPy, scikit-learn, LightGBM, ExtraTrees, RandomForest · 센서 전처리·특징 추출·불균형 평가 |
| API·저장·연결 | FastAPI, Pydantic, REST API, WebSocket, SQLite, MQTT · 추론·상태 전달·정비 이력 |
| 화면·시각화 | JavaScript, Three.js, Streamlit, Plotly, Vue 3 · 3D 관제·데이터 분석·서비스 UI |
| 개발·검증 | Git, Docker, Linux, pytest, GitHub Actions, Playwright · 환경 구성·API/브라우저 테스트 |
| 로봇 환경 | ROS 2, MoveIt 2, RViz2, UR ROS 2 Driver · 가상 계획·실행, 실물 상태 조회·표시 연동 |
| 제조·자동화 | 도면, AutoCAD, Inventor, 선반·밀링·금형, PLC 센서 I/O·인터록 · 셋업·시운전·점검 지원 |

**학습 기반:** C/C++ 기초, SQL, Django·DRF. 기술별 사용 범위와 개인·팀 기여는 프로젝트 설명에서 구분합니다.

## 제조·자동화 경험

| 분야 | 경험 |
|---|---|
| **공공 제조 연구기관 · 현장실습** | 로봇 드릴링·밀링 실험 세팅, 가공 조건·측정 데이터 정리, 홀 형상·표면 상태 비교 지원. ROS 2 기반 가상 계획·실행과 실물 상태 조회·3D 표시 연동 |
| **자동화설비 업체 · 기술 지원** | 설치·셋업·시운전·유지보수 지원. 도면·I/O 리스트와 접점·배선·통신 상태 대조, 시퀀스·인터록 점검, 조치 후 반복 운전 확인 |
| **정밀부품 제조업체 · 제조 현장** | 프레스·사출·조립·검사 공정 경험. 설비·금형 세팅 지원, 버·변형·형상·치수 편차 점검 |

로봇 현장실습의 현재 범위는 실험 지원·개발 환경·상태 연동입니다. PC 명령 기반 실물 이동, 카메라 좌표 보정과 접촉 제어 완료를 포함하지 않습니다.

## 학습과 자격

- **학습 배경:** 소프트웨어융합 전공 재학, 전자·반도체 교과 이수, 경영학 학사, 정밀기계 교육.
- **교육:** AI·소프트웨어 집중교육 1학기 수료, AI반도체 활용·응용 및 온라인 AI 전문교육 수료.
- **성취:** 멀티모달 AI 대회 최우수상, 서비스 프로젝트 우수상, AI 해커톤 본선 진출, 대학 학업 우등 성취.

| 분야 | 자격·성적 |
|---|---|
| 데이터 | 데이터분석 준전문가 **ADsP** · 국가공인 |
| 품질·개선 | **6시그마 Green Belt 프로젝트** · 등록민간자격 |
| 가공·설비 | 금형기능사, 컴퓨터응용선반기능사, 컴퓨터응용밀링기능사, 승강기기능사 |
| 정보처리·사무 | 정보처리기능사(취득 당시 명칭), 컴퓨터활용능력 2급, 워드프로세서, e-Test 워드 1급 |
| 기타 | 텔레마케팅관리사, 매경TEST 우수(과거 취득 이력) |
| 어학 | **TOEIC Speaking IH**, OPIc IM2 |

---

<sub>공개용 기술 포트폴리오 · 소속·세부 학적·근무기간·연락처는 비공개 · 실제 실행 캡처와 원본 수상 자료를 사용하며, 시연 데이터의 범위를 구분합니다.</sub>
