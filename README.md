# 손기석 | Software / Backend / Platform Engineer

업무에서 필요한 기능을 **문제와 제약조건으로 정리하고, 적절한 기술과 AI를 활용해 실제로 사용할 수 있는 시스템으로 구현하는 개발자**입니다.

특정 언어나 프레임워크 자체보다 다음을 중요하게 봅니다.

- 모호한 요구사항을 구현 범위와 완료조건으로 정리하는 것
- 데이터, 권한, 상태와 실패 조건을 명확하게 설계하는 것
- AI를 개발 도구와 서비스 기능 양쪽에 실용적으로 활용하는 것
- 테스트와 실제 실행 결과로 구현이 맞는지 검증하는 것
- 배포, 보안, 장애와 복구까지 고려해 운영 가능한 형태로 끝내는 것

Java/Spring, Python/FastAPI, SQL, Docker와 LLM은 이 일을 하기 위해 사용하는 도구입니다.

[포트폴리오](https://son1004007.github.io/engineering-career-portfolio/) · [코드와 검증 근거](https://github.com/son1004007/engineering-career-portfolio) · [어떻게 개발하는가](https://github.com/son1004007/engineering-career-portfolio/blob/main/HOW_I_ENGINEER.md) · [실무 기술 사례](https://son1004007.github.io/engineering-career-portfolio/blog/)

## 제가 잘하는 일

| 영역 | 쉽게 설명하면 | 기술적으로는 |
|---|---|---|
| 문제 구조화 | 요청을 바로 코딩하지 않고, 무엇을 만들고 어디까지 검증할지 먼저 정리합니다 | system boundary, acceptance criteria, state, transaction |
| 백엔드와 데이터 | 화면이나 AI 기능이 실제 업무 데이터와 안전하게 연결되도록 만듭니다 | API, SQL, Oracle, PostgreSQL, Spring Boot, FastAPI |
| AI 활용 | AI가 잘하는 일과 서버 또는 사람이 책임져야 할 일을 나눕니다 | LLM, Agent, RAG, Text2SQL/NL2SQL, structured output |
| 안전한 업무 처리 | 권한이 없거나 결과가 잘못되면 잘못 처리하지 않고 중단되게 합니다 | RBAC, validation, idempotency, fail-closed |
| 검증 | 만들었다는 설명보다 테스트와 실제 실행 결과를 남깁니다 | unit, integration, E2E, regression, eval |
| 운영 | 개발한 시스템을 배포하고 문제가 생겼을 때 확인하고 복구할 수 있게 합니다 | Linux, Docker, Tomcat, Nginx, CI/CD, health check, rollback |

## 대표 작업

### [OpsMate Local](https://github.com/son1004007/engineering-career-portfolio/tree/main/02_projects/opsmate-local)

구매 요청부터 승인·반려·발주까지의 업무 흐름에 AI를 연결하되, **중요한 업무 결정은 서버의 규칙과 사람의 승인 안에서만 일어나도록 만든 프로젝트**입니다.

- AI는 자연어 요청을 바탕으로 초안을 제안
- 서버는 사용자 권한, 업무 상태, 중복 요청과 발주 가능 여부를 최종 확인
- 모델 오류가 발생하면 잘못된 결과를 저장하지 않고 중단
- 실제 로컬 LLM `gemma3:12b`를 이용한 합성 업무 요청 E2E `9/9` 성공
- Internet HTTPS 경로에서 session 격리, rate limit, DB/model 비노출, close/reopen 경계 검증

### [자연어 질문을 데이터 조회로 연결하는 Text2SQL / NL2SQL](https://github.com/son1004007/engineering-career-portfolio/blob/main/03_portfolio/case-studies/text2sql-validation.md)

사용자의 자연어 질문을 SQL과 데이터 조회로 연결하고, 단순 생성 결과가 아니라 **SQL 문법, 실행 가능성, 업무 정답 여부와 모델별 차이를 따로 검증**했습니다.

- Python / FastAPI 기반 API
- SQL 검증과 실행 흐름
- validation set과 다중 모델 비교
- 실패 유형 분류와 결과 기록

### [실제 업무 문제를 독립 샘플로 재현한 Engineering Case Studies](https://github.com/son1004007/engineering-career-portfolio/tree/main/03_portfolio/case-studies)

회사 코드를 공개하지 않고, 실제 업무에서 다뤘던 문제를 일반화해 다시 구현하고 테스트했습니다.

- 사용자 로그인과 권한 통합: 자동 테스트 `24개`
- 복잡한 기간 조회의 데이터 정합성: 자동 테스트 `12개`
- 배포 환경 차이와 복구 절차: 자동 테스트 `10개`
- 여러 계층의 업무 규칙 정합성: 자동 테스트 `11개`

## AI를 개발에 활용하는 방식

AI에게 코드를 한 번 생성하게 하고 끝내지 않습니다.

```text
문제와 제약 정의
-> 필요한 정보와 기존 코드 확인
-> 구현 계획
-> AI를 활용한 구현
-> 자동 테스트
-> 실제 실행 환경 검증
-> 결과와 한계 기록
```

다른 AI나 개발자가 작업을 이어받아도 프로젝트의 목표, 현재 상태, 검증 기준을 다시 파악할 수 있도록 문서와 evidence를 함께 관리합니다.

[상세한 개발 방식 보기](https://github.com/son1004007/engineering-career-portfolio/blob/main/HOW_I_ENGINEER.md)

## 사용하는 기술

기술 스택은 정체성보다 **문제를 해결하기 위한 도구**로 관리합니다.

- **Backend:** Java, Spring Boot, Python, FastAPI
- **Data:** Oracle, PostgreSQL, SQL
- **AI:** LLM, Agent, RAG, Text2SQL/NL2SQL
- **Operations:** Linux, Docker, Tomcat, Nginx, Jenkins, GitHub Actions
- **Security:** 인증·인가, 권한 통제, session, audit, secure failure handling

보안 운영 경험을 바탕으로 개발 단계에서도 권한, 로그, 감사 가능성과 운영 실패를 함께 고려합니다. IT 내부통제·IT 리스크 관점의 공개 작업 표본은 [IT Audit Work Samples](https://github.com/son1004007/it-audit-work-samples)에 정리했습니다.

공개 저장소에는 회사 코드, 고객 데이터, 내부 URL과 실제 업무 규칙을 포함하지 않습니다. 확인하지 않은 성능, 운영 규모와 성과는 주장하지 않습니다.
