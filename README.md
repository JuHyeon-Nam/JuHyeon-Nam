# 남주현 · JuHyeon Nam

정밀 커넥터를 검사하고 자동화 설비 시운전을 지원했습니다. 설비가 멈추면 센서에 어떤 신호가 들어왔고 실제로 어디까지 움직였는지 확인했습니다. 지금은 Python과 SQL로 장비 기록을 분석하고 점검에 쓸 수 있는 화면을 만듭니다.

[로봇 관제](#무인운반로봇-진단과-관제) · [반도체 불량 탐지](#반도체-불량-탐지) · [SSAFY AI 챌린지](#ssafy-ai-챌린지) · [카치](#카치)

## 무인운반로봇 진단과 관제

로봇에 이상 알림이 떴을 때 어디부터 점검할지 보여주는 화면을 만들었습니다. AI-Hub의 배터리와 주행 기록을 연속된 30개씩 묶어 LightGBM으로 정상과 고장 8종을 구분했습니다. 진단 결과와 점검할 센서를 FastAPI로 보내고, SQLite에 저장한 이전 기록도 화면에서 볼 수 있게 했습니다.

[저장소](https://github.com/JuHyeon-Nam/ServiceRobot_AI) · [▶ 38초 시연](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4) · [모델 평가](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/docs/MODEL_CARD.md) · [SQL 집계 코드](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/src/telemetry_store.py)

[![로봇 위치와 상태를 보여주는 3D 관제 화면](https://raw.githubusercontent.com/JuHyeon-Nam/ServiceRobot_AI/main/assets/twin_workspace.png)](https://raw.githubusercontent.com/JuHyeon-Nam/ServiceRobot_AI/main/assets/twin_workspace.png)

<sub>저장된 기록과 합성 입력을 사용한 관제 시연입니다. 이미지를 누르면 원본이 열립니다.</sub>

## 반도체 불량 탐지

불량을 더 많이 잡으려면 경보가 얼마나 늘어나는지 SECOM 공개 데이터로 살펴봤습니다. 검증 데이터로 경보 기준을 고른 뒤, 따로 둔 테스트 데이터에서 불량 **21건 중 16건**을 탐지했습니다. 정상인데 경보가 울린 **66건**도 집계했습니다.

[저장소](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection) · [평가 상세](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection/blob/main/reports/model_card.md) · [모델 비교표](https://github.com/JuHyeon-Nam/JuHyeon-Nam/blob/main/secom-report.png)

[![경보 기준값에 따른 검증 데이터의 재현율, 정밀도, F2 비교](https://raw.githubusercontent.com/JuHyeon-Nam/semiconductor-process-fault-detection/main/reports/figures/threshold_tradeoff.png)](https://raw.githubusercontent.com/JuHyeon-Nam/semiconductor-process-fault-detection/main/reports/figures/threshold_tradeoff.png)

<sub>경보 기준을 고를 때 사용한 검증 데이터 그래프입니다.</sub>

## SSAFY AI 챌린지

재활용품 사진에 관한 질문에 답하는 과제에서 InternVL 실험을 맡았습니다. 팀원이 실험한 Qwen과 답을 맞춰 보고 개수·위치·재질 등 질문 유형별로 오답을 확인했습니다. 팀은 이 결과를 최종 답안에 반영했고 **193개 팀 중 1위로 최우수상**을 받았습니다.

[저장소와 팀 역할](https://github.com/JuHyeon-Nam/Recycle_VQA_Challenge)

[![SSAFY AI 챌린지 최종 리더보드](https://raw.githubusercontent.com/JuHyeon-Nam/Recycle_VQA_Challenge/master/assets/leaderboard_private.png)](https://raw.githubusercontent.com/JuHyeon-Nam/Recycle_VQA_Challenge/master/assets/leaderboard_private.png)

## 카치

같은 소비 내역으로 보유 카드의 혜택과 추천 카드의 예상 혜택을 비교하는 서비스입니다. Vue로 소비 분석 화면을 만들고 팀원의 API를 연결했습니다. 서버가 보낸 두 금액이 각각 올바른 카드에 표시되는지 팀원과 확인했습니다.

[팀 저장소](https://github.com/whtjddlr/carch)

<p>
  <a href="https://raw.githubusercontent.com/whtjddlr/carch/81356ac769b7a8ca839a48dcae94e54acb829b40/docs/screenshots/appstore/iphone-6-9/01_cards_home.png"><img src="https://raw.githubusercontent.com/whtjddlr/carch/81356ac769b7a8ca839a48dcae94e54acb829b40/docs/screenshots/appstore/iphone-6-9/01_cards_home.png" alt="카치 보유 카드 화면" width="228"></a>
  <a href="https://raw.githubusercontent.com/whtjddlr/carch/81356ac769b7a8ca839a48dcae94e54acb829b40/docs/screenshots/appstore/iphone-6-9/02_analytics.png"><img src="https://raw.githubusercontent.com/whtjddlr/carch/81356ac769b7a8ca839a48dcae94e54acb829b40/docs/screenshots/appstore/iphone-6-9/02_analytics.png" alt="카치 월별 소비 분석 화면" width="228"></a>
</p>

<sub>카치의 보유 카드 화면과 월별 소비 분석 화면입니다.</sub>

## 다른 작업

- [Wafer AI Analyst](https://github.com/JuHyeon-Nam/wafer-ai-analyst) · 웨이퍼 전기 측정 파일을 읽어 소자별 특징을 정리하고 Streamlit에서 볼 수 있게 했습니다.
- [HEOGAON](https://github.com/JuHyeon-Nam/HEOGAON) · 창업 조건이 빠졌을 때 AI가 필요한 정보를 다시 묻는지, 안내한 서류에 근거가 붙는지 확인했습니다.

