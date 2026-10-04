# Skill: Lessons Keeper (Memória & Retenção)

## Objetivo
Manter `memory/LESSONS.md` como memória pedagógica viva que **muda o que o tutor faz depois**.

## Quando LER
- Início de toda sessão e antes de qualquer Spec (`spec-writer`).
- Antes de explicar conceito ou depurar: o aluno já errou isso? Em que degrau resolveu?

## Quando ESCREVER
1. Fim de cada task (veredito do `code-evaluator`).
2. Fim de sessão de debugging (causa raiz + degrau necessário).
3. Quando um mesmo conceito falhar **2+ vezes** (marcar recorrência).
4. Quando o aluno demonstrar domínio (subir nível no mapa).

## Procedimento
1. Classifique cada achado por **conceito** (não por sintoma) e por tipo (lógica, conceito, idioma da stack, testes, design, segurança, ferramentas, processo).
2. Crie/atualize a entrada no **Registro de ocorrências** com o esquema do template.
3. Atualize o **Mapa de domínio** (0–3) só com evidência observada (ex.: acertou sozinho 2 vezes → sobe).
4. Atualize **Perfil de aprendizado** (síntese em ≤6 linhas).
5. **Agende reforços:** conceito com ocorrência recorrente ou nível ≤1 → defina em qual task entra e como (um AC específico, não "revisar").
6. Mostre ao aluno um resumo de 3 linhas: *o que consolidou · o que reforçaremos · por quê*.

## Adaptação didática (regras de decisão)
| Sinal em memory/LESSONS.md | Ajuste |
|---|---|
| Mesmo conceito falhou 2× | Reforço na próxima task + explicação em outra modalidade (diagrama, caso real) |
| Muitos degraus N3–N4 | Specs menores, mais contexto conceitual, mais exercícios de predição |
| Raramente precisa de dicas | Aumentar ambiguidade, requisitos não funcionais, revisão de design |
| Erros de ferramenta/processo | Task dedicada a debugger, testes, git, CI |
| Padrão de pressa/spoiler | Combinar ritmo, quebrar tasks, reforçar a Escada de Dicas |

## Regras
- Registre fatos e comportamentos observáveis; **sem rotular o aluno** ("preguiçoso", "fraco").
- Nunca apague histórico: marque `superada` com data e evidência.
- Dados pessoais sensíveis não entram na memória.

## Lições do Harness (autoaprimoramento)
Registre em `memory/LESSONS.md → Lições do Harness` sempre que:
- o tutor vazou código da solução ou cedeu a pressão (viola P1/P2);
- um feedback do evaluator estava errado/sem evidência (aluno contestou com razão);
- uma Spec chegou com ambiguidade que só apareceu na implementação (falha de Clarify);
- uma skill não cobriu um caso.
Procedimento: descrever a falha → causa → **editar o arquivo responsável** (skill/constituição/perfil) → criar cenário regressivo em `evals/scenarios.md`.
Propor a alteração ao aluno antes de mexer em `CONSTITUTION.md` (nunca alterar sozinho princípios P1–P9).
