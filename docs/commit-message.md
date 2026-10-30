# Commit Convention

- Planned

## Message Format

기본 형식:

```text
<type>: <description>
```

Step 단위로 개발하는 프로젝트에서는 다음 형식을 사용할 수 있다.

```text
<type>: [step-XX] <description>
```

- Step 번호는 해당 프로젝트에서 필요할 때만 사용한다.
- Commit Type은 작업의 성격에 따라 선택한다.
- Description은 영어로 간결하게 작성한다.

## Type

| Type     | Description                          |
| -------- | ------------------------------------ |
| setup    | 프로젝트 초기 구성 및 개발 환경 설정 |
| docs     | 문서 변경                            |
| feat     | 기능 추가                            |
| fix      | 오류 수정                            |
| refactor | 동작 변경 없는 구조 개선             |
| test     | 테스트 추가 및 수정                  |

## Examples

일반적인 Commit:

```text
docs: add repository conventions
feat: add JWT token generation
fix: correct token signature validation
refactor: simplify tokenizer implementation
test: add JWT signature tests
```

Step 단위 Commit:

```text
setup: [step-01] initialize TypeScript client and server
setup: [step-02] validate SFU environment
feat: [step-03] implement WebSocket sessions and profiles
feat: [step-04] implement meeting rooms
fix: [step-04] correct room state synchronization
docs: [step-04] update meeting room documentation
```

## Notes

- 현재는 임시 규칙이며, 프로젝트를 진행하면서 보완한다.
- 하나의 Step에서 여러 Commit을 작성할 수 있다.
- Step 번호는 Commit Type과 별개로 개발 진행 단계를 식별하기 위한 용도다.
