# Quarter Car Suspension System Modeling & Simulation

---

## 📌 문제 정의 (Problem Statement)

자동차는 주행 중 도로의 요철이나 장애물 등 다양한 외란(external disturbance)에 지속적으로 노출됩니다. 이러한 외란은 차량의 승차감(Ride Comfort), 조종 안정성(Handling Stability), 그리고 탑승자의 피로도에 직접적인 영향을 미칩니다.  
서스펜션 시스템은 이러한 외란을 효과적으로 흡수하여 차체의 진동을 감소시키는 핵심적인 역할을 수행합니다.

본 프로젝트에서는 차량 서스펜션 시스템을 **Quarter-Car 모델**을 기반으로 모델링하고, 시스템의 주요 파라미터가 승차감에 미치는 영향을 시뮬레이션과 해석을 통해 분석합니다.

---

## 📌 모델 선정 이유 (Model Selection)

본 연구에서는 2자유도(2-DOF) Quarter-Car 모델을 채택하였으며, 그 이유는 다음과 같습니다:

- **단순성 및 효율성**  
  - Full-Car 모델에 비해 파라미터 수가 적고, 초기 시스템 분석 및 민감도 해석에 적합합니다.
  - 차체 질량 (m₁)과 현가 질량 (m₂)으로 구성되어 서스펜션과 타이어의 상호작용을 효과적으로 표현합니다.

- **서스펜션 동특성 표현 용이**  
  - 스프링 상수 (k₁, k₂), 감쇠기 (c₁), 노면 입력 (z) 등을 이용하여 승차감 및 안정성에 영향을 주는 주요 요인을 포함할 수 있습니다.

- **실험 데이터 검증 및 해석 용이성**  
  - 실험 데이터와의 비교, 시뮬레이션 검증, 파라미터 민감도 분석 등이 수월하게 수행됩니다. 

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
