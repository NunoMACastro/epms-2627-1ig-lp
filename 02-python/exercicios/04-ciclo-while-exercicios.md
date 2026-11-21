![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Ciclo while

Praticas o `while`: as voltas de um ciclo, a validação repetida, a sentinela, o contador e o acumulador. Os exercícios 1 a 5 são obrigatórios. Guarda os ficheiros na tua pasta `lp-python`, e escreve as respostas que se pedem em comentários, nos próprios ficheiros. Para rever: o [guia do tema](../04-ciclo-while.md) e o [laboratório](../laboratorios/04-ciclo-while-laboratorio.md).

## Exercício 1: A colónia de slimes

Num jogo, uma colónia de slimes duplica em cada ronda. Este programa conta as rondas até a colónia passar de 50 slimes:

```python
# slimes.py: conta as rondas até a colónia de slimes passar de 50.
LIMITE = 50

slimes = 3
rondas = 0
while slimes <= LIMITE:
    slimes = slimes * 2
    rondas += 1
print("Rondas:", rondas)
print("Slimes:", slimes)
```

O objetivo é a tabela de iterações deste ciclo, prevista por ti e confirmada pelo computador. Copia o programa para o ficheiro `slimes.py`. Completa a tabela num comentário no fim do ficheiro, até ao teste que dá `False`, e diz o que o programa escreve. Confirma-a com linhas de observação, e tira-as quando a tabela observada for igual à tua.

| Teste | `slimes` | `rondas` | Condição |
| --- | ---: | ---: | --- |
| 1.º | 3 | 0 | `3 <= 50` dá `True` |
| 2.º | 6 | 1 | |

Por fim, corre o programa com 60 slimes no início, e depois volta a pôr 3. Num segundo comentário, diz quantas voltas deu o ciclo com 60 e o que apareceu no ecrã.

Rever: [Repetir com `while`](../04-ciclo-while.md#repetir-com-while) e [Ver as voltas com linhas de observação](../04-ciclo-while.md#ver-as-voltas-com-linhas-de-observação).

<details>
<summary>Pista</summary>

Preenche primeiro a coluna `slimes`, a duplicar de linha para linha, e só depois a condição de cada linha. A tabela acaba na primeira condição que dá `False`.

</details>

## Exercício 2: A classe da personagem

Num jogo de aventura, a personagem pode ser guerreira, maga ou arqueira, e escolhe-se com uma letra maiúscula: `G`, `M` ou `A`. Escreve o programa `classe.py`, que pergunta a classe. Enquanto a resposta não for uma das três letras, escreve `Classe desconhecida. Escreve G, M ou A:` e pergunta outra vez. No fim, escreve a classe escolhida. Com `x` e depois `A`, o ecrã fica assim:

```text
Classe da personagem (G, M ou A)? x
Classe desconhecida. Escreve G, M ou A: A
Classe escolhida: A
```

Experimenta-o também com `M` à primeira, e com `Z`, `guerreiro`, `g` e `G`, por esta ordem.

Rever: [A validação repetida pede o valor outra vez](../04-ciclo-while.md#a-validação-repetida-pede-o-valor-outra-vez) e [Juntar condições com `and`, `or` e `not`](../03-selecao.md#juntar-condições-com-and-or-e-not).

<details>
<summary>Pista</summary>

Escreve primeiro a condição de uma resposta válida, como no `chave.py` do tema 03. A do `while` é a contrária.

</details>

## Exercício 3: A sala de espera

Num jogo online, os jogadores esperam numa sala, e uma partida só começa com pelo menos 4 jogadores. Escreve o programa `sala_de_espera.py`, que lê o nome de cada jogador que entra, até se escrever `fim`. No fim, escreve quantos jogadores entraram. Com pelo menos 4, escreve `A partida pode começar.`; com menos, escreve quantos faltam, como `Jogadores em falta: 3`. Com cinco jogadores, o ecrã fica assim:

```text
Nome do jogador (fim para terminar)? Ana
Nome do jogador (fim para terminar)? Rui
Nome do jogador (fim para terminar)? Eva
Nome do jogador (fim para terminar)? Tó
Nome do jogador (fim para terminar)? Zé
Nome do jogador (fim para terminar)? fim
Jogadores na sala: 5
A partida pode começar.
```

Experimenta-o também com Ana, Rui, Eva, Tó e `fim`; com Ana e `fim`; e com `fim` logo à primeira. O número mínimo de jogadores fica numa constante.

Rever: [Ler até à sentinela](../04-ciclo-while.md#ler-até-à-sentinela) e [O contador e o acumulador](../04-ciclo-while.md#o-contador-e-o-acumulador).

<details>
<summary>Pista</summary>

Se o programa parar com `ValueError`, lê na última linha o que o `int` recebeu.

</details>

## Exercício 4: Subir de nível

Para subir ao nível seguinte, uma personagem precisa de 100 pontos de experiência, que ganha em missões. Cada missão dá pelo menos 1 ponto. Escreve o programa `experiencia.py`, que pergunta os pontos de cada missão e os soma, até a soma chegar aos 100. No fim, escreve `Subiste de nível.`, quantas missões fizeste e com quantos pontos ficaste. Com 40, 35 e 30, o ecrã fica assim:

```text
Pontos desta missão? 40
Pontos desta missão? 35
Pontos desta missão? 30
Subiste de nível.
Missões feitas: 3
Experiência: 105
```

Experimenta-o também com 100 à primeira, com 60 e 40, e com 99 e 1.

Rever: [As três peças de um ciclo](../04-ciclo-while.md#as-três-peças-de-um-ciclo) e [O contador e o acumulador](../04-ciclo-while.md#o-contador-e-o-acumulador).

<details>
<summary>Pista</summary>

Aqui não há sentinela: ninguém escreve um valor para acabar. Pensa nas três peças. Que variável decide se há mais uma missão, com que valor começa e onde muda?

</details>

## Exercício 5: Os erros da pesca

No minijogo de pesca, o programa regista os peixes de cada lançamento da cana, até se escrever -1. No fim, mostra os lançamentos, os peixes apanhados, as pescas boas, que têm 3 peixes ou mais, e a média de peixes por lançamento. O programa tem três erros, de propósito.

```python
# pesca.py: o minijogo de pesca, com os peixes de cada lançamento lidos até ao -1.
# Este programa tem três erros, de propósito.
SENTINELA = -1
PESCA_BOA = 3

lancamentos = 0
peixes = 0
apanhados = int(input("Peixes deste lançamento (-1 para terminar)? "))
while apanhados != SENTINELA:
    lancamentos += 1
    peixes =+ apanhados
    if apanhados >= PESCA_BOA:
        pescas_boas += 1
    apanhados = int(input("Peixes deste lançamento (-1 para terminar)? "))
print("Lançamentos:", lancamentos)
print("Peixes apanhados:", peixes)
print("Pescas boas:", pescas_boas)
if lancamentos > 0:
    print("Peixes por lançamento, em média:", peixes // lancamentos)
else:
    print("Sem lançamentos, não há média.")
```

Com 5, 0, 4, 1 e -1, o ecrã devia ser este:

```text
Peixes deste lançamento (-1 para terminar)? 5
Peixes deste lançamento (-1 para terminar)? 0
Peixes deste lançamento (-1 para terminar)? 4
Peixes deste lançamento (-1 para terminar)? 1
Peixes deste lançamento (-1 para terminar)? -1
Lançamentos: 4
Peixes apanhados: 10
Pescas boas: 2
Peixes por lançamento, em média: 2.5
```

Com o -1 logo à primeira, devia escrever `Lançamentos: 0`, `Peixes apanhados: 0`, `Pescas boas: 0` e `Sem lançamentos, não há média.`.

Copia o programa para o ficheiro `pesca.py` e corrige-o, mudando o mínimo possível, até os dois casos darem o ecrã esperado. Para o erro que deixa errado o número de peixes apanhados, escreve a rotina da depuração num comentário no fim do ficheiro. Diz o caso, o esperado, o obtido e o tipo de erro, a tua hipótese, como a confirmaste e o que mudaste. Para os outros dois erros, basta o tipo de erro e o que mudaste.

Rever: [Os três tipos de erro](../01-do-algoritmo-ao-programa.md#os-três-tipos-de-erro), [Depurar com método, agora no computador](../01-do-algoritmo-ao-programa.md#depurar-com-método-agora-no-computador) e [Ver as voltas com linhas de observação](../04-ciclo-while.md#ver-as-voltas-com-linhas-de-observação).

<details>
<summary>Pista</summary>

Começa pelo erro que dá mensagem. Nos outros, compara o ecrã com o esperado, linha a linha: a primeira linha diferente diz-te que variável seguir com uma linha de observação.

</details>

## Desafios

### Desafio 1: O cofre do castelo

O cofre do castelo abre com o código 4729, e quem errar três vezes deixa-o bloqueado. Escreve o programa `cofre.py`, que pergunta o código até acertares ou até gastares as 3 tentativas. No fim, escreve `O cofre abriu à tentativa 2`, com o número da tentativa certa, ou `O cofre bloqueou`. Escolhe os casos de teste, com pelo menos um para cada maneira de o ciclo acabar. Escreve-os num comentário no fim do ficheiro, com o resultado esperado de cada um.

Rever: [Um ciclo com duas maneiras de acabar](../../01-algoritmos/04-repeticao-e-padroes.md#um-ciclo-com-duas-maneiras-de-acabar).

### Desafio 2: A escada de blocos

Escreve o programa `escada.py`, que pergunta quantos degraus tem a escada, de 1 a 10, e volta a perguntar enquanto o número não der. Depois, desenha a escada com `#`: um bloco no primeiro degrau, e mais um em cada degrau seguinte. Usa só o `while`, também para desenhar cada degrau. Com 4 degraus, o desenho é este:

```text
#
##
###
####
```

Experimenta-o também com 0, depois 11 e depois 1, e com 10.

Rever: [Um ciclo dentro de outro](../../01-algoritmos/04-repeticao-e-padroes.md#um-ciclo-dentro-de-outro) e [Juntar textos](../02-dados-e-interacao.md#juntar-textos).

## Critérios de conclusão

- O `slimes.py` tem a tabela prevista num comentário, igual à observada, e o segundo comentário diz o que acontece com 60 slimes.
- O `classe.py` aceita só `G`, `M` e `A`, e dá o ecrã certo nos três casos do enunciado.
- O `sala_de_espera.py` dá o resultado certo nos quatro casos, também com `fim` logo à primeira.
- O `experiencia.py` dá o resultado certo nos quatro casos, e para assim que a soma chega aos 100.
- O `pesca.py` dá o ecrã esperado nos dois casos. O comentário do fim tem a rotina completa do erro dos peixes apanhados, e o tipo e a correção dos outros dois.

![Rodapé](../../imagens/rodape.png)
