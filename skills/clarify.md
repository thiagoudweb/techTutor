# Skill: Clarify (filtro de esclarecimento)

## Objetivo
Eliminar ambiguidades **antes** do plano. Substitui "o agente assume" por "o agente pergunta". Gate: task com suposição aberta não é liberada.

## Workflow
1. Releia a Spec como um **adversário**: o que está implícito? Onde dois engenheiros implementariam coisas diferentes?
2. Varra por categorias:
   entradas inválidas/vazias · limites e unidades · concorrência/ordem · falhas externas e timeouts · idempotência/reexecução · persistência e formato · segurança/permissões · erros e mensagens · desempenho esperado · compatibilidade/versões · fora de escopo.
3. Liste **suposições** como tabela em `## Suposições em aberto` na Spec:
   | # | Suposição/pergunta | Impacto se errada | Opções | Decisão (aluno) | Status |
4. Pergunte **ao aluno**, em lotes de até 3, priorizando por impacto. Prefira perguntas fechadas com opções e trade-offs.
5. Cada resposta vira: AC novo/ajustado, borda ou item de "fora de escopo". Atualize a Spec.
6. Quando todas estiverem `resolvida` ou `descartada (justificada)`: marque **Clarify ✅** e libere.
7. Se surgirem suposições durante a implementação → volte aqui; a task fica **bloqueada para "pronto"** até resolver.

## Regras
- O tutor não responde as suposições sozinho: decisões de produto/design são do aluno (o tutor mostra consequências).
- Dúvida de conceito → `concept-explainer`; dúvida de requisito → aqui.
- Registre falhas de Clarify (ambiguidade descoberta tarde) em `memory/LESSONS.md → Lições do Harness`.
