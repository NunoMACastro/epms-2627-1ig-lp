![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Do algoritmo ao programa

Laboratório do tema Do algoritmo ao programa, do módulo Desenvolver programas em linguagem estruturada. Vais escrever os teus primeiros programas em Python, pô-los a correr no computador e conhecer as ferramentas do VS Code. Um deles é o ecrã de abertura do duelo de dados, que já conheces do projeto 1. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](01-do-algoritmo-ao-programa.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

No fim, tens dois programas em Python numa pasta tua. O primeiro, `ola.py`, escreve duas linhas no ecrã e serve para confirmar que o Python corre no teu computador. O segundo, `abertura.py`, mostra o nome e as regras do duelo de dados. É a passagem para Python de um algoritmo escrito em pseudocódigo, e vais confirmar que o computador escreve exatamente o que previste.

Pelo caminho, ficas a saber abrir uma pasta no VS Code, criar um ficheiro, guardá-lo e corrê-lo no terminal. Ficas também a saber experimentar uma linha na consola do Python, e conheces as ferramentas que o VS Code junta na mesma janela. E aprendes a reconhecer os três tipos de erro que um programa pode ter. No caderno, fazes o **registo da execução**, com o comando que funciona no teu computador e a versão do Python. Fazes também o **mapa da janela** do VS Code, com o sítio de cada ferramenta.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | `ola.py` | O primeiro programa corre no terminal, e o comando que funciona está no caderno |
| 2 | Nada no disco; experimentas no terminal e na consola do Python | Sabes a versão do teu Python e tens o registo da execução no caderno |
| 3 | Nada de novo no disco; percorres as ferramentas do VS Code com o `ola.py` | Tens o mapa da janela no caderno e corres o `ola.py` também com o botão |
| 4 | `abertura.py` | O ecrã de abertura do duelo de dados aparece no terminal, igual ao que previste |
| 5 | `abertura.py`, com erros provocados e corrigidos | Sabes dizer de que tipo é cada erro e como o encontraste |

No fim, a tua pasta fica assim:

```text
lp-python/
├── ola.py
└── abertura.py
```

## Palavras que vais usar

- Programa: um algoritmo escrito numa linguagem que o computador consegue executar. Para saber mais, vê a secção "Um programa é um algoritmo escrito para o computador" do [guia](01-do-algoritmo-ao-programa.md).
- Python: a linguagem de programação que vais usar neste módulo.
- Interpretador: o programa que lê o teu programa, confirma que está bem escrito e executa as instruções por ordem, de cima para baixo. É o que se instala quando se instala o Python.
- Editor de código: um editor de texto feito para escrever programas, com cores, números de linha e ajudas à escrita. Nas aulas, é o VS Code.
- IDE, ambiente de desenvolvimento integrado: um programa que junta numa só janela as ferramentas para escrever, correr e corrigir programas. As ferramentas conhecem a linguagem. Para saber mais, vê a secção "O IDE: as ferramentas numa só janela" do [guia](01-do-algoritmo-ao-programa.md).
- Extensão: um programa pequeno que se acrescenta ao VS Code para lhe dar ferramentas novas. Com a extensão Python, o VS Code funciona como um IDE para Python.
- Separador: a aba no topo do editor, com o nome do ficheiro aberto.
- Realce de sintaxe: as cores com que o editor mostra cada parte do programa. Não ficam guardadas no ficheiro.
- Sugestões: a lista de nomes que o VS Code propõe enquanto escreves.
- Sublinhado dos erros: a linha ondulada por baixo de um erro de sintaxe ou de um nome que o VS Code não conhece.
- Painel dos problemas (Problems): a lista do que o VS Code sublinhou, com o número da linha de cada problema.
- Barra de estado: a faixa no fundo da janela do VS Code, que mostra, entre outras coisas, a linha e a coluna do cursor.
- Botão de correr: o triângulo no canto de cima do editor, que corre o ficheiro aberto sem escreveres o comando.
- Ficheiro `.py`: o ficheiro de texto onde fica guardado um programa em Python. O nome acaba sempre em `.py`.
- Terminal: uma janela onde se escrevem comandos, um por linha, e se carrega em Enter. O VS Code tem um terminal na parte de baixo.
- Comando: uma ordem escrita no terminal, como `python ola.py`.
- Consola do Python: o modo em que o Python executa uma linha de cada vez e mostra logo o resultado. Reconhece-se pelo sinal `>>>` no início da linha.
- `print`: a instrução do Python que escreve no ecrã. É o `Escreve:` do pseudocódigo.
- Comentário: uma nota para quem lê o código, a seguir a um sinal `#` fora das aspas. O Python não a executa.
- Sintaxe: as regras de escrita de uma linguagem, como as aspas à volta de um texto ou os parênteses do `print`.
- Erro de sintaxe: um erro na escrita do programa. O Python recusa o programa inteiro, antes de executar qualquer linha.
- Erro de execução: um erro que para o programa a meio, numa linha que o Python não consegue executar. As linhas de antes já correram.
- Erro de lógica: um erro que não dá mensagem nenhuma. O programa corre até ao fim, mas o resultado não é o esperado.
- Registo da execução: uma nota no caderno com o que precisas para voltar a correr o programa. Leva a data, o computador, o comando, a versão do Python e o que apareceu.

## O que precisas

- O Python 3, o interpretador. Não precisas de fazer nada agora: na fase 2, confirmas que o tens, com o comando `python --version`. Deve aparecer uma linha como `Python 3.13.2`, com os números da versão que está instalada. O primeiro número tem de ser 3.
- O VS Code, o editor de código das aulas, onde escreves os programas e abres o terminal. Abre-se como qualquer outra aplicação do computador.
- A extensão Python do VS Code, da Microsoft, que acrescenta ao VS Code ferramentas que conhecem o Python, como um botão para correr o programa. Na fase 3, confirmas se está instalada. Sem ela, o laboratório faz-se na mesma, e a fase 3 diz o que muda.
- O caderno, para o registo da execução, para o mapa da janela e para as tabelas que vais fazendo nas paragens.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou apontar outra linha. O nome do erro, a palavra antes dos dois pontos na última linha, é o mesmo.

Os nomes dos menus e dos botões são os do VS Code em inglês. Foram confirmados a 27 de outubro e a 2 de novembro de 2026. Se o teu estiver em português, os menus estão no mesmo sítio, com o nome traduzido.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco, e não o que vês no ecrã. Guarda com Ctrl+S, ou Cmd+S no macOS. No VS Code, uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor mostra a pasta onde estás. Tem de acabar em `lp-python`, antes do sinal `>` no Windows, ou do `%` no macOS. Se não acabar, fecha o terminal e abre outro, no menu Terminal, com a opção New Terminal. O terminal novo abre-se na pasta que tens aberta no VS Code.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. Copiaste o código à mão? Confirma as aspas no início e no fim de cada texto, os dois parênteses de cada `print` e o `print` em minúsculas.

## Preparar o projeto

1. Cria uma pasta para os teus programas de Python, com o nome `lp-python`, no sítio onde costumas guardar os trabalhos, por exemplo em Documentos. Uma pasta própria impede que os programas se misturem com outros ficheiros. O nome não tem espaços nem acentos, para se escrever sem problemas no terminal.

2. Abre o VS Code e abre a pasta. No menu File, escolhe Open Folder..., isto é, "abrir pasta", e escolhe `lp-python`. Se o VS Code perguntar se confias nos autores dos ficheiros desta pasta, responde que sim, porque a pasta é tua. O que deves ver: à esquerda, no painel Explorer, o nome `LP-PYTHON`, ainda sem ficheiros.

3. No caderno, abre uma página com o título "Registo da execução". Vais preenchê-la nas fases 1 e 2.

## Fase 1: Correr o primeiro programa

Na algoritmia, quem executava os algoritmos eras tu, com papel e lápis. Agora vais pôr o computador a fazê-lo. Para isso, escreves as instruções num ficheiro e mandas o interpretador do Python executá-lo. O `Escreve:` do pseudocódigo passa a chamar-se `print`, com o texto entre parênteses. Para saber mais, lê a secção "Correr um programa" do [guia](01-do-algoritmo-ao-programa.md).

1. Cria o primeiro ficheiro. No painel Explorer, passa o rato por cima de `LP-PYTHON` e carrega no primeiro ícone, New File..., isto é, "novo ficheiro". Escreve o nome `ola.py` e carrega em Enter. O `.py` no fim do nome diz ao VS Code e ao Python que é um programa em Python. O ficheiro abre-se à direita, vazio. Escreve nele este conteúdo, que é o ficheiro completo:

   ```python
   # ola.py: o primeiro programa, para confirmar que o Python corre neste computador.
   print("Olá, Python!")
   print("O meu primeiro programa correu.")
   ```

   Leitura guiada: a primeira linha começa com `#`, e por isso é um comentário. Diz o nome do ficheiro e para que serve, e o Python não a executa. As duas linhas seguintes são instruções `print`. Cada uma escreve no ecrã o texto que está entre aspas, pela ordem em que estão. As aspas marcam onde o texto começa e acaba, e não aparecem no ecrã.

   Se aparecer, no canto de baixo do VS Code, um aviso a recomendar uma extensão de Python, fecha-o por agora. Na fase 3, vês para que serve a extensão e confirmas se já está instalada.

2. Guarda o ficheiro, com Ctrl+S, ou Cmd+S no macOS. O Python lê o ficheiro guardado no disco. Um ficheiro por guardar ainda não tem estas linhas, para o Python.

3. Abre o terminal. No menu Terminal, escolhe New Terminal. O que deves ver: uma janela na parte de baixo do VS Code. Tem uma linha que acaba no nome da pasta, `lp-python`, e o cursor à espera. É aí que escreves os comandos.

4. Antes de correres, prevê: o que aparece no terminal, e por que ordem? Depois, no terminal, escreve este comando e carrega em Enter:

   ```bash
   python ola.py
   ```

   O comando tem duas partes. `python` chama o interpretador, e `ola.py` diz-lhe que ficheiro deve executar. No macOS, o comando é `python3 ola.py`.

   O que deves ver:

   ```text
   Olá, Python!
   O meu primeiro programa correu.
   ```

   Isto quer dizer que o interpretador encontrou o ficheiro e executou as duas instruções, de cima para baixo. A linha do comentário não aparece. Se o Windows responder que não conhece o `python`, ou se abrir a Microsoft Store, fecha a loja e experimenta `py ola.py`, que faz o mesmo. Se aparecer outra coisa, vê os [problemas frequentes](#problemas-frequentes).

5. Escreve no caderno, no registo da execução, o comando que funcionou no teu computador: `python`, `py` ou `python3`. É esse que vais usar em todos os programas deste módulo, sempre que este laboratório disser `python`.

6. Provoca um erro de propósito: apaga a aspa que fecha o texto da terceira linha, para ficar `print("O meu primeiro programa correu.)`. Guarda e corre outra vez o mesmo comando. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\lp-python\ola.py", line 3
       print("O meu primeiro programa correu.)
             ^
   SyntaxError: unterminated string literal (detected at line 3)
   ```

   A primeira linha mostra o caminho do ficheiro no teu computador, e muda de computador para computador. A seguir vem o número da linha onde está o problema, `line 3`, e a própria linha. O sinal `^` por baixo dela marca onde o Python deu pelo problema. Está na aspa que abre o texto, porque é a partir dela que o texto nunca acaba. A última linha é a mais importante: quer dizer "erro de sintaxe: texto por terminar, detetado na linha 3". O Python não sabe onde acaba o texto, porque falta a aspa que o fecha.

   Repara que o "Olá, Python!" da linha 2, que estava certa, também não apareceu. Um erro de sintaxe faz o Python recusar o programa inteiro, antes de executar qualquer linha.

7. Corrige: volta a pôr a aspa no fim do texto, guarda e corre outra vez, até veres as duas linhas.

### Paragem 1

O `ola.py` corre e escreve as duas linhas. Sabes criar um ficheiro, guardá-lo e corrê-lo no terminal, e tens no caderno o comando que funciona no teu computador.

Pensa antes de continuares: porque é que, com o erro na linha 3, nem o "Olá, Python!" da linha 2 apareceu? A resposta: antes de executar, o interpretador lê o ficheiro todo e confirma que está bem escrito. Ao encontrar um erro de sintaxe, recusa o programa e não executa nenhuma linha, nem as que estão antes do erro.

## Fase 2: A versão do Python e a consola

Os computadores não têm todos o mesmo Python. A versão diz qual é, e pode explicar porque é que uma mensagem de erro aparece com outras palavras num computador e não noutro. Por isso, a versão entra no registo da execução. Nesta fase vais também conhecer a consola do Python, onde se experimenta uma linha de cada vez, sem criar um ficheiro. Para saber mais, lê as secções "A consola do Python" e "O registo da execução" do [guia](01-do-algoritmo-ao-programa.md).

1. No terminal, escreve o comando seguinte e carrega em Enter. Usa o comando que escreveste no caderno: se for `py`, escreve `py --version`; no macOS, `python3 --version`.

   ```bash
   python --version
   ```

   O que deves ver: uma só linha, como `Python 3.13.2`. Os números podem ser outros, porque dizem a versão instalada no teu computador. O primeiro tem de ser 3, que quer dizer que é o Python 3. Se for 2, avisa o professor, porque o Python 2 é uma versão antiga, que já não se usa.

2. Completa o registo da execução, no caderno. Por exemplo:

   ```text
   Registo da execução
   Data: 29 de outubro de 2026
   Computador: o da sala, lugar 7
   Comando que funciona: python
   Versão: Python 3.13.2
   Programa: ola.py
   O que apareceu: as duas linhas, pela ordem do programa
   Erro provocado: a aspa por fechar, SyntaxError na linha 3
   ```

   Os teus valores são os do teu computador. Se trabalhares também em casa, faz um segundo registo para esse computador, porque o comando e a versão podem ser outros.

3. Entra na consola do Python. No terminal, escreve só `python`, sem nome de ficheiro, e carrega em Enter. Usa o teu comando: `py`, ou `python3` no macOS. O que deves ver: duas linhas em inglês, a primeira com a versão do Python, e por baixo, numa linha à parte, `>>>`. No Python 3.14, a consola pode mostrar o texto a cores. Isto quer dizer que estás na consola, à espera de uma linha de Python.

4. Antes de escreveres cada linha, prevê o que vai aparecer. Depois escreve-a a seguir ao `>>>` e carrega em Enter:

   ```text
   >>> print("Olá da consola")
   Olá da consola
   >>> "DUELO DE DADOS"
   'DUELO DE DADOS'
   ```

   A primeira linha executa-se logo, e o texto aparece sem aspas, como num programa. Na segunda, não há `print`. Quando uma linha é só um texto, a consola mostra-o, com aspas simples à volta para dizer que é um texto. Num programa guardado num ficheiro, uma linha só com um texto não escreve nada: só o `print` escreve.

5. Provoca um erro de propósito: escreve na consola o comando `python ola.py` e carrega em Enter. O que deves ver:

   ```text
   >>> python ola.py
     File "<python-input-2>", line 1
       python ola.py
              ^^^
   SyntaxError: invalid syntax
   ```

   O nome entre aspas, na linha com `File`, muda conforme as linhas que já escreveste na consola, e num Python mais antigo é `<stdin>`. A mensagem quer dizer "erro de sintaxe: escrita inválida". Na consola só se escreve Python, e `python ola.py` é um comando do terminal, e não uma linha de Python. A regra é esta: com `>>>`, escreves Python; sem `>>>`, escreves comandos.

6. Sai da consola: escreve `exit()` e carrega em Enter. O que deves ver: a linha do terminal outra vez, a acabar em `lp-python`.

### Paragem 2

Tens no caderno o registo da execução, com o comando e a versão do teu Python. Sabes entrar e sair da consola. Na pasta não apareceu nenhum ficheiro novo, porque o que se escreve na consola não fica guardado.

Pensa antes de continuares: quando é que usas a consola, e quando é que usas um ficheiro `.py`? A resposta: a consola serve para experimentar uma linha e ver logo o resultado. Um programa que queres guardar, corrigir e voltar a correr escreve-se num ficheiro `.py`.

## Fase 3: As ferramentas do VS Code

Até aqui, usaste o VS Code para escrever o `ola.py` e para abrir o terminal. O editor, o explorador e o terminal estão todos na mesma janela. Com a extensão Python, o VS Code junta-lhes ferramentas que conhecem o Python, como um botão que corre o programa e um sublinhado nos erros. Passa então a funcionar como um ambiente de desenvolvimento integrado, ou IDE. Nesta fase vais encontrar essas ferramentas uma a uma, com o `ola.py`. Vais também desenhar no caderno o mapa da janela, com o sítio de cada uma. Não precisas de as decorar. Precisas de saber que existem, para as ires buscar quando fizerem falta.

Um IDE ajuda, mas nem sempre é preciso. Para experimentar uma linha, chega a consola, como na fase 2. Para mudar uma palavra num ficheiro, num computador sem o VS Code, chega um editor de texto simples, como o Bloco de Notas. Um editor destes guarda só o texto, sem formatação. Para saber mais, lê no [guia](01-do-algoritmo-ao-programa.md) estas três secções:

- "Do editor de texto ao editor de código";
- "O IDE: as ferramentas numa só janela";
- "Quando é preciso um IDE, e quando não".

1. Desenha o mapa da janela. Olha para a janela do VS Code e desenha no caderno um retângulo grande, dividido nestas cinco zonas:

   - a coluna estreita dos ícones, à esquerda;
   - o painel do explorador, ao lado dela;
   - o editor, ao centro;
   - o painel de baixo, onde está o terminal;
   - a barra de estado, a faixa fina no fundo da janela.

   Deixa espaço em cada zona, porque vais escrever lá o nome das ferramentas que encontrares.

2. Confirma se a extensão Python está instalada. Os passos seguintes dependem dela. Na coluna dos ícones, carrega no ícone das extensões, Extensions, o dos quatro quadrados. Na caixa de procura que aparece no topo, escreve `Python`. O que deves ver: uma lista de extensões, com uma chamada Python, da Microsoft, no topo. Se ela tiver um botão Install, isto é, "instalar", não está instalada: avisa o professor antes de a instalares. Se não tiver esse botão, já está instalada. Escreve no caderno se a tens ou não. No mapa, escreve "extensões" na coluna dos ícones. Depois volta ao explorador, com um clique no primeiro ícone da coluna.

3. No explorador, o painel Explorer, carrega no `ola.py`. O que deves ver: o ficheiro abre-se no editor, ao centro, com um separador no topo com o nome `ola.py`. No mapa, escreve "explorador" no painel da esquerda, "editor e separadores" ao centro e "terminal integrado" no painel de baixo. Estas três já as usaste na fase 1.

4. Olha para a margem da esquerda do editor. Tem os números das linhas: 1, 2 e 3. Repara também nas cores. O comentário tem uma cor, a palavra `print` outra, e os textos entre aspas outra. A estas cores chama-se realce de sintaxe. Ajudam a ver o que é cada parte do programa, e não ficam guardadas no ficheiro: o ficheiro tem só o texto.

5. Vê um erro antes de correres. Na linha 3, apaga a aspa que fecha o texto, como fizeste na fase 1, mas desta vez não guardes. O que deves ver: o `)` do fim da linha passa a ter a cor dos textos. O editor também já não sabe onde o texto acaba. No separador, no lugar do X, aparece a bola cheia das alterações por guardar. Com a extensão Python, aparece ainda uma linha ondulada perto do erro: é o sublinhado dos erros. Na primeira vez, pode levar uns segundos a aparecer. Sem a extensão, não aparece nenhuma linha ondulada, mas a cor muda na mesma.

6. Abre o painel dos problemas. No menu View, escolhe Problems. O que deves ver, com a extensão Python: no painel de baixo, uma lista com pelo menos um problema e o número da linha, 3. Carrega no problema, e o cursor salta para a linha 3. Sem a extensão, a lista fica vazia, porque o VS Code sozinho só pinta o texto e não confirma se o programa está bem escrito. Depois, carrega no texto da linha 3, no editor, e desfaz a alteração com Ctrl+Z, ou Cmd+Z no macOS. A aspa volta, a linha volta às cores de antes e a bola volta a ser um X. No mapa, escreve "sublinhado dos erros" no editor e "painel dos problemas" no painel de baixo.

7. Experimenta as sugestões e o fecho automático. Põe o cursor no fim da linha 3, carrega em Enter, para abrires uma linha nova, e escreve só `pri`. O que deves ver: uma lista pequena por baixo do cursor, com `print`. Se a lista não aparecer, carrega em Ctrl+Espaço. Carrega em Tab, ou em Enter, e o VS Code completa a palavra. Escreve agora `(`. O que deves ver: o VS Code escreve sozinho o `)`, e o cursor fica entre os dois parênteses. Pode abrir-se também uma caixa com uma explicação do `print`, em inglês: fecha-a com a tecla Esc. No mapa, escreve "sugestões" no editor. Depois, apaga a linha 4 inteira, até o cursor voltar ao fim da linha 3, e guarda. O `ola.py` volta a ter só as três linhas.

8. Olha para a barra de estado. Põe o cursor no fim da linha 2, a seguir ao último parêntese. O que deves ver, na barra de estado, entre outras coisas: `Ln 2, Col 22`. Quer dizer linha 2, coluna 22: o cursor está na linha 2, depois do 21.º carácter, o último. Quando uma mensagem de erro disser `line 2`, é assim que confirmas que o cursor está na linha certa. No mapa, escreve "barra de estado" na faixa do fundo.

9. Corre o `ola.py` com o botão. Com o `ola.py` à frente no editor, procura um triângulo no canto de cima, à direita. Passa o rato por cima dele: aparece o nome Run Python File, isto é, "correr o ficheiro de Python". Antes de carregares, prevê o que aparece no terminal. Depois carrega no triângulo. O que deves ver: no terminal, uma linha comprida, que não escreveste, e por baixo as duas linhas do `ola.py`. O botão pode abrir um terminal novo para isso, no painel de baixo.

   A linha comprida é o comando que o botão escreveu por ti. Tem o caminho completo do interpretador do Python, um espaço e o caminho completo do `ola.py`. O caminho completo de um ficheiro são as pastas por onde se chega a ele, desde o disco. É o mesmo que `python ola.py`, com os caminhos inteiros. No Windows, a linha começa por `&`, um sinal que o terminal do Windows pede antes de um caminho, e que podes ignorar. O botão também guarda o ficheiro antes de o correr. No registo da execução, fica o comando que escreves tu, porque é ele que funciona em qualquer terminal. Sem a extensão, não há triângulo: lê este passo sem o fazer. No mapa, escreve "botão de correr" no canto de cima do editor.

### Paragem 3

O teu mapa da janela tem nove ferramentas, cada uma na sua zona:

- no painel da esquerda, o explorador;
- ao centro, o editor e os separadores, o sublinhado dos erros, as sugestões e, no canto de cima, o botão de correr;
- no painel de baixo, o terminal integrado e o painel dos problemas;
- na faixa do fundo, a barra de estado;
- na coluna dos ícones, as extensões.

O `ola.py` tem outra vez as três linhas e corre com o comando e com o botão.

Pensa antes de continuares: no passo 5, o VS Code mostrou a aspa por fechar antes de correres. Quer isto dizer que o VS Code executou o programa? A resposta: não. O editor só lê o texto e pinta-o pelas regras de escrita do Python. Quem executa o programa é o interpretador, e só quando o corres, com o comando ou com o botão.

## Fase 4: Do pseudocódigo ao programa

No projeto 1, escreveste o algoritmo do duelo de dados. Um jogo destes começa quase sempre por um ecrã de abertura, com o nome e as regras. Em pseudocódigo, esse ecrã é uma sequência de instruções `Escreve:`, executadas uma depois da outra:

```text
Escreve: "DUELO DE DADOS"
Escreve: "Dois jogadores, no máximo cinco rondas."
Escreve: "Em cada ronda, cada jogador escolhe um número de 1 a 6."
Escreve: "Quem escolher o número maior ganha a ronda."
Escreve: "O duelo acaba quando alguém ganha três rondas."
```

Passar este algoritmo para Python é trocar cada `Escreve:` por um `print`, com o mesmo texto entre parênteses, pela mesma ordem. Antes de o computador o executar, vais dizer o que esperas ver. Depois comparas. É assim que se testa um programa: o resultado esperado escreve-se antes de correr. Para saber mais, lê a secção "Do `Escreve:` ao `print`" do [guia](01-do-algoritmo-ao-programa.md).

1. Escreve no caderno o resultado esperado: o que deve aparecer no ecrã, linha a linha, quando o algoritmo for executado. Lembra-te de que as aspas não aparecem.

   A resposta: as cinco linhas, pela ordem do algoritmo, sem aspas.

   ```text
   DUELO DE DADOS
   Dois jogadores, no máximo cinco rondas.
   Em cada ronda, cada jogador escolhe um número de 1 a 6.
   Quem escolher o número maior ganha a ronda.
   O duelo acaba quando alguém ganha três rondas.
   ```

2. Cria um ficheiro novo, `abertura.py`, como na fase 1, e escreve-lhe este conteúdo:

   ```python
   # abertura.py: o ecrã de abertura do duelo de dados, o projeto 1 da algoritmia.
   # Escreve o nome do jogo e as regras, uma linha de cada vez, de cima para baixo.
   print("DUELO DE DADOS")
   print("Dois jogadores, no máximo cinco rondas.")
   print("Em cada ronda, cada jogador escolhe um número de 1 a 6.")
   print("Quem escolher o número maior ganha a ronda.")
   print("O duelo acaba quando alguém ganha três rondas.")
   ```

   Leitura guiada: as duas primeiras linhas são comentários. A primeira diz o que é o ficheiro, e a segunda diz como funciona. A seguir vêm cinco instruções `print`, uma por cada `Escreve:` do pseudocódigo, pela mesma ordem e com o mesmo texto. Cada `print` começa encostado à margem, numa linha só para ele.

3. Guarda e corre o programa, com o teu comando:

   ```bash
   python abertura.py
   ```

   O que deves ver: as cinco linhas do resultado esperado, pela mesma ordem. Compara-as com o que escreveste no caderno, linha a linha. Se forem iguais, o programa passou o teste. Se houver uma diferença, procura-a no código, na mesma linha, e confirma que o texto é o mesmo do pseudocódigo.

4. No caderno, faz uma tabela com três colunas: "Pseudocódigo", "Python" e "O que muda". É o teu quadro de tradução, e serve para consultares quando passares outros algoritmos para Python. Escreve-lhe estas duas linhas:

   | Pseudocódigo | Python | O que muda |
   | --- | --- | --- |
   | `Escreve: "Olá"` | `print("Olá")` | `print` em minúsculas, e o texto entre parênteses |
   | não havia | `# comentário` | uma nota para quem lê, que o Python não executa |

### Paragem 4

O `abertura.py` mostra o ecrã de abertura do duelo de dados, igual ao resultado esperado que escreveste antes de correr.

Pensa antes de continuares: se trocares a ordem de duas linhas `print`, o que muda no ecrã? A resposta: as duas linhas aparecem trocadas. O Python executa as instruções exatamente pela ordem em que estão no ficheiro, de cima para baixo, como numa sequência do pseudocódigo.

## Fase 5: Os três tipos de erro

Na fase 1 viste um erro de sintaxe: o Python recusou o programa inteiro, e nenhuma linha correu. Na fase 3 viste o mesmo erro no editor, antes de correres. Há mais dois tipos de erro, e cada um se reconhece de outra maneira. Num erro de execução, o programa começa a correr e para a meio, com uma mensagem. Num erro de lógica, não há mensagem nenhuma: o programa corre até ao fim, mas o resultado não é o esperado. Saber que tipo de erro é diz-te onde procurar. Para saber mais, lê a secção "Os três tipos de erro" do [guia](01-do-algoritmo-ao-programa.md).

1. Provoca um erro de execução. No `abertura.py`, na linha 6, muda o `print` para `Print`, com P maiúsculo. A linha fica `Print("Quem escolher o número maior ganha a ronda.")`. Antes de guardares, olha para o editor. Com a extensão Python, o `Print` pode aparecer sublinhado, com uma cor diferente da do erro da aspa. É um aviso de que o VS Code não conhece esse nome. Antes de correres, prevê: aparece alguma linha do ecrã de abertura? Guarda e corre. O que deves ver:

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

   Desta vez, as três primeiras linhas do ecrã apareceram. O programa estava bem escrito, e o Python começou a executá-lo. Parou na linha 6, porque não conhece nenhuma instrução chamada `Print`. Para o Python, uma letra maiúscula e uma minúscula são letras diferentes.

   A mensagem chama-se traceback, e lê-se de baixo para cima. A última linha diz o nome do erro, `NameError`, um erro de nome. Diz também "o nome 'Print' não está definido. Querias dizer 'print'?". Por cima dela estão a instrução que falhou e, numa linha à parte, os sinais `^`, por baixo da parte suspeita. Mais acima, a linha com `File` diz em que linha está, `line 6`, e o `in <module>` quer dizer que foi na parte principal do programa. A primeira linha, `Traceback (most recent call last)`, só anuncia que vem aí a mensagem de um erro de execução.

   O VS Code pode ter avisado antes, mas o tipo de erro não se decide pelo sublinhado. Decide-se pelo que aconteceu quando correste: as linhas de antes apareceram, e o programa parou na linha 6. Por isso, é um erro de execução.

2. Corrige: volta a pôr o `print` em minúsculas, guarda e corre. O que deves ver: as cinco linhas, outra vez.

3. Provoca um erro de lógica. Põe o cursor na linha do `print("DUELO DE DADOS")` e corta a linha inteira, com Ctrl+X, ou Cmd+X no macOS. Depois põe o cursor no fim da última linha, carrega em Enter para abrires uma linha nova e cola, com Ctrl+V, ou Cmd+V. Antes de correres, prevê: o VS Code sublinha alguma coisa? E aparece alguma mensagem de erro? Guarda e corre. O que deves ver:

   ```text
   Dois jogadores, no máximo cinco rondas.
   Em cada ronda, cada jogador escolhe um número de 1 a 6.
   Quem escolher o número maior ganha a ronda.
   O duelo acaba quando alguém ganha três rondas.
   DUELO DE DADOS
   ```

   Não há mensagem nenhuma, nem nada sublinhado no editor. O programa está bem escrito e todas as instruções existem, por isso o Python executou-as todas. Mas o nome do jogo aparece no fim, e não no início. Só dás pelo erro porque comparas o que apareceu com o resultado esperado que escreveste no caderno, na fase 4. É por isso que o resultado esperado se escreve antes de correr.

4. Corrige: corta outra vez a linha do título, da mesma maneira. Põe o cursor no início da linha 3, logo a seguir aos comentários, e cola. Confirma que o `print("DUELO DE DADOS")` ficou numa linha só para ele. Guarda, corre e compara outra vez com o resultado esperado.

5. No caderno, faz uma tabela dos três erros que provocaste neste laboratório. Tem quatro colunas: "O erro", "O tipo", "O que se viu" e "Correu alguma linha?".

   A resposta:

   | O erro | O tipo | O que se viu | Correu alguma linha? |
   | --- | --- | --- | --- |
   | A aspa por fechar, no `ola.py` | De sintaxe | `SyntaxError` e o número da linha | Nenhuma |
   | O `Print` com maiúscula | De execução | As linhas de antes, e depois o traceback com `NameError` | As que estão antes da linha 6 |
   | O título no fim | De lógica | Nenhuma mensagem; o ecrã diferente do esperado | Todas |

### Paragem 5

O `abertura.py` está outra vez certo, e dá as cinco linhas pela ordem do pseudocódigo. Na tabela do caderno tens um erro de cada tipo, com o que se viu em cada um.

Pensa antes de terminares: qual dos três erros é o mais difícil de encontrar, e porquê? A resposta: o erro de lógica, porque o Python não dá nenhuma mensagem, e o VS Code não sublinha nada. Só se encontra comparando o resultado obtido com o resultado esperado, escrito antes de correr o programa.

O ficheiro `abertura.py` completo, como deve estar agora:

```python
# abertura.py: o ecrã de abertura do duelo de dados, o projeto 1 da algoritmia.
# Escreve o nome do jogo e as regras, uma linha de cada vez, de cima para baixo.
print("DUELO DE DADOS")
print("Dois jogadores, no máximo cinco rondas.")
print("Em cada ronda, cada jogador escolhe um número de 1 a 6.")
print("Quem escolher o número maior ganha a ronda.")
print("O duelo acaba quando alguém ganha três rondas.")
```

## Problemas frequentes

### O Windows diz que não conhece o `python`, ou abre a Microsoft Store

O comando `python` não está disponível com esse nome neste computador. Fecha a loja, se abriu, e usa `py` em vez de `python`, como em `py ola.py`. Se nenhum dos dois funcionar, avisa o professor, porque o Python pode não estar instalado.

### `can't open file` e `No such file or directory`

A mensagem quer dizer "não consigo abrir o ficheiro: não existe esse ficheiro nem essa pasta". O terminal não está na pasta do ficheiro, ou o nome no comando tem um erro. Confirma que o texto antes do cursor acaba em `lp-python`. Confirma também que o nome no comando é igual ao do painel Explorer, com o `.py` no fim.

### `SyntaxError: invalid syntax` ao escrever `python ola.py`

Estás dentro da consola do Python, e a linha começa por `>>>`. A consola espera linhas de Python, e não comandos do terminal. Escreve `exit()`, carrega em Enter e escreve o comando outra vez.

### O resultado não muda depois de corrigires o código

O ficheiro não foi guardado, e o Python correu a versão antiga. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre outra vez.

### Não há triângulo no canto de cima do editor

O botão de correr vem com a extensão Python. Confirma, como no passo 2 da fase 3, se a extensão está instalada. Confirma também que o ficheiro que tens à frente acaba em `.py`, porque o botão só aparece nos ficheiros de Python. Enquanto não houver botão, corre os programas com o comando, no terminal.

### `NameError` e `is not defined`

O Python não conhece uma palavra que escreveste, e a mensagem mostra-a entre aspas simples. Na fase 5, é o `Print`, com maiúscula. O Python distingue as maiúsculas das minúsculas, e a instrução é `print`, toda em minúsculas.

### O programa corre e não escreve nada

Confirma que cada linha tem `print`, e não `Escreve:`. Uma linha copiada do pseudocódigo, como `Escreve: "DUELO DE DADOS"`, não dá erro no Python, mas também não escreve nada. Confirma também que guardaste o ficheiro.

## Desafios

1. Uma linha em branco. Muda o `abertura.py` para aparecer uma linha em branco entre o nome do jogo e as regras. Escreve primeiro, no caderno, o resultado esperado, e compara-o com o que aparecer. Pista: experimenta na consola um `print` sem nada entre os parênteses.

2. O ecrã de abertura de outro jogo. Escolhe um jogo de cartas ou de tabuleiro que conheças bem, como o jogo do galo. Escreve, primeiro em pseudocódigo, um ecrã de abertura com o nome do jogo e três regras. Depois passa-o para Python, num ficheiro novo com um nome que diga o que é, sem espaços nem acentos. Testa-o com o resultado esperado escrito antes de correr.

3. O erro que ninguém vê. Num dos teus programas, provoca um erro de lógica diferente do da fase 5, que não troque a ordem das linhas. Dá o programa a um colega, com o resultado esperado, e vê se ele encontra o erro. Pista: pensa no que pode estar errado num programa que corre até ao fim sem mensagem.

4. Sem o VS Code. Este desafio faz-se num computador com Windows; se só tens macOS, salta-o. Abre o `ola.py` no Bloco de Notas. No Explorador de Ficheiros do Windows, carrega no ficheiro com o botão direito do rato. O ficheiro pode aparecer só como `ola`, porque o Windows esconde o fim do nome. Escolhe Abrir com e depois Bloco de Notas. Muda o texto da linha 2, guarda e fecha o Bloco de Notas. Antes de correres, prevê: o programa corre? Depois corre-o no terminal, com o teu comando. No caderno, escreve o que encontraste no Bloco de Notas, comparado com o VS Code, e o que o Bloco de Notas não tem. Pista: compara com as ferramentas do teu mapa da janela.

## Antes de terminares

- [ ] O `ola.py` corre e escreve as duas linhas.
- [ ] O `abertura.py` corre e escreve as cinco linhas do ecrã de abertura, pela ordem do pseudocódigo.
- [ ] O registo da execução, no caderno, tem o comando que funciona no teu computador e a versão do Python.
- [ ] O mapa da janela, no caderno, tem as ferramentas da fase 3, cada uma na sua zona.
- [ ] A tabela dos três erros, no caderno, tem um erro de cada tipo.
- [ ] Sabes sair da consola do Python e voltar ao terminal.
- [ ] Sabes correr um programa com o comando e com o botão de correr.
- [ ] Sabes distinguir um erro de sintaxe, um erro de execução e um erro de lógica pelo que aparece no ecrã.
- [ ] Consegues explicar, por palavras tuas, o que é um IDE e quando te chega a consola ou um editor de texto simples.
- [ ] Consegues explicar, por palavras tuas, o que faz o interpretador quando escreves `python abertura.py`.

![Rodapé](../imagens/rodape.png)
