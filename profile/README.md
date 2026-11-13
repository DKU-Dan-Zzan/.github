<div align="center">

<img src="./collab-logo.jpg" alt="DANZZAN × NAVER Pay" width="640" />

# 단국 축제, 하나로 즐겨라

**공연 · 부스 · 티켓 · 공지 — 단국대 봄 축제를 위해 직접 만들고, 실제로 운영한 서비스**

<p>
  <img src="./facesign-highlight.svg" alt="대학 최초 네이버페이 페이스사인 도입" width="540" />
  <br />
  <sub>네이버 페이스사인 얼굴 인증 연동 · 티켓 양도·대리 입장 원천 차단</sub>
</p>

**졸업작품 시연 주소** · [https://danzzan.koreacentral.cloudapp.azure.com/](https://danzzan.koreacentral.cloudapp.azure.com/)<br />
**축제 운영 당시 주소** · `https://danfesta2026.yaaksok.com/`<br />
<sub>2026 단국대학교 봄 축제 & 가을 축제 기간 실제 운영 · 축제 서비스 종료</sub>

[**Frontend Repository**](https://github.com/DKU-Dan-Zzan/Danzzan-FE)
&nbsp;·&nbsp;
[**Backend Repository**](https://github.com/DKU-Dan-Zzan/Danzzan-BE)

[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3-6DB33F?style=flat-square&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)](https://kafka.apache.org)
[![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white)](https://redis.io)
[![NHN Cloud](https://img.shields.io/badge/NHN_Cloud-003087?style=flat-square&logo=icloud&logoColor=white)](https://www.nhncloud.com)

</div>

---

## 목차

- [0. 팀소개](#team)
- [1. 개발 배경 & 프로젝트 소개](#overview)
- [2. 시연 영상 및 프로젝트 자료](#project-materials)
- [3. 봄축제 운영 — 주요 서비스 화면](#screens)
- [4. 가을축제 운영 — 기능 확장 및 개선](#autumn-festival)
- [5. 기술 스택](#tech-stack)
- [6. 아키텍처](#architecture)
- [7. 협업 도구 및 기록](#collaboration)
- [8. 봄·가을축제 운영 결과](#results)
- [9. 기대 효과 및 확장 계획](#future-plans)

---

<a name="team"></a>

## 0. 팀소개

<table width="100%">
<thead><tr>
  <th width="128" align="center">이름</th>
  <th width="672">핵심 기여</th>
</tr></thead>
<tbody>
<tr><td align="center"><a href="https://github.com/haneul-dev">강하늘</a></td><td>공지·광고 등록·수정·삭제 API 및 관리자 화면 구현, 배너 노출·공지 상태 표시 보완<br>전화 인증 세션·SMS 앱 연결·검증 화면 구현<br>관리자 개편 시 축제 기본정보·티켓 회차 설정을 한곳에 모으고 입력·저장·편집 제어 연동</td></tr>
<tr><td align="center"><a href="https://github.com/jiwoo1105">박지우</a></td><td>단국대 회원 인증·JWT, Redis·Lua 대기열 및 티켓 발급 화면 연동·예외 처리<br>한영 콘텐츠 번역·다국어 화면, 티켓 회차·배경 설정과 AI 이미지 생성 연동<br>공지·광고 관리 화면 통합, 팔찌 지급·취소 연동, 가을 NHN 공동 배포</td></tr>
<tr><td align="center"><a href="https://github.com/juhee0223">박주희</a></td><td>Redis·Lua 티켓 선점·중복 방지와 부하 검증, 팔찌 지급·통계, 비밀번호 재설정·운영진 권한 관리<br>프론트 API·상태 관리 공통 구조 정비, 인증 세션 및 홈·지도·공지·광고 화면 안정화<br>가을 NHN 공동 배포, Azure VM·DB 이관·이미지 저장소·HTTPS 구성 및 배포</td></tr>
<tr><td align="center"><a href="https://github.com/johaeunn">조하은</a></td><td>홈·공연·타임테이블·부스맵 API와 화면, 지도 좌표·콘텐츠·운영일 관리 구현 및 조회·편집 개선<br>전화번호 인증 세션 생성·문자 수신 검증 API, 앱·티켓 서비스 통합<br>AI 색상·테마 추천 API와 편집·미리보기·저장·활성화 화면 구현</td></tr>
</tbody>
</table>

<details>
<summary><strong>강하늘 — 상세역할 및 PR</strong></summary>

<blockquote>

[haneul-dev](https://github.com/haneul-dev) · 32230120

### 백엔드

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>공지·광고 CRUD API</strong></td><td>일반·긴급 공지와 광고 배너의 관리 API, 이미지 업로드, 등록·수정·삭제 및 활성화 기능 구현.</td></tr>
<tr><td><strong>광고 조회·삭제·캐러셀 응답</strong></td><td>광고 목록·ID별 삭제·공개 캐러셀과 기존 광고 동시 노출 방식 보완.</td></tr>
<tr><td><strong>JWT 필터·CORS 및 운영 API 응답</strong></td><td>공지 관리자 인증과 광고 경로의 JWT 필터·OPTIONS·CORS 처리 보완, 오픈 전 티켓 재고 표시와 주점이 없는 날짜의 빈 목록 응답 수정.</td></tr>
<tr><td><strong>관리자 통합 설정 API</strong></td><td>관리자 설정 개편에 맞춰 학교·축제 이름, 운영 기간, 티켓팅 사용 여부와 회차 설정을 조회·저장하는 API 구현.</td></tr>
<tr><td><strong>회차·이벤트 연동과 편집 제어</strong></td><td>설정 회차를 실제 예매 이벤트와 연결하고 삭제 처리·설정 기반 개폐를 추가.</td></tr>
<tr><td><strong>Object Storage 연동·컨테이너 실행·CI 테스트</strong></td><td>NHN Object Storage 연동, Docker·CI 실행 명령과 테스트 Redis 설정 수정.</td></tr>
</tbody>
</table>

### 프론트엔드

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>공지·광고 관리 화면·API 연동</strong></td><td>일반·긴급 공지 및 광고 배너의 관리자 화면과 API 연동 구현.</td></tr>
<tr><td><strong>배너 슬라이딩·공지 상태 표시</strong></td><td>광고 노출 위치·배너 슬라이딩과 관리자 광고 UI, 공지 상태 아이콘 및 모바일 가로 스크롤 보완.</td></tr>
<tr><td><strong>전화 인증 세션·SMS 딥링크·검증 UI</strong></td><td>회원가입에서 인증 세션 생성 API를 호출하고, 서버가 반환한 수신번호·인증 문구를 표시했습니다.<br>문구 복사와 iOS·Android SMS 딥링크를 연결하고, expiresAt을 기준으로 남은 시간을 표시했습니다.<br>세션 재발급·전화번호 입력 검증, 확인 버튼의 검증 API 호출과 완료 세션 ID 전달을 구현했습니다.</td></tr>
<tr><td><strong>타임테이블·프로필·공연 정보 표시</strong></td><td>타임테이블 재디자인과 상단 배너 표시 조건 수정, 내 정보 프로필 표시 개선, 가을 운영일에 맞춘 타임테이블 및 현재 공연 아티스트명 하드코딩 제거.</td></tr>
<tr><td><strong>PWA·인앱 브라우저</strong></td><td>카카오 인앱 브라우저 전환과 Android 아이콘·스플래시 수정, 이후 커스텀 스플래시 제거.</td></tr>
<tr><td><strong>브랜딩 자산·관리자 설정 화면 통합</strong></td><td>LEGEND 포스터·로고·색상을 반영하고 관리자 콘솔 메뉴를 재구성.<br>축제 이름·운영 기간·티켓 회차 설정을 한곳에 모아 입력·저장 흐름을 연결.</td></tr>
<tr><td><strong>회차·이벤트 연동과 편집 제어</strong></td><td>시작된 회차 편집 제한, 발급된 회차 삭제 확인, 내 정보 상시 개방과 설정 화면 연동.</td></tr>
<tr><td><strong>GitHub Actions·스토리지 업로드·빌드 환경변수</strong></td><td>GitHub Actions 빌드·배포 workflow, NHN 업로드 체크섬 호환성과 지도 환경변수 주입 수정.</td></tr>
</tbody>
</table>

<details>
<summary>강하늘의 PR·커밋 근거</summary>

<blockquote>

**백엔드**

- **공지·광고 CRUD API:** [BE #20](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/20) · [BE #26](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/26)
- **광고 조회·삭제·캐러셀 응답:** [BE #31](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/31) · [BE #33](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/33)
- **JWT 필터·CORS 및 운영 API 응답:** [BE #33](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/33) · [BE #39](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/39) · [BE #73](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/73)
- **관리자 통합 설정 API:** [BE #73](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/73)
- **회차·이벤트 연동과 편집 제어:** [BE #73](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/73)
- **Object Storage 연동·컨테이너 실행·CI 테스트:** [BE #48](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/48) · [BE #51](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/51) · [BE #54](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/54) · [BE #55](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/55) · [BE #56](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/56)

**프론트엔드**

- **공지·광고 관리 화면·API 연동:** [FE #16](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/16) · [FE #19](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/19)
- **배너 슬라이딩·공지 상태 표시:** [FE #27](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/27) · [FE #31](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/31) · [FE #32](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/32) · [FE #60](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/60) · [FE #82](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/82)
- **전화 인증 세션·SMS 딥링크·검증 UI:** [FE #53](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/53)
- **타임테이블·프로필·공연 정보 표시:** [FE #38](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/38) · [FE #46](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/46) · [FE #62](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/62) · [FE #66](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/66) · [FE #105](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/105) · [FE #106](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/106)
- **PWA·인앱 브라우저:** [FE #72](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/72) · [FE #83](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/83) · [FE #87](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/87) · [FE #88](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/88) · [FE #91](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/91)
- **브랜딩 자산·관리자 설정 화면 통합:** [FE #113](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/113) · [FE #119](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/119)
- **회차·이벤트 연동과 편집 제어:** [FE #119](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/119)
- **GitHub Actions·스토리지 업로드·빌드 환경변수:** [FE #74](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/74) · [FE #77](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/77) · [FE #78](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/78)

</blockquote>

</details>

</blockquote>

</details>

<details>
<summary><strong>박지우 — 상세역할 및 PR</strong></summary>

<blockquote>

[jiwoo1105](https://github.com/jiwoo1105) · 32211862

### 백엔드

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>단국대 인증·가입 자격·JWT</strong></td><td>단국대 인증·학생 정보 확인, 회원가입·로그인·JWT 인증 구현.<br>만료 토큰으로 로그인·재발급이 실패하는 문제와 학적·캠퍼스별 가입 조건 보완.</td></tr>
<tr><td><strong>전화 인증 결과·회원가입 토큰 연결</strong></td><td>VERIFIED 세션의 잘못된 만료를 방지하고 인증 성공 시 세션을 사용 완료 처리.<br>인증된 전화번호·시각을 signupToken별 JVM 메모리 캐시에 연결하여 최종 가입에 사용하고, 재인증 시작·가입 완료 시 임시 데이터를 정리.</td></tr>
<tr><td><strong>Redis ZSet·Lua 대기열 상태 전이</strong></td><td>Redis ZSet·Lua 상태머신을 구현하고 입장 자격·만료·재고·순번 경쟁 조건, 자동 오픈과 대기열 이탈 처리 구현.</td></tr>
<tr><td><strong>Micrometer·Prometheus·Grafana 관측 지표</strong></td><td>대기열·발급 지표와 Prometheus·Grafana 연계, k6 시나리오 및 테스트 도구 보완.</td></tr>
<tr><td><strong>공지 조회·수동 번역 보호</strong></td><td>긴급공지 미등록 시 읽기 전용 트랜잭션에서 저장을 호출하던 오류를 수정하고, 일부 영문 수정 시 다른 필드가 사라지거나 이전 영문이 재번역을 덮는 문제 보완.<br>빈 원문으로 누락 번역 처리가 멈추는 조건도 수정.</td></tr>
<tr><td><strong>로그인 세션·재설정 처리</strong></td><td>관리자 refreshToken 응답과 쿠키/본문 전달, 로그인·로그아웃 토큰 버전 캐시를 보완하고 미등록 학번의 비밀번호 재설정 오류 처리 수정.</td></tr>
<tr><td><strong>팔찌 지급 취소 API</strong></td><td>기존 팔찌 지급 흐름에 지급 취소 API 구현.</td></tr>
<tr><td><strong>이미지 업로드·일정 오류 보완</strong></td><td>presign CORS 문제에 대응하는 서버 직접 이미지 업로드 API, NHN 전송·URL 호환 처리와 자정을 넘는 부스·공연 운영시간 로직 보완.</td></tr>
<tr><td><strong>콘텐츠 번역·티켓팅 차단</strong></td><td>DeepL 콘텐츠 번역, 영문 필드·수동 보정·원문 대체·누락 번역 처리와 티켓팅 미운영 API 제어 구현.</td></tr>
<tr><td><strong>티켓 설정 연동·예외 처리</strong></td><td>회차·예매 이벤트 동기화, ON/OFF·배경 설정 저장, 기존 회차 잠금 정책의 서버 검증 연동, 입장 만료·발급 상태·빈 큐 정보 예외 보완.</td></tr>
<tr><td><strong>테마·홈·티켓 배경 통합</strong></td><td>포스터 초점·크롭 추천과 홈 이미지 초안 생성, 테마·티켓 배경·홈 이미지 원자적 적용 및 동시 수정 충돌 방어 구현.</td></tr>
<tr><td><strong>AI 이미지 생성·가입 정보 처리</strong></td><td>포스터 크롭 추천에서 포스터 참고 AI 이미지 생성으로 전환하고 회원가입 네이버 ID 검증·저장 복구.</td></tr>
</tbody>
</table>

### 프론트엔드

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>인증·가입 화면 연동</strong></td><td>회원가입·로그인 API와 화면 연동, 로그인 요청에서 만료 토큰 제외, 가입 자격별 오류 안내 수정.</td></tr>
<tr><td><strong>티켓팅 화면 안정화</strong></td><td>대기열 진입부터 발급까지 API 흐름 통합, 응답 정규화, 새로고침·뒤로가기·토큰 처리, 대기 순번별 적응형 폴링과 조회 간격 조정.</td></tr>
<tr><td><strong>내 정보·내 티켓·공지 재디자인</strong></td><td>각 화면의 레이아웃·표현을 재구성하고 티켓팅 헤더·하단 내비게이션, 공지 URL 자동 링크 처리 및 디자인 요청사항 반영.</td></tr>
<tr><td><strong>공지·광고 운영 화면 통합</strong></td><td>기존 공지와 광고 관리 페이지를 한 화면으로 합치고 기존 광고 경로의 이동 처리, 중복된 티켓 설정 추천 버튼 정리.</td></tr>
<tr><td><strong>세션 유지·재설정·가입 UI 보완</strong></td><td>관리자 토큰 갱신 계약 연동, 비밀번호 재설정 오류코드별 안내, 개인정보 필수 동의·팝업 접근성·비밀번호 보기/불일치 및 가입 완료 UI 개선.</td></tr>
<tr><td><strong>팔찌 조회·지급·취소 API 연동</strong></td><td>팔찌 화면에서 행사별 조회·통계·검색·지급·취소 흐름과 응답 매핑 연동.</td></tr>
<tr><td><strong>이미지 업로드·일정 오류 보완</strong></td><td>이미지 전송을 BE 직접 업로드로 전환하고 부스맵 좌표·시간, 타임테이블 및 축제 DAY 날짜 매핑 수정.</td></tr>
<tr><td><strong>가을 다국어·미운영 안내</strong></td><td>언어 저장소를 useSyncExternalStore로 구독하고 브라우저 언어·저장된 선택을 반영.<br>한영 사전·원문 대체, 영어 GET 요청의 lang=en 및 언어별 Query 캐시 키, 관리자 영문 편집폼을 연결.<br>언어별 티켓팅 미운영 안내·관련 페이지 오류 처리 구현.</td></tr>
<tr><td><strong>티켓 설정 연동·예외 처리</strong></td><td>별도 티켓 설정 화면과 회차·예매 시각·수량·공연일·배경·ON/OFF의 사용자 및 팔찌 화면 연동.<br>기존 잠금 정책 표시, 저장/취소, 비동기 발급 완료 확인·만료 복구·오류 안내 보완.</td></tr>
<tr><td><strong>테마·홈·티켓 배경 통합</strong></td><td>테마 관리 화면에서 색상·가로/세로 배경 추천·홈 이미지 준비·화면 미리보기·전체 적용을 연결.<br>취소·오래된 응답 방어·실패 재시도·배경 대비와 로고 가독성 보완.</td></tr>
<tr><td><strong>AI 이미지 생성·가입 정보 처리</strong></td><td>AI 배경 생성 대기·전체 적용 흐름, 모바일 미운영 안내 배경 밝기와 회원가입 마지막 단계 네이버 ID 입력 복구.</td></tr>
</tbody>
</table>

### 배포

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>배포 구성·검증 보완</strong></td><td>FE Docker·nginx 프록시 구성과 정적 파일 권한 403 수정, NHN 업로드 전송 방식·응답 URL 호환성 보완, 로컬 통합 환경 및 PR 테스트·빌드 CI 구성.</td></tr>
<tr><td><strong>가을축제 배포</strong></td><td>박주희와 함께 NHN 환경 배포 담당.</td></tr>
</tbody>
</table>

<details>
<summary>박지우의 PR·커밋 근거</summary>

<blockquote>

**백엔드**

- **단국대 인증·가입 자격·JWT:** [BE #4](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/4) · [BE #35](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/35) · [BE #36](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/36) · [BE #40](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/40) · [BE #58](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/58) · [BE #62](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/62) · [BE #63](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/63)
- **전화 인증 결과·회원가입 토큰 연결:** [BE #43](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/43)
- **Redis ZSet·Lua 대기열 상태 전이:** [BE #7](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/7) · [BE #9](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/9) · [BE #16](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/16) · [BE #24](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/24) · [BE #30](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/30)
- **Micrometer·Prometheus·Grafana 관측 지표:** [BE #29](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/29)
- **공지 조회·수동 번역 보호:** [BE #69](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/69) · [1e80b00](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/1e80b00) · [bde25fc](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/bde25fc) · [79821d7](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/79821d7)
- **로그인 세션·재설정 처리:** [BE #8](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/8) · [BE #62](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/62)
- **팔찌 지급 취소 API:** [21c013c](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/21c013c)
- **이미지 업로드·일정 오류 보완:** [BE #60](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/60) · [BE #61](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/61)
- **콘텐츠 번역·티켓팅 차단:** [BE #69](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/69)
- **티켓 설정 연동·예외 처리:** [BE #75](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/75)
- **테마·홈·티켓 배경 통합:** [BE #77](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/77)
- **AI 이미지 생성·가입 정보 처리:** [BE #78](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/78) · [c54896e7](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/c54896e7) · [e16c05a5](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/e16c05a5)

**프론트엔드**

- **인증·가입 화면 연동:** [FE #43](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/43) · [FE #52](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/52)
- **티켓팅 화면 안정화:** [FE #7](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/7) · [FE #12](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/12) · [FE #20](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/20) · [FE #26](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/26) · [FE #33](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/33) · [FE #34](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/34) · [FE #67](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/67)
- **내 정보·내 티켓·공지 재디자인:** [FE #39](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/39) · [FE #40](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/40) · [FE #41](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/41) · [FE #44](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/44) · [FE #45](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/45) · [FE #48](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/48) · [FE #54](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/54) · [FE #70](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/70) · [FE #71](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/71) · [FE #97](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/97)
- **공지·광고 운영 화면 통합:** [ec2706d7](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/ec2706d7) · [FE #123](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/123)
- **세션 유지·재설정·가입 UI 보완:** [FE #6](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/6) · [FE #57](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/57) · [FE #58](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/58) · [FE #61](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/61) · [FE #75](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/75)
- **팔찌 조회·지급·취소 API 연동:** [2de6837e](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/2de6837e) · [97905210](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/97905210) · [231464af](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/231464af)
- **이미지 업로드·일정 오류 보완:** [FE #80](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/80) · [FE #81](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/81) · [FE #99](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/99)
- **가을 다국어·미운영 안내:** [FE #109](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/109) · [FE #110](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/110) · [FE #112](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/112)
- **티켓 설정 연동·예외 처리:** [FE #121](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/121)
- **테마·홈·티켓 배경 통합:** [FE #123](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/123)
- **AI 이미지 생성·가입 정보 처리:** [FE #124](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/124) · [d4834848](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/d4834848) · [f989540d](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/f989540d) · [f1e0839d](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/f1e0839d)

**배포**

- **배포 구성·검증 보완:** [FE #109](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/109) · [fbda1b4b](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/fbda1b4b) · [BE #60](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/60) · [BE #69](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/69) · [BE #77](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/77)
- **가을축제 배포:** 팀원 확인 내용에 근거.

</blockquote>

</details>

</blockquote>

</details>

<details>
<summary><strong>박주희 — 상세역할 및 PR</strong></summary>

<blockquote>

[juhee0223](https://github.com/juhee0223) · 32221902

### 백엔드

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>티켓팅·팔찌 지급·통계</strong></td><td>관리자 티켓 검색·팔찌 지급·행사별 발급/수령 통계 API 구현.</td></tr>
<tr><td><strong>팔찌 지급·권리 포기 상태 처리</strong></td><td>탈퇴·권리 포기를 팔찌 지급 차단뿐 아니라 발급/수령 통계·재고·자동 오픈 흐름에 반영.</td></tr>
<tr><td><strong>Redis·Lua 원자적 선점·부하 검증</strong></td><td>Redis 키·상태 계약과 입장/선점 분리, Lua 중복 방지·재고 차감·상태 저장 구현.<br>통합 테스트와 k6 부하 시나리오, 결과 집계 및 판정 도구 작성.</td></tr>
<tr><td><strong>번역 결과 저장·트랜잭션 분리</strong></td><td>영문 컬럼 길이를 확장하고 외부 번역 호출과 DB 저장을 분리.<br>행별 저장으로 한 항목 실패가 전체 롤백·성공 항목 재번역으로 이어지던 흐름을 보완해 반복 호출 문제 수정.</td></tr>
<tr><td><strong>비밀번호 재설정·회원 탈퇴</strong></td><td>학교 이메일로 인증코드를 요청·검증하고 비밀번호를 변경하는 API를 구현했습니다.<br>Redis에 요청 상태와 인증코드·검증 토큰의 해시를 저장하고, 유효기간과 검증 시도 횟수를 관리했습니다.<br>Lua로 검증 토큰을 한 번만 사용할 수 있도록 처리하고 재발송 대기 시간과 요청 횟수를 제한했습니다.<br>비밀번호 변경 시 토큰 버전을 갱신하고, 회원 탈퇴·권리 포기 및 비동기 티켓 발급 중 탈퇴가 겹치는 상황을 처리했습니다.</td></tr>
<tr><td><strong>대기열 순번 응답 보완</strong></td><td>대기열 진입 응답의 순번 처리 보완.</td></tr>
<tr><td><strong>광고 랜딩 연동</strong></td><td>광고 랜딩 URL 필드와 수정 API·검증 추가.</td></tr>
<tr><td><strong>광고 저장·업로드·링크 보완</strong></td><td>광고 ID 수정 API와 업로드 호환 경로, 랜딩 URL 검증 및 테스트 추가.</td></tr>
<tr><td><strong>회원가입 정책·응답 보완</strong></td><td>가입 제한 403 응답 문구 수정, 가을 가입·로그인 API에서 네이버 ID 수집·노출 제거.</td></tr>
<tr><td><strong>관리자 인증·권한 재구성</strong></td><td>관리자 인증을 공통 JWT·tokenVersion으로 통합.<br>운영진 지정·회수·최고관리자 관리와 일반 운영/티켓팅 API 권한, 권한 이력·세션 무효화·마지막 관리자 보호 구현.</td></tr>
<tr><td><strong>테마 선택·홈 이미지·추천 요청 처리</strong></td><td>기본 테마 복구·의미 색상 고정, 홈 이미지 비율 보존 및 독립 저장·충돌 방어, AI 색상 요청 제한·설정 보완.</td></tr>
<tr><td><strong>축제 정보 저장·실행 환경·화면 접근성</strong></td><td>축제 설정의 누락 테이블 생성 SQL, 로컬 Compose 및 전화번호 인증 환경변수 전달 보완.</td></tr>
<tr><td><strong>Azure 이미지·외부 서비스 연동</strong></td><td>Blob 이미지 참조와 응답 URL 경계, 외부 서비스 설정·자동 번역 가드·진단 로직 구현.</td></tr>
</tbody>
</table>

### 프론트엔드

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>티켓팅·팔찌 지급·통계</strong></td><td>티켓팅·관리자 플랫폼, 인증 라우팅·API 연동, 학생 티켓팅 및 팔찌 운영 화면 구현.</td></tr>
<tr><td><strong>팔찌 지급·권리 포기 상태 처리</strong></td><td>팔찌 조회표·상태 배지·지급 확인 모달·안내, 검색 결과 없음과 탈퇴·권리포기 티켓 제외 처리 보완.</td></tr>
<tr><td><strong>대기열 UI 보완</strong></td><td>Waiting Room, 응답 스키마 검사, 지터·오프라인 대응, 진행률 표시 및 상태 복원 처리.</td></tr>
<tr><td><strong>API 계약·서버 상태·디자인 토큰·품질 검사</strong></td><td>기존 기능을 유지하며 API 계약·서버 상태 관리, 폴더·의존성 구조, Tailwind·디자인 토큰과 품질 검사 체계 정비.</td></tr>
<tr><td><strong>홈 캐러셀·헤더·모바일 레이아웃</strong></td><td>기존 홈의 포스터·라인업 캐러셀, 헤더 그라데이션·내비게이션·모바일 비율과 레이아웃 개선, 캐러셀 스와이프·인디케이터·이미지 캐시 갱신·긴급공지 고정 및 로그아웃 확인 흐름 추가.</td></tr>
<tr><td><strong>지도 조회·선택 상태·타임테이블 스크롤</strong></td><td>기존 지도 필터·조회 상태를 Query/selector로 정리하고 접근성·탭 사전 로딩·지도 영역 계산 및 관리자 편집/사이드바 구조 보완.<br>타임테이블의 중첩 스크롤·좌우 스와이프·자동 스크롤·시간 정렬·종료 미정 표시 개선.</td></tr>
<tr><td><strong>공지 조회·관리 안정화</strong></td><td>공지 목록·상세와 관리자 조회를 TanStack Query 훅으로 분리하고 검색어·페이지·상태별 캐시를 구성.<br>검색 debounce·로딩·오류·재시도와 모달 포커스 처리를 구현하고 폼·업로드 액션·응답 계약 검증·긴급공지 payload를 화면 코드에서 분리.</td></tr>
<tr><td><strong>GA4 이벤트·앱 아이콘·공유 메타데이터</strong></td><td>GA4 page_view 전송 복구와 언어 선택·영어 사용 추적, 앱 아이콘 캐시 갱신, OG 이미지·카카오톡 공유 썸네일 비율 및 호환성 수정.</td></tr>
<tr><td><strong>비밀번호 재설정·회원 탈퇴</strong></td><td>학교 이메일로 인증코드를 요청·검증하고 비밀번호를 변경하는 API를 구현했습니다.<br>Redis에 요청 상태와 인증코드·검증 토큰의 해시를 저장하고, 유효기간과 검증 시도 횟수를 관리했습니다.<br>Lua로 검증 토큰을 한 번만 사용할 수 있도록 처리하고 재발송 대기 시간과 요청 횟수를 제한했습니다.<br>비밀번호 변경 시 토큰 버전을 갱신하고, 회원 탈퇴·권리 포기 및 비동기 티켓 발급 중 탈퇴가 겹치는 상황을 처리했습니다.</td></tr>
<tr><td><strong>인증 세션·재발급·대기열 복원</strong></td><td>JWT 역할·만료 판독과 관리자 접근 제어, 같은 키의 동시 토큰 재발급 요청을 Promise로 공유하는 로직 구현.<br>401 재발급·재시도와 403/만료를 구분하고 복귀 URL 검증·대기열 복원 조회를 처리.<br>이전 세션 응답 차단·재발급 토큰 보존·계정별 티켓 캐시 분리.</td></tr>
<tr><td><strong>공지·광고 상태 관리·링크 연동</strong></td><td>공지·광고 Query·API 계약과 UI 처리 정비, 광고 배치·개인정보 안내 및 클릭 랜딩 연동.</td></tr>
<tr><td><strong>광고 저장·업로드·링크 보완</strong></td><td>광고 gateway·업로드 응답 검사·관리 훅, 저장 중/실패 표시·수정 액션·URL 입력 및 외부 이동, 공통 광고 슬롯·이미지 규격 개선.</td></tr>
<tr><td><strong>동의·가입 오류·전화 인증·운영 안내</strong></td><td>개인정보·티켓팅 동의 흐름과 문구, 가입 제한 오류·전화번호 인증 안내·종료 시각 미정 표시 보완.<br>가을 네이버 ID 입력·내 정보 노출 및 관련 정책 제거.</td></tr>
<tr><td><strong>관리자 인증·권한 재구성</strong></td><td>운영진 검색·지정·회수·승격/강등 화면, 권한별 메뉴·직접 URL·설정 저장, 세션 동기화·이전 응답 방어와 계정 식별에 따른 조작 제한 구현.</td></tr>
<tr><td><strong>테마 선택·홈 이미지·추천 요청 처리</strong></td><td>기본·5월 프리셋과 테마 선택, 상태·지도 색상 고정, 홈 전체 비율·세로 미리보기·독립 저장 UI 구현.<br>내 정보 배경 분리와 AI 추천 브라우저·프록시 대기 시간 보완.</td></tr>
<tr><td><strong>축제 정보 저장·실행 환경·화면 접근성</strong></td><td>권한별 기본정보/티켓 설정 저장과 부분 실패·재시도 처리.<br>모바일 safe-area·하단 내비 점유 높이·iOS 상태바·manifest 및 접근성 정비.</td></tr>
<tr><td><strong>Azure 이미지 연동</strong></td><td>이미지 SAS 갱신과 관리자·광고·사용자 화면 연동.</td></tr>
</tbody>
</table>

### 배포

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>Azure VM·Docker·DB 이관·HTTPS</strong></td><td>VM·Docker·DB 이관, HTTPS·CORS·외부 서비스 구성, 운영·진단·복구 문서 작성.</td></tr>
<tr><td><strong>가을 NHN 배포</strong></td><td>박지우와 함께 가을축제 NHN 환경 배포 담당.</td></tr>
<tr><td><strong>Azure 배포</strong></td><td>Azure 환경 배포 담당.</td></tr>
</tbody>
</table>

<details>
<summary>박주희의 PR·커밋 근거</summary>

<blockquote>

**백엔드**

- **티켓팅·팔찌 지급·통계:** [fa99dd5](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/fa99dd5) · [2d46922](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/2d46922)
- **팔찌 지급·권리 포기 상태 처리:** [BE #46](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/46) · [b8d3aac](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/b8d3aac) · [fe98948](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/fe98948)
- **Redis·Lua 원자적 선점·부하 검증:** [23f0ff9](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/23f0ff9) · [ad55384](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/ad55384) · [569e409](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/569e409) · [d82e073](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/d82e073)
- **번역 결과 저장·트랜잭션 분리:** [BE #70](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/70)
- **비밀번호 재설정·회원 탈퇴:** [BE #6](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/6) · [BE #11](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/11) · [BE #46](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/46)
- **대기열 순번 응답 보완:** [e3d34d6](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/e3d34d6)
- **광고 랜딩 연동:** [BE #50](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/50)
- **광고 저장·업로드·링크 보완:** [BE #27](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/27) · [BE #50](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/50) · [03264a7](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/03264a7)
- **회원가입 정책·응답 보완:** [BE #59](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/59) · [BE #65](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/65)
- **관리자 인증·권한 재구성:** [BE #27](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/27) · [BE #74](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/74)
- **테마 선택·홈 이미지·추천 요청 처리:** [BE #78](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/78)
- **축제 정보 저장·실행 환경·화면 접근성:** [BE #18](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/18) · [BE #65](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/65) · [BE #73](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/73) · [3e56856](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/3e56856)
- **Azure 이미지·외부 서비스 연동:** [BE #78](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/78)

**프론트엔드**

- **티켓팅·팔찌 지급·통계:** [32716ad9](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/32716ad9) · [d00eb76f](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/d00eb76f)
- **팔찌 지급·권리 포기 상태 처리:** [FE #13](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/13) · [FE #22](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/22) · [FE #68](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/68)
- **대기열 UI 보완:** [5c430437](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/5c430437) · [d720a31e](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/d720a31e) · [0965f033](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/0965f033)
- **API 계약·서버 상태·디자인 토큰·품질 검사:** [FE #22](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/22) · [FE #28](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/28)
- **홈 캐러셀·헤더·모바일 레이아웃:** [FE #37](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/37) · [FE #49](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/49) · [FE #51](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/51) · [FE #55](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/55)
- **지도 조회·선택 상태·타임테이블 스크롤:** [FE #22](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/22) · [FE #28](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/28) · [FE #94](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/94) · [FE #95](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/95) · [FE #96](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/96) · [125cca98](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/125cca98)
- **공지 조회·관리 안정화:** [FE #22](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/22) · [FE #28](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/28) · [9f132ff0](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/9f132ff0) · [49dd6c63](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/49dd6c63)
- **GA4 이벤트·앱 아이콘·공유 메타데이터:** [FE #84](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/84) · [FE #85](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/85) · [FE #86](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/86) · [FE #89](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/89) · [FE #115](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/115) · [FE #116](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/116) · [FE #117](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/117) · [2f2416e2](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/2f2416e2)
- **비밀번호 재설정·회원 탈퇴:** [FE #5](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/5) · [FE #68](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/68)
- **인증 세션·재발급·대기열 복원:** [FE #22](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/22) · [FE #68](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/68) · [FE #120](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/120) · [e9e4c1cb](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/e9e4c1cb) · [0ccbc1e5](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/0ccbc1e5)
- **공지·광고 상태 관리·링크 연동:** [FE #22](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/22) · [FE #56](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/56) · [FE #73](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/73)
- **광고 저장·업로드·링크 보완:** [FE #22](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/22) · [FE #56](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/56) · [FE #73](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/73) · [533abe06](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/533abe06)
- **동의·가입 오류·전화 인증·운영 안내:** [FE #8](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/8) · [FE #59](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/59) · [FE #63](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/63) · [FE #65](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/65) · [FE #79](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/79) · [FE #84](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/84) · [FE #90](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/90) · [FE #94](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/94) · [FE #95](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/95) · [FE #104](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/104)
- **관리자 인증·권한 재구성:** [FE #120](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/120)
- **테마 선택·홈 이미지·추천 요청 처리:** [FE #124](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/124)
- **축제 정보 저장·실행 환경·화면 접근성:** [FE #8](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/8) · [FE #22](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/22) · [FE #120](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/120)
- **Azure 이미지 연동:** [FE #124](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/124)

**배포**

- **Azure VM·Docker·DB 이관·HTTPS:** [FE #124](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/124) · [BE #78](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/78)
- **가을 NHN 배포:** 팀원 확인 내용에 근거.
- **Azure 배포:** 팀원 확인 내용에 근거.

</blockquote>

</details>

</blockquote>

</details>

<details>
<summary><strong>조하은 — 상세역할 및 PR</strong></summary>

<blockquote>

[johaeunn](https://github.com/johaeunn) · 32234364

### 백엔드

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>홈·공연·부스맵</strong></td><td>홈 포스터·라인업·현재 공연·타임테이블, 부스·주점 조회·날짜/단과대 필터·상세·운영시간 API 구현.</td></tr>
<tr><td><strong>쉼터 데이터 확장</strong></td><td>부스 타입에 쉼터를 추가하고 조회 API에 반영.</td></tr>
<tr><td><strong>관리자 지도·콘텐츠 확장</strong></td><td>지도 좌표와 부스·주점·공연·아티스트 CRUD, 이미지 업로드·순서, 날짜별 운영 정보 및 주점 노출 관리 API 구현.</td></tr>
<tr><td><strong>가을 운영일 구조 정비</strong></td><td>부스·주점 운영일 모델과 관리 API, 미배치 부스 생성·운영일 변경 구조 보완.</td></tr>
<tr><td><strong>지도·콘텐츠 조회 안정화</strong></td><td>조회 N+1, 대표 이미지 누락·순서, 날짜 필터·주점 노출일 중복 제약과 운영 데이터 처리 보완.</td></tr>
<tr><td><strong>타임테이블 공개 여부·공연 표시</strong></td><td>타임테이블 표시 설정 분리 및 미사용 분실물 기능 제거.</td></tr>
<tr><td><strong>긴급공지 조회 보완</strong></td><td>홈 긴급공지 조회 기준·미등록 응답 정리.</td></tr>
<tr><td><strong>전화번호 인증</strong></td><td>OCTOMO를 이용한 전화번호 점유 인증의 세션 생성·검증·상태 조회 API를 구현했습니다.<br>세션을 MySQL에 저장하고 인증코드 암호화, 유효기간과 검증 시도 횟수를 관리했습니다.<br>사용자가 인증 문구를 수신번호로 전송하면 외부 문자 수신 확인 API로 전화번호·문자 조합을 검증하여 회원가입에 연결했습니다.</td></tr>
<tr><td><strong>서비스 통합</strong></td><td>분리된 App-BE·Ticket-BE를 단일 서비스로 통합.</td></tr>
<tr><td><strong>AI 테마 추천·팔레트 검증·이미지 관리</strong></td><td>테마 저장·활성화, 포스터·로고·홈 이미지 관리, 색상 분석·AI 시안 추천 API 구현.<br>추천 안정성·팔레트 검증/보정, 저장소 추상화·업로드 용량 정책·SQL 마이그레이션 보완.</td></tr>
</tbody>
</table>

### 프론트엔드

<table width="100%">
<thead><tr>
  <th width="240">기능</th>
  <th width="560">상세 기여</th>
</tr></thead>
<tbody>
<tr><td><strong>홈·공연·부스맵</strong></td><td>홈 포스터·라인업·현재 공연·타임테이블, 지도·날짜/단과대 필터·부스/주점 상세·운영시간 화면 구현.</td></tr>
<tr><td><strong>부스맵 재디자인·예외 개선</strong></td><td>지도·마커·상세 패널 재디자인, 편의시설·쉼터와 선택·노출 동작·부스 데이터 처리 보완.<br>지도 표시를 단순화하며 3D 기능 제거.</td></tr>
<tr><td><strong>관리자 지도·콘텐츠 확장</strong></td><td>지도 좌표 편집, 부스·주점·공연·아티스트 관리 및 이미지 업로드·날짜별 운영 정보·주점 노출 관리 화면 구현.</td></tr>
<tr><td><strong>가을 운영일 구조 정비</strong></td><td>관리자 날짜 선택과 새 주점·부스 입력, 운영 정보 관리 흐름 통합·개선.</td></tr>
<tr><td><strong>지도·콘텐츠 조회 안정화</strong></td><td>조회 응답 순서·썸네일 대체·선택/확대·바텀시트 동작 및 미배치 부스·운영일 편집 UX 개선.</td></tr>
<tr><td><strong>타임테이블 공개 여부·공연 표시</strong></td><td>공개 전 안내·관리자 토글, 날짜별 표시와 현재 공연 종료 시각 예외 처리 보완.</td></tr>
<tr><td><strong>팔찌 날짜·쉼터 문구 보완</strong></td><td>팔찌 배부 화면 날짜 매핑과 쉼터 한영 문구 추가.</td></tr>
<tr><td><strong>인증 화면·저장 정책·광고 동작</strong></td><td>로그인·회원가입·비밀번호 재설정 배치와 학번 단계 저장 정책, 공지 상세 여백 개선.<br>광고 자동 전환·정지, 배너 폭·오버레이 위치 수정.</td></tr>
<tr><td><strong>앱 통합·GA4 이벤트 수집</strong></td><td>기존 앱·티켓 코드·라우팅 통합, GA4 연동과 빌드 환경변수·페이지뷰 수집 보완.</td></tr>
<tr><td><strong>AI 테마 추천·팔레트 검증·이미지 관리</strong></td><td>앱 구동 시 활성 테마를 조회하고 ThemeData의 HEX 색상을 검증하여 문서 루트 CSS 변수에 적용.<br>기본 테마 대체, 테마 편집·추천 시안 비교·저장·활성화·사용자 화면 미리보기와 포스터·로고·홈 이미지 관리 구현.<br>추천 요청과 기준색 동기화, 미리보기 로고·업로드 UX 개선.</td></tr>
</tbody>
</table>

<details>
<summary>조하은의 PR·커밋 근거</summary>

<blockquote>

**백엔드**

- **홈·공연·부스맵:** [BE #3](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/3) · [BE #5](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/5) · [BE #12](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/12) · [BE #19](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/19)
- **쉼터 데이터 확장:** [BE #72](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/72)
- **관리자 지도·콘텐츠 확장:** [BE #25](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/25) · [BE #28](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/28) · [BE #47](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/47) · [BE #64](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/64)
- **가을 운영일 구조 정비:** [BE #67](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/67)
- **지도·콘텐츠 조회 안정화:** [BE #13](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/13) · [BE #47](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/47) · [BE #64](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/64) · [BE #67](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/67)
- **타임테이블 공개 여부·공연 표시:** [BE #42](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/42)
- **긴급공지 조회 보완:** [BE #3](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/3) · [BE #13](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/13) · [0f7c0fc](https://github.com/DKU-Dan-Zzan/Danzzan-BE/commit/0f7c0fc)
- **전화번호 인증:** [BE #38](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/38)
- **서비스 통합:** [BE #1](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/1)
- **AI 테마 추천·팔레트 검증·이미지 관리:** [BE #76](https://github.com/DKU-Dan-Zzan/Danzzan-BE/pull/76)

**프론트엔드**

- **홈·공연·부스맵:** [FE #3](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/3) · [FE #4](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/4) · [FE #10](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/10) · [FE #14](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/14) · [FE #17](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/17)
- **부스맵 재디자인·예외 개선:** [FE #23](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/23) · [FE #29](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/29) · [FE #42](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/42) · [FE #76](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/76) · [FE #92](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/92) · [FE #93](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/93) · [FE #98](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/98) · [FE #118](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/118) · [a7a969b3](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/a7a969b3)
- **관리자 지도·콘텐츠 확장:** [FE #21](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/21) · [FE #69](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/69) · [FE #102](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/102)
- **가을 운영일 구조 정비:** [FE #107](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/107)
- **지도·콘텐츠 조회 안정화:** [FE #69](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/69) · [FE #92](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/92) · [FE #93](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/93) · [FE #98](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/98) · [FE #102](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/102) · [FE #107](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/107)
- **타임테이블 공개 여부·공연 표시:** [FE #64](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/64) · [FE #103](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/103)
- **팔찌 날짜·쉼터 문구 보완:** [FE #100](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/100) · [FE #118](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/118)
- **인증 화면·저장 정책·광고 동작:** [FE #47](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/47) · [FE #50](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/50) · [FE #76](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/76)
- **앱 통합·GA4 이벤트 수집:** [5aa5ee94](https://github.com/DKU-Dan-Zzan/Danzzan-FE/commit/5aa5ee94) · [FE #100](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/100) · [FE #101](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/101)
- **AI 테마 추천·팔레트 검증·이미지 관리:** [FE #122](https://github.com/DKU-Dan-Zzan/Danzzan-FE/pull/122)

</blockquote>

</details>

</blockquote>

</details>

---

<a name="overview"></a>

## 1. 개발 배경 & 프로젝트 소개

공지는 인스타그램, 티켓은 오픈카톡, 부스 위치는 에브리타임 — 축제 정보는 늘 여러 채널에 흩어져 있었습니다.

기존 축제 앱들도 공지나 타임테이블 정도는 제공했지만, **공지부터 티켓팅까지 하나의 서비스에서 함께 처리하는 경우는 없었습니다.**
예매는 여전히 오픈카톡이나 외부 링크로 빠져나갔고, 운영진은 엑셀·구글폼으로 예매 내역을 따로 관리해야 했습니다.

학생들은 채널을 옮겨 다니다 티켓 링크를 놓쳤고, 운영진은 같은 내용을 여러 곳에 반복 게시하면서 DM·댓글로 개별 문의까지 대응해야 했습니다.
예매 내역과 실수령 현황이 실시간으로 맞지 않아 현장에서 혼선도 잦았습니다.

DANZZAN에서는 학생들이 공연 일정과 부스 위치를 확인하고, 티켓을 예매·조회하며, 공지사항까지 한 번에 확인할 수 있습니다.
운영진은 관리자 페이지에서 축제 콘텐츠를 관리하고, 예매 내역과 팔찌 배부 현황을 확인하며 현장 수령 처리를 진행할 수 있습니다.

여기에 **네이버페이와의 협업**이 더해졌습니다.
네이버 페이스사인(얼굴 인증)을 입장 시 신원 확인에 연동해, 티켓 양도나 대리 입장을 구조적으로 차단했습니다. 실제로 비윤리적 양도·도용 사례는 0%에 수렴했습니다.

2026년 5월 봄축제에서 실제 운영한 뒤, 같은 해 9월 가을축제에 맞춰 서비스를 개선해 다시 운영했습니다.
한국어·영어 전환과 콘텐츠 번역 기능을 추가해 축제 정보를 영어로도 확인할 수 있도록 했으며, 가을축제 고유의 로고·포스터와 브랜딩을 화면에 반영했습니다.

총학생회와 직접 미팅하며 요구사항을 수집하고, 하나의 앱으로 해결했습니다.

**공연, 부스, 티켓, 공지 전부 한 앱에서.**

---

<a name="project-materials"></a>

## 2. 시연 영상 및 프로젝트 자료

### 2.1 졸업작품 시연 영상

<p align="center">
  <a href="https://youtu.be/SN-cncHBgns">
    <img src="https://img.youtube.com/vi/SN-cncHBgns/maxresdefault.jpg" alt="DANZZAN 졸업작품 시연 영상" width="640" />
  </a>
</p>

[▶ 졸업작품 시연 영상 보기](https://youtu.be/SN-cncHBgns)

---

### 2.2 소스 코드 및 개발 문서

<table width="100%">
<thead><tr>
  <th width="240">자료</th>
  <th width="560">링크</th>
</tr></thead>
<tbody>
<tr><td>프론트엔드 소스 코드·실행 안내</td><td><a href="https://github.com/DKU-Dan-Zzan/Danzzan-FE">Danzzan-FE</a></td></tr>
<tr><td>백엔드 소스 코드</td><td><a href="https://github.com/DKU-Dan-Zzan/Danzzan-BE">Danzzan-BE</a></td></tr>
<tr><td>프론트엔드 구조·개발 가이드</td><td><a href="https://github.com/DKU-Dan-Zzan/Danzzan-FE/tree/main/docs/architecture">개발 문서</a></td></tr>
<tr><td>티켓팅 부하 테스트·검증</td><td><a href="https://github.com/DKU-Dan-Zzan/Danzzan-BE/blob/main/docs/load-test-report.md">검증 보고서</a> · <a href="https://github.com/DKU-Dan-Zzan/Danzzan-BE/blob/main/docs/ticket-queue-load-test-runbook.md">실행 가이드</a></td></tr>
</tbody>
</table>

---

### 2.3 기획·설계 자료

<table width="100%">
<thead>
<tr>
  <th width="128" nowrap>자료</th>
  <th width="192">개요</th>
  <th width="352">미리보기</th>
  <th width="128" nowrap>파일</th>
</tr>
</thead>
<tbody>
<tr><td nowrap><strong>와이어프레임</strong></td><td>타임테이블·부스맵·관리자 화면의 초기 스케치와 화면 이동 흐름</td><td align="center" nowrap><a href="./docs/wireframes.pdf"><img src="./docs/previews/wireframes.png" alt="타임테이블 화면과 이동 흐름 스케치" width="170" /></a>&nbsp;<a href="./docs/wireframes.pdf"><img src="./docs/previews/wireframes-boothmap.png" alt="부스맵 조회·상세 화면 스케치" width="170" /></a><br>타임테이블 · 부스맵</td><td align="center" nowrap><a href="./docs/wireframes.pdf"><img src="./docs/buttons/pdf.svg" alt="PDF 열기" width="112" height="34" /></a></td></tr>
<tr><td nowrap><strong>설계 보고서</strong></td><td>기능 요구사항·사용자 흐름·화면 설계<br>데이터베이스·API·시스템 구성</td><td align="center" nowrap><a href="./docs/design-report.pdf"><img src="./docs/previews/design-report-requirements.png" alt="설계 보고서의 사용자 기능 요구사항 표" width="170" /></a>&nbsp;<a href="./docs/design-report.pdf"><img src="./docs/previews/design-report.png" alt="홈·타임테이블 와이어프레임과 구현 화면 비교" width="170" /></a><br>기능 요구사항 · 화면 설계·구현 비교</td><td align="center" nowrap><a href="./docs/design-report.pdf"><img src="./docs/buttons/pdf.svg" alt="PDF 열기" width="112" height="34" /></a></td></tr>
<tr><td nowrap><strong>기획 발표</strong></td><td>프로젝트 배경·문제 정의·차별성<br>서비스 구조·주요 기능·개발 계획</td><td align="center" nowrap><a href="./docs/planning-presentation.pdf"><img src="./docs/previews/planning-presentation.png" alt="사용자·웹 서비스·백엔드·관리자 서비스 구조도" width="170" /></a>&nbsp;<a href="./docs/planning-presentation.pdf"><img src="./docs/previews/planning-presentation-features.png" alt="홈·타임테이블·부스맵·공지사항 주요 화면" width="170" /></a><br>서비스 구조 · 주요 기능</td><td align="center" nowrap><a href="./docs/planning-presentation.pdf"><img src="./docs/buttons/pdf.svg" alt="PDF 열기" width="112" height="34" /></a></td></tr>
</tbody>
</table>

---

### 2.4 프로젝트 결과보고서 및 포스터

<table width="100%">
<thead>
<tr>
  <th width="128" nowrap>자료</th>
  <th width="192">개요</th>
  <th width="352">미리보기</th>
  <th width="128" nowrap>파일</th>
</tr>
</thead>
<tbody>
<tr><td nowrap><strong>프로젝트<br>결과보고서</strong></td><td>기획·설계·구현 과정과 테스트·운영 결과를 정리한 최종 보고서</td><td align="center" nowrap><a href="./docs/final-report.pdf"><img src="./docs/previews/final-report.png" alt="프로젝트 결과보고서 표지" width="170" /></a>&nbsp;<a href="./docs/final-report.pdf"><img src="./docs/previews/final-report-implementation.png" alt="결과보고서의 사용자 서비스 구현 화면과 티켓팅 처리 흐름" width="170" /></a><br>보고서 표지 · 주요 구현 화면</td><td align="center" nowrap><a href="./docs/final-report.pdf"><img src="./docs/buttons/pdf.svg" alt="PDF 열기" width="112" height="34" /></a></td></tr>
<tr><td nowrap><strong>졸업작품<br>포스터</strong></td><td>서비스 구성·주요 기능·아키텍처·운영 성과 요약</td><td align="center"><a href="./docs/poster.pdf"><img src="./docs/previews/poster.png" alt="DANZZAN 졸업작품 포스터 전체 미리보기" width="170" /></a><br>프로젝트 포스터</td><td align="center" nowrap><a href="./docs/poster.pdf"><img src="./docs/buttons/pdf.svg" alt="PDF 열기" width="112" height="34" /></a><br><a href="./docs/poster.png"><img src="./docs/buttons/image.svg" alt="이미지 열기" width="112" height="34" /></a></td></tr>
</tbody>
</table>

---

<a name="screens"></a>

## 3. 봄축제 운영 — 주요 서비스 화면

> 봄축제 운영 버전의 화면입니다. 가을축제에서 추가·개선한 화면은 다음 섹션에서 소개합니다.

### 3.1 사용자 화면

#### 3.1.1 주요 기능

<table width="100%">
<thead><tr>
  <th width="266" align="center">홈</th>
  <th width="266" align="center">타임테이블</th>
  <th width="266" align="center">부스맵</th>
</tr></thead>
<tbody>
<tr><td align="center"><img src="./screenshots/user/home.png" width="230"></td><td align="center"><img src="./screenshots/user/timetable.png" width="230"></td><td align="center"><img src="./screenshots/user/boothmap.png" width="230"></td></tr>
</tbody>
</table>

<table width="100%">
<thead><tr>
  <th width="266" align="center">티켓팅 대기열</th>
  <th width="266" align="center">내 티켓</th>
  <th width="266" align="center">공지사항</th>
</tr></thead>
<tbody>
<tr><td align="center"><img src="./screenshots/user/ticketing-queue.png" width="230"></td><td align="center"><img src="./screenshots/user/my-ticket.png" width="230"></td><td align="center"><img src="./screenshots/user/notice.png" width="230"></td></tr>
</tbody>
</table>

#### 3.1.2 회원가입

<table width="100%">
<thead><tr>
  <th width="266" align="center">1단계</th>
  <th width="266" align="center">2단계</th>
  <th width="266" align="center">3단계</th>
</tr></thead>
<tbody>
<tr><td align="center"><img src="./screenshots/user/signup1.png" width="230"></td><td align="center"><img src="./screenshots/user/signup2.png" width="230"></td><td align="center"><img src="./screenshots/user/signup3.png" width="230"></td></tr>
</tbody>
</table>

---

### 3.2 관리자 화면

<table width="100%">
<thead><tr>
  <th width="266" align="center">공지 관리</th>
  <th width="266" align="center">광고 등록</th>
  <th width="266" align="center">팔찌 배부</th>
</tr></thead>
<tbody>
<tr><td align="center"><img src="./screenshots/admin/notice.png" width="350"></td><td align="center"><img src="./screenshots/admin/advertisement.png" width="350"></td><td align="center"><img src="./screenshots/admin/wristband.png" width="350"></td></tr>
</tbody>
</table>

---

<a name="autumn-festival"></a>

## 4. 가을축제 운영 — 기능 확장 및 개선

봄축제 운영 이후, 가을축제의 분위기를 담은 화면과 영어로 축제 정보를 확인할 수 있는 기능을 더해 서비스를 다시 운영했습니다.

### 4.1 가을축제 고유 브랜딩 반영

가을축제 **LEGEND**의 로고와 포스터를 서비스에 반영했습니다. 홈 화면뿐 아니라 타임테이블에서도 축제의 시각적 정체성이 이어지도록 구성했습니다.

<table width="100%">
<thead><tr>
  <th width="266" align="center">봄축제 홈</th>
  <th width="266" align="center">가을축제 홈</th>
  <th width="266" align="center">가을축제 타임테이블</th>
</tr></thead>
<tbody>
<tr><td align="center"><img src="./screenshots/user/home.png" alt="기존 봄축제 홈 화면" width="230" /></td><td align="center"><img src="https://github.com/user-attachments/assets/89c7688c-1b72-4960-be86-b6ee16e5d7c4" alt="LEGEND 브랜딩을 반영한 가을축제 홈 화면" width="250" /></td><td align="center"><img src="https://github.com/user-attachments/assets/b2a582a1-a249-447b-be31-845f289f02e5" alt="가을축제 타임테이블 화면" width="260" /></td></tr>
<tr><td align="center">봄축제 운영 버전</td><td align="center">가을축제 로고·포스터 반영</td><td align="center">주요 화면에 브랜딩 적용</td></tr>
</tbody>
</table>

---

### 4.2 한국어·영어 전환 및 관리자 번역 관리

<table width="100%">
<tr><td colspan="2" valign="top">
<p>사용자는 한국어·영어로 축제 정보를 확인하고, 운영진은 자동 번역된 내용을 확인·수정합니다.</p><table width="100%"><tr><th width="240">구분</th><th width="560">구현 내용</th></tr><tr><td><strong>UI 언어 전환</strong></td><td>한국어·영어 문자열 사전을 분리해 선택한 언어의 문구 표시</td></tr><tr><td><strong>콘텐츠 번역</strong></td><td>DeepL을 연동해 운영 콘텐츠의 한국어 텍스트를 영어로 번역</td></tr><tr><td><strong>운영진 수정</strong></td><td>관리자가 영문 내용을 직접 입력하거나 보정할 수 있도록 지원</td></tr><tr><td><strong>번역 누락 대응</strong></td><td>영문이 없는 항목은 한국어 원문을 표시</td></tr><tr><td><strong>수동 번역 보호</strong></td><td>관리자가 직접 수정한 영문은 자동 번역으로 덮어쓰지 않도록 처리</td></tr></table>
</td></tr>
<tr><th width="400">한국어</th><th width="400">영어</th></tr>
<tr><td align="center"><a href="https://github.com/user-attachments/assets/e3576ab8-2327-47a9-a5cd-e7652c4c1c60"><img alt="가을축제 공지 상세 한국어 화면" src="https://github.com/user-attachments/assets/e3576ab8-2327-47a9-a5cd-e7652c4c1c60" width="280"/></a><br/><sub>사용자 화면</sub></td><td align="center"><a href="https://github.com/user-attachments/assets/04af38cb-3413-403d-8e7c-0d402c92e3de"><img alt="동일한 가을축제 공지 상세 영어 화면" src="https://github.com/user-attachments/assets/04af38cb-3413-403d-8e7c-0d402c92e3de" width="280"/></a><br/><sub>사용자 화면</sub></td></tr>
<tr><td align="center"><a href="https://github.com/user-attachments/assets/f34e37c8-f589-47b5-b911-e459c68a7611"><img alt="관리자 페이지의 한국어 콘텐츠 입력란" src="https://github.com/user-attachments/assets/f34e37c8-f589-47b5-b911-e459c68a7611" width="280"/></a><br/><sub>관리자 화면</sub></td><td align="center"><a href="https://github.com/user-attachments/assets/c2ef91c2-d3bb-498a-ace3-037c127f274b"><img alt="번역 결과가 자동으로 채워진 영어 입력란" src="https://github.com/user-attachments/assets/c2ef91c2-d3bb-498a-ace3-037c127f274b" width="280"/></a><br/><sub>관리자 화면</sub></td></tr>
</table>

---

### 4.3 축제 운영 방식에 따른 티켓팅·회원가입 안내

가을축제는 공연 규모를 고려한 총학생회의 요청에 따라 티켓팅을 진행하지 않았습니다. 이에 티켓팅과 회원가입 화면에 각각 안내 문구를 표시할 수 있도록 구현했습니다. 안내는 사용자가 선택한 언어에 따라 한국어 또는 영어로 제공됩니다.

<table width="100%">
<thead><tr>
  <th width="200" align="center">티켓팅 안내 · 한국어</th>
  <th width="200" align="center">티켓팅 안내 · 영어</th>
  <th width="200" align="center">회원가입 안내 · 한국어</th>
  <th width="200" align="center">회원가입 안내 · 영어</th>
</tr></thead>
<tbody>
<tr><td align="center"><img src="https://github.com/user-attachments/assets/e27425b1-b006-43af-823b-18ed1b40ec3a" alt="가을축제 티켓팅 미운영 안내 한국어 화면" width="180" /></td><td align="center"><img src="https://github.com/user-attachments/assets/400df540-c9cb-4cb5-84f9-35ec0cc944df" alt="가을축제 티켓팅 미운영 안내 영어 화면" width="180" /></td><td align="center"><img src="https://github.com/user-attachments/assets/0029a7dc-ef80-4a8d-a430-a23a439e52c7" alt="가을축제 회원가입 안내 한국어 화면" width="180" /></td><td align="center"><img src="https://github.com/user-attachments/assets/cb7e1801-2503-44b0-adbc-2d1619b4e532" alt="가을축제 회원가입 안내 영어 화면" width="180" /></td></tr>
</tbody>
</table>

---

### 4.4 축제 기본정보와 티켓 운영 설정

<table width="100%">
<tr><td colspan="2" valign="top">
<p>하반기에는 축제마다 바뀌는 운영 정보와 화면 구성을 관리자가 직접 설정할 수 있도록 기능을 확장했습니다. 축제 이름·운영 기간·로고·포스터를 관리하고, 공연일별 티켓 회차와 예매 시작 시각·발급 수량을 설정할 수 있습니다.</p>
<table width="100%"><tr><th width="240">기능</th><th width="560">구현 내용</th></tr><tr><td><strong>축제 기본정보</strong></td><td>축제 이름·운영 기간·브랜딩 이미지와 홈 대표 이미지 관리</td></tr><tr><td><strong>티켓 운영 설정</strong></td><td>티켓팅 ON/OFF, 회차별 공연일·예매 시작 시각·발급 수량 설정</td></tr><tr><td><strong>일정 연동</strong></td><td>사용자 티켓 목록과 관리자 팔찌 배부 화면에 동일한 회차 정보 반영</td></tr><tr><td><strong>변경 보호</strong></td><td>시작된 회차의 주요 정보 수정 제한, 발급 티켓이 있는 회차 삭제 시 영향 안내</td></tr><tr><td><strong>안내 화면 관리</strong></td><td>티켓팅 미운영 안내와 발급 티켓의 배경 이미지 설정·미리보기·기본값 복원</td></tr></table>
<p>티켓팅을 끄더라도 기존 회차와 발급 기록을 보존하며, 로그인·회원가입 등 계정 기능과 신규 예매 허용 여부를 분리했습니다.</p>
</td></tr>
<tr>
<td width="50%" align="center" valign="top">
<a href="./screenshots/admin/features/01-festival-settings.jpg"><img alt="축제 기본정보" src="./screenshots/admin/features/01-festival-settings.jpg" width="440"/></a>
</td>
<td width="50%" align="center" valign="top">
<a href="./screenshots/admin/features/03-ticket-edit-full.jpg"><img alt="티켓 회차 설정" src="./screenshots/admin/features/03-ticket-edit-full.jpg" width="440"/></a>
</td>
</tr>
</table>

---

### 4.5 운영진 지정 및 권한 관리

<table width="100%">
<tr><td colspan="1" valign="top">
<p>최고 관리자가 가입된 사용자를 조회해 운영진으로 지정하고 권한을 부여·회수할 수 있도록 구현했습니다. 일반 운영 관리와 티켓팅 관리 권한을 분리해 담당 업무에 필요한 메뉴를 이용하도록 구성했습니다.</p>
<table width="100%"><tr><th width="240">권한</th><th width="560">관리 범위</th></tr><tr><td><strong>일반 운영</strong></td><td>축제 기본정보·테마·공지·광고·부스맵·타임테이블·번역</td></tr><tr><td><strong>티켓팅 운영</strong></td><td>티켓 설정·회차·발급 및 취소·팔찌 배부·통계</td></tr><tr><td><strong>최고 관리자</strong></td><td>전체 운영 기능과 운영진 권한 지정·회수, 최고 관리자 승격·강등</td></tr></table>
<p>화면의 메뉴 노출뿐 아니라 서버에서도 권한을 확인하고, 권한 변경 이력과 기존 세션의 무효화를 함께 처리합니다. 마지막 최고 관리자나 자기 자신의 권한을 잘못 회수하는 상황도 제한했습니다.</p>
</td></tr>
<tr>
<td width="100%" align="center" valign="top">
<a href="./screenshots/admin/features/staff-permissions.png"><img alt="운영진 역할별 권한과 매니저 목록 관리 화면" src="./screenshots/admin/features/staff-permissions.png" width="720"/></a>
</td>
</tr>
</table>

---

### 4.6 포스터 기반 AI 테마 및 배경 추천

<table width="100%">
<tr><td colspan="2" valign="top">
<p>축제 포스터와 로고를 등록한 뒤 대표색을 추출하고, 이를 바탕으로 AI가 추천한 색상 시안을 선택할 수 있도록 구현했습니다. 관리자는 홈·티켓·안내 화면의 미리보기를 확인하고 선택한 테마와 배경을 함께 적용할 수 있습니다.</p>
<table width="100%"><tr><th width="240">단계</th><th width="560">기능</th></tr><tr><td><strong>이미지 준비</strong></td><td>공식 포스터·로고 등록, 기존 이미지 또는 포스터를 활용한 홈 대표 이미지 준비</td></tr><tr><td><strong>테마 추천</strong></td><td>포스터 대표색 추출, 기준색 선택, 색상 시안 추천 및 팔레트 보정</td></tr><tr><td><strong>배경 추천</strong></td><td>포스터에서 화면 용도에 맞는 가로·세로 영역을 추천하고 포스터를 잘라 배경 이미지 구성</td></tr><tr><td><strong>미리보기</strong></td><td>사용자 화면에 적용될 테마, 티켓 카드, 티켓팅 안내, 내 정보 화면 확인</td></tr><tr><td><strong>전체 적용</strong></td><td>선택한 테마·배경·홈 이미지 초안을 함께 반영하고, 충돌·실패 시 부분 적용 방지</td></tr></table>
<p>배경 추천은 등록한 포스터를 분석·가공하는 흐름입니다. 배경 이미지가 없거나 로딩에 실패하면 공식 포스터·기본 이미지로 대체하며, 화면 배경에 맞춰 로고와 글자의 가독성을 조정했습니다.</p>
</td></tr>
<tr>
<td width="50%" align="center" valign="top">
<a href="./screenshots/admin/features/03-select-palette.jpg"><img alt="AI 테마 추천" src="./screenshots/admin/features/03-select-palette.jpg" width="440"/></a>
</td>
<td width="50%" align="center" valign="top">
<a href="./screenshots/admin/features/04-review-apply.jpg"><img alt="미리보기와 적용" src="./screenshots/admin/features/04-review-apply.jpg" width="440"/></a>
</td>
</tr>
</table>

---

### 4.7 공지·광고 통합 관리

<table width="100%">
<tr><td colspan="1" valign="top">
<p>관리자가 긴급 공지, 일반 공지, 광고 배너를 한 페이지에서 관리할 수 있도록 화면을 통합했습니다. 한영 콘텐츠 확인·수정과 배너 관리를 같은 운영 흐름에서 처리할 수 있습니다.</p>
</td></tr>
<tr>
<td width="100%" align="center" valign="top">
<a href="./screenshots/admin/features/13-notice-ad-unified.jpg"><img alt="공지·광고 통합 관리" src="./screenshots/admin/features/13-notice-ad-unified.jpg" width="720"/></a>
</td>
</tr>
</table>

하반기 기능의 화면과 구현 기록: [티켓 설정](https://github.com/DKU-Dan-Zzan/Danzzan-FE/blob/01be4bedad63a321d13943724e06d45a124ba97e/docs/pr/danz-368/README.md) · [운영진 권한 관리](https://github.com/DKU-Dan-Zzan/Danzzan-BE/blob/e5517ed2c89d1bb824aaf6e95d0448f8ea118729/docs/admin-staff-management.md) · [AI 테마·배경 및 통합 관리 화면](https://github.com/DKU-Dan-Zzan/Danzzan-FE/blob/01be4bedad63a321d13943724e06d45a124ba97e/docs/pr/DANZ-374/README.md).

---

<a name="tech-stack"></a>

## 5. 기술 스택

### 5.1 Frontend

![React](https://img.shields.io/badge/React_18-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript_5-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![TanStack Query](https://img.shields.io/badge/TanStack_Query-FF4154?style=for-the-badge&logo=reactquery&logoColor=white)

---

### 5.2 Backend

![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL_8-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-FF4438?style=for-the-badge&logo=redis&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

---

### 5.3 Infra

![NHN Cloud](https://img.shields.io/badge/NHN_Cloud-003087?style=for-the-badge&logo=icloud&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![k6](https://img.shields.io/badge/k6-7D64FF?style=for-the-badge&logo=k6&logoColor=white)

---

<a name="architecture"></a>

## 6. 아키텍처

### 6.1 시스템 아키텍처

<img src="./architecture/system-architecture.png" alt="System Architecture" width="800">

---

### 6.2 서비스 아키텍처

<img src="./architecture/service-architecture.png" alt="Service Architecture" width="800">

오픈 순간 수천 명(최대 10000명까지 테스트)이 동시에 들어오는 상황을 고려해서 설계했습니다.

---

---

<a name="collaboration"></a>

## 7. 협업 도구 및 기록

<table width="100%">
<thead><tr>
  <th width="240">도구</th>
  <th width="560">활용 방식</th>
</tr></thead>
<tbody>
<tr><td><strong>Jira</strong></td><td>기능별 작업을 이슈로 나누고 담당자·우선순위·일정을 관리.<br>스프린트 보드에서 해야 할 일·진행 중·검토 중·완료 상태를 공유.</td></tr>
<tr><td><strong>Notion</strong></td><td>요구사항·화면 기획·일정·참고 자료를 정리.<br>주간 회의, 총학생회 미팅, 기술 자문 및 스프린트 회고를 회의록으로 기록.</td></tr>
<tr><td><strong>Slack</strong></td><td>개발 이슈, 일정 변경, 배포·테스트 결과를 채널별로 공유.</td></tr>
<tr><td><strong>GitHub</strong></td><td>기능 단위 브랜치와 PR을 통해 코드 변경 사항을 공유하고 검토.</td></tr>
</tbody>
</table>

### 7.1 Jira — 스프린트 및 작업 관리

기능별 작업을 이슈로 등록하고 스프린트 보드에서 담당자와 진행 상태를 확인했습니다.

<p align="center">
  <a href="./screenshots/collaboration/jira-sprint-board.png">
    <img src="./screenshots/collaboration/jira-sprint-board.png" alt="Jira 스프린트 보드: 해야 할 일·진행 중·검토 중·완료 상태별 작업 관리" width="800" />
  </a>
</p>

---

### 7.2 Notion — 회의록 및 의사결정 기록

회의 유형·날짜·스프린트별로 회의록을 정리했습니다.<br>
요구사항 조정, 와이어프레임·ERD·API 논의, 총학생회 미팅과 기술 자문 내용을 함께 기록했습니다.

<p align="center">
  <a href="./screenshots/collaboration/notion-meeting-notes.png">
    <img src="./screenshots/collaboration/notion-meeting-notes.png" alt="Notion 회의록: 주간 회의·요구사항 논의·총학생회 미팅·기술 자문·스프린트 회고 기록" width="720" />
  </a>
</p>

<sub>이미지를 클릭하면 원본 크기로 볼 수 있습니다. 출처: 설계 보고서 30–31쪽.</sub>

[설계 보고서 PDF 보기](./docs/design-report.pdf)

---

<a name="results"></a>

## 8. 봄·가을축제 운영 결과

### 8.1 티켓팅 운영 지표

> 2026년 5월 7일 티켓팅 오픈 기준 실측 데이터

<table width="100%">
<thead><tr>
  <th width="240"></th>
  <th width="560"></th>
</tr></thead>
<tbody>
<tr><td>동시 접속자</td><td><strong>4,500명</strong></td></tr>
<tr><td>티켓 소진 시간</td><td><strong>1분 만에 3,500장 전량 매진</strong></td></tr>
<tr><td>중복 발급 / 순번 오류</td><td><strong>ZERO</strong></td></tr>
<tr><td>CPU 사용률</td><td><strong>약 40%</strong> (16vCPU, 64GB 기준)</td></tr>
<tr><td>queue_enter 평균 응답속도</td><td><strong>498ms</strong></td></tr>
<tr><td>서버 Overflow</td><td><strong>0건</strong></td></tr>
</tbody>
</table>

**트래픽 현황**

<img src="./architecture/traffic.png" alt="Traffic" width="800">

---

### 8.2 사용자 데이터

<table width="100%">
<tr>
<td width="50%" align="center" valign="middle">
<a href="./architecture/spring-autumn-views.png"><img alt="봄·가을축제 핵심 기능별 조회수 비교" src="./architecture/spring-autumn-views.png" width="440"/></a>
</td>
<td width="50%" valign="middle">
<p>봄축제와 가을축제의 핵심 기능별 조회수입니다. 막대는 두 축제의 조회수를 누적해 표시했습니다.</p>
<table width="100%"><tr><th>기능</th><th>봄 축제</th><th>가을 축제</th><th>합계</th></tr><tr><td>타임테이블</td><td>8,146회</td><td>1,893회</td><td>10,039회</td></tr><tr><td>티켓 예매</td><td>7,356회</td><td>0회</td><td>7,356회</td></tr><tr><td>내 티켓</td><td>5,997회</td><td>0회</td><td>5,997회</td></tr><tr><td>부스맵</td><td>4,303회</td><td>1,555회</td><td>5,858회</td></tr><tr><td>공지사항</td><td>3,528회</td><td>1,249회</td><td>4,777회</td></tr></table>
<p>가을축제는 티켓팅을 운영하지 않아 티켓 예매·내 티켓 조회수가 0회입니다.</p>
<p>봄축제 기간(5/10–5/14) 총 누적 이벤트 수(클릭·스크롤 등): <strong>82,000+</strong></p>
</td>
</tr>
</table>

---

### 8.3 사용자 피드백

<table width="100%">
<thead><tr>
  <th width="400" align="center"></th>
  <th width="400" align="center"></th>
</tr></thead>
<tbody>
<tr><td align="center"><img src="./architecture/feedback1.png" width="380"></td><td align="center"><img src="./architecture/feedback2.png" width="380"></td></tr>
<tr><td align="center"><img src="./architecture/feedback3.png" width="380"></td><td align="center"><img src="./architecture/feedback4.png" width="380"></td></tr>
</tbody>
</table>

---

<a name="future-plans"></a>

## 9. 기대 효과 및 확장 계획

### 9.1 기대 효과

<table width="100%">
<thead><tr>
  <th width="240" align="center"></th>
  <th width="560"></th>
</tr></thead>
<tbody>
<tr><td align="center"><strong>운영진 업무 효율화</strong></td><td>티켓 발급, 팔찌 수령, 공지 수정 등 반복 업무를 단일 플랫폼에서 처리. 채널별 중복 게시와 개별 문의 대응 부담 감소</td></tr>
<tr><td align="center"><strong>암표·양도 원천 차단</strong></td><td>네이버 페이스사인 얼굴 인증으로 입장 시 신원 재확인. 대리 입장과 티켓 양도를 구조적으로 차단</td></tr>
<tr><td align="center"><strong>사용자 편의성 향상</strong></td><td>공연 정보, 예매, 부스 위치, 공지를 하나의 앱에서 제공. 채널을 옮겨 다니지 않아도 됨</td></tr>
</tbody>
</table>

---

### 9.2 확장 계획

<table width="100%">
<thead><tr>
  <th width="240" align="center"></th>
  <th width="560"></th>
</tr></thead>
<tbody>
<tr><td align="center"><strong>챗봇 / RAG 도입</strong></td><td>공지, 위치, 티켓 수령 방법 등 자주 묻는 질문을 AI가 자동 응답. 운영진 문의 대응 부담 추가 감소</td></tr>
<tr><td align="center"><strong>네이버 페이스사인 정식 API 연동</strong></td><td>현장 확인 시간 단축 및 외부인 접근 제한 강화</td></tr>
<tr><td align="center"><strong>교내 행사 전반으로 확장</strong></td><td>체육대회, 학과 행사, 동아리 박람회 등으로 적용 범위 확대. 단국대 축제를 시작으로 지속적으로 보완해 교내 행사 전반에 사용 가능한 플랫폼으로 발전</td></tr>
</tbody>
</table>
