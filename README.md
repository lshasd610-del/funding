# 크라우드 펀딩 플랫폼

## 프로젝트 소개
Spring Boot 기반 크라우드 펀딩 서비스로 프로젝트 생성, 상태 전이, 후원 흐름을 도메인 중심으로 설계했습니다.

---

## 기술 스택
- Java
- Spring Boot
- JPA (Hibernate)
- MySQL
- Redis

---

## 담당 역할
- Project 도메인 구현
- 프로젝트 생성 / 수정 / 삭제 기능 구현
- 상태 전이 로직 설계
- ProjectStatusPolicy 설계 및 적용
- 프로젝트 상태 로그 기록 기능 구현
- 조회 API 구현

---

## 주요 기능
- 프로젝트 생성 / 수정 / 삭제
- 프로젝트 상태 관리 (DRAFT, REVIEW_REQUESTED, APPROVED, FUNDING 등)
- 상태 전이 정책 기반 검증
- 프로젝트 조회 (목록 / 상세)

---

## 트러블슈팅

### LazyInitializationException 발생
- 문제: 지연 로딩 상태에서 세션이 종료되어 엔티티 조회 실패
- 해결: fetch join 및 DTO 변환 구조로 변경

### 상태 전이 로직 복잡도 증가
- 문제: if문 증가로 유지보수 어려움
- 해결: ProjectStatusPolicy로 분리하여 관리

### 도메인 간 의존성 문제
- 문제: 다른 도메인 Repository 직접 호출 위험
- 해결: Facade/Application 계층에서만 처리하도록 구조 분리

---

## 실행 방법
1. MySQL 실행
2. application.yml 설정
3. 프로젝트 실행 (Spring Boot)
