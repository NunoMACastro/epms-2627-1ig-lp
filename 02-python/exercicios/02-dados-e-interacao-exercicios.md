![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Dados e interação

Ficha do tema Dados e interação, do módulo Desenvolver programas em linguagem estruturada. Praticas as variáveis, as contas, a leitura do teclado com a conversão e o dinheiro em cêntimos. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](../02-dados-e-interacao.md) e o [laboratório](../laboratorios/02-dados-e-interacao-laboratorio.md).

## Como trabalhar

Faz os exercícios pela ordem. Os exercícios 1 a 5 são obrigatórios. O desafio opcional e o "Para ires mais longe" são para quem acabar.

Trabalha na tua pasta `lp-python`, no VS Code, com o teu comando. Cada programa começa por um comentário que diz o que ele faz, e as regras fixas ficam em constantes, com o nome em maiúsculas. Uma resposta escrita fica num comentário, com `#`, como cada exercício indica. Antes de correres um programa, pensa no resultado que esperas, tirado do enunciado, e não do que o programa mostra.

## Exercício 1: Prever na consola

Prevê o resultado de cada linha, como a consola do Python o mostraria, e só depois confirma-o na consola. Para cada linha em que te enganaste, explica numa frase o que o Python fez. Escreve as frases num ficheiro `prever_na_consola.py`, só com comentários, um por linha.

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

Experimenta-o também com 30 e 29, com 30 e 30, e com 0 e 0 minutos.

## Exercício 3: Que erro é este?

Três colegas escreveram programas que leem um valor do teclado. Nenhum dá o resultado esperado. Para cada um, tens o programa, o que a pessoa escreveu e o que apareceu. Responde a três perguntas sobre cada programa:

- que tipo de erro é: de sintaxe, de execução ou de lógica;
- qual é a causa;
- como se corrige, no programa ou no que se escreve no teclado.

Escreve as respostas num ficheiro `que_erro.py`, só com comentários, com uma parte para cada programa.

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

O dinheiro guarda-se em cêntimos, num `int`. Experimenta-o também com 1 e com 4 amigos.

## Exercício 5: A média das estrelas

No fim de cada nível, o jogo dá de 1 a 5 estrelas. Mostra também a média de dois níveis, arredondada ao inteiro mais próximo como na escola, com as meias para cima.

Escreve o programa `estrelas.py`, que pergunta as estrelas dos dois níveis e escreve a média arredondada com `round`. Experimenta-o com 4 e 5, com 3 e 4, com 3 e 5, e com 1 e 2.

Se algum caso não der o arredondamento da escola, explica porquê num comentário, junto da linha onde está a causa. Depois muda o programa para dar o resultado certo nos quatro casos.

## Apoio

- Exercício 1: em cada linha, pergunta-te primeiro se a conta dá um `int` ou um `float`.
- Exercício 2: começa pelas contas que farias à mão no caso de 70 e 65 minutos. Repara que contas fizeste, e por que ordem.
- Exercício 3: lê a última linha de cada mensagem e traduz as palavras. No programa C, que não tem mensagem, compara o resultado com o esperado e procura a conta que o produziu.
- Exercício 4: quantas divisões há neste problema, e por que ordem se fazem?
- Exercício 5: compara a média do caso que falhou com a dos casos que passaram. O que tem ela de diferente?

## Desafio opcional

Um jogo mostra quanto falta para o fim de um evento em horas, minutos e segundos, mas guarda esse tempo só em segundos. Escreve o programa `cronometro.py`, que pergunta o tempo em segundos e o escreve nas três unidades. Com 3725 segundos, escreve `1 horas, 2 minutos e 5 segundos`. Testa-o com pelo menos quatro casos escolhidos por ti. Num comentário no início do script, escreve a tabela de entradas e saídas desses casos, com a razão de cada um.

## Para ires mais longe

O `round` aceita um segundo argumento, separado do primeiro por uma vírgula. Na consola, experimenta `round(3.14159, 2)`, `round(3.14159, 1)` e `round(2.71828, 3)`. Descobre o que faz o segundo argumento e explica-o por palavras tuas, com um exemplo.

Depois responde: o dinheiro guarda-se em cêntimos, num `int`. Porque é que não se usa o `round` com duas casas para as contas do dinheiro?

Escreve as duas respostas num ficheiro `round_com_casas.py`, só com comentários.

## Critérios de conclusão

- O `prever_na_consola.py` tem uma frase para cada linha do exercício 1 em que te enganaste.
- O `tempo.py` dá o resultado certo nos quatro casos do enunciado.
- O `que_erro.py` tem, para cada programa do exercício 3, o tipo de erro, a causa e a correção.
- O `conta.py` usa só cêntimos nas contas e dá o resultado esperado nos três casos.
- O `estrelas.py` corrigido arredonda as meias para cima e dá o resultado certo nos quatro casos. Um comentário, junto da linha da causa, explica o caso que falhava.

## Autoavaliação

1. Em que exercício te esqueceste da conversão, ou estiveste perto de te esquecer?
2. Qual das três divisões, `/`, `//` ou `%`, te custa mais a escolher? Dá um exemplo de quando usarias cada uma.
3. Porque é que vale a pena ter, numa tabela de entradas e saídas, um caso de fronteira, como os 60 minutos do exercício 2?

![Rodapé](../../imagens/rodape.png)
