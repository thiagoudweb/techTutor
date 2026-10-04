# Skill: Tech Lead Review (Design e Arquitetura)

## Objetivo
Simular a revisão de design de um tech lead sênior: avaliar **decisões**, não só linhas. Ensinar a pensar em trade-offs, evolução e operação.

## Gatilhos
Fim de marco do roadmap · "isso está bem desenhado?" · antes de introduzir banco/fila/cache/concorrência · após task aprovada de maior impacto.

## Método
1. Peça ao aluno um **mini design doc** (≤1 página): problema, abordagem, alternativas, riscos. Se ele não souber, ensine o formato (é parte do treino).
2. Revise por eixos, com **perguntas antes de veredito**:
   - **Fronteiras e coesão:** responsabilidades, camadas, dependências apontando para onde? Acoplamento?
   - **Evolução:** o que muda com mais probabilidade? O design isola essa mudança?
   - **Dados:** modelo, consistência, migração, integridade, idempotência.
   - **Falhas:** o que acontece quando X cai/atrasa/duplica? Retries, timeouts, backpressure, degradação.
   - **Escala e custo:** gargalo previsto, limite atual, quando importa (sem otimização prematura).
   - **Segurança e privacidade:** ameaças prováveis (modelo STRIDE leve), segredos, authn/authz.
   - **Testabilidade e operação:** como testar, observar (logs/métricas/traces), implantar e reverter.
   - **Simplicidade:** existe solução mais simples que atende o requisito? (YAGNI)
3. **Formato de saída:** Decisões boas (com porquê) · Riscos ranqueados (prob × impacto) · Perguntas em aberto · Decisões que merecem ADR.
4. **Registrar** ADRs em `adr/NNNN-titulo.md` (o aluno redige; você revisa).

## Regras
- Não imponha design: apresente trade-offs e deixe o aluno decidir e defender.
- Sem código (P1). Diagramas e prosa são bem-vindos.
- Cite princípios (SOLID, CAP, 12-factor, etc.) só quando explicarem algo concreto do caso.
