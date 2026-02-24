---
tags: []
---
# Obsidian 태그 참조 가이드
## 태그 사용 원칙

1. **계층 구조**: 슬래시(/)로 계층을 구분합니다
2. **소문자 사용**: 일관성을 위해 가급적 소문자로 작성합니다 (제품명과 같이 고유명사는 대문자 허용).
3. **하이픈 연결**: 여러 단어는 하이픈(-)으로 연결합니다
4. **필수 태그**: 최소한 `type`은 반드시 지정합니다
5. **선택적 태그**: 문서 특성에 따라 필요한 태그만 추가합니다

## 태그 체계

| 상위 태그          | 하위 태그 예시        | 설명                         |
| -------------- | --------------- | -------------------------- |
| **#type/**     | guide           | 종합 가이드, 튜토리얼 문서            |
|                | reference       | 레퍼런스, 명령어/API 모음           |
|                | troubleshooting | 문제 해결 문서                   |
|                | faq             | 자주 묻는 질문                   |
|                | meeting-note    | 회의록                        |
|                | daily-log       | 일일 업무 로그                   |
|                | technical-doc   | 기술 문서, 설계 문서               |
|                | architecture    | 아키텍처 설계 문서                 |
|                | spec            | 요구사항 명세서                   |
| **#audience/** | beginner        | 초보자 대상                     |
|                | team            | 팀 전체 대상                    |
|                | developer       | 개발자 대상                     |
|                | admin           | 시스템 관리자 대상                 |
|                | new-member      | 신규 입사자 대상                  |
| **#tool/**     | claude-code     | Claude Code CLI 도구         |
|                | cpp             | C++ 개발 도구                  |
|                | dicom-pacs      | DICOM PACS 서버              |
|                | docker          | Docker/Podman 관련           |
|                | doxygen         | Doxygen 문서화                |
|                | gitlab          | GitLab 관련                  |
|                | lightning       | Lightning Network 관련       |
|                | mongodb         | MongoDB 관련                 |
|                | obsidian        | Obsidian 관련                |
|                | oracle          | Oracle Database 관련         |
|                | rabbitmq        | RabbitMQ 메시지 브로커 관련        |
|                | otl             | OTL 라이브러리                  |
|                | sqlite          | SQLite3 관련                 |
|                | visual-studio   | Visual Studio 관련           |
| **#topic/**    | ai              | AI/머신러닝 관련                 |
|                | api             | API 설계/사용                  |
|                | configuration   | 설정/구성                      |
|                | database        | 데이터베이스                     |
|                | debugging       | 디버깅                        |
|                | deployment      | 배포                         |
|                | installation    | 설치 과정                      |
|                | migration       | 마이그레이션                     |
|                | networking      | 네트워킹                       |
|                | performance     | 성능 최적화                     |
|                | security        | 보안                         |
|                | setup           | 설치 관련                      |
|                | testing         | 테스트                        |
|                | training        | 교육/학습                      |
| **#status/**   | draft           | 작성 중                       |
|                | review-needed   | 검토 필요                      |
|                | approved        | 승인됨                        |
|                | deprecated      | 더 이상 사용 안 함                |
|                | in-progress     | 진행 중                       |
|                | done            | 완료                         |
|                | blocked         | 차단됨                        |
| **#category/** | onboarding      | 신규 팀원 온보딩용                 |
|                | reference       | 레퍼런스 자료                    |
|                | best-practice   | 모범 사례                      |
|                | code-review     | 코드 리뷰 가이드                  |
|                | standards       | 코딩 표준, 규칙                  |
|                | process         | 프로세스 문서                    |
| **#project/**  | cloud-native    | Cloud Native 전환            |
|                | dicom-server    | DICOM 서버 개발                |
|                | gitlab-infra    | GitLab 인프라 관리              |
|                | homelab         | 홈랩 프로젝트                    |
|                | msa-migration   | MSA 전환 프로젝트                |
|                | server2         | Server2 프로젝트               |
|                | server1         | Server1 Legacy 프로젝트        |
| **#tech/**     | cpp             | C++ 관련                     |
|                | oracle          | Oracle 관련                  |
|                | docker          | Docker/컨테이너                |
|                | kubernetes      | Kubernetes (MSA 전환 대비)     |
|                | microservices   | 마이크로서비스                    |
|                | soa             | SOA 아키텍처                   |
|                | rest-api        | REST API                   |
|                | grpc            | gRPC (MSA 통신)              |
|                | message-queue   | 메시지 큐                      |
| **#version/**  | 1.0             | 버전 1.0                     |
|                | 2.0             | 버전 2.0                     |
|                | latest          | 최신 버전                      |
|                | legacy          | 레거시 버전                     |
| #product       | server2         | Server2(?:/ACQ\|TRS\|...)? |
|                | CTC             | CTC                        |
|                | ...             | ...                        |

## 사용 예시

### 예시 1: Obsidian 초보자 가이드
```yaml
---
tags:
  - type/guide
  - audience/beginner
  - tool/obsidian
  - topic/setup
  - status/approved
  - version/1.0
---
```

### 예시 2: OTL 라이브러리 레퍼런스
```yaml
---
tags:
  - type/reference
  - audience/developer
  - tool/otl
  - tech/cpp
  - tech/oracle
---
```

### 예시 3: MSA 마이그레이션 설계 문서
```yaml
---
tags:
  - type/architecture
  - project/msa-migration
  - tech/microservices
  - topic/migration
  - status/in-progress
---
```

### 예시 4: 일일 업무 로그
```yaml
---
tags:
  - type/daily-log
  - status/done
---
```

### 예시 5: 개발팀 기술 전환 교육 계획
```yaml
---
tags:
  - type/technical-doc
  - project/cloud-native
  - project/msa-migration
  - audience/team
  - category/onboarding
  - topic/training
  - status/approved
---
```

