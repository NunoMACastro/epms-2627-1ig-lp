![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Dados e interação

## O que vais construir

Vais construir o `inventario.py`, a calculadora de material de um jogo de construção, em que cada tronco dá 4 tábuas e cada baú gasta 8. O programa pergunta quantos troncos tens e diz quantas tábuas dão, quantos baús constróis e quantas tábuas sobram. Com 7 troncos, o ecrã fica assim:

```text
Quantos troncos tens? 7
Troncos: 7
Pedra: 30
Ferro: 5
Tábuas: 28
Baús que podes construir: 3
Tábuas que sobram: 4
```

1. [Fase 1: Guardar valores em variáveis](#fase-1-guardar-valores-em-variáveis)
2. [Fase 2: Os tipos dos valores e as contas](#fase-2-os-tipos-dos-valores-e-as-contas)
3. [Fase 3: Constantes](#fase-3-constantes)
4. [Fase 4: Ler do teclado e converter](#fase-4-ler-do-teclado-e-converter)
5. [Fase 5: Testar com uma tabela de entradas e saídas](#fase-5-testar-com-uma-tabela-de-entradas-e-saídas)

## O que precisas

- A pasta `lp-python`, aberta no VS Code. Se não a tiveres, cria-a em Documentos e abre-a com a opção `Open Folder...` do menu File.
- O terminal do VS Code, no menu Terminal, com a opção New Terminal. O caminho antes do `>` ou do `%` deve acabar em `lp-python`.
- O comando que funcionou no teu computador no tema anterior, `python`, `py` ou `python3`. Neste laboratório, onde o texto diz `python`, usa o teu.

## Fase 1: Guardar valores em variáveis

O programa guarda o material em variáveis e escreve-o no ecrã. Cada quantidade fica numa variável, com um nome e um valor. Rever: [Guardar valores em variáveis](../02-dados-e-interacao.md#guardar-valores-em-variáveis).

1. Cria o ficheiro onde o programa vai ficar. No painel Explorer, passa o rato por cima de `LP-PYTHON` e carrega no ícone `New File...`. Escreve o nome `inventario.py` e carrega em Enter. Escreve nele esta primeira versão:

   ```python
   # inventario.py: a calculadora de material do inventário de um jogo de construção.
   troncos = 7
   print("Troncos:", troncos)
   ```

2. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre o programa no terminal:

   ```bash
   python inventario.py
   ```

   O que deves ver: `Troncos: 7`. Isto quer dizer que a variável guardou o valor e que o `print` o escreveu. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

3. Acrescenta os outros dois materiais. Em `inventario.py`, a seguir a `troncos = 7`, acrescenta:

   ```python
   pedra = 30
   ferro = 5
   ```

   No fim do ficheiro, acrescenta:

   ```python
   print("Pedra:", pedra)
   print("Ferro:", ferro)
   ```

   Guarda e corre. O que deves ver:

   ```text
   Troncos: 7
   Pedra: 30
   Ferro: 5
   ```

4. Experimenta o espaço do `print`. Na linha do `print` dos troncos, põe um espaço dentro das aspas, depois dos dois pontos: `print("Troncos: ", troncos)`. Guarda e corre. O que deves ver na primeira linha: `Troncos:  7`, com dois espaços, porque o espaço das aspas e o do `print` se somam. Tira o espaço que puseste, guarda e corre outra vez.

5. Provoca um erro de propósito, para o reconheceres quando te acontecer. Na linha do `print` dos troncos, escreve o nome com maiúscula: `print("Troncos:", Troncos)`. Guarda e corre. O que deves ver:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\inventario.py", line 5, in <module>
       print("Troncos:", Troncos)
                         ^^^^^^^
   NameError: name 'Troncos' is not defined. Did you mean: 'troncos'?
   ```

   É um erro de execução. O programa só conhece `troncos`, em minúsculas, e até sugere esse nome, em "Did you mean", isto é, "querias dizer". Volta a pôr o nome em minúsculas, guarda e corre.

### Paragem 1

O `inventario.py` mostra os três materiais, com os valores guardados em variáveis.

Pensa antes de continuares: porque é que `print("Troncos:", troncos)` escreve `Troncos: 7`, e não `Troncos: troncos`? A resposta: o primeiro valor está entre aspas, e é um texto, que aparece tal e qual. O segundo está sem aspas, e é o nome de uma variável, por isso o `print` escreve o valor dela.

## Fase 2: Os tipos dos valores e as contas

Experimentas na consola do Python, sem criar ficheiros. Cada valor tem um tipo, e o tipo muda o resultado das contas. Rever: [Os tipos dos valores e as contas](../02-dados-e-interacao.md#os-tipos-dos-valores-e-as-contas).

1. Entra na consola, onde experimentas uma linha de cada vez. No terminal, escreve só o teu comando, sem nome de ficheiro, e carrega em Enter. O que deves ver: a versão do Python e, numa linha à parte, `>>>`.

2. Confirma o tipo de três valores. Escreve cada linha a seguir ao `>>>`, sem o `>>>`, que é o Python que o põe. O que deves ver:

   ```text
   >>> type(7)
   <class 'int'>
   >>> type(2.5)
   <class 'float'>
   >>> type("7")
   <class 'str'>
   ```

   O nome entre aspas simples é o tipo.

3. Compara estas contas, uma linha de cada vez. O que deves ver:

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

   Com 28 tábuas, fazes 3 baús completos de 8, e sobram 4. A última linha mostra que o `/` dá sempre um `float`, mesmo numa conta exata.

4. Confirma a ordem das contas. O que deves ver:

   ```text
   >>> 2 + 3 * 4
   14
   >>> (2 + 3) * 4
   20
   ```

   A multiplicação faz-se antes da soma, e os parênteses passam à frente de tudo.

5. Compara um número com um texto. Prevê o resultado de cada linha antes de carregares em Enter:

   ```python
   7 * 4
   "7" * 4
   ```

   O que deves ver:

   ```text
   >>> 7 * 4
   28
   >>> "7" * 4
   '7777'
   ```

   Com o número, o `*` multiplica. Com o texto, repete-o quatro vezes, e não aparece nenhuma mensagem de erro.

6. Sai da consola: escreve `exit()` e carrega em Enter. O que deves ver: a linha do terminal outra vez, com `lp-python`.

### Paragem 2

Voltaste ao terminal, e não ficou nenhum ficheiro novo na pasta.

Pensa antes de continuares: com 30 tábuas e baús de 8, quantos baús fazes e quantas tábuas sobram, e que contas do Python o dizem? A resposta: 3 baús, com `30 // 8`, e sobram 6 tábuas, com `30 % 8`. Para confirmar, 8 vezes 3, mais 6, dá 30.

## Fase 3: Constantes

O programa passa a fazer as contas da madeira. O 4 e o 8 são regras do jogo, e por isso ficam em constantes, com o nome em maiúsculas. Rever: [Constantes](../02-dados-e-interacao.md#constantes).

1. Antes de mexeres no código, calcula de cabeça, com 7 troncos, quantas tábuas, quantos baús e quantas tábuas sobram. A resposta: 7 vezes 4 dá 28 tábuas, 28 a dividir por 8 dá 3 baús completos, e sobram 4 tábuas.

2. Acrescenta as regras do jogo e a primeira conta. Em `inventario.py`, a seguir à primeira linha, acrescenta:

   ```python
   # Diz quantas tábuas dão os troncos, e quantos baús se constroem com elas.

   # As regras do jogo, que não mudam enquanto o programa corre.
   TABUAS_POR_TRONCO = 4
   TABUAS_POR_BAU = 8
   ```

   Deixa uma linha em branco a seguir às constantes. No fim do ficheiro, acrescenta uma linha em branco e estas duas:

   ```python
   tabuas = troncos * TABUAS_POR_TRONCO
   print("Tábuas:", tabuas)
   ```

   Guarda e corre. O que deves ver, depois das três linhas do inventário: `Tábuas: 28`.

3. Acrescenta as contas dos baús. A seguir à linha `tabuas = troncos * TABUAS_POR_TRONCO`, acrescenta:

   ```python
   # O // dá os baús completos, e o % dá as tábuas que não chegam para mais um.
   baus = tabuas // TABUAS_POR_BAU
   sobram = tabuas % TABUAS_POR_BAU
   ```

   No fim do ficheiro, acrescenta:

   ```python
   print("Baús que podes construir:", baus)
   print("Tábuas que sobram:", sobram)
   ```

   Guarda e corre. O que deves ver:

   ```text
   Troncos: 7
   Pedra: 30
   Ferro: 5
   Tábuas: 28
   Baús que podes construir: 3
   Tábuas que sobram: 4
   ```

   Os números são os que calculaste no passo 1.

4. Provoca um erro de lógica. Na linha dos baús, troca o `//` por `/`: `baus = tabuas / TABUAS_POR_BAU`. Guarda e corre. O que deves ver na linha dos baús: `Baús que podes construir: 3.5`. Não há mensagem nenhuma, mas meio baú não existe. Volta a pôr `//`, guarda e corre outra vez.

### Paragem 3

O programa calcula as tábuas, os baús e as tábuas que sobram. O ficheiro `inventario.py` completo, como deve estar agora:

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

As constantes ficam no início, o inventário a seguir, e as contas e os resultados no fim. As contas dos baús usam o resultado da conta das tábuas.

Pensa antes de continuares: se cada baú passar a gastar 6 tábuas, o que mudas no programa? A resposta: só a linha `TABUAS_POR_BAU = 6`. Com 7 troncos, passam a dar 4 baús e 4 tábuas a sobrar.

## Fase 4: Ler do teclado e converter

O programa passa a perguntar quantos troncos tens. Vais ver o que acontece quando não convertes a resposta num número. Rever: [Ler do teclado e converter](../02-dados-e-interacao.md#ler-do-teclado-e-converter).

1. Em `inventario.py`, substitui a linha `troncos = 7` por esta:

   ```python
   troncos = input("Quantos troncos tens? ")
   ```

2. Lembra-te da fase 2 e prevê o que acontece se escreveres 7. Guarda e corre. Quando aparecer a pergunta, escreve `7` e carrega em Enter. O que deves ver:

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

   É um erro de execução, um erro de tipo. A mensagem quer dizer "tipos que não servem para o `//`: um texto e um inteiro". O `input` devolveu o texto `"7"`. Na linha das tábuas, `"7" * 4` não deu erro: repetiu o texto, e `tabuas` ficou com `"7777"`. O erro só apareceu na linha dos baús, mas a causa está na linha da leitura. A linha apontada é onde o Python deu pelo problema, e não onde ele nasceu.

3. Corrige a causa. Substitui a linha da leitura por estas duas:

   ```python
   # O input devolve sempre um texto; o int converte-o num número, para as contas.
   troncos = int(input("Quantos troncos tens? "))
   ```

4. Guarda, corre e escreve `7`. O que deves ver: as sete linhas de [O que vais construir](#o-que-vais-construir), com 28 tábuas, 3 baús e 4 tábuas a sobrar.

5. Provoca outro erro de propósito. Corre outra vez e, na pergunta, escreve `sete`. O que deves ver:

   ```text
   Quantos troncos tens? sete
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\inventario.py", line 9, in <module>
       troncos = int(input("Quantos troncos tens? "))
   ValueError: invalid literal for int() with base 10: 'sete'
   ```

   É um erro de execução, um erro de valor: o `int` só converte textos que são números inteiros, escritos com algarismos. Aqui, o programa não está errado: pede um número de troncos, e quem o usou não escreveu um número.

### Paragem 4

O programa pergunta quantos troncos tens, converte a resposta num número e faz as contas com ela. Em relação à paragem 3, só mudou a leitura.

Pensa antes de continuares: sem o `int`, com 3 troncos, que valor ficava em `tabuas`? A resposta: o texto `"3333"`, porque o `*` repete o texto `"3"` quatro vezes.

## Fase 5: Testar com uma tabela de entradas e saídas

Corres o programa com quatro casos e comparas o resultado com o que calculaste antes. Um caso só não chega para confiar num programa. Rever: [Testar com uma tabela de entradas e saídas](../02-dados-e-interacao.md#testar-com-uma-tabela-de-entradas-e-saídas).

1. Os casos de teste são 0, 1, 2 e 7 troncos. Antes de correres, calcula o que o programa deve mostrar em cada caso. A resposta:

   | Troncos | Tábuas | Baús | Sobram |
   | ---: | ---: | ---: | ---: |
   | 0 | 0 | 0 | 0 |
   | 1 | 4 | 0 | 4 |
   | 2 | 8 | 1 | 0 |
   | 7 | 28 | 3 | 4 |

   Cada caso tem uma razão. O 0 é o mínimo. O 1 dá menos tábuas do que um baú gasta. O 7 é um caso normal, com baús e sobras.

2. Corre o programa quatro vezes, uma por linha da tabela, e compara as três últimas linhas do ecrã com o que calculaste. Com 2 troncos, deves ver:

   ```text
   Quantos troncos tens? 2
   Troncos: 2
   Pedra: 30
   Ferro: 5
   Tábuas: 8
   Baús que podes construir: 1
   Tábuas que sobram: 0
   ```

3. Se algum caso não der o que calculaste, depura com método. Num comentário no fim do `inventario.py`, escreve o caso, o esperado, o obtido e a tua hipótese. Corrige só a causa e corre outra vez os quatro casos, e não só o que falhou.

### Paragem 5

Os quatro casos da tabela passaram.

Pensa antes de terminares: porque é que o caso de 2 troncos é importante, se o de 7 já tinha baús e sobras? A resposta: com 2 troncos, as tábuas chegam exatamente para um baú, e o resto é 0. É um caso de fronteira, em cima do limite de um baú.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco.
2. Estás na pasta certa? O texto antes do cursor tem de acabar em `lp-python`. Se não acabar, abre um terminal novo.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.
4. O programa parou e não volta ao terminal? Está à espera que escrevas um valor, depois da pergunta.
5. A mensagem é diferente da deste laboratório? As mensagens aqui são as do Python 3.14. Noutra versão, as palavras podem mudar, mas o nome do erro antes dos dois pontos é o mesmo. O caminho do ficheiro, na linha com `File`, é outro em cada computador.

### `TypeError` numa linha de contas, depois de um `input`

Falta o `int` à volta do `input`, e um texto não serve para contas. Põe a leitura na forma `troncos = int(input("Quantos troncos tens? "))`.

### `NameError: name '...' is not defined`

O Python não conhece um nome que escreveste. Confirma que está escrito igual em todas as linhas, e que a linha que dá valor à variável vem antes da que a usa.

### Dois espaços seguidos, ou um baú com parte decimal

Ficou por corrigir um dos erros que provocaste. Ou há um espaço dentro das aspas, junto a uma vírgula, ou há um `/` no lugar do `//`.

## Desafios

1. A pedra. Cada fornalha gasta 7 pedras. Acrescenta ao programa as contas da pedra: quantas fornalhas podes construir e quantas pedras sobram. Pista: precisas de uma constante nova.

2. Tudo perguntado. Muda o programa para perguntar também quanta pedra e quanto ferro tens, em vez de os ter fixos. Testa-o com três casos à tua escolha, com o resultado esperado de cada um calculado antes de correres.

3. O que falta para o próximo baú. Faz o programa dizer também quantas tábuas faltam para construir mais um baú. Com 7 troncos, sobram 4 tábuas, e faltam 4. Testa-o com os quatro casos da fase 5. Pista: pensa no caso de 2 troncos, em que não sobra nenhuma tábua. Quantas faltam aí?

## Antes de terminares

- [ ] O `inventario.py` pergunta quantos troncos tens e mostra o inventário, as tábuas, os baús e as tábuas que sobram.
- [ ] O `inventario.py` tem o `int` à volta do `input`, e as regras do jogo em constantes.
- [ ] Correste os quatro casos da fase 5, e cada um deu o que calculaste antes de correr.

![Rodapé](../../imagens/rodape.png)
