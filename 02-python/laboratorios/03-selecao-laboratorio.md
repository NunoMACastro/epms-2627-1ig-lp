![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Seleção

Laboratório do tema Seleção, do módulo Desenvolver programas em linguagem estruturada. Vais construir a bancada de construção do inventário de um jogo. O jogador pede baús, e o programa aceita ou recusa o pedido pelas tábuas que há em stock e pelos limites da bancada. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](../03-selecao.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

No fim, tens o programa `bancada.py`, na tua pasta `lp-python`. O inventário tem 24 tábuas, e cada baú gasta 8. A bancada constrói de 1 a 5 baús de cada vez. Quando o corres, o programa pergunta quantos baús queres construir e dá uma de três respostas. Se o pedido estiver fora dos limites, é inválido. Se as tábuas chegarem, é aceite, e as tábuas descontam-se. Se não chegarem, é recusado, e o programa diz quantas faltam. Com 3 baús, por exemplo, o ecrã fica assim:

```text
Quantos baús queres construir (1 a 5)? 3
Pedido aceite. Baús construídos: 3
Tábuas no inventário: 0
```

E com 4 baús:

```text
Quantos baús queres construir (1 a 5)? 4
Pedido recusado. Faltam 8 tábuas.
Tábuas no inventário: 24
```

Pelo caminho, ficas a saber escrever comparações, decidir com `if`, `else` e `elif`, e validar um valor antes de o usar. No fim, testas o programa com uma tabela de entradas e saídas, com casos que fazem correr cada ramo e experimentam cada limite.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | Nada no disco; experimentas na consola do Python | Sabes que uma comparação dá `True` ou `False` |
| 2 | `bancada.py`, com um `if` | O pedido que cabe no stock é aceite, e as tábuas descontam-se |
| 3 | `bancada.py`, com o `else` | O pedido que não cabe é recusado, com as tábuas que faltam |
| 4 | `bancada.py`, com o `elif` e a validação | Um pedido de menos de 1 baú é inválido, e já não dá tábuas de graça |
| 5 | `bancada.py`, com o limite da bancada e o `or` | Um pedido de mais de 5 baús também é inválido |
| 6 | Nada no código; corres o programa com sete casos de teste | Cada ramo e cada fronteira estão confirmados |

## Palavras que vais usar

- Comparação: uma pergunta de sim ou não entre dois valores, como `precisas <= tabuas`. Dá `True` ou `False`. Para saber mais, vê a secção "As comparações dão `True` ou `False`" do [guia](../03-selecao.md).
- `True` e `False`: os dois valores do tipo `bool`, verdadeiro e falso, escritos com maiúscula.
- Condição: a comparação, ou a junção de comparações, de que depende uma decisão.
- Bloco: um conjunto de instruções com a mesma indentação, que correm juntas, como as que estão por baixo de um `if`.
- Indentação: os quatro espaços no início de uma linha, que a põem dentro de um bloco. Em Python, é obrigatória.
- `if`, `else` e `elif`: as palavras do Python para o `Se`, o `Senão` e o `Senão se` do pseudocódigo.
- Ramo: cada um dos caminhos que uma decisão pode seguir. Cada ramo tem o seu bloco.
- Validar: confirmar que um valor serve, antes de o usar.
- `or`: a palavra do Python para o `ou` do pseudocódigo. Dá `True` quando pelo menos uma das partes dá `True`.
- `and`: a palavra do Python para o `e` do pseudocódigo. Só dá `True` quando as duas partes dão `True`.
- Limite: o valor de uma regra, como os 5 baús que a bancada constrói no máximo.
- Fronteira: o sítio, junto de um limite, onde a resposta de uma decisão muda, como entre o 3 e o 4.
- Ramo inacessível: um ramo que nenhum valor consegue fazer correr.
- Caso de teste: uma entrada escolhida para testar o programa, com o resultado esperado calculado antes de correr.
- Tabela de entradas e saídas: uma tabela com uma linha por caso de teste. Cada linha diz o que se escreve no teclado e o que deve aparecer.

## O que precisas

- A pasta `lp-python`, aberta no VS Code. Precisas também do comando que funcionou no teu computador: `python`, `py` ou `python3`. Se não tiveres a pasta, cria-a, por exemplo em Documentos, e abre-a no VS Code, no menu File, com a opção Open Folder....
- O terminal do VS Code, no menu Terminal, com a opção New Terminal. O texto antes do cursor deve acabar em `lp-python`.

Este laboratório começa um programa novo. Não precisas do `inventario.py` do laboratório anterior.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou não ter os sinais por baixo da linha. O nome do erro, a palavra antes dos dois pontos na última linha, é o mesmo.

Neste laboratório, onde o texto diz `python`, usa o teu comando.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco. Guarda com Ctrl+S, ou Cmd+S no macOS, antes de cada vez que corres.
2. Estás na pasta certa? O texto antes do cursor, no terminal, tem de acabar em `lp-python`. Se não acabar, abre um terminal novo, no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.
4. O programa parou e não volta ao terminal? Está à espera que escrevas um valor, depois da pergunta. Escreve-o e carrega em Enter.
5. Copiaste o código à mão? Confirma os dois pontos no fim de cada `if`, `elif` e `else`, e os quatro espaços no início de cada linha de um bloco.

## Fase 1: Experimentar comparações na consola

Uma decisão começa numa pergunta de sim ou não, como "as tábuas chegam?". Num programa, essa pergunta é uma comparação. Os seis operadores de comparação do Python são os do pseudocódigo: `==`, `!=`, `<`, `<=`, `>` e `>=`. O resultado é que muda de forma: em vez de `true` e `false`, o Python escreve `True` e `False`, com maiúscula. Na consola vês o resultado de cada comparação logo a seguir. Para saber mais, lê a secção "As comparações dão `True` ou `False`" do [guia](../03-selecao.md).

1. Entra na consola: no terminal, escreve só `python`, com o teu comando, e carrega em Enter. O que deves ver: duas linhas em inglês, com a versão do Python, e por baixo `>>>`.

2. Guarda um valor e faz duas perguntas. Prevê o que aparece depois de cada linha, escreve-as uma a uma e confirma:

   ```text
   >>> tabuas = 24
   >>> tabuas >= 16
   True
   >>> tabuas >= 32
   False
   ```

   A primeira linha não mostra nada, porque é uma atribuição, com um só `=`: guarda o 24 e não responde. As outras duas são perguntas, e respondem. Com 24 tábuas, um pedido de 16 cabe, e um de 32 não cabe.

3. Compara o `=` com o `==`. Prevê, escreve e confirma:

   ```text
   >>> tabuas == 24
   True
   >>> tabuas != 24
   False
   >>> type(tabuas == 24)
   <class 'bool'>
   >>> tabuas
   24
   ```

   O `==` pergunta "é igual a?", e o `!=` pergunta "é diferente de?". O `type` mostra que a resposta é um `bool`. A última linha mostra que perguntar não muda nada: `tabuas` continua com 24. Só o `=` muda o valor de uma variável.

4. Compara textos. Prevê, escreve e confirma:

   ```text
   >>> "baú" == "baú"
   True
   >>> "Baú" == "baú"
   False
   ```

   Dois textos só são iguais se tiverem exatamente os mesmos caracteres. O `B` maiúsculo e o `b` minúsculo são caracteres diferentes.

5. Sai da consola: escreve `exit()` e carrega em Enter.

### Paragem 1

Sabes que uma comparação dá `True` ou `False`, e que o `==` pergunta sem mudar nada. Não ficou nenhum ficheiro novo na pasta.

Pensa antes de continuares: com `tabuas = 24`, o que dá `tabuas <= 24`, e o que dá `tabuas < 24`? A resposta: `True` e `False`. O 24 é menor ou igual a 24, mas não é menor do que 24. Os dois operadores só discordam no próprio 24, e é por isso que esse valor vai ser um caso de teste.

## Fase 2: Aceitar o pedido com `if`

Agora o programa decide. Um pedido de baús só é aceite se as tábuas do inventário chegarem para ele. Em pseudocódigo escrevias `Se precisas <= tabuas`, com o que depende da condição indentado por baixo. Em Python escreve-se `if precisas <= tabuas:`, com dois pontos no fim. As instruções que só correm quando a condição dá `True` ficam por baixo, quatro espaços para dentro: são o bloco do `if`. A primeira linha que volta à margem já está fora do bloco, e corre sempre. Para saber mais, lê a secção "Decidir com `if`" do [guia](../03-selecao.md).

1. Cria o ficheiro `bancada.py`. No painel Explorer, passa o rato por cima de `LP-PYTHON` e carrega no ícone New File.... Escreve o nome `bancada.py` e carrega em Enter. Escreve nele este conteúdo, que é o ficheiro completo:

   ```python
   # bancada.py: a bancada de construção do inventário de um jogo de construção.
   # O jogador pede baús, e o programa aceita ou recusa o pedido.

   # A regra do jogo, que não muda enquanto o programa corre.
   TABUAS_POR_BAU = 8

   tabuas = 24
   baus = int(input("Quantos baús queres construir? "))
   precisas = baus * TABUAS_POR_BAU

   # O bloco do if só corre quando as tábuas chegam para o pedido.
   if precisas <= tabuas:
       tabuas = tabuas - precisas
       print("Pedido aceite. Baús construídos:", baus)
   print("Tábuas no inventário:", tabuas)
   ```

   Leitura guiada: começa pela constante, a regra do jogo, e pelas 24 tábuas do inventário. A leitura dos baús tem o `int`, porque o `input` devolve sempre um texto, e um texto não se compara com um número. A linha seguinte calcula as tábuas de que o pedido precisa. Depois vem a decisão. A linha do `if` faz a pergunta e acaba em dois pontos. As duas linhas de baixo estão quatro espaços para dentro: são o bloco, que desconta as tábuas e confirma o pedido. A última linha está encostada à margem, fora do bloco, e mostra o inventário em qualquer caso.

   Quando escreves os dois pontos e carregas em Enter, o VS Code começa a linha seguinte com quatro espaços. Na última linha, apaga esses espaços, para ela voltar à margem.

2. Antes de correres, prevê o que aparece com 2 baús e com 4 baús. Depois guarda e corre:

   ```bash
   python bancada.py
   ```

   Escreve `2` e carrega em Enter. O que deves ver:

   ```text
   Quantos baús queres construir? 2
   Pedido aceite. Baús construídos: 2
   Tábuas no inventário: 8
   ```

   Dois baús precisam de 16 tábuas, e `16 <= 24` dá `True`. O bloco correu: as tábuas passaram de 24 a 8, e apareceu a confirmação.

   Corre outra vez e escreve `4`. O que deves ver:

   ```text
   Quantos baús queres construir? 4
   Tábuas no inventário: 24
   ```

   Quatro baús precisam de 32 tábuas, e `32 <= 24` dá `False`. O bloco foi saltado, e só correu a última linha, que está fora dele. As tábuas ficaram como estavam. Por agora, o programa não diz que o pedido foi recusado. É o que vais acrescentar na fase 3.

   No terminal, a seta para cima do teclado volta a escrever o último comando. Para correres outra vez, carrega na seta e em Enter.

3. Provoca um erro de propósito. Na linha do `if`, apaga os dois pontos do fim, para ficar `if precisas <= tabuas`. Antes de correres, prevê que tipo de erro vai ser, e se a pergunta dos baús chega a aparecer. Guarda e corre. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\lp-python\bancada.py", line 12
       if precisas <= tabuas
                            ^
   SyntaxError: expected ':'
   ```

   É um erro de sintaxe: "esperava `:`". A pergunta dos baús não apareceu, porque o Python recusa o programa inteiro antes de correr qualquer linha. Os dois pontos anunciam que vem um bloco, e sem eles o `if` está mal escrito. Num Python mais antigo, a mensagem diz só `invalid syntax`. O caminho do ficheiro, na linha com `File`, muda de computador para computador. Volta a pôr os dois pontos e guarda.

4. Provoca um erro de lógica. Põe quatro espaços no início da última linha, a do inventário, para ela entrar no bloco do `if`. Antes de correres, prevê o que aparece com 4 baús. Guarda, corre e escreve `4`. O que deves ver: só a pergunta, `Quantos baús queres construir? 4`, e mais nada. A última linha passou para dentro do bloco, e o bloco foi saltado. Não há mensagem de erro: o programa fez o que estava escrito. Com 2 baús, o programa dava o mesmo de antes, e por isso só um caso em que a condição dá `False` mostra este erro. Tira os quatro espaços, para a linha voltar à margem, e guarda.

### Paragem 2

O `bancada.py` aceita um pedido que cabe no stock e desconta as tábuas. Com um pedido que não cabe, mostra só o inventário, sem mudar nada.

Pensa antes de continuares: com 3 baús, o pedido é aceite? A resposta: sim. Três baús precisam de 24 tábuas, e `24 <= 24` dá `True`. As tábuas passam a 0. Experimenta.

## Fase 3: Recusar o pedido com `else`

Um pedido que não cabe no stock tem de ter resposta. Em pseudocódigo era o `Senão`; em Python é o `else`, sem condição e com dois pontos. O `else` fica na mesma coluna do `if`, e o seu bloco fica quatro espaços para dentro. Corre sempre exatamente um dos dois blocos: o do `if`, quando a condição dá `True`, ou o do `else`, quando dá `False`. Para saber mais, lê a secção "Dois caminhos: `if` e `else`" do [guia](../03-selecao.md).

1. Em `bancada.py`, substitui as linhas da decisão, desde o comentário que está antes do `if` até ao fim do ficheiro, por estas:

   ```python
   # O pedido só é aceite quando as tábuas chegam.
   if precisas <= tabuas:
       tabuas = tabuas - precisas
       print("Pedido aceite. Baús construídos:", baus)
   else:
       # Esta conta só se faz quando o pedido é recusado.
       faltam = precisas - tabuas
       print("Pedido recusado. Faltam", faltam, "tábuas.")
   print("Tábuas no inventário:", tabuas)
   ```

   Leitura guiada: o bloco do `if` é o da fase 2. O `else` está encostado à margem, na coluna do `if`, e por isso pertence à mesma decisão. O seu bloco calcula quantas tábuas faltam e diz que o pedido foi recusado. A variável `faltam` só nasce neste bloco, porque só faz sentido quando o pedido é recusado. A última linha continua fora dos dois blocos.

2. Antes de correres, prevê o que aparece com 4 baús. Guarda, corre e escreve `4`. O que deves ver:

   ```text
   Quantos baús queres construir? 4
   Pedido recusado. Faltam 8 tábuas.
   Tábuas no inventário: 24
   ```

   Quatro baús precisam de 32 tábuas, e há 24: faltam 8. A condição deu `False`, e correu o bloco do `else`. As tábuas não mudaram, porque o desconto está no bloco do `if`.

3. Experimenta a fronteira. Corre com `3`. O que deves ver: `Pedido aceite. Baús construídos: 3` e `Tábuas no inventário: 0`. O 3 é o pedido maior que ainda cabe, e o 4 é o primeiro que já não cabe. É entre o 3 e o 4 que a resposta muda.

4. Provoca um erro na fronteira. Na linha do `if`, troca o `<=` por `<`, para ficar `if precisas < tabuas:`. Antes de correres, prevê o que aparece com 3 baús. Guarda, corre e escreve `3`. O que deves ver:

   ```text
   Quantos baús queres construir? 3
   Pedido recusado. Faltam 0 tábuas.
   Tábuas no inventário: 24
   ```

   O programa recusou um pedido para o qual as tábuas chegavam exatamente, e diz que faltam 0. É um erro de lógica, sem mensagem: `24 < 24` dá `False`. Com 2 ou com 4 baús, o `<` e o `<=` dão a mesma resposta, e o erro não se nota. Só o caso da própria fronteira o mostra. Volta a pôr `<=` e guarda.

### Paragem 3

O programa aceita os pedidos que cabem no stock e recusa os outros, com as tábuas que faltam.

Pensa antes de continuares: corre o programa com `0` e depois com `-2`. O que aparece, e faz sentido? A resposta: com 0, aparece `Pedido aceite. Baús construídos: 0`. Com -2, o pedido também é aceite, e o inventário passa a ter 40 tábuas. Menos dois baús precisam de menos 16 tábuas, e descontar menos 16 é somar 16. O programa está a dar tábuas de graça. É o problema da fase 4.

## Fase 4: Validar primeiro, com `elif`

Um pedido de 0 baús, ou de menos dois, não faz sentido. Não é para aceitar nem para recusar: é inválido, e o programa nem devia fazer contas com ele. Validar é confirmar que um valor serve, antes de o usar, e na algoritmia a validação vinha sempre em primeiro lugar. Agora a decisão tem três ramos: inválido, aceite e recusado. Em pseudocódigo era uma cadeia com `Senão se`. Em Python, o `Senão se` escreve-se `elif`, uma palavra só, com condição e dois pontos. Na cadeia, as condições avaliam-se de cima para baixo, e a primeira que dá `True` ganha. Para saber mais, lê a secção "Mais de dois caminhos: a cadeia com `elif`" do [guia](../03-selecao.md).

1. Em `bancada.py`, substitui as linhas da decisão, desde o comentário que está antes do `if` até ao fim do ficheiro, por estas:

   ```python
   # A validação vem primeiro: um pedido sem baús não se aceita nem se recusa.
   if baus < 1:
       print("Pedido inválido: pede pelo menos 1 baú.")
   elif precisas <= tabuas:
       tabuas = tabuas - precisas
       print("Pedido aceite. Baús construídos:", baus)
   else:
       # Esta conta só se faz quando o pedido é recusado.
       faltam = precisas - tabuas
       print("Pedido recusado. Faltam", faltam, "tábuas.")
   print("Tábuas no inventário:", tabuas)
   ```

   Leitura guiada: a primeira pergunta da cadeia é a da validação. Se o pedido tiver menos de 1 baú, o programa avisa e salta o resto da cadeia. A pergunta das tábuas passou para o `elif`, e só se faz para os pedidos válidos. O `else` ficou igual. O `if`, o `elif` e o `else` estão todos na mesma coluna. É isso que mostra que são uma só cadeia, em que corre exatamente um ramo.

2. Antes de correres, prevê o que aparece com `-2`, com `0` e com `1`. Guarda e corre os três casos. O que deves ver com -2:

   ```text
   Quantos baús queres construir? -2
   Pedido inválido: pede pelo menos 1 baú.
   Tábuas no inventário: 24
   ```

   Com 0, a mesma resposta. Com 1, `Pedido aceite. Baús construídos: 1` e `Tábuas no inventário: 16`. O inventário já não ganha tábuas de graça. O 0 é inválido e o 1 é válido: é a fronteira de baixo da validação.

   Repara numa coisa: a conta de `precisas` faz-se antes da cadeia, também para o -2. Não faz mal, porque nenhum ramo a usa com um pedido inválido: o primeiro ramo apanha-o antes.

### Paragem 4

O programa tem três respostas: inválido, aceite e recusado. Os pedidos de menos de 1 baú já não mexem no inventário.

Pensa antes de continuares: e se a validação viesse depois da pergunta das tábuas, com `if precisas <= tabuas:` primeiro e `elif baus < 1:` a seguir? O que aparecia com -2? A resposta: `Pedido aceite`, com 40 tábuas, como na fase 3. Com -2, a primeira pergunta, `-16 <= 24`, já dá `True`, e a cadeia acaba aí. Para chegar ao `elif`, o pedido tinha de precisar de mais de 24 tábuas, e então teria pelo menos 4 baús. Nenhum pedido chegava ao ramo do inválido: era um ramo inacessível. A validação vem antes de tudo.

## Fase 5: O limite da bancada, com `or`

A bancada só constrói até 5 baús de cada vez. Um pedido de 6 também é inválido, mesmo que um dia haja tábuas que cheguem. Os pedidos válidos formam um intervalo, de 1 a 5. Um pedido é inválido quando está fora dele: abaixo de 1 ou acima de 5. Em pseudocódigo, juntavas as duas comparações com `ou`. Em Python, o `ou` escreve-se `or`, e dá `True` quando pelo menos uma das partes dá `True`. Para saber mais, lê a secção "Validar um valor: dentro e fora de um intervalo" do [guia](../03-selecao.md).

1. Os dois limites da bancada passam a constantes, também o 1 da fase 4. Em `bancada.py`, substitui as duas linhas da regra do jogo, o comentário e a constante, por estas quatro:

   ```python
   # As regras do jogo, que não mudam enquanto o programa corre.
   TABUAS_POR_BAU = 8
   MINIMO_BAUS = 1
   MAXIMO_BAUS = 5
   ```

2. Na linha da leitura, muda a pergunta, para quem usa o programa saber o limite:

   ```python
   baus = int(input("Quantos baús queres construir (1 a 5)? "))
   ```

3. Substitui as três primeiras linhas da cadeia, o comentário, o `if` e o seu `print`, por estas:

   ```python
   # A validação vem primeiro: um pedido fora dos limites não se aceita nem se recusa.
   if baus < MINIMO_BAUS or baus > MAXIMO_BAUS:
       print("Pedido inválido: pede de", MINIMO_BAUS, "a", MAXIMO_BAUS, "baús.")
   ```

   Leitura guiada: a condição tem duas comparações, uma para cada lado do intervalo, ligadas por `or`. Basta uma dar `True` para o pedido ser inválido: o 0 falha o lado de baixo, e o 6 falha o de cima. A mensagem usa as constantes, e por isso diz sempre os limites certos. A pergunta do `input` tem o 1 e o 5 escritos no texto: se uma regra mudar, essa linha também tem de mudar. O resto da cadeia fica como estava.

4. Antes de correres, prevê o que aparece com 5 e com 6. Guarda e corre os dois casos. O que deves ver com 5:

   ```text
   Quantos baús queres construir (1 a 5)? 5
   Pedido recusado. Faltam 16 tábuas.
   Tábuas no inventário: 24
   ```

   E com 6:

   ```text
   Quantos baús queres construir (1 a 5)? 6
   Pedido inválido: pede de 1 a 5 baús.
   Tábuas no inventário: 24
   ```

   O 5 é válido, e por isso passa à pergunta das tábuas: precisa de 40, há 24, e faltam 16. O 6 já está fora do intervalo, e é inválido. É a fronteira de cima da validação.

5. Provoca um erro de propósito. Na linha do `if`, troca o `or` por `and`, para ficar `if baus < MINIMO_BAUS and baus > MAXIMO_BAUS:`. Antes de correres, prevê o que aparece com 6 e com 0. Guarda e corre. O que deves ver com 6: `Pedido recusado. Faltam 24 tábuas.` E com 0: `Pedido aceite. Baús construídos: 0`. A validação deixou de apanhar os pedidos inválidos. Com `and`, a condição pede um número que seja ao mesmo tempo menor do que 1 e maior do que 5. Esse número não existe. A condição dá sempre `False`, e o ramo do inválido ficou inacessível. Volta a pôr `or` e guarda.

### Paragem 5

O programa valida o pedido de 1 a 5 baús, aceita os que cabem no stock e recusa os outros. O ficheiro `bancada.py` completo, como deve estar agora:

```python
# bancada.py: a bancada de construção do inventário de um jogo de construção.
# O jogador pede baús, e o programa aceita ou recusa o pedido.

# As regras do jogo, que não mudam enquanto o programa corre.
TABUAS_POR_BAU = 8
MINIMO_BAUS = 1
MAXIMO_BAUS = 5

tabuas = 24
baus = int(input("Quantos baús queres construir (1 a 5)? "))
precisas = baus * TABUAS_POR_BAU

# A validação vem primeiro: um pedido fora dos limites não se aceita nem se recusa.
if baus < MINIMO_BAUS or baus > MAXIMO_BAUS:
    print("Pedido inválido: pede de", MINIMO_BAUS, "a", MAXIMO_BAUS, "baús.")
elif precisas <= tabuas:
    tabuas = tabuas - precisas
    print("Pedido aceite. Baús construídos:", baus)
else:
    # Esta conta só se faz quando o pedido é recusado.
    faltam = precisas - tabuas
    print("Pedido recusado. Faltam", faltam, "tábuas.")
print("Tábuas no inventário:", tabuas)
```

Pensa antes de continuares: como escreverias a condição contrária, a de um pedido válido? A resposta: `baus >= MINIMO_BAUS and baus <= MAXIMO_BAUS`. Para estar dentro do intervalo, o pedido tem de cumprir as duas comparações, e por isso leva `and`. Cada comparação passou para a contrária, com o limite a mudar de lado.

## Fase 6: Testar cada ramo e cada fronteira

O programa tem três ramos, e cada execução percorre só um. Um caso que passa diz que aquele ramo está certo, e não diz nada dos outros. Os casos de teste escolhem-se com duas regras: cada ramo tem pelo menos um caso, e cada limite tem três casos. São o valor imediatamente abaixo, o próprio limite e o valor imediatamente acima. O resultado esperado de cada caso calcula-se antes de correr, a partir das regras da bancada, e nunca a partir do que o programa mostra. Para saber mais, lê a secção "Os casos de teste de cada ramo" do [guia](../03-selecao.md).

1. O programa tem três limites. O 1 é o pedido mais pequeno que é válido. O 3 é o maior pedido para o qual as tábuas chegam. O 5 é o maior pedido válido. Com os três casos de cada limite, os casos de teste são os pedidos de 0 a 6 baús. Antes de correres, calcula o que o programa deve mostrar em cada caso.

   A resposta, na tabela de entradas e saídas, agora com o ramo de cada caso:

   | Baús | Ramo | Resposta esperada | Tábuas no fim | Porque é que este caso foi escolhido |
   | ---: | --- | --- | ---: | --- |
   | 0 | inválido | `Pedido inválido: pede de 1 a 5 baús.` | 24 | Imediatamente abaixo do limite de baixo |
   | 1 | aceite | `Pedido aceite. Baús construídos: 1` | 16 | O próprio limite de baixo |
   | 2 | aceite | `Pedido aceite. Baús construídos: 2` | 8 | Imediatamente acima do limite de baixo e abaixo do limite do stock |
   | 3 | aceite | `Pedido aceite. Baús construídos: 3` | 0 | O limite do stock: as tábuas chegam exatamente |
   | 4 | recusado | `Pedido recusado. Faltam 8 tábuas.` | 24 | Imediatamente acima do limite do stock e abaixo do limite de cima |
   | 5 | recusado | `Pedido recusado. Faltam 16 tábuas.` | 24 | O próprio limite de cima |
   | 6 | inválido | `Pedido inválido: pede de 1 a 5 baús.` | 24 | Imediatamente acima do limite de cima |

   Os três ramos têm casos: o inválido tem dois, um de cada lado do intervalo; o aceite tem três; o recusado tem dois. Cada limite tem os seus três casos.

2. Corre o programa sete vezes, uma por linha da tabela, com a seta para cima. Em cada uma, compara as duas linhas do ecrã com o que calculaste. Com 0, por exemplo, deves ver:

   ```text
   Quantos baús queres construir (1 a 5)? 0
   Pedido inválido: pede de 1 a 5 baús.
   Tábuas no inventário: 24
   ```

3. Um caso passa quando o ecrã mostra o que calculaste. Se algum não passar, depura com método. Num comentário no fim do `bancada.py`, escreve o caso, o esperado, o obtido, o tipo de erro e a tua hipótese. Confirma a hipótese no código e corrige só a causa. Depois corre outra vez os sete casos, e não só o que falhou.

### Paragem 6

Os sete casos da tabela passaram. O `bancada.py` tem um comentário em cada parte e dá uma resposta certa a qualquer pedido inteiro.

Pensa antes de terminares: das versões erradas que experimentaste, que caso apanhou cada uma? A resposta: o `<` no lugar do `<=`, da fase 3, só se nota com 3 baús, o limite do stock. O `and` no lugar do `or`, da fase 5, nota-se com 0 e com 6, os dois casos inválidos. Um pedido do meio, como o 2, dava o resultado certo nas duas versões erradas. É por isso que os casos de teste se escolhem nas fronteiras.

## Problemas frequentes

### `SyntaxError: expected ':'`

Faltam os dois pontos no fim de uma linha com `if`, `elif` ou `else`. O sinal `^` aponta para o fim da linha. Num Python mais antigo, a mensagem diz só `invalid syntax`. Acrescenta os dois pontos.

### `IndentationError: expected an indented block`

A linha a seguir a um `if`, a um `elif` ou a um `else` não tem os quatro espaços. O Python esperava um bloco e não o encontrou. Põe quatro espaços no início de cada linha do bloco.

### `IndentationError: unindent does not match any outer indentation level`

Uma linha tem um recuo que não corresponde a nenhum nível, como dois ou três espaços. Confirma que cada linha de um bloco tem exatamente quatro espaços. O `elif` e o `else` ficam encostados à margem, na coluna do `if`.

### `SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?`

Escreveste um só `=` numa condição, como `if baus = 0:`. Para perguntar, usam-se dois: `==`.

### `TypeError: '<' not supported between instances of 'str' and 'int'`

A mensagem pode ter `'<'` ou `'<='`, conforme a comparação onde o Python deu pelo problema. A leitura dos baús ficou sem o `int`, e o Python não compara um texto com um número. A causa está na linha do `input`, e não na do `if`, que é onde o Python deu pelo problema. Põe a leitura na forma `baus = int(input("..."))`.

### Aparecem duas respostas, ou nenhuma

Uma linha ficou no bloco errado. Se a linha do inventário não aparece num dos casos, ficou indentada, dentro de um bloco. Se aparecem duas respostas ao mesmo pedido, um `elif` foi escrito como `if`, e a cadeia partiu-se em duas decisões. Confirma a coluna onde começa cada linha.

## Desafios

1. Sem tábuas. Quando um pedido aceite deixa o inventário com 0 tábuas, o jogo avisa: "Ficaste sem tábuas.". Acrescenta o aviso ao programa. Testa-o com os sete casos da fase 6, com o resultado esperado de cada um calculado antes. Pista: o aviso só faz sentido depois de um pedido aceite.

2. Os baús grandes. A bancada passa a construir dois tipos de baú: o pequeno, que gasta 8 tábuas, e o grande, que gasta 12. O programa pergunta primeiro o tipo, com `P` ou `G`, e depois quantos baús. Um tipo que não seja `P` nem `G` torna o pedido inválido, com a mensagem `Tipo de baú inválido.`. Escolhe os casos de teste, com um caso para cada resposta e para cada tipo. Escreve-os num comentário no início do ficheiro, com o resultado esperado. Pista: as tábuas de cada baú passam a depender de uma decisão, que tem de vir antes da conta das tábuas.

3. Os troncos que faltam. Quando o pedido é recusado, o jogo diz também quantos troncos tens de apanhar, sabendo que cada tronco dá 4 tábuas. Com 4 baús faltam 8 tábuas, e chegam 2 troncos: o programa escreve `Troncos a apanhar: 2`. Testa-o com os pedidos de 4 e de 5 baús, e depois muda o inventário para 26 tábuas e testa-os outra vez. Pista: pensa no caso em que as tábuas que faltam não chegam para um tronco inteiro.

## Antes de terminares

- [ ] O `bancada.py` pergunta quantos baús queres construir e dá uma de três respostas: inválido, aceite ou recusado.
- [ ] Correste os sete casos da tabela da fase 6, e cada um deu o que calculaste antes de correr.
- [ ] Sabes dizer o que dão `24 <= 24` e `24 < 24`.
- [ ] Sabes dizer porque é que o `if`, o `elif` e o `else` de uma cadeia ficam na mesma coluna.
- [ ] Consegues explicar, por palavras tuas, porque é que a validação vem em primeiro lugar na cadeia, e o que acontecia se viesse depois.

![Rodapé](../../imagens/rodape.png)
