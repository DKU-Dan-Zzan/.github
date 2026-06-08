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

## 시연 영상

<!-- 유튜브 업로드 후 링크 교체 -->
[![시연 영상](https://img.shields.io/badge/YouTube-시연영상_보기-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtube.com/링크를_여기에)

---

## 서비스 화면

<!-- 스크린샷 추가 후 주석 해제 -->
<!--
| 홈 | 타임테이블 | 부스맵 |
|:---:|:---:|:---:|
| ![home](./screenshots/home.png) | ![timetable](./screenshots/timetable.png) | ![boothmap](./screenshots/boothmap.png) |

| 티켓팅 | 내 티켓 | 관리자 |
|:---:|:---:|:---:|
| ![ticketing](./screenshots/ticketing.png) | ![myticket](./screenshots/myticket.png) | ![admin](./screenshots/admin.png) |
-->

---

## 시스템 아키텍처

<!-- 이미지 추가 후 주석 해제 -->
<!--
![system-architecture](./architecture/system-architecture.png)
-->

---

## 서비스 아키텍처 (티켓팅)

<!-- 이미지 추가 후 주석 해제 -->
<!--
![service-architecture](./architecture/service-architecture.png)
-->

오픈 순간 수천 명이 동시에 들어오는 상황을 고려해서 설계했습니다.

```
요청 → Redis 대기열 → Lua Script로 선착순 처리 → Kafka로 티켓 발급
                                                  → 실패하면 자동 보상
```

---

## 실제 운영 결과

> 2026년 5월 7일 티켓팅 오픈 기준 실측 데이터

| | |
|---|---|
| 동시 접속자 | **4,500명** |
| 티켓 소진 시간 | **1분 만에 3,500장 전량 매진** |
| 중복 발급 / 순번 오류 | **ZERO** |
| CPU 사용률 | **약 40%** (16vCPU, 64GB 기준) |
| queue_enter 평균 응답속도 | **498ms** |
| 서버 Overflow | **0건** |

---

## 사용자 피드백

> *"서버가 안 터짐! 수강신청 서버보다 좋은듯 ㅎ"*

> *"앱 자체는 예전에도 있었던 적은 있는데 이번에는 부스나 편의시설 위치, 타임테이블 같이 축제 때 필요한 거 다 넣어놨더라"*

> *"비윤리적인 상황 (양도 및 도용)의 상황을 0%에 수렴할 정도로 큰 도움을 받았음"*

> *"정보를 한 눈에 볼 수 있다는 점이 접근성 측면과 이용측면 관리 측면에서 편리"*

---

## 기술 스택

**Frontend** — React 18, TypeScript, Vite, Tailwind CSS, TanStack Query

**Backend** — Spring Boot 3, Kafka, Redis, MySQL, Prometheus / Grafana

**Infra** — NHN Cloud, Docker, RDS HA, EasyCache

---

## 레포지토리

| | |
|---|---|
| [Danzzan-FE](https://github.com/DKU-Dan-Zzan/Danzzan-FE) | 프론트엔드 |
| [Danzzan-BE](https://github.com/DKU-Dan-Zzan/Danzzan-BE) | 백엔드 |
| [Danzzan-Ticket-BE](https://github.com/DKU-Dan-Zzan/Danzzan-Ticket-BE) | 티켓팅 서버 |

---

## 팀

| 이름 | 학번 | 역할 |
|:---:|:---:|---|
| 강하늘 | 32230120 | 팀장 · 관리자 페이지(광고/공지) 개발 (Full-stack) |
| 박주희 | 32221902 | 티켓팅 대기열 시스템, 팔찌 배부 관리 플랫폼, 회원 탈퇴·비밀번호 재설정 개발 (Full-stack) |
| 박지우 | 32211862 | JWT 기반 회원 인증, 로그인·회원가입, Redis 대기열 티켓 예매 시스템 개발 (Full-stack) |
| 조하은 | 32234364 | 축제 메인 포털(홈/부스맵/타임테이블) 개발 (Full-stack) |

---

<div align="center">
단국대학교 컴퓨터공학과 캡스톤디자인 2026
</div>
