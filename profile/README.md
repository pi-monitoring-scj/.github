# Pi-Monitoring Project: Phase 1
> **"From Physical Vibration to Digital Insight"**  
> 하드웨어의 물리적 움직임을 데이터화하고, 실시간으로 관제하는 통합 시스템 설계 프로젝트입니다.

##  Project Overview
본 프로젝트는 산업용 장비의 예지 보전(Predictive Maintenance)을 목표로 하며, 센서 데이터 수집부터 웹 시각화까지의 전체 파이프라인을 구축합니다. 
기계적 구조에 대한 이해와 운영체제(Pintos) 레벨의 시스템 지식을 결합하여 최적화된 모니터링 솔루션을 구현합니다.

---

##  System Architecture
1. **Data Acquisition (C)**: MPU-6050 센서로부터 I2C 통신 및 인터럽트 방식을 통해 가속도/자이로 데이터를 초고속 샘플링합니다.
2. **Edge Processing**: 수집된 Raw 데이터를 전처리하고, 필요시 FFT(고속 푸리에 변환)를 통해 핵심 주파수 성분을 추출합니다.
3. **Real-time Delivery**: FastAPI의 WebSocket을 활용하여 저지연(Low-latency) 데이터 스트리밍을 구현합니다.
4. **Digital Twin**: 센서의 물리적 변화를 웹 상의 3D 모델 및 그래프에 실시간으로 매핑하여 직관적인 관제를 지원합니다.

---

##  Tech Stack
| Category | Technology |
| :--- | :--- |
| **Embedded** | Raspberry Pi 5, C Language, I2C Protocol |
| **Sensor** | MPU-6050 (6-axis Accelerometer & Gyroscope) |
| **Backend** | Python, FastAPI, WebSocket |
| **Frontend** | React, Three.js (Digital Twin 시각화 예정) |
| **Infra** | Docker, Ubuntu Server |

---

##  Key Objectives
* **신뢰성**: 하드웨어 레지스터 직접 제어 및 인터럽트 처리를 통한 데이터 유실 최소화
* **직관성**: 복잡한 물리 수치를 관리자가 즉각 파악할 수 있는 시각화 UI 제공
* **확장성**: 향후 CAN 통신 및 MCU(STM32 등) 노드 추가를 고려한 모듈형 아키텍처 설계

---

언제든지 변경 가능
