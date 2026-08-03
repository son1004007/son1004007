# 손기석 | Java/Spring 백엔드 개발자

Java/Spring 기반 업무 시스템의 인증·권한, 트랜잭션, 데이터 연계를 구현해 왔습니다.
모델 연구보다 Python/FastAPI와 로컬 오픈웨이트 LLM 기능을 업무 시스템의 권한·데이터·승인 흐름에 안전하게 연결하는 데 집중하고 있습니다.

[포트폴리오](https://son1004007.github.io/engineering-career-portfolio/) · [코드와 검증 근거](https://github.com/son1004007/engineering-career-portfolio) · [실무 기술 사례](https://son1004007.github.io/engineering-career-portfolio/blog/)

## 대표 작업

### [OpsMate Local](https://github.com/son1004007/engineering-career-portfolio/tree/main/02_projects/opsmate-local)

구매 요청부터 승인·반려·발주까지의 흐름에 AI 초안 생성을 연결한 Spring Boot 프로젝트입니다.

- Java 21, Spring Boot, Spring Security, Spring Data JPA
- 권한, 상태 전이, 멱등성, 트랜잭션과 감사 이벤트를 서버가 통제
- 모델 오류와 중복 요청을 포함한 자동화 테스트 19개 통과
- 실제 오픈웨이트 모델 E2E와 운영 배포는 아직 검증 전

### [Spring Security Auth Bridge](https://github.com/son1004007/engineering-career-portfolio/tree/main/02_projects/case-study-samples/spring-security-auth-bridge)

DB 로그인과 레거시 SSO를 하나의 사용자·권한·세션 정책으로 통합한 독립 재현 프로젝트입니다.

- 로컬 사용자 상태와 역할을 최종 권한 기준으로 적용
- 세션 회전, CSRF 수명주기, assertion 검증과 replay 차단 구현
- 정상·실패·권한·시간 경계를 포함한 자동화 테스트 24개 통과

## 경험 영역

- **Backend:** Java, Spring Boot, Spring Security, JPA, MyBatis, Python, FastAPI
- **Data:** Oracle, PostgreSQL, SQL, 데이터 정합성 검증
- **Operations:** Linux, Tomcat, Nginx, Docker, Jenkins
- **Engineering:** 인증·인가, 상태 전이, 멱등성, 트랜잭션, 감사와 실패 처리

보안 운영 경험을 바탕으로 권한, 로그, 감사 가능성과 운영 실패를 개발 단계부터 함께 고려합니다. IT 내부통제·IT 리스크 직무용 공개 작업 표본은 [IT Audit Work Samples](https://github.com/son1004007/it-audit-work-samples)에 정리했습니다.

공개 저장소에는 회사 코드, 고객 데이터, 내부 URL과 실제 업무 규칙을 포함하지 않습니다. 확인하지 않은 성능이나 운영 범위는 각 프로젝트에 별도로 표시합니다.
