![Cabeçalho](../imagens/cabecalho.png)

# Seleção

Módulo UC00606, Desenvolver programas em linguagem estruturada. Neste guia, os teus programas passam a decidir: fazem uma coisa num caso e outra coisa noutro, conforme os valores que leem. Vais passar para Python as decisões que já escreves em pseudocódigo e testar cada caminho nas fronteiras. Para praticar, há o [laboratório](laboratorios/03-selecao-laboratorio.md) e a [ficha de exercícios](exercicios/03-selecao-exercicios.md) deste tema.

No tema anterior, os programas faziam sempre as mesmas contas e escreviam sempre as mesmas linhas, fosse qual fosse o valor lido. A partir de agora, o que o programa faz depende dos dados. A ideia já a conheces: é o `Se`, o `Senão se` e o `Senão` da algoritmia. Este guia não a volta a explicar de raiz. Concentra-se no que muda no Python e no que o Python não perdoa. O programa ainda não repete instruções: se a pessoa escrever um valor que não serve, o programa avisa e acaba. Voltar a pedir o valor é o assunto do tema seguinte.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Programas que decidem
4. As comparações dão `True` ou `False`
5. Decidir com `if`
6. Os dois pontos e a indentação são obrigatórios
7. Dois caminhos: `if` e `else`
8. Mais de dois caminhos: a cadeia com `elif`
9. Juntar condições com `and`, `or` e `not`
10. Validar um valor: dentro e fora de um intervalo
11. Uma decisão dentro de outra
12. Os casos de teste de cada ramo
13. Exemplo guiado: a nota do teste, do pseudocódigo ao Python
14. Erros frequentes
15. Palavras novas deste guia
16. Verificar o que aprendeste
17. O que vem a seguir
18. Para saber mais

## O que vais aprender

No fim deste guia, consegues:

- escrever comparações em Python e prever se dão `True` ou `False`, também com textos;
- passar para Python o `Se`, o `Senão se` e o `Senão` do pseudocódigo, com os dois pontos e a indentação certos;
- juntar condições com `and`, `or` e `not`, e confirmar se um valor está dentro de um intervalo;
- validar um valor antes de o usar e pôr uma decisão dentro de outra quando ela só faz sentido num dos ramos;
- encontrar um ramo que nenhum valor consegue alcançar;
- escolher os casos de teste de cada ramo e de cada limite antes de correr o programa, e confirmá-los no computador.

## O que já sabes e vais usar

- Correr um programa no terminal, com o teu comando, `python`, `py` ou `python3`: guia [01 Do algoritmo ao programa](01-do-algoritmo-ao-programa.md).
- A consola do Python, com o `>>>`: guia [01 Do algoritmo ao programa](01-do-algoritmo-ao-programa.md).
- Os três tipos de erro, como se lê uma mensagem e os cinco passos da depuração: guia [01 Do algoritmo ao programa](01-do-algoritmo-ao-programa.md).
- As variáveis, as constantes em maiúsculas e os nomes com traço baixo: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `print` com vários valores separados por vírgulas: guia [02 Dados e interação](02-dados-e-interacao.md).
- A tabela de entradas e saídas, com o resultado esperado de cada caso calculado antes de correr: guia [02 Dados e interação](02-dados-e-interacao.md).
- Os tipos `int`, `float`, `str` e `bool`, com os valores `True` e `False`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `input`, que devolve sempre um texto, e a conversão com `int`: guia [02 Dados e interação](02-dados-e-interacao.md).
- As contas, com `+`, `-`, `*`, `//` e `%`: guia [02 Dados e interação](02-dados-e-interacao.md).
- As condições, os seis operadores de comparação e a diferença entre `=` e `==`, no pseudocódigo. Estão no guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), nas secções "Condições", "Operadores de comparação" e "Dois sinais de igual para perguntar".
- O `Se`, o `Senão se` e o `Senão`, com a indentação a marcar cada ramo. Estão no guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), nas secções "Seleção simples", "Seleção composta" e "Seleção encadeada".
- Os operadores `e`, `ou` e `não`, e os parênteses quando se misturam: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secções "Operador `e`" a "Misturar `e` e `ou`".
- Os intervalos, o contrário de um intervalo e a validação de uma entrada. Estão no guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), nas secções "Intervalos", "O contrário de um intervalo" e "Validar os dados antes de os usar".
- Os limites, as fronteiras e a tabela de casos esperados, escrita antes do algoritmo. Estão no guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), nas secções "Fronteiras e casos de teste" e "A árvore de casos e a tabela de casos esperados".
- A decisão aninhada, um `Se` dentro de um ramo de outro: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Uma decisão dentro de outra".

## Programas que decidem

No inventário de um jogo de construção, o jogador pede para construir um baú. Se tiver tábuas que cheguem, o baú é construído e as tábuas descontam-se. Se não tiver, o pedido é recusado, e o jogo diz quantas faltam. Se pedir menos três baús, o jogo nem devia fazer contas: o pedido não faz sentido. O programa é o mesmo nos três casos, mas o que faz depende dos valores.

Na algoritmia escrevias estas decisões com `Se`, `Senão se` e `Senão`. Em Python, as ideias são as mesmas. Uma condição dá verdadeiro ou falso, cada ramo tem as suas instruções, e numa cadeia a primeira condição verdadeira ganha. Mudam três coisas. As palavras passam a ser as do Python, em inglês. As regras de escrita passam a ser obrigatórias, e os dois pontos ou um espaço a menos param o programa. E já não és tu que segues cada ramo numa tabela: é o computador, e podes experimentar cada caso em poucos segundos.

## As comparações dão `True` ou `False`

Uma decisão começa sempre numa pergunta de sim ou não. No pseudocódigo era uma condição, como `stock > 0`. Em Python também.

Os seis operadores de comparação escrevem-se exatamente como no pseudocódigo das aulas:

| Operador | Pergunta | Exemplo, com `tabuas = 24` | Resultado |
| --- | --- | --- | --- |
| `==` | é igual a? | `tabuas == 24` | `True` |
| `!=` | é diferente de? | `tabuas != 24` | `False` |
| `<` | é menor do que? | `tabuas < 24` | `False` |
| `<=` | é menor ou igual a? | `tabuas <= 24` | `True` |
| `>` | é maior do que? | `tabuas > 16` | `True` |
| `>=` | é maior ou igual a? | `tabuas >= 32` | `False` |

A diferença está no resultado. No pseudocódigo escrevias `true` e `false`. O Python escreve `True` e `False`, com maiúscula, os dois valores do tipo `bool` que conheceste no guia 02. Lá, só guardaste valores destes, como `tem_picareta = True`. Aqui vês de onde eles costumam vir: de uma comparação.

Na consola, uma comparação mostra logo o resultado. Antes de veres as respostas, prevê o que dá cada linha:

```text
>>> tabuas = 24
>>> tabuas >= 16
True
>>> tabuas >= 32
False
>>> type(tabuas >= 16)
<class 'bool'>
>>> tabuas
24
```

A primeira linha não mostra nada, porque é uma atribuição: guarda o 24 e não responde. As duas comparações respondem `True` e `False`. O `type` confirma que o resultado de uma comparação é um `bool`. A última linha mostra que comparar não mudou nada: `tabuas` continua a valer 24.

É a regra do pseudocódigo, e o Python segue-a à letra. Um só `=` guarda um valor. Dois, `==`, perguntam se dois valores são iguais.

### Comparar textos

Os operadores `==` e `!=` também comparam textos. Dois textos só são iguais se tiverem os mesmos caracteres, pela mesma ordem. As maiúsculas contam, e os espaços também. Antes de veres as respostas, prevê:

```text
>>> "pedra" == "pedra"
True
>>> "Pedra" == "pedra"
False
>>> "pedra " == "pedra"
False
>>> "S" != "N"
True
```

Na segunda linha, o `P` maiúsculo e o `p` minúsculo são caracteres diferentes. Na terceira, o primeiro texto tem um espaço no fim, e por isso tem um carácter a mais. Imagina um programa que pergunta "Tens a chave (S/N)?" e compara a resposta com `"S"`. Uma pessoa que escreva `s` minúsculo fica com a resposta errada. Mais à frente, na secção do `or`, vês como aceitar as duas.

## Decidir com `if`

A seleção simples do pseudocódigo executa um bloco só quando a condição é verdadeira. Em Python, escreve-se com `if`, que quer dizer "se". A forma é esta:

```python fragment forma geral, com palavras no lugar da condição e das instruções
if condição:
    instruções que só correm quando a condição dá True
```

A linha do `if` tem a condição e acaba em dois pontos. As instruções que dependem dela vêm por baixo, quatro espaços mais para dentro. A um conjunto de instruções com a mesma indentação, que correm juntas, chama-se **bloco**. O bloco do `if` acaba na primeira linha que volta à coluna do `if`. Essa linha já está fora da decisão, e corre sempre.

No inventário, o jogo avisa quando as tábuas estão quase a acabar. Antes de leres o resultado, prevê o que aparece com 3 tábuas e com 12:

```python
# stock_baixo.py: avisa quando as tábuas do inventário estão quase a acabar.
LIMITE_AVISO = 5

tabuas = int(input("Quantas tábuas tens? "))
# O bloco do if só corre quando a condição dá True.
if tabuas < LIMITE_AVISO:
    print("Atenção: tens poucas tábuas.")
print("Inventário verificado.")
```

Com 3 tábuas:

```text
Quantas tábuas tens? 3
Atenção: tens poucas tábuas.
Inventário verificado.
```

Com 12 tábuas:

```text
Quantas tábuas tens? 12
Inventário verificado.
```

Com 3, a condição `3 < 5` dá `True`, e o bloco corre: aparece o aviso. Com 12, `12 < 5` dá `False`, e o bloco é saltado. Nos dois casos aparece "Inventário verificado.", porque essa linha está encostada à margem, fora do bloco.

Leitura guiada: lê primeiro a linha do `if` e a sua condição. Depois olha para a margem esquerda das linhas de baixo. O `print` do aviso começa quatro espaços para dentro, e por isso pertence ao bloco do `if`. O último `print` começa na coluna do `if`, e por isso já está fora. É a mesma leitura que fazias no pseudocódigo, linha a linha, pela coluna onde cada uma começa.

No VS Code, quando carregas em Enter depois dos dois pontos, a linha nova já começa com quatro espaços. Para voltares à margem, no fim do bloco, apagas esses espaços. A tecla Tab, no VS Code, também escreve quatro espaços. Usa sempre espaços, e sempre quatro por nível.

### O `=` no lugar do `==`

Numa decisão, a condição é uma pergunta, e por isso leva dois sinais, `==`. Com um só `=`, o Python recusa o programa, e até sugere a correção. Antes de leres o resultado, prevê se a pergunta das tábuas chega a aparecer:

```python fragment erro de sintaxe de propósito: um só sinal de igual na condição
# esgotado.py: avisa quando as tábuas do inventário acabaram.
tabuas = int(input("Quantas tábuas tens? "))
if tabuas = 0:
    print("Esgotado")
```

O resultado é este:

```text
  File "C:\Users\aluno\Documents\lp-python\esgotado.py", line 3
    if tabuas = 0:
       ^^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
```

A mensagem quer dizer "escrita inválida: talvez quisesses `==` ou `:=` em vez de `=`". O `:=` é uma forma que não vais usar nesta disciplina. Num Python mais antigo, a mensagem diz só `invalid syntax`, sem a sugestão. Em qualquer dos casos, é um erro de sintaxe: a pergunta das tábuas não aparece, porque nenhuma linha corre. Se a linha é uma pergunta, leva dois sinais.

### Um texto não se compara com um número

O `input` devolve sempre um texto, como viste no guia 02. Se te esqueceres do `int`, a comparação com um número falha. Antes de leres o resultado, prevê o que acontece neste programa quando a pessoa escreve 3:

```python
# pedido_sem_int.py: compara a resposta do input com um número, sem a converter.
baus = input("Quantos baús queres construir? ")
if baus >= 1:
    print("Pedido registado.")
```

O resultado, com 3:

```text
Quantos baús queres construir? 3
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\pedido_sem_int.py", line 3, in <module>
    if baus >= 1:
       ^^^^^^^^^
TypeError: '>=' not supported between instances of 'str' and 'int'
```

É um erro de execução, um `TypeError`. A mensagem quer dizer "o `>=` não funciona entre um texto e um inteiro". O Python não sabe se o texto `"3"` é maior ou menor do que o número 1, e recusa-se a adivinhar. A causa está na linha 2, onde falta o `int`, e não na linha 3, onde o Python deu pelo problema. Corrige-se como no guia 02: `baus = int(input("Quantos baús queres construir? "))`.

## Os dois pontos e a indentação são obrigatórios

No pseudocódigo, a indentação já mostrava o que ficava dentro de cada decisão, mas um espaço a mais não impedia ninguém de o ler. No Python, um espaço a mais ou a menos impede o programa de correr. É ela, e só ela, que diz que linhas estão dentro de um bloco. Os dois pontos no fim da linha do `if` também são obrigatórios: anunciam que vem um bloco. Sem um deles, o programa não corre.

Sem os dois pontos, a mensagem é esta:

```text
  File "C:\Users\aluno\Documents\lp-python\stock_baixo.py", line 6
    if tabuas < LIMITE_AVISO
                            ^
SyntaxError: expected ':'
```

A mensagem quer dizer "erro de sintaxe: esperava `:`". O sinal `^` aponta para o fim da linha, onde faltam os dois pontos. Num Python mais antigo, a mensagem diz só `invalid syntax`.

Sem a indentação no bloco, isto é, com o `print` do aviso encostado à margem, a mensagem é outra:

```text
  File "C:\Users\aluno\Documents\lp-python\stock_baixo.py", line 7
    print("Atenção: tens poucas tábuas.")
    ^^^^^
IndentationError: expected an indented block after 'if' statement on line 6
```

O nome do erro é `IndentationError`, um erro de indentação. A mensagem quer dizer "esperava um bloco indentado depois do `if` da linha 6". Um `if` sem bloco não faz sentido, e o Python recusa o programa inteiro. É um erro de sintaxe, como os outros: nenhuma linha correu, nem a do `input`. É também um dos erros que, como viste no guia 01, tem um nome próprio diferente de `SyntaxError`.

Há um terceiro caso, sem mensagem nenhuma, e é o mais traiçoeiro. Imagina que o último `print` ficou indentado, com os quatro espaços:

```python
# stock_baixo.py: avisa quando as tábuas do inventário estão quase a acabar.
LIMITE_AVISO = 5

tabuas = int(input("Quantas tábuas tens? "))
# O bloco do if só corre quando a condição dá True.
if tabuas < LIMITE_AVISO:
    print("Atenção: tens poucas tábuas.")
    print("Inventário verificado.")
```

O programa corre. Com 3 tábuas, dá exatamente o mesmo de antes. Com 12, aparece só a pergunta, e mais nada, porque as duas linhas passaram para dentro do bloco, e o bloco foi saltado. É um erro de lógica: só a comparação com o resultado esperado o mostra, e só num caso em que a condição dá `False`. Por isso, um teste de uma decisão experimenta sempre os dois lados.

## Dois caminhos: `if` e `else`

A seleção composta do pseudocódigo escolhe entre dois blocos. Em Python, o `Senão` escreve-se `else`, que quer dizer "senão", sem condição e com dois pontos. O `else` fica na mesma coluna do `if` a que pertence, e o seu bloco fica quatro espaços para dentro.

No jogo, uma ponte de madeira aguenta no máximo 4 jogadores de cada vez. Antes de leres o resultado, prevê o que aparece com 3, com 4 e com 5 jogadores:

```python
# ponte.py: a ponte de madeira do jogo aguenta no máximo 4 jogadores de cada vez.
MAXIMO_NA_PONTE = 4

jogadores = int(input("Quantos jogadores querem atravessar? "))
if jogadores <= MAXIMO_NA_PONTE:
    print("Podem atravessar.")
else:
    print("A ponte não aguenta. Atravessem em dois grupos.")
print("Fim da travessia.")
```

| jogadores | `jogadores <= 4` | Bloco que corre | Ecrã |
| ---: | --- | --- | --- |
| 3 | `True` | o do `if` | Podem atravessar. Fim da travessia. |
| 4 | `True` | o do `if` | Podem atravessar. Fim da travessia. |
| 5 | `False` | o do `else` | A ponte não aguenta. Atravessem em dois grupos. Fim da travessia. |

Cada linha do ecrã aparece numa linha à parte. Na tabela, ficaram lado a lado para caberem.

Leitura guiada: a condição avalia-se uma vez. Se der `True`, corre o bloco do `if` e salta-se o do `else`. Se der `False`, salta-se o do `if` e corre o do `else`. Corre sempre exatamente um dos dois. O último `print` está fora dos dois blocos, na coluna do `if`, e aparece sempre. O 4 é o limite, e `4 <= 4` dá `True`: com exatamente 4 jogadores, ainda podem atravessar. É entre o 4 e o 5 que a resposta muda, e a esse sítio chama-se fronteira, como na algoritmia.

O `else` nunca leva condição. Ele apanha todos os casos em que a condição do `if` deu `False`, e por isso não precisa de perguntar nada. Escrever `else jogadores > 4:` é um erro de sintaxe.

## Mais de dois caminhos: a cadeia com `elif`

A seleção encadeada do pseudocódigo usava `Senão se`. Em Python escreve-se `elif`, uma palavra só, que junta o "else" e o "if". Leva condição e dois pontos, como o `if`. As três regras da cadeia são as mesmas da algoritmia:

1. As condições avaliam-se de cima para baixo.
2. A primeira verdadeira ganha, e as outras nem chegam a ser avaliadas.
3. Se nenhuma for verdadeira, corre o `else`.

Este é o algoritmo do estado do stock, do guia 03 da algoritmia, passado para Python. Antes de leres o resultado, prevê o que aparece com 0, com 3 e com 9 tábuas:

```python
# estado_stock.py: classifica as tábuas do inventário em esgotadas, poucas ou normais.
LIMITE_AVISO = 5

tabuas = int(input("Quantas tábuas tens? "))
if tabuas == 0:
    print("Esgotado")
elif tabuas < LIMITE_AVISO:
    print("Stock baixo")
else:
    print("Stock normal")
```

| tabuas | `tabuas == 0` | `tabuas < 5` | Bloco que corre | Ecrã |
| ---: | --- | --- | --- | --- |
| 0 | `True` | não é avaliada | o do `if` | Esgotado |
| 3 | `False` | `True` | o do `elif` | Stock baixo |
| 9 | `False` | `False` | o do `else` | Stock normal |

Leitura guiada: lê a cadeia de cima para baixo, uma pergunta de cada vez, e para na primeira que der `True`. Com 0, a primeira pergunta já dá `True`, e a segunda nem se faz. A segunda também daria `True`, porque 0 é menor do que 5, mas a cadeia já acabou. O `if`, o `elif` e o `else` estão na mesma coluna: é isso que mostra que são a mesma cadeia. Uma cadeia pode ter os `elif` que forem precisos, um a seguir ao outro, e o `else` no fim é opcional.

### A ordem conta: o ramo inacessível

Como a primeira condição verdadeira ganha, a ordem das condições muda o resultado. Imagina a mesma cadeia com as duas perguntas trocadas:

```python
# estado_stock.py, com as perguntas trocadas: o ramo do Esgotado nunca corre.
LIMITE_AVISO = 5

tabuas = int(input("Quantas tábuas tens? "))
if tabuas < LIMITE_AVISO:
    print("Stock baixo")
elif tabuas == 0:
    print("Esgotado")
else:
    print("Stock normal")
```

Antes de continuares, procura um número de tábuas que faça aparecer "Esgotado". Não existe. Com 0, a primeira condição, `0 < 5`, já dá `True`, e aparece "Stock baixo". Para chegar ao `elif`, a primeira condição tem de dar `False`, e isso quer dizer 5 tábuas ou mais. Com 5 ou mais, `tabuas == 0` dá sempre `False`.

A um ramo que nenhum valor consegue alcançar chama-se **ramo inacessível**. O programa corre sem mensagem, mas o ramo está lá para nada, e um caso do enunciado nunca é tratado. Um ramo inacessível nasce quase sempre de uma destas duas causas. Uma é uma condição mais larga, que apanha todos os valores de outra e mais alguns, escrita antes dela. É o caso daqui: `tabuas < 5` apanha o 0, e também o 1, o 2, o 3 e o 4. A outra é uma condição que nunca pode dar `True`, que vais ver na secção da validação.

Para encontrares um ramo inacessível, faz a pergunta desta secção a cada ramo: que valor faz correr este bloco? Se não encontrares nenhum, o ramo é inacessível. Numa cadeia, a condição que apanha menos valores vem primeiro, e a validação vem antes de tudo.

## Juntar condições com `and`, `or` e `not`

Os operadores lógicos são os do pseudocódigo, com as mesmas tabelas de verdade. Só mudam as palavras, que passam para inglês e se escrevem em minúsculas:

| Pseudocódigo | Python | Dá `True` quando |
| --- | --- | --- |
| `e` | `and` | as duas partes dão `True` |
| `ou` | `or` | pelo menos uma das partes dá `True` |
| `não` | `not` | a parte a seguir dá `False` |

### `and`: as duas coisas ao mesmo tempo

No jogo, para partir uma pedra precisas de uma picareta e de pelo menos 2 de energia. Antes de leres o resultado, prevê o que aparece com 1 e com 2 de energia:

```python
# picareta.py: partir uma pedra pede uma picareta e energia que chegue.
ENERGIA_PARA_PARTIR = 2

tem_picareta = True
energia = int(input("Quanta energia tens? "))
if tem_picareta and energia >= ENERGIA_PARA_PARTIR:
    print("Partiste a pedra.")
else:
    print("Não consegues partir a pedra.")
```

Com 1 de energia, aparece "Não consegues partir a pedra.". Com 2, aparece "Partiste a pedra.". Muda a linha da picareta para `tem_picareta = False`, e com qualquer energia aparece "Não consegues partir a pedra.".

Leitura guiada: o `tem_picareta` entra na condição sozinho, sem comparação. É um `bool`, e já vale `True` ou `False`, que é o que uma condição tem de dar. Escrever `tem_picareta == True` dava o mesmo, com mais letras. O `and` só dá `True` se as duas partes derem `True`: a picareta e a energia que chegue. Basta uma faltar para correr o `else`.

### `or`: basta uma

O `or` dá `True` quando pelo menos uma das partes dá `True`. É assim que se aceita uma resposta escrita com maiúscula ou com minúscula:

```python
# chave.py: aceita a resposta S ou s, porque as duas querem dizer sim.
resposta = input("Tens a chave (S/N)? ")
if resposta == "S" or resposta == "s":
    print("A porta abriu.")
else:
    print("A porta continua fechada.")
```

Com `S` ou com `s`, a porta abre. Com `N`, com `n` ou com qualquer outra coisa, continua fechada. Repara que cada lado do `or` é uma comparação completa, com a variável, o `==` e o texto. Escrever só `resposta == "S" or "s"` não faz o que parece. O Python lê o `"s"` sozinho como a segunda parte do `or`, e um texto que não está vazio conta como verdadeiro. O bloco do `if` corre com qualquer resposta. Uma comparação de cada lado, sempre.

### `not`: o contrário

O `not` troca o valor da condição que vem a seguir. `not tem_picareta` dá `True` quando o jogador não tem a picareta:

```python fragment usa a variável tem_picareta do picareta.py, criada mais acima
if not tem_picareta:
    print("Primeiro precisas de uma picareta.")
```

Como no pseudocódigo, quase sempre se pode escrever o contrário sem o `not`, trocando a comparação. `not (energia >= 2)` é o mesmo que `energia < 2`, que se lê melhor. Os parênteses mostram que o `not` troca a comparação inteira, como no pseudocódigo. O `not` fica para os `bool`, como `not tem_picareta`, onde não há comparação para trocar.

### Quando se misturam `and` e `or`

A regra das aulas continua: quando misturas `and` com `or`, usa parênteses para mostrar o que se avalia primeiro. As comparações calculam-se sempre antes do `and`, do `or` e do `not`. Por exemplo, para o jogador abrir o portão com a chave ou com 3 cristais, mas só de dia:

```python fragment mostra só a condição; as variáveis vêm de um programa que não está aqui
if (tem_chave or cristais >= 3) and de_dia:
    print("O portão abriu.")
```

Sem os parênteses, o Python faria o `and` antes do `or`, e a condição diria outra coisa: a chave abria o portão também de noite. Com parênteses, não há dúvida para ninguém.

## Validar um valor: dentro e fora de um intervalo

Validar é confirmar que um valor serve, antes de o usar. Na algoritmia, a validação vinha sempre em primeiro lugar, e em Python também. Um valor dentro de um intervalo escreve-se com duas comparações ligadas por `and`. Um valor fora escreve-se com `or`, com cada comparação trocada pela contrária. Num jogo com os níveis de dificuldade 1, 2 e 3:

```python fragment as duas condições, só para comparar; o programa completo vem a seguir
dificuldade >= 1 and dificuldade <= 3
dificuldade < 1 or dificuldade > 3
```

A primeira linha é a condição de dentro: o valor tem de cumprir as duas comparações. A segunda é a de fora: basta falhar uma. O `and` passou a `or`, e cada limite mudou de lado, como no guia 03 da algoritmia.

Este programa valida a dificuldade antes de a usar. Antes de leres o resultado, prevê o que aparece com 0, com 1, com 3 e com 4:

```python
# dificuldade.py: confirma o nível de dificuldade escolhido, de 1 a 3.
DIFICULDADE_MINIMA = 1
DIFICULDADE_MAXIMA = 3

dificuldade = int(input("Dificuldade (1 a 3)? "))
# A validação vem primeiro: um valor fora do intervalo não se usa.
if dificuldade < DIFICULDADE_MINIMA or dificuldade > DIFICULDADE_MAXIMA:
    print("Essa dificuldade não existe.")
else:
    print("Dificuldade escolhida:", dificuldade)
```

| dificuldade | `dificuldade < 1` | `dificuldade > 3` | Com `or` | Ecrã |
| ---: | --- | --- | --- | --- |
| 0 | `True` | `False` | `True` | Essa dificuldade não existe. |
| 1 | `False` | `False` | `False` | Dificuldade escolhida: 1 |
| 3 | `False` | `False` | `False` | Dificuldade escolhida: 3 |
| 4 | `False` | `True` | `True` | Essa dificuldade não existe. |

Leitura guiada: o `if` pergunta primeiro se o valor é inválido. Se for, o programa avisa e não faz mais nada com ele, porque o `else` é saltado. Só os valores que passam a validação chegam ao `else`. Os limites são constantes, porque são regras do jogo. A pergunta do `input` diz o intervalo, para quem usa o programa saber o que se espera dele.

O erro típico é ligar as duas comparações de fora com `and`. A condição `dificuldade < 1 and dificuldade > 3` pede um número que seja ao mesmo tempo menor do que 1 e maior do que 3. Nenhum número é as duas coisas, e a condição dá sempre `False`. Com 7, aparece "Dificuldade escolhida: 7". O ramo do aviso ficou inacessível: é a segunda causa da secção do `elif`, uma condição que nunca pode dar `True`. Com valores do meio, como o 2, este erro não se nota.

O Python aceita também uma forma mais curta, `1 <= dificuldade <= 3`, que se lê como na matemática. Vais encontrá-la em programas de outras pessoas. Nas aulas continuamos a escrever duas comparações ligadas por `and`, como na algoritmia, porque se leem da mesma maneira em todas as linguagens.

A validação com `if` só funciona depois de o `int` converter o texto num número. Se a pessoa escrever `dois`, o programa para antes do `if`, com o `ValueError` que viste no guia 02. Por agora, quem usa o programa escreve um número inteiro. Apanhar esse erro sem o programa parar é o assunto do tema 07, Validar e depurar.

## Uma decisão dentro de outra

Às vezes, uma decisão só faz sentido num dos ramos de outra. Um baú com cadeado só se abre com a chave. E só depois de aberto faz sentido perguntar se tem um tesouro. A segunda decisão vai para dentro do bloco da primeira, como a decisão aninhada do pseudocódigo.

Antes de leres o resultado, prevê o que aparece em três casos: `S` e 150 moedas, `S` e 40 moedas, e `N`.

```python
# bau.py: um baú com cadeado só se abre com a chave, e pode ter um tesouro.
MOEDAS_DE_TESOURO = 100

chave = input("Tens a chave (S/N)? ")
if chave == "S" or chave == "s":
    print("O baú abriu.")
    # As moedas só se contam depois de o baú abrir, e o if de dentro também.
    moedas = int(input("Quantas moedas tem o baú? "))
    if moedas >= MOEDAS_DE_TESOURO:
        print("Encontraste um tesouro.")
    else:
        print("O baú tem", moedas, "moedas.")
else:
    print("O baú está trancado. Precisas da chave.")
```

Com `S` e 150:

```text
Tens a chave (S/N)? S
O baú abriu.
Quantas moedas tem o baú? 150
Encontraste um tesouro.
```

Com `S` e 40, aparecem "O baú abriu." e, depois da pergunta das moedas, "O baú tem 40 moedas.". Com `N`, aparece só "O baú está trancado. Precisas da chave.", e o programa nem pergunta as moedas.

Leitura guiada: começa pelo `if` de fora e decide o ramo. Aceita `S` e `s`, com o `or` da secção anterior. A leitura das moedas e o `if` de dentro estão quatro espaços para dentro, porque pertencem ao bloco do `if` de fora. Os seus `print` estão oito espaços para dentro, porque estão dentro de dois blocos. O primeiro `else`, com quatro espaços, pertence ao `if` de dentro, que está na mesma coluna. O último `else`, encostado à margem, pertence ao `if` de fora. Cada `else` pertence ao `if` que está na mesma coluna, acima dele.

Repara porque é que aqui não chegava uma cadeia com `elif`. A linha "O baú abriu." e a pergunta das moedas correm nos dois casos de dentro, com tesouro e sem tesouro. Numa cadeia, cada ramo tem as suas instruções, e nenhuma é partilhada. Quando há uma parte comum antes da segunda decisão, a decisão aninhada diz-o melhor. Quando não há, a cadeia com `elif` diz o mesmo com menos níveis de indentação, e lê-se melhor.

## Os casos de teste de cada ramo

Um programa com decisões tem vários caminhos, e cada execução percorre só um. Um caso que passa diz que aquele caminho está certo, e não diz nada dos outros. Por isso, os casos de teste de um programa com decisões escolhem-se com duas regras, as da algoritmia. Um limite é o valor de uma regra, como o 4 da ponte; a fronteira é o sítio, junto dele, onde a resposta muda.

- cada ramo tem pelo menos um caso que o faz correr;
- cada limite tem três casos: o valor imediatamente abaixo, o próprio limite e o valor imediatamente acima.

Os resultados esperados escrevem-se antes de correr, a partir do enunciado, e nunca a partir do que o programa mostra. Se os copiares do ecrã, copias o que o programa fez, certo ou errado, e o teste deixa de apanhar erros.

Os casos ficam numa tabela de entradas e saídas, como no guia 02, agora com uma coluna para o ramo que cada caso faz correr. Para o `ponte.py`, é esta:

| jogadores | Ramo | Resultado esperado | Porque é que este caso foi escolhido |
| ---: | --- | --- | --- |
| 3 | o do `if` | Podem atravessar. | Imediatamente abaixo do limite 4 |
| 4 | o do `if` | Podem atravessar. | O próprio limite: com 4, ainda podem |
| 5 | o do `else` | A ponte não aguenta. Atravessem em dois grupos. | Imediatamente acima do limite |

Os dois ramos têm casos, e o único limite tem os seus três casos. Se alguém tivesse escrito `jogadores < MAXIMO_NA_PONTE`, só o caso do 4 falhava. Testar com 2 e com 10 nunca o mostrava.

Num programa sem repetições, cada execução testa um caso. Para testar três casos, corres o programa três vezes. No terminal, a seta para cima do teclado volta a escrever o último comando. Carregas na seta, em Enter, e escreves o valor do caso seguinte.

Se um caso der um resultado diferente do esperado, segues os cinco passos da depuração do guia 01. Primeiro, o caso que falhou, o esperado, o obtido e o tipo de erro. Depois, uma hipótese, que confirmas com os valores. Corriges só a causa e voltas a correr todos os casos, também os que já passavam. As tuas notas da depuração ficam num comentário no fim do ficheiro, para o código não mudar de linha.

## Exemplo guiado: a nota do teste, do pseudocódigo ao Python

No guia 03 da algoritmia, resolveste em pseudocódigo o problema da nota de um teste. Este exemplo passa esse algoritmo para Python e confirma-o com os mesmos casos de teste. Como o problema já está resolvido, a única coisa nova é a linguagem.

### Passo 1: O enunciado

> Um professor quer um programa que o ajude a classificar os testes. O programa lê a nota de um teste, que é um número inteiro na escala de 0 a 20. Se a nota for igual ou superior a 10, escreve "Positiva". Se for inferior a 10, escreve "Negativa". Se a nota escrita não pertencer à escala, o programa escreve "Nota inválida" e não a classifica.

### Passo 2: Os casos de teste, antes do programa

Os limites são o 0, o 10 e o 20. Cada um dá três casos, e cada um dos três ramos tem casos. É a tabela de entradas e saídas, que na algoritmia se chamava tabela de casos esperados, escrita antes de haver programa:

| Nota | Resultado esperado | Porque é que este caso foi escolhido |
| ---: | --- | --- |
| -1 | Nota inválida | Imediatamente abaixo do limite 0 |
| 0 | Negativa | O próprio limite 0, que é uma nota válida |
| 1 | Negativa | Imediatamente acima do limite 0 |
| 9 | Negativa | Imediatamente abaixo do limiar 10 |
| 10 | Positiva | O próprio limiar, que o enunciado diz ser positiva |
| 11 | Positiva | Imediatamente acima do limiar |
| 19 | Positiva | Imediatamente abaixo do limite 20 |
| 20 | Positiva | O próprio limite 20, que é uma nota válida |
| 21 | Nota inválida | Imediatamente acima do limite 20 |

### Passo 3: O pseudocódigo

É o do guia 03 da algoritmia, com a validação em primeiro lugar:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Senão se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

### Passo 4: Traduzir linha a linha

Cada linha passa para Python com as regras deste guia e do guia 02:

| Pseudocódigo | Python | O que mudou |
| --- | --- | --- |
| `const NOTA_MINIMA = 0` | `NOTA_MINIMA = 0` | Sem `const`; o nome em maiúsculas diz que é uma constante |
| `Escreve: "..."` e `int nota = ler valor` | `nota = int(input("..."))` | A pergunta vai no `input`, e o `int` converte o texto |
| `Se condição` | `if condição:` | `if`, e os dois pontos no fim |
| `ou` | `or` | A palavra em inglês |
| `Senão se condição` | `elif condição:` | Uma palavra só, e os dois pontos |
| `Senão` | `else:` | Sem condição, com os dois pontos |
| `Escreve: "Positiva"` | `print("Positiva")` | O `print` |

A indentação não muda: quatro espaços por nível, como no pseudocódigo das aulas.

### Passo 5: O programa completo

```python
# nota.py: classifica a nota de um teste, de 0 a 20, em positiva ou negativa.
NOTA_MINIMA = 0
NOTA_MAXIMA = 20
LIMIAR_POSITIVA = 10

nota = int(input("Nota do teste (inteiro de 0 a 20)? "))
# A validação vem primeiro: uma nota fora da escala não se classifica.
if nota < NOTA_MINIMA or nota > NOTA_MAXIMA:
    print("Nota inválida")
elif nota >= LIMIAR_POSITIVA:
    print("Positiva")
else:
    print("Negativa")
```

Repara que a condição do `elif` não pergunta se a nota é menor ou igual a 20. Não precisa: quando o programa chega ao `elif`, já sabe que a nota é válida, porque se não fosse tinha entrado no primeiro ramo. E a negativa não tem condição nenhuma: uma nota válida que não é positiva só pode ser negativa, e é isso que o `else` apanha.

### Passo 6: Correr os casos

O programa corre-se nove vezes, uma por linha da tabela do passo 2. Com 10, o próprio limiar:

```text
Nota do teste (inteiro de 0 a 20)? 10
Positiva
```

Com 21, acima da escala:

```text
Nota do teste (inteiro de 0 a 20)? 21
Nota inválida
```

Os outros sete casos dão o resultado esperado da tabela. O -1 dá "Nota inválida". O 0, o 1 e o 9 dão "Negativa". O 11, o 19 e o 20 dão "Positiva". Os nove casos passaram, e o programa está confirmado para os três ramos e as três fronteiras.

### Passo 7: O caso que apanha o operador trocado

Imagina que, ao traduzir, tinhas escrito `elif nota > LIMIAR_POSITIVA:`, sem o igual. O programa corria sem mensagem. Corre os nove casos e compara. Oito passam, e só um falha:

```text
Nota do teste (inteiro de 0 a 20)? 10
Negativa
```

Segue os passos da depuração. É um erro de lógica: o caso 10 esperava "Positiva" e deu "Negativa". A hipótese é "a condição da positiva não inclui o 10". Confirma-se com o valor: `10 > 10` dá `False`, e o programa cai no `else`. Corrige-se a causa, voltando a pôr `>=`, e correm-se outra vez os nove casos. É por isso que a tabela tem o próprio limiar: o 9 e o 11 davam o resultado certo com os dois operadores.

## Erros frequentes

### Palavras do pseudocódigo no meio do Python

O que se vê: `SyntaxError: invalid syntax`, numa linha com `se`, `senão`, `e` ou `ou`, como `if nota >= 0 e nota <= 20:`. Com o `ou`, o Python 3.14 acrescenta `Did you mean 'or'?`, isto é, "querias dizer `or`?". Acontece porque a ideia vem do pseudocódigo, e as palavras também vieram. O Python só conhece as suas: `if`, `elif`, `else`, `and`, `or` e `not`. Corrige-se trocando cada palavra pela do Python, com a tabela do passo 4 do exemplo guiado.

### Uma condição no `else`

O que se vê: `SyntaxError: expected ':'`, numa linha como `else nota < 10:`, com o `^` debaixo da condição. Acontece por querer dizer no `else` o caso que ele apanha. O `else` não leva condição: apanha tudo o que as condições de cima deixaram passar. Se precisas de uma condição, usa `elif`. Se não precisas, apaga-a e deixa `else:`.

### Dois `if` separados em vez de uma cadeia

O que se vê: duas mensagens no ecrã, quando devia aparecer uma. Com a nota 21, por exemplo, aparecem "Nota inválida" e "Positiva". Acontece quando a validação e a classificação ficam em dois `if` seguidos, em vez de uma só cadeia:

```python
# nota.py, com dois if separados: uma nota inválida também é classificada.
NOTA_MINIMA = 0
NOTA_MAXIMA = 20
LIMIAR_POSITIVA = 10

nota = int(input("Nota do teste (inteiro de 0 a 20)? "))
if nota < NOTA_MINIMA or nota > NOTA_MAXIMA:
    print("Nota inválida")
if nota >= LIMIAR_POSITIVA:
    print("Positiva")
else:
    print("Negativa")
```

O segundo `if` encostado à margem começa uma decisão nova, que corre sempre, mesmo depois de a primeira ter apanhado uma nota inválida. Com as notas válidas, o programa dá o resultado certo, e por isso só um caso inválido o mostra. Corrige-se trocando o segundo `if` por `elif`: os resultados que são alternativas uns dos outros ficam numa só cadeia.

### O `elif` ou o `else` fora da coluna do seu `if`

O que se vê: `IndentationError: unindent does not match any outer indentation level`, ou `SyntaxError: invalid syntax`, na linha do `elif` ou do `else`. A primeira mensagem quer dizer "o recuo não corresponde a nenhum nível de indentação de fora". Aparece quando o `elif` ou o `else` fica dois ou três espaços para dentro, um recuo que não existe no programa. A segunda aparece quando fica quatro espaços para dentro. O Python vê-o dentro do bloco do `if`, como uma instrução, e um `else` sozinho não é uma instrução. Corrige-se alinhando o `elif` e o `else` com o `if` a que pertencem. O que está dentro de cada bloco fica quatro espaços mais para dentro.

## Palavras novas deste guia

- `if`, `elif` e `else`: as palavras do Python para o `Se`, o `Senão se` e o `Senão` do pseudocódigo. O `if` e o `elif` levam condição; o `else` não leva. Todos acabam em dois pontos.
- `and`, `or` e `not`: as palavras do Python para o `e`, o `ou` e o `não` do pseudocódigo.
- `True` e `False`: os dois valores do tipo `bool`, que é o que uma comparação dá. Escrevem-se com maiúscula.
- Bloco: um conjunto de instruções com a mesma indentação, que correm juntas, como as que estão por baixo de um `if`.
- `IndentationError`: o erro de indentação, quando um bloco falta ou uma linha fica num recuo que não corresponde a nenhum nível. É um erro de sintaxe, e nenhuma linha corre.
- `TypeError` numa comparação: o erro que aparece quando se compara um texto com um número com `<`, `<=`, `>` ou `>=`. Quase sempre, falta o `int` no `input`.
- Ramo inacessível: um ramo que nenhum valor consegue fazer correr, por causa da ordem das condições ou de uma condição que nunca dá `True`.

## Verificar o que aprendeste

1. Com `vidas = 3`, o que mostra a consola para `vidas == 3`, `vidas != 3`, `vidas > 3` e `vidas >= 3`?
2. Qual é a diferença entre `tabuas = 0` e `tabuas == 0`? Qual das duas pode estar na linha de um `if`?
3. O que dá `"Ferro" == "ferro"`, e porquê?
4. Um programa tem `pontos = input("Pontos? ")` e, mais abaixo, `if pontos >= 50:`. A pessoa escreve 60. O que aparece, e onde está a causa?
5. Num `if`, como é que o Python sabe que linhas estão dentro do bloco e qual é a primeira que já está fora?
6. Que tipo de erro é um `IndentationError`? Corre alguma linha do programa?
7. Porque é que o `else` não leva condição?
8. Numa cadeia com `if tempo < 60:` e depois `elif tempo < 30:`, que valores de `tempo` fazem correr o bloco do `elif`? Como se corrige?
9. Escreve em Python a condição "o nível está entre 1 e 10, incluindo os dois" e a condição contrária.
10. Num programa com um `if`, um `elif` e um `else`, quantos casos de teste precisas, no mínimo, para fazer correr todos os ramos? E se o `if` tiver um limite no 10, que casos lhe juntas?

## O que vem a seguir

Para praticar este tema, faz o [laboratório](laboratorios/03-selecao-laboratorio.md) e depois a [ficha de exercícios](exercicios/03-selecao-exercicios.md). O tema seguinte é Ciclo while. Nele, o programa passa a repetir instruções, por exemplo para voltar a pedir um valor até ele ser válido.

## Para saber mais

- [Instruções `if`](https://docs.python.org/3/tutorial/controlflow.html#if-statements): a parte do tutorial oficial do Python, em inglês, sobre o `if`, o `elif` e o `else`.
- [Comparações](https://docs.python.org/3/library/stdtypes.html#comparisons): a tabela oficial dos operadores de comparação, em inglês.

![Rodapé](../imagens/rodape.png)
