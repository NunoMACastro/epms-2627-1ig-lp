![Cabeçalho](../imagens/cabecalho.png)

# Dados e interação

Módulo UC00606, Desenvolver programas em linguagem estruturada. Neste guia, os teus programas passam a guardar valores, a fazer contas e a ler o que a pessoa escreve no teclado. Vais aprender a não confundir um texto com um número, que é o erro mais frequente de quem começa. Para praticar, há o [laboratório](02-dados-e-interacao-laboratorio.md) e a [ficha de exercícios](02-dados-e-interacao-exercicios.md) deste tema.

No tema anterior, os programas só escreviam texto fixo, sempre igual. A partir de agora, um programa guarda valores, calcula com eles e responde ao que a pessoa escreve. Ainda não decide nem repete: as decisões e as repetições são dos temas seguintes. Os exemplos deste guia vêm quase todos do inventário de um jogo de construção, onde o jogador junta troncos, pedra e ferro para construir objetos.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Guardar valores em variáveis
4. Os nomes das variáveis
5. Constantes
6. Os tipos dos valores
7. Escrever vários valores com `print`
8. As contas: os operadores
9. A ordem das contas
10. Funções predefinidas
11. Ler do teclado com `input`
12. Converter um texto num número
13. Juntar textos
14. O dinheiro guarda-se em cêntimos
15. Exemplo guiado: os bilhetes do torneio
16. Erros frequentes
17. Palavras novas deste guia
18. Verificar o que aprendeste
19. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- guardar valores em variáveis e constantes, com nomes que seguem a forma do Python;
- dizer de que tipo é um valor, `int`, `float`, `str` ou `bool`, e confirmá-lo no computador;
- escrever contas com os operadores do Python e prever o resultado, incluindo a divisão inteira e o resto;
- usar as funções predefinidas `abs`, `round` e `int`, e calcular uma raiz quadrada;
- ler um valor do teclado e convertê-lo no tipo certo antes de fazer contas com ele;
- guardar dinheiro em cêntimos e mostrá-lo em euros e cêntimos;
- testar um programa com uma tabela de entradas e saídas.

## O que já sabes e vais usar

- Escrever, guardar e correr um programa no terminal, com o teu comando, `python`, `py` ou `python3`: guia [01 Do algoritmo ao programa](01-do-algoritmo-ao-programa.md).
- O `print`, os comentários e o resultado esperado escrito antes de correr: guia [01 Do algoritmo ao programa](01-do-algoritmo-ao-programa.md).
- A consola do Python, com o `>>>`: guia [01 Do algoritmo ao programa](01-do-algoritmo-ao-programa.md).
- Os três tipos de erro, como se lê uma mensagem e depurar com método: guia [01 Do algoritmo ao programa](01-do-algoritmo-ao-programa.md).
- As variáveis, as constantes, os tipos e a atribuição com `=`, em pseudocódigo: guia [02 Pseudocódigo](../01-algoritmos/02-pseudocodigo.md).
- O `ler valor` e o `Escreve:` com vários valores separados por vírgulas, em pseudocódigo: guia [02 Pseudocódigo](../01-algoritmos/02-pseudocodigo.md).
- As somas dos contadores e dos totalizadores, como `total = total + valor`: guia [04 Repetição e padrões](../01-algoritmos/04-repeticao-e-padroes.md).

## Guardar valores em variáveis

Um jogo de construção tem de se lembrar de quantos troncos tens. Juntas mais três, gastas dois numa mesa, e o número tem de mudar. Na algoritmia, um valor que o algoritmo guarda e pode mudar ficava numa variável. Em Python, também.

Uma **variável** é um nome que guarda um valor, para o programa o usar mais tarde. Em pseudocódigo escrevias `int troncos = 7`, com o tipo à frente. Em Python, escreve-se só o nome, o `=` e o valor:

```python
troncos = 7
```

O `=` é a **atribuição**, como no pseudocódigo: guarda o valor da direita na variável da esquerda. Lê-se "troncos passa a valer 7". Não é uma pergunta, e não quer dizer "é igual a".

O Python não precisa do tipo à frente, porque o descobre pelo valor. O 7 é um número inteiro, por isso `troncos` guarda um inteiro. A variável nasce na primeira vez que recebe um valor.

Antes de veres o resultado, tenta prever o que este programa escreve:

```python
# troncos.py: o número de troncos muda à medida que o jogador joga.
troncos = 7
print("No início:", troncos)
troncos = troncos + 3
print("Depois de apanhar mais:", troncos)
troncos = troncos - 2
print("Depois de construir uma mesa:", troncos)
```

O resultado é este:

```text
No início: 7
Depois de apanhar mais: 10
Depois de construir uma mesa: 8
```

Leitura guiada: lê o programa de cima para baixo e segue o valor de `troncos`. Na linha 2, a variável nasce com o valor 7. Na linha 4, o lado direito calcula-se primeiro, com o valor que a variável tem nesse momento: 7 mais 3 dá 10. Só depois o 10 é guardado em `troncos`, e o 7 perde-se. Na linha 6 acontece o mesmo com a subtração. É a mesma forma dos totalizadores da algoritmia, como `total = total + valor`.

Na primeira vez que segues variáveis num programa, ajuda fazer a tabela de trace, como no pseudocódigo:

| Linha | Instrução | `troncos` depois | O que aparece no ecrã |
| --- | --- | ---: | --- |
| 2 | `troncos = 7` | 7 | nada |
| 3 | `print("No início:", troncos)` | 7 | `No início: 7` |
| 4 | `troncos = troncos + 3` | 10 | nada |
| 5 | `print(...)` | 10 | `Depois de apanhar mais: 10` |
| 6 | `troncos = troncos - 2` | 8 | nada |
| 7 | `print(...)` | 8 | `Depois de construir uma mesa: 8` |

Repara que, dentro do `print`, `troncos` está sem aspas. Sem aspas, o Python procura uma variável com esse nome e escreve o valor dela. Com aspas, `"troncos"` é só um texto, e aparece a palavra. É a mesma regra do `Escreve:` do pseudocódigo.

O erro típico é usar uma variável antes de ela ter valor. Se o `print(troncos)` vier antes da linha `troncos = 7`, o Python ainda não conhece esse nome quando chega ao `print`. O programa para com `NameError: name 'troncos' is not defined`, isto é, "o nome 'troncos' não está definido". É um erro de execução, e as linhas de antes do `print` já correram. Numa sequência, a ordem importa, como no pseudocódigo.

## Os nomes das variáveis

Um nome bom diz o que a variável guarda. `troncos` diz mais do que `t` ou `x`. Quem lê o programa uma semana depois, incluindo tu, percebe-o sem ter de adivinhar.

O Python tem regras para os nomes, e não aceita outros:

- um nome tem letras, algarismos e o traço baixo, `_`;
- não começa por um algarismo;
- não tem espaços: `total tabuas = 3` dá um erro de sintaxe;
- as maiúsculas contam: `troncos` e `Troncos` são variáveis diferentes.

Além das regras, há uma forma de escrever que toda a gente segue em Python, e que vais seguir também. Os nomes escrevem-se em minúsculas, com um traço baixo entre as palavras: `total_tabuas`, `troncos_por_mesa`. No pseudocódigo das aulas escrevias `totalTabuas`, com uma maiúscula a separar as palavras. O Python aceitava esse nome, mas não é a forma da linguagem.

Escreve os nomes sem acentos nem cedilhas, como `numero` e `preco`. O Python aceita `número`, mas um nome sem acentos escreve-se igual em qualquer teclado e em qualquer computador. É a mesma regra que segues nos nomes dos ficheiros.

## Constantes

Num jogo, um tronco dá sempre 4 tábuas. Esse 4 é uma regra do jogo, que não muda enquanto o programa corre. Se aparecer espalhado pelo programa, quem lê não sabe o que quer dizer. E se a regra mudar, tens de o procurar e trocar em todo o lado.

Em pseudocódigo, um valor destes era uma constante, com `const`. Em Python não há `const`. Uma **constante** é uma variável com o nome todo em maiúsculas, que se combina não mudar:

```python
TABUAS_POR_TRONCO = 4
```

O nome em maiúsculas é um aviso para quem lê: este valor é uma regra, e o programa não o muda. O Python não impede a mudança. É uma convenção, isto é, uma forma combinada entre programadores, que se respeita. As constantes escrevem-se no início do programa, a seguir ao comentário, para se encontrarem depressa.

Com a constante, a conta diz o que faz: `tabuas = troncos * TABUAS_POR_TRONCO` lê-se sem precisar de explicação. Com o número, `tabuas = troncos * 4`, o leitor tem de adivinhar de onde vem o 4.

## Os tipos dos valores

Na algoritmia, cada variável tinha um tipo à frente: `int`, `float`, `string` ou `bool`. Em Python, o tipo não se escreve, mas continua a existir. Cada valor tem um tipo, e o tipo diz que contas se podem fazer com ele.

| Tipo | O que guarda | Exemplos | No pseudocódigo |
| --- | --- | --- | --- |
| `int` | números inteiros | `7`, `0`, `-3` | `int` |
| `float` | números com parte decimal | `2.5`, `7.0`, `-0.75` | `float` |
| `str` | textos, entre aspas | `"pedra"`, `"7"`, `""` | `string` |
| `bool` | verdadeiro ou falso | `True`, `False` | `bool`, com `true` e `false` |

Há três pormenores que mudam do pseudocódigo para o Python. O tipo dos textos chama-se `str`, uma abreviatura de string. Os valores de um `bool` escrevem-se com maiúscula, `True` e `False`. E a parte decimal de um `float` escreve-se com ponto, e não com vírgula: dois e meio é `2.5`.

Para saber de que tipo é um valor, usa-se `type`, na consola. Antes de veres as respostas, prevê o tipo de cada um:

```text
>>> type(7)
<class 'int'>
>>> type(2.5)
<class 'float'>
>>> type("7")
<class 'str'>
>>> type(True)
<class 'bool'>
```

O nome entre aspas simples, a seguir a `class`, é o tipo. Repara na terceira linha: `"7"`, entre aspas, é um texto, e não um número. O número 7 e o texto `"7"` parecem iguais no ecrã, mas são valores diferentes. Com o primeiro fazem-se contas; o segundo é um símbolo escrito, como uma letra. Esta diferença vai voltar várias vezes neste guia.

Um `bool` serve para guardar um sim ou um não, como se o jogador já tem uma picareta: `tem_picareta = True`. Neste tema, só vais guardar e escrever valores destes. Como se usam para decidir é o assunto do tema seguinte.

O erro típico é escrever `true` em minúsculas, como no pseudocódigo. O Python responde `NameError: name 'true' is not defined. Did you mean: 'True'?`. Procura uma variável chamada `true`, que não existe, e sugere a palavra certa.

## Escrever vários valores com `print`

Quase sempre, um programa escreve um texto e um valor na mesma linha, como "Troncos: 7". No pseudocódigo, separavas as partes com vírgulas, e os espaços tinham de ir dentro das aspas. Em Python, também se separam com vírgulas, mas há uma diferença.

Antes de veres o resultado, prevê o que escreve cada `print`, com atenção aos espaços:

```python
# espacos.py: o print com vírgulas, com e sem espaços dentro das aspas.
caixas = 2
print("Vão", caixas, "caixas")
print("Vão ", caixas, " caixas")
```

O resultado é este:

```text
Vão 2 caixas
Vão  2  caixas
```

Leitura guiada: cada `print` recebe três valores, separados por vírgulas: um texto, o valor de `caixas` e outro texto. O `print` escreve-os pela ordem, e põe sozinho um espaço entre cada dois. No primeiro, os textos não têm espaços, e o resultado fica certo. No segundo, os textos já trazem espaços, e o `print` junta os seus: ficam dois espaços seguidos.

É ao contrário do pseudocódigo das aulas. Lá, `Escreve: "Vão", caixas, "caixas"` dava `Vão2caixas`, e os espaços iam dentro das aspas. Em Python, com vírgulas, os espaços não vão nas aspas, porque o `print` já os põe.

Um `print` sem nada entre os parênteses, `print()`, escreve uma linha vazia. Serve para separar partes do que aparece no ecrã.

## As contas: os operadores

Um jogo faz contas a toda a hora: quantas tábuas dão 7 troncos, quantos baús se fazem com 30 tábuas, quantas tábuas sobram. Uma conta escrita num programa chama-se **expressão**. É formada por valores, variáveis e operadores. Um **operador** é o sinal que diz que conta se faz, como o `+`.

Os operadores das contas, em Python:

| Operador | O que faz | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `+` | soma | `7 + 2` | `9` |
| `-` | subtração | `7 - 2` | `5` |
| `*` | multiplicação | `7 * 2` | `14` |
| `/` | divisão, com parte decimal | `7 / 2` | `3.5` |
| `//` | divisão inteira: quantas vezes cabe | `7 // 2` | `3` |
| `%` | resto da divisão inteira | `7 % 2` | `1` |
| `**` | potência | `2 ** 3` | `8` |

A multiplicação escreve-se com asterisco, porque o "x" é uma letra e podia ser o nome de uma variável. A potência escreve-se com dois asteriscos: `2 ** 3` é 2 vezes 2 vezes 2.

A divisão com `/` dá sempre um `float`, mesmo quando é exata. Antes de leres, prevê quanto dá `6 / 2`. Dá `3.0`, e não `3`. O ponto zero diz que o resultado é um `float`: a conta podia ter dado parte decimal, e o Python trata o resultado como tal.

Os operadores `//` e `%` são as contas de dividir da escola primária, antes dos números decimais. Num baú cabem 8 tábuas, e tens 28. Quantos baús completos fazes, e quantas tábuas sobram? Pensa antes de leres.

Fazes 3 baús, que levam 24 tábuas, e sobram 4. Em Python, `28 // 8` dá `3`, os baús completos, e `28 % 8` dá `4`, o que sobra. No pseudocódigo das aulas, estas duas contas escrevem-se `div` e `resto`: `28 div 8` e `28 resto 8`.

Há uma forma de confirmar as duas contas ao mesmo tempo. O divisor vezes a divisão inteira, mais o resto, dá o número de partida: 8 vezes 3, mais 4, dá 28. E o resto é sempre mais pequeno do que o divisor. Se sobrassem 8 tábuas ou mais, cabia mais um baú.

Quando o número é mais pequeno do que o divisor, não cabe nenhuma vez, e sobra tudo. Antes de leres, prevê `5 // 8` e `5 % 8`. Dão `0` e `5`. Com 5 tábuas não se faz nenhum baú, e as 5 sobram todas.

A escolha entre `/` e `//` depende do que estás a contar. Usa `//` e `%` quando a parte decimal não faz sentido, como baús, pessoas ou bilhetes: 3,5 baús não existem. Usa `/` quando a parte decimal interessa, como numa média.

Nesta disciplina, `//` e `%` usam-se só com números inteiros. O da esquerda é igual ou maior do que zero, e o da direita é maior do que zero. Dividir por zero, com qualquer das três divisões, para o programa com `ZeroDivisionError`, um erro de execução.

## A ordem das contas

Antes de leres, calcula tu quanto dá `2 + 3 * 4`. Se fizeres da esquerda para a direita, dá 20. Mas o Python dá `14`.

O Python segue a ordem das operações da matemática:

1. primeiro, o que está entre parênteses;
2. depois, as potências, com `**`;
3. depois, as multiplicações e as divisões, incluindo `//` e `%`;
4. por fim, as somas e as subtrações;
5. entre operações do mesmo nível, da esquerda para a direita.

Em `2 + 3 * 4`, a multiplicação faz-se primeiro: 3 vezes 4 dá 12, mais 2 dá 14. Com parênteses, `(2 + 3) * 4` dá `20`, porque a soma passa à frente.

O erro mais frequente aparece nas médias. A média de duas pontuações, 14 e 17, é a soma a dividir por dois. Prevê quanto dá cada uma destas linhas:

```python
# medias.py: a média de duas pontuações, com e sem parênteses.
print((14 + 17) / 2)
print(14 + 17 / 2)
```

O resultado é este:

```text
15.5
22.5
```

Leitura guiada: na primeira linha, os parênteses fazem a soma primeiro, 31, e só depois a divisão. Na segunda, a divisão passa à frente da soma: divide só o 17, que dá 8.5, e soma-lhe 14. Uma média maior do que as duas pontuações é impossível, e é isso que denuncia o erro. Sempre que queres dividir uma soma, a soma vai entre parênteses. Na dúvida, põe parênteses: não custam nada e tiram a dúvida a quem lê.

## Funções predefinidas

Algumas contas aparecem em todo o lado, como tirar o sinal a um número ou arredondá-lo. O Python já as traz feitas. Uma **função predefinida** é um pedaço de programa que já vem com a linguagem, com um nome, pronto a usar. Dás-lhe um valor entre parênteses, e ela devolve um resultado. Ao valor que lhe dás chama-se **argumento**.

Pensa numa máquina de venda automática. Não sabes como funciona por dentro, e não precisas. Sabes o que lhe dás e o que ela te devolve, e isso chega para a usar. O `print` e o `type`, que já usaste, também são funções predefinidas. O `type` devolve um resultado, o tipo. O `print` não devolve nada que se use: escreve no ecrã. Nesta secção vais conhecer mais três, que fazem contas.

| Função | O que devolve | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `abs(x)` | o valor absoluto: o número sem sinal | `abs(-7)` | `7` |
| `round(x)` | o inteiro mais próximo; as meias vão para o número par | `round(2.6)` | `3` |
| `int(x)` | a parte inteira, cortando as casas decimais | `int(3.9)` | `3` |

### `abs`, o número sem sinal

`abs` devolve a distância de um número a zero. Serve quando interessa o tamanho de uma diferença, e não o sentido dela. Tens 30 pedras e o teu amigo tem 45: a diferença é `abs(30 - 45)`, que dá `15`. Se trocares a ordem, `abs(45 - 30)` também dá `15`. Sem o `abs`, a primeira conta dava `-15`, e uma diferença de menos 15 pedras não diz nada.

### `round`, o inteiro mais próximo

`round(2.4)` dá `2`, e `round(2.6)` dá `3`, porque são os inteiros mais próximos. O caso que engana é o das meias, que estão a meio caminho. Antes de leres, prevê `round(2.5)` e `round(3.5)`.

`round(2.5)` dá `2`, e `round(3.5)` dá `4`. O Python leva as meias para o número par mais próximo, e não sempre para cima. É uma regra que se usa em contas com muitos números, porque os arredondamentos para cima e para baixo se compensam.

Às vezes precisas de arredondar as meias sempre para cima, como na escola. Para números positivos, há uma forma com o que já sabes: soma-se 0.5 e corta-se a parte decimal com `int`. `int(2.5 + 0.5)` dá `3`, e `int(2.4 + 0.5)` dá `2`.

### `int`, a parte inteira

`int` corta as casas decimais e fica só com a parte inteira. `int(3.9)` dá `3`, mesmo estando 3,9 muito perto de 4. Não arredonda: corta. Com números negativos, aproxima-se de zero: `int(-3.7)` dá `-3`. Vais voltar a usar o `int` daqui a pouco, para outra coisa: converter um texto num número.

### A raiz quadrada, com `**`

A raiz quadrada não tem função própria neste tema. Faz-se com o operador da potência, o `**`, que está na tabela dos operadores. Elevar a `0.5` é o mesmo que tirar a raiz quadrada. `49 ** 0.5` dá `7.0`, porque 7 vezes 7 dá 49. Uma sala quadrada com 49 metros quadrados tem 7 metros de lado. O resultado é sempre um `float`, e só se usa com números iguais ou maiores do que zero.

O `**` faz-se antes das multiplicações, como viste na ordem das contas. Na dúvida, usa parênteses: `(9 + 16) ** 0.5` dá `5.0`, porque soma primeiro.

## Ler do teclado com `input`

Até agora, os valores estavam escritos no programa. Para saber quantos troncos tem cada jogador, o programa tem de perguntar. Em pseudocódigo era o `ler valor`. Em Python, é a função `input`.

O `input` faz três coisas. Escreve a pergunta que está entre parênteses e fica à espera que a pessoa escreva e carregue em Enter. Depois, devolve o que ela escreveu. Guarda-se numa variável, com a mesma forma do pseudocódigo:

```python
nome = input("Como se chama o teu mundo? ")
```

A pergunta acaba num espaço, dentro das aspas. Sem ele, o que a pessoa escreve fica colado ao ponto de interrogação.

Agora o ponto mais importante deste guia. O `input` devolve sempre um texto, um `str`, mesmo que a pessoa escreva um número. Se ela escrever 7, o `input` devolve o texto `"7"`, e não o número 7. Antes de leres, prevê o que o `type` mostra neste programa, quando a pessoa escreve 7:

```python
# tipo_lido.py: confirma de que tipo é o valor que o input devolve.
troncos = input("Quantos troncos tens? ")
print(type(troncos))
```

O resultado, depois de a pessoa escrever 7:

```text
Quantos troncos tens? 7
<class 'str'>
```

Leitura guiada: a primeira linha de código escreve a pergunta e espera. A pessoa escreve 7 e carrega em Enter, e o 7 aparece a seguir à pergunta. O `input` devolve o que foi escrito, e esse valor fica em `troncos`. A segunda linha mostra o tipo desse valor: `str`, um texto. Para o computador, a pessoa escreveu o símbolo 7, e não um número. O Enter só diz que a resposta acabou, e não fica no texto.

## Converter um texto num número

Um texto não serve para contas. Antes de leres, prevê o que dá `"7" * 4`, na consola. Dá `'7777'`: entre um texto e um número, o `*` não multiplica, repete o texto. E o programa não dá nenhuma mensagem. É um erro de lógica, que só a comparação com o resultado esperado mostra.

Para fazer contas, converte-se o texto num número. **Converter** é transformar um valor de um tipo noutro. Há uma função para cada tipo:

| Função | Converte em | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `int(x)` | número inteiro | `int("7")` | `7` |
| `float(x)` | número com parte decimal | `float("2.5")` | `2.5` |
| `str(x)` | texto | `str(7)` | `'7'` |

A forma habitual junta a leitura e a conversão numa só linha. Antes de veres o resultado, prevê o que este programa escreve quando a pessoa escreve 7:

```python
# tabuas.py: lê os troncos do jogador e diz quantas tábuas dão.
TABUAS_POR_TRONCO = 4

# O int converte o texto escrito no teclado num número inteiro.
troncos = int(input("Quantos troncos tens? "))
tabuas = troncos * TABUAS_POR_TRONCO
print("Tábuas:", tabuas)
```

O resultado, com 7:

```text
Quantos troncos tens? 7
Tábuas: 28
```

Leitura guiada: a linha da leitura lê-se de dentro para fora. Primeiro o `input` escreve a pergunta e devolve o texto `"7"`. Depois o `int` converte esse texto no número 7. Só então o 7 é guardado em `troncos`. A partir daí, `troncos` é um número, e a multiplicação dá 28. É o `int troncos = ler valor` do pseudocódigo, com a conversão que o pseudocódigo não precisava de escrever.

O `int` converte só textos que são números inteiros. Se a pessoa escrever `doze`, o programa para:

```text
Quantos troncos tens? doze
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\tabuas.py", line 5, in <module>
    troncos = int(input("Quantos troncos tens? "))
ValueError: invalid literal for int() with base 10: 'doze'
```

O nome do erro é `ValueError`, um erro de valor. A mensagem quer dizer "valor inválido para o `int()` na base 10: 'doze'". A base 10 é a forma normal de escrever números, com os algarismos de 0 a 9. É um erro de execução. Aqui, o programa não está errado: pede um número de troncos, e a pessoa não escreveu um número. Neste tema, os programas partem do princípio de que a pessoa escreve o que lhe pedem. Resistir a entradas erradas é o assunto do tema 07.

O caminho do ficheiro, na linha com `File`, muda de computador para computador. Nos exemplos deste guia, é só uma ilustração.

## Juntar textos

O `print` com vírgulas chega quase sempre. Às vezes, porém, queres o texto exatamente com os espaços que escolheste. Ou queres guardar a frase numa variável. Para isso, juntam-se textos com o `+`.

Entre dois textos, o `+` não soma: junta-os. `"Baú" + " de madeira"` dá `'Baú de madeira'`. Os espaços são os que estão dentro das aspas, e mais nenhum.

Entre um texto e um número, o `+` não sabe o que fazer. Antes de leres, prevê o que acontece com `print("Tábuas: " + 28)`:

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\juntar.py", line 1, in <module>
    print("Tábuas: " + 28)
          ~~~~~~~~~~~^~~~
TypeError: can only concatenate str (not "int") to str
```

O nome do erro é `TypeError`, um erro de tipo. A mensagem quer dizer "só se pode juntar um texto a um texto, e não um `int`". Os sinais `~` e `^` marcam as duas partes da conta e o operador. Para juntar, converte-se o número em texto, com `str`: `"Tábuas: " + str(28)` dá `'Tábuas: 28'`.

## O dinheiro guarda-se em cêntimos

Um bilhete custa 2,50 €. Parece natural guardá-lo como `2.5`. Antes de leres, prevê o que dá `0.1 + 0.2` na consola.

```text
>>> 0.1 + 0.2
0.30000000000000004
```

Não dá `0.3`. O computador guarda os `float` em binário, com uns e zeros. Muitos números com parte decimal, como 0,1, não se conseguem guardar exatamente, e fica um erro muito pequeno. Num jogo, ninguém nota. Com dinheiro, os erros pequenos acumulam-se em milhares de contas, e uma conta deixa de bater certo ao cêntimo.

Por isso, o dinheiro guarda-se em **cêntimos**, num `int`. Os inteiros são sempre exatos. O bilhete de 2,50 € guarda-se como `250`, e as contas fazem-se em cêntimos.

Para mostrar o valor em euros, usam-se o `//` e o `%`, porque um euro tem 100 cêntimos. Com 750 cêntimos, `750 // 100` dá `7`, os euros, e `750 % 100` dá `50`, os cêntimos que sobram. O resultado escreve-se "7 euros e 50 cêntimos". O exemplo guiado faz isto do princípio ao fim.

## Exemplo guiado: os bilhetes do torneio

A escola organiza um torneio de jogos, e cada bilhete custa 2,50 €. Quem vende os bilhetes quer um programa que pergunte quantos bilhetes a pessoa quer e diga quanto tem de pagar, em euros e cêntimos.

### Passo 1: Análise

A entrada é o número de bilhetes, um número inteiro igual ou maior do que zero. A saída é o total a pagar, em euros e cêntimos. O preço de um bilhete é uma regra, que não muda: 2,50 €.

Antes de escrever código, escreve-se a tabela de entradas e saídas, com o resultado esperado calculado à mão. Uma **tabela de entradas e saídas** tem uma linha por caso de teste, com o que se escreve no teclado e o que deve aparecer. É a tabela de casos esperados do guia 05 da algoritmia, agora para um programa que se corre.

| Bilhetes | Conta à mão | Saída esperada |
| ---: | --- | --- |
| 0 | 0 vezes 250 dá 0 cêntimos | `Total: 0 euros e 0 cêntimos` |
| 1 | 1 vezes 250 dá 250 cêntimos | `Total: 2 euros e 50 cêntimos` |
| 3 | 3 vezes 250 dá 750 cêntimos | `Total: 7 euros e 50 cêntimos` |
| 4 | 4 vezes 250 dá 1000 cêntimos | `Total: 10 euros e 0 cêntimos` |

O caso 0 testa o mínimo. O caso 4 dá euros certos, sem cêntimos: é a fronteira dos cêntimos, onde o resto dá 0.

### Passo 2: Desenho

Em pseudocódigo, com o dinheiro em cêntimos:

```text
const PRECO_BILHETE = 250
Escreve: "Quantos bilhetes queres? "
int bilhetes = ler valor
int total = bilhetes * PRECO_BILHETE
int euros = total div 100
int centimos = total resto 100
Escreve: "Total: ", euros, " euros e ", centimos, " cêntimos"
```

### Passo 3: Implementação

Cada linha passa para Python, com as mudanças que este guia explicou:

- o nome da constante em maiúsculas, sem `const`;
- as variáveis sem tipo à frente;
- o `input` com o `int`;
- o `//` e o `%`, no lugar do `div` e do `resto`;
- o `print` com vírgulas, sem espaços dentro das aspas.

```python
# bilhetes.py: diz quanto custam os bilhetes do torneio da escola, em euros e cêntimos.
# O dinheiro guarda-se em cêntimos, num int, para as contas serem exatas.
PRECO_BILHETE = 250
CENTIMOS_POR_EURO = 100

bilhetes = int(input("Quantos bilhetes queres? "))
total = bilhetes * PRECO_BILHETE

# Os euros são as centenas de cêntimos; o resto são os cêntimos que sobram.
euros = total // CENTIMOS_POR_EURO
centimos = total % CENTIMOS_POR_EURO
print("Total:", euros, "euros e", centimos, "cêntimos")
```

### Passo 4: Testes

Antes de correr, prevê o que aparece com 3 bilhetes. Depois corre o programa quatro vezes, uma por linha da tabela, e compara. Com 3 bilhetes, aparece:

```text
Quantos bilhetes queres? 3
Total: 7 euros e 50 cêntimos
```

Com 4 bilhetes, `Total: 10 euros e 0 cêntimos`. Com 0, `Total: 0 euros e 0 cêntimos`. Com 1, `Total: 2 euros e 50 cêntimos`. Os quatro casos dão a saída esperada, e o programa passou nos testes.

### Passo 5: Um erro de lógica que os testes apanham

Imagina que, na implementação, tinhas escrito `euros = total / CENTIMOS_POR_EURO`, com uma só barra. O programa corria sem mensagem. Com 3 bilhetes, escrevia `Total: 7.5 euros e 50 cêntimos`. Comparando com a tabela, a diferença salta à vista: o `7.5` é um `float`, e já inclui os cêntimos, que aparecem duas vezes. Depura-se com método, como no guia anterior. É um erro de lógica, e a hipótese é "a divisão dos euros não é inteira". Confirma-se na linha dos euros. A correção é usar `//`, e voltar a testar os quatro casos.

Com o `/`, os quatro casos falham, e qualquer um apanha o erro. O que fez o trabalho foi a tabela de entradas e saídas, escrita antes de correr.

## Erros frequentes

### A conversão esquecida

Escreveste `troncos = input("Quantos troncos tens? ")`, sem o `int`, e fizeste contas com `troncos`. Com o `*`, o texto repete-se: 7 troncos dão `7777` tábuas, sem mensagem. Com o `+` entre o texto e um número, aparece `TypeError`. Com o `//`, também. Acontece porque o `input` devolve sempre um texto. Corrige-se pondo o `int` à volta do `input`, na linha da leitura.

### Espaços a mais no `print`

O resultado tem dois espaços seguidos, como em `Vão  2  caixas`. Acontece quando se põem espaços dentro das aspas e se separam os valores com vírgulas, porque o `print` já põe um espaço entre eles. Tira os espaços das aspas, junto às vírgulas.

### Uma variável usada antes de ter valor

Aparece `NameError: name '...' is not defined`, com o nome de uma variável tua. Há duas causas possíveis. A variável é usada antes da linha que lhe dá valor. Ou o nome está escrito de outra maneira, como `Troncos` em vez de `troncos`. Confirma a ordem das linhas e o nome, letra a letra.

## Palavras novas deste guia

- Variável: um nome que guarda um valor, para o programa o usar mais tarde.
- Atribuição: a instrução com `=`, que guarda o valor da direita na variável da esquerda.
- Constante: uma variável com o nome em maiúsculas, que se combina não mudar.
- Convenção: uma forma combinada de fazer as coisas, que se respeita mesmo sem a linguagem a impor.
- `int`, `float`, `str` e `bool`: os tipos dos números inteiros, dos números com parte decimal, dos textos e dos valores verdadeiro e falso.
- Expressão: uma conta escrita num programa, com valores, variáveis e operadores.
- Operador: o sinal que diz que conta se faz, como o `+` ou o `//`.
- Potência: a conta com `**`, que multiplica um número por si próprio várias vezes; elevar a `0.5` dá a raiz quadrada.
- Divisão inteira: a conta com `//`, que diz quantas vezes um número cabe noutro.
- Resto: a conta com `%`, que diz o que sobra da divisão inteira.
- Função predefinida: um pedaço de programa que já vem com a linguagem, com um nome, pronto a usar.
- Argumento: o valor que se dá a uma função, entre parênteses.
- Converter: transformar um valor de um tipo noutro, como o texto `"7"` no número 7.
- Cêntimos: a unidade em que se guarda o dinheiro num programa, num `int`, para as contas serem exatas.
- Tabela de entradas e saídas: uma tabela com uma linha por caso de teste. Cada linha diz o que se escreve no teclado e o que deve aparecer.

## Verificar o que aprendeste

1. O que escreve este programa? Faz a tabela de trace de `moedas`.

   ```python
   # moedas.py: as moedas de um jogador ao longo de uma partida.
   moedas = 20
   moedas = moedas + 15
   moedas = moedas - 8
   print("Moedas:", moedas)
   ```

2. Dos nomes `totalTabuas`, `total_tabuas`, `total tabuas` e `2troncos`, quais é que o Python aceita? Qual deles segue a forma do Python?
3. De que tipo é cada um destes valores: `12`, `12.0`, `"12"` e `False`?
4. O que escrevem `print("Pedra:", 30)` e `print("Pedra: ", 30)`? Qual deles tem espaços a mais, e porquê?
5. Quanto dão `23 // 5`, `23 % 5` e `23 / 5`? Confirma as duas primeiras com a regra do divisor vezes a divisão inteira, mais o resto.
6. Quanto dão `3 + 6 / 3` e `(3 + 6) / 3`? Porque é que os dois resultados são `float`?
7. Quanto dão `round(4.5)`, `round(5.5)` e `int(4.9)`?
8. Um programa tem `vidas = input("Quantas vidas? ")` e, depois, `print(vidas * 2)`. A pessoa escreve 3. O que aparece, e porquê? Como se corrige?
9. Porque é que o dinheiro se guarda em cêntimos, num `int`? Como se mostram 1205 cêntimos em euros e cêntimos?
10. Para que serve a tabela de entradas e saídas, e porque é que se escreve antes de correr o programa?

## O que vem a seguir

Para praticar este tema, faz o [laboratório](02-dados-e-interacao-laboratorio.md) e depois a [ficha de exercícios](02-dados-e-interacao-exercicios.md). O tema seguinte é Seleção, em que o programa passa a decidir, com o `if`, o que faz a seguir.

## Para saber mais

- [Python como calculadora](https://docs.python.org/3/tutorial/introduction.html#using-python-as-a-calculator): a parte do tutorial oficial, em inglês, sobre os números, as contas e os textos na consola.

![Rodapé](../imagens/rodape.png)
