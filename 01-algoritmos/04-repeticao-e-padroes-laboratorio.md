![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Repetição e padrões

Laboratório do tema Repetição e padrões, do módulo Desenvolver algoritmos. Vais desenhar no diagrams.net o fluxograma de um algoritmo com um ciclo, com a seta que volta atrás até ao losango da condição. Cada passo diz o que fazer, porquê e o que deves ver. Avanças ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte. Tudo o que precisas está aqui; o [guia do tema](04-repeticao-e-padroes.md) tem a teoria completa, para quem quiser saber mais.

Este laboratório é todo de fluxogramas, e é opcional. Só o fazes quando o professor o indicar. Nenhum exercício obrigatório da ficha depende dele. A matéria do tema é saber reconhecer um ciclo num fluxograma, pela seta que volta ao losango. Desenhá-lo é a parte opcional que este laboratório treina.

## O que vais construir

No fim, tens na tua pasta `algoritmos` o fluxograma de um algoritmo que conta os pedidos de uma papelaria. Fica em dois ficheiros: o desenho que se pode editar, `fluxograma-pedidos-validos.drawio`, e uma imagem, `fluxograma-pedidos-validos.png`.

Este algoritmo tem um ciclo. Por isso, o fluxograma tem uma seta que volta atrás, para cima, até ao losango da condição. Os fluxogramas sem ciclos não têm nenhuma seta assim. Essa seta é a técnica nova deste laboratório. O objetivo é desenhá-la de forma que qualquer pessoa perceba, sem hesitar, de onde sai e onde chega. E que ninguém a confunda com as outras setas.

O algoritmo é este. O funcionário escreve a quantidade de cada pedido, um de cada vez, e escreve 0 quando já não há mais pedidos. Um pedido é válido se tiver de 1 a 50 unidades. Cada pedido recusado é assinalado no momento. No fim, o algoritmo mostra quantos pedidos válidos houve, quantas unidades somam e quantos pedidos foram recusados.

```text
const SENTINELA = 0
const QUANTIDADE_MINIMA = 1
const CAPACIDADE_MAXIMA = 50
int pedidosValidos = 0
int pedidosRecusados = 0
int totalUnidades = 0
Escreve: "Quantidade do pedido (0 para terminar)?"
int quantidade = ler valor
Enquanto quantidade != SENTINELA
    Se quantidade >= QUANTIDADE_MINIMA e quantidade <= CAPACIDADE_MAXIMA
        pedidosValidos = pedidosValidos + 1
        totalUnidades = totalUnidades + quantidade
    Senão
        pedidosRecusados = pedidosRecusados + 1
        Escreve: "Pedido recusado: ", quantidade, " unidades"
    Escreve: "Quantidade do pedido (0 para terminar)?"
    quantidade = ler valor
Escreve: "Pedidos válidos: ", pedidosValidos
Escreve: "Total de unidades: ", totalUnidades
Escreve: "Pedidos recusados: ", pedidosRecusados
```

Leitura guiada: as três linhas `const` dão nome a valores fixos, o 0 que marca o fim e os limites 1 e 50. As três linhas seguintes põem os resultados a 0. Depois, o algoritmo faz a pergunta e lê a primeira quantidade, antes do ciclo. A linha do `Enquanto` é o ciclo. Repete as linhas indentadas debaixo dela enquanto a quantidade lida não for 0. Dentro dessas linhas, um `Se` decide se o pedido é válido, e o seu ramo e o do `Senão` ficam oito espaços mais para dentro. As duas últimas linhas do ciclo, de novo com quatro espaços, perguntam e leem a quantidade seguinte. Depois, o algoritmo volta à linha do `Enquanto` e testa a quantidade nova. Quando ela é 0, o ciclo termina, e o algoritmo escreve os três resultados.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | Planeias no papel onde fica cada figura | Um esquema em três faixas, com um caminho livre para a seta de volta |
| 2 | Pões as figuras e as setas que descem | Todas as figuras ligadas, menos a seta de volta e a saída do ciclo |
| 3 | Desenhas a seta de volta e a saída do ciclo | O losango do ciclo com duas setas a entrar e duas a sair, cada uma no seu ponto |
| 4 | Segues o desenho com um caso de teste | Três passagens pelo losango do ciclo, e os resultados certos no fim |
| 5 | Exportas uma imagem do desenho | O `.drawio` e o `.png` na pasta `algoritmos` |

## Palavras que vais usar

- Fluxograma: o desenho de um algoritmo, com figuras ligadas por setas. Cada figura é uma instrução, e as setas dizem a ordem.
- Terminal: a figura de pontas redondas onde o algoritmo começa, `Início`, e acaba, `Fim`. Na aplicação chama-se Terminator.
- Retângulo: a figura das contas e das instruções que dão um valor a uma variável. Na aplicação chama-se Process.
- Paralelogramo: a figura das entradas e das saídas, como `ler valor` e `Escreve:`. Na aplicação chama-se Data.
- Losango: a figura de uma condição, com uma entrada e duas saídas, `Sim` e `Não`. Na aplicação chama-se Decision.
- Ciclo: uma parte de um algoritmo que se repete. Com `Enquanto`, repete-se enquanto a condição for verdadeira. Para saber mais, vê a secção "Um ciclo volta atrás e pergunta outra vez" do [guia](04-repeticao-e-padroes.md).
- Corpo do ciclo: as linhas que se repetem, indentadas debaixo do `Enquanto`.
- Iteração: cada vez que o corpo do ciclo se executa.
- Seta de volta: a seta que sobe da última figura do corpo até ao losango do ciclo, para a condição ser testada outra vez. Para saber mais, vê a secção "A seta que volta ao losango" do [guia](04-repeticao-e-padroes.md).
- Sentinela: o valor combinado que quer dizer "acabou". Neste algoritmo é o 0, guardado na constante `SENTINELA`.
- Leitura antecipada: a leitura do primeiro valor, feita antes do ciclo, para a condição ter um valor para testar.
- Ramo: cada um dos caminhos que saem de um losango.
- Seta ambígua: uma seta de que não se percebe bem de onde vem ou para onde vai. Por exemplo, duas setas a entrar no mesmo ponto de uma figura.
- `Para`: um ciclo que repete o corpo um número de vezes que se sabe antes de começar. `Para corredor de 1 até 3` repete-o com `corredor` a valer 1, 2 e 3. Aparece nos desafios.
- Ficheiro `.drawio`: o desenho que a aplicação volta a abrir para continuares a editar.
- Imagem PNG: uma fotografia do desenho, que qualquer computador abre, mas que não se edita.
- Exportar: criar a imagem PNG a partir do desenho.

## O que precisas

- Um computador com um browser, como o Chrome, o Edge, o Firefox ou o Safari, e ligação à internet.
- O diagrams.net, uma aplicação gratuita de desenho de diagramas que funciona no browser, sem criar conta. Também se chama draw.io, o nome antigo. Confirma que chegas a ela. Abre `https://app.diagrams.net/?lang=pt`. Deve aparecer um diagrama em branco chamado "Diagrama sem nome", o que quer dizer que a aplicação está pronta a usar.
- A pasta `algoritmos`, onde guardas os fluxogramas desta disciplina. Se fizeste o laboratório do tema 02 ou o do tema 03, já a tens. Se não, cria-a antes de começar, no sítio que o professor indicar: uma pasta do computador ou uma pen.
- Papel e caneta, para as fases 1 e 4.

Se fizeste os laboratórios dos temas 02 e 03, já conheces a aplicação, e podes passar depressa pelos passos que já sabes. Se não os fizeste, não faz mal, porque cada ação está explicada na primeira vez que aparece.

## Se alguma coisa falhar

1. A aplicação aparece em inglês? Abre-a com o endereço `https://app.diagrams.net/?lang=pt`, com o `?lang=pt` no fim.
2. Vês a barra de menus no topo da aplicação, com Ficheiro, Editar, Visualização, Ordenar, Extras e Ajuda? Se não a vês, a janela do browser está estreita. Maximiza-a, ou usa o botão redondo com reticências, no canto superior direito, que tem as mesmas opções.
3. O teu ficheiro está guardado no computador? O nome que lhe deste aparece no topo da aplicação. Se o "Guardar como" te pedir para entrar numa conta, o campo "Onde:" ficou no Google Drive. Muda-o para "Aparelho" ou "Descarregar".
4. As setas estão presas às figuras? Arrasta uma figura um pouco para o lado. Se as setas a acompanharem, estão presas. Depois carrega em Ctrl+Z, ou Cmd+Z num Mac, para a figura voltar ao sítio.
5. Enganaste-te? Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação. Podes repetir para desfazer várias.

## Preparar o projeto

A aplicação muda de aspeto de vez em quando. Os passos descrevem cada opção pelo que faz. Se um nome no teu ecrã não for exatamente igual, procura o que faz a mesma coisa, porque os passos são os mesmos.

1. Abre a aplicação em português. Maximiza a janela do browser, para ocupar o ecrã todo, e escreve na barra de endereços `https://app.diagrams.net/?lang=pt`. A parte final, `?lang=pt`, pede a aplicação em português.

   O que deves ver: um diagrama em branco, chamado "Diagrama sem nome". A aplicação não te pergunta nada nem te pede conta.

2. Conhece as quatro zonas do ecrã, porque vais usá-las:

   | Zona | Onde está | Para que serve |
   | --- | --- | --- |
   | Painel das figuras | à esquerda | tem as figuras, arrumadas em grupos, e no topo uma caixa de pesquisa |
   | Página | ao centro, a zona branca com uma grelha | é onde desenhas; a grelha só ajuda a alinhar |
   | Painel de formatação | à direita, com os separadores "Diagrama" e "Estilo" | muda o aspeto do que estiver selecionado |
   | Barra de menus | no topo | o menu "Ficheiro" tem tudo o que é guardar e exportar |

3. Guarda já o ficheiro, antes de desenhares. Neste momento, o diagrama só existe dentro do separador do browser, e se o fechares perdes tudo. Guardar logo dá-lhe um nome e um sítio.

   1. Na barra de menus, carrega em "Ficheiro" e, na lista que se abre, em "Guardar como...".
   2. Abre-se a janela "Guardar como". No campo "Guardar como:", apaga o que lá estiver e escreve `fluxograma-pedidos-validos.drawio`.
   3. No campo "Tipo:", deixa ficar "Ficheiro XML (.drawio)". É o formato que a aplicação volta a abrir para continuares a editar.
   4. O campo "Onde:" vem com "Google Drive", que pede uma conta. Muda-o para "Aparelho", que guarda o ficheiro numa pasta do teu computador. Se "Aparelho" não funcionar, escolhe "Descarregar", que põe o ficheiro na pasta de transferências.
   5. Carrega em "Guardar". Com "Aparelho", abre-se a janela do sistema para escolheres a pasta. Escolhe a pasta `algoritmos` e confirma.

   O que deves ver: o nome `fluxograma-pedidos-validos.drawio` no topo da aplicação, onde antes estava "Diagrama sem nome". Daqui para a frente, para guardar, carrega em Ctrl+S, ou Cmd+S num Mac, no fim de cada fase. Se escolheste "Descarregar", cada vez que guardas vai uma cópia nova para as transferências. No fim, passa a mais recente para a pasta `algoritmos`.

4. Encontra as figuras de fluxograma. O painel da esquerda tem as figuras arrumadas em grupos com nome, e as que te interessam estão no grupo "Fluxograma". Desce no painel até perto do fim da lista e carrega no nome "Fluxograma" para o abrir. Se o grupo não estiver na lista, carrega no botão "+ Mais formas", no fundo do painel. Na janela "Formas", marca "Fluxograma" e confirma.

   Passa o rato devagar por cima das figuras do grupo. Ao lado de cada uma aparece o nome dela, em inglês, mesmo com a aplicação em português. Neste laboratório usas estas quatro:

   | Figura | Nome que vais ver | Para que serve |
   | --- | --- | --- |
   | Retângulo de pontas redondas | Terminator | `Início` e `Fim` |
   | Retângulo | Process | as contas e as instruções que dão um valor a uma variável |
   | Paralelogramo | Data | ler um valor (`ler valor`) e escrever no ecrã (`Escreve:`) |
   | Losango | Decision | uma condição, com duas saídas |

   O grupo tem muitas outras figuras, que pertencem a convenções mais pormenorizadas do que a nossa. Usa sempre estas quatro, do grupo "Fluxograma".

## Fase 1: planear a disposição antes de desenhar

Num fluxograma, cada figura liga-se à seguinte por uma seta, e as setas descem. Num ciclo, há uma seta que sobe. Depois da última linha do corpo, o algoritmo não continua para baixo. Volta à linha do `Enquanto` e testa a condição outra vez. No desenho, essa volta é a seta de volta, que sobe da última figura do corpo até ao losango do ciclo.

Um fluxograma com um ciclo fica confuso quando as figuras são postas à sorte e as setas se arranjam depois. A seta de volta precisa de um caminho livre para subir, e esse caminho tem de ser planeado antes de pores a primeira figura.

1. Copia para o papel este esquema. É a disposição que vais usar, com três faixas lado a lado:

   ```text
     faixa livre        faixa do meio                        faixa da direita
     (a seta de volta   (o caminho principal,                (o ramo Sim do Se; mais à
      sobe por aqui)     de cima para baixo)                  direita ainda, a saída do ciclo)

                        Início
                        as três inicializações
                        a pergunta e a leitura antecipada
     +--------------->  losango do ciclo  ---- Não -----------------------------------+
     |                   | Sim                                                        |
     |                  losango do Se  ---- Sim ---->  válidos + 1                    |
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

2. Repara em quatro pormenores do esquema, porque são eles que tornam o desenho claro.

   O losango do `Se` segue a arrumação habitual dos fluxogramas destes materiais. O `Não` sai por baixo e o `Sim` sai pela direita, e assim quem lê sabe onde procurar cada saída. Os dois ramos do `Se` juntam-se na pergunta que está no fim do corpo. No pseudocódigo, é a primeira linha depois do `Se` e do `Senão`, a que volta aos quatro espaços.

   O losango do ciclo tem a arrumação contrária. O `Sim` sai por baixo, para o corpo do ciclo, e o `Não` sai pela direita, para fora do ciclo. Há uma razão para esta diferença. O losango de um ciclo tem quatro setas, e não três: a que chega de cima, as duas saídas e a seta de volta. Com o `Sim` por baixo, o corpo do ciclo fica na faixa do meio. E a ponta esquerda do losango fica livre para a seta de volta. Se o `Sim` saísse pela direita, o corpo ficava na faixa da direita. A seta de volta, para chegar à ponta esquerda, teria de cruzar a saída `Não` ou a seta que chega de cima.

   A faixa da esquerda fica vazia de figuras. É por ali que a seta de volta sobe, sem passar por cima de nada. Vai da leitura da quantidade seguinte até à ponta esquerda do losango do ciclo. A seta que vem da leitura antecipada chega ao mesmo losango pela ponta de cima. São duas setas a chegar ao mesmo losango, e cada uma chega por um lado diferente.

   A saída `Não` do ciclo desce por fora de tudo, mais à direita do que o ramo `Sim` do `Se`, até às escritas dos resultados. Entre a leitura da quantidade seguinte e as escritas dos resultados fica um espaço vazio, sem seta. Quem sai do corpo volta sempre ao losango, e só a saída `Não` chega aos resultados.

### Paragem 1

Tens no papel o esquema das três faixas, com o caminho livre à esquerda para a seta de volta.

Pensa antes de continuares: como distingues, à primeira vista, o losango do ciclo do losango do `Se`? A resposta: ao losango do ciclo chega uma seta pela esquerda, a seta de volta. Ao losango do `Se`, não chega nenhuma seta pela esquerda.

## Fase 2: as figuras e as setas que descem

Cada linha do pseudocódigo que faz alguma coisa é uma figura do fluxograma. As três linhas `const` não têm figura. Dão nome a valores fixos, e esses nomes aparecem dentro das figuras onde são usados. A palavra `Senão` também não tem figura própria. O ramo dela começa no retângulo dos pedidos recusados. E o texto de um `Escreve:` encurta-se, para caber na figura. No pseudocódigo está completo.

Estas são as figuras da faixa do meio, de cima para baixo, com o texto de cada uma:

| Ordem | Figura | Texto a escrever |
| ---: | --- | --- |
| 1 | Terminator | `Início` |
| 2 | Process | `int pedidosValidos = 0` |
| 3 | Process | `int pedidosRecusados = 0` |
| 4 | Process | `int totalUnidades = 0` |
| 5 | Data | `Escreve: pergunta` |
| 6 | Data | `int quantidade = ler valor` |
| 7 | Decision | `quantidade != SENTINELA?` |
| 8 | Decision | `quantidade >= QUANTIDADE_MINIMA e quantidade <= CAPACIDADE_MAXIMA?` |
| 9 | Process | `pedidosRecusados = pedidosRecusados + 1` |
| 10 | Data | `Escreve: pedido recusado` |
| 11 | Data | `Escreve: pergunta` |
| 12 | Data | `quantidade = ler valor` |
| 13 | Data | `Escreve: pedidosValidos` |
| 14 | Data | `Escreve: totalUnidades` |
| 15 | Data | `Escreve: pedidosRecusados` |
| 16 | Terminator | `Fim` |

E estas são as duas figuras da faixa da direita, o ramo `Sim` do `Se`:

| Ordem | Figura | Texto a escrever |
| ---: | --- | --- |
| 17 | Process | `pedidosValidos = pedidosValidos + 1` |
| 18 | Process | `totalUnidades = totalUnidades + quantidade` |

O texto é o mesmo do pseudocódigo, com o mesmo nome de cada variável e o mesmo `=` para dar um valor. Onde uma variável aparece pela primeira vez, o texto leva o tipo à frente, como no pseudocódigo. Tudo se escreve diretamente no teclado, sem símbolos especiais.

1. Põe a primeira figura e escreve-lhe o texto. No grupo "Fluxograma", carrega na figura Terminator e, sem largar o botão do rato, arrasta-a para a página. Larga-a perto do topo, ao centro da faixa do meio. Depois faz duplo clique dentro da figura, escreve `Início` e carrega numa zona vazia da página para acabar.

   O que deves ver: o terminal com o texto `Início` lá dentro. Se te enganares no texto, faz outra vez duplo clique e corrige.

2. Põe as figuras 2 a 16, pela ordem da tabela, em coluna, com espaço entre elas, mais ou menos a altura de uma figura. Entre a figura 12, a leitura da quantidade seguinte, e a figura 13, a primeira escrita dos resultados, deixa um espaço maior, sem nada. É o espaço vazio do esquema.

   Para poupar tempo, desenha uma figura, escreve-lhe o texto, e depois duplica-a e muda só o texto. Para duplicar, seleciona a figura e carrega em Ctrl+D, ou Cmd+D num Mac. As três inicializações, por exemplo, são três Process iguais com textos diferentes. Quando arrastas uma figura, a aplicação mostra linhas de guia coloridas quando ela fica alinhada com outra. Larga a figura quando a linha de guia vertical aparecer, e as figuras ficam centradas umas por baixo das outras.

   O que deves ver: dezasseis figuras em coluna, do Início ao Fim, com um espaço vazio entre a 12 e a 13.

3. Põe as figuras 17 e 18 na faixa da direita, à direita do losango do `Se`. A 17 fica à mesma altura do losango, e a 18 por baixo dela.

4. Alarga o losango do `Se`. A condição dele é comprida, e não cabe num losango pequeno. Carrega uma vez no losango para o selecionar. Aparecem pequenos pontos nos cantos e a meio dos lados. Puxa um dos cantos para fora até o texto caber, de preferência numa ou duas linhas.

5. Liga as figuras da faixa do meio com setas, de cima para baixo. Passa o rato por cima da figura 1, sem carregar. Aparecem quatro pequenas setas azuis, uma de cada lado da figura. Carrega na seta azul de baixo e, sem largar o botão do rato, arrasta até à figura 2. Larga quando a figura 2 ficar com o contorno azul. É esse contorno que mostra que a seta ficou presa à figura.

   Faz o mesmo da figura 2 para a 3, e assim por diante até à figura 7, o losango do ciclo. Depois liga, também de cima para baixo, a figura 8 à 9, a 9 à 10, a 10 à 11 e a 11 à 12. Não ligues a figura 12 a nada, e não ligues nada às figuras 13 a 16. Essas setas são as da fase 3.

   O que deves ver: setas presas nas duas pontas, todas a apontar para baixo. Se uma ficar ao contrário, seleciona-a, apaga-a com a tecla Delete ou Backspace, e desenha-a outra vez a partir da figura de cima.

6. Liga o losango do ciclo, a figura 7, ao losango do `Se`, a figura 8, pela ponta de baixo. Falta o nome desta saída. Faz duplo clique a meio da seta, escreve `Sim` e carrega numa zona vazia.

   O que deves ver: a seta do losango do ciclo para o losango do `Se`, com a palavra `Sim` em cima.

7. Dá nome às saídas do `Se`. A seta que desce do losango do `Se` para a figura 9 leva `Não`. Depois liga a ponta direita do losango do `Se` à figura 17 e escreve `Sim` nessa seta. Liga a figura 17 à 18.

8. Junta os dois ramos do `Se`. Liga a figura 18 à figura 11, a pergunta do fim do corpo, e faz a seta chegar à pergunta pelo lado direito. Assim não se sobrepõe à seta que chega de cima, vinda do ramo `Não`. Esta seta não leva texto, porque não sai de um losango.

   Guarda o ficheiro, com Ctrl+S ou Cmd+S.

### Paragem 2

Conta as figuras e as setas do teu desenho. Deve ter dezoito figuras e catorze setas. Três setas têm texto: o `Sim` do losango do ciclo, e o `Sim` e o `Não` do losango do `Se`. Os dois ramos do `Se` chegam à figura 11, a pergunta, um por cima e outro pela direita.

Pensa antes de continuares: porque é que a figura 12, a leitura do fim do corpo, ainda não tem nenhuma seta a sair? A resposta: a seta que sai dela é a seta de volta, a técnica nova deste laboratório. Desenha-se na fase 3, com um cuidado especial.

## Fase 3: a seta que volta ao losango

A seta de volta vai sempre ao losango do ciclo, porque é lá que o ciclo decide se continua. Se fosse à primeira inicialização, os contadores e o total voltavam a zero em cada iteração. Se fosse para uma figura depois do losango, a condição nunca mais era testada, e o ciclo nunca acabava. Esta fase faz-se devagar. Confirma cada passo antes de passares ao seguinte.

1. Começa na figura certa. A seta de volta sai da última figura do corpo do ciclo, a leitura da quantidade seguinte, `quantidade = ler valor`. Não sai do losango, nem da pergunta que está acima da leitura. Para confirmares, procura no pseudocódigo a última linha com quatro espaços, antes das linhas sem indentação do fim. É dessa figura que a seta sai.

2. Sai pelo lado esquerdo. Passa o rato por cima da leitura. Aparecem as pequenas setas azuis nos quatro lados. Carrega na seta azul do lado esquerdo e, sem largar o botão do rato, arrasta para cima, até ao losango do ciclo.

3. Larga na ponta esquerda do losango. Nas setas da fase 2, largaste a seta quando a figura de destino ficava com o contorno azul. Isso prende a seta à figura, mas deixa a aplicação escolher o lado por onde a seta entra. Muitas vezes ela escolhe a ponta de cima, onde já chega a seta da leitura antecipada. Ficavas com duas setas a entrar no mesmo ponto, e quem olhasse para o desenho já não conseguia ver qual delas vem de onde. É isto que quer dizer uma seta ambígua.

   Para a seta de volta, és tu que escolhes o lado. Quando o rato passa por cima do losango, aparecem no seu contorno pequenas marcas, que são os pontos onde uma seta se pode prender. Leva o rato até à marca que está na ponta esquerda do losango, e só então larga o botão.

   O que deves ver: a seta presa à ponta esquerda do losango, e não à de cima.

4. Vê o caminho que a seta fez. A aplicação desenha as setas com ângulos retos. A seta deve sair da leitura para a esquerda, subir pela faixa livre e virar à direita para entrar na ponta esquerda do losango. Se a seta aparecer como uma linha inclinada, a direito, seleciona-a com um clique. Depois, no painel da direita, no separador "Estilo", procura a opção das linhas com ângulos retos. Na aplicação em português, chama-se "Pontos de passagem", e escolhe-se "Ortogonal".

5. Afasta a seta das figuras. Se a parte vertical da seta passar por cima de alguma figura, ou muito encostada a elas, carrega na seta. Depois arrasta o ponto que aparece a meio dessa parte vertical para a esquerda, até a seta subir pela faixa livre, bem afastada das figuras. Se a seta ficar com um caminho estranho e não a conseguires endireitar, carrega nela com o botão direito do rato. No menu que aparece, procura a opção que devolve a seta ao caminho automático, "Limpar pontos de passagem", e tenta outra vez.

6. Confirma o sentido. A ponta da seta tem de estar no losango, e não na leitura. Se estiver ao contrário, é porque arrastaste do losango para a leitura. Seleciona a seta, apaga-a com a tecla Delete e faz de novo, a partir da leitura.

7. Deixa a seta sem texto. O `Sim` e o `Não` pertencem às saídas do losango. Uma palavra na seta de volta faria parecer que ela é uma saída.

8. Desenha a saída do ciclo. Liga a ponta direita do losango do ciclo à primeira escrita dos resultados, `Escreve: pedidosValidos`. A seta deve sair para a direita, passar além da faixa da direita, descer por fora de tudo e entrar na escrita pelo lado direito. Se passar por cima das figuras da faixa da direita, afasta-a como no passo 5. Escreve `Não` nesta seta.

9. Liga os resultados ao fim. Liga as três escritas dos resultados e o Fim, de cima para baixo.

   Guarda o ficheiro.

### Paragem 3

Olha para o losango do ciclo. Chegam-lhe duas setas, uma por cima e outra pela esquerda, e saem duas, o `Sim` por baixo e o `Não` pela direita. Nenhuma das quatro partilha o mesmo ponto do contorno. O desenho tem agora dezoito figuras e dezanove setas.

Pensa antes de continuares: porque é que a seta de volta não leva o `Sim`, se é por ela que o ciclo continua? A resposta: o `Sim` já está na saída de baixo do losango, por onde se entra no corpo. A seta de volta não sai do losango, chega a ele. É o caminho de regresso ao teste, depois de o corpo acabar.

## Fase 4: verificar o desenho com um caso de teste

Um fluxograma verifica-se percorrendo-o com um caso de teste, como se fosses tu o computador. Em cada losango, a saída escolhe-se pela condição, com os valores que as variáveis têm nesse momento.

1. Segue o caminho com o ponteiro do rato, desde o Início, para este caso: o funcionário escreve 12, depois 60, e depois 0. Acompanha o valor de cada variável sempre que ele muda. Conta quantas vezes passas pelo losango do ciclo e quantas passas pelo losango do `Se`.

2. Confere o teu percurso com este, passagem a passagem:

   | Passagem | Losango | Condição, com os valores do momento | Saída | O que acontece a seguir |
   | --- | --- | --- | --- | --- |
   | 1.ª | do ciclo | `12 != 0` dá `true` | `Sim` | vais para o losango do `Se` |
   | 1.ª | do `Se` | `12 >= 1` dá `true`, `12 <= 50` dá `true`; `true` e `true` dá `true` | `Sim` | os válidos passam a 1 e o total a 12; lês 60 |
   | 2.ª | do ciclo | `60 != 0` dá `true` | `Sim` | vais para o losango do `Se` |
   | 2.ª | do `Se` | `60 >= 1` dá `true`, `60 <= 50` dá `false`; `true` e `false` dá `false` | `Não` | os recusados passam a 1; escreves "Pedido recusado: 60 unidades"; lês 0 |
   | 3.ª | do ciclo | `0 != 0` dá `false` | `Não` | escreves os três resultados e chegas ao Fim |

   O que deves ver: três passagens pelo losango do ciclo e duas pelo losango do `Se`. No fim, 1 pedido válido, 12 unidades e 1 pedido recusado. Se deres por ti numa figura de onde não sai nenhuma seta, ou a voltar a uma inicialização, há uma seta errada. Corrige-a antes de continuares.

3. Confirma esta lista:

   - há um único Início e um único Fim;
   - todas as figuras têm pelo menos uma seta a entrar e uma a sair, menos o Início e o Fim;
   - o Início só tem uma seta a sair, e o Fim só tem uma seta a entrar;
   - cada losango tem exatamente duas saídas, uma com `Sim` e outra com `Não`;
   - a seta de volta sai da última figura do corpo e chega ao losango do ciclo, e não a outra figura;
   - nenhuma seta cruza outra, e nenhuma passa por cima de uma figura;
   - o texto de cada figura é o mesmo do pseudocódigo.

### Paragem 4

O teu desenho passou no caso de teste: três passagens pelo losango do ciclo, e no fim 1 válido, 12 unidades e 1 recusado.

Pensa antes de continuares: se a seta de volta chegasse à primeira inicialização, `int pedidosValidos = 0`, o que acontecia com este caso? A resposta: no fim da primeira iteração, os contadores e o total voltavam a zero, e a leitura antecipada lia logo o valor seguinte. O 60 era substituído pelo 0 sem nunca chegar ao losango. O desenho chegava ao Fim com 0 válidos, 0 unidades e 0 recusados.

## Fase 5: uma imagem do fluxograma

O ficheiro `.drawio` é o teu fluxograma editável. É esse que abres para continuar a trabalhar ou para corrigir. Para mostrar o fluxograma a alguém, ou para o entregar, exporta-se uma imagem, que qualquer computador ou telemóvel abre sem precisar da aplicação. Uma imagem não se edita. Se precisares de mudar alguma coisa, mudas o `.drawio` e exportas a imagem outra vez. Por isso, guardas sempre os dois ficheiros.

1. Guarda primeiro o `.drawio`, com Ctrl+S ou Cmd+S.

2. Na barra de menus, escolhe "Ficheiro", depois "Exportar como" e depois "PNG...". PNG é um formato de imagem que mantém as letras nítidas.

3. Abre-se a janela "Imagem". Deixa as opções como estão, e confirma só que a opção "Fundo Transparente" está desligada. Com o fundo transparente, a imagem pode ficar ilegível quando aberta num fundo escuro.

4. Carrega em "Exportar". Se a aplicação pedir um nome e um sítio, o nome é `fluxograma-pedidos-validos.png`, e o sítio é "Aparelho" ou "Descarregar", nunca o Google Drive.

5. Vai à pasta onde a imagem ficou e abre-a.

   O que deves ver: o fluxograma inteiro, com todo o texto legível e todas as setas, incluindo a de volta.

### Paragem 5

Na tua pasta `algoritmos` estão `fluxograma-pedidos-validos.drawio` e `fluxograma-pedidos-validos.png`. Se usaste "Descarregar", passa as cópias mais recentes da pasta de transferências para a pasta `algoritmos`.

Pensa antes de terminares: se descobrires um erro no desenho depois de exportar, qual dos dois ficheiros corriges? A resposta: o `.drawio`, porque a imagem não se edita. Depois de o corrigires, exportas a imagem outra vez.

## Problemas frequentes

### A seta de volta entra no losango por cima, no mesmo ponto da seta da leitura antecipada

Largaste a seta quando o losango ficou com o contorno azul, e a aplicação escolheu o lado. Apaga a seta e desenha-a outra vez. Larga-a na marca da ponta esquerda do losango, e não no meio dele.

### A seta de volta atravessa figuras

O caminho automático passou por cima das figuras. Carrega na seta e arrasta o ponto do meio da parte vertical para a esquerda, até ela subir pela faixa livre.

### A seta ficou torta ou com um caminho estranho

Carrega na seta com o botão direito, escolhe "Limpar pontos de passagem" e ajusta outra vez.

### A ponta da seta de volta está na leitura e não no losango

Arrastaste ao contrário, do losango para a leitura. Apaga a seta e desenha-a a partir da leitura.

### Quando mexes uma figura, a seta não vai atrás dela

A seta não ficou presa à figura. Apaga-a e desenha-a outra vez. Larga o botão do rato só quando a figura de destino ficar com o contorno azul. Na seta de volta, larga-o sobre a marca da ponta esquerda do losango.

### O Sim fica no sítio quando mexes a seta

Escreveste o `Sim` numa caixa de texto solta, ao lado da seta, e não na própria seta. Apaga essa caixa e faz duplo clique exatamente em cima da linha da seta.

### O texto não cabe no losango

Carrega uma vez no losango para o selecionar e puxa um dos cantos para fora.

### Não encontras o grupo Fluxograma

Desce até ao fim da lista do painel da esquerda. Se o grupo não estiver lá, carrega em "+ Mais formas", no fundo do painel, marca "Fluxograma" e confirma. Também podes escrever o nome de uma figura, como `Decision`, na caixa de pesquisa, no topo do painel.

### Não aparece a barra de menus no topo

A janela do browser está estreita. Maximiza-a, ou usa o botão redondo com reticências, no canto superior direito. Nesse botão, o "Exportar como" aparece logo ao lado do "Ficheiro", em vez de estar dentro dele.

## Desafios

Para quem acabou e quer consolidar, na aula ou em casa. Se o tempo da aula não chegar para o primeiro desafio, termina-o no início da aula seguinte. Cada desafio é um ficheiro novo na pasta `algoritmos`. Para o criar, na barra de menus, escolhe "Ficheiro" e "Novo...". Se a aplicação perguntar que tipo de diagrama queres, escolhe o diagrama em branco. Guarda-o logo, como na preparação, com o nome que o desafio indica.

1. Um `Para` no fluxograma. Este algoritmo soma as caixas guardadas nos 3 corredores de um armazém:

   ```text
   const NUMERO_DE_CORREDORES = 3
   int totalCaixas = 0
   Para corredor de 1 até NUMERO_DE_CORREDORES
       Escreve: "Caixas no corredor ", corredor, "?"
       int caixas = ler valor
       totalCaixas = totalCaixas + caixas
   Escreve: "Total de caixas no armazém: ", totalCaixas
   ```

   Nos fluxogramas destes materiais, o `Para` não tem figura própria. Desenha-se com as figuras que já usaste, como o `Enquanto` que faz o mesmo. Por isso, o desenho tem figuras que não aparecem escritas como linhas no pseudocódigo. Guarda o desenho em `fluxograma-inventario-de-corredores.drawio`.

   a) No papel, escreve as duas instruções que o `Para` faz sem aparecerem escritas como linhas, a inicialização e a atualização. Diz onde fica cada uma no fluxograma: antes do losango, ou no fim do corpo, mesmo antes da seta de volta.

   b) Desenha o fluxograma, com essas duas figuras e o losango `corredor <= NUMERO_DE_CORREDORES?`. A seta de volta chega à ponta esquerda do losango, como na fase 3. O `Sim` sai por baixo e o `Não` pela direita.

   c) Percorre o desenho com o ponteiro do rato, com 5, 3 e 4 caixas nos três corredores. Escreve no papel quantas vezes passaste pelo losango e que total apareceu no fim.

   Exporta a imagem como `fluxograma-inventario-de-corredores.png`, como na fase 5. Pista: escreve primeiro, no papel, o mesmo ciclo com `Enquanto`. As linhas que aparecem nessa versão, e não na do `Para`, são as figuras escondidas.

2. Dois ciclos no mesmo fluxograma. Muda o algoritmo dos corredores para que o número de corredores deixe de ser uma constante. O funcionário escreve-o no início, e o algoritmo pede-o outra vez até ser pelo menos 1:

   ```text
   Escreve: "Quantos corredores tem o armazém?"
   int numeroDeCorredores = ler valor
   Enquanto numeroDeCorredores < 1
       Escreve: "Tem de haver pelo menos 1 corredor. Quantos corredores?"
       numeroDeCorredores = ler valor
   int totalCaixas = 0
   Para corredor de 1 até numeroDeCorredores
       Escreve: "Caixas no corredor ", corredor, "?"
       int caixas = ler valor
       totalCaixas = totalCaixas + caixas
   Escreve: "Total de caixas no armazém: ", totalCaixas
   ```

   Agora há dois ciclos, um a seguir ao outro. É a indentação que os separa. A linha `int totalCaixas = 0` volta a não ter indentação, e por isso já está fora do primeiro ciclo e antes do segundo. Cada ciclo tem o seu losango e a sua seta de volta, e cada seta de volta tem de chegar ao losango do seu ciclo. Guarda o desenho em `fluxograma-dois-ciclos.drawio`.

   Verifica o desenho com este caso: o funcionário escreve 0 corredores, depois 2 corredores, e depois 5 caixas e 3 caixas. Conta quantas vezes passas por cada losango e escreve o que aparece no ecrã, do princípio ao fim. Pista: planeia a disposição num papel antes de desenhar, para as duas setas de volta subirem pela faixa livre sem se cruzarem.

## Antes de terminares

- [ ] Na pasta `algoritmos` estão `fluxograma-pedidos-validos.drawio` e `fluxograma-pedidos-validos.png`.
- [ ] A seta de volta sai da última figura do corpo e chega ao losango do ciclo.
- [ ] Nenhuma seta cruza outra, e nenhuma passa por cima de uma figura.
- [ ] Ao losango do ciclo chegam duas setas e saem duas, cada uma no seu ponto do contorno.
- [ ] Cada losango tem uma saída `Sim` e uma saída `Não`, e a seta de volta não tem texto.
- [ ] Percorri o fluxograma com o caso 12, 60, 0 e cheguei a 1 pedido válido, 12 unidades e 1 pedido recusado.
- [ ] Se fiz o primeiro desafio, tenho também `fluxograma-inventario-de-corredores.drawio` e `fluxograma-inventario-de-corredores.png`.
- [ ] Se fiz o primeiro desafio, o `Para` está desenhado com as suas três peças.
- [ ] Se fiz o primeiro desafio, tenho na folha as duas instruções do `Para`, o número de passagens pelo losango e o total.
- [ ] Consegues explicar, por palavras tuas, porque é que a seta de volta tem de chegar ao losango do ciclo, e não a outra figura.

![Rodapé](../imagens/rodape.png)
