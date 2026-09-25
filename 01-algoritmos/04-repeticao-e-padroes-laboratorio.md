![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: ciclos no diagrams.net

UC: UC00245

Blocos: ALG04

Requisitos: UC00245-R04, UC00245-K05, UC00245-A05, UC00245-A06, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Laboratório do bloco ALG04, acompanha o [guia](04-repeticao-e-padroes.md) |
| Fundamento curricular | Unidade de competência UC00245, bloco ALG04 |
| Duração | 60 minutos dos 300 do bloco: é a prática guiada no computador |
| Evidência a guardar | Os ficheiros `.drawio` e as imagens `.png` dos dois fluxogramas deste laboratório: `fluxograma-pedidos-validos` e `fluxograma-inventario-de-corredores` |

## O que vais fazer

Vais desenhar no diagrams.net o fluxograma do exemplo explicado do guia, o algoritmo que conta os pedidos válidos e totaliza as unidades. É um fluxograma com um ciclo, e por isso tem uma coisa que os fluxogramas dos laboratórios anteriores não tinham: uma seta que volta atrás, para cima, até ao losango da condição do ciclo.

Essa seta é a única técnica nova deste laboratório. Tudo o resto já fizeste antes. O objetivo é aprender a desenhá-la de forma que qualquer pessoa, ao olhar para o desenho, perceba sem hesitar de onde sai, onde chega, e que não se confunde com as outras setas.

No fim há uma parte autónoma, com outro algoritmo, que desenhas sozinho.

## O que precisas de saber antes

Do [laboratório do bloco 02](02-pseudocodigo-e-fluxogramas-laboratorio.md) e do [laboratório do bloco 03](03-decisoes-e-validacao-laboratorio.md), precisas de saber, no diagrams.net:

- abrir a aplicação no browser, sem criar conta, e guardar o ficheiro na tua pasta `algoritmos`, com Ficheiro, Guardar como... e o campo "Onde:" em "Aparelho" ou "Descarregar";
- encontrar o grupo Fluxograma no fim da lista do painel da esquerda e reconhecer as figuras pelo nome que aparece ao passar o rato: Terminator para o início e o fim, Process para o retângulo, Data para o paralelogramo e Decision para o losango;
- escrever o texto dentro de uma figura, com um duplo clique;
- ligar duas figuras com uma seta presa nas duas pontas;
- escrever `Sim` e `Não` nas setas que saem de um losango, seguindo a convenção do laboratório 03: num `SE`, o `Não` sai por baixo e o `Sim` sai pela direita;
- juntar os dois ramos de uma decisão numa mesma figura;
- exportar o desenho como imagem PNG.

Este laboratório não volta a explicar esses passos em pormenor. Se te esqueceres de algum, volta à parte do laboratório que o explica.

Do guia deste bloco precisas das secções [A seta que volta ao losango](04-repeticao-e-padroes.md#a-seta-que-volta-ao-losango) e [Passo 6: O fluxograma](04-repeticao-e-padroes.md#passo-6-o-fluxograma). Tem o guia aberto ao lado: é de lá que vais copiar o texto de cada figura, e este laboratório não repete a teoria.

Material: o computador com um browser, e papel e caneta para a parte autónoma.

## Parte 1: Preparar o ficheiro (5 min)

1. Abre o browser, maximiza a janela e vai a `https://app.diagrams.net/?lang=pt`.
2. A aplicação abre logo um diagrama em branco, chamado "Diagrama sem nome".
3. Guarda-o já, antes de desenhares. Na barra de menus, no topo, escolhe Ficheiro e depois Guardar como....
4. No campo "Guardar como:", escreve `fluxograma-pedidos-validos.drawio`. Deixa o campo "Tipo:" em Ficheiro XML (.drawio).
5. No campo "Onde:", a aplicação sugere o Google Drive. Muda para "Aparelho". Se "Aparelho" não funcionar no teu computador, escolhe "Descarregar".
6. Carrega em Guardar e escolhe a pasta `algoritmos`. Com "Descarregar", o ficheiro vai para a pasta de transferências, e no fim do laboratório passas a cópia mais recente para a pasta `algoritmos`.

A partir daqui, guarda com Ctrl+S, ou Cmd+S num Mac, sempre que acabares uma parte.

Uma nota para quem tiver a janela do browser estreita, por exemplo a ocupar só metade do ecrã: nesse caso a barra de menus não aparece, e o menu abre no botão redondo com reticências, no canto superior direito, onde encontras Ficheiro e, ao mesmo nível, Exportar como. O mais simples é maximizar a janela.

## Parte 2: Planear a disposição antes de desenhar (5 min)

Um fluxograma com um ciclo fica confuso quando as figuras são postas à sorte e as setas se arranjam depois. A seta de volta precisa de um caminho livre para subir, e esse caminho tem de ser planeado antes de pores a primeira figura.

A disposição que vais usar tem três faixas, lado a lado:

```text
  faixa livre        faixa do meio                        faixa da direita
  (a seta de volta   (o caminho principal,                (o ramo Sim do SE; mais à
   sobe por aqui)     de cima para baixo)                  direita ainda, a saída do ciclo)

                     Início
                     as três inicializações
                     a pergunta e a leitura antecipada
  +--------------->  losango do ciclo  ---- Não -----------------------------------+
  |                   | Sim                                                        |
  |                  losango do SE  ---- Sim ---->  válidos + 1                    |
  |                   | Não                          total + quantidade            |
  |                  recusados + 1                        |                        |
  |                  escrever pedido recusado             |                        |
  |                  pergunta  <--------------------------+                        |
  +----------------- leitura da quantidade seguinte                                |
                                                                                   |
                     (espaço vazio: aqui não há seta)                              |
                     escrever pedidosValidos  <------------------------------------+
                     escrever totalUnidades
                     escrever pedidosRecusados
                     Fim
```

Repara em quatro pormenores deste esquema, porque são eles que tornam o desenho inequívoco.

O losango do `SE` segue a convenção do laboratório 03: o `Não` sai por baixo e o `Sim` sai pela direita. Os dois ramos juntam-se na pergunta que está no fim do corpo, que corresponde ao `FIM SE`.

O losango do ciclo tem a disposição contrária: o `Sim` sai por baixo, para o corpo do ciclo, e o `Não` sai pela direita, para fora do ciclo. Há uma razão para esta diferença. O losango de um ciclo tem quatro setas, e não três: a que chega de cima, as duas saídas e a seta de volta. Com o `Sim` por baixo, o corpo do ciclo fica na faixa do meio e a ponta esquerda do losango fica livre para a seta de volta. Se o `Sim` saísse pela direita, o corpo ficava na faixa da direita, e a seta de volta, para chegar à ponta esquerda, teria de cruzar a saída `Não` ou a seta que chega de cima. Para distinguires os dois losangos à primeira vista: ao losango do ciclo chega uma seta pela esquerda; ao losango do `SE`, não.

A faixa da esquerda fica vazia de figuras. É por ali que a seta de volta sobe, da leitura da quantidade seguinte até à ponta esquerda do losango do ciclo, sem passar por cima de nada. A seta que vem da leitura antecipada chega ao mesmo losango pela ponta de cima. São duas setas a chegar ao mesmo losango, e cada uma chega por um lado diferente.

A saída `Não` do ciclo desce por fora de tudo, mais à direita do que o ramo `Sim` do `SE`, até às escritas dos resultados. Entre a leitura da quantidade seguinte e as escritas dos resultados fica um espaço vazio, sem seta: quem sai do corpo volta sempre ao losango, e só a saída `Não` chega aos resultados.

## Parte 3: Desenhar as figuras e as setas que já sabes fazer (15 min)

1. No painel da esquerda, desce até ao fim da lista e abre o grupo Fluxograma.
2. Desenha a faixa do meio, de cima para baixo: o Terminator do início, os três Process das inicializações, os dois Data da pergunta e da leitura antecipada, o Decision do ciclo, o Decision do `SE`, o Process de `pedidosRecusados ← pedidosRecusados + 1`, o Data de `ESCREVER pedido recusado`, os dois Data da pergunta e da leitura no fim do corpo, depois um espaço vazio, os três Data das escritas dos resultados e o Terminator do fim.
3. Desenha a faixa da direita: os dois Process do ramo `Sim` do `SE`, `pedidosValidos ← pedidosValidos + 1` e `totalUnidades ← totalUnidades + quantidade`, à direita do losango do `SE`, o primeiro à mesma altura dele.
4. Escreve em cada figura o texto do fluxograma do guia. O texto é o mesmo do pseudocódigo, com o mesmo nome de cada variável e as mesmas setas de atribuição.
5. O losango do `SE` tem uma condição longa. Seleciona-o e puxa um dos cantos para fora, até o texto caber sem ficar cortado.

Para poupar tempo, desenha uma figura, escreve-lhe o texto, e depois duplica-a e muda só o texto: seleciona a figura e usa Ctrl+D, ou Cmd+D num Mac. As três inicializações, por exemplo, são três Process iguais com textos diferentes.

6. Liga as figuras da faixa do meio com setas, de cima para baixo, como no laboratório 02, desde o início até ao losango do ciclo, e do losango do `SE` até à leitura da quantidade seguinte. Não ligues a leitura da quantidade seguinte a nada, e não ligues nada às escritas dos resultados: essas setas são as da parte 4.
7. Liga o losango do ciclo ao losango do `SE`, pela ponta de baixo, e escreve `Sim` nessa seta.
8. No losango do `SE`, a seta que desce para `pedidosRecusados ← pedidosRecusados + 1` leva `Não`. Liga a ponta direita do losango do `SE` a `pedidosValidos ← pedidosValidos + 1` e escreve `Sim`. Liga as duas figuras da faixa da direita uma à outra.
9. Junta os dois ramos do `SE`: liga `totalUnidades ← totalUnidades + quantidade` à pergunta do fim do corpo, fazendo a seta chegar à pergunta pelo lado direito. Assim não se sobrepõe à seta que chega de cima, vinda do ramo `Não`.

Guarda o ficheiro.

## Parte 4: A seta que volta ao losango (15 min)

Esta é a parte nova. Faz os passos devagar e confirma cada um antes de passares ao seguinte.

**1. Começar na figura certa.** A seta de volta sai da última figura do corpo do ciclo, a leitura da quantidade seguinte, `LER quantidade`, no fundo do corpo. Não sai do losango, nem da pergunta que está acima da leitura. Para confirmares, procura no pseudocódigo do guia a última instrução antes do `FIM ENQUANTO`: é dessa figura que a seta sai.

**2. Sair pelo lado esquerdo.** Passa o rato por cima dessa figura. Aparecem as pequenas setas azuis nos quatro lados. Carrega na seta azul do lado esquerdo e, sem largar o botão do rato, arrasta para cima, até ao losango do ciclo.

**3. Largar na ponta esquerda do losango.** No laboratório 03 largavas a seta quando a figura de destino ficava com o contorno azul. Isso prende a seta à figura, mas deixa a aplicação escolher o lado por onde a seta entra, e muitas vezes ela escolhe a ponta de cima, onde já chega a seta da leitura antecipada. Ficavas com duas setas a entrar no mesmo ponto, e quem olhasse para o desenho já não conseguia ver qual delas vem de onde. É isto que quer dizer uma seta ambígua.

Para a seta de volta, és tu que escolhes o lado. Quando o rato passa por cima do losango, aparecem no seu contorno pequenas marcas, que são os pontos onde uma seta se pode prender. Leva o rato até à marca que está na ponta esquerda do losango e só então larga o botão.

**4. Ver o caminho que a seta fez.** Olha para a seta nova. A aplicação desenha as setas com ângulos retos: a seta deve sair da leitura para a esquerda, subir pela faixa livre e virar à direita para entrar na ponta esquerda do losango. Se a seta aparecer como uma linha inclinada, a direito, seleciona-a com um clique e, no painel da direita, no separador Estilo, procura a opção Pontos de passagem e escolhe Ortogonal, que é a opção das linhas com ângulos retos.

**5. Afastar a seta das figuras.** Se a parte vertical da seta passar por cima de alguma figura, ou muito encostada a elas, faz como no laboratório 03: clica na seta e arrasta o ponto que aparece a meio dessa parte vertical para a esquerda, até a seta subir pela faixa livre, bem afastada das figuras. Se a seta ficar com um caminho estranho e não a conseguires endireitar, clica nela com o botão direito do rato e procura a opção Limpar pontos de passagem, que devolve a seta ao caminho automático. Depois tenta outra vez.

**6. Confirmar o sentido.** A ponta da seta tem de estar no losango, e não na leitura. Se estiver ao contrário, é porque arrastaste do losango para a leitura. Seleciona a seta, apaga-a com a tecla Delete e faz de novo, a partir da leitura.

**7. Deixar a seta sem texto.** Não escrevas nada na seta de volta. O `Sim` e o `Não` pertencem às saídas do losango, e uma palavra na seta de volta faria parecer que ela é uma saída.

**8. Desenhar a saída do ciclo.** Liga a ponta direita do losango do ciclo à primeira escrita dos resultados, `ESCREVER pedidosValidos`. A seta deve sair para a direita, passar além da faixa da direita, descer por fora de tudo e entrar na escrita pelo lado direito. Se passar por cima das figuras da faixa da direita, afasta-a como no passo 5. Escreve `Não` nesta seta.

**9. Ligar os resultados ao fim.** Liga as três escritas dos resultados e o fim, de cima para baixo.

Agora olha para o losango do ciclo. Devem chegar-lhe duas setas, uma por cima e uma pela esquerda, e sair duas, o `Sim` por baixo e o `Não` pela direita. Nenhuma das quatro partilha o mesmo ponto do contorno.

## Parte 5: Verificar o desenho com um caso de teste (5 min)

Um fluxograma verifica-se percorrendo-o, como fizeste com o dedo no guia e no laboratório 03. Usa o caso curto do [passo 7 do exemplo](04-repeticao-e-padroes.md#passo-7-o-trace-linha-a-linha-de-um-caso-curto): o funcionário escreve 12, depois 60, e depois 0.

Com o ponteiro do rato, segue o caminho desde o início, e diz em voz baixa o valor de cada variável sempre que ele muda. Em cada losango, escolhe a saída pela condição, com os valores do momento. Enquanto percorres, conta quantas vezes passas pelo losango do ciclo e quantas passas pelo losango do `SE`.

Se o desenho estiver certo, passas três vezes pelo losango do ciclo e duas pelo do `SE`, e chegas ao fim com 1 pedido válido, 12 unidades e 1 pedido recusado, os mesmos valores da tabela do guia. Se deres por ti numa figura de onde não sai nenhuma seta, ou a voltar a uma inicialização, há uma seta errada. Corrige-a antes de continuares.

Confirma depois esta lista:

- há um único início e um único fim;
- todas as figuras têm pelo menos uma seta a entrar e uma a sair, menos o início, que só tem saída, e o fim, que só tem entrada;
- cada losango tem exatamente duas saídas, uma com `Sim` e outra com `Não`;
- a seta de volta sai da última figura do corpo e chega ao losango do ciclo, e não a outra figura;
- nenhuma seta cruza outra, e nenhuma passa por cima de uma figura;
- o texto de cada figura é o mesmo do pseudocódigo.

## Parte 6: Guardar e exportar (5 min)

1. Guarda o `.drawio`, com Ctrl+S ou Cmd+S.
2. Na barra de menus, escolhe Ficheiro, depois Exportar como e depois PNG....
3. Abre-se a janela Imagem. Deixa tudo como está, e confirma só que a opção Fundo Transparente está desligada, como aprendeste no laboratório 02: com o fundo transparente, a imagem pode ficar ilegível quando aberta num fundo escuro.
4. Carrega em Exportar. Se a aplicação pedir um nome e um sítio, o nome é `fluxograma-pedidos-validos.png` e o sítio é "Aparelho" ou "Descarregar", nunca o Google Drive.
5. Abre a imagem exportada e confirma que se lê todo o texto e que se veem todas as setas, incluindo a de volta.

## Parte autónoma: um PARA no fluxograma (10 min)

Esta parte fazes sozinho. Cria um ficheiro novo, em Ficheiro, Novo..., e guarda-o logo na pasta `algoritmos`, com o nome `fluxograma-inventario-de-corredores.drawio`.

Vais desenhar o fluxograma deste algoritmo, que soma as caixas guardadas nos 3 corredores de um armazém:

```text
ALGORITMO InventarioDeCorredores
CONSTANTES
    NUMERO_DE_CORREDORES ← 3
VARIÁVEIS
    corredor: inteiro
    caixas: inteiro
    totalCaixas: inteiro
INÍCIO
    totalCaixas ← 0
    PARA corredor ← 1 ATÉ NUMERO_DE_CORREDORES FAZER
        ESCREVER "Caixas no corredor ", corredor, "?"
        LER caixas
        totalCaixas ← totalCaixas + caixas
    FIM PARA
    ESCREVER "Total de caixas no armazém: ", totalCaixas
FIM
```

A única coisa nova é o `PARA`. No guia viste que, nesta disciplina, o `PARA` se desenha como o `ENQUANTO` equivalente (guia, [PARA: a forma curta do ciclo contado](04-repeticao-e-padroes.md#para-a-forma-curta-do-ciclo-contado)). Por isso o desenho tem figuras que não aparecem escritas no pseudocódigo acima.

**a)** No papel, escreve as duas instruções que o `PARA` esconde no cabeçalho e diz onde fica cada uma no fluxograma: antes do losango, ou no fim do corpo, mesmo antes da seta de volta.

**b)** Desenha o fluxograma no diagrams.net, com essas duas figuras, o losango `corredor <= NUMERO_DE_CORREDORES?` e a seta de volta a chegar à ponta esquerda do losango, como na parte 4. O `Sim` sai por baixo e o `Não` pela direita.

**c)** Percorre o desenho com o ponteiro do rato, com 5, 3 e 4 caixas nos três corredores. Escreve no papel quantas vezes passaste pelo losango e que total apareceu no fim.

Guarda e exporta a imagem como `fluxograma-inventario-de-corredores.png`, como na parte 6. Se o tempo da aula não chegar para esta parte, termina-a no início da aula seguinte.

## Para ires mais longe: dois ciclos no mesmo fluxograma

Esta parte é opcional, para quem acabou a parte autónoma ou quer praticar em casa. Muda o algoritmo dos corredores para que o número de corredores deixe de ser uma constante: o funcionário escreve-o no início, e o algoritmo pede-o outra vez até ser pelo menos 1. Guarda o desenho noutro ficheiro, `fluxograma-dois-ciclos.drawio`.

```text
ALGORITMO InventarioComValidacao
VARIÁVEIS
    numeroDeCorredores: inteiro
    corredor: inteiro
    caixas: inteiro
    totalCaixas: inteiro
INÍCIO
    ESCREVER "Quantos corredores tem o armazém?"
    LER numeroDeCorredores
    ENQUANTO numeroDeCorredores < 1 FAZER
        ESCREVER "Tem de haver pelo menos 1 corredor. Quantos corredores?"
        LER numeroDeCorredores
    FIM ENQUANTO
    totalCaixas ← 0
    PARA corredor ← 1 ATÉ numeroDeCorredores FAZER
        ESCREVER "Caixas no corredor ", corredor, "?"
        LER caixas
        totalCaixas ← totalCaixas + caixas
    FIM PARA
    ESCREVER "Total de caixas no armazém: ", totalCaixas
FIM
```

Agora há dois ciclos, um a seguir ao outro. Cada um tem o seu losango e a sua seta de volta, e cada seta de volta tem de chegar ao losango do seu ciclo. Planeia a disposição num papel antes de desenhar, para as duas setas subirem pela faixa livre sem se cruzarem. Verifica o desenho com este caso: o funcionário escreve 0 corredores, depois 2 corredores, e depois 5 caixas e 3 caixas. Conta quantas vezes passas por cada losango e escreve o que aparece no ecrã, do princípio ao fim.

## Quando alguma coisa corre mal na aplicação

| O que acontece | O que fazer |
| --- | --- |
| A seta de volta entra no losango por cima, no mesmo ponto da seta da leitura antecipada | Apaga-a e desenha-a outra vez, largando na marca da ponta esquerda do losango, e não no meio dele |
| A seta de volta atravessa figuras | Clica nela e arrasta o ponto do meio da parte vertical para a esquerda |
| A seta ficou torta ou com um caminho estranho | Botão direito sobre a seta, Limpar pontos de passagem, e ajusta outra vez |
| A ponta da seta está na leitura e não no losango | Arrastaste ao contrário: apaga a seta e desenha-a a partir da leitura |
| O texto não cabe no losango | Seleciona o losango e puxa um dos cantos para fora |
| O ficheiro foi guardado no Google Drive | Volta a guardar com Ficheiro, Guardar como... e, no campo "Onde:", escolhe "Aparelho" ou "Descarregar" |
| Não aparece a barra de menus no topo | A janela está estreita: maximiza o browser, ou usa o botão redondo com reticências, no canto superior direito |
| Apagaste uma figura sem querer | Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação |

## O que entregar

Na tua pasta `algoritmos` tens de ter quatro ficheiros novos:

- `fluxograma-pedidos-validos.drawio` e `fluxograma-pedidos-validos.png`;
- `fluxograma-inventario-de-corredores.drawio` e `fluxograma-inventario-de-corredores.png`.

E em papel, a folha da parte autónoma, com as duas instruções que o `PARA` esconde, o número de passagens pelo losango e o total que apareceu no ecrã.

Antes de entregares, confirma:

- [ ] A seta de volta de cada ciclo sai da última figura do corpo e chega ao losango desse ciclo, sem cruzar nenhuma seta nem passar por cima de nenhuma figura.
- [ ] Em cada losango de ciclo chegam duas setas e saem duas, cada uma no seu ponto do contorno.
- [ ] Cada losango tem uma saída `Sim` e uma saída `Não`, e as setas de volta não têm texto.
- [ ] Percorri o fluxograma dos pedidos com o caso 12, 60, 0 e obtive os mesmos valores da tabela do guia.
- [ ] No fluxograma dos corredores, o `PARA` está desenhado com as suas três peças.

![Rodapé](../imagens/rodape.png)
