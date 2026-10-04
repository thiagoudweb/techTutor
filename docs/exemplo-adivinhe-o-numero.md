# Exemplo de uso: jogo "Adivinhe o número" (Python)

> Simulação ilustrativa do comportamento esperado do tutor, **não** uma execução real. As saídas de ferramentas abaixo são exemplos inventados. Os diagramas do fluxo estão no [README](../README.md#-fluxo-visual-do-tutor).

**O jogo:** programa de terminal que sorteia um número de 1 a 100, dá 7 tentativas e responde "maior" ou "menor" a cada palpite.

## Passo 0 — Boot (início da sessão)
O tutor lê `CONSTITUTION.md`. Como `memory/HANDOFF.md`, `memory/LESSONS.md` e `PROJECT.md` não existem, ele os cria a partir de `templates/`. Com o `PROJECT.md` vazio, aciona o `stack-architect`.

## Passo 1 — Stack e roadmap
> **Tutor:** Qual é a ideia, que linguagem você já conhece e quanto tempo tem por semana?
> **Aluno:** Um jogo de terminal em Python, sou iniciante, umas 5 horas por semana.

O aluno já escolheu Python, então o tutor apenas valida a escolha. Ele propõe `pytest`, `ruff` e `mypy` como ferramentas e espera o "confirmo". Depois grava:
- `adr/0001-stack.md` e `stacks/python.md` (via `harness-builder`);
- `PROJECT.md` com o roadmap: M1 lógica do jogo · M2 loop e entrada do usuário · M3 recorde em arquivo · M4 argumentos de linha de comando.

## Passo 2 — Specify (Task 01, tamanho 🟢 pequena)
O `spec-writer` escreve a Spec com motivação, "porquê" e critérios de aceite (EARS):
- **AC1** Quando o palpite for menor que o número secreto, o jogo deve responder "maior".
- **AC2** Quando o palpite for maior, deve responder "menor".
- **AC3** Quando for igual, deve responder "acertou".
- **AC4** Se o palpite estiver fora de 1 a 100, então o jogo deve… *(indefinido: vai para o Clarify)*

O contrato diz apenas "recebe dois inteiros e devolve um de três resultados" — sem corpo de função, pois o tutor nunca escreve a solução. Conceito-alvo: separar a lógica de decisão da entrada e saída.

## Passo 3 — Clarify e gate de compreensão
O tutor lista as suposições abertas e o aluno decide:
1. Palpite fora do intervalo gasta tentativa? *Não, é erro de entrada.*
2. E se digitarem texto? *Mostra aviso e pede de novo (Task 02).*
3. O resultado é texto ou enumeração? *Texto simples por enquanto.*

Com 0 suposições abertas, a Spec é liberada. Antes de começar, o tutor pergunta: "Por que a decisão não deve imprimir nem ler do teclado?" Se a explicação for fraca, aciona o `concept-explainer`.

## Passo 4 — Plan e tasks
A Task 01 é 🟢, então o plano é pulado (Auto-Sizing). Na Task 02 (🟡) o aluno escreveria um plano curto, revisado pelo tutor com perguntas.

## Passo 5 — Implement (só o aluno)
O aluno escreve primeiro os testes a partir dos AC (vermelho), depois o código (verde), com commits pequenos: `test: cobre palpite menor`, `feat: compara palpite`.

## Passo 6 — Travou (Task 02, entrada do usuário)
O aluno cola o erro `TypeError: '>' not supported between instances of 'str' and 'int'`. O `debugging-coach` traduz: "você comparou texto com número". Depois sobe a Escada de Dicas, um degrau por vez:
- **N1:** "Que tipo de valor a leitura do teclado devolve? Como você confirmaria sem mudar o programa?"
- **N2:** o conceito de tipos e conversão, com um termo de busca.
- **N3:** a falha aparece na linha da comparação, mas nasce onde o valor entra.
- **N4:** passos em prosa (converter antes de comparar e decidir o que fazer se não for número), sem código.

Termina com 2 perguntas-guia e pede que o aluno explique a causa raiz com as próprias palavras.

## Passo 7 — Validate
O aluno diz "terminei". O tutor responde "mostre as evidências do Gate de Pronto", e os sensores rodam. O verificador, em contexto limpo, devolve algo como:

> **Veredito: aprovado com ressalvas.** Sensores verdes, todos os AC cobertos.
> 🟠 `test_jogo.py:12` — os testes não discriminam o limite: ao inverter a condição de propósito, nenhum teste falha.
> Pergunta-guia: que valor de entrada distingue "menor que" de "menor ou igual"?

O aluno adiciona o teste de borda e reenvia. O verificador confere cada achado anterior e o veredito vira **aprovado**.

## Passo 8 — Lições e próximo ciclo
O `lessons-keeper` atualiza `memory/LESSONS.md`:
- "tipos e conversão de entrada" sobe do nível 1 para 2 (precisou do N2);
- "teste de borda" é registrado como 1ª ocorrência;
- reforço agendado para a Task 03, com um AC específico de validação e valor de borda.

Atualiza também `memory/HANDOFF.md` e sugere uma sessão limpa. A próxima Spec nasce adaptada a essas lacunas, e o ciclo recomeça no Specify.
