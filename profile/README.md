<div align="center">

<img src="./logo.png" alt="DANZZAN" width="280" />

<br /><br />

**단국대 봄 축제를 위해 직접 만들고, 실제로 운영한 서비스입니다.**

<br />

[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3-6DB33F?style=flat-square&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)](https://kafka.apache.org)
[![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white)](https://redis.io)
[![NHN Cloud](https://img.shields.io/badge/NHN_Cloud-003087?style=flat-square&logo=icloud&logoColor=white)](https://www.nhncloud.com)

</div>

---

## 어떤 서비스인가요?

총학생회와 직접 미팅하면서 만든 단국대 축제 앱입니다.

기존에는 공연 정보는 인스타그램, 티켓은 오픈카톡, 부스 위치는 에브리타임에 올라오다 보니
학생들이 이리저리 찾아다녀야 했고 운영진도 같은 내용을 여러 곳에 올려야 했습니다.

그래서 만들었습니다. 공연, 부스, 티켓, 공지 전부 한 앱에서.

---

## 뭘 만들었나요?

| | |
|---|---|
| 홈 | 공연 라인업, 포스터, 긴급 공지 |
| 부스맵 | 캠퍼스 지도에서 부스 위치 확인, 단과대·날짜 필터 |
| 타임테이블 | 공연 일정 한눈에 |
| 티켓팅 | 선착순 예매 + QR 입장 검증 |
| 관리자 페이지 | 총학이 직접 티켓·부스·공연 관리 |

---

## 티켓팅은 어떻게 만들었나요?

오픈 순간 수천 명이 동시에 들어오는 상황을 고려해서 설계했습니다.

```
요청 → Redis 대기열 → Lua Script로 선착순 처리 → Kafka로 티켓 발급
                                                  → 실패하면 자동 보상
```

k6로 5,000 / 8,000 / 10,000명 동시접속 시나리오를 직접 테스트했습니다.

---

## 기술 스택

**Frontend** — React 18, TypeScript, Vite, Tailwind CSS, TanStack Query

**Backend** — Spring Boot 3, Kafka, Redis, MySQL

**Infra** — NHN Cloud, Docker, Prometheus, Grafana

---

## 레포지토리

| | |
|---|---|
| [Danzzan-FE](https://github.com/DKU-Dan-Zzan/Danzzan-FE) | 프론트엔드 |
| [Danzzan-BE](https://github.com/DKU-Dan-Zzan/Danzzan-BE) | 백엔드 |
| [Danzzan-Ticket-BE](https://github.com/DKU-Dan-Zzan/Danzzan-Ticket-BE) | 티켓팅 서버 |

---

<div align="center">
단국대학교 컴퓨터공학과 캡스톤디자인 2026
</div>
