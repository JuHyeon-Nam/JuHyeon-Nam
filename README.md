# 남주현 · JuHyeon Nam

정밀 커넥터를 검사하고 자동화 설비 시운전을 지원했습니다. 설비가 멈추면 센서 신호와 실제 동작부터 대조했습니다. 지금은 Python과 SQL로 장비 기록을 정리하고, 점검에 필요한 정보를 화면으로 보여주는 도구를 만듭니다.

## 주요 프로젝트

### [ServiceRobot AI](https://github.com/JuHyeon-Nam/ServiceRobot_AI) · 무인운반로봇 진단과 관제

AI-Hub의 공개 센서 기록을 연속된 30개씩 묶고, LightGBM으로 정상과 고장 8종을 구분했습니다. FastAPI 응답에 점검할 센서 항목을 담고, SQLite에 쌓인 진단 이력을 관제 화면에서 조회할 수 있게 했습니다.

[38초 시연](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4) · [모델 평가](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/docs/MODEL_CARD.md) · [이력 집계 코드](https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/src/telemetry_store.py)

### [Semiconductor Fault Detection](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection) · 반도체 공정 센서 분석

공개 SECOM 데이터로 불량 탐지 모델을 비교했습니다. 테스트 불량 21건 중 16건을 찾았고, 정상인데 불량으로 분류된 66건도 함께 기록했습니다. [평가 결과와 기준](https://github.com/JuHyeon-Nam/semiconductor-process-fault-detection/blob/main/reports/model_card.md)

### [Recycle VQA Challenge](https://github.com/JuHyeon-Nam/Recycle_VQA_Challenge) · SSAFY AI 챌린지

InternVL 실험을 맡아 팀원이 실험한 Qwen과 답을 비교했습니다. 개수, 위치, 재질처럼 질문 유형을 나눠 오답을 확인했고, 팀은 이 결과를 최종 답안에 반영했습니다. 5인 팀으로 **193개 팀 중 1위·최우수상**을 받았습니다.

## 다른 작업

- [카치](https://github.com/whtjddlr/carch) · Vue로 소비 분석 화면을 만들고 팀원의 API를 연결했습니다. 보유 카드와 추천 카드의 예상 혜택이 각각 맞게 표시되는지 확인했습니다.
- [Wafer AI Analyst](https://github.com/JuHyeon-Nam/wafer-ai-analyst) · 웨이퍼 전기 측정 파일을 읽어 소자별 특징을 정리하고 Streamlit 화면에서 확인할 수 있게 했습니다.
- [HEOGAON](https://github.com/JuHyeon-Nam/HEOGAON) · 창업 조건이 빠졌을 때 AI가 추가로 묻는지, 답변에서 준비 서류와 근거를 확인할 수 있는지 테스트했습니다.

## 로봇 관제 화면

<a href="https://github.com/JuHyeon-Nam/ServiceRobot_AI/blob/main/assets/twin_walkthrough.mp4">
  <img src="https://raw.githubusercontent.com/JuHyeon-Nam/ServiceRobot_AI/main/assets/twin_workspace.png" alt="로봇 위치와 상태를 보여주는 ServiceRobot AI 관제 화면" width="640">
</a>

저장된 센서 기록과 합성 입력을 사용한 시연입니다.

