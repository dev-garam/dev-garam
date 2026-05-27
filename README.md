# 김가람 | Backend Engineer

Node.js/NestJS 기반의 백엔드 개발자입니다.  
이벤트성 트래픽, 대용량 로그/정산 데이터, 복잡한 권한 모델처럼 운영 중 병목이 드러나는 영역을 주로 다뤄왔습니다.

- **주요 기술**: Node.js, TypeScript, NestJS, Express, MySQL, MongoDB, Redis, Kafka
- **관심 영역**: 대용량 데이터 처리, 비동기 이벤트 처리, DB 성능 개선, 운영 가능한 백엔드 구조 설계
- **경력**: 6년 10개월
- **연락처**: [feelsky665@naver.com](mailto:feelsky665@naver.com)
- **GitHub**: [github.com/dev-garam](https://github.com/dev-garam)
- **Service**: [fateflow.app](https://fateflow.app)

## Summary

서비스 성장 과정에서 발생한 성능 저하와 데이터 정합성 문제를 개선해 온 백엔드 개발자입니다.

MongoDB Sharding, MySQL 인덱스/쿼리 튜닝, Redis 기반 실시간 집계, Kafka 이벤트 파이프라인을 사용해 쓰기 부하와 응답 지연을 줄였습니다. 단순히 새 기술을 도입하기보다, 장애 복구 가능성, 운영 난이도, 팀의 유지보수 비용을 함께 고려해 구조를 선택하는 편입니다.

최근에는 글로벌 리워드 서비스에서 월 600만 건 이상 누적되는 걸음 로그와 GPS 이벤트를 처리했고, 복잡한 RBAC 목록 API의 응답 시간을 13초에서 1초대로 줄인 경험이 있습니다.

## Core Strengths

| Area | Experience |
| --- | --- |
| Backend API | Node.js, NestJS, Express 기반 API 서버 설계 및 개발 |
| Data & Performance | MySQL `EXPLAIN` 분석, 인덱스 재설계, MongoDB Sharding, 대량 로그 처리 |
| Event Architecture | Kafka, Redis, 배치 처리를 활용한 비동기 처리 및 정합성 관리 |
| Reliability | 원본 로그 기반 재계산 구조, 무중단 스키마 변경, Kubernetes CronJob 분리 |
| Collaboration | 시퀀스 다이어그램 기반 요구사항 정리, 기획/디바이스/AI 모델 담당자와 인터페이스 조율 |

## Experience

### 주식회사 시어스랩

**Backend Engineer**  
2024.07 - 2026.02

#### StepEarth - 글로벌 리워드 플랫폼

**2024.07 - 2025.11**  
`Node.js` `Express` `MySQL` `MongoDB Sharding` `Redis` `Kubernetes`

- 월 600만 건 이상 누적되는 걸음 로그를 처리하기 위해 MongoDB Sharding을 적용했습니다.
- `user_id`를 샤딩 키로 설계해 특정 사용자/국가 구간에 쓰기가 몰리는 상황을 줄이고, 로그 저장 구조를 글로벌 타임존 처리에 맞게 정리했습니다.
- GPS 기반 타일 이동 이벤트에서 발생하는 실시간 쓰기 부하를 줄이기 위해, 실시간 집계와 실제 수익 정산을 분리했습니다.
- 이동 이벤트는 Redis에 빠르게 집계하고, 정산은 원본 로그를 기준으로 비동기/배치 처리하도록 설계해 장애 후 재계산이 가능하게 만들었습니다.
- 트래픽이 몰리는 시기에도 운영 중 스키마 변경이 가능하도록 온라인 스키마 변경 방식을 적용했습니다.

#### AI Noon - AI Agent 연동 서버

**2025.12 - 2026.02**  
`Node.js` `NestJS` `MongoDB` `Redis` `Python`

- 디바이스와 AI 모델 사이의 실시간 대화 흐름을 연결하는 서버를 개발했습니다.
- STT, LLM, TTS로 이어지는 응답 흐름에서 불필요한 Pub/Sub 구성을 제거하고, REST와 단방향 SSE 기반으로 단순한 통신 구조를 선택했습니다.
- 기능 흐름을 시퀀스 다이어그램으로 정리해 기획, 디바이스, AI 모델 담당자 간 인터페이스 논의를 빠르게 맞췄습니다.

#### MakeON - 외부 파트너 사용자 연동 서버

**2024.12 - 2025.02**  
`Node.js` `NestJS` `MongoDB` `Redis` `Kafka`

- 외부 파트너사의 사용자 라이프사이클 이벤트를 안정적으로 처리하기 위해 Kafka 기반 비동기 파이프라인을 설계했습니다.
- OAuth 계정 연동과 이벤트 동기화 흐름을 분리해, 파트너 시스템의 트래픽 변화가 내부 처리 흐름에 직접 영향을 주지 않도록 했습니다.
- 이벤트 재처리와 상태 동기화를 고려해 데이터 유실 가능성을 낮추는 구조로 구현했습니다.

#### 개발 조직 생산성 개선

**2024.07 - 2026.02**

- AI 코딩 도구를 실무 과제에 적용해 반복 작업, 테스트 코드 작성, 레거시 코드 파악에 미치는 효과를 검증했습니다.
- 검증 결과를 정리해 조직 차원의 도입 필요성을 공유했고, 개발자 대상 도구 구독 예산 확보에 기여했습니다.

### 페이브 / 영우정보서비스

**Backend Engineer**  
2020.12 - 2024.07

#### WECAKE - 세무사 SaaS 플랫폼

**2022.01 - 2024.06**  
`Node.js` `MySQL`

- 세무사가 다수의 고객사를 관리하는 N:M 권한 구조에서 목록 API 응답이 느려지는 문제를 개선했습니다.
- `EXPLAIN`으로 다중 Join 구간의 Full Scan을 확인하고, 조회 조건과 인덱스 구조를 재설계했습니다.
- API 응답 시간을 13초에서 1초대로 줄여, 고객사 목록 조회의 대기 시간과 DB 부하를 낮췄습니다.

#### Data Marketplace Dashboard - 데이터 API 서버

**2021.01 - 2023.11**  
`Python` `FastAPI` `MySQL`

- 이커머스 정제 데이터를 제공하는 분석 리포트 API 서버를 구축했습니다.
- 기존 세션 기반 인증의 확장 한계를 줄이기 위해 JWT 기반 인증 구조로 전환했습니다.
- 데이터 API를 독립 서버로 분리해 리포트 요구사항 변경과 API 확장을 더 쉽게 처리할 수 있도록 했습니다.

### 디케이이노베이션

**Backend Engineer**  
2020.01 - 2020.04

#### 공장 내 이슈 및 일정 관리 시스템

`Python` `Django` `PostgreSQL`

- 제조 현장의 구두/문서 기반 업무 흐름을 분석해 이슈 및 일정 관리 기능으로 전산화했습니다.
- Django 모듈 구조로 공정 관련 데이터를 관리하고, 현장 업무 진행 상태를 추적할 수 있도록 구현했습니다.

### 에스포엔

**Backend Engineer**  
2018.08 - 2019.10

#### 실시간 웹 모니터링 및 위험 감지 시스템

**2019.03 - 2019.09**  
`Java` `Spring` `MongoDB` `PostgreSQL`

- 대용량 로그를 적재하고 통계 데이터를 조회하는 모니터링 서버를 개발했습니다.
- MongoDB와 PostgreSQL을 함께 사용해 원본 로그 저장과 통계성 조회를 분리했습니다.

## Projects

### Fateflow - 사주 분석 서비스

**2026.03 - 현재**  
`Terraform` `GCP` `RDB` `CI/CD`

- GCP 콘솔에서 수동으로 관리하던 인프라를 Terraform 기반 IaC로 구성했습니다.
- 인프라 변경 이력을 코드로 관리하고, 배포 과정에서 발생할 수 있는 설정 누락과 휴먼 에러를 줄였습니다.
- 사주 원국, 대운 등 명리학 도메인을 RDB 구조로 모델링하고 조회 API를 개발했습니다.
- 향후 LLM 기반 문장형 해석을 확장할 수 있도록 도메인 데이터와 해석 생성 흐름을 분리해 설계했습니다.

## Education

- **한국방송통신대학교** 컴퓨터과학과 재학, 2025.01 -
- **동아방송예술대학교** 음향제작과 중퇴, 2010.03 - 2011.12

## Skills

`Node.js` `TypeScript` `NestJS` `Express` `MySQL` `MongoDB` `Redis` `Kafka` `Python` `FastAPI` `Django` `Java` `Spring` `PostgreSQL` `Kubernetes` `AWS` `GCP` `Terraform`

## Original Resume

기존 PDF 이력서는 [docs/김가람_Node.js_백엔드.pdf](docs/%EA%B9%80%EA%B0%80%EB%9E%8C_Node.js_%EB%B0%B1%EC%97%94%EB%93%9C.pdf)에 보관되어 있습니다.
