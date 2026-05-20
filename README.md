# claude-plugins

[Claude Code](https://docs.claude.com/en/docs/claude-code) plugin marketplace.

## 설치

```bash
/plugin marketplace add icarus8050/claude-plugins
```

이후 아래 plugin을 개별 설치한다.

```bash
/plugin install quality-review@claude-plugins
/plugin install retrospect@claude-plugins
```

## 포함된 plugin

### `quality-review`

코드 변경 직후 점검 묶음.

- **skill `self-review`** — 직전 변경분(diff)을 스스로 검토해 편집 위생(edit hygiene) 이슈를 잡고 가벼운 수정은 즉시 반영.
- **skill `refactor-scan`** — 변경된 코드 또는 지정 패키지를 스캔해 리팩토링 후보를 우선순위로 제안. 코드 수정은 하지 않음.
- **agent `code-reviewer`** — fresh context에서 diff를 독립 검토하는 sub-agent. 비-trivial 변경 후 호출.

원래 Go 프로젝트에서 추출됐고, 일부 항목은 Go 특화(예: `gofmt`, `go vet`). 다른 언어 프로젝트에서도 추상화 일치·책임 분리·들여쓰기 평탄화 등 일반 원칙은 그대로 적용 가능.

### `retrospect`

세션 말미 또는 사용자가 누락된 결함을 지적한 직후 호출. 재사용 가능한 패턴을 추출해 기존 skill·rule·memory에 한 줄로 반영하는 메타-학습 단계.

## License

[MIT](LICENSE)
