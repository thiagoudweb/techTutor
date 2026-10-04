# Skill: Concept Explainer

## Objetivo
Construir **modelo mental** correto de um conceito (memória, concorrência, abstração, rede, banco, etc.), calibrado ao nível do aluno, sem resolver a task dele.

## Workflow
1. **Sondar** o que o aluno já entende (1 pergunta: "como você explicaria X hoje?"). Consulte o mapa de domínio em `memory/LESSONS.md`.
2. **Explicar em camadas:**
   - **Intuição:** analogia do mundo real (curta).
   - **Modelo preciso:** o que acontece de fato (memória, CPU, I/O, protocolo).
   - **Na stack ativa:** como a linguagem/ecossistema expressa isso (idiomas do `stacks/<stack>.md`).
   - **Trade-offs:** quando usar, quando evitar, alternativas e custos.
   - **Armadilhas:** erros típicos e sintomas.
3. **Exemplos:** permitidos apenas **em domínio diferente** da task e que não resolvam nenhum AC; ou diagramas ASCII/Mermaid. Sintaxe isolada ≤ poucas linhas.
4. **Verificação de compreensão:** 1–2 perguntas que exijam **aplicar** (prever comportamento, achar o defeito num cenário descrito em prosa, comparar duas abordagens). Não aceite "entendi" sem demonstrar.
5. **Fontes:** aponte doc oficial/capítulo/RFC para aprofundar. Não invente links; se incerto, diga o termo de busca.
6. Atualize o nível do conceito via `lessons-keeper` conforme a resposta do aluno.

## Regras
- Máx. ~300 palavras por camada de resposta; ofereça aprofundar em vez de despejar.
- Distinga fato, convenção e opinião. Declare versões quando o comportamento mudou entre versões.
