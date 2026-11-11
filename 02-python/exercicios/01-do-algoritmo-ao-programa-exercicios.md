![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Do algoritmo ao programa

Praticas a passagem de um algoritmo para Python, os três tipos de erro e a depuração com método. Praticas também as fases do ciclo de vida e a escolha da ferramenta. Os exercícios 1 a 6 são obrigatórios. Trabalha na tua pasta `lp-python`, com o comando do teu registo da execução, e escreve as respostas em comentários, com `#`. Para rever: o [guia do tema](../01-do-algoritmo-ao-programa.md) e o [laboratório](../laboratorios/01-do-algoritmo-ao-programa-laboratorio.md).

## Exercício 1: Prever o ecrã

Este programa mostra o marcador de um jogo de basquetebol da escola:

```python
# marcador.py: o marcador de um jogo de basquetebol da escola.
print("JOGO #3")
print("Casa contra visitantes")
print("Marcador: 0 a 0")
```

Sem correres o programa, prevê o que aparece no ecrã, linha a linha. Depois cria o `marcador.py` com este conteúdo e confirma. Para cada linha do ecrã em que te enganaste, explica porquê num comentário, no fim da linha do programa a que diz respeito. Se acertaste em todas, diz isso num comentário.

Rever: [Do `Escreve:` ao `print`](../01-do-algoritmo-ao-programa.md#do-escreve-ao-print).

<details>
<summary>Pista</summary>

Lê cada linha como o interpretador a leria, de cima para baixo.

</details>

## Exercício 2: Do pseudocódigo ao programa

Um colega escreveu o algoritmo do menu de um jogo. Na segunda linha, escreveu uma frase clara, como se aceitava na algoritmia:

```text
Escreve: "MENU PRINCIPAL"
Escreve as três opções, numeradas de 1 a 3, uma por linha: Jogar, Ver as regras e Sair
Escreve: "Escolhe uma opção."
```

Passa o algoritmo para Python, no ficheiro `menu.py`, com o comentário no início. O programa escreve o ecrã que o algoritmo descreve, com as três opções numeradas, uma por linha. A forma da numeração decides tu.

Rever: [Do `Escreve:` ao `print`](../01-do-algoritmo-ao-programa.md#do-escreve-ao-print).

<details>
<summary>Pista</summary>

Decide primeiro o resultado esperado, linha a linha.

</details>

## Exercício 3: Que tipo de erro?

Uma colega escreveu o anúncio do campeonato de matraquilhos da escola. O resultado esperado é este:

```text
CAMPEONATO DA ESCOLA
Matraquilhos
Equipas de dois jogadores.
```

Fez três versões, e nenhuma dá o resultado esperado. Para cada uma, diz que tipo de erro é, em que linha está e como o soubeste, e como se corrige. Escreve as respostas num ficheiro `erros.py`, só com comentários, com uma parte para cada versão.

Versão A:

```python fragment erro de propósito: o exercício pede que o aluno o encontre
# campeonato.py: o anúncio do campeonato de matraquilhos da escola.
print("CAMPEONATO DA ESCOLA")
print("Matraquilhos")
print("Equipas de dois jogadores."
```

```text
  File "C:\Users\aluno\Documents\lp-python\campeonato.py", line 4
    print("Equipas de dois jogadores."
         ^
SyntaxError: '(' was never closed
```

Versão B:

```python
# campeonato.py: o anúncio do campeonato de matraquilhos da escola.
print("CAMPEONATO DA ESCOLA")
print(Matraquilhos)
print("Equipas de dois jogadores.")
```

```text
CAMPEONATO DA ESCOLA
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\campeonato.py", line 3, in <module>
    print(Matraquilhos)
          ^^^^^^^^^^^^
NameError: name 'Matraquilhos' is not defined
```

Versão C:

```python
# campeonato.py: o anúncio do campeonato de matraquilhos da escola.
print("CAMPEONATO DA ESCOLA")
# print("Matraquilhos")
print("Equipas de dois jogadores.")
```

```text
CAMPEONATO DA ESCOLA
Equipas de dois jogadores.
```

Rever: [Os três tipos de erro](../01-do-algoritmo-ao-programa.md#os-três-tipos-de-erro).

<details>
<summary>Pista</summary>

Para cada versão, olha primeiro para o que apareceu. Correu alguma linha? Há mensagem? Depois lê a última linha da mensagem, se a houver: `never closed` quer dizer "nunca foi fechado".

</details>

## Exercício 4: Encontrar e corrigir o erro com método

Este programa devia mostrar o horário das finais de um torneio de jogos de computador. Cria o `horario.py`, copia para ele este conteúdo, exatamente como está, e corre-o:

```python fragment erro de propósito: o exercício pede que o aluno o encontre
# horario.py: o horário das finais de um torneio de jogos de computador.
print("FINAIS DO TORNEIO")
print("Meias-finais às 14h00.")
 print("Final às 16h00.")
print("Entrega dos prémios às 17h00.")
```

O resultado esperado é este:

```text
FINAIS DO TORNEIO
Meias-finais às 14h00.
Final às 16h00.
Entrega dos prémios às 17h00.
```

Corrige-o até dar o resultado esperado, depurando com método. Escreve os cinco passos num comentário no fim do `horario.py`. São o esperado, o obtido e o tipo de erro; a hipótese; o que a confirmou; o que mudaste; e o que apareceu depois.

Rever: [Depurar com método, agora no computador](../01-do-algoritmo-ao-programa.md#depurar-com-método-agora-no-computador), [As regras de escrita do Python](../01-do-algoritmo-ao-programa.md#as-regras-de-escrita-do-python) e [Os três tipos de erro](../01-do-algoritmo-ao-programa.md#os-três-tipos-de-erro).

<details>
<summary>Pista</summary>

Traduz as palavras da última linha da mensagem: `unexpected` quer dizer inesperado, e `indent` quer dizer indentação.

</details>

## Exercício 5: As fases do ciclo de vida

A Rita fez o ecrã de abertura de um jogo de memória, que um colega lhe pediu. Estas são as coisas que ela fez, fora de ordem:

- A. Correu o programa e comparou o que apareceu com o resultado esperado.
- B. Escreveu o algoritmo em pseudocódigo, com um `Escreve:` por linha.
- C. Leu o pedido do colega e escreveu o resultado esperado, linha a linha.
- D. Passou o algoritmo para Python, no ficheiro `memoria.py`.
- E. Um mês depois, acrescentou uma regra nova que o colega lhe pediu.
- F. Viu que faltava uma linha e acrescentou o `print` que faltava.

Num ficheiro `fases.py`, só com comentários, escreve as letras pela ordem em que a Rita as fez, uma por linha. Ao lado de cada letra, escreve a fase do ciclo de vida a que pertence.

Rever: [O ciclo de vida de um programa](../01-do-algoritmo-ao-programa.md#o-ciclo-de-vida-de-um-programa).

<details>
<summary>Pista</summary>

Começa pela coisa que se faz antes de haver código. Depois procura a que se faz quando o programa já está em uso.

</details>

## Exercício 6: Onde se programa, certo ou errado

Quatro colegas disseram estas frases na sala. Para cada uma, diz se está certa ou errada, e porquê, numa ou duas frases. Se estiver errada, diz o que farias tu. Escreve as respostas num ficheiro `ferramentas.py`, só com comentários.

1. A Beatriz: "Abri o meu `ola.py` no Bloco de Notas e as cores desapareceram todas. O ficheiro estragou-se."
2. A Inês: "Copiei para o VS Code um programa de uma apresentação que encontrei na internet. O texto ficou igual ao da apresentação, letra a letra, por isso tem de correr."
3. O Rui: "Escrevi na consola do Python as cinco linhas do ecrã de abertura do meu jogo, e funcionaram todas. Amanhã abro a consola outra vez e mostro-as ao professor."
4. O Tomás: "O VS Code sublinhou o `Print` da linha 3 do meu programa. Por isso, quando o correr, não vai aparecer nenhuma linha."

Rever: [Do editor de texto ao editor de código](../01-do-algoritmo-ao-programa.md#do-editor-de-texto-ao-editor-de-código), [A consola do Python](../01-do-algoritmo-ao-programa.md#a-consola-do-python) e [Os três tipos de erro](../01-do-algoritmo-ao-programa.md#os-três-tipos-de-erro).

<details>
<summary>Pista</summary>

Em cada frase, pergunta-te que ferramenta está em causa, o que ela faz e o que não faz.

</details>

## Desafios

### Desafio 1: Dois erros de tipos diferentes

Este programa tem dois erros, de tipos diferentes:

```python fragment erros de propósito: o desafio pede que o aluno os encontre
# loja.py: as boas-vindas da loja de um jogo de quintas.
print("LOJA DA QUINTA")
print("Sementes novas todas as semanas.")
print("Regador a partir de 100 moedas."))
print("Enxada a partir de 50 moedas.")
print("Sementes novas todas as semanas.")
```

O resultado esperado é este:

```text
LOJA DA QUINTA
Sementes novas todas as semanas.
Regador a partir de 100 moedas.
Enxada a partir de 50 moedas.
```

Sem o correres, prevê o que aparece no ecrã. Depois copia-o para um ficheiro `loja.py`, sem o escreveres à mão, porque o VS Code fecha sozinho as aspas e os parênteses. Corrige-o, um erro de cada vez. Num comentário no fim, explica porque é que o segundo erro só se vê depois de corrigires o primeiro.

### Desafio 2: Aspas simples e aspas dentro do texto

Na consola do Python, descobre se o Python aceita um texto entre aspas simples, como `print('Olá')`. Descobre também como se escreve um `print` que mostre esta frase, com as aspas incluídas: `O árbitro gritou "golo"`. Escreve o que experimentaste e o que aconteceu, também nas tentativas que deram erro, num ficheiro `aspas.py`, só com comentários.

## Critérios de conclusão

- O `marcador.py` tem, no fim de cada linha em que te enganaste, um comentário com a explicação, ou diz que acertaste em todas.
- O `menu.py` corre e escreve o menu, com as três opções numeradas, uma por linha.
- O `erros.py` tem, para cada versão do exercício 3, o tipo de erro, a linha, como o soubeste e a correção.
- O `horario.py` corrigido dá o resultado esperado, com os cinco passos da depuração num comentário no fim.
- O `fases.py` tem as seis letras por ordem, cada uma com a sua fase.
- O `ferramentas.py` tem, para cada frase, se está certa ou errada e porquê.

![Rodapé](../../imagens/rodape.png)
