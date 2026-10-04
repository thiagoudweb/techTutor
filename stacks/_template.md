# Perfil de Stack: <Linguagem + Ecossistema>
> Copie este arquivo para `stacks/<nome>.md`. O `harness-builder` ajuda a preencher.
> Tudo o que é específico de linguagem mora AQUI; as skills permanecem genéricas.

## Toolchain (comandos exatos que o tutor executa como sensores)
| Função | Comando | Falha bloqueia aprovação? |
|---|---|---|
| Formatar (check) | `<ex: gofmt -l . / ruff format --check / cargo fmt --check>` | Não (sugestão) |
| Lint | `<ex: golangci-lint run / ruff check / cargo clippy -- -D warnings>` | Sim se erro de correção/segurança |
| Tipos | `<ex: mypy --strict / tsc --noEmit>` | Sim |
| Testes | `<ex: go test -race ./... / pytest -q / cargo test>` | Sim |
| Cobertura | `<comando>` — meta: <n>% | Não (informativo) |
| Segurança | `<ex: gosec / bandit / cargo audit / npm audit>` | Sim se severidade alta |
| Mutação (testes discriminantes) | `<ex: mutmut / cargo-mutants / go-mutesting / Stryker>` ⚠️ verificar | Não (informativo; manual se não houver ferramenta) |
| Pre-commit / CI | `<ex: pre-commit run -a / make ci>` | Sim |

## MCP / ferramentas recomendadas para esta stack (ver tools/MCP.md)
- <servidor/ferramenta> — finalidade — modo: leitura | escrita (confirmação)

## Convenções oficiais (fonte de verdade)
- Guia de estilo: <PEP 8 | Effective Go + Code Review Comments | Rust API Guidelines | Google Java Style ...>
- Nomenclatura / estrutura de projeto: <...>
- Gerenciador de dependências e versionamento: <...>

## Idiomas centrais que o tutor deve cobrar
- Tratamento de erros: <ex: retorno `error` e wrapping | exceções específicas | `Result<T,E>`>
- Concorrência: <goroutines/channels | asyncio | threads/Tokio ...> e armadilhas típicas
- Gestão de memória/recursos: <defer/RAII/context managers/ownership ...>
- Testabilidade: <table-driven | fixtures/parametrize | traits/mocks ...>
- Padrões de design naturais da stack e anti-padrões comuns

## Armadilhas clássicas (alimentam checklists do evaluator e do debugging coach)
1. <...>
2. <...>

## Trilha de conceitos (ordem sugerida, pré-requisitos → avançado)
1. <...> → 2. <...> → 3. <...>

## Fontes oficiais
- <doc oficial, spec da linguagem, guia de estilo>
