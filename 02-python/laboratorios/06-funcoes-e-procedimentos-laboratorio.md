![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Funções e procedimentos

## O que vais construir

Vais reorganizar o armazém do laboratório 05 em funções, no `armazem_funcoes.py`. Cada conta passa para uma função testada sozinha, e a parte principal fica com as listas, as chamadas e os `print`. No fim, as mesmas funções mostram também um segundo armazém, o da mina, e o ecrã fica assim:

```text
Armazém da base
Materiais no armazém: 5
1. troncos: 12
2. tábuas: 30
3. pedra: 45
4. ferro: 0
5. carvão: 8
Total de unidades: 95
Lugares livres: 25
Mais unidades: pedra com 45
Primeiro material esgotado: ferro
A encomendar: ['ferro', 'carvão']

Armazém da mina
Materiais no armazém: 3
1. pedra: 60
2. ferro: 4
3. carvão: 15
Total de unidades: 79
A encomendar: ['ferro']
```

1. [Fase 1: Do pseudocódigo para Python, com `def`](#fase-1-do-pseudocódigo-para-python-com-def)
2. [Fase 2: O `return` devolve um valor a quem chamou](#fase-2-o-return-devolve-um-valor-a-quem-chamou)
3. [Fase 3: Testar cada função sozinha](#fase-3-testar-cada-função-sozinha)
4. [Fase 4: Os procedimentos devolvem `None`](#fase-4-os-procedimentos-devolvem-none)
5. [Fase 5: As funções calculam, e a parte principal escreve](#fase-5-as-funções-calculam-e-a-parte-principal-escreve)
6. [Fase 6: O `return` termina a função](#fase-6-o-return-termina-a-função)
7. [Fase 7: As variáveis de uma função são locais](#fase-7-as-variáveis-de-uma-função-são-locais)
8. [Fase 8: Dentro da função: parâmetros, variáveis locais e constantes](#fase-8-dentro-da-função-parâmetros-variáveis-locais-e-constantes)

## O que precisas

- A pasta `lp-python`, aberta no VS Code, e o terminal do VS Code a trabalhar nessa pasta.
- O comando com que corres os teus programas: `python`, `py` ou `python3`. Neste laboratório aparece `python`, e trocas pelo teu, se for outro.
- O ficheiro completo da [Paragem 9 do laboratório 05](05-ciclo-for-e-listas-simples-laboratorio.md#paragem-9), que é o ponto de partida. Toda a gente parte dele, mesmo quem não acabou o laboratório 05, e o teu `armazem.py` fica como está.

## Preparar o projeto

1. Cria o ficheiro novo. No painel Explorer, passa o rato por cima de `LP-PYTHON`, carrega no ícone `New File...`, escreve `armazem_funcoes.py` e carrega em Enter.

2. Abre a [Paragem 9 do laboratório 05](05-ciclo-for-e-listas-simples-laboratorio.md#paragem-9) e copia o ficheiro completo que lá está, da primeira à última linha, para o `armazem_funcoes.py`.

3. A primeira linha diz o nome e o papel do ficheiro. Troca-a por esta:

   ```python
   # armazem_funcoes.py: o armazém do inventário de um jogo de construção, com funções.
   ```

4. Guarda e corre:

   ```bash
   python armazem_funcoes.py
   ```

   O que deves ver:

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

   É o ecrã do fim do laboratório 05. Em cada fase, um bloco de código da parte principal passa para uma função. O ecrã fica igual, a não ser onde o passo diz o que muda. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

## Fase 1: Do pseudocódigo para Python, com `def`

A lista numerada passa para `mostrar_armazem`, um procedimento: uma função que só escreve e não tem `return`. Escreve-se com `def` e chama-se na parte principal. Rever: [Do pseudocódigo para Python, com `def`](../06-funcoes-e-procedimentos.md#do-pseudocódigo-para-python-com-def).

1. Escreve o procedimento. Entre `MINIMO_ENCOMENDA = 10` e `nomes = [` já há uma linha em branco. Acrescenta lá a função, de modo que fiquem duas linhas em branco antes do `def` e duas depois da função:

   ```python
   def mostrar_armazem(nomes, quantidades):
       """Escreve quantos materiais há e a lista numerada dos materiais.

       Recebe a lista dos nomes dos materiais, textos, e a lista das quantidades,
       inteiros, com os mesmos índices. Não devolve nada: escreve uma linha com o
       número de materiais e uma linha por material.
       """
       print("Materiais no armazém:", len(nomes))
       # nomes[i] e quantidades[i] são do mesmo material, porque as listas têm os mesmos índices.
       for i in range(0, len(nomes)):
           print(str(i + 1) + ".", nomes[i] + ":", quantidades[i])
   ```

   O corpo são as linhas que já escreviam a lista, agora com mais quatro espaços. O texto entre as três aspas é a docstring: diz o que a função recebe e faz, e o Python não o executa. Rever: [A documentação diz o que a função recebe e devolve](../06-funcoes-e-procedimentos.md#a-documentação-diz-o-que-a-função-recebe-e-devolve).

2. Antes de correres, prevê: o que muda no ecrã? Guarda e corre. O ecrã fica igual, e a lista aparece só uma vez. O `def` só cria a função, e o corpo não corre enquanto ninguém a chamar.

3. Chama o procedimento. A parte principal, o que na algoritmia era o algoritmo principal, começa em `nomes = [`. Por cima dessa linha, acrescenta este comentário:

   ```python
   # A parte principal: o armazém da base.
   ```

   Depois, apaga as quatro linhas que escreviam a lista: o `print` de `Materiais no armazém`, o comentário dos índices, o `for` e o `print` dele. No lugar delas, escreve:

   ```python
   mostrar_armazem(nomes, quantidades)
   ```

   Guarda e corre. O que deves ver: o mesmo ecrã da preparação. A lista é agora escrita pelo procedimento.

4. Provoca um erro de propósito. Na chamada, apaga o segundo argumento, para ficar `mostrar_armazem(nomes)`. Guarda e corre. O que deves ver:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\armazem_funcoes.py", line 39, in <module>
       mostrar_armazem(nomes)
       ~~~~~~~~~~~~~~~^^^^^^^
   TypeError: mostrar_armazem() missing 1 required positional argument: 'quantidades'
   ```

   A mensagem quer dizer "falta 1 argumento obrigatório: `quantidades`". O cabeçalho tem dois parâmetros, e a chamada só deu um argumento. Volta a pôr `mostrar_armazem(nomes, quantidades)` e guarda.

### Paragem 1

O programa mostra o mesmo ecrã, e a lista numerada é escrita pelo `mostrar_armazem`.

Pensa antes de continuares: o parâmetro `quantidades` e a lista `quantidades` da parte principal têm de ter o mesmo nome? A resposta: não. O parâmetro recebe o valor do argumento que está na mesma posição, seja qual for o nome dele. Com `mostrar_armazem(nomes, outra_lista)`, o parâmetro `quantidades` recebia `outra_lista`.

## Fase 2: O `return` devolve um valor a quem chamou

A soma das unidades passa para uma função, `total_de_unidades`, que devolve o total com `return`. Depois, o total serve também para uma conta, a dos lugares livres. Rever: [O `return` devolve um valor a quem chamou](../06-funcoes-e-procedimentos.md#o-return-devolve-um-valor-a-quem-chamou).

1. Escreve a função a seguir ao `mostrar_armazem`, com duas linhas em branco antes e duas depois:

   ```python
   def total_de_unidades(quantidades):
       """Devolve a soma das unidades de todos os materiais.

       Recebe a lista das quantidades, inteiros. Devolve um inteiro: a soma,
       ou 0 se a lista estiver vazia.
       """
       total = 0
       for unidades in quantidades:
           total += unidades
       return total
   ```

2. Usa o valor devolvido. Na parte principal, troca as quatro linhas do total, de `total = 0` até ao `print` de `Total de unidades`, por estas duas:

   ```python
   total = total_de_unidades(quantidades)
   print("Total de unidades:", total)
   ```

   Guarda e corre. O que deves ver: o mesmo ecrã, com `Total de unidades: 95`. A chamada passou a valer 95: é como se a linha fosse `total = 95`.

3. Usa o total numa conta. O armazém leva 120 unidades. Logo abaixo de `MINIMO_ENCOMENDA = 10`, acrescenta a constante:

   ```python
   # O número de unidades que cabem no armazém.
   CAPACIDADE = 120
   ```

   Na parte principal, logo abaixo do `print` de `Total de unidades`, acrescenta:

   ```python
   print("Lugares livres:", CAPACIDADE - total)
   ```

   Antes de correres, prevê o número que aparece. Guarda e corre. O que deves ver, a seguir ao total: `Lugares livres: 25`, porque 120 menos 95 dá 25.

### Paragem 2

O ecrã tem uma linha nova, `Lugares livres: 25`, e o total vem da função.

Pensa antes de continuares: podias escrever `print("Lugares livres:", CAPACIDADE - total_de_unidades(quantidades))`, sem a variável `total`? A resposta: sim. A chamada vale 95 e pode entrar numa conta, como o `len`.

## Fase 3: Testar cada função sozinha

A função `total_de_unidades` passa a ter linhas de teste, que comparam o que ela devolve com o que se esperava. Rever: [Testar cada função sozinha](../06-funcoes-e-procedimentos.md#testar-cada-função-sozinha).

1. Escreve as linhas de teste. Entre a última função e o comentário da parte principal, acrescenta estas linhas. Deixa duas linhas em branco antes e duas depois:

   ```python
   # Testes das funções sozinhas: o valor devolvido e o que se esperava.
   print(total_de_unidades([]), "esperado: 0")
   print(total_de_unidades([7]), "esperado: 7")
   print(total_de_unidades([12, 30, 45, 0, 8]), "esperado: 95")
   ```

   Os três casos são a lista vazia, uma lista com um elemento e uma com vários.

2. Guarda e corre. O que deves ver no início, antes do armazém:

   ```text
   0 esperado: 0
   7 esperado: 7
   95 esperado: 95
   ```

   As três linhas batem certo, e a função está pronta a usar.

3. Provoca um erro na função. Em `total_de_unidades`, troca `total = 0` por `total = 1`. Guarda e corre. O que deves ver no início:

   ```text
   1 esperado: 0
   8 esperado: 7
   96 esperado: 95
   ```

   Os três testes falham pelo mesmo 1 a mais, e o armazém mostra `Total de unidades: 96` e `Lugares livres: 24`. Os testes mostram que o erro está na função, sem procurares na parte principal. Volta a pôr `total = 0` e guarda.

4. Desliga as linhas de teste. Seleciona as três linhas que começam por `print(total_de_unidades` e escolhe `Toggle Line Comment`, no menu Edit. Cada linha passa a começar por `# `. Guarda e corre. O que deves ver: o ecrã da Paragem 2, sem as linhas de teste.

### Paragem 3

O ficheiro tem as três linhas de teste do `total_de_unidades`, desligadas com `#`, e o ecrã é o da Paragem 2.

Pensa antes de continuares: porque é que as linhas de teste ficam no ficheiro, desligadas, em vez de se apagarem? A resposta: para voltares a testar quando mudares a função. Basta ligá-las outra vez com `Toggle Line Comment`.

## Fase 4: Os procedimentos devolvem `None`

As quantidades que saem da tabela dos baús passam para uma função que devolve uma lista. Depois, vês o que acontece quando o `return` falta, e o que devolve um procedimento. Rever: [Os procedimentos devolvem `None`](../06-funcoes-e-procedimentos.md#os-procedimentos-devolvem-none).

1. Escreve a função a seguir ao `total_de_unidades`, com duas linhas em branco antes e duas depois:

   ```python
   def quantidades_dos_baus(baus):
       """Devolve a quantidade de cada material, somando as unidades dos baús.

       Recebe a tabela dos baús, uma lista de listas de inteiros, com uma linha
       por material e uma coluna por baú. Devolve uma lista de inteiros, com a
       soma de cada linha, pela mesma ordem, ou a lista vazia se a tabela estiver
       vazia.
       """
       quantidades = []
       for linha in baus:
           # O total volta a 0 em cada material, antes de somar os baús dele.
           total_material = 0
           for unidades_bau in linha:
               total_material += unidades_bau
           quantidades.append(total_material)
       return quantidades
   ```

2. Na parte principal, troca o bloco que fazia as quantidades, do comentário `# A quantidade de cada material` até ao `quantidades.append(total_material)`, por esta linha:

   ```python
   quantidades = quantidades_dos_baus(baus)
   ```

   Guarda e corre. O que deves ver: o ecrã da Paragem 2.

3. Testa a função sozinha. Logo a seguir às linhas de teste desligadas, sem linha em branco, acrescenta estas três:

   ```python
   print(quantidades_dos_baus([]), "esperado: []")
   print(quantidades_dos_baus([[3, 4]]), "esperado: [7]")
   print(quantidades_dos_baus([[8, 4], [0, 0], [5, 3]]), "esperado: [12, 0, 8]")
   ```

   Guarda e corre. O que deves ver no início: `[] esperado: []`, `[7] esperado: [7]` e `[12, 0, 8] esperado: [12, 0, 8]`. Desliga as três com `Toggle Line Comment` e guarda.

4. Provoca um erro de propósito. Em `quantidades_dos_baus`, põe um `#` no início da linha `return quantidades`, para ela passar a comentário. Guarda e corre. O que deves ver:

   ```text
   Materiais no armazém: 5
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\armazem_funcoes.py", line 74, in <module>
       mostrar_armazem(nomes, quantidades)
       ~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^
     File "C:\Users\aluno\Documents\lp-python\armazem_funcoes.py", line 20, in mostrar_armazem
       print(str(i + 1) + ".", nomes[i] + ":", quantidades[i])
                                               ~~~~~~~~~~~^^^
   TypeError: 'NoneType' object is not subscriptable
   ```

   A mensagem quer dizer "não se pode usar um índice no `None`". Sem `return`, a função devolveu `None`, e `quantidades` ficou com ele. O programa parou dentro do `mostrar_armazem`, mas a causa está na função sem `return`. Tira o `#` e guarda.

5. Vê o que devolve um procedimento. No fim do ficheiro, acrescenta esta linha provisória:

   ```python
   print(mostrar_armazem(nomes, quantidades))
   ```

   Guarda e corre. O que deves ver, no fim: a lista dos cinco materiais outra vez, e por baixo `None`. A chamada escreveu a lista, e o `print` escreveu o que ela devolveu. Apaga a linha e guarda.

### Paragem 4

O programa mostra o ecrã da Paragem 2. As quantidades vêm do `quantidades_dos_baus`, testado sozinho. O ficheiro `armazem_funcoes.py` completo, como deve estar agora:

```python
# armazem_funcoes.py: o armazém do inventário de um jogo de construção, com funções.
# Guarda os materiais e as quantidades em duas listas, com os mesmos índices.

# Abaixo deste número de unidades, um material tem de ser encomendado.
MINIMO_ENCOMENDA = 10
# O número de unidades que cabem no armazém.
CAPACIDADE = 120


def mostrar_armazem(nomes, quantidades):
    """Escreve quantos materiais há e a lista numerada dos materiais.

    Recebe a lista dos nomes dos materiais, textos, e a lista das quantidades,
    inteiros, com os mesmos índices. Não devolve nada: escreve uma linha com o
    número de materiais e uma linha por material.
    """
    print("Materiais no armazém:", len(nomes))
    # nomes[i] e quantidades[i] são do mesmo material, porque as listas têm os mesmos índices.
    for i in range(0, len(nomes)):
        print(str(i + 1) + ".", nomes[i] + ":", quantidades[i])


def total_de_unidades(quantidades):
    """Devolve a soma das unidades de todos os materiais.

    Recebe a lista das quantidades, inteiros. Devolve um inteiro: a soma,
    ou 0 se a lista estiver vazia.
    """
    total = 0
    for unidades in quantidades:
        total += unidades
    return total


def quantidades_dos_baus(baus):
    """Devolve a quantidade de cada material, somando as unidades dos baús.

    Recebe a tabela dos baús, uma lista de listas de inteiros, com uma linha
    por material e uma coluna por baú. Devolve uma lista de inteiros, com a
    soma de cada linha, pela mesma ordem, ou a lista vazia se a tabela estiver
    vazia.
    """
    quantidades = []
    for linha in baus:
        # O total volta a 0 em cada material, antes de somar os baús dele.
        total_material = 0
        for unidades_bau in linha:
            total_material += unidades_bau
        quantidades.append(total_material)
    return quantidades


# Testes das funções sozinhas: o valor devolvido e o que se esperava.
# print(total_de_unidades([]), "esperado: 0")
# print(total_de_unidades([7]), "esperado: 7")
# print(total_de_unidades([12, 30, 45, 0, 8]), "esperado: 95")
# print(quantidades_dos_baus([]), "esperado: []")
# print(quantidades_dos_baus([[3, 4]]), "esperado: [7]")
# print(quantidades_dos_baus([[8, 4], [0, 0], [5, 3]]), "esperado: [12, 0, 8]")


# A parte principal: o armazém da base.
nomes = ["troncos", "tábuas", "pedra", "ferro", "carvão"]
# Uma linha por material, pela ordem de nomes, e uma coluna por baú.
baus = [
    [8, 4],
    [20, 10],
    [30, 15],
    [0, 0],
    [5, 3],
]

quantidades = quantidades_dos_baus(baus)
mostrar_armazem(nomes, quantidades)

total = total_de_unidades(quantidades)
print("Total de unidades:", total)
print("Lugares livres:", CAPACIDADE - total)

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

As três funções estão em cima, por baixo das constantes, e as linhas de teste vêm a seguir, desligadas. A parte principal já chama as três, e ainda tem três blocos por passar a funções: o maior, o primeiro esgotado e a encomenda.

Pensa antes de continuares: porque é que `mostrar_armazem` não precisa de `return`, e `quantidades_dos_baus` precisa? A resposta: o `mostrar_armazem` é um procedimento, e o trabalho dele é escrever no ecrã. O `quantidades_dos_baus` calcula uma lista, que a parte principal usa a seguir.

## Fase 5: As funções calculam, e a parte principal escreve

O material com mais unidades passa para uma função que devolve o índice do maior. Quem escreve o nome e a quantidade é a parte principal. Rever: [As funções calculam, e a parte principal escreve](../06-funcoes-e-procedimentos.md#as-funções-calculam-e-a-parte-principal-escreve).

1. Escreve a função a seguir ao `quantidades_dos_baus`, com duas linhas em branco antes e duas depois:

   ```python
   def indice_do_maior(quantidades):
       """Devolve o índice do material com mais unidades.

       Recebe a lista das quantidades, inteiros, com pelo menos um elemento.
       Devolve um inteiro: o índice do maior e, num empate, o do primeiro.
       Com a lista vazia, devolve 0, que não é um índice dessa lista, por isso
       confirma antes que ela tem elementos.
       """
       i_maior = 0
       for i in range(0, len(quantidades)):
           # Com >, um empate não troca o índice: fica o primeiro.
           if quantidades[i] > quantidades[i_maior]:
               i_maior = i
       return i_maior
   ```

   A função guarda só o índice do maior. A quantidade dele está sempre em `quantidades[i_maior]`.

2. Na parte principal, troca o bloco do maior, do comentário `# Sem materiais` até ao `print` de `Mais unidades`, por este:

   ```python
   # Sem materiais, não há maior: indice_do_maior precisa de pelo menos um.
   if len(quantidades) == 0:
       print("O armazém está vazio.")
   else:
       i_maior = indice_do_maior(quantidades)
       print("Mais unidades:", nomes[i_maior], "com", quantidades[i_maior])
   ```

   Guarda e corre. O que deves ver: o ecrã da Paragem 2, com `Mais unidades: pedra com 45`.

3. Testa a função sozinha. Logo a seguir às linhas de teste desligadas, sem linha em branco, acrescenta:

   ```python
   print(indice_do_maior([7]), "esperado: 0")
   print(indice_do_maior([12, 30, 45, 0, 8]), "esperado: 2")
   print(indice_do_maior([5, 9, 9]), "esperado: 1")
   ```

   Guarda e corre. O que deves ver no início: `0 esperado: 0`, `2 esperado: 2` e `1 esperado: 1`. O último caso é um empate, e fica o primeiro dos dois 9. Desliga as três linhas e guarda.

### Paragem 5

O programa mostra o ecrã da Paragem 2, e o material com mais unidades vem do índice que a função devolve.

Pensa antes de continuares: se `indice_do_maior` escrevesse o índice com `print`, em vez de o devolver, o que acontecia? A resposta: `i_maior` ficava com `None`, e `nomes[i_maior]` parava o programa com `TypeError: list indices must be integers or slices, not NoneType`. Só um valor devolvido se usa a seguir.

## Fase 6: O `return` termina a função

O primeiro material esgotado passa para uma função com dois `return`: um dentro do ciclo, quando encontra, e outro depois dele. A bandeira e o `break` deixam de fazer falta. Rever: [O `return` termina a função](../06-funcoes-e-procedimentos.md#o-return-termina-a-função).

1. Escreve a função a seguir ao `indice_do_maior`, com duas linhas em branco antes e duas depois:

   ```python
   def indice_do_primeiro_esgotado(quantidades):
       """Devolve o índice do primeiro material esgotado.

       Recebe a lista das quantidades, inteiros. Devolve um inteiro: o índice
       do primeiro material com 0 unidades, ou -1 se nenhum estiver esgotado.
       """
       for i in range(0, len(quantidades)):
           if quantidades[i] == 0:
               # Encontrado: o return devolve o índice, e a função acaba aqui.
               return i
       # Só se chega aqui depois de o ciclo ver todos os materiais.
       return -1
   ```

2. Na parte principal, troca o bloco da bandeira, do comentário `# A bandeira começa em False` até ao `print` de `Nenhum material esgotado`, por este:

   ```python
   # O -1 quer dizer que nenhum está esgotado: confirma-se antes de usar o índice.
   i_esgotado = indice_do_primeiro_esgotado(quantidades)
   if i_esgotado == -1:
       print("Nenhum material esgotado.")
   else:
       print("Primeiro material esgotado:", nomes[i_esgotado])
   ```

   Guarda e corre. O que deves ver: o ecrã da Paragem 2, com `Primeiro material esgotado: ferro`.

3. Testa a função sozinha. Junta as linhas de teste dela às outras, logo a seguir e sem linha em branco:

   ```python
   print(indice_do_primeiro_esgotado([]), "esperado: -1")
   print(indice_do_primeiro_esgotado([0]), "esperado: 0")
   print(indice_do_primeiro_esgotado([12, 30, 45, 0, 8]), "esperado: 3")
   print(indice_do_primeiro_esgotado([12, 30]), "esperado: -1")
   ```

   Guarda e corre. As quatro linhas do início batem certo. Desliga-as e guarda.

4. Provoca um erro de lógica. Na função, põe mais quatro espaços antes de `return -1`, para ele ficar com oito, alinhado com o `if`. Antes de correres, prevê o que aparece na linha do primeiro esgotado. Guarda e corre. O que deves ver, no lugar do ferro: `Nenhum material esgotado.`. Com oito espaços, o `return -1` ficou dentro do ciclo. Na 1.ª volta, os troncos não estão esgotados, e a função acaba logo com -1. Tira os quatro espaços e guarda.

### Paragem 6

O programa mostra o ecrã da Paragem 2, e o primeiro esgotado vem da função, sem bandeira nem `break`.

Pensa antes de continuares: com as quantidades da base, quantas voltas dá o ciclo da função? A resposta: quatro. Na 4.ª, encontra o 0 do ferro, e o `return i` acaba a função sem passar ao carvão, como o `break` fazia.

## Fase 7: As variáveis de uma função são locais

Confirmas que as variáveis criadas dentro de uma função não existem na parte principal. Rever: [As variáveis de uma função são locais](../06-funcoes-e-procedimentos.md#as-variáveis-de-uma-função-são-locais).

1. Acrescenta, no fim do ficheiro, esta linha provisória:

   ```python
   print(total_material)
   ```

   A variável `total_material` nasce dentro do `quantidades_dos_baus`. Antes de correres, prevê o que acontece. Guarda e corre. O que deves ver, a seguir ao armazém:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\armazem_funcoes.py", line 137, in <module>
       print(total_material)
             ^^^^^^^^^^^^^^
   NameError: name 'total_material' is not defined
   ```

   O `total_material` só existiu durante a chamada, e desapareceu quando a função acabou. Apaga a linha e guarda.

### Paragem 7

O programa mostra o ecrã da Paragem 2, sem erros.

Pensa antes de continuares: depois de `quantidades = quantidades_dos_baus(baus)`, o que fica da chamada na parte principal? A resposta: só a lista devolvida, guardada em `quantidades`. O `total_material`, a `linha` e a `unidades_bau` eram locais, e desapareceram com a chamada.

## Fase 8: Dentro da função: parâmetros, variáveis locais e constantes

A encomenda passa para uma função que lê a constante `MINIMO_ENCOMENDA`. Depois, um segundo armazém, o da mina, usa as mesmas funções, com outras listas. Rever: [Dentro da função: parâmetros, variáveis locais e constantes](../06-funcoes-e-procedimentos.md#dentro-da-função-parâmetros-variáveis-locais-e-constantes).

1. Escreve a função a seguir ao `indice_do_primeiro_esgotado`, com duas linhas em branco antes e duas depois:

   ```python
   def materiais_a_encomendar(nomes, quantidades):
       """Devolve a lista dos materiais que têm de ser encomendados.

       Recebe a lista dos nomes, textos, e a lista das quantidades, inteiros,
       com os mesmos índices. Devolve a lista dos nomes dos materiais com menos
       unidades do que MINIMO_ENCOMENDA, pela ordem das listas.
       """
       a_encomendar = []
       for i in range(0, len(quantidades)):
           if quantidades[i] < MINIMO_ENCOMENDA:
               a_encomendar.append(nomes[i])
       return a_encomendar
   ```

   A função pode ler a constante `MINIMO_ENCOMENDA` sem a receber, porque só a lê e nunca lhe dá um valor. O resto recebe-o pelos parâmetros.

2. Na parte principal, troca o bloco da encomenda, de `a_encomendar = []` até ao `print` de `A encomendar`, por esta linha:

   ```python
   print("A encomendar:", materiais_a_encomendar(nomes, quantidades))
   ```

   Guarda e corre. O que deves ver: o ecrã da Paragem 2, com `A encomendar: ['ferro', 'carvão']`.

3. Testa a função sozinha. Acrescenta as linhas de teste dela no fim das outras, sem linha em branco:

   ```python
   print(materiais_a_encomendar([], []), "esperado: []")
   print(materiais_a_encomendar(["ferro"], [10]), "esperado: []")
   print(materiais_a_encomendar(["ferro", "carvão"], [9, 30]), "esperado: ['ferro']")
   ```

   O 10 e o 9 são os dois lados do mínimo. Guarda e corre. As três linhas do início batem certo. Desliga-as e guarda.

4. Dá um título ao primeiro armazém. Logo abaixo do comentário `# A parte principal: o armazém da base.`, acrescenta:

   ```python
   print("Armazém da base")
   ```

5. Junta o armazém da mina. No fim do ficheiro, depois de uma linha em branco, acrescenta:

   ```python
   # O armazém da mina usa as mesmas funções, com outras listas.
   nomes_mina = ["pedra", "ferro", "carvão"]
   quantidades_mina = [60, 4, 15]
   # O print sem nada escreve uma linha em branco, a separar os dois armazéns.
   print()
   print("Armazém da mina")
   mostrar_armazem(nomes_mina, quantidades_mina)
   print("Total de unidades:", total_de_unidades(quantidades_mina))
   print("A encomendar:", materiais_a_encomendar(nomes_mina, quantidades_mina))
   ```

   Antes de correres, prevê o total da mina: 79, ou o 95 da base? Guarda e corre. O que deves ver: o ecrã de [O que vais construir](#o-que-vais-construir), com `Total de unidades: 79` na mina. Dentro de `total_de_unidades`, `quantidades` é o parâmetro, que nesta chamada recebeu `quantidades_mina`.

### Paragem 8

O programa mostra os dois armazéns. O ficheiro `armazem_funcoes.py` completo, como deve estar no fim:

```python
# armazem_funcoes.py: o armazém do inventário de um jogo de construção, com funções.
# Guarda os materiais e as quantidades em duas listas, com os mesmos índices.

# Abaixo deste número de unidades, um material tem de ser encomendado.
MINIMO_ENCOMENDA = 10
# O número de unidades que cabem no armazém.
CAPACIDADE = 120


def mostrar_armazem(nomes, quantidades):
    """Escreve quantos materiais há e a lista numerada dos materiais.

    Recebe a lista dos nomes dos materiais, textos, e a lista das quantidades,
    inteiros, com os mesmos índices. Não devolve nada: escreve uma linha com o
    número de materiais e uma linha por material.
    """
    print("Materiais no armazém:", len(nomes))
    # nomes[i] e quantidades[i] são do mesmo material, porque as listas têm os mesmos índices.
    for i in range(0, len(nomes)):
        print(str(i + 1) + ".", nomes[i] + ":", quantidades[i])


def total_de_unidades(quantidades):
    """Devolve a soma das unidades de todos os materiais.

    Recebe a lista das quantidades, inteiros. Devolve um inteiro: a soma,
    ou 0 se a lista estiver vazia.
    """
    total = 0
    for unidades in quantidades:
        total += unidades
    return total


def quantidades_dos_baus(baus):
    """Devolve a quantidade de cada material, somando as unidades dos baús.

    Recebe a tabela dos baús, uma lista de listas de inteiros, com uma linha
    por material e uma coluna por baú. Devolve uma lista de inteiros, com a
    soma de cada linha, pela mesma ordem, ou a lista vazia se a tabela estiver
    vazia.
    """
    quantidades = []
    for linha in baus:
        # O total volta a 0 em cada material, antes de somar os baús dele.
        total_material = 0
        for unidades_bau in linha:
            total_material += unidades_bau
        quantidades.append(total_material)
    return quantidades


def indice_do_maior(quantidades):
    """Devolve o índice do material com mais unidades.

    Recebe a lista das quantidades, inteiros, com pelo menos um elemento.
    Devolve um inteiro: o índice do maior e, num empate, o do primeiro.
    Com a lista vazia, devolve 0, que não é um índice dessa lista, por isso
    confirma antes que ela tem elementos.
    """
    i_maior = 0
    for i in range(0, len(quantidades)):
        # Com >, um empate não troca o índice: fica o primeiro.
        if quantidades[i] > quantidades[i_maior]:
            i_maior = i
    return i_maior


def indice_do_primeiro_esgotado(quantidades):
    """Devolve o índice do primeiro material esgotado.

    Recebe a lista das quantidades, inteiros. Devolve um inteiro: o índice
    do primeiro material com 0 unidades, ou -1 se nenhum estiver esgotado.
    """
    for i in range(0, len(quantidades)):
        if quantidades[i] == 0:
            # Encontrado: o return devolve o índice, e a função acaba aqui.
            return i
    # Só se chega aqui depois de o ciclo ver todos os materiais.
    return -1


def materiais_a_encomendar(nomes, quantidades):
    """Devolve a lista dos materiais que têm de ser encomendados.

    Recebe a lista dos nomes, textos, e a lista das quantidades, inteiros,
    com os mesmos índices. Devolve a lista dos nomes dos materiais com menos
    unidades do que MINIMO_ENCOMENDA, pela ordem das listas.
    """
    a_encomendar = []
    for i in range(0, len(quantidades)):
        if quantidades[i] < MINIMO_ENCOMENDA:
            a_encomendar.append(nomes[i])
    return a_encomendar


# Testes das funções sozinhas: o valor devolvido e o que se esperava.
# print(total_de_unidades([]), "esperado: 0")
# print(total_de_unidades([7]), "esperado: 7")
# print(total_de_unidades([12, 30, 45, 0, 8]), "esperado: 95")
# print(quantidades_dos_baus([]), "esperado: []")
# print(quantidades_dos_baus([[3, 4]]), "esperado: [7]")
# print(quantidades_dos_baus([[8, 4], [0, 0], [5, 3]]), "esperado: [12, 0, 8]")
# print(indice_do_maior([7]), "esperado: 0")
# print(indice_do_maior([12, 30, 45, 0, 8]), "esperado: 2")
# print(indice_do_maior([5, 9, 9]), "esperado: 1")
# print(indice_do_primeiro_esgotado([]), "esperado: -1")
# print(indice_do_primeiro_esgotado([0]), "esperado: 0")
# print(indice_do_primeiro_esgotado([12, 30, 45, 0, 8]), "esperado: 3")
# print(indice_do_primeiro_esgotado([12, 30]), "esperado: -1")
# print(materiais_a_encomendar([], []), "esperado: []")
# print(materiais_a_encomendar(["ferro"], [10]), "esperado: []")
# print(materiais_a_encomendar(["ferro", "carvão"], [9, 30]), "esperado: ['ferro']")


# A parte principal: o armazém da base.
print("Armazém da base")
nomes = ["troncos", "tábuas", "pedra", "ferro", "carvão"]
# Uma linha por material, pela ordem de nomes, e uma coluna por baú.
baus = [
    [8, 4],
    [20, 10],
    [30, 15],
    [0, 0],
    [5, 3],
]

quantidades = quantidades_dos_baus(baus)
mostrar_armazem(nomes, quantidades)

total = total_de_unidades(quantidades)
print("Total de unidades:", total)
print("Lugares livres:", CAPACIDADE - total)

# Sem materiais, não há maior: indice_do_maior precisa de pelo menos um.
if len(quantidades) == 0:
    print("O armazém está vazio.")
else:
    i_maior = indice_do_maior(quantidades)
    print("Mais unidades:", nomes[i_maior], "com", quantidades[i_maior])

# O -1 quer dizer que nenhum está esgotado: confirma-se antes de usar o índice.
i_esgotado = indice_do_primeiro_esgotado(quantidades)
if i_esgotado == -1:
    print("Nenhum material esgotado.")
else:
    print("Primeiro material esgotado:", nomes[i_esgotado])

print("A encomendar:", materiais_a_encomendar(nomes, quantidades))

# O armazém da mina usa as mesmas funções, com outras listas.
nomes_mina = ["pedra", "ferro", "carvão"]
quantidades_mina = [60, 4, 15]
# O print sem nada escreve uma linha em branco, a separar os dois armazéns.
print()
print("Armazém da mina")
mostrar_armazem(nomes_mina, quantidades_mina)
print("Total de unidades:", total_de_unidades(quantidades_mina))
print("A encomendar:", materiais_a_encomendar(nomes_mina, quantidades_mina))
```

As seis funções fazem as contas e a escrita da lista, e as cinco que calculam foram testadas sozinhas. A parte principal só guarda as listas, chama as funções e escreve os resultados, uma vez para cada armazém.

Pensa antes de terminares: imagina que o cabeçalho era `def total_de_unidades(lista):` e o corpo continuava com `for unidades in quantidades:`. Que total mostrava a mina? A resposta: 95, o total da base, sem nenhuma mensagem. O ciclo percorria a lista `quantidades` da parte principal, e não a que a função recebeu. É por isso que uma função usa sempre os seus parâmetros.

## Se alguma coisa falhar

1. Guardaste as alterações? Só corre o que está guardado.
2. O terminal está na pasta certa? O caminho escrito antes do `>` ou do `%` tem de acabar em `lp-python`.
3. Estás a correr o `armazem_funcoes.py`, e não o `armazem.py` do laboratório 05?
4. A tua mensagem tem outras palavras, ou não tem os sinais por baixo da linha? Noutras versões do Python, o nome do erro é o mesmo. Se o número da linha for outro, procura a linha pelo texto que a mensagem mostra.

### `NameError: name 'mostrar_armazem' is not defined`

A chamada ficou antes do `def`. As funções ficam todas em cima, por baixo das constantes, e a parte principal fica no fim do ficheiro. O mesmo vale para as outras funções.

### `IndentationError: expected an indented block after function definition`

O corpo da função não tem os quatro espaços. Todas as linhas do corpo, também a docstring, ficam quatro espaços para dentro do `def`.

### Aparecem as linhas de teste antes do armazém

Ficou uma linha de teste ligada. Seleciona as linhas que começam por `print(` e têm `esperado` e desliga-as com `Toggle Line Comment`, no menu Edit.

### `TypeError: 'NoneType' object is not subscriptable` ou `None` no ecrã

Uma função que devia devolver um valor chegou ao fim sem `return`. Confirma que cada função que calcula acaba com o seu `return`, com quatro espaços, alinhado com o primeiro `for`.

### `TypeError: ... missing 1 required positional argument`

Falta um argumento na chamada que a mensagem aponta. Compara a chamada com o cabeçalho da função: cada parâmetro precisa do seu argumento, pela mesma ordem.

### O armazém diz `Nenhum material esgotado.` com o ferro a 0

O `return -1` ficou dentro do ciclo. Tem de ter quatro espaços, alinhado com o `for`, para só correr depois de o ciclo ver todos os materiais.

## Desafios

1. O material com menos unidades. Escreve uma função `indice_do_menor(quantidades)`, com a sua docstring e as suas linhas de teste. Usa-a para mostrar, nos dois armazéns, o material com menos unidades, como `Menos unidades: ferro com 0`. Pista: parte do `indice_do_maior`, e pensa no que muda no `if`.

2. A entrega. Depois de calcular as quantidades da base, e antes de as mostrar, o programa pergunta que material chegou e quantas unidades. Soma-as à quantidade desse material. Se o material não estiver em `nomes`, aparece `Esse material não existe no armazém.`, e nada muda. Escreve uma função `indice_do_material(nomes, material)`, que devolve a posição do material ou -1. Testa o programa com 20 de ferro e com areia. Pista: a função não lê do teclado; quem pergunta é a parte principal.

3. O resumo de um armazém. Escreve um procedimento `mostrar_resumo(titulo, nomes, quantidades)`, que escreve o título e todas as linhas que a base mostra hoje. A mina passa a mostrar as mesmas linhas. A parte principal fica com as listas, a conta das quantidades da base e uma chamada por armazém. Pista: um procedimento também pode chamar outras funções, como o `mostrar_equipa` do [exemplo guiado do guia](../06-funcoes-e-procedimentos.md#passo-6-o-procedimento-e-a-parte-principal).

## Antes de terminares

- [ ] O `armazem_funcoes.py` mostra os dois armazéns, como em "O que vais construir".
- [ ] As seis funções têm a sua docstring, e as cinco que calculam têm linhas de teste, desligadas com `#`.
- [ ] A parte principal fica no fim do ficheiro e não tem nenhum ciclo.

![Rodapé](../../imagens/rodape.png)
