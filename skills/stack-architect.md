# Skill: Stack Architect

## Objetivo
Transformar uma ideia (ou a falta dela) em **projeto + stack + roadmap** decididos com o aluno, e registrá-los em `PROJECT.md` e `adr/0001-stack.md`. Nenhuma Task 1 é gerada antes da confirmação explícita.

## Gatilhos
Primeira sessão · `PROJECT.md` vazio · "que stack usar?" · mudança de projeto.

## Workflow
1. **Descoberta (máx. 5 perguntas, uma por vez, pule o que já é conhecido):**
   - Qual problema/ideia e para quem? Qual o resultado final desejado?
   - Tipo: CLI, API REST, Sistema Distribuído, Automação, IA/Agentes, Web/Mobile, Dados, Embarcado, Outro.
   - Linguagens que já conhece e nível; preferência ou restrição de stack?
   - Objetivo de aprendizado (ex.: concorrência, arquitetura, mercado, performance) e tempo semanal?
   - Restrições: prazo, infra/custo, deploy, compliance.
2. **Se o aluno já tem stack:** valide a adequação ao projeto. Se houver incompatibilidade grave, apresente o risco com evidência e deixe a decisão com ele.
3. **Se pedir recomendação:** proponha **2–3 stacks** (nunca 1, nunca mais de 3). Para cada uma:
   - Composição (linguagem, framework, banco, infra, testes).
   - **Prós / contras no contexto deste projeto**, não genéricos.
   - Curva de aprendizado vs. o nível dele; ecossistema de testes e tooling.
   - O que ela **ensina** de mais valioso (conceitos que o aluno ganha).
   - Risco principal e como mitigar.
   Termine com uma recomendação **justificada**, deixando claro que a decisão é dele.
4. **Aguarde confirmação explícita** ("vamos com a Stack B").
5. **Registre:**
   - `PROJECT.md` preenchido.
   - `adr/0001-stack.md` (Contexto · Decisão · Alternativas rejeitadas · Consequências).
   - Verifique se existe `stacks/<stack>.md`; se não, acione `harness-builder`.
6. **Roadmap macro:** 4–8 marcos incrementais (cada um entrega algo executável), mapeados a conceitos-alvo. Peça aprovação.
7. Só então acione `spec-writer` para a Task 1.

## Formato do ADR
```
# ADR-0001: Escolha de stack
Status: Aceito | Data: YYYY-MM-DD
Contexto: ...
Decisão: ...
Alternativas consideradas: A (por que não) · B (por que não)
Consequências: positivas · negativas · riscos · critério de revisão
```

## Anti-padrões (não faça)
- Escolher a stack mais "da moda" sem ligar ao projeto/objetivo.
- Despejar 5+ opções. Recomendar sem trade-offs. Gerar Task 1 sem confirmação.
- Gerar boilerplate/scaffold com código (viola P1): descreva a estrutura em prosa, o aluno cria.
