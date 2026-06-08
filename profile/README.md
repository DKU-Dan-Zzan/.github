<div align="center">

<img src="https://raw.githubusercontent.com/DKU-Dan-Zzan/Danzzan-FE/main/public/%EB%8B%A8%EC%A7%A5%EB%A7%88%ED%81%AC.png" alt="DANZZAN Logo" width="300" />

<br />
<br />

# DANZZAN

### 단국 축제, 하나로 즐겨라

**Dankook Festival, All in One Bite**

<br />

[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3-6DB33F?style=flat-square&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)](https://kafka.apache.org)
[![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white)](https://redis.io)
[![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://www.mysql.com)
[![NHN Cloud](https://img.shields.io/badge/NHN_Cloud-003087?style=flat-square&logo=icloud&logoColor=white)](https://www.nhncloud.com)

<br />

> 단국대학교 봄 축제에 **실제 배포·운영**된 올인원 축제 웹앱 플랫폼

</div>

---

## 📌 프로젝트 소개

공연·부스·티켓 정보가 인스타그램, 에브리타임, 오픈카톡 등 여러 채널에 분산되는 문제를 해결하기 위해
총학생회와 직접 협업하여 개발한 단국대학교 축제 올인원 플랫폼입니다.

---

## ✨ 주요 기능

| 기능 | 설명 |
|---|---|
| **홈** | 공연 라인업 캐러셀, 메인 포스터, 긴급 공지 |
| **부스맵** | 캠퍼스 지도 기반 부스 위치, 단과대·날짜 필터 |
| **타임테이블** | 공연·행사 일정 시각화 |
| **티켓팅** | Redis 대기열 + Kafka 기반 선착순 예매, QR 입장 검증 |
| **공지** | 일반 공지 및 긴급 공지 분리 제공 |
| **마이페이지** | 내 티켓 조회, 회원 정보 관리 |
| **관리자 페이지** | 티켓 발급 현황, 부스·공연 정보 실시간 관리 |

---

## 🛠 기술 스택

### Frontend
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7-646CFF?style=flat-square&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![TanStack Query](https://img.shields.io/badge/TanStack_Query-FF4154?style=flat-square&logo=reactquery&logoColor=white)

### Backend
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?style=flat-square&logo=mysql&logoColor=white)

### Infrastructure
![NHN Cloud](https://img.shields.io/badge/NHN_Cloud-003087?style=flat-square&logo=icloud&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)

---

## 🏗 티켓팅 아키텍처

동시접속 8,000명을 안정적으로 처리하기 위한 구조

```
사용자 요청
    ↓
Redis 대기열 진입
    ↓
Lua Script 원자적 선착순 처리
    ↓
Kafka 비동기 티켓 발급 (Outbox Pattern)
    ↓
실패 시 보상 트랜잭션 자동 처리
```

---

## 📦 레포지토리

| 레포 | 설명 |
|---|---|
| [Danzzan-FE](https://github.com/DKU-Dan-Zzan/Danzzan-FE) | 프론트엔드 (React + TypeScript) |
| [Danzzan-BE](https://github.com/DKU-Dan-Zzan/Danzzan-BE) | 백엔드 (Spring Boot) |
| [Danzzan-Ticket-BE](https://github.com/DKU-Dan-Zzan/Danzzan-Ticket-BE) | 티켓팅 전용 서버 |

---

<div align="center">

**단국대학교 컴퓨터공학과 캡스톤디자인 2026**

*Dankook Festival, All in One Bite*

</div>
