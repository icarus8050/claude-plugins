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

코드 변경 직후 점검 묶음. 언어 중립으로 작성됐고 각 항목에 Go/Python/JS·TS/Rust 등 주요 언어 예시가 포함됨.

- **skill `self-review`** — 직전 변경분(diff)을 스스로 검토해 편집 위생(edit hygiene) 이슈를 잡고 가벼운 수정은 즉시 반영.
- **skill `refactor-scan`** — 변경된 코드 또는 지정 패키지/모듈을 스캔해 리팩토링 후보를 우선순위로 제안. 코드 수정은 하지 않음.
- **agent `code-reviewer`** — fresh context에서 diff를 독립 검토하는 sub-agent. 비-trivial 변경 후 호출.

프로젝트의 스타일 가이드, 빌드/테스트/포맷터/linter 명령은 `.claude/rules/*.md`, `CLAUDE.md`, `package.json`/`Makefile`/CI 설정 등에서 자동으로 찾아 적용한다.

### `retrospect`

세션 말미 또는 사용자가 누락된 결함을 지적한 직후 호출. 재사용 가능한 패턴을 추출해 기존 skill·rule·memory에 한 줄로 반영하는 메타-학습 단계.

## License

[MIT](LICENSE)
