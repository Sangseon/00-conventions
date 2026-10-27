# Repository README Convention

Repository에서 사용하는 `README.md` 작성 규칙을 정의한다.

README는 Repository를 처음 보는 사람이 다음 내용을 빠르게 이해할 수 있도록 작성한다.

```text
무엇을 위한 Repository인가
+
어디까지 구현했는가
+
어떤 기술을 사용했는가
+
무엇을 학습하거나 검증했는가
+
AI를 어떤 방식으로 사용했는가
+
어떻게 실행하는가
```

Repository의 성격에 따라 README 구성을 다르게 적용한다.

- Learning Repository
- Product Repository

---

## 1. Common Principles

README는 프로젝트를 과장하기 위한 문서가 아니라 실제 구현 범위와 의도를 정확하게 전달하기 위한 문서로 작성한다.

다음 원칙을 따른다.

- 구현하지 않은 기능을 구현한 것처럼 표현하지 않는다.
- 사용한 기술을 나열하는 것보다 프로젝트의 목적과 구현 범위를 우선한다.
- 학습용 Repository는 학습 목적과 검증 범위를 명확히 한다.
- 코드만 봐서는 알기 어려운 설계 판단과 실험 결과를 기록한다.
- AI 사용 방식은 Repository 이름의 `mode`와 일치시킨다.
- 실행 가능한 Repository는 최소 실행 방법을 제공한다.
- Secret, Password, API Key 등의 민감 정보는 기록하지 않는다.
- 외부 자료를 기반으로 구현한 경우 주요 출처를 남긴다.
- README 내용과 실제 Repository 상태가 다르지 않도록 유지한다.

---

## 2. Learning Repository README

Learning Repository는 기술 학습, 실습, 검증, 실험 및 포트폴리오 목적의 Repository에 사용한다.

기본적으로 다음 구조를 사용한다.

[`# Project Name`](#21-project-name)

[`## Overview`](#22-overview)  
[`## Focus`](#23-focus)  
[`## Tech Stack`](#24-tech-stack)  
[`## Scope`](#25-scope)  
[`## Implementation`](#26-implementation)  
[`## What I Learned`](#27-what-i-learned)  
[`## AI Usage`](#28-ai-usage)  
[`## How to Run`](#29-how-to-run)  
[`## References`](#210-references)

모든 항목을 반드시 사용할 필요는 없다.

다만 다음 항목은 가능한 한 유지한다.

```text
Overview
Scope
AI Usage
```

Repository Type에 따라 일부 Section을 다른 이름으로 변경하거나 추가할 수 있다.

---

## 2.1 Project Name

Repository의 이름을 그대로 반복하기보다 사람이 읽기 쉬운 프로젝트명을 사용한다.

예:

Repository:

```text
js-0001-manual-jwt-token-practice
```

README:

```text
# JWT Token Practice
```

Repository:

```text
ts-0001-ai-llm-from-scratch-playground
```

README:

```text
# LLM From Scratch Playground
```

---

## 2.2 Overview

프로젝트가 무엇을 위한 것인지 짧게 설명한다.

다음 내용을 중심으로 작성한다.

- 왜 만들었는가
- 무엇을 학습하거나 검증하는가
- Repository의 성격이 무엇인가

예:

```text
JWT의 Header, Payload, Signature 생성 과정을 직접 구현하며
토큰 생성 구조와 서명 원리를 확인하기 위한 연습 프로젝트다.
```

또는:

```text
Transformer 기반 언어 모델의 Tokenization, Training, Generation 과정을
TypeScript와 Node.js 환경에서 직접 실험하기 위한 Playground다.
```

프로젝트에서 다루는 주요 Topic을 명시할 필요가 있는 경우 `Overview` 하위에 `### Topics`로 작성한다.

`Topics`는 기본 README 구조의 별도 Section으로 추가하지 않으며, 필요하지 않은 경우 생략할 수 있다.

예:

```md
### Topics

- jwt
- hmac
- signature
```

---

## 2.3 Focus

Repository에서 중점적으로 다루는 학습, 구현, 검증 또는 관찰 대상을 작성한다.

Repository Type에 따라 표현 방식은 달라질 수 있지만, 다음 질문에 답할 수 있도록 작성한다.

```text
무엇을 다루는가?
무엇을 직접 확인하려는가?
어떤 결과를 이해하거나 관찰하려는가?
```

예:

```text
- JWT의 Header, Payload, Signature 생성 구조 이해
- Secret을 이용한 HMAC Signature 생성 과정 확인
```

```text
- Transformer의 Next Token Prediction 학습 과정 이해
- Tokenizer 설정에 따른 Token 분할 결과 비교
- Generation 설정에 따른 출력 결과 관찰
```

`Focus`는 구현 기능 목록보다 Repository에서 무엇을 이해하거나 검증하려는지를 중심으로 작성한다.

---

## 2.4 Tech Stack

프로젝트에서 실제로 사용한 주요 기술만 작성한다.

예:

```text
- JavaScript
- Node.js
- crypto
```

또는:

```text
- TypeScript
- Node.js
- React
- tiktoken
- TensorFlow.js
```

Framework, Runtime, Library를 과도하게 나열하지 않는다.

프로젝트 목적과 직접적인 관련이 없는 개발 도구까지 모두 나열하지 않는다.

---

## 2.5 Scope

구현한 범위와 구현하지 않은 범위를 명확하게 구분한다.

Learning Repository에서 특히 중요한 항목이다.

예:

```text
### Implemented

- JWT Header 구성
- JWT Payload 구성
- Base64URL Encoding
- Secret을 이용한 HMAC Signature 생성
- Header.Payload.Signature 형태의 Token 생성

### Not Implemented

- Login
- User Authentication
- Authorization
- Access Token / Refresh Token
- Token Rotation
- Authentication Middleware
```

Repository 이름이나 설명이 실제 구현 범위보다 과장되지 않도록 한다.

---

## 2.6 Implementation

핵심 구현 내용을 설명한다.

전체 코드를 README에 복사하기보다 다음 내용을 중심으로 정리한다.

- 주요 처리 흐름
- 핵심 구조
- 직접 구현한 부분
- 중요한 설계 선택
- 비교하거나 실험한 내용
- 구현 중 발견한 제약사항

필요한 경우 다음 표현을 사용할 수 있다.

- Architecture Diagram
- Sequence Diagram
- Flow Diagram
- Directory Structure
- 주요 코드 일부
- 실행 결과
- Benchmark 결과

---

## 2.7 What I Learned

구현 과정에서 실제로 이해하거나 확인한 내용을 기록한다.

단순한 기술 설명보다 프로젝트를 통해 직접 확인한 내용을 우선한다.

예:

```text
- JWT의 Secret은 Token 자체의 구성 요소가 아니라 Signature 생성에 사용된다.
- JWT는 Header.Payload.Signature 구조로 구성된다.
- Payload는 Encoding될 뿐 기본적으로 암호화되지 않는다.
```

또는:

```text
- Next Token Prediction에서는 Input과 Target이 한 Token 차이로 구성된다.
- Causal Mask를 사용해 미래 Token을 Attention 대상으로 포함하지 않는다.
- Tokenizer의 Vocabulary와 Embedding의 Vocabulary Size는 일치해야 한다.
```

---

## 2.8 AI Usage

Repository 이름의 `mode`와 연결하여 AI 사용 방식을 기록한다.

### manual

예:

```text
## AI Usage

Mode: manual

설계와 구현 코드는 직접 작성했다.
AI는 개념 확인, 기술 질문, 문서 탐색 및 작성한 코드 검토 등의
보조 목적으로만 사용했다.
```

### ai

예:

```text
## AI Usage

Mode: ai

Generative AI 또는 Coding Agent를 코드 생성, 반복 구현,
테스트 작성, Refactoring 등의 개발 과정에 사용했다.

생성된 결과는 직접 검토하고 수정했으며,
주요 설계 결정과 검증 내용은 README에 기록한다.
```

AI 사용 여부 자체보다 다음 내용을 명확히 하는 것을 우선한다.

```text
어디에 AI를 사용했는가
+
어떤 부분을 직접 판단했는가
+
생성된 결과를 어떻게 검토했는가
```

---

## 2.9 How to Run

다른 사람이 Repository를 Clone한 후 실행할 수 있도록 최소 실행 절차를 작성한다.

예:

```text
npm install
npm run dev
```

필요한 경우 다음 내용을 함께 작성한다.

- Runtime Version
- Package Manager
- Environment Variable
- Database
- External Service
- Build Command
- Test Command

Secret, API Key, Password 등의 실제 값은 README에 작성하지 않는다.

환경 변수가 필요한 경우 `.env.example` 사용을 권장한다.

예:

```text
DATABASE_URL=
API_KEY=
```

---

## 2.10 References

학습 또는 구현 과정에서 참고한 주요 자료를 기록한다.

예:

- 공식 문서
- 책
- 강의
- 기술 문서
- 논문
- 참고 Repository

강의나 기존 구현을 기반으로 작성한 경우 가능한 한 출처를 명확히 남긴다.

---

## 3. Learning Repository Type

Learning Repository는 Type과 관계없이 [2. Learning Repository README](#2-learning-repository-readme)의 공통 구조를 사용한다.

Type별로 별도의 README 구조를 만들지 않고, `Focus`, `Scope`, `Implementation`, `What I Learned`에서 강조하는 관점만 다르게 한다.

| Type         | Focus                                                           |
| ------------ | --------------------------------------------------------------- |
| `practice`   | 직접 구현하면서 기술이나 개념의 동작과 원리를 이해한다.         |
| `notes`      | 특정 문제나 기술을 코드 또는 실험으로 확인하고 결과를 정리한다. |
| `playground` | 입력값이나 설정을 직접 변경하면서 동작과 결과를 관찰한다.       |
| `study`      | 특정 개념을 학습하고 작은 예제를 통해 이해한 내용을 확인한다.   |

공통적으로 다음 흐름을 유지한다.

```text
무엇을 다루는가
        ↓
어디까지 구현하거나 검증하는가
        ↓
어떻게 구현하거나 확인했는가
        ↓
무엇을 이해하거나 확인했는가
```

Type은 README의 구조를 결정하기보다 Repository의 **학습 방식과 관점**을 표현한다.

예:

```text
practice
→ 직접 구현하여 이해

notes
→ 문제를 검증하고 결과 정리

playground
→ 값을 변경하며 결과 관찰

study
→ 개념을 학습하고 예제로 확인
```

새로운 Type이 추가되더라도 별도의 README 구조를 만들기보다 동일한 공통 구조 안에서 `Focus`를 정의한다.

---

## 4. Product Repository README

Product Repository는 Learning Repository와 달리 학습 과정보다 서비스의 목적, 구조, 실행 및 운영 정보를 우선한다.

기본적으로 다음 구조를 권장한다.

[`# Service Name`](#4-product-repository-readme)

[`## Overview`](#41-overview)  
[`## Features`](#42-features)  
[`## Architecture`](#43-architecture)  
[`## Tech Stack`](#44-tech-stack)  
[`## Project Structure`](#45-project-structure)  
[`## Getting Started`](#46-getting-started)  
[`## Configuration`](#47-configuration)  
[`## Deployment`](#48-deployment)  
[`## Operations`](#49-operations)  
[`## License`](#410-license)

필요한 경우 다음 Section을 추가한다.

```text
API Documentation
Database Schema
Monitoring
Troubleshooting
Security
Contributing
```

Product Repository에서는 서비스를 이해하고 실행하고 운영하는 데 필요한 정보를 우선한다.

---

## 4.1 Overview

서비스가 해결하려는 문제와 제공하는 기능을 간단하게 설명한다.

다음 내용을 중심으로 한다.

```text
누구를 위한 서비스인가
+
무엇을 할 수 있는 서비스인가
+
핵심 기능은 무엇인가
```

---

## 4.2 Features

사용자가 실제로 사용할 수 있는 주요 기능을 작성한다.

구현 예정 기능과 구현 완료 기능을 혼동하지 않는다.

구현 예정 기능을 작성할 경우 명확하게 구분한다.

---

## 4.3 Architecture

서비스의 주요 Component와 데이터 흐름을 설명한다.

예:

```text
Client
  ↓
Web
  ↓
API
  ↓
Database
```

필요한 경우 다음 내용을 포함한다.

- Web
- API
- Worker
- Database
- Cache
- Queue
- Object Storage
- External API
- Infrastructure

---

## 4.4 Tech Stack

서비스에서 실제로 사용하는 주요 기술을 영역별로 정리한다.

예:

```text
Backend
- Java
- Spring Boot

Frontend
- TypeScript
- React

Database
- PostgreSQL

Infrastructure
- Docker
- Terraform
```

프로젝트 목적과 직접적인 관련이 없는 개발 도구까지 과도하게 나열하지 않는다.

기술 이름만 나열하기보다 필요하다면 해당 기술의 역할을 함께 설명한다.

---

## 4.5 Project Structure

Monorepo 또는 Multi-module 구조에서 각 디렉터리의 역할을 설명한다.

예:

```text
service/
├─ apps/
│  ├─ web/
│  ├─ api/
│  └─ worker/
├─ packages/
└─ infra/
```

---

## 4.6 Getting Started

로컬 환경에서 서비스를 실행하기 위한 최소 절차를 작성한다.

가능하면 처음 보는 사람이 README만 보고 실행할 수 있도록 한다.

필요한 경우 다음 내용을 포함한다.

- Runtime Version
- Package Manager
- Build Command
- Run Command
- Database 준비
- Local Dependency

---

## 4.7 Configuration

필요한 환경 변수와 설정 항목을 설명한다.

실제 Secret 값은 포함하지 않는다.

환경 변수가 필요한 경우 `.env.example` 또는 동등한 예제 설정 파일을 제공한다.

---

## 4.8 Deployment

서비스가 어디에 어떻게 배포되는지 설명한다.

예:

```text
GitHub
  ↓
GitHub Actions
  ↓
Build / Test
  ↓
Deployment
```

Infrastructure as Code를 사용하는 경우 Terraform, Ansible, Docker, Kubernetes, Helm 등의 역할을 함께 설명할 수 있다.

---

## 4.9 Operations

운영 중 필요한 내용을 기록한다.

예:

- Health Check
- Logging
- Monitoring
- Alert
- Backup
- Rollback
- 장애 대응

서비스 규모에 따라 필요하지 않은 항목은 생략할 수 있다.

---

## 4.10 License

Repository에 적용되는 License를 명시한다.

Open Source License를 사용하는 경우 License 이름과 `LICENSE` 파일을 연결한다.

예:

```text
MIT License
```

개인 포트폴리오 또는 공개 소스 Repository라도 재사용 조건을 명확하게 하고 싶다면 적절한 License를 선택한다.

별도의 License를 부여하지 않는 경우에는 해당 사실을 명확하게 유지하며, 필요하지 않다면 이 Section은 생략할 수 있다.

---

## 5. README Status

README는 Repository의 실제 상태와 함께 유지한다.

Repository 구현 상태가 변경되면 README도 함께 수정한다.

예:

```text
기능 추가
→ Features / Scope 갱신

Architecture 변경
→ Architecture 갱신

새로운 환경 변수 추가
→ Configuration 갱신

AI 사용 방식 변경
→ AI Usage 갱신
```

README를 최초 작성 이후 방치하지 않고 Repository의 현재 상태를 나타내는 문서로 유지한다.

---

## 6. Writing Style

README는 간결하고 명확하게 작성한다.

다음 기준을 권장한다.

- 긴 문단보다 짧은 설명과 구조화된 Section을 사용한다.
- 기술명은 실제 사용한 명칭을 정확하게 작성한다.
- 불필요한 수식어나 과장된 표현을 피한다.
- 단순한 코드 설명보다 설계 이유와 검증 결과를 우선한다.
- 필요한 경우 표, Diagram, 코드 블록을 활용한다.
- 동일한 의미를 여러 Section에서 반복하지 않는다.
- 영어 기술 용어는 일반적으로 사용되는 표기를 유지한다.

README는 코드의 대체물이 아니라 코드만으로 전달하기 어려운 **목적, 범위, 판단, 결과**를 설명하는 문서로 작성한다.
