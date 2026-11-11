![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Do algoritmo ao programa

## O que vais construir

Vais escrever e correr os teus primeiros programas em Python. São o `ola.py`, com o registo da execução num comentário, e o `abertura.py`, com o ecrã de abertura do duelo de dados. Pelo caminho, desenhas no caderno o mapa da janela do VS Code. No fim, a pasta fica assim:

```text
lp-python/
├── ola.py
└── abertura.py
```

1. [Fase 1: Correr um programa](#fase-1-correr-um-programa)
2. [Fase 2: A consola do Python](#fase-2-a-consola-do-python)
3. [Fase 3: O IDE: as ferramentas numa só janela](#fase-3-o-ide-as-ferramentas-numa-só-janela)
4. [Fase 4: Do `Escreve:` ao `print`](#fase-4-do-escreve-ao-print)
5. [Fase 5: Os três tipos de erro](#fase-5-os-três-tipos-de-erro)

## O que precisas

- O Python 3. Confirmas que o tens no passo 4 da fase 1, quando o primeiro programa corre, e a versão na fase 2.
- O VS Code, com a extensão Python, da Microsoft. Confirmas a extensão na fase 3; sem ela, o laboratório faz-se na mesma.
- O caderno, para o mapa da janela.

Os menus e os botões têm os nomes do VS Code em inglês. Se o teu estiver em português, estão no mesmo sítio, com o nome traduzido.

## Preparar o projeto

1. Cria uma pasta `lp-python` onde guardas os trabalhos, por exemplo em Documentos. O nome não tem espaços nem acentos, para se escrever sem problemas no terminal.

2. Abre a pasta no VS Code, com a opção `Open Folder...` do menu File. Se o VS Code perguntar se confias nos autores dos ficheiros, responde que sim, porque a pasta é tua. O que deves ver: à esquerda, no painel Explorer, o nome `LP-PYTHON`, ainda sem ficheiros.

## Fase 1: Correr um programa

Escreves um programa num ficheiro e mandas o interpretador executá-lo, no terminal. O `Escreve:` do pseudocódigo passa a chamar-se `print`. Rever: [Correr um programa](../01-do-algoritmo-ao-programa.md#correr-um-programa).

1. Cria o primeiro ficheiro. No painel Explorer, passa o rato por cima de `LP-PYTHON` e carrega no primeiro ícone, uma folha com um +, o `New File...`. Escreve o nome `ola.py` e carrega em Enter. O ficheiro abre-se ao centro, vazio. Escreve nele o programa, e repara que o VS Code fecha sozinho as aspas e os parênteses, que não precisas de escrever outra vez:

   ```python
   # ola.py: o primeiro programa, para confirmar que o Python corre neste computador.
   print("Olá, Python!")
   print("O meu primeiro programa correu.")
   ```

   Se aparecer um aviso a recomendar uma extensão de Python, fecha-o por agora.

2. Guarda o ficheiro, com Ctrl+S, ou Cmd+S no macOS, porque o Python lê o ficheiro guardado no disco. O que deves ver: no separador `ola.py`, no topo do editor, a bola cheia volta a ser um X.

3. Abre o terminal, no menu Terminal, com a opção New Terminal. O que deves ver: uma janela na parte de baixo, com uma linha que acaba em `lp-python` e o cursor à espera.

4. Prevê o que aparece, e por que ordem. Depois escreve no terminal este comando e carrega em Enter:

   ```bash
   python ola.py
   ```

   No macOS, o comando é `python3 ola.py`. O que deves ver:

   ```text
   Olá, Python!
   O meu primeiro programa correu.
   ```

   O interpretador executou as duas instruções, de cima para baixo. A linha 1, que começa por `#`, é um comentário e não aparece. Se o Windows não conhecer o `python`, ou aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

5. Fixa o comando que funcionou no teu computador: `python`, `py` ou `python3`. É esse que usas sempre que este laboratório diz `python`.

6. Provoca um erro de propósito: apaga a aspa que fecha o texto da linha 3, para ficar `print("O meu primeiro programa correu.)`. O número da linha está na margem esquerda do editor. Guarda e corre outra vez. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\lp-python\ola.py", line 3
       print("O meu primeiro programa correu.)
             ^
   SyntaxError: unterminated string literal (detected at line 3)
   ```

   A última linha quer dizer "erro de sintaxe: texto por terminar, detetado na linha 3". O caminho do ficheiro, na primeira linha, é outro no teu computador. Repara que o "Olá, Python!" da linha 2 também não apareceu.

7. Corrige: volta a pôr a aspa, guarda e corre outra vez, até veres as duas linhas.

### Paragem 1

O `ola.py` corre e escreve as duas linhas, e sabes que comando funciona no teu computador.

Pensa antes de continuares: porque é que, com o erro na linha 3, nem o "Olá, Python!" da linha 2 apareceu? A resposta: o interpretador confirma o ficheiro todo antes de executar. Ao encontrar um erro de sintaxe, recusa o programa e não executa nenhuma linha.

## Fase 2: A consola do Python

Confirmas a versão do teu Python, guardas o registo da execução e experimentas a consola. A consola executa uma linha de cada vez, sem ficheiro. Rever: [A consola do Python](../01-do-algoritmo-ao-programa.md#a-consola-do-python) e [O registo da execução](../01-do-algoritmo-ao-programa.md#o-registo-da-execução).

1. No terminal, escreve o teu comando seguido de `--version` e carrega em Enter:

   ```bash
   python --version
   ```

   O que deves ver: uma só linha, como `Python 3.14.8`. Os números são os da versão instalada, e o primeiro tem de ser 3. Se for 2, avisa o professor.

2. Escreve o registo da execução num comentário no fim do `ola.py`, a seguir às três linhas do programa. Cada linha começa por `#`. Com os teus valores, fica parecido com isto:

   ```python
   # Registo da execução
   # Data: 29 de outubro de 2026
   # Computador: o da sala, lugar 7
   # Comando que funciona: python
   # Versão: Python 3.14.8
   # O que apareceu: as duas linhas, pela ordem do programa
   # Erro provocado: a aspa por fechar, SyntaxError na linha 3
   ```

   Guarda e corre outra vez o `ola.py`. O que deves ver: as mesmas duas linhas, porque os comentários não se executam. Se aparecer uma mensagem de erro, falta o `#` numa das linhas.

3. Entra na consola: no terminal, escreve só o teu comando, sem nome de ficheiro, e carrega em Enter. O que deves ver: a versão do Python, uma linha em inglês e, por baixo, `>>>`.

4. Prevê o que aparece a seguir a cada linha. Depois escreve-as a seguir ao `>>>`, uma de cada vez:

   ```python
   print("Olá da consola")
   "DUELO DE DADOS"
   ```

   O que deves ver:

   ```text
   >>> print("Olá da consola")
   Olá da consola
   >>> "DUELO DE DADOS"
   'DUELO DE DADOS'
   ```

   A segunda linha não tem `print`, e a consola mostra o texto com aspas simples, para dizer que é um texto.

5. Provoca um erro de propósito: escreve na consola `python ola.py` e carrega em Enter. O que deves ver:

   ```text
   >>> python ola.py
     File "<python-input-2>", line 1
       python ola.py
              ^^^
   SyntaxError: invalid syntax
   ```

   Na consola só se escreve Python, e `python ola.py` é um comando do terminal. O número em `<python-input-2>` depende das linhas que já escreveste.

6. Sai da consola: escreve `exit()` e carrega em Enter. O que deves ver: a linha do terminal outra vez, a acabar em `lp-python`.

### Paragem 2

O registo da execução está no fim do `ola.py`, e não apareceu nenhum ficheiro novo na pasta.

Pensa antes de continuares: quando usas a consola, e quando usas um ficheiro `.py`? A resposta: a consola serve para experimentar uma linha; um programa que queres guardar e voltar a correr escreve-se num ficheiro.

## Fase 3: O IDE: as ferramentas numa só janela

Percorres as ferramentas que o VS Code junta na mesma janela, com o `ola.py`, e desenhas o mapa da janela no caderno. Rever: [Do editor de texto ao editor de código](../01-do-algoritmo-ao-programa.md#do-editor-de-texto-ao-editor-de-código) e [O IDE: as ferramentas numa só janela](../01-do-algoritmo-ao-programa.md#o-ide-as-ferramentas-numa-só-janela).

1. Desenha no caderno um retângulo grande, dividido em cinco zonas, e deixa espaço em cada uma para os nomes das ferramentas. As zonas são a coluna estreita dos ícones, à esquerda, o painel do explorador, ao lado dela, e o editor, ao centro. Por baixo ficam o painel do terminal e a barra de estado, a faixa fina do fundo.

2. Confirma a extensão Python. Na coluna dos ícones, carrega em Extensions, o ícone dos quatro quadrados, e escreve `Python` na caixa de procura. O que deves ver: a extensão Python, da Microsoft, no topo da lista. Se tiver um botão Install, não está instalada: avisa o professor. No mapa, escreve "extensões" na coluna dos ícones. Volta ao explorador, com o primeiro ícone da coluna.

3. No painel Explorer, carrega no `ola.py`. O que deves ver: o ficheiro aberto ao centro, com um separador `ola.py` no topo. No mapa, escreve "explorador", "editor e separadores" e "terminal" nas zonas certas.

4. Olha para o editor. A margem da esquerda tem os números das linhas, e o comentário, a palavra `print` e os textos têm cores diferentes. São o realce de sintaxe, e não ficam guardados no ficheiro.

5. Vê um erro antes de correres. Na linha 3, apaga a aspa que fecha o texto, sem guardar. O que deves ver: o `)` do fim passa à cor dos textos, e no separador aparece a bola cheia das alterações por guardar. Com a extensão, aparece também uma linha ondulada perto do erro, ao fim de uns segundos.

6. Abre o painel dos problemas, no menu View, com a opção Problems. O que deves ver: um ou dois problemas na linha 3. Carrega nele, e o cursor salta para a linha. Sem a extensão, a lista fica vazia. Depois desfaz a alteração com Ctrl+Z, ou Cmd+Z, até a bola voltar a ser um X. No mapa, escreve "sublinhado" no editor e "problemas" no painel de baixo.

7. Experimenta as sugestões. No fim da linha 3, carrega em Enter e escreve `pri`. O que deves ver: uma lista com `print`. Carrega em Tab para a aceitar e escreve `(`: o VS Code escreve sozinho o `)`. Se abrir uma caixa de explicação, fecha-a com Esc. No mapa, escreve "sugestões" no editor. Depois apaga a linha 4 inteira: com o cursor nela, carrega em Ctrl+Shift+K, ou Cmd+Shift+K no macOS. Guarda.

8. Olha para a barra de estado. Põe o cursor no fim da linha 2. O que deves ver, entre outras coisas: `Ln 2, Col 22`, linha 2, coluna 22. É assim que confirmas a linha de que fala uma mensagem de erro. No mapa, escreve "barra de estado" na faixa do fundo.

9. Corre o `ola.py` com o botão: o triângulo no canto de cima, à direita do editor, com o nome Run Python File. Carrega nele. O que deves ver: uma linha comprida, que não escreveste, e por baixo as duas linhas do `ola.py`. A linha comprida é o comando que o botão escreveu por ti, com os caminhos completos. No Windows, começa por `&`, que podes ignorar. No mapa, escreve "botão de correr" no canto do editor. Sem a extensão, não há triângulo, e lês este passo sem o fazer.

### Paragem 3

O teu mapa da janela tem nove ferramentas, cada uma na sua zona, e o `ola.py` está como estava. Corre com o comando e com o botão.

Pensa antes de continuares: no passo 5, o VS Code mostrou a aspa por fechar antes de correres. Quer isto dizer que executou o programa? A resposta: não. O editor só lê o texto e pinta-o. Quem executa é o interpretador, quando corres o programa.

## Fase 4: Do `Escreve:` ao `print`

Passas para Python o ecrã de abertura do duelo de dados, trocando cada `Escreve:` por um `print`. Decides o resultado esperado antes de correr, e comparas. Rever: [Do `Escreve:` ao `print`](../01-do-algoritmo-ao-programa.md#do-escreve-ao-print).

O algoritmo, em pseudocódigo:

```text
Escreve: "DUELO DE DADOS"
Escreve: "Dois jogadores, no máximo cinco rondas."
Escreve: "Em cada ronda, cada jogador escolhe um número de 1 a 6."
Escreve: "Quem escolher o número maior ganha a ronda."
Escreve: "O duelo acaba quando alguém ganha três rondas."
```

1. Antes de escreveres o programa, decide o resultado esperado: o que aparece no ecrã, linha a linha. A resposta: as cinco linhas, pela ordem do algoritmo, sem aspas.

   ```text
   DUELO DE DADOS
   Dois jogadores, no máximo cinco rondas.
   Em cada ronda, cada jogador escolhe um número de 1 a 6.
   Quem escolher o número maior ganha a ronda.
   O duelo acaba quando alguém ganha três rondas.
   ```

2. Cria o ficheiro `abertura.py`, como na fase 1, com esta primeira versão, só com o título:

   ```python
   # abertura.py: o ecrã de abertura do duelo de dados, o projeto 1 da algoritmia.
   # Escreve o nome do jogo e as regras, uma linha de cada vez, de cima para baixo.
   print("DUELO DE DADOS")
   ```

   Guarda e corre com `python abertura.py`. O que deves ver: `DUELO DE DADOS`.

3. Acrescenta as regras. No fim do ficheiro, acrescenta:

   ```python
   print("Dois jogadores, no máximo cinco rondas.")
   print("Em cada ronda, cada jogador escolhe um número de 1 a 6.")
   print("Quem escolher o número maior ganha a ronda.")
   print("O duelo acaba quando alguém ganha três rondas.")
   ```

   Guarda e corre. O que deves ver: as cinco linhas do passo 1. Compara-as, uma a uma: se forem iguais, o programa passou o teste.

### Paragem 4

O `abertura.py` mostra o ecrã de abertura do duelo de dados, igual ao resultado esperado.

Pensa antes de continuares: se trocares a ordem de duas linhas `print`, o que muda no ecrã? A resposta: as duas linhas aparecem trocadas, porque o Python executa pela ordem do ficheiro.

## Fase 5: Os três tipos de erro

Provocas um erro de execução e um erro de lógica no `abertura.py`, e comparas com o erro de sintaxe da fase 1. Cada tipo reconhece-se pelo que acontece no ecrã. Rever: [Os três tipos de erro](../01-do-algoritmo-ao-programa.md#os-três-tipos-de-erro).

1. Provoca um erro de execução. Na linha 6, muda o `print` para `Print`, com P maiúsculo. Com a extensão, o `Print` pode aparecer sublinhado. Prevê se aparece alguma linha do ecrã, guarda e corre. O que deves ver:

   ```text
   DUELO DE DADOS
   Dois jogadores, no máximo cinco rondas.
   Em cada ronda, cada jogador escolhe um número de 1 a 6.
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\lp-python\abertura.py", line 6, in <module>
       Print("Quem escolher o número maior ganha a ronda.")
       ^^^^^
   NameError: name 'Print' is not defined. Did you mean: 'print'?
   ```

   As três primeiras linhas apareceram, e o programa parou na linha 6, porque o Python não conhece `Print`. A última linha quer dizer "o nome 'Print' não está definido. Querias dizer 'print'?". É um erro de execução, porque as linhas de antes correram.

2. Corrige: volta a pôr `print` em minúsculas, guarda e corre. O que deves ver: as cinco linhas.

3. Provoca um erro de lógica. Põe o cursor na linha `print("DUELO DE DADOS")`, sem selecionar nada, e carrega em Ctrl+X, ou Cmd+X: o VS Code corta a linha inteira. Põe o cursor no fim da última linha, carrega em Enter e cola, com Ctrl+V, ou Cmd+V. Guarda e corre. O que deves ver:

   ```text
   Dois jogadores, no máximo cinco rondas.
   Em cada ronda, cada jogador escolhe um número de 1 a 6.
   Quem escolher o número maior ganha a ronda.
   O duelo acaba quando alguém ganha três rondas.
   DUELO DE DADOS
   ```

   Não há mensagem nem nada sublinhado, mas o nome do jogo aparece no fim. Só dás pelo erro porque comparas com o resultado esperado da fase 4.

4. Corrige: corta outra vez a linha do título, da mesma maneira. Põe o cursor na linha 3, a primeira das regras, e cola: a linha entra por cima dela. Guarda, corre e compara com o resultado esperado.

### Paragem 5

O `abertura.py` está outra vez certo:

```python
# abertura.py: o ecrã de abertura do duelo de dados, o projeto 1 da algoritmia.
# Escreve o nome do jogo e as regras, uma linha de cada vez, de cima para baixo.
print("DUELO DE DADOS")
print("Dois jogadores, no máximo cinco rondas.")
print("Em cada ronda, cada jogador escolhe um número de 1 a 6.")
print("Quem escolher o número maior ganha a ronda.")
print("O duelo acaba quando alguém ganha três rondas.")
```

Os dois comentários dizem o que é o ficheiro, e os cinco `print` seguem a ordem do pseudocódigo.

Pensa antes de terminares: qual dos três erros é o mais difícil de encontrar? A resposta: o de lógica, porque não há mensagem nem sublinhado. Só se encontra comparando o obtido com o esperado, decidido antes de correr.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco. Uma bola cheia no separador, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? O caminho antes do `>` ou do `%`, como `C:\Users\aluno\Documents\lp-python>`, tem de acabar em `lp-python`. Se não acabar, abre um terminal novo, no menu Terminal.
3. Estás na consola sem quereres? Se a linha começa por `>>>`, escreve `exit()`.
4. A tua mensagem tem outras palavras? As deste laboratório são as do Python 3.14. O nome do erro, antes dos dois pontos, é o mesmo noutras versões.

### O Windows diz que não conhece o `python`, ou abre a Microsoft Store

Fecha a loja e usa `py`, como em `py ola.py`. Se nenhum dos dois funcionar, avisa o professor, porque o Python pode não estar instalado.

### `can't open file` e `No such file or directory`

O terminal não está na pasta do ficheiro, ou o nome no comando tem um erro. Confirma a pasta e o nome, com o `.py` no fim.

### Não há triângulo no canto de cima do editor

O botão vem com a extensão Python, e só aparece nos ficheiros `.py`. Enquanto não houver botão, corre os programas com o comando.

### O programa corre e não escreve nada

Confirma que cada linha tem `print`, e não `Escreve:`. Uma linha copiada do pseudocódigo não dá erro, mas também não escreve nada.

## Desafios

1. Uma linha em branco. Muda o `abertura.py` para aparecer uma linha em branco entre o nome do jogo e as regras.

2. O ecrã de abertura de outro jogo. Escolhe um jogo de cartas ou de tabuleiro que conheças, como o jogo do galo. Escreve em pseudocódigo um ecrã de abertura com o nome e três regras, e depois passa-o para Python, num ficheiro novo. Testa-o com o resultado esperado, decidido antes de correr.

3. O erro que ninguém vê. Num dos teus programas, provoca um erro de lógica que não troque a ordem das linhas. Dá-o a um colega, com o resultado esperado, e vê se ele o encontra.

4. Sem o VS Code. Num computador com Windows, abre o `ola.py` no Bloco de Notas. No Explorador de Ficheiros, carrega no ficheiro com o botão direito, escolhe Abrir com e depois Bloco de Notas. Muda o texto da linha 2, guarda e corre-o no terminal. Compara o Bloco de Notas com o VS Code e escreve, num comentário no fim do `ola.py`, o que lhe falta.

## Antes de terminares

- [ ] O `ola.py` corre e tem, num comentário no fim, o registo da execução, com o comando e a versão do Python.
- [ ] O `abertura.py` corre e escreve as cinco linhas, pela ordem do pseudocódigo.
- [ ] O mapa da janela está desenhado, com as nove ferramentas da fase 3.

![Rodapé](../../imagens/rodape.png)
