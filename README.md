# -hybrid-suspension-analysis/
│
├── README.md                ← 프로젝트 개요 + 결과 정리
├── LICENSE                  ← MIT 라이선스 (원하면 추가)
│
├── model/                   ← 시스템 모델 수식 및 전달함수
│   └── quarter_car_eq.md
│
├── simulation/              ← MATLAB 코드 및 시뮬 결과
│   ├── step_response.m
│   ├── sine_input_response.m
│   ├── bump_input_response.m
│   └── results/             
│       ├── step_plot.png
│       ├── sine_plot.png
│       └── bump_plot.png
│
├── analysis/                ← 주파수 응답, RMS 계산
│   ├── bode_plot.png
│   ├── rms_calc.m
│   └── transfer_function.txt
│
└── report/                  ← 보고서 초안 및 PDF
    ├── quarter_car_report.md
    └── quarter_car_report.pdf
