![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Dados e interação

Ficha do tema Dados e interação, do módulo Desenvolver programas em linguagem estruturada. Praticas as variáveis, as contas, a leitura do teclado com a conversão e o dinheiro em cêntimos. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](02-dados-e-interacao.md) e o [laboratório](02-dados-e-interacao-laboratorio.md).

## Como trabalhar

Faz os exercícios pela ordem. Os exercícios 1 a 5 são obrigatórios. O desafio opcional e o "Para ires mais longe" são para quem acabar.

Trabalha na tua pasta `lp-python`, no VS Code, com o teu comando. Escreve no caderno as previsões e as tabelas de entradas e saídas antes de correres, e não as mudes depois. Cada programa começa por um comentário que diz o que ele faz, e as regras fixas ficam em constantes, com o nome em maiúsculas.

## Exercício 1: Prever na consola

Sem usares o computador, escreve no caderno o resultado de cada linha, como a consola do Python o mostraria. Depois confirma na consola e, onde te enganaste, explica numa frase porquê.

```text
>>> 20 // 6
>>> 20 % 6
>>> 20 / 4
>>> 9 % 3
>>> 3 + 4 * 2
>>> abs(3 - 10)
>>> type(20 / 4)
```

## Exercício 2: O tempo de jogo

O jogo regista em minutos o tempo de cada sessão. O jogador quer saber quanto jogou em duas sessões seguidas, em horas e minutos. Escreve o programa `tempo.py`. O programa pergunta os minutos de cada sessão e escreve o tempo das duas juntas em horas e minutos. Com 70 e 65 minutos, por exemplo, escreve:

```text
Minutos da primeira sessão? 70
Minutos da segunda sessão? 65
Jogaste 2 horas e 15 minutos
```

Por agora, o programa escreve sempre "horas", mesmo quando é só uma, e `1 horas` aceita-se.

Antes de escreveres o código, faz no caderno a tabela de entradas e saídas. Escreve o resultado esperado para estes casos: 70 e 65; 30 e 29; 30 e 30; 0 e 0. Depois testa o programa com os quatro.

## Exercício 3: Que erro é este?

Três colegas escreveram programas que leem um valor do teclado. Nenhum dá o resultado esperado. Para cada um, tens o programa, o que a pessoa escreveu e o que apareceu. Responde no caderno:

- que tipo de erro é: de sintaxe, de execução ou de lógica;
- qual é a causa;
- como se corrige, no programa ou no que se escreve no teclado.

Programa A. Devia dizer a altura do salto do jogador em centímetros. A pessoa escreveu `2.5`.

```python
# salto.py: converte a altura de um salto de metros para centímetros.
CENTIMETROS_POR_METRO = 100
metros = int(input("Altura do salto, em metros? "))
print("Saltaste", metros * CENTIMETROS_POR_METRO, "centímetros")
```

```text
Altura do salto, em metros? 2.5
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\salto.py", line 3, in <module>
    metros = int(input("Altura do salto, em metros? "))
ValueError: invalid literal for int() with base 10: '2.5'
```

Programa B. Devia dizer o peso da mochila do jogador em gramas. A pessoa escreveu `2,5`.

```python
# mochila.py: converte o peso da mochila de quilos para gramas.
GRAMAS_POR_QUILO = 1000
quilos = float(input("Peso da mochila, em quilos? "))
print("A mochila pesa", quilos * GRAMAS_POR_QUILO, "gramas")
```

```text
Peso da mochila, em quilos? 2,5
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\mochila.py", line 3, in <module>
    quilos = float(input("Peso da mochila, em quilos? "))
ValueError: could not convert string to float: '2,5'
```

Programa C. Devia dizer quantas equipas de 4 jogadores se formam. A pessoa escreveu `18`, e o resultado esperado era 4 equipas.

```python
# equipas.py: forma equipas de 4 jogadores para um torneio.
JOGADORES_POR_EQUIPA = 4
jogadores = int(input("Quantos jogadores? "))
equipas = jogadores % JOGADORES_POR_EQUIPA
print("Equipas:", equipas)
```

```text
Quantos jogadores? 18
Equipas: 2
```

## Exercício 4: A conta do jogo

Alguns amigos querem comprar juntos um jogo que custa 20 € e dividir a conta em partes iguais. Escreve o programa `conta.py`. O programa pergunta quantos amigos pagam e escreve quanto paga cada um, em euros e cêntimos. Escreve também quantos cêntimos ficam por dividir. Com 3 amigos, por exemplo, escreve:

```text
Quantos amigos pagam? 3
Cada um paga 6 euros e 66 cêntimos
Ficam por dividir 2 cêntimos
```

O dinheiro guarda-se em cêntimos, num `int`. Antes de escreveres o código, faz a tabela de entradas e saídas, com o resultado esperado para 1, 3 e 4 amigos. Depois testa o programa com os três.

## Exercício 5: A média das estrelas

No fim de cada nível, o jogo dá de 1 a 5 estrelas. Mostra também a média de dois níveis, arredondada ao inteiro mais próximo como na escola, com as meias para cima.

1. Escreve o programa `estrelas.py`, que pergunta as estrelas dos dois níveis e escreve a média arredondada com `round`.
2. Antes de correres, calcula à mão a média arredondada destes casos: 4 e 5; 3 e 4; 3 e 5; 1 e 2. Depois testa-os, e escreve no caderno, para cada um, o que esperavas e o que apareceu.
3. Se algum caso falhou, explica porquê. Muda o programa para dar o resultado esperado nos quatro casos, e testa-os outra vez.

## Apoio

- Exercício 1: em cada linha, pergunta-te primeiro se a conta dá um `int` ou um `float`.
- Exercício 2: faz primeiro, à mão, as contas do caso de 70 e 65 minutos. Repara que contas fizeste, e por que ordem.
- Exercício 3: lê a última linha de cada mensagem e traduz as palavras. No programa C, que não tem mensagem, compara o resultado com o esperado e procura a conta que o produziu.
- Exercício 4: quantas divisões há neste problema, e por que ordem se fazem?
- Exercício 5: compara a média do caso que falhou com a dos casos que passaram. O que tem ela de diferente?

## Desafio opcional

Um jogo mostra quanto falta para o fim de um evento em horas, minutos e segundos, mas guarda esse tempo só em segundos. Escreve o programa `cronometro.py`, que pergunta o tempo em segundos e o escreve nas três unidades. Com 3725 segundos, escreve `1 horas, 2 minutos e 5 segundos`. Faz primeiro a tabela de entradas e saídas, com pelo menos quatro casos, e explica porque escolheste cada um.

## Para ires mais longe

O `round` aceita um segundo argumento, separado do primeiro por uma vírgula. Na consola, experimenta `round(3.14159, 2)`, `round(3.14159, 1)` e `round(2.71828, 3)`. Descobre o que faz o segundo argumento e escreve-o no caderno, por palavras tuas, com um exemplo.

Depois responde: o dinheiro guarda-se em cêntimos, num `int`. Porque é que não se usa o `round` com duas casas para as contas do dinheiro?

## Critérios de conclusão

- O exercício 1 tem as sete previsões escritas antes de usares a consola, e a explicação das que falharam.
- O `tempo.py` dá o resultado esperado da tua tabela nos quatro casos.
- No exercício 3, cada programa tem o tipo de erro, a causa e a correção.
- O `conta.py` usa só cêntimos nas contas e dá o resultado esperado nos três casos.
- O `estrelas.py` corrigido arredonda as meias para cima, e os quatro casos estão no caderno, com o esperado e o obtido.

## Autoavaliação

1. Em que exercício te esqueceste da conversão, ou estiveste perto de te esquecer?
2. Qual das três divisões, `/`, `//` ou `%`, te custa mais a escolher? Dá um exemplo de quando usarias cada uma.
3. Porque é que vale a pena ter, numa tabela de entradas e saídas, um caso de fronteira, como os 60 minutos do exercício 2?

![Rodapé](../imagens/rodape.png)
