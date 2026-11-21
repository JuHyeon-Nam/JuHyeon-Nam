## 남주현

정밀 커넥터를 검사하고 자동화 설비 시운전을 도우며 제조 현장에서 일했습니다. 지금은 로봇과 설비에서 나오는 신호를 분석하고, 이상이 생겼을 때 어디부터 점검할지 보여주는 소프트웨어를 만듭니다.

### 경력 · 현장실습

| 기간 | 소속 | 맡은 일 |
| --- | --- | --- |
| 2026.07 ~ 현재 | **한국생산기술연구원** · 현장실습 | Ubuntu와 ROS 2로 협동로봇 UR30의 동작을 시험하고, 로봇 드릴링 실험에서 재료별 가공음을 비교했습니다. |
| 2023.06 ~ 2024.03 | **카일코리아** · 제어기술팀 | PLC 자동화 설비의 설치와 시운전을 지원했습니다. 설비가 멈추면 도면을 보며 센서 신호와 실제 동작을 대조했습니다. |
| 2020.01 ~ 2021.01 | **HRS코리아** · 제조2팀 | 정밀 커넥터를 생산·검사했습니다. 현미경으로 휨과 버를 확인하고 주요 치수를 도면 공차와 대조했습니다. |

### 학력 · 교육

- **인하대학교 소프트웨어융합공학과** · 2025.03 편입, 2027.02 졸업 예정
- **삼성청년SW·AI아카데미(SSAFY) 15기** · AI 트랙 1학기 925시간 이수
- **금오공과대학교 전자공학부** · 반도체시스템전공, 2024.03 ~ 2025.02
- **학점은행제 경영학사** · 학위 취득
- **수원하이텍고등학교 정밀기계과** · 2020.02 졸업

### 프로젝트

#### [무인운반로봇 진단·관제](https://github.com/JuHyeon-Nam/ServiceRobot_AI)

로봇 한 대를 고르면 어떤 센서부터 점검할지 보여주는 관제 화면을 만들었습니다. 배터리와 주행 기록으로 고장 유형을 분류하고, FastAPI로 진단 결과와 근거가 된 센서 항목을 함께 보냅니다. [38초 시연](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4) · [모델 평가](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/docs/MODEL_CARD.md)

<a href="https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4"><img src="https://raw.githubusercontent.com/JuHyeon-Nam/ServiceRobot_AI/main/assets/twin_workspace.png" alt="무인운반로봇 관제 화면. 누르면 38초 시연 영상을 엽니다." width="320"></a>

#### [반도체 공정 불량 탐지](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection)

불량을 더 많이 잡을 때 오경보가 얼마나 늘어나는지 SECOM 데이터로 비교했습니다. 선택한 기준으로 테스트한 결과, 불량 21건 중 16건을 찾았고 정상 66건에도 경보가 울렸습니다. [평가 결과](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection/blob/main/reports/model_card.md)

<a href="https://raw.githubusercontent.com/JuHyeon-Nam/semiconductor-process-fault-detection/main/reports/figures/threshold_tradeoff.png"><img src="https://raw.githubusercontent.com/JuHyeon-Nam/semiconductor-process-fault-detection/main/reports/figures/threshold_tradeoff.png" alt="반도체 불량 경보 기준을 바꿔 가며 비교한 평가 그래프" width="320"></a>

#### [SSAFY AI 챌린지 · 재활용품 이미지 질의응답](https://github.com/JuHyeon-Nam/Recycle_VQA_Challenge)

사진 속 물건의 개수나 재질을 묻는 문제에서 InternVL 실험을 맡았습니다. 팀원과 두 모델의 오답을 질문 유형별로 비교해 최종 답안을 정했고, **193개 팀 중 1위로 최우수상**을 받았습니다.

<a href="https://raw.githubusercontent.com/JuHyeon-Nam/Recycle_VQA_Challenge/master/assets/leaderboard_private.png"><img src="https://raw.githubusercontent.com/JuHyeon-Nam/Recycle_VQA_Challenge/master/assets/leaderboard_private.png" alt="재활용품 이미지 질의응답 대회 최종 순위표" width="320"></a>

#### [카치 · 카드 혜택 비교](https://github.com/whtjddlr/carch)

같은 소비 내역을 내 카드와 추천 카드로 결제하면 혜택이 얼마나 달라지는지 보여주는 서비스입니다. Vue로 소비 분석 화면을 만들고 팀원이 개발한 API를 연결했습니다.

<a href="https://raw.githubusercontent.com/whtjddlr/carch/81356ac769b7a8ca839a48dcae94e54acb829b40/docs/screenshots/appstore/iphone-6-9/01_cards_home.png"><img src="https://raw.githubusercontent.com/whtjddlr/carch/81356ac769b7a8ca839a48dcae94e54acb829b40/docs/screenshots/appstore/iphone-6-9/01_cards_home.png" alt="카치 보유 카드 화면" width="142"></a>
<a href="https://raw.githubusercontent.com/whtjddlr/carch/81356ac769b7a8ca839a48dcae94e54acb829b40/docs/screenshots/appstore/iphone-6-9/02_analytics.png"><img src="https://raw.githubusercontent.com/whtjddlr/carch/81356ac769b7a8ca839a48dcae94e54acb829b40/docs/screenshots/appstore/iphone-6-9/02_analytics.png" alt="카치 월별 소비 분석 화면" width="142"></a>

#### [Wafer AI Analyst · 웨이퍼 전기 측정 데이터 분석](https://github.com/JuHyeon-Nam/wafer-ai-analyst)

측정 장비가 내보낸 CSV와 엑셀 파일을 읽는 코드를 작성했습니다. 다이오드, 저항 등 소자별 측정 곡선과 이상 후보를 Streamlit 대시보드에서 살펴볼 수 있도록 연결했습니다.

<a href="https://github.com/JuHyeon-Nam/wafer-ai-analyst/blob/main/docs/assets/dashboard_summary.png"><img src="https://raw.githubusercontent.com/JuHyeon-Nam/wafer-ai-analyst/main/docs/assets/dashboard_summary.png" alt="웨이퍼 전기 측정 분석 대시보드 요약" width="320"></a>

#### [HEOGAON · 창업 인허가 안내](https://github.com/JuHyeon-Nam/HEOGAON)

창업 조건에 맞춰 필요한 서류를 안내하는 팀 프로젝트에서 AI 답변 검증을 맡았습니다. 판매 품목이나 시설 정보가 빠졌을 때 서비스가 되묻는지, 안내한 서류에 근거가 있는지 확인했습니다. [시연 영상](https://youtu.be/qiv1yjfYUZQ)

<a href="https://youtu.be/qiv1yjfYUZQ"><img src="https://img.youtube.com/vi/qiv1yjfYUZQ/hqdefault.jpg" alt="HEOGAON 인허가 안내 서비스 시연 영상 미리보기" width="300"></a>
