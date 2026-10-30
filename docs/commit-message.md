# Commit Message Convention

Git Commit Message의 작성 형식과 기준을 정의한다.

본 컨벤션은 GitHub에서 관리하는 모든 Repository에 공통으로 적용한다.

Commit Message는 변경 목적과 주요 내용을 명확하게 전달하고, Git History에서 작업 이력을 쉽게 파악할 수 있도록 작성한다.

## 1. Common Principles

Commit Message는 Subject(제목)를 기본으로 작성하며, 필요한 경우 Body(본문)를 추가한다.

다음 원칙을 따른다.

- Subject는 필수이며, Body는 선택 사항이다.
- Commit Type은 정의된 영어 키워드를 사용한다.
- Subject와 Body는 한글 또는 영어로 작성할 수 있다.
- 언어보다 변경 목적과 내용을 명확하게 전달하는 것을 우선한다.
- Commit Type은 작업의 주된 목적을 기준으로 선택한다.
- 하나의 Commit에는 서로 관련된 변경 사항을 포함한다.
- 서로 독립적인 목적의 변경은 별도 Commit으로 구분할 수 있다.
- 불필요한 Commit 분리나 Body 작성을 강제하지 않는다.

## 2. Message Format

### Basic Format

기본 형식:

```text
<type>: <description>
```

Body가 필요한 경우:

```text
<type>: <description>

<body>
```

### Step-based Format

Step 단위로 개발하는 프로젝트에서는 다음 형식을 사용할 수 있다.

```text
<type>: [step-XX] <description>
```

Body가 필요한 경우:

```text
<type>: [step-XX] <description>

<body>
```

- `type`은 변경의 주된 목적을 나타낸다.
- `description`은 변경 내용을 간결하게 표현한다.
- `[step-XX]`는 해당 프로젝트의 개발 단계를 식별한다.
- Step 번호는 프로젝트에서 필요한 경우에만 사용한다.
- Body를 작성하는 경우 Subject와 빈 줄 하나로 구분한다.

## 3. Subject

Subject는 Commit에서 수행한 핵심 변경 사항을 한 줄로 표현한다.

다음 기준을 권장한다.

- 한글 또는 영어로 작성할 수 있다.
- 영어로 작성하는 경우 `add`, `implement`, `fix`, `update`, `remove` 등 명령형 동사를 사용한다.
- 한글로 작성하는 경우 `추가`, `구현`, `수정`, `변경`, `제거` 등 간결한 표현을 사용한다.
- 문장 끝에 마침표를 사용하지 않는다.
- 가능하면 50자 내외로 작성하고, 길어지는 경우 72자 이내를 권장한다.
- 세부 구현 내용을 모두 나열하지 않는다.
- 변경한 파일 이름보다 변경 목적을 우선한다.

예:

```text
feat: add JWT token generation
feat: JWT 토큰 생성 기능 추가
fix: WebSocket 종료 코드 경합 수정
docs: 저장소 문서 업데이트
```

## 4. Body

Body는 Subject만으로 설명하기 어려운 변경 사항이나 배경이 있을 때 작성한다.

다음 내용을 포함할 수 있다.

- 주요 변경 사항
- 변경 이유 및 배경
- 설계 선택과 Trade-off
- 테스트 및 검증 결과
- 기존 동작에 미치는 영향
- 알려진 제약 사항

작성 시 다음 원칙을 따른다.

- 한글 또는 영어로 작성할 수 있다.
- 필요한 경우 `-` 목록이나 문단으로 정리할 수 있다.
- Subject와 동일한 내용을 불필요하게 반복하지 않는다.
- 모든 파일 변경 사항을 나열할 필요는 없다.
- 항목 수나 작성 형식을 강제하지 않는다.
- 추가 설명이 필요하지 않으면 생략한다.

## 5. Commit Type

변경의 주된 목적에 따라 Commit Type을 선택한다.

| Type       | Description                          |
| ---------- | ------------------------------------ |
| `setup`    | 프로젝트 초기 구성 및 개발 환경 설정 |
| `docs`     | 문서 변경                            |
| `feat`     | 기능 추가                            |
| `fix`      | 오류 수정                            |
| `refactor` | 동작 변경 없는 구조 개선             |
| `test`     | 테스트 추가 및 수정                  |

### Type Selection

하나의 Commit에 여러 종류의 변경이 포함된 경우 주된 목적을 기준으로 Type을 선택한다.

- 기능 구현과 관련 테스트·문서를 함께 변경한 경우 `feat`
- 오류 수정과 회귀 테스트를 함께 변경한 경우 `fix`
- 구현 변경 없이 문서만 수정한 경우 `docs`
- 외부 동작을 유지하면서 내부 구조를 개선한 경우 `refactor`
- 기능 변경 없이 테스트만 추가하거나 수정한 경우 `test`
- 프로젝트의 초기 실행 환경을 구성한 경우 `setup`

기존 Type으로 변경 목적을 적절하게 표현하기 어려운 경우 새로운 Type을 추가할 수 있다.

새로운 Type은 실제 사용 사례가 발생했을 때 검토하고 본 컨벤션에 반영한다.

## 6. Step-based Commit

Step 단위 개발 계획이 있는 Repository에서는 `[step-XX]` 형식을 사용할 수 있다.

Step 번호는 해당 변경이 속한 개발 단계를 나타내며, Commit Type과는 별개로 관리한다.

예:

```text
setup: [step-01] TypeScript 클라이언트 및 서버 환경 구성
setup: [step-02] SFU 실행 환경 검증
feat: [step-03] WebSocket 세션 및 프로필 동기화 구현
feat: [step-04] 다중 회의방 관리 구현
feat: [step-05] 전체 및 회의방 채팅 구현
```

완료된 Step에서 발견된 오류를 이후에 수정하는 경우에도 원래 Step 번호를 사용할 수 있다.

```text
fix: [step-03] WebSocket 초과 메시지 종료 처리 수정
```

Step에 직접 대응하지 않는 공통 변경이나 Repository 관리 작업에서는 Step 번호를 생략할 수 있다.

```text
docs: 저장소 컨벤션 업데이트
refactor: 공통 유틸리티 구조 개선
```

## 7. Examples

### 7.1 Basic Commit

```text
docs: add repository conventions
feat: JWT 토큰 생성 기능 추가
fix: correct token signature validation
refactor: 토큰 검증 로직 단순화
test: add JWT signature tests
```

### 7.2 Feature Commit with Body

```text
feat: [step-05] 전체 및 회의방 채팅 구현

- 기존 WebSocket 연결을 이용한 전체·회의방 채팅 추가
- 회의방 소속 검증 및 메시지 전달 범위 분리
- 브라우저 메모리 기반 채팅 내역 관리
- 통합 테스트 및 Step 05 검증 문서 작성
```

### 7.3 Fix Commit with Body

```text
fix: [step-03] WebSocket 초과 메시지 종료 처리 수정

- Close 핸드셰이크 중 불필요한 강제 종료 방지
- close 이벤트에서 세션 및 회의방 정리 일원화
- 메시지 크기 경계 및 종료 코드 회귀 테스트 추가
- 극단적인 부하 환경에서 발생할 수 있는 제약 사항 문서화
```

### 7.4 Documentation Commit

```text
docs: [step-04] 다중 회의방 참여 정책 변경
```

Subject만으로 변경 목적을 충분히 설명할 수 있다면 Body를 생략할 수 있다.

## 8. Commit Separation

Commit은 변경 목적과 작업 범위를 기준으로 구분한다.

다음 원칙을 권장한다.

- 하나의 기능 구현에 필요한 코드·테스트·문서는 함께 Commit할 수 있다.
- 독립적인 기능 추가와 오류 수정은 가능한 한 별도 Commit으로 구분한다.
- 기존 기능에서 발견된 결함을 별도 작업으로 수정한 경우 독립된 `fix` Commit으로 관리할 수 있다.
- 요구사항이나 정책 변경을 기능 구현 전에 확정한 경우 별도 `docs` Commit으로 기록할 수 있다.
- 하나의 Step에서 여러 Commit을 작성할 수 있다.

Commit을 지나치게 세분화하기보다 변경 목적과 작업 이력을 이해하기 쉬운 단위를 우선한다.

## 9. Maintenance

본 컨벤션은 GitHub에서 관리하는 Repository에 적용하는 Active 규칙이다.

다음 기준으로 유지한다.

- 실제 프로젝트 적용 과정에서 개선이 필요한 경우 규칙을 수정할 수 있다.
- 변경 시 기존 규칙과의 일관성을 고려한다.
- 새로운 Commit Type은 필요성이 확인된 경우 추가한다.
- 프로젝트별 특성이 필요한 경우 공통 규칙을 유지하면서 추가 기준을 정의할 수 있다.
- 과거 Commit Message를 새로운 규칙에 맞춰 수정할 필요는 없다.

Active는 변경할 수 없는 규칙이라는 의미가 아니라, 현재 프로젝트에 적용하는 공통 기준이라는 의미다.
