![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Ciclo while

## O que vais construir

Vais construir o `recolha.py`, o registo das idas à floresta no inventário de um jogo de construção. Em cada viagem, o jogador traz troncos, e o programa lê os de cada viagem até se escrever 0. No fim, mostra as viagens e os troncos e converte os troncos que escolheres em tábuas, a 4 tábuas por tronco. Com três viagens, de 12, 5 e 10 troncos, e 20 troncos para converter, o ecrã fica assim:

```text
Troncos desta viagem (0 para terminar)? 12
Troncos desta viagem (0 para terminar)? 5
Troncos desta viagem (0 para terminar)? 10
Troncos desta viagem (0 para terminar)? 0
Viagens: 3
Viagens grandes: 2
Troncos recolhidos: 27
Troncos por viagem, em média: 9.0
Quantos troncos queres converter em tábuas? 20
Tábuas feitas: 80
Troncos que ficam: 7
```

1. [Fase 1: Ler até à sentinela](#fase-1-ler-até-à-sentinela)
2. [Fase 2: O ciclo que nunca acaba, e o Ctrl+C](#fase-2-o-ciclo-que-nunca-acaba-e-o-ctrlc)
3. [Fase 3: O contador e o acumulador](#fase-3-o-contador-e-o-acumulador)
4. [Fase 4: Ver as voltas com linhas de observação](#fase-4-ver-as-voltas-com-linhas-de-observação)
5. [Fase 5: Contar só algumas voltas](#fase-5-contar-só-algumas-voltas)
6. [Fase 6: A média, só quando há valores](#fase-6-a-média-só-quando-há-valores)
7. [Fase 7: A validação repetida pede o valor outra vez](#fase-7-a-validação-repetida-pede-o-valor-outra-vez)

## O que precisas

- A pasta `lp-python` aberta no VS Code, e um terminal dentro dela, que se abre no menu Terminal, com a opção New Terminal.
- O comando que corre o Python no teu computador: `python`, `py` ou `python3`. Neste laboratório aparece `python`, e trocas pelo teu se for outro.

O `recolha.py` é um programa novo, e não precisas dos ficheiros dos laboratórios anteriores.

## Fase 1: Ler até à sentinela

O programa lê os troncos de cada viagem com um `while`, até aparecer o 0, a sentinela, e por agora só conta as viagens. Nenhuma viagem volta da floresta sem troncos, e por isso o 0 pode querer dizer "acabou". Rever: [Ler até à sentinela](../04-ciclo-while.md#ler-até-à-sentinela).

1. Cria `recolha.py` na pasta `lp-python`, com esta primeira versão:

   ```python
   # recolha.py: as viagens à floresta do inventário de um jogo de construção.
   # Lê os troncos de cada viagem até ao 0.

   # O valor que diz que acabaram as viagens.
   SENTINELA = 0

   viagens = 0
   troncos = int(input("Troncos desta viagem (0 para terminar)? "))
   while troncos != SENTINELA:
       viagens += 1
       # Ler o valor seguinte é a atualização: sem esta linha, o ciclo nunca acabava.
       troncos = int(input("Troncos desta viagem (0 para terminar)? "))
   print("Viagens:", viagens)
   ```

   O `viagens += 1` soma 1 às viagens, com a forma curta do guia ([A forma curta da atualização: `+=`](../04-ciclo-while.md#a-forma-curta-da-atualização-)). O `print` do fim fica encostado à margem.

2. Vais testar zero viagens, uma e várias. Antes de correres, prevê quantas voltas dá o ciclo em cada caso. Guarda e corre o programa uma vez por caso:

   ```bash
   python recolha.py
   ```

   A resposta:

   | Valores escritos, por ordem | Voltas | A última linha |
   | --- | ---: | --- |
   | 0 | 0 | `Viagens: 0` |
   | 7, 0 | 1 | `Viagens: 1` |
   | 12, 5, 10, 0 | 3 | `Viagens: 3` |

   O que deves ver, no último caso:

   ```text
   Troncos desta viagem (0 para terminar)? 12
   Troncos desta viagem (0 para terminar)? 5
   Troncos desta viagem (0 para terminar)? 10
   Troncos desta viagem (0 para terminar)? 0
   Viagens: 3
   ```

   O 0 termina o ciclo e nunca é contado. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

### Paragem 1

O `recolha.py` lê os troncos de cada viagem até ao 0 e conta as viagens.

Pensa antes de continuares: e se uma viagem pudesse voltar sem troncos? A resposta: o 0 passava a ser um dado verdadeiro. A sentinela teria de ser outro valor, que nenhuma viagem pode ter, como o -1 das partidas do guia.

## Fase 2: O ciclo que nunca acaba, e o Ctrl+C

Tiras de propósito a atualização, para veres um ciclo que nunca acaba e o parares com Ctrl+C. Sem a leitura do fim do corpo, `troncos` nunca muda, e a condição dá sempre `True`. Rever: [O ciclo que nunca acaba, e o Ctrl+C](../04-ciclo-while.md#o-ciclo-que-nunca-acaba-e-o-ctrlc).

1. Na linha 12, a leitura do fim do corpo, escreve um `#` logo antes de `troncos`, e deixa os quatro espaços antes do `#`. A linha passa a comentário e deixa de correr. Guarda, corre e escreve `7`.

   O que deves ver: depois do 7, não aparece mais nada, e o terminal não fica pronto para outro comando. O programa está a dar voltas sem parar, muito depressa, sem escrever nada.

2. Para o programa. Clica dentro do terminal e carrega em Ctrl+C: segura a tecla Ctrl e carrega na tecla C. No macOS, a tecla é a Control, e não a Cmd. O que deves ver no fim do ecrã é parecido com isto:

   ```text
   Troncos desta viagem (0 para terminar)? 7
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\recolha.py", line 10, in <module>
       viagens += 1
       ^^^^^^^
   KeyboardInterrupt
   ```

   O programa parou. Nalguns terminais, aparece também `^C` antes de `Traceback`.

3. Tira o `#` que escreveste, guarda e corre com `7` e `0`. O que deves ver: `Viagens: 1`. O programa volta a terminar.

### Paragem 2

O `recolha.py` voltou a ler até ao 0, e sabes parar um programa que não acaba.

Pensa antes de continuares: com a linha 12 em comentário, o que acontecia se escrevesses logo `0`? A resposta: o programa terminava com `Viagens: 0`. O ciclo dava zero voltas, e a linha que faltava nunca era precisa.

## Fase 3: O contador e o acumulador

O programa passa a somar os troncos de todas as viagens. A variável `viagens` é um contador, e o acumulador `total_troncos` soma o valor de cada volta, com `+=`. Rever: [O contador e o acumulador](../04-ciclo-while.md#o-contador-e-o-acumulador).

1. O acumulador começa antes do ciclo, a 0. A seguir à linha `viagens = 0`, acrescenta:

   ```python
   total_troncos = 0
   ```

2. Cada volta soma os troncos desta viagem, antes de ler os da seguinte. A seguir à linha `viagens += 1`, acrescenta, com os mesmos quatro espaços:

   ```python fragment uma linha do corpo do while, com os quatro espaços
       total_troncos += troncos
   ```

3. No fim do ficheiro, encostado à margem, acrescenta:

   ```python
   print("Troncos recolhidos:", total_troncos)
   ```

4. Guarda e corre com as três viagens, 12, 5, 10 e 0. O que deves ver no fim:

   ```text
   Viagens: 3
   Troncos recolhidos: 27
   ```

   Corre também com o 0 logo à primeira. O que deves ver: `Viagens: 0` e `Troncos recolhidos: 0`. Sem viagens, os dois ficam com o valor com que começaram.

### Paragem 3

O `recolha.py` conta as viagens e soma os troncos.

Pensa antes de continuares: com uma só viagem, de 7 troncos, que valor fica no contador e no acumulador? A resposta: 1 e 7. O contador soma sempre 1, e o acumulador soma o próprio valor.

## Fase 4: Ver as voltas com linhas de observação

Prevês a tabela de iterações de um caso e confirma-la no computador. As linhas de observação são `print` provisórios que mostram as variáveis, e escrevem a tabela observada. Rever: [Ver as voltas com linhas de observação](../04-ciclo-while.md#ver-as-voltas-com-linhas-de-observação).

1. Prevê a tabela de iterações para 12, 5, 10 e 0, com uma linha por cada teste da condição e os valores nesse momento. A resposta:

   | Teste | `troncos` | `viagens` | `total_troncos` | Condição |
   | --- | ---: | ---: | ---: | --- |
   | 1.º | 12 | 0 | 0 | `12 != 0` dá `True` |
   | 2.º | 5 | 1 | 12 | `5 != 0` dá `True` |
   | 3.º | 10 | 2 | 17 | `10 != 0` dá `True` |
   | 4.º | 0 | 3 | 27 | `0 != 0` dá `False` |

2. Põe o cursor no fim da linha do `while`, carrega em Enter e escreve, com os quatro espaços que o VS Code já pôs:

   ```python fragment duas linhas do corpo do while, com os quatro espaços
       # Linha de observação: tira-a quando acabares de ver as voltas.
       print("(observação) troncos =", troncos, "viagens =", viagens, "total =", total_troncos)
   ```

3. Logo a seguir ao ciclo, antes de `print("Viagens:", viagens)`, acrescenta, encostado à margem:

   ```python
   # Linha de observação: o estado no teste que deu False.
   print("(observação) troncos =", troncos, "viagens =", viagens, "total =", total_troncos)
   ```

4. Guarda, corre e escreve 12, 5, 10 e 0. O que deves ver:

   ```text
   Troncos desta viagem (0 para terminar)? 12
   (observação) troncos = 12 viagens = 0 total = 0
   Troncos desta viagem (0 para terminar)? 5
   (observação) troncos = 5 viagens = 1 total = 12
   Troncos desta viagem (0 para terminar)? 10
   (observação) troncos = 10 viagens = 2 total = 17
   Troncos desta viagem (0 para terminar)? 0
   (observação) troncos = 0 viagens = 3 total = 27
   Viagens: 3
   Troncos recolhidos: 27
   ```

   As quatro linhas de observação são a tabela observada. São iguais às da tabela prevista, linha a linha.

5. Provoca um erro de propósito. Apaga a linha `total_troncos += troncos` e escreve-a outra vez no fim do corpo, por baixo da leitura do valor seguinte, com quatro espaços. Guarda, corre e escreve os mesmos valores. O que deves ver:

   ```text
   Troncos desta viagem (0 para terminar)? 12
   (observação) troncos = 12 viagens = 0 total = 0
   Troncos desta viagem (0 para terminar)? 5
   (observação) troncos = 5 viagens = 1 total = 5
   Troncos desta viagem (0 para terminar)? 10
   (observação) troncos = 10 viagens = 2 total = 15
   Troncos desta viagem (0 para terminar)? 0
   (observação) troncos = 0 viagens = 3 total = 15
   Viagens: 3
   Troncos recolhidos: 15
   ```

   Não há mensagem de erro, e o total devia ser 27. A primeira linha diferente da tabela prevista é a do 2.º teste, com o total a 5, e não a 12. A soma passou a usar os troncos da viagem seguinte: o 12 nunca foi somado, e o 0 foi. Volta a pôr a linha logo a seguir a `viagens += 1`.

6. Apaga as duas linhas de observação e os comentários delas. Guarda e corre outra vez com as três viagens. O que deves ver: `Viagens: 3` e `Troncos recolhidos: 27`, sem nenhuma linha de observação.

### Paragem 4

As linhas de observação já saíram, e a tabela observada coincidiu com a prevista. O ficheiro `recolha.py` completo, como deve estar agora:

```python
# recolha.py: as viagens à floresta do inventário de um jogo de construção.
# Lê os troncos de cada viagem até ao 0.

# O valor que diz que acabaram as viagens.
SENTINELA = 0

viagens = 0
total_troncos = 0
troncos = int(input("Troncos desta viagem (0 para terminar)? "))
while troncos != SENTINELA:
    viagens += 1
    total_troncos += troncos
    # Ler o valor seguinte é a atualização: sem esta linha, o ciclo nunca acabava.
    troncos = int(input("Troncos desta viagem (0 para terminar)? "))
print("Viagens:", viagens)
print("Troncos recolhidos:", total_troncos)
```

O contador e o acumulador começam antes do ciclo, e o corpo trata uma viagem de cada vez. Os resultados vêm depois do ciclo, encostados à margem.

Pensa antes de continuares: com a soma no sítio errado, o caso de uma só viagem, 7 e 0, dava o total certo? A resposta: não, dava 0. Somava só o 0 da sentinela, e o 7 ficava de fora.

## Fase 5: Contar só algumas voltas

O programa passa a contar as viagens grandes, as que trazem 10 troncos ou mais. Este contador só aumenta nas voltas em que a condição de um `if` dá `True`. Rever: [Contar só algumas voltas](../04-ciclo-while.md#contar-só-algumas-voltas).

1. A regra das viagens grandes é uma constante. A seguir à linha `SENTINELA = 0`, acrescenta:

   ```python
   # O número de troncos a partir do qual uma viagem é grande.
   VIAGEM_GRANDE = 10
   ```

2. O contador novo começa antes do ciclo. A seguir à linha `total_troncos = 0`, acrescenta:

   ```python
   viagens_grandes = 0
   ```

3. No corpo do ciclo, a seguir a `total_troncos += troncos`, acrescenta estas linhas, com a indentação que mostram:

   ```python fragment duas linhas do corpo do while, com o if lá dentro
       if troncos >= VIAGEM_GRANDE:
           viagens_grandes += 1
   ```

   A linha do aumento fica com oito espaços, porque está dentro do `if`, que está dentro do `while`.

4. A seguir a `print("Viagens:", viagens)`, acrescenta:

   ```python
   print("Viagens grandes:", viagens_grandes)
   ```

5. Antes de correres, prevê: com 12, 5, 10 e 0, a viagem de 10 troncos conta como grande? Guarda, corre e confirma. O que deves ver no fim:

   ```text
   Viagens: 3
   Viagens grandes: 2
   Troncos recolhidos: 27
   ```

   Conta: a condição usa `>=`, e `10 >= 10` dá `True`. As viagens grandes são a de 12 e a de 10.

6. Provoca um erro de propósito. Na linha da leitura do fim do corpo, a do `input`, acrescenta quatro espaços no início, para ficar com oito, alinhada com `viagens_grandes += 1`. Guarda, corre e escreve 12 e depois 5.

   O que deves ver: depois do 5, não aparece mais nada. A leitura passou para dentro do `if`, e uma viagem pequena já não lê o valor seguinte. Carrega em Ctrl+C e tira os quatro espaços que puseste. Guarda e corre com 12, 5, 10 e 0, para confirmares as três linhas do passo 5.

### Paragem 5

O `recolha.py` conta as viagens, as viagens grandes e os troncos. O corpo conta, soma e, só às vezes, conta uma viagem grande, e a leitura do fim do corpo voltou aos quatro espaços.

Pensa antes de continuares: com 9, 9, 9 e 0, quantas viagens grandes há? A resposta: nenhuma. Nenhuma viagem chega aos 10 troncos, mesmo com 27 troncos ao todo.

## Fase 6: A média, só quando há valores

O programa passa a mostrar a média de troncos por viagem. Sem viagens, a conta seria 0 a dividir por 0, e por isso a média vai ficar dentro de um `if`. Rever: [A média, só quando há valores](../04-ciclo-while.md#a-média-só-quando-há-valores).

1. Experimenta primeiro sem o `if`. No fim do ficheiro, acrescenta:

   ```python
   media = total_troncos / viagens
   print("Troncos por viagem, em média:", media)
   ```

   Guarda e corre com as viagens de sempre, 12, 5, 10 e 0. O que deves ver na última linha: `Troncos por viagem, em média: 9.0`.

2. Provoca o erro do dia sem viagens. Corre com o 0 logo à primeira. O que deves ver:

   ```text
   Troncos desta viagem (0 para terminar)? 0
   Viagens: 0
   Viagens grandes: 0
   Troncos recolhidos: 0
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\recolha.py", line 23, in <module>
       media = total_troncos / viagens
               ~~~~~~~~~~~~~~^~~~~~~~~
   ZeroDivisionError: division by zero
   ```

   É um erro de execução: as três linhas dos resultados apareceram, e o programa parou na divisão por zero.

3. Substitui as duas linhas que acrescentaste no passo 1 por estas:

   ```python
   # Sem este if, sem viagens, a conta seria 0 / 0 e o programa parava.
   if viagens > 0:
       media = total_troncos / viagens
       print("Troncos por viagem, em média:", media)
   else:
       print("Não houve viagens, por isso não há média.")
   ```

4. Guarda e corre o programa uma vez por caso. O que deves ver na última linha:

   | Valores escritos | A última linha |
   | --- | --- |
   | 0 | `Não houve viagens, por isso não há média.` |
   | 7, 0 | `Troncos por viagem, em média: 7.0` |
   | 12, 5, 10, 0 | `Troncos por viagem, em média: 9.0` |

   O caso sem viagens passa pelo `else`, e os outros dois pelo `if`, com uma volta e com várias.

### Paragem 6

O `recolha.py` mostra a média só quando houve viagens, e o dia sem viagens já não para o programa.

Pensa antes de continuares: porque é que o `if` da média fica encostado à margem, e não dentro do ciclo? A resposta: dentro do ciclo, calculava e escrevia uma média em cada volta, com a contagem a meio. Depois do ciclo, corre uma vez, com tudo contado.

## Fase 7: A validação repetida pede o valor outra vez

No fim, o programa pergunta quantos troncos queres converter em tábuas, e só aceita de 0 até aos troncos que tens. Enquanto o número estiver fora desse intervalo, o `while` volta a pedi-lo. Rever: [A validação repetida pede o valor outra vez](../04-ciclo-while.md#a-validação-repetida-pede-o-valor-outra-vez).

1. Cada tronco dá 4 tábuas, e essa regra é mais uma constante. A seguir à linha `VIAGEM_GRANDE = 10`, acrescenta:

   ```python
   # As tábuas que cada tronco dá.
   TABUAS_POR_TRONCO = 4
   ```

2. O programa passa a fazer mais uma coisa, e o comentário do início deve dizê-lo. Troca a segunda linha do ficheiro por esta:

   ```python
   # Lê os troncos de cada viagem até ao 0, e no fim converte troncos em tábuas.
   ```

3. No fim do ficheiro, depois do `else` da média, deixa uma linha em branco e acrescenta, encostado à margem, a pergunta e a validação:

   ```python
   converter = int(input("Quantos troncos queres converter em tábuas? "))
   # Enquanto o número estiver fora de 0 a total_troncos, pede-se outra vez.
   while converter < 0 or converter > total_troncos:
       converter = int(input("Número inválido. Escreve de 0 a " + str(total_troncos) + ": "))
   ```

   A pergunta repetida junta o número de troncos ao texto, com `+` e `str`, como no tema 02.

4. A seguir à validação, encostado à margem, acrescenta as contas da conversão:

   ```python
   tabuas = converter * TABUAS_POR_TRONCO
   print("Tábuas feitas:", tabuas)
   print("Troncos que ficam:", total_troncos - converter)
   ```

5. Guarda e corre. Escreve as três viagens e o 0, e na pergunta da conversão escreve 30, depois -2 e depois 20. O fim do ecrã deve ser este:

   ```text
   Troncos por viagem, em média: 9.0
   Quantos troncos queres converter em tábuas? 30
   Número inválido. Escreve de 0 a 27: -2
   Número inválido. Escreve de 0 a 27: 20
   Tábuas feitas: 80
   Troncos que ficam: 7
   ```

   O 30 e o -2 foram recusados, um de cada lado do intervalo, e o 20 foi aceite à terceira pergunta.

6. Experimenta as fronteiras, com as mesmas viagens. Com 27, todos os troncos, deves ver `Tábuas feitas: 108` e `Troncos que ficam: 0`. Com 28, a pergunta repete-se, e acabas com um número válido. Com 0, deves ver `Tábuas feitas: 0` e `Troncos que ficam: 27`.

7. Provoca um erro de propósito. Na linha do `while` da validação, escreve a condição de um número válido: `while converter >= 0 and converter <= total_troncos:`. Antes de correres, prevê o que acontece com 20. Guarda, corre com 12, 5, 10 e 0, e escreve 20 e depois 30.

   O que deves ver: o 20 é recusado, e o 30 é aceite, com `Tábuas feitas: 120` e `Troncos que ficam: -3`. O ciclo continua enquanto a condição dá `True`, e por isso a sua condição tem de descrever um número inválido. Volta a pôr `while converter < 0 or converter > total_troncos:`, guarda e corre com 20, para confirmares `Tábuas feitas: 80`.

### Paragem 7

O `recolha.py` está completo. O ficheiro, como deve estar agora:

```python
# recolha.py: as viagens à floresta do inventário de um jogo de construção.
# Lê os troncos de cada viagem até ao 0, e no fim converte troncos em tábuas.

# O valor que diz que acabaram as viagens.
SENTINELA = 0
# O número de troncos a partir do qual uma viagem é grande.
VIAGEM_GRANDE = 10
# As tábuas que cada tronco dá.
TABUAS_POR_TRONCO = 4

viagens = 0
total_troncos = 0
viagens_grandes = 0
troncos = int(input("Troncos desta viagem (0 para terminar)? "))
while troncos != SENTINELA:
    viagens += 1
    total_troncos += troncos
    if troncos >= VIAGEM_GRANDE:
        viagens_grandes += 1
    # Ler o valor seguinte é a atualização: sem esta linha, o ciclo nunca acabava.
    troncos = int(input("Troncos desta viagem (0 para terminar)? "))
print("Viagens:", viagens)
print("Viagens grandes:", viagens_grandes)
print("Troncos recolhidos:", total_troncos)
# Sem este if, sem viagens, a conta seria 0 / 0 e o programa parava.
if viagens > 0:
    media = total_troncos / viagens
    print("Troncos por viagem, em média:", media)
else:
    print("Não houve viagens, por isso não há média.")

converter = int(input("Quantos troncos queres converter em tábuas? "))
# Enquanto o número estiver fora de 0 a total_troncos, pede-se outra vez.
while converter < 0 or converter > total_troncos:
    converter = int(input("Número inválido. Escreve de 0 a " + str(total_troncos) + ": "))
tabuas = converter * TABUAS_POR_TRONCO
print("Tábuas feitas:", tabuas)
print("Troncos que ficam:", total_troncos - converter)
```

O programa tem dois ciclos, um a seguir ao outro. O primeiro junta as viagens até ao 0, e o segundo só deixa passar um número de troncos que existe.

Corre-o uma última vez com o caso sem viagens: escreve 0, e na conversão escreve 5 e depois 0. A pergunta repetida diz `Número inválido. Escreve de 0 a 0:`, e no fim aparecem `Tábuas feitas: 0` e `Troncos que ficam: 0`.

Pensa antes de terminares: porque é que a validação não podia vir antes do primeiro ciclo? A resposta: o limite da validação é o total de troncos, e esse total só se sabe depois de o primeiro ciclo terminar.

## Se alguma coisa falhar

1. O ficheiro está guardado? O Python corre a versão guardada, e não a que vês no editor.
2. O caminho que aparece antes do cursor, no terminal, acaba em `lp-python`? Se não acabar, abre outro terminal, no menu Terminal, com a opção New Terminal.
3. A linha começa por `>>>`? Estás na consola do Python: escreve `exit()` e carrega em Enter.
4. A tua mensagem não é igual à do laboratório? As mensagens daqui são as do Python 3.14. Noutra versão, as palavras e os sinais por baixo da linha podem mudar, e o caminho do ficheiro é outro em cada computador.

### O programa não termina

Olha para o cursor. À frente de uma pergunta, o programa está à espera da tua resposta. Numa linha vazia, é um ciclo que não acaba: carrega em Ctrl+C. Depois, procura a leitura do fim do corpo, que falta ou ficou dentro do `if`.

### O Ctrl+C não para o programa

Clica primeiro dentro do terminal, para ele ficar com o cursor. No Windows, se houver texto selecionado no terminal, o Ctrl+C copia-o: clica no terminal, sem arrastar, e carrega outra vez.

### `ValueError: invalid literal for int() with base 10: ''`

Carregaste em Enter sem escrever nada. A mesma mensagem, com outro texto no fim, aparece quando escreves uma letra ou um número com casas decimais. Corre outra vez e escreve só números inteiros.

### Escreves 0 e o programa continua a perguntar

A leitura do fim do corpo ficou sem o `int`. O 0 fica guardado como o texto `"0"`, que é diferente do número 0, e a condição continua a dar `True`.

### `TypeError: unsupported operand type(s) for +=: 'int' and 'str'`

Uma das leituras dos troncos ficou sem o `int`, e o `+=` não soma um texto a um número. A mensagem aponta a linha da soma, mas a causa está na leitura.

### `ZeroDivisionError: division by zero`

A divisão da média não está dentro do `if viagens > 0:`. Confirma que as duas linhas da média têm quatro espaços, por baixo do `if`.

### Os resultados aparecem várias vezes

Um `print` dos resultados ficou com quatro espaços, dentro do ciclo. Os `print` dos resultados ficam encostados à margem.

## Desafios

1. Os baús. Cada baú gasta 8 tábuas. No fim, o programa diz também quantos baús constróis com as tábuas feitas e quantas tábuas sobram. Com 20 troncos convertidos, são 10 baús e sobram 0 tábuas; com 5, são 2 baús e sobram 4. Pista: as contas dos baús são as do laboratório do tema 02.

2. A mochila. A mochila do jogador leva no máximo 20 troncos, e um número maior, ou negativo, é um engano. Quando isso acontece, o programa volta a perguntar os troncos daquela viagem. Com 12, 25, 5, -3, 10 e 0, o 25 e o -3 são recusados, e no fim aparecem 3 viagens e 27 troncos. Testa-o também com 25 logo à primeira, e depois 7 e 0. Pista: os troncos leem-se em dois sítios, e os dois precisam da validação.

3. A meta. O jogador quer juntar 25 troncos. Depois do ciclo, o programa escreve em que viagem atingiu a meta, como `Meta atingida na viagem 3.`, ou quantos troncos faltam, como `Faltam 13 troncos para a meta.`. Testa-o com 12, 5, 10 e 0, com 30, 4 e 0, com 12 e 0, e com o 0 logo à primeira. Pista: a viagem da meta descobre-se dentro do ciclo, na primeira volta em que o total chega aos 25.

## Antes de terminares

- [ ] O `recolha.py` lê os troncos de cada viagem até ao 0 e mostra as viagens, as viagens grandes, os troncos e a média.
- [ ] Correste os três casos da fase 6, sem viagens, com uma e com várias, e cada um deu a última linha da tabela.
- [ ] As linhas de observação já saíram do programa.
- [ ] A conversão só aceita um número de troncos de 0 até ao total, e calcula as tábuas com a constante `TABUAS_POR_TRONCO`.

![Rodapé](../../imagens/rodape.png)
