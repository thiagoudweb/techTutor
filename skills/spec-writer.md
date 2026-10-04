# Skill: Spec Writer (Specify) + Auto-Sizing

## Objetivo
Produzir a **Spec** de cada task: clara, verificável, calibrada ao nível do aluno e às lacunas de `memory/LESSONS.md`. É o contrato que o `code-evaluator` usará. Após escrever, **sempre** acione `clarify`.

## Entradas
`PROJECT.md` (roadmap) · `memory/LESSONS.md` (reforços, mapa de domínio) · `stacks/<stack>.md` (trilha, idiomas) · veredito anterior · `research/` relevante.

## Auto-Sizing (dimensionamento do fluxo)
| Tamanho | Critério | Fluxo |
|---|---|---|
| 🟢 Pequena | ≤3 arquivos, conceito já nível ≥2, sem decisão de design | Spec mínima (motivação, contrato, AC, bordas) → Clarify rápido → Implement → Validate |
| 🟡 Média | 4–8 arquivos ou conceito novo | Spec completa → Clarify → Plan curto → Implement → Validate |
| 🔴 Grande / marco | Nova camada, dados, concorrência, integração | Spec completa → Clarify → Plan → Tasks (dependências) → Implement por task → Validate → Convergência + Review |
Na dúvida entre tamanhos, escolha o maior e diga o motivo.

## Calibração de dificuldade
- Conceito-alvo nível 0–1 → escopo menor, mais contexto conceitual. Nível 2 → escopo médio, menos pistas. Nível 3 → mais ambiguidade controlada e requisitos não funcionais.
- Sempre incluir **1 critério de reforço** de lacuna aberta em `memory/LESSONS.md`.
- Uma task = 1 a 3 horas e **1 conceito novo principal**.

## Template (salvar em `specs/task-NN.md`)
```
# Task NN — <título>          Tamanho: 🟢|🟡|🔴
## Motivação e "porquê" (como a indústria resolve este problema)
## Conceitos-alvo (Novo / Reforço)
## Contexto e pré-requisitos (leituras: docs oficiais)
## Escopo / Fora de escopo
## Contrato (I/O)  — entradas, saídas, formatos, erros, assinaturas/interfaces (só contrato, nunca corpo)
## Critérios de Aceite (verificáveis) — use EARS ou Dado/Quando/Então
- [ ] AC1 [EARS] Quando <evento>, o <sistema> deve <resposta>.
- [ ] AC2 [GWT] Dado <contexto>, quando <ação>, então <resultado observável>.
- (EARS: Ubíquo "O sistema deve…" · Evento "Quando…" · Estado "Enquanto…" · Indesejado "Se… então…" · Opcional "Onde…")
## Casos de borda obrigatórios
## Requisitos não funcionais (metas mensuráveis: p95, memória, segurança, logs)
## Estratégia de testes (o aluno escreve; derive testes dos AC antes do código — TDD)
## Suposições em aberto  ← preenchida pelo Clarify; deve terminar VAZIA
## Definição de Pronto
AC ok · sensores verdes (com evidência) · testes discriminantes (mutação) · suposições = 0 · commits atômicos · LESSONS atualizado
## Rubrica de avaliação (Bloqueante / Importante / Sugestão)
## Dicas preparadas (Escada N1–N2)
```

## Regras
- Cada AC testável **sem interpretação subjetiva**: "rápido" → "p95 < X ms para N itens".
- Nunca inclua corpo de função, algoritmo em código ou testes completos da solução (P1).
- Salve em `specs/` e atualize o roadmap em `PROJECT.md`.
- **Gate de compreensão (passo 4 do estudo):** antes de liberar, peça ao aluno que explique com as próprias palavras o "porquê" e os pré-requisitos. Se não conseguir, acione `concept-explainer` e reavalie.
- **Não libere a task** até: Clarify concluído + aluno aprovou + suposições abertas = 0.
