# 손기석 | Backend Engineer - AI Integration & Reliable Systems

업무 요구사항을 **데이터, 권한, 처리 상태와 실패 조건이 명확한 백엔드 시스템으로 구현**합니다.

AI 기능은 결과를 그대로 신뢰하지 않고, 서버의 검증과 사람의 승인 안에서 실제 업무와 연결합니다. Java/Spring과 Python/FastAPI를 업무 특성에 따라 사용해 왔으며, 현재 독립 공개 재현 샘플은 Java/Spring 쪽이 더 강합니다. SQL, Docker와 LLM은 필요한 문제를 해결하기 위한 도구로 사용하고, 자동 테스트와 실제 실행 환경 검증으로 동작 범위와 실패 조건을 확인합니다.

[포트폴리오](https://son1004007.github.io/engineering-career-portfolio/) | [코드와 검증 근거](https://github.com/son1004007/engineering-career-portfolio) | [어떻게 개발하는가](https://github.com/son1004007/engineering-career-portfolio/blob/main/HOW_I_ENGINEER.md) | [실무 기술 사례](https://son1004007.github.io/engineering-career-portfolio/blog/)

## 제가 잘하는 일

| 영역 | 쉽게 설명하면 | 기술적으로는 |
|---|---|---|
| 업무 요구사항을 시스템으로 구조화 | 모호한 요청을 구현 범위, 처리 단계와 완료 조건으로 정리합니다 | system boundary, state, transaction, acceptance criteria |
| 백엔드와 데이터 연결 | 화면이나 AI 기능이 실제 업무 데이터와 안전하게 연결되도록 만듭니다 | API, SQL, Oracle, PostgreSQL, Spring Boot, FastAPI |
| AI 기능 통합 | AI가 제안할 일과 서버 또는 사람이 최종 책임질 일을 분리합니다 | LLM integration, structured output validation, Text2SQL/NL2SQL |
| 잘못된 처리 차단 | 권한이 없거나 입력과 결과가 잘못되면 중요한 처리가 진행되지 않게 합니다 | RBAC, validation, idempotency, fail-closed |
| 실제 동작 검증 | 정상 상황뿐 아니라 실패, 권한, 중복과 외부 장애까지 확인합니다 | unit, integration, E2E, regression, eval |
| 배포와 복구 | 개발한 시스템을 실행하고 상태를 확인하며 문제가 생기면 복구할 수 있게 합니다 | Linux, Docker, Tomcat, Nginx, CI/CD, health check, rollback |

## 대표 작업

### [OpsMate Local](https://github.com/son1004007/engineering-career-portfolio/tree/main/02_projects/opsmate-local)

구매 요청부터 승인, 반려, 발주까지의 업무 흐름에 AI를 연결하되, **중요한 업무 결정은 서버의 규칙과 사람의 승인 안에서만 일어나도록 만든 프로젝트**입니다.

- AI는 자연어 요청을 바탕으로 초안을 제안
- 서버는 사용자 권한, 업무 상태, 중복 요청과 발주 가능 여부를 최종 확인
- 모델 오류나 잘못된 출력은 저장 전에 차단
- 실제 로컬 LLM `gemma3:12b`로 9개 핵심 합성 업무 시나리오 E2E 전건 성공
- 실제 Internet HTTPS 경로에서 사용자 작업 분리, rate limit, DB/model 비노출, close/reopen 검증

### [자연어 질문을 데이터 조회로 연결하는 Text2SQL / NL2SQL](https://github.com/son1004007/engineering-career-portfolio/blob/main/03_portfolio/case-studies/text2sql-validation.md)

사용자의 자연어 질문을 SQL과 데이터 조회로 연결하고, 단순 생성 결과가 아니라 **SQL 문법, 실행 가능성, 업무 정답 여부와 모델별 차이를 따로 검증**했습니다.

- Python / FastAPI 기반 API
- SQL 검증과 실행 흐름
- validation set과 다중 모델 비교
- 실패 유형 분류와 결과 기록

이 경험은 공개 가능한 실무 evidence가 중심이며, Java/Spring 사례와 같은 수준의 독립 실행 가능한 Python/FastAPI 공개 샘플은 다음 보강 대상으로 두고 있습니다.

### [실제 업무 문제를 독립 샘플로 재현한 Engineering Case Studies](https://github.com/son1004007/engineering-career-portfolio/blob/main/03_portfolio/case-studies/README.md)

회사 코드를 공개하지 않고, 실제 업무에서 다뤘던 문제를 일반화해 다시 구현하고 정상, 실패, 경계 조건을 테스트했습니다.

- 서로 다른 로그인 방식에서 사용자와 권한이 잘못 연결되지 않는지 검증
- 여러 기간을 조회할 때 데이터가 빠지거나 겹치지 않는지 검증
- 서버 환경이 달라도 같은 애플리케이션을 배포하고 복구할 수 있는지 검증
- 사용자 식별과 업무 기준이 화면, API, DB에서 다르게 적용되지 않는지 검증

## AI를 개발에 활용하는 방식

AI는 조사, 구현과 리뷰를 빠르게 만드는 도구로 사용합니다. 완료 여부는 AI의 설명이 아니라 테스트와 실제 실행 결과로 판단합니다.

```text
문제와 제약 정의
-> 필요한 정보와 기존 코드 확인
-> 구현 계획
-> AI를 활용한 탐색과 구현
-> 자동 테스트와 리뷰
-> 실제 실행 환경 검증
-> 결과와 한계 기록
```

다른 개발자나 AI가 작업을 이어받아도 프로젝트의 목표, 현재 상태와 검증 기준을 다시 파악할 수 있도록 문서와 근거를 함께 관리합니다.

[상세한 개발 방식 보기](https://github.com/son1004007/engineering-career-portfolio/blob/main/HOW_I_ENGINEER.md)

## 사용하는 기술

기술 스택은 정체성보다 **백엔드 시스템을 구현하기 위한 도구**로 관리합니다.

- **Backend:** Java, Spring Boot, Python, FastAPI
- **Data:** Oracle, PostgreSQL, SQL
- **AI integration:** LLM integration, structured output validation, Text2SQL/NL2SQL
- **Operations:** Linux, Docker, Tomcat, Nginx, Jenkins, GitHub Actions
- **Security:** 인증, 권한 통제, session, audit, secure failure handling

보안 운영 경험을 바탕으로 개발 단계에서도 권한, 로그, 감사 가능성과 운영 실패를 함께 고려합니다. IT 내부통제와 IT 리스크 관점의 공개 작업 표본은 [IT Audit Work Samples](https://github.com/son1004007/it-audit-work-samples)에 정리했습니다.

공개 저장소에는 회사 코드, 고객 데이터, 내부 URL과 실제 업무 규칙을 포함하지 않습니다. 확인하지 않은 성능, 운영 규모와 성과는 주장하지 않습니다.
