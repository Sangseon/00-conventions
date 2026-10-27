# Conventions

Repository 관리 및 작성 규칙을 정리한다.

각 Convention은 별도의 문서로 관리하며, 현재 적용 상태와 마지막 수정 일자를 함께 기록한다.

## Convention List

| Convention                                                            | Description                                    | Status  | Last Updated |
| --------------------------------------------------------------------- | ---------------------------------------------- | ------- | ------------ |
| [Repository Naming Convention](./docs/repository-naming.md)           | Repository 분류 및 이름 작성 규칙              | Active  | 2026-10-27   |
| [Repository README Convention](./docs/repository-readme.md)           | 각 Repository의 `README.md` 작성 규칙          | Active  | 2026-10-27   |
| [Project Classification Convention](./docs/project-classification.md) | 프로젝트의 Category 및 Topic 분류 규칙         | Active  | 2026-10-27   |
| [Commit Convention](./docs/commit-message.md)                         | Commit Message 작성 및 관리 규칙               | Planned | -            |
| [Branch Convention](./docs/branch-naming.md)                          | Branch 생성 및 Naming 규칙                     | Planned | -            |
| [Project Structure Convention](./docs/project-structure.md)           | Repository 내부 디렉터리 및 프로젝트 구조 규칙 | Planned | -            |

## Status

Convention 문서는 다음 상태를 사용한다.

```text
Planned
   ↓
Draft
   ↓
Active
```

| Status    | Description                                                           |
| --------- | --------------------------------------------------------------------- |
| `Planned` | 작성할 Convention으로 등록했지만 아직 문서를 작성하지 않은 상태       |
| `Draft`   | Convention을 작성하거나 검토 중이며 아직 최종 적용하지 않은 상태      |
| `Active`  | 현재 Repository 관리 및 개발 과정에서 실제로 적용하고 있는 Convention |

필요한 경우 향후 다음 상태를 추가할 수 있다.

| Status       | Description                                                          |
| ------------ | -------------------------------------------------------------------- |
| `Deprecated` | 더 이상 사용하지 않으며 다른 Convention으로 대체되었거나 폐기된 상태 |

## Directory Structure

```text
00-conventions/
├─ README.md
└─ docs/
   ├─ repository-naming.md
   ├─ repository-readme.md
   ├─ project-classification.md
   ├─ commit-message.md
   ├─ branch-naming.md
   └─ project-structure.md
```

새로운 Convention이 필요해지면 먼저 `Planned` 상태로 목록에 추가하고, 문서 작성을 시작할 때 `Draft`, 실제 적용을 시작할 때 `Active`로 변경한다.

`Last Updated`는 해당 Convention 문서의 내용이 마지막으로 변경된 날짜를 `YYYY-MM-DD` 형식으로 기록한다.
