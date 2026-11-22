![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Funções e procedimentos

Praticas as funções que devolvem um valor com `return`, os procedimentos, a docstring e as linhas de teste. Os exercícios 1 a 6 são obrigatórios. Os ficheiros ficam na tua pasta `lp-python`, e as respostas por palavras vão em comentários, nos próprios ficheiros. Cada função que escreveres leva a sua docstring. As que devolvem um valor levam também linhas de teste, que desligas com `#` quando batem certo. Para rever: o [guia do tema](../06-funcoes-e-procedimentos.md) e o [laboratório](../laboratorios/06-funcoes-e-procedimentos-laboratorio.md).

## Exercício 1: O combate

Num jogo de aventura, este programa calcula o dano dos ataques e a vida das personagens:

```python
# combate.py: as personagens de um jogo de aventura, num combate.
DANO_BASE = 10


def dano(nivel):
    """Devolve o dano de um ataque, que cresce com o nível de quem ataca.

    Recebe o nível, um inteiro igual ou maior do que zero. Devolve um
    inteiro: o dano base mais 5 por cada nível.
    """
    return DANO_BASE + 5 * nivel


def mostrar_vida(nome, vida):
    """Escreve a vida de uma personagem.

    Recebe o nome, um texto, e a vida, um inteiro. Não devolve nada:
    escreve uma linha.
    """
    print(nome, "tem", vida, "de vida")


def vida_depois(vida, ataque):
    """Devolve a vida de uma personagem depois de um ataque.

    Recebe a vida e o dano do ataque, dois inteiros. Devolve um inteiro:
    a vida que sobra, ou 0 se o ataque for igual ou maior do que a vida.
    """
    if ataque >= vida:
        return 0
    return vida - ataque


print(dano(1))
print(dano(0) + dano(2))
mostrar_vida("Dragão", 50)
print(vida_depois(50, dano(4)))
print(vida_depois(20, dano(3)))
resultado = mostrar_vida("Goblin", 8)
print(resultado)
```

Copia o programa para o ficheiro `combate.py`. Antes de o correres, escreve num comentário, no fim do ficheiro, as linhas que esperas ver no ecrã, pela ordem. Depois, corre-o e confere. Para cada linha em que te enganaste, explica no mesmo comentário o que aconteceu.

Rever: [O `return` devolve um valor a quem chamou](../06-funcoes-e-procedimentos.md#o-return-devolve-um-valor-a-quem-chamou) e [Os procedimentos devolvem `None`](../06-funcoes-e-procedimentos.md#os-procedimentos-devolvem-none).

<details>
<summary>Pista</summary>

Uma chamada que está dentro dos parênteses de outra calcula-se primeiro. Para cada linha do programa, pergunta-te se escreve alguma coisa no ecrã, e o quê.

</details>

## Exercício 2: A medalha do nível

Num jogo de puzzles, cada nível dá uma medalha pelos pontos:

| Pontos | Medalha |
| --- | --- |
| menos de 100 | sem medalha |
| 100 a 249 | bronze |
| 250 a 399 | prata |
| 400 ou mais | ouro |

Escreve o programa `medalha.py`, com uma função `medalha_do_nivel(pontos)` que devolve o texto da medalha: `"sem medalha"`, `"bronze"`, `"prata"` ou `"ouro"`. A parte principal pergunta os pontos e escreve a medalha:

```text
Pontos do nível? 250
Medalha: prata
```

As linhas de teste da função experimentam os dois lados de cada limite e também o 0.

Rever: [O `return` devolve um valor a quem chamou](../06-funcoes-e-procedimentos.md#o-return-devolve-um-valor-a-quem-chamou) e [Testar cada função sozinha](../06-funcoes-e-procedimentos.md#testar-cada-função-sozinha).

## Exercício 3: A loja de poções

Na loja do jogo, cada poção custa 15 moedas. Este programa mostra o custo de uma compra:

```python
# pocoes.py: uma compra de poções na loja do jogo.
PRECO_POCAO = 15


def mostrar_custo(pocoes):
    """Escreve o custo de uma compra de poções, em moedas.

    Recebe o número de poções, um inteiro igual ou maior do que zero.
    Não devolve nada: escreve uma linha com o custo.
    """
    print("Custo:", pocoes * PRECO_POCAO, "moedas")


mostrar_custo(3)
```

Copia-o para o ficheiro `pocoes.py` e muda-o. O programa passa a perguntar quantas poções queres e quantas moedas tens. Mostra o custo e diz se a compra se faz, com as moedas que sobram, ou quantas moedas faltam. A conta do custo continua a fazer-se só na função. Com 3 poções e 50 moedas, o ecrã fica assim:

```text
Quantas poções? 3
Quantas moedas tens? 50
Custo: 45 moedas
Compra feita. Ficas com 5 moedas.
```

Experimenta-o também com 4 poções e 50 moedas, que dá `Faltam 10 moedas.`, e com 10 poções e 150 moedas. Com 0 poções e 20 moedas, dá `Compra feita. Ficas com 20 moedas.`.

Rever: [As funções calculam, e a parte principal escreve](../06-funcoes-e-procedimentos.md#as-funções-calculam-e-a-parte-principal-escreve).

<details>
<summary>Pista</summary>

Na parte principal, experimenta `print(mostrar_custo(3))`. O que aparece por baixo do custo, e serve para fazer contas?

</details>

## Exercício 4: A primeira onda difícil

Num jogo de defesa da torre, os inimigos chegam em ondas. Esta lista tem os inimigos de cada onda, pela ordem em que chegam:

```python
ondas = [8, 12, 25, 30, 18]
```

No modo normal, uma onda é difícil com mais de 20 inimigos, e no modo fácil, com mais de 28. Escreve o programa `ondas.py`, com uma função `primeira_onda_dificil(inimigos, limite)`. A função devolve o índice da primeira onda com mais inimigos do que o limite, ou -1 se nenhuma tiver. Com a lista acima, o programa escreve:

```text
Modo normal: a primeira onda difícil é a onda 3
Modo fácil: a primeira onda difícil é a onda 4
```

Com a lista `[8, 12, 25]`, a segunda linha passa a ser `Modo fácil: nenhuma onda difícil`. As linhas de teste da função incluem a lista vazia, uma onda com exatamente o limite e a mesma lista com dois limites diferentes.

Rever: [O `return` termina a função](../06-funcoes-e-procedimentos.md#o-return-termina-a-função).

## Exercício 5: As manobras de skate

Num jogo de skate, cada manobra de uma volta dá pontos. O programa `skate.py` devia mostrar o total da volta e o número da melhor manobra, a contar do 1, mas tem três erros, de propósito.

```python fragment erros de propósito: o exercício pede que o aluno os encontre
# skate.py: os pontos das manobras de uma volta num jogo de skate.
# Este programa tem três erros, de propósito.


def total_de_pontos(manobras)
    """Devolve o total de pontos de uma volta.

    Recebe a lista dos pontos de cada manobra, inteiros.
    Devolve um inteiro: a soma, ou 0 se a lista estiver vazia.
    """
    total = 0
    for pontos in manobras:
        total += pontos
    return total


def melhor_manobra(manobras):
    """Devolve o número da manobra com mais pontos, a contar do 1.

    Recebe a lista dos pontos de cada manobra, inteiros, com pelo menos uma.
    Devolve um inteiro e, num empate, o número da primeira.
    """
    i_melhor = 0
    for i in range(0, len(manobras)):
        if manobras[i] > manobras[i_melhor]:
            i_melhor = i
    return i_melhor


manobras = [300, 750, 120, 750]
print("Total da volta:", total_de_pontos(manobras))
print("Melhor manobra:", melhor_manobra)
```

| Lista | Resultado esperado |
| --- | --- |
| `[300, 750, 120, 750]` | `Total da volta: 1920` e `Melhor manobra: 2` |
| `[500]` | `Total da volta: 500` e `Melhor manobra: 1` |
| `[100, 200]` | `Total da volta: 300` e `Melhor manobra: 2` |

Copia o programa para o ficheiro `skate.py` e corrige-o, mudando o mínimo possível, até dar o esperado nas três listas. Num comentário no fim do programa, diz que tipo de erro é cada um. Para o erro do número da melhor manobra, escreve também a rotina da depuração. Diz o caso que falhou, o esperado e o obtido, a tua hipótese, como a confirmaste e a linha que mudaste.

Rever: [Os três tipos de erro](../01-do-algoritmo-ao-programa.md#os-três-tipos-de-erro) e [Depurar com método, agora no computador](../01-do-algoritmo-ao-programa.md#depurar-com-método-agora-no-computador).

<details>
<summary>Pista</summary>

O primeiro erro não deixa o programa começar. Depois de o corrigires, a última linha nem sequer é um número. Quando já mostrar um número, compara-o com o esperado nas três listas: falha sempre pela mesma diferença?

</details>

## Exercício 6: O torneio de dardos

Este programa mostra os pontos de três jogadores num torneio de dardos. Funciona, mas repete as mesmas contas para cada jogador:

```python
# dardos.py: os pontos dos jogadores de um torneio de dardos.
CENTRO = 50

falcao = [20, 50, 5, 50, 1]
raio = [50, 50, 50]
cometa = []

total = 0
no_centro = 0
for pontos in falcao:
    total += pontos
    if pontos == CENTRO:
        no_centro += 1
print("Falcão:", total, "pontos,", no_centro, "no centro")

total = 0
no_centro = 0
for pontos in raio:
    total += pontos
    if pontos == CENTRO:
        no_centro += 1
print("Raio:", total, "pontos,", no_centro, "no centro")

total = 0
no_centro = 0
for pontos in cometa:
    total += pontos
    if pontos == CENTRO:
        no_centro += 1
print("Cometa:", total, "pontos,", no_centro, "no centro")
```

O programa escreve:

```text
Falcão: 126 pontos, 2 no centro
Raio: 150 pontos, 3 no centro
Cometa: 0 pontos, 0 no centro
```

Copia-o para o ficheiro `dardos.py` e reescreve-o com funções, sem nenhum ciclo na parte principal. O ecrã tem de continuar igual, letra a letra. Depois, junta um quarto jogador, o Trovão, com os lançamentos `[5, 50, 20]`, que acrescenta a linha `Trovão: 75 pontos, 1 no centro`.

Rever: [As funções calculam, e a parte principal escreve](../06-funcoes-e-procedimentos.md#as-funções-calculam-e-a-parte-principal-escreve) e [A ordem no ficheiro: constantes, funções e parte principal](../06-funcoes-e-procedimentos.md#a-ordem-no-ficheiro-constantes-funções-e-parte-principal).

<details>
<summary>Pista</summary>

Começa por um só jogador: o que precisa o bloco dele de saber para escrever a linha?

</details>

## Desafios

### Desafio 1: A tabela do torneio

Os pontos de um torneio de dardos estão numa tabela, com uma linha por jogador e uma coluna por ronda:

```python
torneio = [
    [20, 50, 5],
    [50, 50, 50],
    [1, 20, 30],
]
```

Escreve o programa `torneio_dardos.py`, com uma função `total_do_jogador(tabela, jogador)` e outra `total_da_ronda(tabela, ronda)`. Recebem o índice de uma linha ou de uma coluna e devolvem a soma dela. A parte principal mostra o total de cada jogador e de cada ronda, como `Jogador 1 fez 75 pontos` e `Ronda 1 teve 71 pontos`.

Rever: [Listas de listas: uma tabela numa só variável](../05-ciclo-for-e-listas-simples.md#listas-de-listas-uma-tabela-numa-só-variável).

### Desafio 2: As cartas repetidas

Num jogo de cartas, a mão é uma lista com os números das cartas. Escreve o programa `repetidos.py`, com uma função `tem_repetidos(cartas)`, que devolve `True` se algum número aparecer mais do que uma vez, e `False` se não aparecer. A função deixa de procurar assim que encontra a primeira repetida. Testa-a com `[]`, `[5]`, `[1, 2, 3]`, `[3, 7, 3]`, `[4, 9, 2, 9]` e `[8, 8]`.

Rever: [O `return` termina a função](../06-funcoes-e-procedimentos.md#o-return-termina-a-função).

## Critérios de conclusão

- O `combate.py` tem, no comentário do fim, as linhas previstas e a explicação das que falharam.
- O `medalha.py` dá a medalha certa nos dois lados de cada limite, e as linhas de teste mostram-no.
- O `pocoes.py` diz se a compra se faz nos quatro casos, com o custo devolvido por uma função.
- O `ondas.py` dá as duas linhas certas com as duas listas, e a função devolve -1 quando não há onda difícil.
- O `skate.py` dá o esperado nas três listas. O comentário do fim diz o tipo de cada erro e tem a rotina do erro da melhor manobra.
- O `dardos.py` escreve o mesmo ecrã com funções, sem ciclos na parte principal, e mostra também o Trovão.
- Cada função que escreveste tem a sua docstring, e as que devolvem um valor têm linhas de teste, desligadas com `#`.

![Rodapé](../../imagens/rodape.png)
