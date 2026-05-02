# Pi-Monitoring Project: Phase 1 (MQTT Integrated)
> **"From Physical Vibration to Digital Insight via Industrial Standard"**  
> 하드웨어의 물리적 움직임을 데이터화하고, MQTT 메시징 프로토콜을 통해 실시간 관제하는 통합 시스템 설계 프로젝트입니다.

## Project Overview
본 프로젝트는 산업용 장비의 예지 보전(Predictive Maintenance)을 목표로 합니다. 
특히 **MQTT(Message Queuing Telemetry Transport)** 브로커를 도입하여, 데이터 수집(C)과 서비스 제공(FastAPI)을 완전히 분리한 **분산형 시스템 아키텍처**를 지향합니다.

---

## System Architecture


1. **Data Acquisition (C - Publisher)**: MPU-6050 센서 데이터를 초고속 샘플링한 후, `paho-mqtt` 라이브러리를 통해 특정 Topic으로 데이터를 발행(Publish)합니다.
2. **Message Brokering (Mosquitto)**: 라즈베리 파이 내부에 구축된 MQTT 브로커가 메시지를 수신하고, 필요한 모든 클라이언트에게 실시간으로 전달합니다.
3. **Backend Processing (FastAPI - Subscriber)**: MQTT Topic을 구독(Subscribe)하여 데이터를 가공하고, 웹 프론트엔드 전달을 위해 WebSocket으로 변환 송출합니다.
4. **Digital Twin (React/Three.js)**: 전달받은 물리 데이터를 기반으로 3D 모델의 회전(Rotation) 및 진동 수치를 실시간 렌더링합니다.

---

## Tech Stack
| Category | Technology |
| :--- | :--- |
| **Embedded** | Raspberry Pi 5, C Language, I2C Protocol |
| **Messaging** | **MQTT (Eclipse Mosquitto)** |
| **Sensor** | MPU-6050 (6-axis Accelerometer & Gyroscope) |
| **Backend** | Python, FastAPI, Paho-MQTT, WebSocket |
| **Frontend** | React, Three.js (Digital Twin 시각화 예정) |

---

## Key Objectives
* **비동기성 & 확장성**: MQTT Pub/Sub 구조를 통해 센서 노드가 늘어나도 시스템 전체의 수정 없이 유연하게 확장 가능.
* **신뢰성**: 하드웨어 레지스터 직접 제어 및 인터럽트 처리를 통한 데이터 유실 최소화.
* **실무형 아키텍처**: 자동차/제어 산업군에서 널리 쓰이는 표준 통신 규약을 적용한 시스템 설계 역량 입증.

---
언제든 수정 가능 
