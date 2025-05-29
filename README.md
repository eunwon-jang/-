# quarter_car 서스펜션 시스템 분석

(quarter-car) 서스펜션 시스템의 모델링, 시뮬레이션 및 주파수 응답을 분석하고 승차감에 가장 큰 영향을 주는 변수를 분석하여 파라미터를 최적화한다.

## 📌 포함 내용

- 시스템 모델링 및 전달함수 도출
- MATLAB 기반 시뮬레이션 (단계 응답, 사인파, 요철 입력)
- 주파수 응답 (Bode Plot), RMS 가속도 계산
- 결과 보고서 (PDF 포함)

## 💻 실행 방법

1. `/시뮬레이션/` 폴더 내 `.m` 파일을 MATLAB에서 실행하세요.  
2. 입력 조건에 따라 차체 응답을 시각화할 수 있습니다.

## 📈 핵심 결과
git add step_응답.m
git commit -m "% 파라미터 설정
m1 = 250;    % kg (Sprung mass)
m2 = 50;     % kg (Unsprung mass)
k1 = 16000;  % N/m (Suspension stiffness)
c1 = 1000;   % Ns/m (Damping coefficient)
k2 = 190000; % N/m (Tire stiffness)

% 상태공간 행렬
A = [0 1 0 0;
    -k1/m1 -c1/m1 k1/m1 c1/m1;
     0 0 0 1;
     k1/m2 c1/m2 -(k1+k2)/m2 -c1/m2];

B = [0; 0; 0; k2/m2];
C = [1 0 0 0];  % x1만 출력 (차체 변위)
D = 0;

sys = ss(A,B,C,D);

% Step input (도로 변화)
step(sys)
title('차량 차체 변위 응답')
xlabel('시간 [s]')
ylabel('차체 변위 [m]')
grid on




% 시간 설정
t = 0:0.001:5;  % 5초까지 0.001초 간격

% 사인파 입력 (도로 진동 모델) - 진폭 0.05m, 주파수 1Hz
z_input = 0.05 * sin(2 * pi * 1 * t);

% LTI 시스템 시뮬레이션
[y, t_out, x_out] = lsim(sys, z_input, t);

% 그래프
plot(t_out, y, 'b')
title('사인파 입력에 대한 차체 응답')
xlabel('시간 [s]')
ylabel('차체 변위 [m]')
grid on

% 시간 설정
t = 0:0.001:5;

% 펄스 + 랜덤 진동 조합 (노면 요철)
z_input = zeros(size(t));
z_input(t >= 1 & t < 1.1) = 0.03;  % 1초에 3cm 요철
z_input = z_input + 0.005 * randn(size(t));  % 랜덤 노면 진동 추가

% 시뮬레이션
[y, t_out, x_out] = lsim(sys, z_input, t);

% 그래프
plot(t_out, y, 'r')
title('노면 요철 입력에 대한 차체 응답')
xlabel('시간 [s]')
ylabel('차체 변위 [m]')
grid on

"
git push

- RMS 가속도: **331.11 m/s²**
- 전달함수:
