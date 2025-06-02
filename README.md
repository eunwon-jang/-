# Quarter Car Suspension System Modeling & Simulation

본 프로젝트는 차량 서스펜션 시스템의 1/4 모델을 바탕으로 
모델링, 수치해석, 그리고 제어 시스템 해석을 수행한 결과를 정리한 것입니다.

---

## 📌 프로젝트 목적
- 차량 승차감 및 조향안정성 향상
- 서스펜션 파라미터 변화에 따른 시스템 응답 분석
- MATLAB 기반 RMS 가속도 분석 및 Frequency Response 평가

---

## 🔧 모델 구성

- 2 DOF Quarter Car Model 사용
- Newton 및 Lagrangian 기반 수식 유도
- State-Space 모델 구성

모델 상세 유도는 [`model/equations.md`](model/equations.md) 참조

---

## 🧪 시뮬레이션

MATLAB 기반 시뮬레이션:

- Step Response
- Sine Input Response
- Bump (요철) Response
- Parameter Sweep (k₁, c₁ 변화)

코드는 [`simulation/suspension_sine_rms_analysis.m`](simulation/suspension_sine_rms_analysis.m) 참조

---

## 📊 주요 결과

- RMS 가속도 결과: `results.csv` 참고
- Frequency Response: `analysis/bode_plot.png`
- 최적 감쇠비 및 스프링 상수 제안

---

## 📈 시각화 샘플

![Step Response](simulation/plots/step_response.png)
![Sine Response](simulation/plots/sine_response_f1Hz.png)

---

## 📄 보고서

최종 보고서는 [`report/QuarterCar_Report.pdf`](report/QuarterCar_Report.pdf) 참조
