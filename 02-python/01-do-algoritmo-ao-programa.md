![Cabeçalho](../imagens/cabecalho.png)

# Do algoritmo ao programa

Módulo UC00606, Desenvolver programas em linguagem estruturada. Neste guia passas da algoritmia para a programação. Vais ver o que é um programa e que ferramentas se usam para o escrever e o pôr a correr. Vais ver também como se reconhece cada tipo de erro. Para praticar, há o [laboratório](01-do-algoritmo-ao-programa-laboratorio.md) e a [ficha de exercícios](01-do-algoritmo-ao-programa-exercicios.md) deste tema.

Na algoritmia, escreveste algoritmos em pseudocódigo e executaste-os tu, à mão, com papel e lápis. Agora é o computador que os executa. Neste tema, os programas fazem uma só coisa: escrevem texto no ecrã, numa sequência de instruções. Não leem nada do teclado, não fazem contas, não decidem nem repetem. Assim, a única novidade é a linguagem e as ferramentas, e não o problema.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Um programa é um algoritmo escrito para o computador
4. O ciclo de vida de um programa
5. As ferramentas: o editor, o ficheiro, o terminal e o interpretador
6. Correr um programa
7. A consola do Python
8. Do `Escreve:` ao `print`
9. A sintaxe e a estrutura de um programa
10. Os três tipos de erro
11. Depurar com método, agora no computador
12. O registo da execução
13. Exemplo guiado: as regras do pedra, papel, tesoura
14. Erros frequentes
15. Palavras novas deste guia
16. Verificar o que aprendeste
17. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- explicar a diferença entre um algoritmo e um programa, e o que faz o interpretador do Python;
- dizer por que fases passa um programa, desde o problema até às mudanças que se fazem depois de estar em uso;
- distinguir o editor, o ficheiro, o terminal e o interpretador, e dizer para que serve cada um;
- escrever um programa curto em Python, guardá-lo e corrê-lo no terminal;
- passar para Python uma sequência de `Escreve:` do pseudocódigo e confirmar que o resultado é o esperado;
- ler uma mensagem de erro, dizer de que tipo é o erro e corrigir a causa, depurando com método.

## O que já sabes e vais usar

- O que é um algoritmo, e as etapas para construir um algoritmo: guia [01 Do problema ao algoritmo](../01-algoritmos/01-do-problema-ao-algoritmo.md).
- As instruções ambíguas, e porque cada passo só se pode ler de uma maneira: guia [01 Do problema ao algoritmo](../01-algoritmos/01-do-problema-ao-algoritmo.md).
- A sequência e o `Escreve:`, com o texto entre aspas: guia [02 Pseudocódigo](../01-algoritmos/02-pseudocodigo.md).
- Seguir um algoritmo à mão e prever o que ele escreve no ecrã: guia [02 Pseudocódigo](../01-algoritmos/02-pseudocodigo.md).
- A sintaxe e o erro de sintaxe, e porque o pseudocódigo não os tem: guia [02 Pseudocódigo](../01-algoritmos/02-pseudocodigo.md).
- Os casos de teste, o resultado esperado e os cinco passos de depurar com método: guia [05 Testar, depurar e melhorar](../01-algoritmos/05-testar-depurar-e-melhorar.md).
- O duelo de dados, que resolveste no [projeto 1](../01-algoritmos/05-projeto-1-duelo-de-dados.md).
- Criar uma pasta, abrir uma aplicação e guardar um ficheiro no computador, do dia a dia.

## Um programa é um algoritmo escrito para o computador

Na algoritmia, quem executava os algoritmos eras tu. Seguias as instruções uma a uma, anotavas os valores numa tabela e escrevias o resultado. Com três casos de teste, isso leva uns minutos. Com mil encomendas de uma loja, ou com os jogos de uma liga inteira, ninguém o faria à mão. Um computador executa milhões de instruções por segundo, sem se cansar e sem se enganar nas contas. O problema é que não percebe português, nem o pseudocódigo das aulas.

Lembra-te das instruções ambíguas do guia 01. Uma pessoa que lê "escreve o título" pergunta qual título, ou adivinha. Um computador não pergunta nem adivinha. Para ele, cada instrução tem de ter um só significado, sem nenhuma dúvida possível. Por isso, para dar instruções a um computador, usa-se uma língua própria, com poucas palavras e regras de escrita muito rigorosas.

A uma língua destas chama-se **linguagem de programação**. É uma linguagem com um vocabulário pequeno e regras rigorosas, em que cada instrução quer dizer uma só coisa. Um algoritmo escrito numa linguagem de programação chama-se **programa**. É o mesmo algoritmo, escrito de outra forma. O pseudocódigo serve para pensar e para seguir à mão. O programa serve para o computador executar.

Vê o mesmo passo escrito das duas maneiras. Em pseudocódigo:

```text
Escreve: "Olá"
```

E em Python:

```python
print("Olá")
```

O **Python** é a linguagem de programação que vais usar neste módulo. Existem centenas de linguagens, e cada uma é uma ferramenta pensada para certos trabalhos, como um martelo e uma chave de fendas. O Python usa-se para automatizar tarefas, analisar dados, fazer sites e treinar sistemas de inteligência artificial. Escolheu-se para começar porque se lê quase como o pseudocódigo das aulas, e um programa pequeno ocupa poucas linhas. Vais usar a versão 3, a que se usa hoje.

Falta saber quem executa o programa. O computador, sozinho, não sabe o que é um `print`. Precisa de outro programa que leia o teu e faça o que ele diz. A esse programa chama-se **interpretador**. O interpretador lê o teu programa, confirma que está bem escrito e executa as instruções, uma a uma, de cima para baixo. Quando se diz que um computador "tem o Python instalado", quer dizer que tem o interpretador do Python.

O interpretador faz o que tu fazias com a tabela de trace: lê uma instrução, executa-a e passa à seguinte. A diferença é que nunca se cansa, e também nunca adivinha. Executa exatamente o que está escrito, mesmo quando não é o que querias dizer.

Um erro comum é pensar que o computador percebe a intenção. Se escreveres o título no fim do programa, o título aparece no fim, mesmo que seja óbvio para ti que devia aparecer no início.

## O ciclo de vida de um programa

Um programa não nasce quando se começa a escrever código. Pensa no duelo de dados, o projeto 1 da algoritmia. Primeiro leste o enunciado e escreveste o contrato. Depois escreveste o algoritmo, em pseudocódigo, e simulaste-o com casos de teste. Se o passares agora para Python, falta escrevê-lo, testá-lo no computador e corrigir o que falhar. E se um dia as regras mudarem, por exemplo para sete rondas, alguém vai ter de mudar o programa.

A estas fases, por que passa um programa desde o problema até deixar de ser usado, chama-se **ciclo de vida do software**. São cinco:

1. **Análise**: perceber o problema e escrever o que o programa tem de fazer. É o contrato da algoritmia, com as entradas, as saídas, as restrições, as condições e os exemplos com o resultado esperado.
2. **Desenho**: decidir como o programa o vai fazer. É a decomposição em subproblemas e o algoritmo em pseudocódigo.
3. **Implementação**: escrever o programa numa linguagem de programação, como o Python.
4. **Testes**: correr o programa com os casos de teste e comparar o resultado obtido com o resultado esperado. O que falhar corrige-se, e testa-se outra vez.
5. **Manutenção**: mudar o programa depois de estar em uso, para corrigir um erro que alguém encontrou ou para acrescentar uma regra nova.

As etapas para construir um algoritmo, do guia 01, são as duas primeiras fases deste ciclo, com um primeiro teste no papel:

| Etapa do guia 01 | Fase do ciclo de vida |
| --- | --- |
| 1 e 2: ler o enunciado e escrever o contrato | Análise |
| 3 e 4: decompor e escrever os passos | Desenho |
| 5 e 6: simular com os exemplos e procurar ambiguidades | Testes, ainda no papel |

Na algoritmia, trabalhaste a análise e o desenho. Com o Python, juntas a implementação, os testes no computador e a manutenção.

As fases não têm de se fazer todas de uma vez. À forma de as organizar no tempo chama-se **metodologia de desenvolvimento**. Há duas formas simples, que é bom saber distinguir.

Na forma **em cascata**, cada fase faz-se uma só vez, por inteiro, antes de passar à seguinte. É como construir uma casa: primeiro as plantas todas, depois as fundações, depois as paredes. O risco é este. Um erro da análise só aparece nos testes, no fim, quando já há muito código escrito por cima dele.

Na forma **incremental**, o programa cresce aos bocados. Cada bocado passa por todas as fases: pensas um pouco, escreves poucas linhas, corres e testas, e só depois passas ao bocado seguinte. Os erros aparecem cedo, perto da linha que os causou, quando ainda são fáceis de encontrar.

Nas aulas trabalhas de forma incremental. No laboratório deste tema, primeiro confirmas que um programa de duas linhas corre, e só depois escreves o ecrã de abertura do duelo de dados. Voltar a uma fase anterior também é normal. Se um teste mostra que falta uma regra, voltas à análise para a escrever, como já fazias na algoritmia.

O erro típico é saltar a análise e começar logo a escrever código. Sem saber o que o programa tem de fazer, não há resultado esperado. E sem resultado esperado, não há forma de testar.

## As ferramentas: o editor, o ficheiro, o terminal e o interpretador

Para escrever e correr um programa, usas quatro coisas ao mesmo tempo, e quase todas aparecem na mesma janela. Confundi-las é a dificuldade mais comum da primeira semana. Por isso vale a pena separá-las com calma.

Pensa numa receita de cozinha. Escreves a receita num caderno. A receita fica numa página, e a página fica guardada no caderno. Quando queres o bolo, dizes ao cozinheiro "faz a receita da página 3". O cozinheiro lê a página e faz cada passo, pela ordem. Com um programa é igual:

- o **editor** é o caderno onde escreves e mudas o programa. Nas aulas, é o VS Code. O editor pinta as palavras de cores diferentes, para ajudar a ler, mas não executa nada;
- o **ficheiro** é a página onde o programa fica guardado, no disco do computador. Um programa em Python guarda-se num ficheiro com o nome a acabar em `.py`, como `ola.py`;
- o **terminal** é a janela onde dás ordens ao computador, escritas, uma por linha. A cada ordem chama-se **comando**. O VS Code tem um terminal na parte de baixo, que se abre no menu Terminal;
- o **interpretador** é o cozinheiro: lê o ficheiro e executa cada instrução, pela ordem.

| Ferramenta | O que faz | Onde a vês |
| --- | --- | --- |
| Editor | Escreves e mudas o programa | O VS Code, com o ficheiro aberto à direita |
| Ficheiro `.py` | Guarda o programa no disco | O painel Explorer do VS Code, à esquerda |
| Terminal | Recebe os teus comandos | A janela na parte de baixo do VS Code |
| Interpretador | Executa o programa | Não se vê: trabalha quando escreves o comando `python` |

Os ficheiros de um trabalho ficam todos numa pasta, a **pasta do projeto**. No VS Code, abre-se a pasta inteira, e não só um ficheiro. Assim, o painel Explorer mostra os ficheiros dessa pasta, e o terminal abre-se dentro dela. Os nomes dos ficheiros e das pastas escrevem-se em minúsculas, sem espaços e sem acentos, como `lp-python` e `abertura.py`. Um nome com espaços obriga a usar aspas no terminal, e um nome com acentos pode dar problemas noutro computador.

Um erro típico é pensar que o VS Code e o Python são a mesma coisa. São dois programas diferentes, instalados à parte. O VS Code é só o editor. Um computador com o VS Code e sem o Python deixa-te escrever programas, mas não os consegue executar.

## Correr um programa

Um programa escrito e guardado ainda não fez nada. Para que o computador o execute, dás uma ordem ao interpretador, no terminal. A isto chama-se **correr** o programa, ou executá-lo.

Antes de veres o resultado, tenta prever: o que aparece no ecrã quando corres este programa, e por que ordem?

```python
# ola.py: o primeiro programa, para confirmar que o Python corre neste computador.
print("Olá, Python!")
print("O meu primeiro programa correu.")
```

Para o correr, escreve-se no terminal, na pasta do ficheiro, este comando:

```bash
python ola.py
```

O resultado é este:

```text
Olá, Python!
O meu primeiro programa correu.
```

Aparecem as duas linhas, pela ordem em que estão no ficheiro. A primeira linha do programa não aparece, porque é um comentário.

Leitura guiada: começa pelo comando. A palavra `python` chama o interpretador, e `ola.py` diz-lhe que ficheiro deve executar. Depois lê o programa de cima para baixo. A primeira linha começa com `#`, e o Python não a executa: é uma nota para quem lê, que diz o que é o ficheiro. As duas linhas seguintes são instruções `print`, e cada uma escreve no ecrã o texto entre aspas. As aspas marcam onde o texto começa e acaba, e não aparecem.

Quando carregas em Enter, acontece isto, por esta ordem:

1. O terminal recebe o comando e põe o interpretador do Python a trabalhar.
2. O interpretador procura o ficheiro `ola.py` na pasta onde o terminal está.
3. Lê o ficheiro todo e confirma que está bem escrito, segundo as regras do Python.
4. Executa as instruções uma a uma, de cima para baixo: salta o comentário, escreve a primeira linha e escreve a segunda.
5. Quando acaba a última instrução, o programa termina, e o terminal fica outra vez à espera de um comando.

O nome do comando muda de computador para computador. No Windows, é quase sempre `python`. Se o Windows disser que não o conhece, ou se abrir a Microsoft Store, usa-se `py`, que faz o mesmo. No macOS e no Linux, é `python3`. Quando descobrires qual funciona no teu computador, escreve-o no caderno. Neste guia, escreve-se sempre `python`, e tu usas o teu.

Antes de correr, guarda sempre o ficheiro, com Ctrl+S, ou Cmd+S no macOS. O interpretador lê o ficheiro que está guardado no disco, e não o que vês no editor. No VS Code, uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.

## A consola do Python

Às vezes só queres saber o que faz uma linha, sem criar um ficheiro. Por exemplo, queres confirmar se o `print` aceita um texto com acentos. Criar um ficheiro, guardá-lo e corrê-lo, só para isso, leva tempo.

Para estes casos há a **consola do Python**: o modo em que o Python executa uma linha de cada vez e mostra logo o resultado. Entra-se nela escrevendo no terminal só `python`, sem nome de ficheiro. Aparecem duas linhas em inglês, a primeira com a versão do Python, e por baixo, numa linha à parte, o sinal `>>>`. No Python 3.14, a consola pode mostrar o texto a cores. Esse sinal quer dizer que a consola está à espera de uma linha de Python.

Antes de leres o resultado, tenta prever o que aparece a seguir a cada uma destas duas linhas:

```text
>>> print("Olá da consola")
Olá da consola
>>> "DUELO DE DADOS"
'DUELO DE DADOS'
```

A primeira linha tem um `print`, e o texto aparece sem aspas, como num programa. A segunda não tem `print`, e mesmo assim aparece qualquer coisa. Quando uma linha é só um texto, a consola mostra-o, com aspas simples à volta para dizer que é um texto. Num ficheiro, uma linha só com um texto não escreve nada no ecrã. Só o `print` escreve.

Leitura guiada: cada linha que começa por `>>>` foi escrita por ti. Cada linha sem `>>>` foi escrita pelo Python, em resposta à linha de cima.

O que escreves na consola não fica guardado em lado nenhum. Quando sais, perde-se. Por isso, a consola serve para experimentar uma linha, e um programa que queres guardar escreve-se num ficheiro. Para sair, escreve-se `exit()` e carrega-se em Enter.

O erro mais comum é escrever um comando do terminal dentro da consola, como `python ola.py` a seguir ao `>>>`. A consola espera linhas de Python, e responde com um erro. A regra que evita a confusão é esta: com `>>>`, escreves Python; sem `>>>`, escreves comandos.

## Do `Escreve:` ao `print`

Tens um algoritmo em pseudocódigo e queres passá-lo para Python. Neste tema, os algoritmos são sequências de `Escreve:`, e a passagem faz-se instrução a instrução. Vê o ecrã de abertura de um quiz:

```text
Escreve: "QUIZ DE GEOGRAFIA"
Escreve: "São dez perguntas."
Escreve: "Cada resposta certa vale um ponto."
```

Antes de leres o programa, tenta escrever tu o Python. Depois tenta prever o que ele escreve no ecrã.

```python
# quiz.py: o ecrã de abertura de um quiz de geografia.
print("QUIZ DE GEOGRAFIA")
print("São dez perguntas.")
print("Cada resposta certa vale um ponto.")
```

O resultado é este:

```text
QUIZ DE GEOGRAFIA
São dez perguntas.
Cada resposta certa vale um ponto.
```

É o mesmo que o pseudocódigo escreveria. O algoritmo é o mesmo, e só mudou a forma de o escrever.

Leitura guiada: o comentário da primeira linha diz o que é o ficheiro. Cada `Escreve:` do pseudocódigo passou a uma linha com `print`, pela mesma ordem. O texto entre aspas ficou igual, com os acentos e os espaços. O Python aceita acentos dentro das aspas.

A passagem segue sempre as mesmas regras:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `Escreve: "Olá"` | `print("Olá")` | `print` em minúsculas, e o texto entre parênteses |
| um `Escreve:` por linha | um `print` por linha | nada: uma instrução por linha |
| a ordem das instruções | a mesma ordem | nada: executa-se de cima para baixo |
| não havia | `# comentário` | uma nota para quem lê, que o Python não executa |

A palavra `print` é inglesa e quer dizer "imprimir". Vem do tempo em que os computadores mostravam os resultados em papel, numa impressora. Hoje, o `print` escreve no ecrã, no terminal.

Um **comentário** é uma nota para quem lê o código, a seguir a um sinal `#` que está fora das aspas. O Python ignora tudo o que vem depois desse `#`, até ao fim da linha. Os programas das aulas começam todos por um comentário que diz o nome do ficheiro e para que serve. Quem abre o ficheiro uma semana depois sabe logo o que tem à frente.

O texto entre aspas aparece tal e qual, com os espaços que lá estiverem, como no pseudocódigo.

## A sintaxe e a estrutura de um programa

No pseudocódigo das aulas, a forma não era o mais importante. Uma frase clara, como "escreve o nome do jogo", com a lógica certa, era aceite. O interpretador do Python não aceita nada fora das regras. Se faltar uma aspa, o programa não corre, mesmo que se perceba bem o que querias.

No guia 02, viste que às regras de escrita de uma linguagem se chama sintaxe, e que o pseudocódigo não tem erros de sintaxe. O Python tem. As regras dele são como a ortografia e a pontuação do português, mas sem tolerância nenhuma. Para os programas deste tema, as regras são estas:

1. A instrução escreve-se `print`, toda em minúsculas. Para o Python, `print` e `Print` são palavras diferentes.
2. O que se escreve vai entre parênteses, e cada parêntese que abre tem de fechar.
3. Um texto vai entre aspas, uma no início e outra no fim. Sem aspas, o Python não sabe que é um texto.
4. Escreve-se uma instrução por linha.
5. Cada instrução começa encostada à margem esquerda, sem espaços antes. Os espaços no início de uma linha têm um significado próprio no Python, como a indentação do pseudocódigo, e só aparecem com os blocos.
6. Um comentário começa num `#` fora das aspas e vai até ao fim da linha.

À forma como as partes de um programa se arrumam chama-se **estrutura**. Por agora, a estrutura de um programa é sempre a mesma. No início, um comentário diz o que é o ficheiro. Depois vêm as instruções, pela ordem em que se executam. É como um documento com um título e o texto por baixo.

O erro típico é pensar que o Python "percebe a ideia". Não percebe: lê o que está escrito, segundo as regras. Uma diferença de uma letra, ou uma aspa a menos, chega para o programa não correr, ou para fazer outra coisa.

## Os três tipos de erro

Quando um programa falha, a primeira pergunta é onde procurar. A resposta depende do tipo de erro. Há três, e cada um se reconhece pelo que acontece no ecrã.

Para os veres, parte do `quiz.py` da secção "Do `Escreve:` ao `print`". O resultado esperado são as três linhas do quiz.

**Primeiro caso.** Falta a aspa que fecha o texto na linha 3. Antes de leres o resultado, prevê: aparece a primeira linha do quiz, que está certa?

```python fragment erro de sintaxe de propósito: falta a aspa que fecha o texto
# quiz.py: o ecrã de abertura de um quiz de geografia.
print("QUIZ DE GEOGRAFIA")
print("São dez perguntas.)
print("Cada resposta certa vale um ponto.")
```

O resultado é este:

```text
  File "C:\Users\aluno\Documents\lp-python\quiz.py", line 3
    print("São dez perguntas.)
          ^
SyntaxError: unterminated string literal (detected at line 3)
```

Não aparece nenhuma linha do quiz, nem a primeira. É um **erro de sintaxe**: um erro na escrita do programa. Antes de executar, o interpretador lê o ficheiro todo e confirma que está bem escrito. Ao encontrar uma regra quebrada, recusa o programa inteiro, e nenhuma linha corre. A mensagem quer dizer "erro de sintaxe: texto por terminar, detetado na linha 3".

**Segundo caso.** A linha 4 tem `Print`, com P maiúsculo. Antes de leres o resultado, prevê: aparece alguma linha do quiz?

```python
# quiz.py: o ecrã de abertura de um quiz de geografia.
print("QUIZ DE GEOGRAFIA")
print("São dez perguntas.")
Print("Cada resposta certa vale um ponto.")
```

O resultado é este:

```text
QUIZ DE GEOGRAFIA
São dez perguntas.
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\lp-python\quiz.py", line 4, in <module>
    Print("Cada resposta certa vale um ponto.")
    ^^^^^
NameError: name 'Print' is not defined. Did you mean: 'print'?
```

Desta vez, as duas primeiras linhas apareceram. É um **erro de execução**: um erro que para o programa a meio, numa linha que o Python não consegue executar. O programa estava bem escrito, por isso o Python começou a executá-lo. Executou as linhas 2 e 3 e parou na 4, porque não conhece nenhuma instrução chamada `Print`. As linhas de antes do erro já correram, e as de depois nunca correm.

**Terceiro caso.** O programa está bem escrito, mas o texto da linha 4 diz "dois pontos", em vez de "um ponto". Antes de leres o resultado, prevê: aparece alguma mensagem de erro?

```python
# quiz.py: o ecrã de abertura de um quiz de geografia.
print("QUIZ DE GEOGRAFIA")
print("São dez perguntas.")
print("Cada resposta certa vale dois pontos.")
```

O resultado é este:

```text
QUIZ DE GEOGRAFIA
São dez perguntas.
Cada resposta certa vale dois pontos.
```

Não há mensagem nenhuma, e o programa correu até ao fim. Mas a última linha não é a do resultado esperado. É um **erro de lógica**: um erro que não dá mensagem, em que o programa corre e dá um resultado diferente do esperado. O Python não tem forma de saber que querias "um ponto". Só tu sabes, porque escreveste o resultado esperado antes de correr.

| Tipo de erro | Corre alguma linha? | Há mensagem? | Como o encontras |
| --- | --- | --- | --- |
| De sintaxe | Nenhuma | Sim, com `SyntaxError` ou parecido | Pela linha que a mensagem aponta |
| De execução | As que estão antes do erro | Sim, com `Traceback` | Pela linha que a mensagem aponta |
| De lógica | Todas | Não | Comparando o resultado obtido com o esperado |

O nome do erro, a palavra antes dos dois pontos na última linha da mensagem, ajuda, mas não chega para saber o tipo. Alguns erros de sintaxe têm um nome próprio, diferente de `SyntaxError`. O que decide o tipo é o que aconteceu: se correu alguma linha, e se houve mensagem.

### Como se lê uma mensagem de erro

As mensagens de erro estão em inglês e parecem complicadas, mas têm sempre a mesma forma. A mensagem de um erro de execução chama-se **traceback**, e lê-se de baixo para cima:

1. A última linha diz o nome do erro, antes dos dois pontos, e uma descrição curta, depois deles. Começa sempre por aqui.
2. Por cima dela estão a instrução onde o Python deu pelo problema e, numa linha à parte, sinais `^` por baixo da parte suspeita.
3. Mais acima, a linha com `File` diz o ficheiro e o número da linha, a seguir a `line`.

A linha apontada é onde o Python deu pelo problema, e nem sempre é onde ele nasceu. Se não encontrares nada de errado nessa linha, olha também para a de cima. A mensagem é uma pista, e não a resposta.

O caminho do ficheiro, na linha com `File`, muda de computador para computador. Nos exemplos deste guia, `C:\Users\aluno\Documents\lp-python` é só uma ilustração.

As palavras que mais vais ver:

| Na mensagem | Quer dizer |
| --- | --- |
| `File`, `line` | Ficheiro, linha |
| `Traceback (most recent call last)` | Vem aí a mensagem de um erro de execução |
| `SyntaxError` | Erro de sintaxe |
| `invalid syntax` | Escrita inválida |
| `unterminated string literal` | Texto por terminar: falta uma aspa |
| `NameError` | Erro de nome: o Python não conhece uma palavra |
| `is not defined` | Não está definido |
| `Did you mean` | Querias dizer |
| `in <module>` | Na parte principal do programa |

As mensagens deste guia são as do Python 3.14. Num Python mais antigo, a mesma aspa por fechar pode dar `SyntaxError: EOL while scanning string literal`. EOL quer dizer fim da linha: o Python chegou ao fim da linha sem encontrar a aspa que fecha o texto. As palavras mudam, mas o nome do erro, antes dos dois pontos, é o mesmo.

## Depurar com método, agora no computador

No guia 05 da algoritmia, aprendeste a depurar com método, em cinco passos, quando um algoritmo falha. No computador, os passos são os mesmos. Muda só o que tens à mão para cada um:

| Passo | No computador |
| --- | --- |
| 1. Observar e reproduzir o erro | Corres outra vez e confirmas que o erro se repete. Escreves o resultado esperado, o obtido e o tipo de erro: de sintaxe, de execução ou de lógica |
| 2. Formular uma hipótese | Escreves uma explicação possível, que se possa confirmar, como "falta a aspa que fecha o texto da linha 3" |
| 3. Verificar a hipótese | Lês a mensagem, de baixo para cima, e a linha que ela aponta. Num erro de lógica, comparas o programa com o algoritmo, linha a linha |
| 4. Corrigir a causa | Mudas só o que causou o erro, uma coisa de cada vez, e guardas |
| 5. Voltar a testar tudo | Corres outra vez e comparas todas as linhas com o resultado esperado, e não só a que estava errada |

O passo 1 tem agora uma pergunta a mais: que tipo de erro é? A resposta diz-te onde procurar. Um erro de sintaxe ou de execução tem uma mensagem a apontar uma linha. Um erro de lógica só se vê comparando com o resultado esperado.

O que o método evita é mudar linhas ao acaso até o programa parecer certo. Uma mudança feita à sorte pode esconder o erro sem o corrigir, ou criar outro.

## O registo da execução

Um programa que corre num computador pode não correr noutro da mesma maneira. O comando pode ser `python` num e `py` no outro. A versão do Python pode ser diferente, e com ela as palavras das mensagens de erro. E daqui a uma semana, já não te lembras de que comando usaste nem do que apareceu.

Por isso, quando corres um programa num computador pela primeira vez, fazes um **registo da execução**. É uma nota com o que é preciso para voltar a correr o programa e para comparar resultados. Leva:

- a data e o computador;
- o comando que funciona nesse computador, `python`, `py` ou `python3`;
- a versão do Python, que o comando `python --version` mostra;
- o programa que correste;
- o que apareceu, comparado com o resultado esperado;
- os erros que encontraste, com o tipo de cada um e como os corrigiste.

Por exemplo:

```text
Registo da execução
Data: 29 de outubro de 2026
Computador: o da sala, lugar 7
Comando que funciona: python
Versão: Python 3.13.2
Programa: quiz.py
O que apareceu: as três linhas, iguais ao resultado esperado
Erros: uma aspa por fechar na linha 3, erro de sintaxe, corrigido
```

A versão escreve-se porque explica diferenças. Se a tua mensagem de erro não for igual à do colega, compara as versões antes de pensar que o erro é outro.

## Exemplo guiado: as regras do pedra, papel, tesoura

Um colega está a fazer um jogo de pedra, papel, tesoura. Pede-te o ecrã de abertura, com o nome do jogo e as regras de quem ganha. Vais fazê-lo passando pelas fases do ciclo de vida, de forma incremental, até ao programa testado.

### Passo 1: Análise

Primeiro, decide-se o que o programa tem de fazer. Não há entradas: o programa não lê nada. As saídas são as linhas que aparecem no ecrã. No pedra, papel, tesoura, a pedra parte a tesoura, a tesoura corta o papel e o papel embrulha a pedra. Se os dois jogadores escolherem o mesmo, é empate.

O resultado esperado, escrito antes de qualquer código:

```text
PEDRA, PAPEL, TESOURA
A pedra parte a tesoura.
A tesoura corta o papel.
O papel embrulha a pedra.
Se escolherem o mesmo, é empate.
```

### Passo 2: Desenho

Cada linha do resultado esperado é um `Escreve:`, pela mesma ordem. É uma sequência, sem decisões nem repetições:

```text
Escreve: "PEDRA, PAPEL, TESOURA"
Escreve: "A pedra parte a tesoura."
Escreve: "A tesoura corta o papel."
Escreve: "O papel embrulha a pedra."
Escreve: "Se escolherem o mesmo, é empate."
```

Seguido à mão, este algoritmo escreve exatamente o resultado esperado. O desenho está certo.

### Passo 3: Implementação

Cada `Escreve:` passa a um `print`, com um comentário no início. Escrito à pressa, o programa ficou assim, no ficheiro `regras.py`:

```python
# regras.py: o ecrã de abertura do pedra, papel, tesoura, com as regras de quem ganha.
print("PEDRA, PAPEL, TESOURA")
print("A pedra parte a tesoura.")
print("A tesoura corta o papel.")
print("Se escolherem o mesmo, é empate.")
```

### Passo 4: Testes

Guarda-se e corre-se com `python regras.py`. O que aparece:

```text
PEDRA, PAPEL, TESOURA
A pedra parte a tesoura.
A tesoura corta o papel.
Se escolherem o mesmo, é empate.
```

Não há mensagem de erro. Se não tivesses o resultado esperado, era tentador dar o programa por acabado. Mas, comparando linha a linha, o resultado obtido tem quatro linhas, e o esperado tem cinco. Falta "O papel embrulha a pedra.".

### Passo 5: Depurar com método

A correção ainda faz parte dos testes: corrige-se o que o teste mostrou, e testa-se outra vez.

1. Observar e reproduzir. Corre-se outra vez, e falta a mesma linha. O esperado tem cinco linhas, e o obtido tem quatro, sem "O papel embrulha a pedra.". Não há mensagem, e o programa correu até ao fim: é um erro de lógica.
2. Formular uma hipótese. "Falta no programa o `print` da terceira regra."
3. Verificar a hipótese. Compara-se o programa com o algoritmo, linha a linha. O algoritmo tem cinco `Escreve:`, e o programa tem quatro `print`. O `print` do papel não está lá. A hipótese confirma-se.
4. Corrigir a causa. Acrescenta-se o `print` que falta, no sítio certo: depois da regra da tesoura e antes do empate. A ordem importa, porque o Python escreve as linhas pela ordem do ficheiro.
5. Voltar a testar tudo. Guarda-se, corre-se e comparam-se as cinco linhas com o resultado esperado, e não só a que faltava.

O programa corrigido:

```python
# regras.py: o ecrã de abertura do pedra, papel, tesoura, com as regras de quem ganha.
print("PEDRA, PAPEL, TESOURA")
print("A pedra parte a tesoura.")
print("A tesoura corta o papel.")
print("O papel embrulha a pedra.")
print("Se escolherem o mesmo, é empate.")
```

O que aparece agora é igual, linha a linha, ao resultado esperado do passo 1. O programa passou o teste.

### Passo 6: O registo da execução

No caderno, fica o registo da execução. Tem a data, o computador, o comando, a versão do Python e o programa `regras.py`. Tem também o resultado, igual ao esperado, e o erro encontrado. Esse erro foi uma linha em falta, um erro de lógica, encontrado ao comparar com o resultado esperado.

### Passo 7: Manutenção

Uma semana depois, o colega muda o jogo: agora, ganha quem vencer duas de três jogadas. O programa já está em uso, e mudá-lo é manutenção. Volta-se à análise e acrescenta-se ao resultado esperado uma linha, no fim: "Ganha quem vencer duas de três jogadas.". No programa, acrescenta-se um `print` no fim. Depois, testa-se tudo outra vez, as seis linhas, e atualiza-se o registo.

Repara no caminho completo: análise, desenho, implementação, testes, com a correção do erro encontrado, e manutenção. O erro só se encontrou porque o resultado esperado estava escrito antes de correr o programa.

## Erros frequentes

### O resultado não muda depois de corrigires o código

Corrigiste no editor, correste, e aparece o mesmo de antes. Acontece porque o ficheiro não foi guardado, e o interpretador leu a versão antiga, que está no disco. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre outra vez.

### `can't open file` e `No such file or directory`

A mensagem quer dizer "não consigo abrir o ficheiro: não existe esse ficheiro nem essa pasta". Acontece quando o terminal não está na pasta do ficheiro, ou quando o nome no comando tem um erro. Confirma que o texto antes do cursor acaba no nome da pasta do projeto. Confirma também que o nome no comando é igual ao do ficheiro, com o `.py`.

### O comando do terminal escrito na consola

Escreveste `python ola.py` e apareceu `SyntaxError: invalid syntax`. Acontece porque estás dentro da consola do Python, e a linha começa por `>>>`. Sai com `exit()` e escreve o comando outra vez.

### O `Escreve:` copiado do pseudocódigo

Copiaste uma linha do pseudocódigo, como `Escreve: "Olá"`, e o programa corre sem mensagem e sem escrever nada. Por coincidência, o Python aceita essa linha, com outro significado, que não escreve nada no ecrã. É um erro de lógica. Troca cada `Escreve:` por `print`, com o texto entre parênteses.

### O Windows não conhece o `python`

Escreveste `python ola.py` e o Windows diz que não conhece o comando, ou abre a Microsoft Store. O comando `python` não está disponível com esse nome nesse computador. Fecha a loja e usa `py ola.py`. Se nenhum dos dois funcionar, o Python pode não estar instalado.

## Palavras novas deste guia

- Linguagem de programação: uma linguagem com um vocabulário pequeno e regras rigorosas, em que cada instrução quer dizer uma só coisa.
- Programa: um algoritmo escrito numa linguagem de programação, que o computador consegue executar.
- Python: a linguagem de programação deste módulo, na versão 3.
- Interpretador: o programa que lê o teu programa, confirma que está bem escrito e executa as instruções, uma a uma, de cima para baixo.
- Ciclo de vida do software: as fases por que passa um programa, a análise, o desenho, a implementação, os testes e a manutenção.
- Análise: a fase em que se percebe o problema e se escreve o que o programa tem de fazer.
- Desenho: a fase em que se decide como, com a decomposição e o algoritmo.
- Implementação: a fase em que se escreve o programa numa linguagem de programação.
- Testes: a fase em que se corre o programa com os casos de teste e se compara o resultado obtido com o esperado.
- Manutenção: as mudanças feitas a um programa depois de estar em uso.
- Metodologia de desenvolvimento: a forma de organizar no tempo as fases do ciclo de vida.
- Em cascata: cada fase faz-se uma só vez, por inteiro, antes da seguinte.
- Incremental: o programa cresce aos bocados, e cada bocado passa por todas as fases.
- Editor: o programa onde se escreve e muda o código; nas aulas, o VS Code.
- Ficheiro `.py`: o ficheiro onde fica guardado um programa em Python.
- Terminal: a janela onde se escrevem comandos, um por linha.
- Comando: uma ordem escrita no terminal, como `python ola.py`.
- Pasta do projeto: a pasta com os ficheiros de um trabalho, que se abre inteira no VS Code.
- Correr: pôr o interpretador a executar um programa.
- Consola do Python: o modo em que o Python executa uma linha de cada vez e mostra logo o resultado, a seguir ao `>>>`.
- `print`: a instrução do Python que escreve no ecrã; o `Escreve:` do pseudocódigo.
- Comentário: uma nota para quem lê o código, a seguir a um `#` fora das aspas, que o Python não executa.
- Estrutura: a forma como as partes de um programa se arrumam.
- Erro de execução: um erro que para o programa a meio; as linhas de antes já correram.
- Erro de lógica: um erro sem mensagem; o programa corre, mas o resultado não é o esperado.
- Traceback: a mensagem de um erro de execução, que se lê de baixo para cima.
- Registo da execução: a nota com a data, o computador, o comando, a versão do Python e o que apareceu.

## Verificar o que aprendeste

1. Qual é a diferença entre um algoritmo e um programa? Porque é que o computador não executa o pseudocódigo das aulas?
2. O que faz o interpretador quando escreves `python quiz.py`? Diz os passos por ordem.
3. Diz para que serve o editor, o ficheiro, o terminal e o interpretador, e onde vês cada um no VS Code.
4. Escreve as cinco fases do ciclo de vida, por ordem. Em qual delas escreveste o pseudocódigo do duelo de dados?
5. Qual é a diferença entre desenvolver em cascata e de forma incremental? Porque é que, na forma incremental, os erros se encontram mais depressa?
6. O que aparece no ecrã com este programa?

   ```python
   # torneio.py: o anúncio de um torneio de xadrez da escola.
   print("TORNEIO DE XADREZ")
   print("Inscrições na biblioteca.")
   ```

7. Um programa tem seis linhas `print` e um erro na quarta. Que linhas aparecem no ecrã, se o erro for de sintaxe? E se for de execução?
8. Porque é que um erro de lógica não dá mensagem? Como o encontras?
9. Na consola, o que quer dizer o `>>>`? O que acontece se lá escreveres `python ola.py`, e porquê?
10. Que informação leva o registo da execução? Porque é que a versão do Python faz parte dele?

## O que vem a seguir

Para praticar este tema, faz o [laboratório](01-do-algoritmo-ao-programa-laboratorio.md) e depois a [ficha de exercícios](01-do-algoritmo-ao-programa-exercicios.md). O tema seguinte é Dados e interação.

## Para saber mais

- [Transferir o Python](https://www.python.org/downloads/): a página oficial, em inglês, para instalares o Python no teu computador de casa. Se tiveres dúvidas na instalação, fala com o professor.
- [Transferir o VS Code](https://code.visualstudio.com/download): a página oficial do editor das aulas, em inglês, com as versões para Windows, macOS e Linux.

![Rodapé](../imagens/rodape.png)
