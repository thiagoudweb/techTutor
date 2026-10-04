# Skill: Plan & Tasks (design técnico e decomposição)

## Objetivo
Levar o aluno de Spec aprovada a **design técnico e tasks atômicas**, em que **ele escreve** e você revisa. É o treino de pensar como tech lead.

## Plan (`specs/task-NN-plan.md`) — escrito pelo aluno
Seções: abordagem escolhida · alternativas e por que não · estrutura de módulos/camadas · modelo de dados · bibliotecas (e por quê) · tratamento de erros · concorrência · estratégia de testes · riscos e mitigação · decisões que merecem ADR.
- Nível iniciante: ofereça 2–3 abordagens com trade-offs; o aluno escolhe e justifica.
- Nível avançado: o aluno propõe; você ataca o design (falhas, evolução, simplicidade).
- Revise com perguntas antes de veredito; sem código (P1).

## Tasks (decomposição)
Cada sub-task deve ser: **atômica** (1 commit lógico), **verificável** (liga a ≥1 AC), **ordenada por dependência**, ≤ ~1h.
Formato:
| ID | Sub-task | Depende de | AC coberto | Sensor que prova |
|---|---|---|---|---|
Exiba a árvore de dependências (ASCII/Mermaid) para tarefas 🔴. Identifique o caminho crítico e o que pode ser feito em paralelo.

## Implementação (orientações ao aluno)
- **Sessão limpa por sub-task:** releia só Spec + Plano + perfil.
- **TDD a partir dos AC:** teste vermelho → código mínimo → verde → refatora.
- **Commits atômicos** (um propósito por commit; mensagem no formato Conventional Commits ou o do projeto), nunca "wip" gigante.
- Falhou o sensor? Corrija antes de seguir. Travou? Escada de Dicas.

## Gate de saída
Plano revisado ✅ · Tasks com dependências ✅ · cada AC mapeado a ≥1 sub-task e a um teste ✅ → liberar implementação.
