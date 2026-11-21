![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Ciclo for e listas simples

Praticas as listas, o `for` pelo valor e pelo índice, o `append`, a pesquisa com `break`, as listas de listas, o `continue` e o `in`. Os exercícios 1 a 7 são obrigatórios. Guarda os ficheiros na tua pasta `lp-python`, e escreve as respostas por palavras em comentários, nos próprios ficheiros. Para rever: o [guia do tema](../05-ciclo-for-e-listas-simples.md) e o [laboratório](../laboratorios/05-ciclo-for-e-listas-simples-laboratorio.md).

## Exercício 1: A barra rápida

Na barra rápida do jogo, as nove casas guardam estes objetos, da casa 1 à casa 9:

```python
barra = ["espada", "picareta", "machado", "pá", "tocha", "pão", "maçã", "balde", "arco"]
```

Escreve o programa `barra.py`. Mostra quantos objetos tem a barra, o primeiro e o último. Depois, pergunta que casa queres usar e mostra o objeto que lá está. Uma casa que não existe dá `Essa casa não existe.`. Com a casa 5, o ecrã fica assim:

```text
Objetos na barra: 9
Primeiro: espada
Último: arco
Que casa queres usar? 5
Na casa 5 está: tocha
```

Experimenta-o também com as casas 1, 9, 0 e 10.

Rever: [O índice é a posição de cada elemento](../05-ciclo-for-e-listas-simples.md#o-índice-é-a-posição-de-cada-elemento) e [O `len` diz quantos elementos tem a lista](../05-ciclo-for-e-listas-simples.md#o-len-diz-quantos-elementos-tem-a-lista). Para a casa que não existe: [Validar um valor: dentro e fora de um intervalo](../03-selecao.md#validar-um-valor-dentro-e-fora-de-um-intervalo).

<details>
<summary>Pista</summary>

Que números de casa são válidos? Confirma a casa antes de a passares a índice.

</details>

## Exercício 2: O nível de experiência

Em cada missão do jogo, ganhas pontos de experiência, e cada 100 pontos dão um nível. Os pontos das missões que fizeste estão nesta lista:

```python
xp = [120, 0, 75, 200, 40]
```

Escreve o programa `nivel_experiencia.py`, que mostra o total de pontos e o nível a que chegaste. Faz a soma com um `for`, sem o `sum`. Com a lista acima, o ecrã fica assim:

```text
Pontos de experiência: 435
Nível: 4
```

Experimenta-o também com as listas `[]`, `[99]` e `[100]`.

Rever: [Percorrer a lista pelo valor, com `for`](../05-ciclo-for-e-listas-simples.md#percorrer-a-lista-pelo-valor-com-for) e [A divisão inteira e o resto](../02-dados-e-interacao.md#a-divisão-inteira-e-o-resto).

## Exercício 3: As rondas acima da média

Num jogo de ritmo, cada ronda dá de 0 a 100 pontos. Escreve o programa `rondas.py`, que pergunta os pontos de cada ronda até escreveres -1. No fim, mostra quantas rondas jogaste, a média dos pontos e quantas rondas ficaram acima da média:

```text
Pontos da ronda (-1 para acabar)? 40
Pontos da ronda (-1 para acabar)? 80
Pontos da ronda (-1 para acabar)? 60
Pontos da ronda (-1 para acabar)? 0
Pontos da ronda (-1 para acabar)? -1
Rondas jogadas: 4
Média: 45.0
Rondas acima da média: 2
```

Sem nenhuma ronda, a seguir a `Rondas jogadas: 0`, mostra `Não jogaste nenhuma ronda.`, em vez da média e da contagem. Experimenta-o também com estas entradas: só o `-1`; o `50` e o `-1`; o `10`, o `20`, o `30` e o `-1`.

Rever: [Juntar elementos com `append`](../05-ciclo-for-e-listas-simples.md#juntar-elementos-com-append) e [A média, só quando há valores](../04-ciclo-while.md#a-média-só-quando-há-valores).

<details>
<summary>Pista</summary>

Em que momento do programa já sabes a média? E, nesse momento, onde estão os pontos de cada ronda?

</details>

## Exercício 4: O desgaste das ferramentas

Cada ferramenta do inventário tem uma durabilidade, que diz quantos usos ainda aguenta:

```python
durabilidade = [40, 3, 25, 0, 12]
```

Num dia de trabalho, cada ferramenta perde 5 de durabilidade, mas nenhuma fica abaixo de 0. Escreve o programa `desgaste.py`, que muda os valores da própria lista e, no fim, a mostra numa linha como `Depois do dia: [...]`. Experimenta-o com a lista acima e com as listas `[]`, `[5]` e `[3]`.

Rever: [Mudar um elemento pelo índice](../05-ciclo-for-e-listas-simples.md#mudar-um-elemento-pelo-índice).

## Exercício 5: Os passos seguros

Um caminho do jogo é uma lista de blocos, do primeiro ao último:

```python
caminho = ["relva", "areia", "lava", "relva", "lava"]
```

O jogador anda bloco a bloco e para antes da primeira lava. Escreve o programa `caminho.py`, que diz quantos passos seguros o jogador pode dar, numa linha como `Passos seguros: 2`. São os blocos antes da primeira lava, ou todos, se o caminho não tiver lava. O programa deixa de procurar quando encontra a primeira lava.

Experimenta-o com estes caminhos:

- `["relva", "areia", "lava", "relva", "lava"]`
- `["lava"]`
- `["relva", "relva", "relva"]`
- `[]`

Rever: [Procurar um valor com uma bandeira](../05-ciclo-for-e-listas-simples.md#procurar-um-valor-com-uma-bandeira) e [Parar a pesquisa com `break`](../05-ciclo-for-e-listas-simples.md#parar-a-pesquisa-com-break).

<details>
<summary>Pista</summary>

Pensa primeiro no caminho sem lava: qual é a resposta, e de onde vem esse número?

</details>

## Exercício 6: O mapa das moedas

O mapa de um nível tem 3 linhas e 4 colunas, e cada casa guarda as moedas que lá estão:

```python
mapa = [
    [0, 2, 0, 1],
    [3, 0, 0, 0],
    [1, 1, 5, 0],
]
```

Escreve o programa `mapa.py`, que mostra as moedas de cada linha e, no fim, quantas casas do mapa estão vazias, sem moedas. Com o mapa acima, o ecrã fica assim:

```text
Linha 1 tem 3 moedas
Linha 2 tem 3 moedas
Linha 3 tem 7 moedas
Casas vazias: 6
```

Experimenta-o também com os mapas `[[0]]`, `[[2, 3]]` e `[]`.

Rever: [Listas de listas: uma tabela numa só variável](../05-ciclo-for-e-listas-simples.md#listas-de-listas-uma-tabela-numa-só-variável) e [Percorrer uma lista de listas: um `for` dentro de outro](../05-ciclo-for-e-listas-simples.md#percorrer-uma-lista-de-listas-um-for-dentro-de-outro).

<details>
<summary>Pista</summary>

Faz primeiro só as moedas de cada linha, e confirma-as. Depois, para as casas vazias, pergunta-te se a contagem é de uma linha ou do mapa todo.

</details>

## Exercício 7: A temperatura mais alta

No bioma da neve, o jogo regista a temperatura de cada hora, e há sempre pelo menos um registo. O programa `temperatura.py` devia mostrar a temperatura mais alta, mas tem dois erros, de propósito.

```python
# temperatura.py: mostra a temperatura mais alta registada no bioma da neve.
# Este programa tem dois erros, de propósito.
temperaturas = [-5, -2, -8, -3]
maior = 0
for i in range(temperaturas):
    if temperaturas[i] > maior:
        maior = temperaturas[i]
print("Temperatura mais alta:", maior)
```

| Lista | Resultado esperado |
| --- | --- |
| `[-5, -2, -8, -3]` | `Temperatura mais alta: -2` |
| `[-7]` | `Temperatura mais alta: -7` |
| `[3, -1, 0]` | `Temperatura mais alta: 3` |

Copia o programa para o ficheiro `temperatura.py` e corrige-o, mudando o mínimo possível, até dar o esperado nas três listas. Para o erro de lógica, escreve a rotina da depuração num comentário no fim do programa. Diz o caso que falhou, o esperado, o obtido, a tua hipótese, como a confirmaste e a linha que mudaste.

Rever: [Os três tipos de erro](../01-do-algoritmo-ao-programa.md#os-três-tipos-de-erro) e [Depurar com método, agora no computador](../01-do-algoritmo-ao-programa.md#depurar-com-método-agora-no-computador).

<details>
<summary>Pista</summary>

O primeiro erro para o programa, e a mensagem diz em que linha. O segundo não dá mensagem: compara o obtido com o esperado em cada lista, e procura o que têm em comum as listas que falham.

</details>

## Desafios

### Desafio 1: As voltas da pesquisa

No `caminho.py` do exercício 5, acrescenta um contador provisório das voltas do ciclo. Corre-o com estes quatro caminhos, todos de 5 blocos:

- `["lava", "relva", "relva", "relva", "relva"]`
- `["relva", "areia", "lava", "relva", "lava"]`
- `["relva", "relva", "relva", "relva", "lava"]`
- `["relva", "relva", "areia", "relva", "relva"]`

Num comentário no fim do ficheiro, escreve as voltas que o ciclo deu em cada caminho e responde a três perguntas. Que caminho é o melhor caso, com menos voltas, e qual é o pior, com mais? Quantas voltas dava o ciclo num caminho de 100 blocos sem lava? E, sem o `break`, o programa dava a resposta certa?

Rever: [Contar as voltas: a pesquisa com e sem `break`](../05-ciclo-for-e-listas-simples.md#contar-as-voltas-a-pesquisa-com-e-sem-break).

### Desafio 2: Três em linha

No jogo do galo, o tabuleiro tem 3 linhas e 3 colunas, e cada casa tem `"X"`, `"O"` ou um espaço, `" "`, quando está vazia:

```python
tabuleiro = [
    ["X", "O", "X"],
    ["O", "O", "O"],
    ["X", " ", "X"],
]
```

Escreve o programa `galo.py`, que diz se algum jogador fez três em linha numa das linhas do tabuleiro, como `O fez três em linha na linha 2`. Se ninguém fez, mostra `Ninguém fez três em linha numa linha.`. Escolhe três tabuleiros de teste, um deles com uma linha toda vazia, e escreve-os num comentário no fim do ficheiro, com o resultado esperado. Se quiseres ir mais longe, procura também nas colunas.

Rever: [Listas de listas: uma tabela numa só variável](../05-ciclo-for-e-listas-simples.md#listas-de-listas-uma-tabela-numa-só-variável).

### Desafio 3: A mochila do explorador

Na mochila do explorador, os objetos que se partiram ficaram registados como `"partido"`:

```python
mochila = ["espada", "partido", "tocha", "pão", "partido"]
```

Escreve o programa `mochila_explorador.py`, que mostra, um por linha, os objetos que se podem usar, e diz quantos são. Salta os partidos com o `continue`. No fim, diz com o `in` se há uma tocha na mochila: `Tens uma tocha.` ou `Não tens nenhuma tocha.`. Com a mochila acima, o ecrã fica assim:

```text
espada
tocha
pão
Objetos que se podem usar: 3
Tens uma tocha.
```

Experimenta-o também com as mochilas `[]`, `["partido"]` e `["pão", "pão"]`.

Rever: [Saltar uma volta com `continue`](../05-ciclo-for-e-listas-simples.md#saltar-uma-volta-com-continue) e [As funções prontas: `sum`, `max`, `min` e `in`](../05-ciclo-for-e-listas-simples.md#as-funções-prontas-sum-max-min-e-in).

## Critérios de conclusão

- O `barra.py` mostra o objeto certo nas casas 1, 5 e 9, e a mensagem nas casas 0 e 10.
- O `nivel_experiencia.py` dá o total e o nível certos nas quatro listas, com a soma feita num `for`.
- O `rondas.py` dá o resultado certo nas quatro entradas, também sem nenhuma ronda.
- O `desgaste.py` muda a própria lista, e nenhuma durabilidade fica abaixo de 0.
- O `caminho.py` dá os passos certos nos quatro caminhos e para de procurar na primeira lava.
- O `mapa.py` dá as moedas de cada linha e as casas vazias nos quatro mapas.
- O `temperatura.py` dá o esperado nas três listas, e o comentário do fim tem a rotina do erro de lógica.

![Rodapé](../../imagens/rodape.png)
