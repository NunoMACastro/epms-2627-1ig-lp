![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: o primeiro fluxograma no diagrams.net

UC: UC00245

Blocos: ALG02

Requisitos: UC00245-R04, UC00245-K05, UC00245-A06, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Laboratório do bloco ALG02, acompanha o [guia](02-pseudocodigo-e-fluxogramas.md) |
| Fundamento curricular | Unidade de competência UC00245, bloco ALG02 |
| Duração | 40 minutos dos 300 do bloco: é a prática guiada no computador |
| Evidência a guardar | Os ficheiros `.drawio` e as imagens `.png` dos dois fluxogramas deste laboratório |

Este laboratório diz o que fazer, passo a passo, com a aplicação de fluxogramas aberta ao lado. As explicações do porquê estão no [guia](02-pseudocodigo-e-fluxogramas.md): quando um passo usa uma ideia do guia, o texto diz em que secção ela está explicada.

Vais fazer duas coisas. Primeiro, com a ajuda deste documento, desenhas na aplicação o fluxograma do exemplo dos cadernos, que já conheces do guia. Depois, na última parte, desenhas sozinho o fluxograma de outro algoritmo.

## Antes de começar

Antes do laboratório deves ter lido, no guia, a secção "Os símbolos do fluxograma" e o exemplo explicado dos cadernos, até ao passo 4, onde está o fluxograma. O laboratório não repete essas explicações: aplica-as.

Precisas de um computador com um browser (Chrome, Edge, Firefox ou Safari) e ligação à internet. Tem o guia aberto noutro separador do browser, ou o pseudocódigo dos cadernos escrito em papel, porque vais copiar o texto de cada instrução.

A aplicação chama-se diagrams.net, e também é conhecida por draw.io, que é o nome antigo. Usa-se no browser, é gratuita e não precisa de conta. Os ficheiros que ela cria terminam em `.drawio`.

Decide antes de começar onde vais guardar os ficheiros desta disciplina: numa pasta do computador, numa pen ou no sítio que o professor indicar. Cria lá uma pasta chamada `algoritmos`. Todos os ficheiros deste laboratório têm nomes em minúsculas, com hífenes entre as palavras e sem acentos nem espaços, como `fluxograma-caixas-de-cadernos.drawio`. Um nome assim funciona em qualquer computador e diz o que o ficheiro contém sem ser preciso abri-lo.

A aplicação muda de aspeto de vez em quando. Os nomes dos menus e dos botões deste laboratório foram confirmados em setembro de 2026, com a aplicação em português. Se um nome no teu ecrã não for exatamente igual, procura o que faz a mesma coisa: os passos são os mesmos.

## Parte 1: abrir a aplicação e conhecer o ecrã

1. Abre o browser, maximiza a janela para ocupar o ecrã todo, e escreve na barra de endereços `https://app.diagrams.net/?lang=pt`. A parte final, `?lang=pt`, pede à aplicação que apareça em português. Sem ela, a aplicação usa a língua do browser, que pode ser o inglês.
2. A aplicação abre logo um diagrama em branco, chamado "Diagrama sem nome". Não te pergunta nada nem te pede conta.

Repara nas quatro zonas do ecrã, porque vais usá-las todas:

| Zona | Onde está | Para que serve |
| --- | --- | --- |
| Painel das figuras | à esquerda | tem as figuras, arrumadas em grupos, e no topo uma caixa de pesquisa onde se lê "Escreva / para pesquisar" |
| Página | ao centro, a zona branca com uma grelha de quadrados | é onde desenhas; a grelha só serve para ajudar a alinhar |
| Painel de formatação | à direita, com os separadores "Diagrama" e "Estilo" | muda o aspeto do que estiver selecionado; neste laboratório quase não precisas dele |
| Barra de menus | no topo, com Ficheiro, Editar, Visualização, Ordenar, Extras e Ajuda | o menu "Ficheiro" tem tudo o que é guardar, abrir e exportar |

Neste laboratório só vais usar o menu "Ficheiro", da barra de menus. Os passos seguintes dizem sempre o caminho completo, por exemplo "Ficheiro" e depois "Guardar como...": carregas em "Ficheiro", abre-se uma lista, e escolhes a opção nessa lista.

A aplicação muda de aspeto conforme a largura da janela. Se a janela do browser estiver estreita, por exemplo a ocupar só metade do ecrã, a barra de menus desaparece e aparece em vez dela um botão redondo com reticências (três pontos), no canto superior direito. Esse botão abre um menu com "Ficheiro" e "Exportar como" lado a lado. A forma mais simples de seguir este laboratório é maximizar a janela; se não puderes, usa esse botão sempre que os passos falarem da barra de menus, e procura "Exportar como" diretamente no menu, e não dentro de "Ficheiro".

Neste momento, o diagrama só existe dentro do separador do browser. Se fechares o separador, perdes tudo. É por isso que a parte seguinte é guardar, antes de desenhar.

## Parte 2: guardar o ficheiro no teu computador

Guardar logo no início dá um nome e um sítio ao ficheiro. A partir daí, cada vez que guardares, o trabalho vai para o mesmo ficheiro.

1. Na barra de menus, carrega em "Ficheiro".
2. Na lista que se abre, escolhe "Guardar como...".
3. Abre-se a janela "Guardar como", com três campos. No campo "Guardar como:", apaga o que lá estiver e escreve `fluxograma-caixas-de-cadernos.drawio`. Mantém o `.drawio` no fim.
4. No campo "Tipo:" deixa ficar "Ficheiro XML (.drawio)". É o formato próprio da aplicação, o único que ela consegue voltar a abrir para continuares a editar.
5. O campo "Onde:" é o mais importante, e vem com "Google Drive" escolhido. Tens de o mudar: escolhe "Aparelho", que guarda o ficheiro numa pasta do teu computador. Se "Aparelho" não funcionar no teu browser, escolhe "Descarregar", que põe o ficheiro na pasta de transferências.
6. Carrega em "Guardar". Com "Aparelho", abre-se a janela habitual do sistema para escolheres a pasta: escolhe a pasta `algoritmos` que criaste e confirma. Com "Descarregar", o ficheiro vai para a pasta de transferências do browser, e no fim do laboratório passas a cópia mais recente para a pasta `algoritmos`.
7. Confirma que o nome que escreveste aparece agora no topo da aplicação, onde antes estava "Diagrama sem nome".

As outras opções do campo "Onde:" não servem aqui. Google Drive, OneDrive, Microsoft 365 e GitHub pedem uma conta nesses serviços. "Navegador" guarda o ficheiro dentro do próprio browser, e basta alguém limpar os dados do browser, ou mudares de computador, para o perderes.

Daqui para a frente, para guardar basta carregar em Ctrl+S, ou Cmd+S num Mac, ou escolher "Ficheiro" e depois "Guardar", na barra de menus. Guarda muitas vezes: no fim de cada parte deste laboratório, pelo menos. Se escolheste "Descarregar", cada vez que guardas é descarregada uma cópia nova, e o browser pode acrescentar um número ao nome. No fim, fica com a mais recente.

## Parte 3: encontrar as figuras de fluxograma

O painel da esquerda tem as figuras arrumadas em grupos com nome: Rascunho, Geral, Diversos, Avançado, Básico, Setas, Fluxograma e outros. As figuras que te interessam estão no grupo "Fluxograma".

1. Desce no painel da esquerda com a roda do rato, ou com o dedo no trackpad. O grupo "Fluxograma" fica perto do fim da lista.
2. Carrega no nome "Fluxograma" para abrir o grupo e ver as figuras.
3. Se o grupo não aparecer na lista, carrega no botão "+ Mais formas", no fundo do painel da esquerda. Abre-se a janela "Formas". Confirma que "Fluxograma" está marcado e fecha a janela com o botão de confirmar. O grupo passa a aparecer no painel.

Passa o rato por cima das figuras do grupo, devagar. Ao lado de cada uma aparece uma pré-visualização com o nome da figura. Os nomes aparecem em inglês, mesmo com a aplicação em português, e por isso convém saberes o que cada um quer dizer:

| Figura | Nome que aparece | O que quer dizer | Para que a usas |
| --- | --- | --- | --- |
| Retângulo de pontas redondas | Terminator | terminal, o sítio onde o algoritmo começa ou acaba | `Início` e `Fim`; é o oval do guia |
| Paralelogramo | Data | dados, que entram ou saem do algoritmo | `LER` e `ESCREVER` |
| Retângulo | Process | processo, ou seja, processamento | atribuições e contas |
| Losango | Decision | decisão | só a partir do guia 03 |

O grupo "Fluxograma" tem muitas outras figuras, com nomes como Display, Document ou Manual Input. Pertencem a convenções de fluxograma mais pormenorizadas do que a desta disciplina, e não as vais usar. Usa sempre as quatro da tabela, e sempre do grupo "Fluxograma", mesmo que encontres figuras parecidas noutros grupos, como o "Geral".

## Parte 4: pôr as figuras na página, com o texto

O fluxograma dos cadernos tem 8 figuras: uma por cada uma das seis instruções do pseudocódigo, mais o início e o fim. A razão está no passo 4 do exemplo explicado do guia. Esta é a lista completa, pela ordem de cima para baixo:

| Ordem | Figura | Nome que aparece | Texto a escrever |
| --- | --- | --- | --- |
| 1 | Retângulo de pontas redondas | Terminator | `Início` |
| 2 | Paralelogramo | Data | `ESCREVER "Quantos cadernos foram encomendados?"` |
| 3 | Paralelogramo | Data | `LER cadernos` |
| 4 | Retângulo | Process | `caixasCompletas ← cadernos DIV UNIDADES_POR_CAIXA` |
| 5 | Retângulo | Process | `unidadesSoltas ← cadernos RESTO UNIDADES_POR_CAIXA` |
| 6 | Paralelogramo | Data | `ESCREVER "Caixas completas: ", caixasCompletas` |
| 7 | Paralelogramo | Data | `ESCREVER "Unidades soltas: ", unidadesSoltas` |
| 8 | Retângulo de pontas redondas | Terminator | `Fim` |

### Pôr a primeira figura

1. No grupo "Fluxograma", carrega na figura Terminator e, sem largar o botão do rato, arrasta-a para a página. Larga-a perto do topo, ao centro.
2. A figura fica selecionada, com um contorno azul e uns quadradinhos nos cantos. Se carregares numa zona vazia da página, deixa de estar selecionada; se carregares nela, volta a ficar.

### Escrever o texto dentro da figura

1. Faz duplo clique dentro da figura. Aparece um cursor a piscar.
2. Se a figura já tiver algum texto, apaga-o. Escreve `Início`.
3. Para acabar de escrever, carrega numa zona vazia da página. O texto fica dentro da figura.

Se te enganares, faz outra vez duplo clique e corrige. Se fizeres uma asneira maior, como apagar a figura sem querer, carrega em Ctrl+Z, ou Cmd+Z num Mac, que desfaz a última ação. Podes carregar várias vezes para desfazer várias ações.

### Pôr as outras figuras

Repete o arrastar e o duplo clique para as figuras 2 a 8, sempre com a figura e o texto da tabela. Três conselhos poupam-te tempo:

- Deixa espaço entre as figuras, mais ou menos a altura de uma figura, para caberem as setas.
- Mantém as figuras em coluna. Quando arrastas uma figura, a aplicação mostra linhas de guia coloridas quando ela fica alinhada com outra. Larga a figura quando a linha de guia vertical aparecer: ficam todas centradas umas por baixo das outras.
- Para repetir uma figura já feita, copia-a. Seleciona um paralelogramo, carrega em Ctrl+C e depois em Ctrl+V (Cmd+C e Cmd+V num Mac). Aparece uma cópia ao lado, que arrastas para o sítio certo, e só tens de mudar o texto.

Se o texto não couber na figura, seleciona-a e arrasta um dos quadradinhos azuis dos cantos para a alargar. As instruções das figuras 4 e 5 são compridas: vale a pena alargar esses dois retângulos para cada instrução caber numa só linha.

### Escrever a seta da atribuição

As figuras 4 e 5 têm a seta `←`, que não está no teclado. A forma mais simples de a escrever é copiá-la e colá-la:

1. Neste documento, seleciona com o rato só a seta desta linha: ←
2. Copia-a com Ctrl+C, ou Cmd+C num Mac.
3. Na aplicação, enquanto escreves o texto da figura 4, cola-a com Ctrl+V, ou Cmd+V, no sítio certo, e continua a escrever.

A seta fica guardada para colar até copiares outra coisa, por isso serve também para a figura 5. Se a seta colada aparecer com outro tamanho, outra letra ou um fundo de outra cor, desfaz com Ctrl+Z e cola sem formatação: Ctrl+Shift+V no Windows, ou Cmd+Option+Shift+V num Mac.

Não substituas a seta por `<-` nem por `=`. O texto de cada figura tem de ser igual ao do pseudocódigo, e a secção "Atribuição: dar um valor não é perguntar se é igual", no guia, explica porque é que o `=` não serve.

Quando tiveres as 8 figuras com o texto, guarda (Ctrl+S ou Cmd+S).

## Parte 5: ligar as figuras com setas

O fluxograma dos cadernos tem 7 setas, uma entre cada par de figuras seguidas. Oito figuras em coluna precisam de sete ligações.

1. Passa o rato por cima da figura 1, a do Início, sem carregar. Aparecem quatro pequenas setas azuis, uma de cada lado da figura.
2. Carrega na seta azul de baixo e, sem largar o botão do rato, arrasta até à figura 2.
3. Quando a figura 2 ficar com um contorno azul, larga o botão. Fica uma seta desenhada da figura 1 para a figura 2, com a ponta virada para a figura 2.
4. Faz o mesmo da figura 2 para a 3, da 3 para a 4, e assim até à 8.

A ponta de cada seta tem de apontar para a figura seguinte, que é o sentido em que o algoritmo é executado. Se uma seta ficar ao contrário, seleciona-a, apaga-a com a tecla Delete ou Backspace, e desenha-a outra vez a partir da figura certa.

Uma seta só está bem feita se estiver presa às duas figuras. Há uma forma simples de o confirmar: arrasta uma figura um pouco para o lado. Se as setas a acompanharem, esticando-se, estão presas. Se uma ponta ficar parada no sítio antigo, essa seta está solta: apaga-a e desenha-a outra vez, largando só quando a figura de destino ficar com o contorno azul. Depois, carrega em Ctrl+Z para a figura voltar ao sítio.

Num algoritmo sequencial, as setas não levam texto. As setas com texto, com Sim e Não, aparecem no guia 03, quando houver decisões.

Guarda outra vez (Ctrl+S ou Cmd+S).

## Parte 6: verificar o fluxograma contra o pseudocódigo

Antes de dares o desenho por acabado, verifica-o como o guia ensina no passo 4 do exemplo explicado, com o pseudocódigo ao lado:

- [ ] Tem 8 figuras e 7 setas.
- [ ] Tem um único Início, no topo, e um Fim, em baixo, os dois em retângulos de pontas redondas.
- [ ] O `ESCREVER` e o `LER` do princípio e os dois `ESCREVER` do fim estão em paralelogramos, e as duas atribuições estão em retângulos.
- [ ] O texto de cada figura é igual ao da instrução correspondente, letra a letra: as aspas, as vírgulas, os espaços dentro das aspas, a seta, `DIV` e `RESTO` em maiúsculas.
- [ ] As figuras estão pela mesma ordem que as instruções do pseudocódigo.
- [ ] Todas as setas estão presas nas duas pontas e apontam para baixo.

Depois percorre o fluxograma com o dedo no ecrã, como se a pessoa tivesse escrito 30 cadernos. Em cada paralelogramo de `ESCREVER`, diz em voz baixa o que aparece no ecrã. Tens de chegar ao mesmo que a primeira tabela de trace do passo 5 do guia: a pergunta, depois "Caixas completas: 2" e por fim "Unidades soltas: 6". Se não chegares, há uma figura fora do sítio ou com o texto errado.

## Parte 7: exportar uma imagem do fluxograma

O ficheiro `.drawio` é o teu fluxograma editável: é esse que abres para continuar a trabalhar ou para corrigir. Para mostrar o fluxograma a alguém, ou para o entregar, exporta-se uma imagem, que qualquer computador ou telemóvel abre sem precisar da aplicação. Uma imagem não se edita: se precisares de mudar alguma coisa, mudas o `.drawio` e exportas a imagem outra vez. Por isso guardas sempre os dois ficheiros.

1. Guarda primeiro o `.drawio` (Ctrl+S ou Cmd+S).
2. Na barra de menus, escolhe "Ficheiro", depois "Exportar como" e depois "PNG...". PNG é um formato de imagem que mantém as letras nítidas.
3. Abre-se uma janela chamada "Imagem", com as opções da imagem. Em "Tamanho", escolhe "Diagrama", para a imagem ter só o fluxograma e não a página inteira com espaço vazio à volta. Confirma que "Fundo Transparente" está desligado: com o fundo transparente, a imagem pode ficar ilegível quando aberta num fundo escuro. Deixa as outras opções, como "Zoom" e "Incluir uma cópia do meu diagrama", como estão.
4. Carrega em "Exportar".
5. Se a aplicação pedir um nome e um sítio, faz como na parte 2: o nome é `fluxograma-caixas-de-cadernos.png`, e o sítio é "Aparelho" ou "Descarregar", nunca Google Drive nem "Navegador".
6. Vai à pasta onde a imagem ficou e abre-a com duplo clique. Confirma que se vê o fluxograma inteiro, com as oito figuras e o texto legível.

Por fim, confirma que o `.drawio` ficou mesmo guardado. Fecha o separador da aplicação, abre outra vez `https://app.diagrams.net/?lang=pt`, e na barra de menus escolhe "Ficheiro", "Abrir de" e o sítio onde o guardaste. Escolhe o ficheiro. Se o fluxograma aparecer como o deixaste, está guardado. Se a aplicação te perguntar se queres guardar alterações a um diagrama sem nome, podes responder que não: o teu trabalho está no ficheiro que acabaste de abrir.

## Parte 8: desenhar sozinho

Agora sem a lista de figuras. Uma loja faz, de vez em quando, a contagem do stock: conta à mão quantas unidades de um artigo estão na prateleira e compara com o número que o registo do computador diz que devia haver. Se os dois números não coincidirem, alguém tem de investigar porquê. Este algoritmo mostra de quantas unidades é a diferença, sem sinal, porque tanto faz faltarem unidades como sobrarem: nos dois casos há uma diferença a investigar.

```text
ALGORITMO DiferencaDeInventario
VARIÁVEIS
    stockRegistado: inteiro
    stockContado: inteiro
    diferenca: inteiro
INÍCIO
    ESCREVER "Quantas unidades diz o registo?"
    LER stockRegistado
    ESCREVER "Quantas unidades foram contadas na prateleira?"
    LER stockContado
    diferenca ← ABS(stockRegistado - stockContado)
    ESCREVER "Diferença a investigar: ", diferenca, " unidades"
FIM
```

A função `ABS` está explicada no guia, na secção "Funções predefinidas".

1. Cria um diagrama novo: na barra de menus, escolhe "Ficheiro" e depois "Novo...". A aplicação pode abrir o diagrama novo noutro separador do browser. Se te perguntar que tipo de diagrama queres, escolhe o diagrama em branco.
2. Guarda-o logo, como na parte 2, com o nome `fluxograma-diferenca-de-inventario.drawio`.
3. Antes de desenhar, conta em papel quantas figuras e quantas setas o fluxograma vai ter, e decide a forma de cada figura. Escreve essa lista: é o que vais comparar com o desenho no fim.
4. Desenha o fluxograma, com as figuras certas, o texto de cada instrução igual ao do pseudocódigo e as setas presas nas duas pontas.
5. Verifica-o com a lista da parte 6, adaptada a este algoritmo.
6. Percorre o fluxograma com o dedo para duas contagens diferentes e escreve, para cada uma, tudo o que aparece no ecrã. Primeira: o registo diz 120 e foram contadas 115. Segunda: o registo diz 80 e foram contadas 86. Explica numa frase porque é que a segunda não mostra um número negativo.
7. Guarda o `.drawio` e exporta a imagem, com o nome `fluxograma-diferenca-de-inventario.png`.
8. Troca de computador com um colega. Cada um verifica o fluxograma do outro com a lista da parte 6 e diz-lhe se encontrou uma figura a mais, uma a menos, uma forma errada, um texto diferente do pseudocódigo ou uma seta solta.

Concluíste quando o teu fluxograma tiver uma figura por instrução, mais o início e o fim, com as formas certas, quando as duas contagens do ponto 6 estiverem escritas e quando os dois ficheiros deste fluxograma estiverem guardados na tua pasta.

## Se alguma coisa correr mal

| O que acontece | O que fazer |
| --- | --- |
| A aplicação aparece em inglês | Abre-a com o endereço `https://app.diagrams.net/?lang=pt` |
| Não vejo a barra de menus, só um botão redondo com reticências no canto superior direito | A janela está estreita: maximiza-a, ou usa esse botão, onde estão "Ficheiro" e "Exportar como" |
| A imagem tem muito espaço vazio à volta do fluxograma | Exporta outra vez com "Tamanho" em "Diagrama", na janela "Imagem" |
| Não encontro o grupo "Fluxograma" | Desce até ao fim do painel da esquerda; se não estiver lá, usa o botão "+ Mais formas" |
| Apaguei ou estraguei alguma coisa | Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação; repete para desfazer mais |
| A seta não fica presa à figura | Larga o botão do rato só quando a figura de destino ficar com contorno azul |
| O texto não cabe na figura | Seleciona a figura e alarga-a pelos quadradinhos azuis dos cantos |
| O "Guardar como" pede para entrar numa conta | O campo "Onde:" ficou em Google Drive ou noutro serviço: muda para "Aparelho" ou "Descarregar" |
| Guardei no "Navegador" | Faz outra vez "Guardar como" e escolhe "Aparelho" ou "Descarregar" |
| Não sei onde ficou o ficheiro | Com "Descarregar", está na pasta de transferências do computador |
| A grelha de quadrados aparece na página | É só uma ajuda para alinhar, e normalmente não aparece na imagem exportada |

## O que fica guardado no fim

Na tua pasta `algoritmos` tens de ter quatro ficheiros:

- `fluxograma-caixas-de-cadernos.drawio` e `fluxograma-caixas-de-cadernos.png`;
- `fluxograma-diferenca-de-inventario.drawio` e `fluxograma-diferenca-de-inventario.png`.

As imagens são a evidência que entregas, pela forma de entrega que o professor indicar. Os ficheiros `.drawio` guardas tu, porque vais voltar a abri-los: na ficha deste bloco vais desenhar mais fluxogramas na aplicação, e no laboratório do guia 03 vais acrescentar a figura que ainda falta, o losango das decisões.

![Rodapé](../imagens/rodape.png)
