![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Do algoritmo ao programa

Ficha do tema Do algoritmo ao programa, do módulo Desenvolver programas em linguagem estruturada. Praticas a passagem de um algoritmo para Python, a previsão do que um programa escreve e o reconhecimento dos três tipos de erro. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](01-do-algoritmo-ao-programa.md) e o [laboratório](01-do-algoritmo-ao-programa-laboratorio.md).

## Como trabalhar

Faz os exercícios pela ordem. Os exercícios 1 a 5 são obrigatórios. O desafio opcional e o "Para ires mais longe" são para quem acabar.

Trabalha na tua pasta `lp-python`, no VS Code, e usa o comando que tens no registo da execução. Escreve no caderno as previsões, os resultados esperados e as respostas. Escreve sempre a previsão antes de correres o programa, e não a mudes depois: é ela que mostra o que já percebeste.

## Exercício 1: Prever o ecrã

Este programa mostra o placar de um jogo de basquetebol da escola:

```python
# placar.py: o placar de um jogo de basquetebol da escola.
print("JOGO #3")
print("Casa contra visitantes")
print("Placar: 0 a 0")
```

1. Sem correres o programa, escreve no caderno o que aparece no ecrã, linha a linha.
2. Cria o ficheiro `placar.py` na tua pasta, com este conteúdo, e corre-o. Compara o que apareceu com a tua previsão. Se forem diferentes, explica numa frase em que te enganaste.

## Exercício 2: Do pseudocódigo ao programa

Um colega escreveu o algoritmo do menu de um jogo. Na segunda linha, em vez de três `Escreve:`, escreveu uma frase clara, como se aceitava na algoritmia:

```text
Escreve: "MENU PRINCIPAL"
Escreve as três opções, numeradas de 1 a 3, uma por linha: Jogar, Ver as regras e Sair
Escreve: "Escolhe uma opção."
```

1. Escreve no caderno o resultado esperado: o que o programa deve mostrar no ecrã, linha a linha, com o texto exato de cada linha. A forma da numeração decides tu.
2. Escreve o programa em Python, no ficheiro `menu.py`, com o comentário no início.
3. Corre-o e compara o que apareceu com o resultado esperado, linha a linha.

## Exercício 3: Que tipo de erro?

Uma colega escreveu o anúncio do campeonato de matraquilhos da escola. O resultado esperado é este:

```text
CAMPEONATO DA ESCOLA
Matraquilhos
Equipas de dois jogadores.
```

Fez três versões do programa, e nenhuma dá o resultado esperado. Para cada versão, tens o programa e o que apareceu no terminal. Responde no caderno:

- que tipo de erro é: de sintaxe, de execução ou de lógica;
- em que linha está o erro, e como o soubeste;
- como se corrige.

Versão A:

```python fragment erro de propósito: o exercício pede que o aluno o encontre
# campeonato.py: o anúncio do campeonato de matraquilhos da escola.
print("CAMPEONATO DA ESCOLA")
print("Matraquilhos")
print("Equipas de dois jogadores."
```

```text
  File "C:\Users\aluno\Documents\lp-python\campeonato.py", line 4
    print("Equipas de dois jogadores."
         ^
SyntaxError: '(' was never closed
```

Versão B:

```python
# campeonato.py: o anúncio do campeonato de matraquilhos da escola.
print("CAMPEONATO DA ESCOLA")
print(Matraquilhos)
print("Equipas de dois jogadores.")
```

```text
CAMPEONATO DA ESCOLA
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\campeonato.py", line 3, in <module>
    print(Matraquilhos)
          ^^^^^^^^^^^^
NameError: name 'Matraquilhos' is not defined
```

Versão C:

```python
# campeonato.py: o anúncio do campeonato de matraquilhos da escola.
print("CAMPEONATO DA ESCOLA")
# print("Matraquilhos")
print("Equipas de dois jogadores.")
```

```text
CAMPEONATO DA ESCOLA
Equipas de dois jogadores.
```

## Exercício 4: Encontrar e corrigir o erro com método

Este programa devia mostrar o horário das finais de um torneio de jogos de computador. Cria o ficheiro `horario.py`, copia para ele este conteúdo, exatamente como está, e corre-o:

```python fragment erro de propósito: o exercício pede que o aluno o encontre
# horario.py: o horário das finais de um torneio de jogos de computador.
print("FINAIS DO TORNEIO")
print("Meias-finais às 14h00.")
 print("Final às 16h00.")
print("Entrega dos prémios às 17h00.")
```

O resultado esperado é este:

```text
FINAIS DO TORNEIO
Meias-finais às 14h00.
Final às 16h00.
Entrega dos prémios às 17h00.
```

Depura com método, como no guia 05 da algoritmia, e escreve no caderno os cinco passos:

1. Observar e reproduzir: o resultado esperado, o que apareceu e o tipo de erro.
2. Formular uma hipótese: uma frase com a causa possível.
3. Verificar a hipótese: o que leste na mensagem e no programa que a confirma.
4. Corrigir a causa: o que mudaste, e em que linha.
5. Voltar a testar tudo: o que apareceu depois da correção, comparado com o resultado esperado.

## Exercício 5: As fases do ciclo de vida

A Rita fez o ecrã de abertura de um jogo de memória, que um colega lhe pediu. Estas são as coisas que ela fez, fora de ordem:

- A. Correu o programa e comparou o que apareceu com o resultado esperado.
- B. Escreveu o algoritmo em pseudocódigo, com um `Escreve:` por linha.
- C. Leu o pedido do colega e escreveu o resultado esperado, linha a linha.
- D. Passou o algoritmo para Python, no ficheiro `memoria.py`.
- E. Um mês depois, acrescentou uma regra nova que o colega lhe pediu.
- F. Viu que faltava uma linha e acrescentou o `print` que faltava.

1. Escreve as letras pela ordem em que a Rita as fez.
2. Ao lado de cada letra, escreve a fase do ciclo de vida a que pertence: análise, desenho, implementação, testes ou manutenção.

## Apoio

- Exercício 1: relê, no guia, a regra dos comentários, e aplica-a a cada linha, uma de cada vez.
- Exercício 2: o programa tem tantos `print` quantas linhas o ecrã tem. Decide primeiro o resultado esperado, e só depois escreve o código.
- Exercício 3: para cada versão, olha primeiro para o que apareceu. Correu alguma linha? Há mensagem? Depois, lê a última linha da mensagem, se a houver.
- Exercício 4: traduz as palavras da última linha da mensagem: `unexpected` quer dizer inesperado, e `indent` quer dizer indentação. Depois relê as regras da sintaxe, no guia.
- Exercício 5: começa pela coisa que se faz antes de haver código. Depois procura a que se faz quando o programa já está em uso.

## Desafio opcional

Este programa tem dois erros, de tipos diferentes:

```python fragment erros de propósito: o desafio pede que o aluno os encontre
# loja.py: as boas-vindas da loja de um jogo de quintas.
print("LOJA DA QUINTA")
print("Sementes novas todas as semanas.")
print("Regador a partir de 100 moedas."))
print("Enxada a partir de 50 moedas.")
print("Sementes novas todas as semanas.")
```

O resultado esperado é este:

```text
LOJA DA QUINTA
Sementes novas todas as semanas.
Regador a partir de 100 moedas.
Enxada a partir de 50 moedas.
```

1. Sem correres, prevê o que aparece no ecrã com o programa assim, e explica porquê.
2. Corrige só o erro que faz o Python recusar o programa. Sem correres, prevê o que aparece agora.
3. Copia o programa original para um ficheiro `loja.py`, sem o escreveres à mão, porque o VS Code fecha sozinho as aspas e os parênteses. Confirma as duas previsões no computador. Depois corrige o segundo erro e testa tudo outra vez.
4. Explica, numa ou duas frases, porque é que o segundo erro só se vê depois de corrigires o primeiro.

## Para ires mais longe

Os textos deste tema estão todos entre aspas duplas. Na consola do Python, descobre:

1. se o Python aceita um texto entre aspas simples, como `print('Olá')`;
2. como se escreve um `print` que mostre esta frase, com as aspas incluídas: `O árbitro gritou "golo"`.

Escreve no caderno o que experimentaste e o que aconteceu em cada tentativa, também nas que deram erro.

## Critérios de conclusão

- O exercício 1 tem a previsão escrita antes de correres, e a comparação com o que apareceu.
- O `menu.py` do exercício 2 corre e dá o resultado esperado que escreveste antes de o correres.
- No exercício 3, cada versão tem o tipo de erro, a linha, a forma como o soubeste e a correção.
- O exercício 4 tem os cinco passos de depurar com método escritos, e o `horario.py` corrigido dá o resultado esperado.
- O exercício 5 tem as seis letras por ordem, cada uma com a sua fase.

## Autoavaliação

1. Que tipo de erro te custou mais a reconhecer, e porquê?
2. Em que exercício a tua previsão falhou? O que percebeste com isso?
3. Se tivesses de explicar a um colega a diferença entre o terminal e a consola do Python, o que lhe dirias?

![Rodapé](../imagens/rodape.png)
