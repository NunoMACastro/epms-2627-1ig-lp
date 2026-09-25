![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Decisões e validação

UC: UC00245

Blocos: ALG03

Requisitos: UC00245-R03, UC00245-R04, UC00245-K05, UC00245-K06, UC00245-A06, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Laboratório do bloco ALG03, acompanha o [guia](03-decisoes-e-validacao.md) |
| Fundamento curricular | Unidade de competência UC00245, bloco ALG03 |
| Duração | 60 minutos dos 300 do bloco: é a prática guiada no computador |
| Evidência a guardar | Os ficheiros `.drawio` e as imagens `.png` dos dois fluxogramas deste laboratório, e as folhas das partes 4 e 5, com os caminhos seguidos |

## O que vais fazer

Neste laboratório vais desenhar no diagrams.net fluxogramas com decisões. No fim deves conseguir:

- pôr um losango no desenho e escrever nele uma condição;
- ligar as duas saídas do losango e escrever `Sim` e `Não` nas setas;
- levar os ramos de uma decisão a juntarem-se de novo antes de o algoritmo continuar;
- seguir com o dedo o caminho de cada caso de teste e confirmar que todos têm um caminho, e um só.

Não vais aprender teoria nova. Tudo o que desenhas aqui está explicado no [guia](03-decisoes-e-validacao.md), e este documento diz-te em cada parte que secção do guia deves ter aberta ao lado.

## O que precisas antes

Do [laboratório do bloco 02](02-pseudocodigo-e-fluxogramas-laboratorio.md) precisas de saber abrir o diagrams.net, guardar o ficheiro no computador, encontrar o grupo Fluxograma, pôr figuras na página, escrever texto dentro delas, ligá-las com setas presas nas duas pontas e exportar uma imagem PNG. Este laboratório não volta a explicar esses passos em pormenor. Se te esqueceres de algum, volta à parte desse laboratório que o explica.

Do guia deste bloco precisas das secções "Seleção simples", "Seleção composta" e "Seleção encadeada", e de todo o exemplo explicado, sobretudo o passo 3 (a árvore de casos), o passo 4 (a tabela de casos esperados), o passo 6 (o pseudocódigo) e o passo 8 (o fluxograma).

Material: o computador com um browser, e papel e caneta para a parte 4 e para a parte 5.

## Os nomes das figuras na aplicação

No painel da esquerda do diagrams.net há vários grupos de figuras. O grupo **Fluxograma** é o último da lista, e é preciso descer até ao fim para o encontrar. Quando passas o rato por cima de uma figura desse grupo, a aplicação mostra o nome dela, e esse nome aparece em inglês mesmo com a aplicação em português. Estas são as quatro figuras de que precisas:

| Figura | Nome que vais ver | O que quer dizer | Para que serve |
| --- | --- | --- | --- |
| Retângulo com as pontas redondas | Terminator | "Terminal": onde o algoritmo começa ou acaba | Início e Fim |
| Paralelogramo | Data | "Dados": é por ali que os dados entram e saem | `LER` e `ESCREVER` |
| Retângulo | Process | "Processamento" | Contas e atribuições |
| Losango | Decision | "Decisão" | Uma condição, com duas saídas |

A figura nova deste laboratório é a Decision, o losango. As outras três já as usaste no laboratório 02. Neste laboratório não vais precisar do retângulo, porque os algoritmos que vais desenhar não fazem contas.

## Parte 1: Preparar o ficheiro (5 min)

1. Abre o browser e vai a `https://app.diagrams.net/?lang=pt`. O `?lang=pt` no fim do endereço pede a aplicação em português.
2. A aplicação abre logo um diagrama em branco, chamado "Diagrama sem nome".
3. Guarda-o já, antes de desenhares, para não perderes trabalho. Na barra de menus, no topo da aplicação, carrega em **Ficheiro** e depois em **Guardar como...**.
4. No diálogo que aparece, no campo **Guardar como:**, escreve o nome `fluxograma-classificar-nota.drawio`.
5. No campo **Onde:**, a aplicação sugere o Google Drive. Muda para **Aparelho**, para o ficheiro ficar no computador. Se a opção Aparelho não funcionar no teu computador, escolhe **Descarregar**, e o ficheiro vai para a pasta de transferências.
6. Carrega em **Guardar** e escolhe a pasta `algoritmos`, onde guardaste os fluxogramas do laboratório 02.

A partir daqui, sempre que quiseres guardar, usa Ctrl+S (Cmd+S no Mac), ou **Ficheiro** e **Guardar**, na barra de menus.

**Se não vires a barra de menus.** Com o browser maximizado, num ecrã de computador, a aplicação mostra no topo a barra de menus, com Ficheiro, Editar, Visualização, Ordenar, Extras e Ajuda. Se a janela do browser for estreita, por exemplo se ocupar só metade do ecrã, a barra desaparece e o menu passa para um **botão redondo com reticências**, no canto superior direito. Maximiza a janela e a barra volta. Se não puderes, usa esse botão: tem as mesmas opções, e lá o **Exportar como** aparece logo ao lado do **Ficheiro**, em vez de estar dentro dele.

## Parte 2: A primeira decisão (10 min)

Tem aberta ao lado a secção "Seleção simples" do guia. Vais desenhar esse exemplo, o aviso de stock baixo, para aprenderes a técnica com um algoritmo pequeno. No fim desta parte apagas este desenho e começas o da parte 3 na página limpa.

O fluxograma tem três figuras: um losango com `stock < 5?`, um paralelogramo com o aviso e um paralelogramo com "Verificação concluída". Para o desenho ficar arrumado, segue sempre a mesma convenção: a saída `Não` sai por baixo do losango e a saída `Sim` sai pela direita. Quem ler os teus fluxogramas passa a saber onde procurar cada uma.

### O losango

1. No painel da esquerda, desce até ao fim da lista e abre o grupo **Fluxograma**. Passa o rato pelas figuras até encontrares a que se chama **Decision**, o losango.
2. Arrasta o losango para a página, perto do topo.
3. Faz duplo clique dentro do losango e escreve `stock < 5?`. Clica fora da figura para terminar.

O ponto de interrogação não é obrigatório, mas ajuda: lembra a quem lê que dentro do losango está uma pergunta, e que a resposta é sim ou não.

Os sinais `<` e `>` estão numa tecla própria do teclado, e o `>` obtém-se com Shift. Nos teclados portugueses essa tecla fica muitas vezes junto ao Z. Se não a encontrares, pede ajuda: os teclados variam de computador para computador.

### A saída Sim

1. Arrasta um paralelogramo (a figura **Data**) para a direita do losango, à mesma altura. Escreve dentro `ESCREVER "Atenção: stock baixo"`.
2. Passa o rato por cima do losango. Aparecem pequenas setas azuis nos quatro lados. Carrega na seta azul do lado direito e arrasta até ao paralelogramo. Larga quando o paralelogramo ficar com o contorno azul: é esse contorno que mostra que a seta ficou presa à figura.
3. Agora escreve o nome da saída. Faz duplo clique a meio da seta que acabaste de desenhar. Aparece um espaço para escrever em cima da linha. Escreve `Sim` e clica fora.

### A saída Não e o ponto de encontro

1. Arrasta outro paralelogramo para baixo do losango, com espaço entre os dois. Escreve dentro `ESCREVER "Verificação concluída"`.
2. Liga a seta azul de baixo do losango a este paralelogramo. Faz duplo clique a meio da seta e escreve `Não`.
3. Falta o ponto de encontro. Liga o paralelogramo do aviso ao paralelogramo de "Verificação concluída": passa o rato pelo aviso, arrasta a seta azul de baixo até ao outro paralelogramo e larga quando ele ficar com o contorno azul. Esta seta não leva texto, porque não sai de um losango.

Olha para o que desenhaste e compara com o fluxograma da secção "Seleção simples" do guia. O ramo do `Sim` passa pelo aviso; o ramo do `Não` vai direto a "Verificação concluída", sem nenhuma figura pelo caminho. Os dois ramos juntam-se no paralelogramo de "Verificação concluída", e esse ponto de encontro corresponde ao `FIM SE`. É isto que quer dizer "os ramos voltam a juntar-se": seja qual for a resposta ao losango, o algoritmo acaba por passar pela mesma figura e continua a partir daí.

### Verificar e apagar

Segue o desenho com o dedo, primeiro com o stock a valer 3 e depois com o stock a valer 12. Com 3, `3 < 5` é verdadeiro: sais pelo `Sim`, passas pelo aviso e chegas a "Verificação concluída". Com 12, sais pelo `Não` e chegas diretamente a "Verificação concluída". Nos dois casos o dedo chega ao mesmo sítio.

Confirma três coisas antes de avançares: do losango saem exatamente duas setas; cada uma tem o seu texto, `Sim` ou `Não`; e as duas acabam por chegar à mesma figura.

Agora apaga este desenho. Carrega com o rato numa zona vazia da página e arrasta um retângulo que envolva as três figuras e as setas. Tudo o que ficar dentro do retângulo fica selecionado. Carrega na tecla Delete ou Backspace. A página fica limpa para a parte seguinte.

## Parte 3: O fluxograma do exemplo explicado (20 min)

Tem aberto ao lado o guia, no passo 6 (o pseudocódigo) e no passo 8 (o fluxograma) do exemplo explicado. Vais desenhar esse fluxograma, figura a figura, pela ordem do pseudocódigo. O desenho vai ter uma coluna ao centro, com o caminho principal a descer, e uma coluna à direita, com os resultados que saem pelo `Sim` de cada losango.

### O início e a entrada

1. Arrasta um **Terminator** para o topo da página e escreve `Início`.
2. Por baixo, um paralelogramo (**Data**) com `ESCREVER pergunta`. Liga o Início a ele.
3. Por baixo, outro paralelogramo com `LER nota`. Liga o anterior a este.

Estes três passos já os conheces do laboratório 02. Faz as ligações pela seta azul de baixo de cada figura, e larga sempre com a figura de destino de contorno azul.

### O primeiro losango: a validação

1. Por baixo de `LER nota`, arrasta um losango (**Decision**) e escreve `nota < NOTA_MINIMA OU nota > NOTA_MAXIMA?`.
2. O texto é comprido e não cabe bem num losango pequeno. Clica uma vez no losango para o selecionar: aparecem pequenos pontos nos cantos e a meio dos lados. Puxa um dos cantos para fora até o texto caber, de preferência numa ou duas linhas.
3. Liga `LER nota` ao losango.
4. À direita do losango, à mesma altura, arrasta um paralelogramo com `ESCREVER "Nota inválida"`.
5. Liga a seta azul do lado direito do losango a este paralelogramo e escreve `Sim` na seta.

Pensa no que acabaste de desenhar antes de continuares: quem sai pelo `Sim` do primeiro losango é uma nota fora da escala, e vai direto para a mensagem de erro. Não passa por mais nenhum losango.

### O segundo losango: o SENÃO SE

1. Por baixo do primeiro losango, com espaço entre os dois, arrasta outro losango e escreve `nota >= LIMIAR_POSITIVA?`.
2. Liga a seta azul de baixo do primeiro losango a este segundo losango e escreve `Não` na seta.

Este é o desenho do `SENÃO SE`: o segundo losango está pendurado na saída `Não` do primeiro. Só se chega a ele quando a validação é falsa, isto é, quando a nota é válida.

3. À direita do segundo losango, um paralelogramo com `ESCREVER "Positiva"`. Liga-o pela seta azul do lado direito do losango e escreve `Sim`.
4. Por baixo do segundo losango, um paralelogramo com `ESCREVER "Negativa"`. Liga-o pela seta azul de baixo e escreve `Não`.

O paralelogramo "Negativa" é o `SENÃO`: é para lá que vai a nota quando as duas condições são falsas.

### O fim e o ponto de encontro

1. Por baixo de "Negativa", arrasta um **Terminator** e escreve `Fim`. Liga "Negativa" ao Fim.
2. Liga agora "Positiva" ao Fim, e depois "Nota inválida" ao Fim. As duas setas descem pela coluna da direita e entram no Fim.

Os três caminhos juntam-se no Fim, e esse ponto de encontro corresponde ao `FIM SE` do pseudocódigo. Se uma seta atravessar outra figura ou fizer um percurso estranho, clica nela e arrasta o pequeno ponto que aparece a meio da linha até ela passar por onde queres.

### Conferir com o guia

Conta as figuras e as setas do teu desenho e compara com o fluxograma do passo 8 do guia:

- nove figuras: dois terminais (Início e Fim), cinco paralelogramos (a pergunta, o `LER`, e as três mensagens) e dois losangos;
- dez setas, das quais quatro têm texto: as duas que saem de cada losango;
- cada losango com uma seta `Sim` e uma seta `Não`, e nenhum com uma só saída;
- nenhuma seta solta, sem figura numa das pontas.

Se o teu desenho tiver uma figura a mais ou a menos, compara-o figura a figura com o pseudocódigo do passo 6, pela mesma ordem, e descobre qual é. Guarda o ficheiro (Ctrl+S, ou Cmd+S no Mac).

## Parte 4: Seguir cada caminho com o dedo (10 min)

Um fluxograma de decisões está certo quando cada caso de teste tem um caminho, e um só, do início até ao fim, e esse caminho acaba na mensagem que o enunciado pede. É isso que vais confirmar agora, com a tabela de casos esperados do passo 4 do guia.

Copia esta tabela para uma folha. Para cada nota, põe o dedo no Início do teu desenho e segue as setas. Em cada losango, calcula a condição com o valor da nota e sai pelo `Sim` ou pelo `Não` conforme o resultado. Escreve por onde saíste de cada losango e a mensagem a que chegaste. As duas primeiras linhas estão preenchidas para veres como se faz.

| Nota | Saída do primeiro losango | Saída do segundo losango | Mensagem a que chegaste | Coincide com o esperado? |
| ---: | --- | --- | --- | --- |
| -1 | Sim, porque `-1 < 0` é verdadeiro | não se chega a ele | Nota inválida | sim |
| 0 | Não, porque `0 < 0` e `0 > 20` são falsos | Não, porque `0 >= 10` é falso | Negativa | sim |
| 1 | | | | |
| 9 | | | | |
| 10 | | | | |
| 11 | | | | |
| 19 | | | | |
| 20 | | | | |
| 21 | | | | |

Quando tiveres as nove linhas, responde na mesma folha a quatro perguntas:

1. Cada caso seguiu um caminho só, sem teres de escolher entre duas setas em nenhum losango?
2. Cada uma das três mensagens foi alcançada por pelo menos um caso? Se houvesse uma mensagem a que nenhum caso chegasse, ou faltava um caso na tabela, ou o desenho tinha um caminho impossível.
3. Todos os caminhos acabaram no Fim?
4. Houve alguma nota fora da escala que chegasse ao segundo losango? Explica porquê com a regra da seleção encadeada que está no guia.

Para terminar a parte 4, guarda o ficheiro `.drawio` e exporta a imagem. Na barra de menus, carrega em **Ficheiro**, depois em **Exportar como** e depois em **PNG...**. Abre-se a janela **Imagem**. Mantém as opções como estão, com a opção **Fundo Transparente** desligada, e carrega em **Exportar**. Se a aplicação te pedir um nome e um sítio, faz como na parte 7 do laboratório 02: o nome é `fluxograma-classificar-nota.png` e a pasta é a `algoritmos`, nunca o Google Drive nem o Navegador.

## Parte 5: Trabalho autónomo, a caixa de envio (15 min)

Agora sem passos dados. O problema é novo, mas a técnica é a mesma das partes 3 e 4. O pseudocódigo já está escrito, porque nesta parte o que treinas é o desenho na aplicação e a verificação dos caminhos. Escrever o pseudocódigo de raiz é o que vais fazer na ficha.

> Uma loja online escolhe a caixa de envio pelo peso da encomenda, em gramas (um número inteiro). Encomendas até 2000 gramas, inclusive, vão numa caixa pequena; acima de 2000 gramas, vão numa caixa grande. Um peso de zero gramas, ou negativo, é um erro de pesagem, e o algoritmo escreve "Peso inválido" em vez de escolher a caixa. Em todos os casos, no fim, o algoritmo escreve "Pesagem concluída".

```text
ALGORITMO EscolherCaixa
CONSTANTES
    PESO_MAXIMO_CAIXA_PEQUENA ← 2000
VARIÁVEIS
    peso: inteiro
INÍCIO
    ESCREVER "Peso da encomenda em gramas?"
    LER peso
    SE peso <= 0 ENTÃO
        ESCREVER "Peso inválido"
    SENÃO SE peso <= PESO_MAXIMO_CAIXA_PEQUENA ENTÃO
        ESCREVER "Caixa pequena"
    SENÃO
        ESCREVER "Caixa grande"
    FIM SE
    ESCREVER "Pesagem concluída"
FIM
```

Repara na linha `ESCREVER "Pesagem concluída"`: está alinhada com o `SE`, e não dentro de nenhum ramo. Executa-se depois de os ramos se juntarem, seja qual for o peso. É esta a diferença de estrutura em relação ao algoritmo da nota.

1. Guarda uma cópia com outro nome: na barra de menus, **Ficheiro** e **Guardar como...**, escreve o nome `fluxograma-caixa-de-envio.drawio` e escolhe **Aparelho** e a pasta `algoritmos`. O ficheiro da nota fica guardado como estava, e passas a trabalhar no ficheiro novo, que por enquanto tem o mesmo desenho. Se preferires começar num diagrama em branco, usa antes **Ficheiro** e **Novo...**, como na parte 8 do laboratório 02, e guarda-o logo com esse nome.
2. Desenha o fluxograma deste pseudocódigo. Se aproveitares o desenho da nota e mudares os textos, confirma figura a figura que o desenho corresponde a este pseudocódigo, e não ao da nota. Os três ramos juntam-se no paralelogramo de "Pesagem concluída", e só depois se desce para o Fim.
3. Copia esta tabela para a folha e segue com o dedo o caminho de cada peso, como na parte 4. Os pesos são o valor abaixo, o próprio limite e o valor acima de cada um dos dois limites do enunciado, o 0 e o 2000.

| Peso | Saída do primeiro losango | Saída do segundo losango | Mensagens a que chegaste | Coincide com o enunciado? |
| ---: | --- | --- | --- | --- |
| -1 | | | | |
| 0 | | | | |
| 1 | | | | |
| 1999 | | | | |
| 2000 | | | | |
| 2001 | | | | |

4. Guarda o ficheiro e exporta a imagem, com o nome `fluxograma-caixa-de-envio.png`.

Terminaste quando os seis pesos tiverem um caminho, cada caminho acabar na mensagem que o enunciado pede, e todos passarem por "Pesagem concluída" antes do Fim.

## Quando alguma coisa corre mal na aplicação

| O que acontece | O que fazer |
| --- | --- |
| Não encontras o losango | Desce até ao fim da lista do painel da esquerda e abre o grupo Fluxograma; a figura chama-se Decision. Também podes escrever `Decision` na caixa de pesquisa, no topo do painel |
| Quando mexes uma figura, a seta não vai atrás dela | A seta não ficou presa. Apaga-a e desenha-a outra vez, largando só quando a figura de destino ficar com o contorno azul |
| Não consegues escrever `Sim` na seta | Faz duplo clique exatamente em cima da linha da seta, e não ao lado |
| O texto não cabe no losango | Seleciona o losango e puxa um dos cantos para fora |
| Uma seta passa por cima de outra figura | Clica na seta e arrasta o ponto que aparece a meio da linha |
| Não aparece a barra de menus no topo | A janela do browser está estreita. Maximiza-a, ou usa o botão redondo com reticências, no canto superior direito |
| O ficheiro foi guardado no Google Drive | Volta a guardar com Guardar como... e, no campo Onde:, escolhe Aparelho ou Descarregar |
| Apagaste uma figura sem querer | Ctrl+Z (Cmd+Z no Mac) desfaz a última ação |

## O que entregar

Na tua pasta `algoritmos` tens de ter quatro ficheiros novos:

- `fluxograma-classificar-nota.drawio` e `fluxograma-classificar-nota.png`;
- `fluxograma-caixa-de-envio.drawio` e `fluxograma-caixa-de-envio.png`.

E em papel:

- A folha da parte 4, com as nove linhas preenchidas e as respostas às quatro perguntas.
- A folha da parte 5, com as seis linhas preenchidas.

Depois deste laboratório segue-se a [ficha de exercícios](03-decisoes-e-validacao-exercicios.md), onde vais voltar a usar a aplicação no exercício 5.

![Rodapé](../imagens/rodape.png)
