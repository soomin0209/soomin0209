<p align='center'> <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=FFA07A&height=200&section=header&text=Soomin%20Kim&fontColor=ffffff&fontSize=70&animation=fadeIn&fontAlignY=38"/> </p>

단순 기능 구현보다 **실시간 처리와 성능 최적화**에 관심을 가진 백엔드 개발자입니다. <br>
Redis 기반 실시간 채팅·알림 시스템, 동시성 제어, 조회 성능 개선을 경험했으며 **문제 원인을 분석하고 수치 기반으로 개선**하는 개발 방식을 지향합니다.

<br>

## 🛠️ Tech Stack

| 분류 | 기술 |
|---|---|
| **Language** | ![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white) |
| **Backend** | ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white) ![JPA](https://img.shields.io/badge/JPA-59666C?style=flat-square&logo=hibernate&logoColor=white) ![QueryDSL](https://img.shields.io/badge/QueryDSL-0769AD?style=flat-square) ![Spring AI](https://img.shields.io/badge/Spring_AI-6DB33F?style=flat-square&logo=spring&logoColor=white) |
| **Database** | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) |
| **Real-time** | ![WebSocket](https://img.shields.io/badge/WebSocket(STOMP)-010101?style=flat-square&logo=socketdotio&logoColor=white) ![SSE](https://img.shields.io/badge/SSE-FF6F00?style=flat-square) ![Redis Pub/Sub](https://img.shields.io/badge/Redis_Pub/Sub-DC382D?style=flat-square&logo=redis&logoColor=white) |
| **Infra / DevOps** | ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) |
| **Test / Monitoring** | ![k6](https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white) ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white) |
| **Frontend (학습 중)** | ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) |

<br>

## 🚀 Projects
 
### 🔨 기가찰 — 중고 물품 역경매 플랫폼
`2026.04 ~ 2026.05` · `4인 팀` · `내일배움캠프 최종 프로젝트` · [GitHub](https://github.com/GigaMak2)
 
실시간 채팅·알림과 AI 챗봇을 제공하는 역경매 서비스로, Redis Pub/Sub 기반 다중 인스턴스 실시간 처리와 성능 최적화에 집중했습니다.
 
**담당** 인증/인가, 사용자, 카테고리, 리뷰, 실시간 채팅·알림
 
- **Virtual Thread로 SSE 알림 서버 처리량 개선**: DB 커넥션 대기로 플랫폼 스레드가 고갈되는 문제를 Java 21 가상 스레드로 해결. <br> k6 부하 테스트 500 VUs 기준 RPS **4,398 → 5,831 (약 33%↑)**
- **다중 인스턴스 실시간 채팅**: Redis Pub/Sub 브로드캐스트 구조 설계, STOMP CONNECT 단계 JWT 인증, <br> `@TransactionalEventListener(afterCommit)`로 DB 저장과 메시지 발행 간 정합성 보장
- **카테고리 트리 Redis 캐싱**: Cache Evict로 정합성 유지, 응답 속도 **352ms → 7ms (약 50배)**
- **AI Tool Calling 안정화**: Spring AI 기본 temperature로 인한 Tool 미호출·허위 시세 생성 문제를 원인 분석 후 개선
- **비용 효율 인프라**: I/O 중심 서비스 특성을 고려해 ARM 기반, 메모리 중심 ECS Fargate 구성

<br>

### 🍷 The One Bottle Shop — 주류 커머스 플랫폼
`2026.03` · `5인 팀` · `내일배움캠프 팀 프로젝트` · [GitHub](https://github.com/TheOne-team-1/TheOne-Bottle-Shop)
 
동시성 제어와 조회 성능 최적화에 집중한 커머스 백엔드 서비스입니다.
 
**담당** 상품·포인트·즐겨찾기 도메인, 동시성 제어, 조회 성능 최적화
 
- **락 전략 비교를 통한 재고 정합성 확보**: 비관적 락 / 낙관적 락 / Lettuce 스핀락 / Redisson 분산락 4종 비교 검증. 재고 차감 실패율 **85% → 0%**
- **측정 기반 기술 선택**: 비관적 락(186ms)이 Redisson(567ms)보다 빨라 단일 DB 환경에서 채택, DB 병목 시 분산락 전환 기준 정리
- **실행 계획 기반 인덱스 튜닝**: `EXPLAIN ANALYZE`로 분석해 정렬 컬럼 선행 인덱스 적용. Full Table Scan·filesort 제거, <br> 응답 **0.342ms → 0.0556ms (약 6배)**

<br>

## 📚 Experience & Education
 
| 기간 | 내용 |
|---|---|
| 2026.08 ~ 2026.09 | **(주)소울웨어** 백엔드 개발 인턴 · Spring Boot 자유게시판 개발 |
| 2025.11 ~ 2026.05 | **내일배움캠프** Spring 백엔드 개발 트랙 (팀스파르타) |
| 2021.03 ~ 2025.02 (졸업) | **강원대학교** 소프트웨어미디어융합전공 |
 
**자격증** 정보처리기사 (2025.09) · SQLD (2025.09) · ADsP (2025.06)
