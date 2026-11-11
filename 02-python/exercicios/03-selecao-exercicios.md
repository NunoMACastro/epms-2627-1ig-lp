![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Seleção

Praticas as comparações, o `if`, o `elif` e o `else`, os operadores `and`, `or` e `not`, e a validação. Os exercícios 1 a 5 são obrigatórios. Guarda os ficheiros na tua pasta `lp-python`. Antes de correres, calcula à mão o resultado de cada caso, a partir do enunciado. Para rever: o [guia do tema](../03-selecao.md) e o [laboratório](../laboratorios/03-selecao-laboratorio.md).

## Exercício 1: Prever comparações

Prevê o resultado de cada linha, como a consola do Python o mostraria, e confirma-o na consola. Nas linhas em que falhaste, escreve uma frase com o que o Python fez, num ficheiro `prever_comparacoes.py`, só com comentários. Se acertaste em todas, diz isso num comentário.

```text
>>> 12 >= 12
>>> 12 > 12
>>> "Ouro" == "ouro"
>>> 5 == 5.0
>>> 7 > 3 and 2 > 5
>>> 7 > 3 or 2 > 5
>>> not 7 > 3
>>> type(7 > 3)
```

Rever: [As comparações dão `True` ou `False`](../03-selecao.md#as-comparações-dão-true-ou-false) e [Juntar condições com `and`, `or` e `not`](../03-selecao.md#juntar-condições-com-and-or-e-not).

<details>
<summary>Pista</summary>

Em cada linha, pergunta-te primeiro que valores se comparam, e de que tipo são. Nas linhas com `and`, `or` ou `not`, faz primeiro as comparações.

</details>

## Exercício 2: Uma vida ou várias

O jogo mostra quantas vidas tens, e a frase tem de estar certa em português. Escreve o programa `vidas.py`, que pergunta quantas vidas tens e escreve a frase. A resposta é um inteiro igual ou maior do que zero. Com 1 e com 3, escreve:

```text
Quantas vidas tens? 1
Tens 1 vida.
```

```text
Quantas vidas tens? 3
Tens 3 vidas.
```

Experimenta-o também com 0 e com 2.

Rever: [Dois caminhos: `if` e `else`](../03-selecao.md#dois-caminhos-if-e-else).

<details>
<summary>Pista</summary>

Escreve a frase certa para cada um dos quatro casos antes de escreveres a condição. Em que casos a palavra fica no singular?

</details>

## Exercício 3: As estrelas do tempo

No fim de cada nível, o jogo dá estrelas pelo tempo que demoraste, em segundos inteiros. Até 30 segundos, inclusive, ganhas 3 estrelas. Mais de 30 e até 60, inclusive, ganhas 2. Mais de 60, ganhas 1.

Escreve o programa `estrelas_tempo.py`, que pergunta o tempo e escreve as estrelas. Com 25 segundos, escreve:

```text
Tempo do nível, em segundos? 25
Estrelas: 3
```

Um tempo negativo não existe, e o programa escreve `Tempo inválido.`. Experimenta-o com -1, 0, 30, 31, 60, 61 e 200 segundos. As regras fixas ficam em constantes.

Rever: [Mais de dois caminhos: a cadeia com `elif`](../03-selecao.md#mais-de-dois-caminhos-a-cadeia-com-elif).

<details>
<summary>Pista</summary>

Procura no enunciado as palavras "até" e "mais de". Que operador corresponde a cada uma? Depois pensa na ordem das perguntas da cadeia.

</details>

## Exercício 4: O erro de cada programa

Três colegas escreveram programas com decisões, e nenhum dá o resultado esperado. Para cada um, diz que tipo de erro é, de sintaxe, de execução ou de lógica, qual é a causa e como se corrige. Escreve as respostas num ficheiro `que_erro.py`, só com comentários, com uma parte para cada programa.

Programa A. Devia começar o jogo quando a pessoa escreve 1. A pessoa escreveu `1`.

```python
# menu.py: o menu inicial de um jogo.
opcao = input("1 Jogar, 2 Sair. Escolhe: ")
if opcao == 1:
    print("A começar o jogo.")
elif opcao == 2:
    print("Até à próxima.")
else:
    print("Opção inválida.")
```

```text
1 Jogar, 2 Sair. Escolhe: 1
Opção inválida.
```

Programa B. Devia aceitar as respostas `S` e `N` e recusar as outras. A pessoa escreveu `S`.

```python
# continuar.py: pergunta ao jogador se quer continuar e recusa outras respostas.
resposta = input("Queres continuar (S/N)? ")
if resposta != "S" or resposta != "N":
    print("Resposta inválida.")
elif resposta == "S":
    print("A continuar.")
else:
    print("Fim do jogo.")
```

```text
Queres continuar (S/N)? S
Resposta inválida.
```

Programa C. Devia dizer `Perdeste.` com a vida a 0, `Estás bem.` acima de 50 e `Cuidado.` nos outros casos. Não chegou a perguntar nada.

```python fragment programa C do exercício 4, para analisar
# vida.py: diz o estado da barra de vida do jogador, de 0 a 100.
vida = int(input("Vida (0 a 100)? "))
if vida > 50:
    print("Estás bem.")
else:
    print("Cuidado.")
elif vida == 0:
    print("Perdeste.")
```

```text
  File "C:\Users\aluno\Documents\lp-python\vida.py", line 7
    elif vida == 0:
    ^^^^
SyntaxError: 'elif' block follows an 'else' block
```

Rever: [O `int` esquecido](../03-selecao.md#o-int-esquecido), [Validar um valor: dentro e fora de um intervalo](../03-selecao.md#validar-um-valor-dentro-e-fora-de-um-intervalo) e [Mais de dois caminhos: a cadeia com `elif`](../03-selecao.md#mais-de-dois-caminhos-a-cadeia-com-elif).

<details>
<summary>Pista</summary>

Lê a última linha da mensagem e traduz as palavras. Nos programas que não têm mensagem, compara o resultado com o esperado e pergunta-te que valor tem a variável na linha da condição.

</details>

## Exercício 5: O nível seguinte

Para desbloquear o nível seguinte, precisas de pelo menos 3 estrelas e da chave do nível. Quando não o desbloqueias, o jogo diz o que te falta.

Escreve o programa `nivel.py`, que pergunta as estrelas, um inteiro de 0 a 5, e se tens a chave, com `S` ou `N`, em maiúscula. O programa escreve uma destas frases: `Nível desbloqueado.`, `Faltam estrelas.`, `Falta a chave.` ou `Faltam estrelas e a chave.`. Com 4 estrelas e a chave, escreve:

```text
Quantas estrelas tens? 4
Tens a chave (S/N)? S
Nível desbloqueado.
```

Experimenta-o também com 3 estrelas e `S`, com 2 estrelas e `S`, com 5 estrelas e `N`, e com 0 estrelas e `N`.

Rever: [Juntar condições com `and`, `or` e `not`](../03-selecao.md#juntar-condições-com-and-or-e-not).

<details>
<summary>Pista</summary>

Quantas respostas diferentes pode dar o programa? O que tem de ser verdade para cada uma aparecer?

</details>

## Desafios

### Desafio 1: Pedra, papel, tesoura

Cada jogador escreve a sua jogada: `pedra`, `papel` ou `tesoura`. A pedra parte a tesoura, a tesoura corta o papel e o papel embrulha a pedra. Se os dois escolherem o mesmo, é empate. Escreve o programa `pedra_papel_tesoura.py`, que pergunta a jogada de cada jogador e escreve `Empate.`, `Ganha o jogador 1.` ou `Ganha o jogador 2.`. Se alguma das jogadas não for uma das três palavras, escreve `Jogada inválida.` e não decide nada. Escolhe os casos de teste, com pelo menos um para cada resposta, e escreve-os num comentário no fim do ficheiro, com o resultado esperado.

Rever: [Juntar condições com `and`, `or` e `not`](../03-selecao.md#juntar-condições-com-and-or-e-not).

### Desafio 2: Comparar números com parte decimal

Na consola, prevê e confirma o que dá `0.1 + 0.2 == 0.3`. Explica o resultado num comentário, ligando-o aos `float` e ao dinheiro em cêntimos. Rever: [O dinheiro guarda-se em cêntimos](../02-dados-e-interacao.md#o-dinheiro-guarda-se-em-cêntimos) e [Funções predefinidas](../02-dados-e-interacao.md#funções-predefinidas).

Num jogo de exploração, o jogador anda duas etapas pelo mapa, em quilómetros, e o acampamento fica a 0.3 quilómetros. Escreve o programa `acampamento.py`, que pergunta as duas etapas, com `float`. O programa escreve `Chegaste ao acampamento.` quando a soma é 0.3 e `Ainda não chegaste.` nos outros casos. Experimenta-o com 0.1 e 0.2, com 0.15 e 0.15, e com 0.1 e 0.1.

Depois, muda a condição para aceitar uma soma que fique a menos de 0.000001 do acampamento, com o `abs`. Num comentário, responde: porque é que esta forma funciona, e a comparação com `==` não?

### Desafio 3: O código do objeto

No inventário, o código de cada objeto tem três letras do material, um hífen e o número, como `PED-015`. As letras são `MAD` para a madeira, `PED` para a pedra e `FER` para o ferro. Rever: [Partes de um texto: índices e cortes](../02-dados-e-interacao.md#partes-de-um-texto-índices-e-cortes).

Escreve o programa `codigo_objeto.py`, que pergunta o código e escreve o material por extenso, como `Material: pedra`. Se o quarto carácter não for um hífen, escreve `Código mal escrito.`. Se as três letras não forem de nenhum dos três materiais, escreve `Material desconhecido.`. O código tem sempre pelo menos quatro caracteres. Experimenta-o com `PED-015`, `MAD-002`, `FER-120`, `OUR-001` e `PED015`.

## Critérios de conclusão

- O `prever_comparacoes.py` tem uma frase para cada linha do exercício 1 em que falhaste, ou diz que acertaste em todas.
- O `vidas.py` escreve a frase certa nos quatro casos do enunciado.
- O `estrelas_tempo.py` dá o resultado certo nos sete casos do enunciado.
- O `que_erro.py` tem, para cada programa do exercício 4, o tipo de erro, a causa e a correção.
- O `nivel.py` dá a frase certa nos cinco casos do enunciado.

![Rodapé](../../imagens/rodape.png)
