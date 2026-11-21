![Cabeçalho](../imagens/cabecalho.png)

# Ciclo while

Neste guia, os teus programas passam a repetir instruções, e é o computador que dá as voltas do `Enquanto`. Vês o `while`, as três peças de um ciclo, a validação repetida, a sentinela, o contador e o acumulador. E confirmas as voltas no computador, com linhas de observação.

Usa os ciclos da algoritmia e os blocos do tema 03. Rever: [Enquanto](../01-algoritmos/04-repeticao-e-padroes.md#enquanto-repetir-enquanto-a-condição-for-verdadeira), [A tabela de iterações](../01-algoritmos/04-repeticao-e-padroes.md#a-tabela-de-iterações), [Padrão sentinela](../01-algoritmos/04-repeticao-e-padroes.md#padrão-sentinela) e [Os dois pontos e a indentação são obrigatórios](03-selecao.md#os-dois-pontos-e-a-indentação-são-obrigatórios). Para praticar: [laboratório](laboratorios/04-ciclo-while-laboratorio.md) e [ficha de exercícios](exercicios/04-ciclo-while-exercicios.md).

## Neste guia

1. [Repetir com `while`](#repetir-com-while)
2. [As três peças de um ciclo](#as-três-peças-de-um-ciclo)
3. [Ver as voltas com linhas de observação](#ver-as-voltas-com-linhas-de-observação)
4. [O ciclo que nunca acaba, e o Ctrl+C](#o-ciclo-que-nunca-acaba-e-o-ctrlc)
5. [A validação repetida pede o valor outra vez](#a-validação-repetida-pede-o-valor-outra-vez)
6. [Ler até à sentinela](#ler-até-à-sentinela)
7. [O contador e o acumulador](#o-contador-e-o-acumulador)
8. [Contar só algumas voltas](#contar-só-algumas-voltas)
9. [A média, só quando há valores](#a-média-só-quando-há-valores)
10. [Exemplo guiado: contar pedidos válidos e totalizar unidades](#exemplo-guiado-contar-pedidos-válidos-e-totalizar-unidades)

## Repetir com `while`

No jogo de construção, uma torre de 3 andares constrói-se um andar de cada vez. Com o que já sabes, o programa tinha três `print` quase iguais, e com 30 andares tinha trinta. Um ciclo repete as mesmas instruções, e o `while` é o `Enquanto` do pseudocódigo: repete o corpo enquanto a condição dá `True`. A linha do `while` acaba em dois pontos, como a do `if`, e o corpo fica quatro espaços para dentro.

```python
# torre.py: constrói uma torre de 3 andares, um andar de cada vez.
ANDARES = 3

andar = 1
while andar <= ANDARES:
    print("Andar", andar, "construído")
    andar = andar + 1
print("Torre pronta")
```

```text
Andar 1 construído
Andar 2 construído
Andar 3 construído
Torre pronta
```

A tabela de iterações mostra as voltas, com uma linha por cada teste da condição, como na algoritmia. Em Python, os resultados escrevem-se `True` e `False`, com maiúscula.

| Teste | `andar` | Condição | Durante a volta |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` dá `True` | escreve `Andar 1 construído` |
| 2.º | 2 | `2 <= 3` dá `True` | escreve `Andar 2 construído` |
| 3.º | 3 | `3 <= 3` dá `True` | escreve `Andar 3 construído` |
| 4.º | 4 | `4 <= 3` dá `False` | o ciclo termina |

Depois da última linha do corpo, o Python volta à linha do `while` e testa outra vez a condição.

## As três peças de um ciclo

Quando um ciclo falha, a causa está quase sempre numa das três peças da algoritmia. Na torre, são estas:

| Peça | O que faz | Na torre |
| --- | --- | --- |
| Inicialização | dá o valor de partida, antes do ciclo | `andar = 1` |
| Condição | diz em que situação se dá mais uma volta | `andar <= ANDARES` |
| Atualização | muda a variável da condição e aproxima o fim | `andar = andar + 1` |

Com `while andar > ANDARES:`, a condição trocada, o ciclo dá zero voltas e aparece só `Torre pronta`, porque `1 > 3` dá `False` logo no primeiro teste.

### A forma curta da atualização: `+=`

A atualização soma quase sempre um número à própria variável, e o Python tem uma forma curta para isso. `andar += 1` faz o mesmo que `andar = andar + 1`: soma 1 ao valor que `andar` já tinha. O número da direita pode ser outro, e `tabuas += 4` soma 4 às tábuas. Na torre, a última linha do corpo passa a `andar += 1`, e o ecrã não muda.

## Ver as voltas com linhas de observação

Na algoritmia, eras tu que davas as voltas, e a tabela mostrava o valor de cada variável. No computador, as variáveis ficam escondidas. Se o ciclo der uma volta a mais, como dás por isso?

Antes de correres, fazes de cabeça a tabela de iterações, a tabela prevista. Depois, pões o programa a mostrar as variáveis, com **linhas de observação**. Uma linha de observação é um `print` provisório, cujo texto começa por `(observação)`, e que tiras quando acabares de ver.

```python
# torre_observar.py: a torre de 3 andares, com linhas de observação.
ANDARES = 3

andar = 1
while andar <= ANDARES:
    # Linha de observação: o valor de andar no início de cada volta.
    print("(observação) andar =", andar)
    print("Andar", andar, "construído")
    andar += 1
# Linha de observação: o valor com que o ciclo terminou.
print("(observação) depois do ciclo, andar =", andar)
print("Torre pronta")
```

```text
(observação) andar = 1
Andar 1 construído
(observação) andar = 2
Andar 2 construído
(observação) andar = 3
Andar 3 construído
(observação) depois do ciclo, andar = 4
Torre pronta
```

As quatro linhas de observação são a **tabela observada**: a tabela de iterações, escrita pelo computador. Compara-a com a prevista, linha a linha. A primeira linha diferente diz-te em que volta o programa se afastou do que esperavas.

## O ciclo que nunca acaba, e o Ctrl+C

Sem a linha `andar += 1`, a variável fica sempre a 1, e a condição dá sempre `True`. É um ciclo infinito: o ecrã enche-se de `Andar 1 construído`, e `Torre pronta` nunca aparece.

Para parar o programa, clica dentro do terminal e carrega em Ctrl+C. No macOS também é Ctrl+C, com a tecla Control, e não com a Cmd. O fim do ecrã fica parecido com isto:

```text
Andar 1 construído
Andar 1 construído
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\torre.py", line 6, in <module>
    print("Andar", andar, "construído")
    ~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
KeyboardInterrupt
```

Em alguns terminais, aparece antes de `Traceback` um `^C`, que é o Ctrl+C que carregaste. Um **`KeyboardInterrupt`** é uma interrupção pelo teclado: foste tu que paraste o programa. A mensagem não aponta um erro, e só diz em que linha o programa ia. Depois, procura a peça que falha, com a pergunta da atualização: o que muda em cada volta, e essa mudança aproxima o fim?

## A validação repetida pede o valor outra vez

No guia 03, o `dificuldade.py` escrevia `Essa dificuldade não existe.` e acabava, e quem queria jogar tinha de o correr outra vez. Com um ciclo, o programa pede o valor outra vez, até ele ser válido. É o padrão validação repetida da algoritmia: a condição do `while` diz que o valor é inválido, e o corpo lê um valor novo.

```python
# escolher_dificuldade.py: pede o nível de dificuldade até ele ser de 1 a 3.
DIFICULDADE_MINIMA = 1
DIFICULDADE_MAXIMA = 3

dificuldade = int(input("Dificuldade (1 a 3)? "))
while dificuldade < DIFICULDADE_MINIMA or dificuldade > DIFICULDADE_MAXIMA:
    # Lê um valor novo, que o while volta a testar.
    dificuldade = int(input("Essa dificuldade não existe. Escolhe de 1 a 3: "))
print("Dificuldade escolhida:", dificuldade)
```

```text
Dificuldade (1 a 3)? 0
Essa dificuldade não existe. Escolhe de 1 a 3: 7
Essa dificuldade não existe. Escolhe de 1 a 3: 2
Dificuldade escolhida: 2
```

| Teste | `dificuldade` | Condição | Durante a volta |
| --- | ---: | --- | --- |
| 1.º | 0 | `0 < 1 or 0 > 3` dá `True` | pede outra vez e lê 7 |
| 2.º | 7 | `7 < 1 or 7 > 3` dá `True` | pede outra vez e lê 2 |
| 3.º | 2 | `2 < 1 or 2 > 3` dá `False` | o ciclo termina |

A pergunta repetida diz o que está mal, e por isso faz também de aviso. Quando o programa chega ao último `print`, a condição acabou de dar `False`, e a dificuldade está de certeza entre 1 e 3.

Testa também um valor válido à primeira: o ciclo dá zero voltas.

As duas leituras levam o `int`. Sem ele na leitura do corpo, o primeiro valor inválido faz o corpo guardar um texto, e o programa para no teste seguinte:

```text
Dificuldade (1 a 3)? 0
Essa dificuldade não existe. Escolhe de 1 a 3: 2
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\escolher_dificuldade.py", line 6, in <module>
    while dificuldade < DIFICULDADE_MINIMA or dificuldade > DIFICULDADE_MAXIMA:
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
TypeError: '<' not supported between instances of 'str' and 'int'
```

Quer dizer que o `<` não funciona entre um texto e um inteiro. A mensagem aponta a linha 6, a do `while`, mas a causa está na linha 8, a leitura do corpo.

<details>
<summary>Para ires mais longe: um ciclo dentro de outro</summary>

Uma validação repetida pode ficar dentro do corpo de outro ciclo. Aqui, cada um dos dois jogadores escolhe a sua dificuldade, e o `while` de dentro volta a pedi-la a quem se enganar. O corpo do ciclo de dentro fica com oito espaços.

```python
# dois_jogadores.py: pede a dificuldade de cada um dos dois jogadores, até ser de 1 a 3.
JOGADORES = 2
DIFICULDADE_MINIMA = 1
DIFICULDADE_MAXIMA = 3

jogador = 1
while jogador <= JOGADORES:
    dificuldade = int(input("Dificuldade do jogador " + str(jogador) + " (1 a 3)? "))
    # O ciclo de dentro dá todas as suas voltas antes de o de fora continuar.
    while dificuldade < DIFICULDADE_MINIMA or dificuldade > DIFICULDADE_MAXIMA:
        dificuldade = int(input("Essa dificuldade não existe. Escolhe de 1 a 3: "))
    print("O jogador", jogador, "joga na dificuldade", dificuldade)
    jogador += 1
```

```text
Dificuldade do jogador 1 (1 a 3)? 2
O jogador 1 joga na dificuldade 2
Dificuldade do jogador 2 (1 a 3)? 5
Essa dificuldade não existe. Escolhe de 1 a 3: 0
Essa dificuldade não existe. Escolhe de 1 a 3: 3
O jogador 2 joga na dificuldade 3
```

O ciclo de fora deu duas voltas. Na segunda, o de dentro deu duas, com o 5 e com o 0.

</details>

## Ler até à sentinela

Num jogo de arcada, o programa regista os pontos de cada partida, e ninguém sabe quantas partidas vão ser. Combina-se um valor que quer dizer "acabou", a sentinela, que nenhum dado verdadeiro pode ter. Uma partida pode acabar com 0 pontos, e por isso o 0 não serve: aqui, a sentinela é o -1.

Lê-se o primeiro valor antes do ciclo, na leitura antecipada. A condição é "o valor não é a sentinela", com `!=`. O corpo trata o valor e, na última linha, lê o seguinte.

```python
# partidas.py: conta as partidas de um jogo de arcada até aparecer a sentinela -1.
SENTINELA = -1

partidas = 0
pontos = int(input("Pontos da partida (-1 para terminar)? "))
while pontos != SENTINELA:
    partidas += 1
    # O valor seguinte lê-se no fim do corpo, para ir direto ao teste.
    pontos = int(input("Pontos da partida (-1 para terminar)? "))
print("Partidas:", partidas)
```

```text
Pontos da partida (-1 para terminar)? 120
Pontos da partida (-1 para terminar)? 0
Pontos da partida (-1 para terminar)? 85
Pontos da partida (-1 para terminar)? -1
Partidas: 3
```

O valor lido vai sempre direto ao teste do `while`. A partida de 0 pontos conta, e a sentinela faz a condição dar `False` sem ser contada. Com o -1 logo à primeira, o ciclo dá zero voltas e escreve `Partidas: 0`.

Num ciclo com sentinela, o erro típico é ler no princípio do corpo. Como a condição precisa de um valor, inventa-se um para entrar no ciclo:

```python fragment só o ciclo, com a leitura no princípio do corpo; o resto é o partidas.py
pontos = 0
while pontos != SENTINELA:
    pontos = int(input("Pontos da partida (-1 para terminar)? "))
    partidas += 1
```

Com os mesmos valores, este ciclo escreve `Partidas: 4`, porque conta o -1 antes de o testar. Um valor inventado, que não veio do teclado, é um sinal de alarme.

As três peças estão em todos os ciclos deste guia, mas em sítios diferentes:

| Peça | Torre | Validação | Sentinela |
| --- | --- | --- | --- |
| Inicialização | `andar = 1` | a primeira leitura, antes do ciclo | a leitura antecipada, antes do ciclo |
| Condição | `andar <= ANDARES` | o valor é inválido | o valor não é a sentinela |
| Atualização | `andar += 1` | a leitura do corpo | a leitura na última linha do corpo |

## O contador e o acumulador

A variável `partidas` é um contador: começa em 0, antes do ciclo, e aumenta 1 em cada volta. Falta saber quantos pontos se fizeram ao todo, e para isso é preciso um acumulador, que soma o valor de cada volta. Na algoritmia, chamava-se totalizador.

```python
# partidas_total.py: conta as partidas e soma os pontos, até aparecer a sentinela -1.
SENTINELA = -1

partidas = 0
total_pontos = 0
pontos = int(input("Pontos da partida (-1 para terminar)? "))
while pontos != SENTINELA:
    partidas += 1
    total_pontos += pontos
    pontos = int(input("Pontos da partida (-1 para terminar)? "))
print("Partidas:", partidas)
print("Pontos ao todo:", total_pontos)
```

Com 120, 0, 85 e o -1, o fim do ecrã é `Partidas: 3` e `Pontos ao todo: 205`. A última coluna da tabela não mostra as perguntas do `input`.

| Teste | `pontos` | `partidas` | `total_pontos` | Condição | Durante a volta |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 120 | 0 | 0 | `120 != -1` dá `True` | conta, soma 120 e lê 0 |
| 2.º | 0 | 1 | 120 | `0 != -1` dá `True` | conta, soma 0 e lê 85 |
| 3.º | 85 | 2 | 120 | `85 != -1` dá `True` | conta, soma 85 e lê -1 |
| 4.º | -1 | 3 | 205 | `-1 != -1` dá `False` | o ciclo termina |

O contador soma sempre 1, com `partidas += 1`, e o acumulador soma o próprio valor, com `total_pontos += pontos`. Os dois começam antes do ciclo. Se `total_pontos = 0` passar para dentro do corpo, o total recomeça em cada volta, e o programa escreve `Pontos ao todo: 85`, os pontos da última partida.

## Contar só algumas voltas

O jogo dá um prémio às partidas com 100 pontos ou mais, e quer saber quantas foram. A linha que aumenta este contador vai para dentro de um `if`, e só corre nas voltas em que a condição dá `True`.

```python
# partidas_premio.py: conta as partidas, as que dão prémio e os pontos, até à sentinela -1.
SENTINELA = -1
PONTOS_DO_PREMIO = 100

partidas = 0
partidas_com_premio = 0
total_pontos = 0
pontos = int(input("Pontos da partida (-1 para terminar)? "))
while pontos != SENTINELA:
    partidas += 1
    total_pontos += pontos
    # Uma partida dá prémio com PONTOS_DO_PREMIO pontos ou mais.
    if pontos >= PONTOS_DO_PREMIO:
        partidas_com_premio += 1
    pontos = int(input("Pontos da partida (-1 para terminar)? "))
print("Partidas:", partidas)
print("Partidas com prémio:", partidas_com_premio)
print("Pontos ao todo:", total_pontos)
```

Com 120, 0, 85, 100 e o -1, aparecem `Partidas: 4`, `Partidas com prémio: 2` e `Pontos ao todo: 305`. A partida de 100 conta, porque a condição usa `>=`.

É a margem de cada linha que decide quantas vezes ela corre:

| Margem | Linhas | Quantas vezes correm, com estes valores |
| --- | --- | --- |
| Nenhuma | as constantes, os três `= 0`, a primeira leitura e os três `print` | 1 vez |
| Quatro espaços | a contagem, a soma, o `if` e a leitura do valor seguinte | 4 vezes, uma por partida |
| Oito espaços | `partidas_com_premio += 1` | 2 vezes, só quando o `if` dá `True` |

A linha do `while` está na margem, mas é o teste, e corre 5 vezes. Testa antes de cada partida e, por fim, o -1.

A leitura do valor seguinte fica com quatro espaços, fora do `if`. Se ficasse dentro, numa partida sem prémio não se lia nenhum valor novo, e o ciclo nunca acabava.

## A média, só quando há valores

Com o contador e o acumulador, calcula-se a média de pontos por partida. A conta fica dentro de um `if`, depois do ciclo, e só se faz quando houve partidas.

```python
# partidas_media.py: conta as partidas e os pontos até à sentinela -1, e mostra a média.
SENTINELA = -1

partidas = 0
total_pontos = 0
pontos = int(input("Pontos da partida (-1 para terminar)? "))
while pontos != SENTINELA:
    partidas += 1
    total_pontos += pontos
    pontos = int(input("Pontos da partida (-1 para terminar)? "))
print("Partidas:", partidas)
print("Pontos ao todo:", total_pontos)
# Sem este if, sem partidas, a conta seria 0 / 0, e o programa parava.
if partidas > 0:
    media = total_pontos / partidas
    print("Pontos por partida, em média:", media)
else:
    print("Sem partidas, não há média.")
```

Com 120, 0, 90 e o -1, a média é `70.0`, com o ponto zero, porque a divisão com `/` dá sempre um `float`. Com o -1 logo à primeira, aparece `Sem partidas, não há média.`, sem chegar à divisão. Sem o `if`, o programa escrevia as duas primeiras linhas e parava com `ZeroDivisionError: division by zero`, o erro de divisão por zero do tema 02.

## Exemplo guiado: contar pedidos válidos e totalizar unidades

Este problema está resolvido em pseudocódigo no [guia 04 da algoritmia](../01-algoritmos/04-repeticao-e-padroes.md#exemplo-guiado-contar-pedidos-válidos-e-totalizar-unidades). Aqui passa-se para Python, com os mesmos quatro casos.

### Passo 1: O enunciado

Ao longo do dia, uma papelaria recebe pedidos de material, e o funcionário escreve a quantidade de cada um. Escreve 0 quando já não há mais pedidos. Só se aceitam pedidos de 1 a 50 unidades, porque 50 é o máximo que a carrinha de entregas leva numa viagem. Uma quantidade negativa é um engano de escrita, e também se recusa.

Um pedido recusado é assinalado logo, no momento em que é escrito. No fim, o programa mostra quantos pedidos válidos houve, quantas unidades somam e quantos pedidos foram recusados.

### Passo 2: Os casos de teste, antes do programa

| Caso | Quantidades escritas | Válidos | Unidades | Recusados | Porque se escolheu |
| --- | --- | ---: | ---: | ---: | --- |
| A | 12, 60, 30, -4, 50, 0 | 3 | 92 | 2 | O caso normal, com recusados dos dois lados do intervalo |
| B | 0 | 0 | 0 | 0 | Zero voltas: nenhum pedido no dia |
| C | 1, 50, 51, 0 | 2 | 51 | 1 | As fronteiras: o 1 e o 50 são válidos, e o 51 não |
| D | 75, 0 | 0 | 0 | 1 | Só pedidos recusados |

### Passo 3: O pseudocódigo

```text
const SENTINELA = 0
const QUANTIDADE_MINIMA = 1
const QUANTIDADE_MAXIMA = 50
int pedidosValidos = 0
int pedidosRecusados = 0
int totalUnidades = 0
Escreve: "Quantidade do pedido (0 para terminar)?"
int quantidade = ler valor
Enquanto quantidade != SENTINELA
    Se quantidade >= QUANTIDADE_MINIMA e quantidade <= QUANTIDADE_MAXIMA
        pedidosValidos = pedidosValidos + 1
        totalUnidades = totalUnidades + quantidade
    Senão
        pedidosRecusados = pedidosRecusados + 1
        Escreve: "Pedido recusado: ", quantidade, " unidades"
    Escreve: "Quantidade do pedido (0 para terminar)?"
    quantidade = ler valor
Escreve: "Pedidos válidos: ", pedidosValidos
Escreve: "Total de unidades: ", totalUnidades
Escreve: "Pedidos recusados: ", pedidosRecusados
```

### Passo 4: Traduzir linha a linha

| Pseudocódigo | Python | O que mudou |
| --- | --- | --- |
| `const SENTINELA = 0` | `SENTINELA = 0` | Sem `const` |
| `int pedidosValidos = 0` | `pedidos_validos = 0` | Sem o tipo, e o nome com traço baixo |
| `Escreve: "..."` e `int quantidade = ler valor` | `quantidade = int(input("..."))` | As duas linhas juntam-se, antes do ciclo e no fim do corpo |
| `Enquanto condição` | `while condição:` | `while`, e os dois pontos no fim |
| `Se ... e ...` | `if ... and ...:` | `if` e `and`, com os dois pontos |
| `pedidosValidos = pedidosValidos + 1` | `pedidos_validos += 1` | A forma curta |
| `totalUnidades = totalUnidades + quantidade` | `total_unidades += quantidade` | A forma curta, que soma o valor |
| `Senão` | `else:` | Com os dois pontos |
| `Escreve: "Pedido recusado: ", quantidade, " unidades"` | `print("Pedido recusado:", quantidade, "unidades")` | Sem os espaços dentro das aspas, que o `print` já põe |

### Passo 5: O programa, parte a parte

Começa-se pelo ciclo, com a decisão e os dois contadores, para confirmar que cada pedido vai para o ramo certo:

```python
# pedidos.py: conta os pedidos válidos da papelaria e soma as unidades, até ao 0.
SENTINELA = 0
QUANTIDADE_MINIMA = 1
QUANTIDADE_MAXIMA = 50

pedidos_validos = 0
pedidos_recusados = 0
quantidade = int(input("Quantidade do pedido (0 para terminar)? "))
while quantidade != SENTINELA:
    # Cada pedido vai para um só ramo: ou é válido, ou é recusado.
    if quantidade >= QUANTIDADE_MINIMA and quantidade <= QUANTIDADE_MAXIMA:
        pedidos_validos += 1
    else:
        pedidos_recusados += 1
        print("Pedido recusado:", quantidade, "unidades")
    quantidade = int(input("Quantidade do pedido (0 para terminar)? "))
print("Pedidos válidos:", pedidos_validos)
print("Pedidos recusados:", pedidos_recusados)
```

Com o caso D, aparece `Pedido recusado: 75 unidades`, e no fim 0 válidos e 1 recusado. Com o caso A, 3 válidos e 2 recusados. Falta o acumulador das unidades, que nasce antes do ciclo e soma só os pedidos válidos. O programa completo fica assim:

```python
# pedidos.py: conta os pedidos válidos da papelaria e soma as unidades, até ao 0.
SENTINELA = 0
QUANTIDADE_MINIMA = 1
QUANTIDADE_MAXIMA = 50

pedidos_validos = 0
pedidos_recusados = 0
total_unidades = 0
quantidade = int(input("Quantidade do pedido (0 para terminar)? "))
while quantidade != SENTINELA:
    # Cada pedido vai para um só ramo: ou é válido, ou é recusado.
    if quantidade >= QUANTIDADE_MINIMA and quantidade <= QUANTIDADE_MAXIMA:
        pedidos_validos += 1
        total_unidades += quantidade
    else:
        pedidos_recusados += 1
        print("Pedido recusado:", quantidade, "unidades")
    quantidade = int(input("Quantidade do pedido (0 para terminar)? "))
print("Pedidos válidos:", pedidos_validos)
print("Total de unidades:", total_unidades)
print("Pedidos recusados:", pedidos_recusados)
```

Lê-se de cima para baixo como o pseudocódigo. As linhas dentro do `if` e do `else` têm oito espaços, porque o `if` está dentro do `while`. A leitura do fim do corpo volta aos quatro espaços, e por isso corre em todas as voltas.

### Passo 6: Correr os casos

O programa corre-se quatro vezes, uma por caso. Com o caso A:

```text
Quantidade do pedido (0 para terminar)? 12
Quantidade do pedido (0 para terminar)? 60
Pedido recusado: 60 unidades
Quantidade do pedido (0 para terminar)? 30
Quantidade do pedido (0 para terminar)? -4
Pedido recusado: -4 unidades
Quantidade do pedido (0 para terminar)? 50
Quantidade do pedido (0 para terminar)? 0
Pedidos válidos: 3
Total de unidades: 92
Pedidos recusados: 2
```

Os casos B, C e D dão também os números da tabela do passo 2. O caso B não mostra nenhuma mensagem de recusado e escreve três zeros.

### Passo 7: O caso que apanha o contador fora do `if`

Imagina que `pedidos_validos += 1` tinha ficado com quatro espaços, antes do `if`. O programa corria sem mensagem. Com o caso A, dava 5 válidos, e com o caso D, 1 válido e 1 recusado ao mesmo tempo. A hipótese é "o contador dos válidos conta todos os pedidos". Confirma-se com linhas de observação, que mostram os válidos a subir em todas as voltas. A mesma linha de observação entra duas vezes. Uma fica logo a seguir à linha do `while`, com quatro espaços, e a outra logo a seguir ao ciclo, encostada à margem. A correção é pôr o contador dentro do `if`, com oito espaços, tirar as linhas de observação e voltar a correr os quatro casos. O caso B, sem pedidos, dava zero válidos com as duas versões, e é por isso que a tabela tem o caso D.

## Erros frequentes

### O `++` do pseudocódigo

Numa linha como `andar++`, o Python recusa o programa, com o `^` a apontar para o fim da linha:

```text
  File "C:\Users\aluno\Documents\lp-python\torre.py", line 7
    andar++
           ^
SyntaxError: invalid syntax
```

Como é um erro de sintaxe, o programa não chega a começar. Corrige-se com `andar += 1`.

### Um `if` no lugar do `while`, na validação

Com um `if`, o programa pede o valor outra vez uma só vez, e aceita o segundo valor sem o testar:

```text
Dificuldade (1 a 3)? 0
Essa dificuldade não existe. Escolhe de 1 a 3: 7
Dificuldade escolhida: 7
```

O `if` decide uma vez, e não volta a perguntar. Corrige-se trocando o `if` por `while`, sem mudar a condição.

### O resultado escrito dentro do ciclo

Com o `print("Partidas:", partidas)` quatro espaços para dentro, o resultado aparece em todas as voltas:

```text
Pontos da partida (-1 para terminar)? 120
Pontos da partida (-1 para terminar)? 0
Partidas: 1
Pontos da partida (-1 para terminar)? 85
Partidas: 2
Pontos da partida (-1 para terminar)? -1
Partidas: 3
```

O `print` passou a fazer parte do corpo. Corrige-se encostando-o à margem, para correr uma vez, depois do ciclo, com a contagem completa.

## Palavras novas deste guia

- `+=`: a forma curta de somar um valor a uma variável; `andar += 1` faz o mesmo que `andar = andar + 1`.
- Linha de observação: um `print` provisório que mostra o valor das variáveis num sítio do programa.
- Tabela prevista: a tabela de iterações que fazes de cabeça, antes de correr.
- Tabela observada: a mesma tabela, escrita pelo computador, com as linhas de observação.
- `KeyboardInterrupt`: a última linha da mensagem de um programa parado com Ctrl+C.

## O que vem a seguir

No tema seguinte, Ciclo for e listas simples, guardas uma série de valores numa lista e percorre-la com o `for`.

## Para saber mais

- [Primeiros passos na programação](https://docs.python.org/3/tutorial/introduction.html#first-steps-towards-programming): a parte do tutorial oficial do Python, em inglês, com o primeiro ciclo `while`.
- [A instrução `while`](https://docs.python.org/3/reference/compound_stmts.html#the-while-statement): a descrição oficial do `while`, em inglês.

![Rodapé](../imagens/rodape.png)
