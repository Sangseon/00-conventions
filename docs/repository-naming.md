# Repository Naming Convention

Repository 분류 및 이름 작성 규칙을 정의한다.

Repository는 목적에 따라 다음 세 가지로 구분한다.

| Category   | Purpose                                | Naming Convention                             |
| ---------- | -------------------------------------- | --------------------------------------------- |
| Management | Repository 관리 규칙 및 공통 기준 관리 | 별도 관리                                     |
| Learning   | 학습, 실습, 검증 및 기술 탐구          | `<tech>-<sequence>-<mode>-<subject>[-<type>]` |
| Product    | 실제 서비스 또는 제품 개발             | `<service-name>[-<component>]`                |

---

## 1. Management Repository

Repository 관리 규칙 및 공통 기준을 관리한다.

예:

```text
00-conventions
```

Management Repository는 Learning Repository 또는 Product Repository의 Naming Convention을 적용하지 않는다.

`00-` prefix는 관리 목적의 Repository를 다른 Repository보다 먼저 정렬하기 위해 사용한다.

---

## 2. Learning Repository

기술 학습, 실습, 검증, 실험 및 포트폴리오 목적의 Repository에 사용한다.

### Naming Convention

```text
<tech>-<sequence>-<mode>-<subject>[-<type>]
```

예:

```text
js-0001-manual-jwt-token-practice
java-0001-ai-payment-integration-notes
py-0001-manual-llm-from-scratch-practice
ts-0001-ai-llm-from-scratch-playground
dart-0001-manual-flutter-navigation-practice
tf-0001-manual-aws-infrastructure-practice
ansible-0001-manual-server-configuration-practice
docker-0001-manual-container-network-practice
k8s-0001-manual-workload-management-practice
helm-0001-manual-kubernetes-deployment-practice
```

---

## 2.1 Tech

프로젝트의 주된 구현 언어 또는 학습·실습 대상이 되는 핵심 기술을 식별한다.

### Programming Language

| Value  | Technology |
| ------ | ---------- |
| `java` | Java       |
| `kt`   | Kotlin     |
| `py`   | Python     |
| `js`   | JavaScript |
| `ts`   | TypeScript |
| `dart` | Dart       |
| `c`    | C          |
| `cpp`  | C++        |
| `cs`   | C#         |
| `go`   | Go         |
| `rs`   | Rust       |

### Infrastructure / DevOps

| Value     | Technology |
| --------- | ---------- |
| `tf`      | Terraform  |
| `ansible` | Ansible    |
| `docker`  | Docker     |
| `k8s`     | Kubernetes |
| `helm`    | Helm       |

`tech`는 Repository에서 가장 중심이 되는 학습 또는 구현 대상을 기준으로 결정한다.

예:

```text
tf-0001-manual-aws-infrastructure-practice
```

Terraform을 사용해 AWS Infrastructure를 구성하는 것이 핵심이므로 `tf`를 사용한다.

```text
docker-0001-manual-container-network-practice
```

Docker Container와 Network 동작을 학습하는 것이 핵심이므로 `docker`를 사용한다.

```text
k8s-0001-manual-workload-management-practice
```

Kubernetes의 Pod, Deployment, Service 등 Workload 관리 자체를 학습하는 것이 핵심이므로 `k8s`를 사용한다.

Helm Chart 작성이나 배포 자동화가 핵심인 경우에는 Kubernetes가 아니라 `helm`을 사용한다.

```text
helm-0001-manual-kubernetes-deployment-practice
```

Framework, Runtime, Library는 원칙적으로 `tech`로 사용하지 않는다.

예:

```text
java-0001-ai-payment-integration-notes
```

Spring Boot를 사용하더라도 다음과 같이 작성하지 않는다.

```text
spring-0001-ai-payment-integration-notes
```

TypeScript와 React를 사용하는 경우:

```text
ts-0001-ai-llm-from-scratch-playground
```

다음과 같이 작성하지 않는다.

```text
react-0001-ai-llm-from-scratch-playground
```

Dart와 Flutter를 사용하는 경우에도 동일한 원칙을 적용한다.

Dart는 프로그래밍 언어이므로 `tech`로 사용할 수 있다.

```text
dart-0001-manual-mobile-app-practice
```

Flutter는 Framework이므로 기본적으로 `tech`로 사용하지 않는다.

다음과 같은 이름은 권장하지 않는다.

```text
flutter-0001-manual-mobile-app-practice
```

다만 Flutter 자체의 기능이나 동작을 학습하는 것이 프로젝트의 핵심 Subject라면 Subject에 포함할 수 있다.

예:

```text
dart-0001-manual-flutter-navigation-practice
dart-0002-manual-flutter-state-management-practice
dart-0003-manual-flutter-widget-lifecycle-notes
```

Framework, Runtime, Library, Cloud Provider 등의 상세 기술은 각 Repository의 `README.md`에서 관리한다.

---

## 2.2 Sequence

동일한 `tech` 내에서 Repository 생성 순서를 4자리 숫자로 관리한다.

```text
0001
0002
0003
...
```

Sequence는 `tech`별로 독립적으로 증가한다.

예:

```text
java-0001-...
java-0002-...

js-0001-...
js-0002-...

dart-0001-...
dart-0002-...

tf-0001-...
tf-0002-...

k8s-0001-...
k8s-0002-...
```

삭제되거나 중단된 Repository의 Sequence는 재사용하지 않는다.

---

## 2.3 Mode

프로젝트 구현 과정에서 Generative AI가 사용된 방식을 구분한다.

| Value    | Description                                                        |
| -------- | ------------------------------------------------------------------ |
| `manual` | 설계와 코드 구현을 직접 수행                                       |
| `ai`     | Generative AI 또는 Coding Agent를 실제 개발 과정에 적극적으로 사용 |

### manual

다음과 같은 보조적인 AI 사용은 `manual`로 분류할 수 있다.

- 개념 질문
- 기술 학습
- 문서 탐색
- 작성한 코드에 대한 질문
- 구현 결과 검토

AI가 코드 생성이나 구현을 실질적으로 수행한 경우에는 `manual`로 분류하지 않는다.

### ai

다음과 같이 AI가 실제 구현 과정에 참여한 경우 사용한다.

- 코드 생성
- 테스트 코드 생성
- Refactoring
- 설계 초안 생성
- 반복 구현
- Coding Agent 사용

`mode`는 프로젝트의 품질이나 개발자의 역량을 평가하기 위한 값이 아니다.

프로젝트가 어떤 방식으로 구현되었는지를 기록하기 위한 메타데이터다.

---

## 2.4 Subject

Repository에서 다루는 핵심 주제를 표현한다.

Framework 또는 Library 이름보다 학습하거나 해결하려는 문제를 중심으로 작성한다.

권장:

```text
jwt-token
payment-integration
llm-from-scratch
transaction-consistency
container-network
workload-management
server-configuration
kubernetes-deployment
aws-infrastructure
flutter-navigation
flutter-state-management
```

지양:

```text
spring-project
react-project
tensorflow-test
docker-test
flutter-test
```

`tech`가 이미 기술을 나타내는 경우 Subject에서 동일한 기술명을 불필요하게 반복하지 않는다.

예:

```text
tf-0001-manual-aws-infrastructure-practice
```

다음과 같이 작성하지 않는다.

```text
tf-0001-manual-terraform-aws-infrastructure-practice
```

---

## 2.5 Type

선택 항목이다.

Repository의 성격을 추가로 표현할 필요가 있을 때 사용한다.

| Type         | Description                                           |
| ------------ | ----------------------------------------------------- |
| `practice`   | 기술이나 개념을 직접 구현하며 연습                    |
| `notes`      | 특정 기술, 설계 또는 문제를 코드와 함께 검증하고 정리 |
| `playground` | 입력값이나 설정을 변경하며 기술의 동작을 실험         |
| `study`      | 개념 학습과 여러 작은 예제를 중심으로 구성            |

예:

```text
js-0001-manual-jwt-token-practice
java-0001-ai-payment-integration-notes
py-0001-manual-llm-from-scratch-practice
ts-0001-ai-llm-from-scratch-playground
dart-0001-manual-flutter-navigation-practice
```

새로운 Type은 기존 Type으로 Repository의 성격을 표현하기 어려운 경우에만 추가한다.

---

## 3. Product Repository

실제로 배포하거나 사용자에게 제공하는 서비스 또는 제품 개발 Repository에 사용한다.

Learning Repository와 달리 구현 언어나 사용 기술보다 서비스 자체의 정체성을 우선한다.

### Naming Convention

```text
<service-name>[-<component>]
```

### Monorepo

하나의 Repository에서 서비스 전체를 관리하는 경우 서비스 이름만 사용한다.

예:

```text
memento
```

구조 예:

```text
memento/
├─ apps/
│  ├─ web/
│  ├─ api/
│  └─ worker/
├─ packages/
└─ infra/
```

Java, TypeScript, Python, Dart, Terraform 등 여러 기술을 사용하더라도 Repository 이름에는 특정 기술을 포함하지 않는다.

Flutter 기반 모바일 앱도 Product Repository에서는 기술명이 아니라 서비스 이름을 우선한다.

예:

```text
memento
```

Multi-repo 구조라면 역할에 따라 다음과 같이 구분할 수 있다.

```text
memento-api
memento-web
memento-mobile
memento-worker
memento-infra
```

### Multi-repo

서비스를 여러 Repository로 분리하는 경우 Component를 추가한다.

Component는 기술 이름보다 서비스 내 역할을 기준으로 작성한다.

권장:

```text
-api
-web
-mobile
-worker
-infra
```

지양:

```text
-spring
-react
-flutter
-python
-terraform
```

---

## 4. Principles

Learning Repository는 이름만 보고 가능한 한 다음 내용을 파악할 수 있도록 한다.

```text
어떤 기술을 중심으로 하는가
+
해당 기술의 몇 번째 프로젝트인가
+
AI를 어떤 방식으로 사용했는가
+
무엇을 학습하거나 검증하는가
+
어떤 성격의 Repository인가
```

Product Repository는 다음 내용을 중심으로 한다.

```text
어떤 서비스인가
+
필요한 경우 어떤 Component인가
```

Repository 이름에는 구현 세부사항을 과도하게 포함하지 않는다.

Framework, Runtime, Library, Cloud Provider 및 세부 Architecture는 각 Repository의 [`README.md`](../README.md)에서 관리한다.

Repository 이름은 프로젝트의 목적과 정체성을 안정적으로 표현하는 것을 우선한다.
