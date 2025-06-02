# Quarter Car Suspension System Modeling & Simulation

본 프로젝트는 차량 서스펜션 시스템의 1/4 모델을 바탕으로 
모델링, 수치해석, 그리고 제어 시스템 해석을 수행한 결과를 정리한 것입니다.

---

## 📌 프로젝트 목적
1. 문제 정의 및 모델 선택 이유
1.1 문제 정의
자동차는 주행 중 도로의 요철이나 장애물과 같은 외란(external disturbance)에 지속적으
로 노출된다. 이러한 외란은 차량 승차감(ride comfort), 조종 안정성(handling stability), 탑
승자의 피로도 등에 큰 영향을 미친다. 특히, 서스펜션 시스템은 이러한 외란을 효과적으로
흡수하고 차체의 진동을 감소시키는 역할을 수행한다.
본 연구에서는 차량의 서스펜션 시스템을 Quarter-Car 모델을 이용하여 모델링하고자 한
다. Quarter-Car 모델은 차량 전체가 아닌 1/4 부분(한쪽 바퀴 부분)을 대상으로 하는 대표
적인 단순화 모델로, 차량 시스템의 주요 진동 거동을 비교적 정확하게 설명할 수 있다. 이
모델을 통해 다음과 같은 문제를 분석하고자 한다.

1.2 모델 선택 이유
본 연구에서 2자유도(2-DOF) Quarter-Car 모델을 선정한 이유는 다음과 같다.
- 모델의 단순성과 효율성: 전체 차량 시스템을 모델링하는 4-DOF 또는 Full-Car 모델은
복잡하고 많은 파라미터를 요구하므로, 초기 분석에는 Quarter-Car 모델이 적절하다. 특히,
2개의 질량(차체 질량 m1, 현가 질량 m2)을 이용하여 서스펜션과 타이어의 상호작용을 효
과적으로 고려할 수 있다.
- 서스펜션 동특성 표현 가능: 스프링(k1, k2), 감쇠기(b1), 노면 입력(z) 등의 파라미터를
포함하여 차량 승차감 및 주행 안정성에 영향을 주는 주요 요인을 반영할 수 있다.
- 실험 데이터 및 이론 검증 용이성: 실험 데이터와의 비교, 시뮬레이션 검증, 파라미터 민
감도 분석 등에 적합한 구조를 가진다.

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
