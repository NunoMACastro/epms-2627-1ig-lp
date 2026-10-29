![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Dados e interação

Laboratório do tema Dados e interação, do módulo Desenvolver programas em linguagem estruturada. Vais construir a calculadora de material do inventário de um jogo de construção. O programa pergunta quantos troncos tens e diz quantas tábuas dão, quantos baús constróis e quantas tábuas sobram. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](02-dados-e-interacao.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

No fim, tens o programa `inventario.py`, na tua pasta `lp-python`. Quando o corres, ele pergunta quantos troncos tens. Depois mostra o inventário e faz as contas da madeira. Num jogo de construção, cada tronco dá 4 tábuas, e cada baú gasta 8 tábuas. Com 7 troncos, por exemplo, o ecrã fica assim:

```text
Quantos troncos tens? 7
Troncos: 7
Pedra: 30
Ferro: 5
Tábuas: 28
Baús que podes construir: 3
Tábuas que sobram: 4
```

Pelo caminho, ficas a saber guardar valores em variáveis e constantes, fazer contas e ler um valor do teclado. Ficas também a saber converter esse valor num número, para as contas darem certo. No fim, testas o programa com uma **tabela de entradas e saídas**, escrita no caderno antes de correr. É a tabela de casos esperados da algoritmia, agora para um programa que se corre.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | `inventario.py`, com variáveis | O programa mostra o inventário, com os valores guardados em variáveis |
| 2 | Nada no disco; experimentas na consola do Python | Sabes de que tipo é um valor e como o Python faz as contas |
| 3 | `inventario.py`, com constantes e contas | O programa calcula as tábuas, os baús e as tábuas que sobram |
| 4 | `inventario.py`, com `input` e a conversão | O programa pergunta quantos troncos tens e faz as contas com a resposta |
| 5 | Nada no código; o caderno | A tabela de entradas e saídas, com quatro casos, confirma o programa |

## Palavras que vais usar

- Variável: um nome que guarda um valor, para o programa o usar mais tarde, como `troncos = 7`. Para saber mais, vê a secção "Guardar valores em variáveis" do [guia](02-dados-e-interacao.md).
- Atribuição: a instrução com `=`, que guarda o valor da direita na variável da esquerda.
- Constante: uma variável com o nome em maiúsculas, como `TABUAS_POR_BAU`, que guarda uma regra que não muda.
- Tipo: a espécie de valor que se guarda. Neste laboratório usas três: `int`, para números inteiros, `float`, para números com parte decimal, e `str`, para textos.
- Operador: o sinal que diz que conta se faz, como o `+`, o `*` ou o `//`.
- Divisão inteira: a conta com `//`, que diz quantas vezes um número cabe noutro, sem partes decimais.
- Resto: a conta com `%`, que diz o que sobra da divisão inteira.
- `input`: a função que escreve uma pergunta, espera que a pessoa escreva e carregue em Enter, e devolve o que ela escreveu, sempre como texto.
- Função: um pedaço de programa que já vem com o Python, com um nome, que recebe valores entre parênteses. Umas devolvem um resultado, como o `int`; outras fazem uma coisa, como o `print`, que escreve no ecrã.
- Converter: transformar um valor de um tipo noutro, como o texto `"7"` no número 7, com a função `int`.
- Tabela de entradas e saídas: uma tabela com uma linha por caso de teste. Cada linha diz o que se escreve no teclado e o que deve aparecer.

## O que precisas

- A pasta `lp-python`, aberta no VS Code. Precisas também do comando que funciona no teu computador, `python`, `py` ou `python3`, que tens no registo da execução do caderno. Se não tiveres a pasta, cria-a, por exemplo em Documentos, e abre-a no VS Code, no menu File, com a opção Open Folder....
- O terminal do VS Code, no menu Terminal, com a opção New Terminal. O texto antes do cursor deve acabar em `lp-python`.
- O caderno, para as previsões e para a tabela de entradas e saídas.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou não ter os sinais por baixo da linha. O nome do erro, a palavra antes dos dois pontos na última linha, é o mesmo.

Neste laboratório, onde o texto diz `python`, usa o teu comando.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco. Guarda com Ctrl+S, ou Cmd+S no macOS, antes de cada vez que corres.
2. Estás na pasta certa? O texto antes do cursor, no terminal, tem de acabar em `lp-python`. Se não acabar, abre um terminal novo, no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.
4. O programa parou e não volta ao terminal? Está à espera que escrevas um valor, depois da pergunta. Escreve-o e carrega em Enter.
5. Copiaste o código à mão? Confirma os parênteses, as aspas e os nomes das variáveis, letra a letra: `troncos` e `Troncos` são nomes diferentes.

## Fase 1: Guardar valores em variáveis

Um jogo tem de se lembrar de quanto material tens. Para isso, o programa guarda cada quantidade numa variável: um nome com um valor. Em pseudocódigo escrevias `int troncos = 7`. Em Python, o tipo não se escreve: basta `troncos = 7`, e o Python percebe pelo valor que é um inteiro. Os nomes escrevem-se em minúsculas, e, quando têm várias palavras, com um traço baixo entre elas, como `total_tabuas`. Para saber mais, lê as secções "Guardar valores em variáveis" e "Os nomes das variáveis" do [guia](02-dados-e-interacao.md).

1. Cria o ficheiro `inventario.py`. No painel Explorer, passa o rato por cima de `LP-PYTHON` e carrega no ícone New File.... Escreve o nome `inventario.py` e carrega em Enter. Escreve nele este conteúdo, que é o ficheiro completo:

   ```python
   # inventario.py: a calculadora de material do inventário de um jogo de construção.
   troncos = 7
   pedra = 30
   ferro = 5
   print("Troncos:", troncos)
   print("Pedra:", pedra)
   print("Ferro:", ferro)
   ```

   Leitura guiada: depois do comentário, as três linhas seguintes criam três variáveis, cada uma com a quantidade de um material. O `=` guarda o valor da direita no nome da esquerda. Os três `print` escrevem cada um um texto e o valor de uma variável, separados por uma vírgula. O nome da variável está sem aspas, e por isso o `print` escreve o valor dela, e não o nome.

2. Antes de correres, prevê o que aparece. Depois guarda e corre:

   ```bash
   python inventario.py
   ```

   O que deves ver:

   ```text
   Troncos: 7
   Pedra: 30
   Ferro: 5
   ```

   Isto quer dizer que as três variáveis guardaram os valores e que o `print` os escreveu. Repara que há um espaço entre os dois pontos e o número, e que não o escreveste. O `print` põe sozinho um espaço entre os valores separados por vírgulas.

3. Experimenta o espaço. Na linha do `print` dos troncos, põe um espaço dentro das aspas, depois dos dois pontos: `print("Troncos: ", troncos)`. Antes de correres, prevê o que muda. Guarda e corre. O que deves ver na primeira linha: `Troncos:  7`, com dois espaços. O espaço das aspas e o do `print` somam-se. É ao contrário do pseudocódigo, em que os espaços iam dentro das aspas. Tira o espaço que puseste, guarda e corre outra vez.

4. Provoca um erro de propósito. Na linha do `print` dos troncos, escreve o nome com maiúscula: `print("Troncos:", Troncos)`. Antes de correres, prevê que tipo de erro vai ser. Guarda e corre. O que deves ver:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\inventario.py", line 5, in <module>
       print("Troncos:", Troncos)
                         ^^^^^^^
   NameError: name 'Troncos' is not defined. Did you mean: 'troncos'?
   ```

   É um erro de execução, um `NameError`. O programa não conhece nenhuma variável `Troncos`, com maiúscula, só `troncos`. O Python até sugere o nome certo, em "Did you mean", isto é, "querias dizer". O caminho do ficheiro, na linha com `File`, muda de computador para computador. Corrige, voltando a pôr o nome em minúsculas, guarda e corre.

### Paragem 1

O `inventario.py` mostra os três materiais, com os valores guardados em variáveis.

Pensa antes de continuares: porque é que `print("Troncos:", troncos)` escreve `Troncos: 7`, e não `Troncos: troncos`? A resposta: o primeiro valor está entre aspas, e é um texto, que aparece tal e qual. O segundo está sem aspas, e é o nome de uma variável: o `print` escreve o valor que ela guarda.

## Fase 2: Experimentar tipos e contas na consola

Antes de pôr contas no programa, vale a pena ver como o Python as faz. Cada valor tem um tipo, e o tipo muda o resultado das contas. Na consola do Python, experimentas uma linha de cada vez e vês logo o resultado, sem criar ficheiros. Para saber mais, lê as secções "Os tipos dos valores", "As contas: os operadores" e "A ordem das contas" do [guia](02-dados-e-interacao.md).

1. Entra na consola: no terminal, escreve só `python`, com o teu comando, e carrega em Enter. O que deves ver: duas linhas em inglês, a primeira com a versão do Python, e por baixo, numa linha à parte, `>>>`.

2. Prevê o tipo de cada valor, escreve as linhas e confirma:

   ```text
   >>> type(7)
   <class 'int'>
   >>> type(2.5)
   <class 'float'>
   >>> type("7")
   <class 'str'>
   ```

   O nome entre aspas simples, a seguir a `class`, é o tipo. `7` é um inteiro, um `int`. `2.5` tem parte decimal, e é um `float`; a parte decimal escreve-se com ponto, e não com vírgula. `"7"`, entre aspas, é um texto, um `str`. O número 7 e o texto `"7"` são valores diferentes.

3. Prevê o resultado de cada divisão, escreve e confirma:

   ```text
   >>> 28 / 8
   3.5
   >>> 28 // 8
   3
   >>> 28 % 8
   4
   >>> 8 / 2
   4.0
   ```

   O `/` é a divisão com parte decimal: 28 a dividir por 8 dá 3,5. O `//` é a divisão inteira: com 28 tábuas, fazes 3 baús completos de 8. O `%` é o resto da divisão inteira: sobram 4 tábuas. A última linha mostra que o `/` dá sempre um `float`, mesmo numa conta exata: `4.0`, e não `4`.

4. Prevê o resultado, escreve e confirma:

   ```text
   >>> 2 + 3 * 4
   14
   >>> (2 + 3) * 4
   20
   ```

   O Python segue a ordem das operações da matemática: a multiplicação faz-se antes da soma. Os parênteses passam à frente de tudo.

5. Agora a experiência mais importante. Prevê o resultado de cada linha antes de carregares em Enter:

   ```text
   >>> 7 * 4
   28
   >>> "7" * 4
   '7777'
   ```

   Com o número 7, o `*` multiplica. Com o texto `"7"`, o `*` repete o texto quatro vezes, e não aparece nenhuma mensagem de erro. Guarda esta experiência, porque vais voltar a ela na fase 4.

6. Sai da consola: escreve `exit()` e carrega em Enter.

### Paragem 2

Sabes dizer de que tipo é um valor e como o Python faz as divisões. Não ficou nenhum ficheiro novo na pasta.

Pensa antes de continuares: com 30 tábuas e baús de 8, quantos baús fazes e quantas tábuas sobram, e que contas do Python o dizem? A resposta: 3 baús, com `30 // 8`, e sobram 6 tábuas, com `30 % 8`. Confirma: 8 vezes 3, mais 6, dá 30.

## Fase 3: Constantes e contas no programa

Agora o programa faz as contas da madeira. Cada tronco dá 4 tábuas, e cada baú gasta 8. Estes números são regras do jogo, que não mudam. Se aparecessem soltos no meio das contas, quem lesse não saberia o que querem dizer. Por isso, ficam em constantes: variáveis com o nome todo em maiúsculas, que se combina não mudar. Para saber mais, lê a secção "Constantes" do [guia](02-dados-e-interacao.md).

1. Antes de mexeres no código, prevê no caderno, com 7 troncos: quantas tábuas, quantos baús e quantas tábuas sobram. A resposta: 7 vezes 4 dá 28 tábuas; 28 a dividir por 8 dá 3 baús completos; e sobram 4 tábuas.

2. Substitui todo o conteúdo de `inventario.py` por este, que é o ficheiro completo:

   ```python
   # inventario.py: a calculadora de material do inventário de um jogo de construção.
   # Diz quantas tábuas dão os troncos, e quantos baús se constroem com elas.

   # As regras do jogo, que não mudam enquanto o programa corre.
   TABUAS_POR_TRONCO = 4
   TABUAS_POR_BAU = 8

   troncos = 7
   pedra = 30
   ferro = 5
   print("Troncos:", troncos)
   print("Pedra:", pedra)
   print("Ferro:", ferro)

   tabuas = troncos * TABUAS_POR_TRONCO
   # O // dá os baús completos, e o % dá as tábuas que não chegam para mais um.
   baus = tabuas // TABUAS_POR_BAU
   sobram = tabuas % TABUAS_POR_BAU
   print("Tábuas:", tabuas)
   print("Baús que podes construir:", baus)
   print("Tábuas que sobram:", sobram)
   ```

   Leitura guiada: começa pelas duas constantes, logo a seguir aos comentários. São as regras do jogo, e ficam no início para se encontrarem depressa. A parte do inventário é a da fase 1. Depois vêm as contas, de cima para baixo. A variável `tabuas` nasce com o resultado da multiplicação. As duas linhas seguintes usam esse resultado: `baus` guarda a divisão inteira, e `sobram` guarda o resto. Os três `print` do fim mostram os resultados. As linhas em branco não fazem nada: separam as partes, para se lerem melhor.

3. Guarda e corre. O que deves ver:

   ```text
   Troncos: 7
   Pedra: 30
   Ferro: 5
   Tábuas: 28
   Baús que podes construir: 3
   Tábuas que sobram: 4
   ```

   Compara com a tua previsão do passo 1. Se for igual, as contas estão certas.

4. Provoca um erro de lógica. Na linha dos baús, troca o `//` por `/`: `baus = tabuas / TABUAS_POR_BAU`. Antes de correres, prevê o que muda. Guarda e corre. O que deves ver na linha dos baús: `Baús que podes construir: 3.5`. Não há mensagem nenhuma, mas meio baú não existe. O `/` dá a divisão com parte decimal, e aqui o que interessa são os baús completos. Volta a pôr `//`, guarda e corre outra vez.

### Paragem 3

O programa calcula as tábuas, os baús e as tábuas que sobram, e dá o resultado da tua previsão.

Pensa antes de continuares: se o jogo mudar e cada baú passar a gastar 6 tábuas, o que mudas no programa? A resposta: só a linha da constante, `TABUAS_POR_BAU = 6`. As contas usam o nome, e ficam certas sem mais nenhuma mudança. Com 7 troncos, passam a dar 4 baús e 4 tábuas a sobrar.

## Fase 4: Ler do teclado e converter

Até aqui, o programa tinha sempre 7 troncos. Um programa útil pergunta. Em pseudocódigo era o `ler valor`; em Python, é o `input`. O `input` escreve a pergunta, espera que a pessoa escreva e carregue em Enter, e devolve o que ela escreveu. Mas devolve sempre um texto, mesmo que a pessoa escreva um número. Nesta fase vais ver o que acontece quando te esqueces disso, e como se resolve. Para saber mais, lê as secções "Ler do teclado com `input`" e "Converter um texto num número" do [guia](02-dados-e-interacao.md).

1. Em `inventario.py`, substitui a linha `troncos = 7` por esta:

   ```python
   troncos = input("Quantos troncos tens? ")
   ```

   Leitura guiada: o `input` escreve a pergunta que está entre parênteses e espera. O que a pessoa escrever fica em `troncos`. A pergunta acaba num espaço, dentro das aspas, para a resposta não ficar colada ao ponto de interrogação.

2. Antes de correres, lembra-te da fase 2 e prevê o que aparece se escreveres 7. Guarda e corre. Quando aparecer a pergunta, escreve `7` e carrega em Enter. O que deves ver:

   ```text
   Quantos troncos tens? 7
   Troncos: 7
   Pedra: 30
   Ferro: 5
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\inventario.py", line 17, in <module>
       baus = tabuas // TABUAS_POR_BAU
              ~~~~~~~^^~~~~~~~~~~~~~~~
   TypeError: unsupported operand type(s) for //: 'str' and 'int'
   ```

   O inventário apareceu, e o programa parou na linha 17, a dos baús. O nome do erro é `TypeError`, um erro de tipo. A mensagem quer dizer "tipos que não servem para o `//`: um texto e um inteiro". Os sinais `~` e `^` marcam as duas partes da conta e o operador.

   O que aconteceu foi isto. O `input` devolveu o texto `"7"`, e não o número 7. Na linha das tábuas, `"7" * 4` não deu erro: repetiu o texto, como na fase 2, e `tabuas` ficou com o texto `"7777"`. O erro só apareceu na linha dos baús, porque não se faz a divisão inteira de um texto.

   Repara onde a mensagem aponta: para a linha dos baús, mas a causa está na linha da leitura, nove linhas acima. A linha apontada é onde o Python deu pelo problema, e não onde ele nasceu.

3. Corrige a causa. Substitui a linha da leitura por estas duas, o comentário e a leitura com a conversão:

   ```python
   # O input devolve sempre um texto; o int converte-o num número, para as contas.
   troncos = int(input("Quantos troncos tens? "))
   ```

   Leitura guiada: a segunda linha lê-se de dentro para fora. Primeiro o `input` escreve a pergunta e devolve o texto. Depois o `int` converte esse texto num número inteiro. Só então o número é guardado em `troncos`. O comentário diz porque é que o `int` está lá, para quem ler o programa mais tarde.

4. Guarda, corre e escreve `7`. O que deves ver: o ecrã de "O que vais construir", com 28 tábuas, 3 baús e 4 tábuas a sobrar.

5. Provoca outro erro de propósito. Corre outra vez e, na pergunta, escreve `sete`. O que deves ver:

   ```text
   Quantos troncos tens? sete
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\inventario.py", line 9, in <module>
       troncos = int(input("Quantos troncos tens? "))
   ValueError: invalid literal for int() with base 10: 'sete'
   ```

   É um erro de execução, um `ValueError`, um erro de valor. A mensagem quer dizer "valor inválido para o `int()` na base 10: 'sete'". A base 10 é a forma normal de escrever números, com os algarismos de 0 a 9. O `int` só converte textos que são números inteiros escritos com algarismos. Aqui, o programa não está errado: pede um número de troncos, e quem o usou não escreveu um número. Por agora, os programas partem do princípio de que a pessoa escreve o que lhe pedem.

### Paragem 4

O programa pergunta quantos troncos tens, converte a resposta num número e faz as contas com ela. O ficheiro `inventario.py` completo, como deve estar agora:

```python
# inventario.py: a calculadora de material do inventário de um jogo de construção.
# Diz quantas tábuas dão os troncos, e quantos baús se constroem com elas.

# As regras do jogo, que não mudam enquanto o programa corre.
TABUAS_POR_TRONCO = 4
TABUAS_POR_BAU = 8

# O input devolve sempre um texto; o int converte-o num número, para as contas.
troncos = int(input("Quantos troncos tens? "))
pedra = 30
ferro = 5
print("Troncos:", troncos)
print("Pedra:", pedra)
print("Ferro:", ferro)

tabuas = troncos * TABUAS_POR_TRONCO
# O // dá os baús completos, e o % dá as tábuas que não chegam para mais um.
baus = tabuas // TABUAS_POR_BAU
sobram = tabuas % TABUAS_POR_BAU
print("Tábuas:", tabuas)
print("Baús que podes construir:", baus)
print("Tábuas que sobram:", sobram)
```

Pensa antes de continuares: porque é que a mensagem do passo 2 apontava a linha dos baús, se o erro estava na leitura? A resposta: na linha das tábuas, `"7" * 4` não dá erro, porque repete o texto. O Python só deu pelo problema quando tentou fazer o `//` com um texto. O valor errado nasceu antes, na leitura sem `int`.

## Fase 5: Testar com uma tabela de entradas e saídas

Um caso só não chega para confiar num programa. Pode dar certo com 7 troncos e errado com 0 ou com 2. Testar é escolher casos que experimentam situações diferentes e comparar o resultado com o esperado, escrito antes de correr. A forma de o organizar é uma tabela de entradas e saídas. Tem uma linha por caso, com o que se escreve no teclado e o que deve aparecer. Para saber mais, vê o exemplo guiado do [guia](02-dados-e-interacao.md).

1. No caderno, faz uma tabela com quatro colunas: "Troncos", "Tábuas", "Baús" e "Sobram". Escreve quatro linhas, com 0, 1, 2 e 7 troncos, e preenche as outras colunas à mão, antes de correres.

   A resposta:

   | Troncos | Tábuas | Baús | Sobram |
   | ---: | ---: | ---: | ---: |
   | 0 | 0 | 0 | 0 |
   | 1 | 4 | 0 | 4 |
   | 2 | 8 | 1 | 0 |
   | 7 | 28 | 3 | 4 |

   Cada caso tem uma razão. O 0 é o mínimo. O 1 dá menos tábuas do que um baú gasta. O 2 dá exatamente um baú, sem sobras: é a fronteira, onde é fácil enganar-se no resto. O 7 é um caso normal, com baús e sobras.

2. Corre o programa quatro vezes, uma por linha da tabela. Em cada uma, compara as três últimas linhas do ecrã com a tua tabela. Com 2 troncos, por exemplo, deves ver:

   ```text
   Quantos troncos tens? 2
   Troncos: 2
   Pedra: 30
   Ferro: 5
   Tábuas: 8
   Baús que podes construir: 1
   Tábuas que sobram: 0
   ```

3. Acrescenta à tabela uma quinta coluna, "Passou?", e marca cada caso. Se algum não passar, depura com método. Escreve o esperado e o obtido, faz uma hipótese, confirma-a no código e corrige só a causa. Depois corre outra vez os quatro casos, e não só o que falhou.

### Paragem 5

A tabela de entradas e saídas tem os quatro casos, todos marcados como passados. O `inventario.py` está comentado e funciona com qualquer número inteiro de troncos, igual ou maior do que zero.

Pensa antes de terminares: porque é que o caso de 2 troncos é importante, se o de 7 já tinha baús e sobras? A resposta: com 2 troncos, as tábuas chegam exatamente para um baú, e o resto é 0. É a fronteira, o ponto onde o resultado muda. Um erro de uma unidade a mais ou a menos pode passar nos outros casos, e mostra-se aqui.

## Problemas frequentes

### `TypeError` numa linha de contas, depois de um `input`

Falta o `int` à volta do `input`. O `input` devolve sempre um texto, e um texto não serve para contas. Põe a leitura na forma `troncos = int(input("Quantos troncos tens? "))`.

### Aparece `7777` em vez de `28`

Acontece quando o `print` das tábuas vem logo a seguir à multiplicação, antes de outra conta. É o mesmo problema, mais escondido: falta o `int`, e o `*` repetiu o texto em vez de multiplicar. Corrige a linha da leitura.

### `ValueError: invalid literal for int() with base 10`

Escreveste no teclado uma coisa que o `int` não converte, como `sete`. O `int` só converte números inteiros escritos com algarismos. Corre outra vez e escreve um número inteiro.

### `NameError: name '...' is not defined`

O Python não conhece um nome que escreveste. Confirma que o nome está escrito igual em todas as linhas, com as mesmas minúsculas e o mesmo traço baixo. Confirma também que a linha que dá valor à variável vem antes da linha que a usa.

### Dois espaços seguidos no ecrã

Puseste um espaço dentro das aspas, junto a uma vírgula do `print`. O `print` já põe um espaço entre os valores. Tira o espaço das aspas.

### O baú aparece com parte decimal, como `3.5`

Usaste `/` em vez de `//`. Para contar objetos completos, usa a divisão inteira, `//`.

## Desafios

1. A pedra. Num jogo de construção, cada fornalha gasta 7 pedras. Acrescenta ao programa as contas da pedra: quantas fornalhas podes construir com a pedra que tens, e quantas pedras sobram. Escreve primeiro o resultado esperado, com 30 pedras. Pista: precisas de uma constante nova.

2. Tudo perguntado. Muda o programa para perguntar também quanta pedra e quanto ferro tens, em vez de os ter fixos. Testa com uma tabela de entradas e saídas com três casos.

3. O que falta para o próximo baú. Faz o programa dizer também quantas tábuas faltam para construir mais um baú. Com 7 troncos, sobram 4 tábuas, e faltam 4. Testa com os quatro casos da tabela. Pista: pensa no caso de 2 troncos, em que não sobra nenhuma tábua. Quantas faltam aí?

## Antes de terminares

- [ ] O `inventario.py` pergunta quantos troncos tens e mostra o inventário, as tábuas, os baús e as tábuas que sobram.
- [ ] A tabela de entradas e saídas, no caderno, tem os quatro casos, preenchidos antes de correr e marcados depois.
- [ ] Sabes dizer de que tipo é `7`, `2.5` e `"7"`.
- [ ] Sabes dizer o que fazem o `/`, o `//` e o `%`.
- [ ] Consegues explicar, por palavras tuas, porque é que o `input` precisa do `int` antes de fazeres contas com o que a pessoa escreveu.

![Rodapé](../imagens/rodape.png)
