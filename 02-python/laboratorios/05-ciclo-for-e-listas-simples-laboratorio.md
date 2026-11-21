![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Ciclo for e listas simples

## O que vais construir

Vais construir o `armazem.py`, o armazém do inventário de um jogo de construção. Os nomes dos materiais ficam numa lista e as quantidades noutra, com os mesmos índices. O programa mostra o armazém, o total de unidades, o material com mais unidades, o primeiro material esgotado e o que é preciso encomendar. No fim, as quantidades passam a sair de uma tabela com dois baús, e o ecrã fica assim:

```text
Materiais no armazém: 5
1. troncos: 12
2. tábuas: 30
3. pedra: 45
4. ferro: 0
5. carvão: 8
Total de unidades: 95
Mais unidades: pedra com 45
Primeiro material esgotado: ferro
A encomendar: ['ferro', 'carvão']
```

1. [Fase 1: Uma lista guarda vários valores com um só nome](#fase-1-uma-lista-guarda-vários-valores-com-um-só-nome)
2. [Fase 2: Percorrer a lista pelo valor, com `for`](#fase-2-percorrer-a-lista-pelo-valor-com-for)
3. [Fase 3: Percorrer a lista pelo índice, com `range` e `len`](#fase-3-percorrer-a-lista-pelo-índice-com-range-e-len)
4. [Fase 4: O maior valor de uma lista](#fase-4-o-maior-valor-de-uma-lista)
5. [Fase 5: Parar a pesquisa com `break`](#fase-5-parar-a-pesquisa-com-break)
6. [Fase 6: Juntar elementos com `append`](#fase-6-juntar-elementos-com-append)
7. [Fase 7: As funções prontas: `sum`, `max`, `min` e `in`](#fase-7-as-funções-prontas-sum-max-min-e-in)
8. [Fase 8: A lista vazia e os três casos de teste](#fase-8-a-lista-vazia-e-os-três-casos-de-teste)
9. [Fase 9: Listas de listas: uma tabela numa só variável](#fase-9-listas-de-listas-uma-tabela-numa-só-variável)

## O que precisas

- A pasta `lp-python`, aberta no VS Code, e o terminal do VS Code a trabalhar nessa pasta. Se ainda não existir, cria-a dentro de Documentos e abre-a no VS Code, no menu File, com `Open Folder...`.
- O comando com que corres os teus programas: `python`, `py` ou `python3`. Neste laboratório aparece `python`, e trocas pelo teu, se for outro.

O `armazem.py` é um programa novo, e não precisas dos programas dos laboratórios anteriores.

## Fase 1: Uma lista guarda vários valores com um só nome

Crias o programa com duas listas, uma com os nomes e outra com as quantidades, e usas o índice e o `len`. O índice começa em 0, e o `len` diz quantos elementos tem a lista. Rever: [Uma lista guarda vários valores com um só nome](../05-ciclo-for-e-listas-simples.md#uma-lista-guarda-vários-valores-com-um-só-nome) e [O índice é a posição de cada elemento](../05-ciclo-for-e-listas-simples.md#o-índice-é-a-posição-de-cada-elemento).

1. Cria o programa. No painel Explorer, passa o rato por cima de `LP-PYTHON`, carrega no ícone `New File...`, escreve `armazem.py` e carrega em Enter. Escreve esta primeira versão:

   ```python
   # armazem.py: o armazém do inventário de um jogo de construção.
   # Guarda os materiais e as quantidades em duas listas, com os mesmos índices.

   nomes = ["troncos", "tábuas", "pedra", "ferro", "carvão"]
   quantidades = [12, 30, 45, 0, 8]
   print(nomes)
   print(quantidades)
   ```

2. Guarda e corre:

   ```bash
   python armazem.py
   ```

   O que deves ver:

   ```text
   ['troncos', 'tábuas', 'pedra', 'ferro', 'carvão']
   [12, 30, 45, 0, 8]
   ```

   Isto quer dizer que as duas listas ficaram guardadas, cada uma com um só nome. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

3. Mostra o primeiro e o último material. No fim do ficheiro, acrescenta:

   ```python
   print("Primeiro material:", nomes[0], quantidades[0])
   print("Último material:", nomes[-1], quantidades[-1])
   ```

   Guarda e corre. O que deves ver, a seguir às listas: `Primeiro material: troncos 12` e `Último material: carvão 8`. O mesmo índice, nas duas listas, dá o nome e a quantidade do mesmo material:

   | Índice | `nomes` | `quantidades` |
   | ---: | --- | ---: |
   | 0 | `"troncos"` | 12 |
   | 1 | `"tábuas"` | 30 |
   | 2 | `"pedra"` | 45 |
   | 3 | `"ferro"` | 0 |
   | 4 | `"carvão"` | 8 |

4. Provoca um erro de propósito. Na última linha, troca o `nomes[-1]` por `nomes[5]`. Guarda e corre. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\armazem.py", line 9, in <module>
       print("Último material:", nomes[5], quantidades[-1])
                                 ~~~~~^^^
   IndexError: list index out of range
   ```

   A lista tem cinco elementos, com os índices de 0 a 4, e o 5 não existe. Volta a pôr `nomes[-1]` e guarda.

5. Troca as duas linhas que escrevem as listas inteiras por esta, que diz quantos materiais há. Rever: [O `len` diz quantos elementos tem a lista](../05-ciclo-for-e-listas-simples.md#o-len-diz-quantos-elementos-tem-a-lista).

   ```python
   print("Materiais no armazém:", len(nomes))
   ```

   Guarda e corre. O que deves ver:

   ```text
   Materiais no armazém: 5
   Primeiro material: troncos 12
   Último material: carvão 8
   ```

### Paragem 1

O `armazem.py` diz quantos materiais há e mostra o primeiro e o último, com a quantidade de cada um.

Pensa antes de continuares: se `quantidades` tivesse só os quatro primeiros valores, `[12, 30, 45, 0]`, o que mostrava a linha do último material? A resposta: `Último material: carvão 0`, sem nenhuma mensagem. O nome é o do carvão, e a quantidade é a do ferro. As duas listas têm de ter sempre o mesmo número de elementos.

## Fase 2: Percorrer a lista pelo valor, com `for`

Somas as unidades de todos os materiais, com um `for` que passa por cada quantidade. O total começa em 0 antes do ciclo e soma cada elemento com o `+=`. Rever: [Percorrer a lista pelo valor, com `for`](../05-ciclo-for-e-listas-simples.md#percorrer-a-lista-pelo-valor-com-for).

1. No fim do ficheiro, deixa uma linha em branco e acrescenta:

   ```python
   total = 0
   for unidades in quantidades:
       total += unidades
   print("Total de unidades:", total)
   ```

   Guarda e corre. O que deves ver, no fim: `Total de unidades: 95`. Em cada volta, `unidades` recebeu uma das quantidades, e o `+=` somou-a ao total.

2. Provoca um erro de lógica. Põe quatro espaços no início do último `print`, para ele passar para dentro do ciclo. Guarda e corre. O que deves ver no fim:

   ```text
   Total de unidades: 12
   Total de unidades: 42
   Total de unidades: 87
   Total de unidades: 87
   Total de unidades: 95
   ```

   São cinco linhas, uma por volta, e só a última é o total. Tira os quatro espaços e guarda.

### Paragem 2

O programa mostra o total de unidades, numa só linha, depois da última volta.

Pensa antes de continuares: quanto vale `total` no fim da 4.ª volta, e porque é igual ao da 3.ª? A resposta: 87. Na 4.ª volta, `unidades` recebeu o 0 do ferro, e somar 0 não muda nada.

## Fase 3: Percorrer a lista pelo índice, com `range` e `len`

Trocas o primeiro e o último material pela lista numerada de todos. Cada volta precisa do índice, para ir buscar o nome e a quantidade do mesmo material. Rever: [Percorrer a lista pelo índice, com `range` e `len`](../05-ciclo-for-e-listas-simples.md#percorrer-a-lista-pelo-índice-com-range-e-len) e [Contar voltas com `for` e `range`](../05-ciclo-for-e-listas-simples.md#contar-voltas-com-for-e-range).

1. Apaga as linhas do primeiro e do último material e, no lugar delas, escreve:

   ```python
   # nomes[i] e quantidades[i] são do mesmo material, porque as listas têm os mesmos índices.
   for i in range(0, len(nomes)):
       print(str(i + 1) + ".", nomes[i] + ":", quantidades[i])
   ```

   O `range(0, len(nomes))` dá os índices de 0 a 4. O `str(i + 1) + "."` junta o número ao ponto, sem espaço pelo meio. Rever: [Juntar textos](../02-dados-e-interacao.md#juntar-textos).

2. Guarda e corre. O que deves ver:

   ```text
   Materiais no armazém: 5
   1. troncos: 12
   2. tábuas: 30
   3. pedra: 45
   4. ferro: 0
   5. carvão: 8
   Total de unidades: 95
   ```

3. Provoca um erro no limite. Na linha do `for`, troca `len(nomes)` por `len(nomes) + 1`. Guarda e corre. O que deves ver, a seguir às cinco linhas dos materiais:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\armazem.py", line 9, in <module>
       print(str(i + 1) + ".", nomes[i] + ":", quantidades[i])
                               ~~~~~^^^
   IndexError: list index out of range
   ```

   Na 6.ª volta, `i` vale 5, e a lista não tem o índice 5. O programa parou antes do total. Volta a pôr `len(nomes)` e guarda.

### Paragem 3

O programa mostra os cinco materiais numerados, de 1 a 5, e o total.

Pensa antes de continuares: porque é que este ciclo vai pelo índice, e o do total vai pelo valor? A resposta: este precisa da posição, para ir buscar a `nomes` o nome do material e para o numerar. O do total só precisa das quantidades.

## Fase 4: O maior valor de uma lista

Descobres o material com mais unidades, com o padrão do maior. Como precisas também do nome, o ciclo vai pelo índice. Rever: [O maior valor de uma lista](../05-ciclo-for-e-listas-simples.md#o-maior-valor-de-uma-lista).

1. Depois do `print` do total, deixa uma linha em branco e acrescenta:

   ```python
   # O maior começa no primeiro material, e o ciclo procura um com mais unidades.
   maior = quantidades[0]
   nome_maior = nomes[0]
   for i in range(0, len(quantidades)):
       if quantidades[i] > maior:
           maior = quantidades[i]
           nome_maior = nomes[i]
   print("Mais unidades:", nome_maior, "com", maior)
   ```

   O nome e a quantidade mudam juntos, dentro do mesmo `if`, para nunca ficarem de materiais diferentes.

2. Guarda e corre. O que deves ver, no fim: `Mais unidades: pedra com 45`.

3. Experimenta um empate. Na lista `quantidades`, troca o 45 da pedra por 30, que é o mesmo das tábuas. Guarda e corre. O que deves ver, no fim: `Mais unidades: tábuas com 30`. Com o `>`, um empate não troca o maior, e fica o primeiro dos dois. Volta a pôr 45 e guarda.

### Paragem 4

O programa diz que material tem mais unidades, com o nome e a quantidade.

Pensa antes de continuares: com as quantidades originais, em que voltas muda o maior? A resposta: na 2.ª volta, passa a 30, as tábuas, e na 3.ª passa a 45, a pedra. Na 1.ª, o 12 compara-se consigo mesmo, e nas outras nenhuma quantidade passa o maior.

## Fase 5: Parar a pesquisa com `break`

Procuras o primeiro material esgotado, com 0 unidades. Uma bandeira diz, depois do ciclo, se apareceu algum, e o `break` para a pesquisa no primeiro. Rever: [Procurar um valor com uma bandeira](../05-ciclo-for-e-listas-simples.md#procurar-um-valor-com-uma-bandeira), [Parar a pesquisa com `break`](../05-ciclo-for-e-listas-simples.md#parar-a-pesquisa-com-break) e [Contar as voltas: a pesquisa com e sem `break`](../05-ciclo-for-e-listas-simples.md#contar-as-voltas-a-pesquisa-com-e-sem-break).

1. Depois do `print` de `Mais unidades`, deixa uma linha em branco e escreve:

   ```python
   # A bandeira começa em False e só passa a True num material esgotado.
   encontrado = False
   for i in range(0, len(quantidades)):
       if quantidades[i] == 0:
           print("Primeiro material esgotado:", nomes[i])
           encontrado = True
   if not encontrado:
       print("Nenhum material esgotado.")
   ```

   Guarda e corre. O que deves ver, no fim: `Primeiro material esgotado: ferro`.

2. Esgota também o carvão. Na lista `quantidades`, troca o 8 por 0. Guarda e corre. O que deves ver, no fim:

   ```text
   Primeiro material esgotado: ferro
   Primeiro material esgotado: carvão
   ```

   O ciclo continuou depois do ferro, e o carvão também passou no `if`. A segunda linha está errada, porque o carvão não é o primeiro.

3. Para a pesquisa no primeiro. A seguir à linha `encontrado = True`, com os mesmos oito espaços, acrescenta:

   ```python fragment fica dentro do if, a seguir a encontrado = True
           # O primeiro já foi encontrado, e os outros materiais não interessam.
           break
   ```

   Guarda e corre, ainda com o carvão a 0. O que deves ver, no fim: só `Primeiro material esgotado: ferro`. Volta a pôr o 8 do carvão e guarda.

4. Experimenta um armazém sem esgotados. Troca o 0 do ferro por 6, guarda e corre. O que deves ver, no fim: `Nenhum material esgotado.`. A bandeira ficou em `False`, porque o ciclo chegou ao fim sem passar pelo `break`. Volta a pôr o 0 do ferro e guarda.

### Paragem 5

O programa diz qual é o primeiro material esgotado, ou que nenhum está esgotado.

Pensa antes de continuares: com as quantidades originais, quantas voltas dá este ciclo com o `break`? E quantas dava sem ele? A resposta: com o `break`, dá 4, a última no ferro, e sem ele dava 5. A resposta é a mesma, e o `break` poupa a volta do carvão. Num armazém de cem materiais com o ferro em primeiro, poupava 99.

## Fase 6: Juntar elementos com `append`

Fazes a lista do que é preciso encomendar. Começa vazia, e o `append` junta-lhe um nome de cada vez. Rever: [Juntar elementos com `append`](../05-ciclo-for-e-listas-simples.md#juntar-elementos-com-append).

1. O mínimo de cada material é uma regra do jogo, e por isso fica numa constante. Por baixo dos dois comentários do início, antes da linha de `nomes`, acrescenta estas duas linhas, com uma linha em branco antes e outra depois:

   ```python
   # Abaixo deste número de unidades, um material tem de ser encomendado.
   MINIMO_ENCOMENDA = 10
   ```

2. No fim do ficheiro, a seguir a uma linha em branco, escreve:

   ```python
   a_encomendar = []
   for i in range(0, len(quantidades)):
       # Um material entra na encomenda quando tem menos unidades do que o mínimo.
       if quantidades[i] < MINIMO_ENCOMENDA:
           a_encomendar.append(nomes[i])
   print("A encomendar:", a_encomendar)
   ```

   Guarda e corre. O que deves ver, no fim: `A encomendar: ['ferro', 'carvão']`. O ferro tem 0 e o carvão tem 8, os dois abaixo de 10.

3. Provoca um erro de propósito. Na linha do `append`, escreve `a_encomendar = a_encomendar.append(nomes[i])`. Guarda e corre. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\armazem.py", line 43, in <module>
       a_encomendar = a_encomendar.append(nomes[i])
                      ^^^^^^^^^^^^^^^^^^^
   AttributeError: 'NoneType' object has no attribute 'append'
   ```

   O `append` do ferro correu, mas a atribuição guardou o `None` em `a_encomendar`, e no do carvão já não havia lista. Volta a escrever só `a_encomendar.append(nomes[i])` e guarda.

### Paragem 6

O programa já mostra tudo o que o armazém precisa de dizer. O ficheiro `armazem.py` completo, como deve estar agora:

```python
# armazem.py: o armazém do inventário de um jogo de construção.
# Guarda os materiais e as quantidades em duas listas, com os mesmos índices.

# Abaixo deste número de unidades, um material tem de ser encomendado.
MINIMO_ENCOMENDA = 10

nomes = ["troncos", "tábuas", "pedra", "ferro", "carvão"]
quantidades = [12, 30, 45, 0, 8]
print("Materiais no armazém:", len(nomes))
# nomes[i] e quantidades[i] são do mesmo material, porque as listas têm os mesmos índices.
for i in range(0, len(nomes)):
    print(str(i + 1) + ".", nomes[i] + ":", quantidades[i])

total = 0
for unidades in quantidades:
    total += unidades
print("Total de unidades:", total)

# O maior começa no primeiro material, e o ciclo procura um com mais unidades.
maior = quantidades[0]
nome_maior = nomes[0]
for i in range(0, len(quantidades)):
    if quantidades[i] > maior:
        maior = quantidades[i]
        nome_maior = nomes[i]
print("Mais unidades:", nome_maior, "com", maior)

# A bandeira começa em False e só passa a True num material esgotado.
encontrado = False
for i in range(0, len(quantidades)):
    if quantidades[i] == 0:
        print("Primeiro material esgotado:", nomes[i])
        encontrado = True
        # O primeiro já foi encontrado, e os outros materiais não interessam.
        break
if not encontrado:
    print("Nenhum material esgotado.")

a_encomendar = []
for i in range(0, len(quantidades)):
    # Um material entra na encomenda quando tem menos unidades do que o mínimo.
    if quantidades[i] < MINIMO_ENCOMENDA:
        a_encomendar.append(nomes[i])
print("A encomendar:", a_encomendar)
```

A constante e as duas listas vêm primeiro. Depois, cada parte do armazém é um ciclo sobre as listas, com o seu resultado escrito logo a seguir.

Pensa antes de continuares: porque é que `a_encomendar = []` está antes do ciclo, e não dentro dele? A resposta: dentro, a lista voltava a ficar vazia em cada volta. No fim, só tinha o que a última volta juntou, o carvão, e aparecia `A encomendar: ['carvão']`.

## Fase 7: As funções prontas: `sum`, `max`, `min` e `in`

Confirmas os resultados dos padrões com as funções prontas do Python. Elas dão o valor, mas não dizem a posição. Rever: [As funções prontas: `sum`, `max`, `min` e `in`](../05-ciclo-for-e-listas-simples.md#as-funções-prontas-sum-max-min-e-in).

1. No fim do ficheiro, acrescenta estas duas linhas provisórias:

   ```python
   print("Confirmação:", sum(quantidades), max(quantidades), min(quantidades))
   print("Há esgotados?", 0 in quantidades, "Há areia?", "areia" in nomes)
   ```

   Guarda e corre. O que deves ver, no fim:

   ```text
   Confirmação: 95 45 0
   Há esgotados? True Há areia? False
   ```

   O 95 é o total, e o 45 é o maior. O `0 in quantidades` confirma que há um material esgotado, mas não diz qual é.

2. Apaga as duas linhas provisórias do fim, guarda e corre. O ecrã volta a ser o de "O que vais construir", sem a confirmação.

### Paragem 7

O programa voltou a ser o da paragem 6, e as funções prontas confirmaram o total e o maior.

Pensa antes de continuares: porque é que o programa não usa o `max(quantidades)` na linha `Mais unidades`? A resposta: o `max` dá o 45, mas não diz que é a pedra. Para o nome, é preciso a posição, e o padrão à mão guarda-a.

## Fase 8: A lista vazia e os três casos de teste

Corres o programa com o armazém vazio, com um só material e com vários, e comparas com o que pensaste antes. A lista vazia apanha os índices que não existem. Rever: [A lista vazia e os três casos de teste](../05-ciclo-for-e-listas-simples.md#a-lista-vazia-e-os-três-casos-de-teste).

1. Antes de correres, pensa no que o programa deve fazer em cada caso. A resposta:

   | Caso | `nomes` | `quantidades` | O que deve acontecer |
   | --- | --- | --- | --- |
   | Vazio | `[]` | `[]` | 0 materiais, total 0, nenhum maior, nenhum esgotado e nada a encomendar, sem parar com um erro |
   | Um material | `["pedra"]` | `[45]` | 1 material, total 45, a pedra com mais unidades, nenhum esgotado e nada a encomendar |
   | Vários | os cinco materiais | `[12, 30, 45, 0, 8]` | o ecrã de "O que vais construir" |

2. Esvazia o armazém: troca as duas listas por `nomes = []` e `quantidades = []`. Guarda e corre. O que deves ver:

   ```text
   Materiais no armazém: 0
   Total de unidades: 0
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\armazem.py", line 20, in <module>
       maior = quantidades[0]
               ~~~~~~~~~~~^^^
   IndexError: list index out of range
   ```

   O ciclo da lista numerada e o do total deram zero voltas, e funcionaram. O padrão do maior parou, porque numa lista vazia nem o índice 0 existe.

3. Protege o padrão do maior. Substitui as linhas do maior, do comentário ao `print` de `Mais unidades`, por estas:

   ```python
   # Sem materiais, não há maior: quantidades[0] nem existe.
   if len(quantidades) == 0:
       print("O armazém está vazio.")
   else:
       # O maior começa no primeiro material, e o ciclo procura um com mais unidades.
       maior = quantidades[0]
       nome_maior = nomes[0]
       for i in range(0, len(quantidades)):
           if quantidades[i] > maior:
               maior = quantidades[i]
               nome_maior = nomes[i]
       print("Mais unidades:", nome_maior, "com", maior)
   ```

   O padrão do maior passou para dentro do `else`, com mais quatro espaços em cada linha. No VS Code, podes selecionar as linhas e carregar em Tab, para lhes dar os quatro espaços de uma vez.

4. Guarda e corre, com o armazém ainda vazio. O que deves ver:

   ```text
   Materiais no armazém: 0
   Total de unidades: 0
   O armazém está vazio.
   Nenhum material esgotado.
   A encomendar: []
   ```

5. Experimenta um só material: troca as listas por `nomes = ["pedra"]` e `quantidades = [45]`. Guarda e corre. O que deves ver:

   ```text
   Materiais no armazém: 1
   1. pedra: 45
   Total de unidades: 45
   Mais unidades: pedra com 45
   Nenhum material esgotado.
   A encomendar: []
   ```

   Com um só material, a primeira volta é também a última, e a pedra é ao mesmo tempo o primeiro material e o maior.

6. Volta a pôr as duas listas com os cinco materiais e as quantidades `[12, 30, 45, 0, 8]`. Guarda e corre. O que deves ver: o ecrã de "O que vais construir".

### Paragem 8

Os três casos dão agora o que pensaste antes, e o armazém vazio já não para com um erro.

Pensa antes de continuares: que linha do programa só o caso vazio pôs à prova? A resposta: a do `maior = quantidades[0]`. Nos outros dois casos, o índice 0 existe, e o erro nunca aparecia.

## Fase 9: Listas de listas: uma tabela numa só variável

As unidades passam a estar numa tabela de dois baús, com uma linha por material e uma coluna por baú. A quantidade de cada material sai da soma da sua linha, com um `for` dentro de outro. Rever: [Listas de listas: uma tabela numa só variável](../05-ciclo-for-e-listas-simples.md#listas-de-listas-uma-tabela-numa-só-variável) e [Percorrer uma lista de listas: um `for` dentro de outro](../05-ciclo-for-e-listas-simples.md#percorrer-uma-lista-de-listas-um-for-dentro-de-outro).

1. Acrescenta a tabela. A seguir à linha da lista `nomes`, escreve:

   ```python
   # Uma linha por material, pela ordem de nomes, e uma coluna por baú.
   baus = [
       [8, 4],
       [20, 10],
       [30, 15],
       [0, 0],
       [5, 3],
   ]
   print("Pedra no baú 2:", baus[2][1])
   ```

   Guarda e corre. O que deves ver, logo na primeira linha: `Pedra no baú 2: 15`. O índice 2 escolhe a linha da pedra, e o índice 1 escolhe a coluna do baú 2.

2. Provoca um erro de propósito. No `print` que acabaste de escrever, troca `baus[2][1]` por `baus[2][2]`. Guarda e corre. O que deves ver:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\armazem.py", line 16, in <module>
       print("Pedra no baú 2:", baus[2][2])
                                ~~~~~~~^^^
   IndexError: list index out of range
   ```

   A linha da pedra só tem dois baús, com os índices 0 e 1. Apaga este `print`, que já não faz falta, e guarda.

3. As quantidades passam a sair da tabela. Substitui a linha `quantidades = [12, 30, 45, 0, 8]` por uma linha em branco e estas:

   ```python
   # A quantidade de cada material é a soma da sua linha da tabela.
   quantidades = []
   for linha in baus:
       total_material = 0
       for unidades_bau in linha:
           total_material += unidades_bau
       quantidades.append(total_material)
   ```

   O ciclo de fora passa pelas linhas, e o de dentro soma os baús de uma linha. O `append` junta cada soma à lista, pela ordem dos materiais.

4. Guarda e corre. O ecrã é igual ao de antes da tabela, porque as somas das linhas dão as quantidades de antes:

   | Material | Baú 1 | Baú 2 | Soma |
   | --- | ---: | ---: | ---: |
   | troncos | 8 | 4 | 12 |
   | tábuas | 20 | 10 | 30 |
   | pedra | 30 | 15 | 45 |
   | ferro | 0 | 0 | 0 |
   | carvão | 5 | 3 | 8 |

   O resto do programa, que só usa `quantidades`, não precisou de mudar.

5. Provoca um erro de lógica. Passa a linha `total_material = 0` para antes do `for linha in baus:`, encostada à margem. Guarda e corre. O que deves ver: as quantidades 12, 42, 87, 87 e 95, `Mais unidades: carvão com 95` e `Nenhum material esgotado.`. O total já não volta a 0 em cada material, e cada linha soma também as anteriores. Volta a pôr a linha onde estava, dentro do ciclo de fora, com quatro espaços, e guarda.

### Paragem 9

O programa mostra o armazém a partir da tabela dos dois baús. O ficheiro `armazem.py` completo, como deve estar no fim:

```python
# armazem.py: o armazém do inventário de um jogo de construção.
# Guarda os materiais e as quantidades em duas listas, com os mesmos índices.

# Abaixo deste número de unidades, um material tem de ser encomendado.
MINIMO_ENCOMENDA = 10

nomes = ["troncos", "tábuas", "pedra", "ferro", "carvão"]
# Uma linha por material, pela ordem de nomes, e uma coluna por baú.
baus = [
    [8, 4],
    [20, 10],
    [30, 15],
    [0, 0],
    [5, 3],
]

# A quantidade de cada material é a soma da sua linha da tabela.
quantidades = []
for linha in baus:
    total_material = 0
    for unidades_bau in linha:
        total_material += unidades_bau
    quantidades.append(total_material)
print("Materiais no armazém:", len(nomes))
# nomes[i] e quantidades[i] são do mesmo material, porque as listas têm os mesmos índices.
for i in range(0, len(nomes)):
    print(str(i + 1) + ".", nomes[i] + ":", quantidades[i])

total = 0
for unidades in quantidades:
    total += unidades
print("Total de unidades:", total)

# Sem materiais, não há maior: quantidades[0] nem existe.
if len(quantidades) == 0:
    print("O armazém está vazio.")
else:
    # O maior começa no primeiro material, e o ciclo procura um com mais unidades.
    maior = quantidades[0]
    nome_maior = nomes[0]
    for i in range(0, len(quantidades)):
        if quantidades[i] > maior:
            maior = quantidades[i]
            nome_maior = nomes[i]
    print("Mais unidades:", nome_maior, "com", maior)

# A bandeira começa em False e só passa a True num material esgotado.
encontrado = False
for i in range(0, len(quantidades)):
    if quantidades[i] == 0:
        print("Primeiro material esgotado:", nomes[i])
        encontrado = True
        # O primeiro já foi encontrado, e os outros materiais não interessam.
        break
if not encontrado:
    print("Nenhum material esgotado.")

a_encomendar = []
for i in range(0, len(quantidades)):
    # Um material entra na encomenda quando tem menos unidades do que o mínimo.
    if quantidades[i] < MINIMO_ENCOMENDA:
        a_encomendar.append(nomes[i])
print("A encomendar:", a_encomendar)
```

A tabela é a única fonte das unidades, e a lista `quantidades` faz-se a partir dela. O resto do programa é o da fase 8, e trabalha sobre `quantidades` como antes.

Pensa antes de terminares: se o armazém ganhar um terceiro baú, o que tens de mudar? A resposta: só a tabela, com um terceiro valor em cada linha. O ciclo de dentro passa a dar três voltas por material, sem mudares mais nada.

## Se alguma coisa falhar

1. Guardaste as alterações? Só corre o que está guardado.
2. O terminal está na pasta certa? O caminho escrito antes do `>` ou do `%` tem de acabar em `lp-python`.
3. Aparece `>>>`? Estás na consola, e voltas ao terminal com `exit()`.
4. A tua mensagem tem outras palavras? Noutras versões do Python, o nome do erro é o mesmo, e podem faltar os sinais por baixo da linha.

### `IndexError: list index out of range`

Usaste um índice que a lista não tem. Confirma que o `range` é `range(0, len(...))`, sem o `+ 1`, e que `nomes` e `quantidades` têm o mesmo número de elementos. Com o armazém vazio, confirma que o padrão do maior está dentro do `else`.

### `AttributeError: 'NoneType' object has no attribute 'append'`

O `append` ficou numa atribuição. Escreve-se sozinho na linha: `a_encomendar.append(nomes[i])`.

### `TypeError: unsupported operand type(s) for +: 'int' and 'str'`

Na lista numerada, falta o `str` à volta do `i + 1`. Um número não se junta a um texto com o `+`.

### `SyntaxError: '[' was never closed`

Falta um `]` numa lista ou na tabela. Cada `[` tem o seu `]`, e a tabela fecha com um `]` sozinho na última linha.

### `TypeError: list indices must be integers or slices, not tuple`

Falta uma vírgula entre duas linhas da tabela. Por cima do erro aparece o aviso `perhaps you missed a comma?`, "talvez te tenhas esquecido de uma vírgula?". Cada linha da tabela acaba numa vírgula.

### `NameError: name 'baus' is not defined`

O ciclo que soma as linhas ficou antes da tabela. A tabela tem de vir primeiro, logo a seguir a `nomes`.

### Aparecem duas linhas de primeiro material esgotado

Falta o `break`. Se, pelo contrário, aparece sempre `Nenhum material esgotado.`, o `break` ficou com quatro espaços, fora do `if`, e o ciclo acaba logo na primeira volta.

### As quantidades crescem de material para material

O `total_material = 0` ficou fora do ciclo de fora. Tem de estar dentro dele, com quatro espaços, para voltar a 0 em cada material.

## Desafios

1. A entrega. Uma entrega traz unidades de um material. Antes de mostrar o armazém, o programa pergunta que material chegou e quantas unidades. As unidades somam-se à quantidade desse material, na lista `quantidades`, depois de ela ser feita a partir da tabela. Um material que não está em `nomes` dá `Esse material não existe no armazém.` e não muda nada. Testa-o com 20 de ferro e com areia. Pista: primeiro procura a posição do material, e só depois muda a quantidade.

2. O baú mais cheio. No fim, o programa mostra o total de unidades de cada baú e diz qual é o baú mais cheio. Com a tabela da fase 9, o baú 1 tem 63 unidades, e o baú 2 tem 32. Pista: num baú, a coluna fica sempre a mesma, e mudam as linhas.

3. Quanto encomendar. Em vez da lista, para cada material abaixo do mínimo, o programa mostra quantas unidades faltam para lá chegar, como `ferro: encomendar 10`. Se não houver nada a encomendar, mostra `Não há nada a encomendar.`. Testa-o também com um armazém em que todos os materiais têm 10 ou mais unidades. Pista: a frase de quando não há nada só se pode escrever depois do ciclo.

## Antes de terminares

- [ ] O `armazem.py` mostra os materiais numerados, o total, o material com mais unidades, o primeiro esgotado e o que é preciso encomendar.
- [ ] As quantidades saem da tabela dos dois baús, com um `for` dentro de outro.
- [ ] Correste os três casos da fase 8, e o armazém vazio não para com um erro.

![Rodapé](../../imagens/rodape.png)
