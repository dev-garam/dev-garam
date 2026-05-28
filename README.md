# 김가람 | Backend Engineer

Node.js/NestJS 기반의 백엔드 개발자입니다.  
지속적으로 누적되는 로그, 이벤트성 트래픽, 복잡한 권한 모델처럼 서비스 운영 중 개선이 필요한 백엔드 영역을 주로 다뤄왔습니다.

- **주요 기술**: Node.js, TypeScript, NestJS, Express, MySQL, MongoDB, Redis, Kafka
- **강점 영역**: DB 성능 개선, 비동기 이벤트 처리, 로그/정산 데이터 처리, 운영 가능한 백엔드 구조 설계
- **경력**: 6년 10개월
- **연락처**: [feelsky665@naver.com](mailto:feelsky665@naver.com)

## Summary

Node.js/NestJS 기반으로 운영 중인 서비스의 성능 개선과 안정적인 API 서버 개발을 해온 백엔드 개발자입니다.

DB 쿼리 병목, 이벤트성 트래픽, 로그성 데이터 누적, 외부 API 연동처럼 운영 과정에서 반복적으로 발생하는 문제를 구조적으로 정리하고 개선해 왔습니다.

서버 개발을 단독으로 맡은 프로젝트에서는 기능 개발, 배포/릴리즈, 장애 원인 추적, Slow Query 점검, DevOps 협업까지 함께 수행했습니다.

AI Agent 기반 개발 도구를 활용해 레거시 코드 파악, 반복 구현, API 변경 영향 범위 확인 등 백엔드 개발 생산성을 높이는 방식에도 익숙합니다.

## Core Strengths

| Area | Experience |
| --- | --- |
| API Server | Node.js, NestJS, Express 기반 백엔드 API 서버 설계 및 개발 |
| DB Performance | MySQL `EXPLAIN` 분석, 인덱스 재설계, MongoDB Sharding |
| Event Processing | Kafka, Redis, 배치 처리를 활용한 비동기 처리와 쓰기 부하 분산 |
| Reliability | 원본 로그 기반 재계산을 고려한 정산 흐름, 운영 중 스키마 변경 |
| AI-assisted Development | AI Agent 기반 개발 도구를 활용한 코드베이스 탐색, 반복 구현, 변경 영향 범위 확인 |

## Experience

### 주식회사 시어스랩

**Backend Engineer**  
2024.07 - 2026.02

#### StepEarth - 글로벌 리워드 플랫폼

**2024.07 - 2025.11**  
`Node.js` `Express` `MySQL` `MongoDB Sharding` `Redis` `Kubernetes`

- 서버 개발을 단독으로 담당하며 기능 개발, 배포/릴리즈, 운영 대응을 함께 진행했습니다.
- 인프라를 담당한 DevOps 개발자와 협업해 운영 중 발생한 API 응답 지연, 신규 배포 이슈, 사용자 요청 패턴을 함께 확인하고 원인을 추적했습니다.
- Managed DB의 Slow Query 조회와 알림 기능을 활용해 지연 가능성이 있는 쿼리를 확인하고, 인덱스/쿼리 개선이 필요한 구간을 운영 중 지속적으로 점검했습니다.
- 신규 반영 기능에서 문제가 확인된 경우 롤백 또는 수정 배포를 진행하고, 재현 테스트 후 운영에 다시 반영했습니다.
- 걸음 로그 저장/조회 구조를 정리하기 위해 MongoDB Sharding을 적용하고, `user_id` 기반 샤딩 키로 지역 쏠림에 따른 hot shard 가능성을 줄였습니다.
- GPS 좌표를 100㎡ 단위 타일로 변환하고, 전주 방문 수 기준의 소유권 확정과 타일 양도 기능을 개발했습니다.
- 다른 사용자가 소유권이 있는 타일을 방문하면 통행세 리워드가 발생하고, 소유자가 캐시박스를 통해 획득할 수 있도록 구현했습니다.
- 월 600만 건 이상 누적되는 이동 이벤트 로그를 기준으로 UTC 02시에 일별 통행세 누적 통계를 계산하는 정산 배치를 구성했습니다.
- 이동 이벤트는 MySQL 이벤트 로그로 저장하고, 캐시박스/통행세 발생 및 획득 내역은 Redis에 캐싱해 사용자 응답 처리와 정산 처리를 분리했습니다.
- 같은 사용자가 같은 타일에 연속 체류할 때는 방문 집계에서 제외하고, 다른 타일 이동 후 재방문해야 다시 집계되도록 처리했습니다.
- 여러 처리가 한 API에 몰려 3초 이상 지연되던 구간을 비동기 처리로 분리해 주요 API 응답 시간을 300ms 이내로 개선했습니다.
- 글로벌 리워드 상품 API와 베트남 오프라인 매장 연동 상품 API를 서버 프록시 형태로 연동해 클라이언트에서 직접 구매/획득 요청을 보내지 않도록 구성했습니다.
- 변경 대상 테이블과 `ALTER` 구문을 직접 작성하고 dev DB에서 검증한 뒤, pt-online-schema-change(pt-osc)를 활용해 운영 MySQL 인덱스/컬럼 변경을 서비스 중단 없이 반영했습니다.

#### AI Noon - AI Agent 연동 서버

**2025.12 - 2026.02**  
`Node.js` `NestJS` `MongoDB` `Redis` `Python`

- 기존 서버 개발자 1명, Agent 개발자 1명으로 진행되던 프로젝트에 후발대로 투입되어 일부 기능 개발과 통신 구조 개선을 담당했습니다.
- STT, LLM, TTS로 이어지는 응답 흐름에서 Pub/Sub 구성을 제거하고, REST와 단방향 SSE 기반 통신 구조로 단순화했습니다.
- 사용자 정보, 성격, 보이스톤을 AI 응답에 반영하는 페르소나 기능을 개발했습니다.
- TMap 기반 도보 내비게이션 기능에서 경로 조회 API 호출을 1회로 제한하고, 이후 이동 판단은 GPS 좌표 계산으로 처리하는 구조를 설계했습니다.
- 현재 좌표 기준 5m 범위의 폴리곤과 목적지 거리 변화를 활용해 경로 이탈 안내 로직을 개발했습니다.

#### MakeON - 외부 파트너 사용자 연동 서버

**2024.12 - 2025.02**  
`Node.js` `NestJS` `MongoDB` `Redis` `Kafka`

- 외부 파트너 계정 연동 영역을 담당했습니다.
- OAuth 기반 로그인과 계정 연동 API를 개발했습니다.
- 파트너 회원 정보 조회, 수정, 탈퇴 기능을 개발했습니다.
- 파트너사에서 회원 탈퇴 이벤트가 발생하면 Kafka로 전달받아 내부 서비스 사용자도 함께 탈퇴 처리되도록 구현했습니다.

### 페이브 / 영우정보서비스

**Backend Engineer**  
2020.12 - 2024.07

#### WECAKE - 세무사 SaaS 플랫폼

**2022.01 - 2024.06**  
`Node.js` `MySQL`

- 개발자 2명이 제품 전반의 기능을 나누어 개발했으며, 백엔드 API 개발과 성능 개선을 담당했습니다.
- 세무사가 관리하는 고객사 목록과 담당 직원 권한을 함께 조회하는 N:M 권한 구조에서 목록 API 응답 지연 문제를 개선했습니다.
- 관리 고객사가 100개 이상인 회사에서 직원 수, 권한, 회사 매핑 정보를 함께 조회할 때 Full Scan이 발생하는 구간을 `EXPLAIN`으로 확인했습니다.
- 회사, 직원, 직원 권한, 관리 회사 매핑 테이블의 Join 조건과 인덱스 구조를 재설계했습니다.
- 고객사 목록 API 응답 시간을 13초에서 1초 이내로 줄여 사용자 대기 시간과 DB 부하를 낮췄습니다.

#### Data Marketplace Dashboard - 데이터 API 서버

**2021.01 - 2023.11**  
`Python` `FastAPI` `MySQL`

- 외부 데이터 기업이 1차 가공한 이커머스 판매 지표, 상품 지표, 광고 이벤트 데이터를 제공하는 분석 리포트 API 서버를 FastAPI 기반으로 구축했습니다.
- 기업 관리자들이 판매, 상품, 광고 클릭/접근/구매 이벤트를 리포트 형태로 확인할 수 있도록 데이터 조회 API를 제공했습니다.
- API 서버 분리에 맞춰 JWT 기반 인증 구조를 적용했습니다.
- 분석 데이터 제공 API를 독립 서버로 분리해 리포트 요구사항 변경과 API 확장을 분리해서 처리할 수 있도록 했습니다.

### Previous Experience

- **디케이이노베이션** Backend Engineer, 2020.01 - 2020.04  
  `Python` `Django` `PostgreSQL`  
  제조 현장의 이슈 및 일정 관리 시스템을 개발했습니다.
- **에스포엔** Backend Engineer, 2018.08 - 2019.10  
  `Java` `Spring` `MongoDB` `PostgreSQL`  
  실시간 웹 모니터링 및 위험 감지 시스템의 로그 적재/통계 조회 기능을 개발했습니다.

## Projects

### Gift Service - 선물하기 서비스/어드민 외주 개발

**2026.02 - 2026.03**  
`Express` `JavaScript` `OAuth` `KG Inicis`

- 선물하기 서비스/어드민 개발 중 소셜 로그인과 결제/환불 콜백 연동을 담당했습니다.
- Apple 로그인 콜백 처리가 필요한 구간은 Express 기반 웹 서버에서 처리했습니다.
- KG이니시스 결제 및 환불 콜백을 Express 웹 서버로 수신해 서비스 주문/결제 흐름과 연결했습니다.

### Fateflow - 사주 분석 서비스

**2026.03 - 현재**  
`NestJS` `TypeScript` `Prisma` `Supabase PostgreSQL` `Redis` `Terraform` `GCP Cloud Run`

- NestJS 기반 API 서버를 구축하고, Prisma migration을 기준으로 Supabase PostgreSQL 스키마를 관리했습니다.
- Google OAuth, JWT 토큰 재발급, 로그아웃, 회원탈퇴 등 인증 API와 Redis 기반 세션/토큰 흐름을 구현했습니다.
- 만세력 프로필, 오늘/월별/연별/10년 주기 운세 조회, 공유 스냅샷 API를 개발했습니다.
- 사주 원국, 대운 등 명리학 도메인을 RDB 구조로 모델링하고, 문장형 해석 기능을 고려해 도메인 데이터와 해석 생성 흐름을 분리했습니다.
- GCP Cloud Run 배포와 Supabase/Redis 인프라를 Terraform 기반 IaC로 구성하고, main 브랜치 기준 CI/CD 흐름을 정리했습니다.

## Education

- **한국방송통신대학교** 컴퓨터과학과 재학, 2025.01 -
- **동아방송예술대학교** 음향제작과 중퇴, 2010.03 - 2011.12

## Skills

`Node.js` `TypeScript` `NestJS` `Express` `MySQL` `PostgreSQL` `MongoDB` `Redis` `Kafka` `Prisma` `Python` `FastAPI` `Kubernetes` `AWS` `GCP` `Terraform`
