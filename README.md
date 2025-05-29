# quarter_car 서스펜션 시스템 분석

(quarter-car) 서스펜션 시스템의 모델링, 시뮬레이션 및 주파수 응답을 분석하고 승차감에 가장 큰 영향을 주는 변수를 분석하여 파라미터를 최적화한다.

## 📌 포함 내용

- 시스템 모델링 및 전달함수 도출
- MATLAB 기반 시뮬레이션 (단계 응답, 사인파, 요철 입력)
- 주파수 응답 (Bode Plot), RMS 가속도 계산
- 결과 보고서 (PDF 포함)

## 💻 실행 방법

## 🧪 시뮬레이션 코드

- [step_response.m](simulation/step_response.m) → Step 응답 시뮬레이션
- [sine_input.m](simulation/sine_input.m) → 사인파 입력 응답
- [bump_input.m](simulation/bump_input.m) → 노면 요철 입력 응답

```matlab
% 일부 예시만 보여주기
t = 0:0.001:5;
z_input = 0.05 * sin(2*pi*1*t);
[y, t_out, x_out] = lsim(sys, z_input, t);
plot(t_out, y)

- RMS 가속도: **331.11 m/s²**
- 전달함수:
