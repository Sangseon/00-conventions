# Project Classification

프로젝트를 Repository 이름과 별개로 `Categories`와 `Topics` 기준으로 분류한다.

Repository 이름은 개별 프로젝트의 정체성을 표현하고,  
Classification은 여러 프로젝트를 주제별로 묶거나 검색하기 위한 기준으로 사용한다.

```text
Repository Name
→ 개별 프로젝트 식별

Categories
→ 여러 프로젝트를 비교적 큰 주제로 묶기 위한 분류

Topics
→ 프로젝트에서 실제로 다루는 세부 기술 및 개념
```

---

## 1. Categories

`Categories`는 여러 프로젝트를 함께 모아보기 위한 비교적 큰 주제다.

하나의 프로젝트는 필요에 따라 여러 Category에 포함될 수 있다.

Category는 상하 관계를 강제하지 않는다.

예를 들어 `Payment`가 반드시 `Backend`의 하위 Category가 되는 식의 계층 구조를 만들지 않는다.

### Categories

| Category                       | Description                                                              |
| ------------------------------ | ------------------------------------------------------------------------ |
| Authentication / Authorization | 인증, 인가 및 사용자 접근 제어와 관련된 프로젝트                         |
| Payment                        | 결제 연동, 승인, 취소, 정산 등 결제 흐름과 관련된 프로젝트               |
| AI / ML                        | LLM, Machine Learning, 생성형 AI 등과 관련된 프로젝트                    |
| Infrastructure                 | Cloud, IaC, Provisioning, Server Automation 등과 관련된 프로젝트         |
| Container / Orchestration      | Container, Kubernetes, Helm 등 실행 및 배포 환경과 관련된 프로젝트       |
| Observability                  | Logging, Metrics, Tracing, Monitoring 등 시스템 관찰성과 관련된 프로젝트 |
| Frontend                       | Web UI 및 Frontend Application과 관련된 프로젝트                         |
| Mobile                         | Mobile Application과 관련된 프로젝트                                     |

필요한 Category는 프로젝트가 늘어남에 따라 추가한다.

---

## 2. Topics

`Topics`는 프로젝트에서 실제로 다루는 세부 기술, 개념 또는 관심사를 표현한다.

하나의 프로젝트는 여러 Topic을 가질 수 있다.

예:

```text
jwt
oauth2
hmac
signature
transaction
data-consistency
idempotency
settlement
database
concurrency
llm
transformer
tokenizer
pretraining
terraform
docker
kubernetes
```

Topic은 가능한 한 짧고 구체적인 이름을 사용한다.

---

## 3. Repository README Usage

각 Learning Repository의 `README.md`에는 Category를 직접 작성하지 않고 `Topics`만 기록한다.

`Topics`는 `Overview` 하위에 선택적으로 작성한다.

예:

```md
## Overview

JWT의 Header, Payload, Signature 생성 과정을 직접 구현하며
Token 생성 구조와 서명 원리를 확인하기 위한 연습 프로젝트다.

### Topics

- jwt
- hmac
- signature
- token
```

결제 관련 프로젝트라면:

```md
### Topics

- payment-integration
- transaction
- data-consistency
- idempotency
- settlement
- external-api
```

LLM 관련 프로젝트라면:

```md
### Topics

- llm
- transformer
- tokenizer
- pretraining
- inference
```

---

## 4. Category and Topic Relationship

Category와 Topic은 고정된 상하 관계를 갖지 않는다.

하나의 Topic이 여러 Category의 프로젝트에서 사용될 수 있다.

예:

```text
transaction
```

은 다음과 같은 여러 프로젝트에서 사용할 수 있다.

```text
Payment
Course Registration
Order
Inventory
```

따라서 `transaction`을 특정 Category에 종속시키지 않는다.

Category는 프로젝트를 모아보기 위한 기준이고,  
Topic은 프로젝트가 실제로 다루는 내용을 나타낸다.

---

## 5. Examples

### Authentication / Authorization

Repository:

```text
js-0001-manual-jwt-token-practice
```

Topics:

```text
jwt
token
hmac
signature
```

Category:

```text
Authentication / Authorization
```

### Payment

Repository:

```text
java-0001-ai-payment-integration-notes
```

Topics:

```text
payment-integration
transaction
data-consistency
idempotency
settlement
external-api
```

Category:

```text
Payment
```

### AI / ML

Repository:

```text
py-0001-manual-llm-from-scratch-practice
```

Topics:

```text
llm
transformer
tokenizer
pretraining
```

Category:

```text
AI / ML
```

Repository:

```text
ts-0001-ai-llm-from-scratch-playground
```

Topics:

```text
llm
transformer
tokenizer
training
inference
visualization
```

Category:

```text
AI / ML
```

---

## 6. Category Addition Criteria

새로운 Category가 필요한 경우 다음 기준을 참고한다.

1. 여러 프로젝트를 함께 묶어볼 필요가 있는 주제인지 확인한다.
2. 기존 Category에 포함했을 때 프로젝트의 성격이 자연스럽게 이해되는지 확인한다.
3. 특정 기술 하나를 표현하기 위한 분류인지 확인한다.
4. 향후 다른 프로젝트에서도 재사용할 가능성이 있는지 생각해본다.

다음과 같은 경우에는 새로운 Category보다 Topic 사용을 우선한다.

```text
JWT
Transaction
Database
Kafka
Redis
Terraform
Docker
```

이들은 프로젝트의 세부 기술 또는 개념으로 표현할 수 있으므로 일반적으로 Topic으로 관리한다.

새로운 Category는 여러 프로젝트를 묶는 데 도움이 되고 기존 Category보다 의미를 더 명확하게 표현할 수 있을 때 추가할 수 있다.

---

## 7. Principles

Classification은 프로젝트를 완벽한 계층 구조로 만들기 위한 것이 아니다.

다음 원칙을 따른다.

- Repository 이름은 개별 프로젝트의 정체성을 표현한다.
- Category는 프로젝트를 큰 주제로 모아보기 위한 분류로 사용한다.
- Topic은 프로젝트에서 실제로 다루는 세부 기술과 개념을 표현한다.
- Category와 Topic은 고정된 상하 관계를 만들지 않는다.
- 하나의 프로젝트는 여러 Topic을 가질 수 있다.
- 필요한 경우 하나의 프로젝트가 여러 Category에 포함될 수 있다.
- 새로운 분류를 만들기보다 기존 Category와 Topic으로 자연스럽게 표현할 수 있는지 먼저 확인한다.
- 프로젝트를 이해하고 다시 찾아보기 쉬운 분류를 우선한다.
- 분류 체계는 프로젝트가 늘어나거나 관점이 바뀌면 함께 변경할 수 있다.
