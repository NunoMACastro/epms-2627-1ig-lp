![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Seleção

Ficha do tema Seleção, do módulo Desenvolver programas em linguagem estruturada. Praticas as comparações, o `if`, o `elif` e o `else`, e os operadores `and`, `or` e `not`. Praticas também a validação e os casos de teste de cada ramo. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](../03-selecao.md) e o [laboratório](../laboratorios/03-selecao-laboratorio.md).

## Como trabalhar

Faz os exercícios pela ordem. Os exercícios 1 a 5 são obrigatórios. O desafio opcional e o "Para ires mais longe" são para quem acabar.

Trabalha na tua pasta `lp-python`, no VS Code, com o teu comando. Cada programa começa por um comentário que diz o que ele faz, e as regras fixas ficam em constantes, com o nome em maiúsculas. Uma resposta escrita fica num comentário, com `#`, como cada exercício indica. Antes de correres um programa, pensa no resultado que esperas em cada caso, tirado do enunciado, e não do que o programa mostra. Um programa com decisões corre-se uma vez por caso de teste: a seta para cima, no terminal, volta a escrever o último comando.

## Exercício 1: Prever comparações

Prevê o resultado de cada linha, como a consola do Python o mostraria, e só depois confirma-o na consola. Para cada linha em que te enganaste, explica numa frase o que o Python fez. Escreve as frases num ficheiro `prever_comparacoes.py`, só com comentários, um por linha.

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

## Exercício 2: Uma vida ou várias

O jogo mostra quantas vidas tens, e a frase tem de estar certa em português. Escreve o programa `vidas.py`, que pergunta quantas vidas tens e escreve a frase. Podes partir do princípio de que a resposta é um inteiro igual ou maior do que zero. Com 1, escreve:

```text
Quantas vidas tens? 1
Tens 1 vida.
```

E com 3:

```text
Quantas vidas tens? 3
Tens 3 vidas.
```

Experimenta-o também com 0 e com 2.

## Exercício 3: As estrelas do tempo

No fim de cada nível, o jogo dá estrelas pelo tempo que demoraste, em segundos inteiros. Até 30 segundos, inclusive, ganhas 3 estrelas. Mais de 30 e até 60, inclusive, ganhas 2. Mais de 60, ganhas 1. Um tempo negativo não existe, e o jogo diz que é inválido.

Escreve o programa `estrelas_tempo.py`, que pergunta o tempo e escreve as estrelas. Com 25 segundos, escreve:

```text
Tempo do nível, em segundos? 25
Estrelas: 3
```

Com um tempo negativo, escreve `Tempo inválido.`. Experimenta-o com -1, 0, 30, 31, 60, 61 e 200 segundos.

## Exercício 4: O erro de cada programa

Três colegas escreveram programas com decisões. Nenhum dá o resultado esperado. Para cada um, tens o programa, o que a pessoa escreveu e o que apareceu. Responde a três perguntas sobre cada programa:

- que tipo de erro é: de sintaxe, de execução ou de lógica;
- qual é a causa;
- como se corrige.

Escreve as respostas num ficheiro `que_erro.py`, só com comentários, com uma parte para cada programa.

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

Programa C. Devia dizer "Perdeste." com a vida a 0, "Estás bem." acima de 50 e "Cuidado." nos outros casos. Não chegou a perguntar nada.

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

## Exercício 5: O nível seguinte

Para desbloquear o nível seguinte, precisas de pelo menos 3 estrelas e da chave do nível. Quando não o desbloqueias, o jogo diz o que te falta: as estrelas, a chave ou as duas.

Escreve o programa `nivel.py`, que pergunta as estrelas, um inteiro de 0 a 5, e se tens a chave, com `S` ou `N`. O programa escreve uma destas quatro frases: `Nível desbloqueado.`, `Faltam estrelas.`, `Falta a chave.` ou `Faltam estrelas e a chave.`. Podes partir do princípio de que as estrelas são um inteiro de 0 a 5. A resposta da chave é sempre `S` ou `N`, em maiúscula. Com 4 estrelas e a chave, escreve:

```text
Quantas estrelas tens? 4
Tens a chave (S/N)? S
Nível desbloqueado.
```

Experimenta-o também com 3 estrelas e `S`, com 2 estrelas e `S`, com 5 estrelas e `N`, e com 0 estrelas e `N`.

## Apoio

- Exercício 1: em cada linha, pergunta-te primeiro que valores se comparam, e de que tipo são. Nas linhas com `and`, `or` ou `not`, faz primeiro as comparações.
- Exercício 2: escreve a frase certa para cada um dos quatro casos antes de escreveres a condição. Em que casos a palavra fica no singular?
- Exercício 3: procura no enunciado as palavras "até" e "mais de". Que operador corresponde a cada uma? Depois pensa na ordem das perguntas da cadeia.
- Exercício 4: lê a última linha de cada mensagem e traduz as palavras. Nos programas que não têm mensagem, compara o resultado com o esperado e pergunta-te que valor tem a variável na linha da condição.
- Exercício 5: quantas respostas diferentes pode dar o programa? Para cada uma, escreve as duas condições que a fazem acontecer.

## Desafio opcional

Num jogo de pedra, papel, tesoura, cada jogador escreve a sua jogada: `pedra`, `papel` ou `tesoura`. A pedra parte a tesoura, a tesoura corta o papel e o papel embrulha a pedra. Se os dois escolherem o mesmo, é empate. Escreve o programa `pedra_papel_tesoura.py`, que pergunta a jogada de cada jogador e escreve `Empate.`, `Ganha o jogador 1.` ou `Ganha o jogador 2.`. Se alguma das jogadas não for uma das três palavras, escreve `Jogada inválida.` e não decide nada. Escolhe tu os casos de teste, com pelo menos um para cada resposta possível. Escreve-os num comentário no início do programa, com o resultado esperado de cada um.

## Para ires mais longe

### Mais longe 1: Comparar números com parte decimal

Na consola, prevê e depois confirma o que dá `0.1 + 0.2 == 0.3`. Explica o resultado num comentário, ligando-o ao que aprendeste no guia 02 sobre os `float` e o dinheiro em cêntimos.

Num jogo de exploração, o jogador anda duas etapas pelo mapa, em quilómetros, e o acampamento fica a 0.3 quilómetros. Escreve o programa `acampamento.py`, que pergunta as duas etapas, com `float`, e escreve `Chegaste ao acampamento.` quando a soma é 0.3 e `Ainda não chegaste.` nos outros casos. Experimenta-o com 0.1 e 0.2, com 0.15 e 0.15, e com 0.1 e 0.1.

Depois, muda a condição para aceitar uma soma que fique a menos de 0.000001 do acampamento, com o `abs`. Num comentário, responde: porque é que esta forma funciona, e a comparação com `==` não?

### Mais longe 2: O código do objeto

No inventário, o código de cada objeto tem três letras do material, um hífen e o número, como `PED-015`. As letras são `MAD` para a madeira, `PED` para a pedra e `FER` para o ferro. Para tirar uma parte de um texto, usa os índices e os cortes da secção "Partes de um texto: índices e cortes" do [guia 02](../02-dados-e-interacao.md).

Escreve o programa `codigo_objeto.py`, que pergunta o código de um objeto e escreve o material por extenso, como `Material: pedra`. Se o carácter do meio, o quarto, não for um hífen, escreve `Código mal escrito.` e não procura o material. Se as três letras não forem de nenhum dos três materiais, escreve `Material desconhecido.`. Podes partir do princípio de que o código tem pelo menos quatro caracteres. Experimenta-o com `PED-015`, `MAD-002`, `FER-120`, `OUR-001` e `PED015`.

## Critérios de conclusão

- O `prever_comparacoes.py` tem uma frase para cada linha do exercício 1 em que te enganaste.
- O `vidas.py` escreve a frase certa nos quatro casos do enunciado.
- O `estrelas_tempo.py` dá o resultado certo nos sete casos do enunciado.
- O `que_erro.py` tem, para cada programa do exercício 4, o tipo de erro, a causa e a correção.
- O `nivel.py` dá a frase certa nos cinco casos do enunciado.

## Autoavaliação

1. Em que exercício a ordem das perguntas da cadeia mudou o resultado, ou podia ter mudado?
2. Que caso de teste te apanhou um erro que os outros não apanhavam?
3. Qual destes te custa mais a escolher: o `and` ou o `or`, o `<` ou o `<=`? Dá um exemplo de uma vez em que te enganaste.

![Rodapé](../../imagens/rodape.png)
