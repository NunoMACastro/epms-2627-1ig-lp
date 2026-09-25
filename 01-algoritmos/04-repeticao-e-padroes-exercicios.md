![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Repetição e padrões

UC: UC00245

Blocos: ALG04

Requisitos: UC00245-R03, UC00245-R04, UC00245-R05, UC00245-K05, UC00245-K06, UC00245-A05, UC00245-A06, UC00245-A07, UC00245-C01, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG04, acompanha o [guia](04-repeticao-e-padroes.md) e o [laboratório](04-repeticao-e-padroes-laboratorio.md) |
| Tempo total | 120 minutos dos 300 do bloco: 90 de prática autónoma, nos exercícios 1 a 7, e 30 de desafio |
| Entrega | Pseudocódigo e tabelas de iterações dos exercícios 1 a 7; o que fizeres da secção "Para ires mais longe" e do desafio |

## Objetivos e conceitos necessários

Vais praticar sem ajuda o que o guia explicou sobre ciclos: seguir um ciclo numa tabela de iterações, reconhecer as três peças de um ciclo e escrever ciclos com os quatro padrões, o contador, o totalizador, a sentinela e a validação repetida.

A ficha vai por passos, e cada exercício usa o que os anteriores treinaram. Primeiro aplicas o que o guia mostrou: nos exercícios 1 e 2 segues e completas ciclos que já estão quase escritos, e nos exercícios 3 e 4 escreves ciclos pequenos, um com um contador e outro com um totalizador, a partir de um algoritmo do guia. Depois decides: no exercício 5 descobres porque é que um ciclo conta mal e corriges a linha errada. No fim constróis os ciclos que dependem do que a pessoa escreve: no exercício 6, um ciclo com sentinela, e no exercício 7, uma validação repetida.

Antes de começares, deves ter lido o [guia](04-repeticao-e-padroes.md) até ao fim. Cada exercício diz a secção do guia onde está a matéria de que precisas. Tem o guia aberto ao lado e segue os algoritmos de lá sempre que o enunciado o sugerir. Para quem está a escrever os primeiros ciclos, partir de um algoritmo que já funciona é a forma certa de começar. No exercício 7 vais usar também o contrário de um intervalo, escrito com `OU`, que aprendeste no guia 03.

Material: papel quadriculado e lápis.

Uma regra para todos os exercícios: quando te pedirem uma tabela de iterações, escreve primeiro o resultado que esperas, e só depois faz a tabela. Se só o escreveres depois, a tabela concorda sempre contigo e não te ensina nada.

Os exercícios 1 a 7 são obrigatórios e cabem nos 90 minutos da prática autónoma. No fim da ficha há o desafio e uma secção "Para ires mais longe", ambos opcionais, para quem terminar.

## Exercício 1: Seguir um ciclo já escrito (10 min)

Um armazém tem 20 caixas de papel. Em cada um dos próximos 3 dias chega uma entrega de 15 caixas, e não sai nenhuma. Este algoritmo mostra o stock no fim de cada dia:

```text
ALGORITMO StockDePapel
CONSTANTES
    STOCK_INICIAL ← 20
    CAIXAS_POR_ENTREGA ← 15
    NUMERO_DE_DIAS ← 3
VARIÁVEIS
    dia: inteiro
    stock: inteiro
INÍCIO
    stock ← STOCK_INICIAL
    dia ← 1
    ENQUANTO dia <= NUMERO_DE_DIAS FAZER
        stock ← stock + CAIXAS_POR_ENTREGA
        ESCREVER "Fim do dia ", dia, ": ", stock, " caixas"
        dia ← dia + 1
    FIM ENQUANTO
    ESCREVER "Stock final: ", stock, " caixas"
FIM
```

A tabela de iterações já tem a primeira linha, para veres o formato:

| Teste | dia | stock | Condição | Durante a iteração |
| --- | ---: | ---: | --- | --- |
| 1.º | 1 | 20 | `1 <= 3` é VERDADEIRO | escreve "Fim do dia 1: 35 caixas" |

**a)** Copia a tabela e completa-a, com uma linha por cada teste da condição, até ao teste que dá falso. Cada linha mostra os valores no momento em que o algoritmo chega ao `ENQUANTO` (guia, [A tabela de iterações](04-repeticao-e-padroes.md#a-tabela-de-iterações)).

**b)** Quantas iterações teve o ciclo? Quantas vezes foi testada a condição?

**c)** Que valores têm `dia` e `stock` depois do ciclo? O que escreve a última instrução do algoritmo?

**d)** Explica numa frase porque é que `dia` acaba com o valor 4, e não com 3.

Concluíste quando a última linha da tua tabela tiver a condição falsa e souberes dizer porque é que há mais um teste do que iterações.

## Exercício 2: Completar a peça que falta (11 min)

Cada um destes três ciclos tem uma linha em branco, marcada com pontos. Para cada um, escreve a linha que falta e diz qual das três peças ela é: a inicialização, a condição ou a atualização (guia, [As três peças de um ciclo](04-repeticao-e-padroes.md#as-três-peças-de-um-ciclo)).

**a)** Escrever as etiquetas das caixas de uma encomenda, da caixa 1 à caixa 4, com a constante `NUMERO_DE_CAIXAS ← 4`:

```text
    ..........
    ENQUANTO caixa <= NUMERO_DE_CAIXAS FAZER
        ESCREVER "Etiqueta da caixa ", caixa
        caixa ← caixa + 1
    FIM ENQUANTO
```

**b)** Escrever a lista das prateleiras a contar no inventário, da prateleira 1 à 5, com a constante `ULTIMA_PRATELEIRA ← 5`:

```text
    prateleira ← 1
    ENQUANTO .......... FAZER
        ESCREVER "Contar a prateleira ", prateleira
        prateleira ← prateleira + 1
    FIM ENQUANTO
```

**c)** Imprimir os talões numerados de 101 a 103, com as constantes `PRIMEIRO_TALAO ← 101` e `ULTIMO_TALAO ← 103`:

```text
    talao ← PRIMEIRO_TALAO
    ENQUANTO talao <= ULTIMO_TALAO FAZER
        ESCREVER "Talão ", talao
        ..........
    FIM ENQUANTO
```

**d)** Imagina que a linha da alínea c) ficava mesmo em branco. Faz as três primeiras linhas da tabela de iterações dessa versão e explica numa frase porque é que o ciclo nunca acabaria (guia, [O ciclo que nunca acaba](04-repeticao-e-padroes.md#o-ciclo-que-nunca-acaba)).

Concluíste quando cada ciclo, com a tua linha, escrever exatamente os números que o enunciado pede, nem mais um nem menos um.

## Exercício 3: Escrever um ciclo com um contador (17 min)

Uma papelaria recebeu hoje 3 encomendas pela internet. Para cada encomenda, o funcionário escreve o número de artigos. Uma encomenda com mais de 5 artigos vai numa caixa grande. O algoritmo conta quantas caixas grandes são precisas. Já tens o princípio do algoritmo:

```text
ALGORITMO ContarCaixasGrandes
CONSTANTES
    NUMERO_DE_ENCOMENDAS ← 3
    LIMITE_CAIXA_PEQUENA ← 5
VARIÁVEIS
    encomenda: inteiro
    artigos: inteiro
    caixasGrandes: inteiro
INÍCIO
    (as tuas instruções)
FIM
```

**a)** Escreve as instruções que faltam entre `INÍCIO` e `FIM`. Usa um `PARA`, porque se sabe que são 3 encomendas, e segue o algoritmo `ContarStockBaixo` do guia ([Padrão contador](04-repeticao-e-padroes.md#padrão-contador)).

**b)** Escreve quantas caixas grandes esperas para encomendas de 4, 9 e 7 artigos. Depois faz a tabela de iterações, com colunas para `encomenda`, `artigos` e `caixasGrandes`, e confirma o resultado.

**c)** Explica numa frase porque é que a linha que aumenta `caixasGrandes` fica dentro do `SE`.

Concluíste quando a tua tabela confirmar o resultado que esperavas e o contador começar em 0, antes do `PARA`.

## Exercício 4: Escrever um ciclo com um totalizador (15 min)

Numa gráfica houve, durante a manhã, 3 trabalhos de impressão. Para cada trabalho, o funcionário escreve o número de páginas impressas. O algoritmo mostra o total de páginas da manhã. Já tens o princípio do algoritmo:

```text
ALGORITMO PaginasDaManha
CONSTANTES
    NUMERO_DE_TRABALHOS ← 3
VARIÁVEIS
    trabalho: inteiro
    paginas: inteiro
    totalPaginas: inteiro
INÍCIO
    (as tuas instruções)
FIM
```

**a)** Escreve as instruções que faltam, com um `PARA` e um totalizador. Segue o algoritmo `TotalDeVendas` do guia ([Padrão totalizador](04-repeticao-e-padroes.md#padrão-totalizador)), mas repara que aqui o número de trabalhos já está numa constante.

**b)** Escreve o total que esperas para trabalhos de 12, 40 e 8 páginas. Depois faz a tabela de iterações, com colunas para `trabalho`, `paginas` e `totalPaginas`, e confirma o resultado.

**c)** Explica numa frase o que acontecia ao resultado se a linha que põe `totalPaginas` a 0 passasse para dentro do `PARA`, logo a seguir ao cabeçalho.

Concluíste quando a tua tabela confirmar o total que esperavas e souberes dizer a diferença entre o contador do exercício 3 e o totalizador deste.

## Exercício 5: Descobrir porque é que um contador conta mal (10 min)

Uma loja tem 4 encomendas por expedir. Uma encomenda é urgente se o prazo de entrega for de 2 dias ou menos. Um colega escreveu este algoritmo para contar as encomendas urgentes, mas o resultado não bate certo:

```text
ALGORITMO EncomendasUrgentes
CONSTANTES
    NUMERO_DE_ENCOMENDAS ← 4
    PRAZO_URGENTE ← 2
VARIÁVEIS
    encomenda: inteiro
    prazo: inteiro
    urgentes: inteiro
INÍCIO
    urgentes ← 0
    PARA encomenda ← 1 ATÉ NUMERO_DE_ENCOMENDAS FAZER
        ESCREVER "Prazo de entrega da encomenda ", encomenda, ", em dias?"
        LER prazo
        SE prazo <= PRAZO_URGENTE ENTÃO
            urgentes ← urgentes + prazo
        FIM SE
    FIM PARA
    ESCREVER "Encomendas urgentes: ", urgentes
FIM
```

**a)** Faz a tabela de iterações com os prazos 3, 1, 2 e 5, com colunas para `encomenda`, `prazo` e `urgentes`. O que aparece no ecrã no fim?

**b)** Conta à mão, olhando só para os quatro prazos, quantas encomendas são urgentes. O resultado do algoritmo coincide?

**c)** Qual é a linha errada? Responde numa frase: essa linha segue o padrão contador ou o padrão totalizador, e qual dos dois devia seguir? A diferença entre os dois está explicada no guia, no [Padrão totalizador](04-repeticao-e-padroes.md#padrão-totalizador).

**d)** Escreve a linha corrigida e diz o que o ecrã passa a mostrar com os mesmos prazos.

Concluíste quando a tua versão corrigida der, com os mesmos prazos, o número que contaste à mão.

## Exercício 6: Escrever um ciclo com sentinela (17 min)

À tarde, na mesma gráfica do exercício 4, ninguém sabe quantos trabalhos vão chegar. O funcionário escreve o número de páginas de cada trabalho à medida que o trabalho fica pronto, e escreve 0 quando a gráfica fecha. Nenhum trabalho tem 0 páginas, e por isso o 0 serve de sentinela. O algoritmo mostra o total de páginas da tarde. Já tens o princípio do algoritmo:

```text
ALGORITMO PaginasDaTarde
CONSTANTES
    SENTINELA ← 0
VARIÁVEIS
    paginas: inteiro
    totalPaginas: inteiro
INÍCIO
    (as tuas instruções)
FIM
```

**a)** No exercício 4 usaste um `PARA`. Explica numa frase porque é que aqui não serve, com a pergunta que o guia ensina para escolher entre os dois ciclos (guia, [Escolher entre ENQUANTO e PARA](04-repeticao-e-padroes.md#escolher-entre-enquanto-e-para)).

**b)** Escreve as instruções que faltam, com a leitura antecipada antes do ciclo e a leitura do valor seguinte no fim do corpo. Segue o algoritmo `SomarCaixas` do guia ([Padrão sentinela](04-repeticao-e-padroes.md#padrão-sentinela)), sem o contador de caixas, porque aqui só se pede o total.

**c)** Escreve o total que esperas e faz a tabela de iterações em dois casos: quando o funcionário escreve 40, 8 e 0; e quando escreve logo 0, porque à tarde não houve trabalhos.

Concluíste quando os dois casos derem o total que esperavas e o 0 nunca tiver sido somado como se fosse um trabalho.

## Exercício 7: Escrever uma validação repetida (10 min)

Uma loja de informática organiza workshops gratuitos. Cada inscrição pode reservar de 1 a 6 lugares. O algoritmo pede o número de lugares e, enquanto o valor não for válido, escreve uma mensagem com o intervalo aceite e pede outra vez. No fim, escreve quantos lugares ficaram reservados. Já tens o princípio do algoritmo:

```text
ALGORITMO ReservarLugares
CONSTANTES
    MINIMO_DE_LUGARES ← 1
    MAXIMO_DE_LUGARES ← 6
VARIÁVEIS
    lugares: inteiro
INÍCIO
    (as tuas instruções)
FIM
```

**a)** Escreve as instruções que faltam. Segue o algoritmo `PedirQuantidadeValida` do guia ([Padrão validação repetida](04-repeticao-e-padroes.md#padrão-validação-repetida)): a condição do ciclo descreve o valor inválido.

**b)** Faz a tabela de iterações quando a pessoa escreve 0, depois 7 e depois 3.

**c)** A pessoa escreve logo 6. Responde numa frase: quantas iterações tem o ciclo, e o que aparece no ecrã?

Concluíste quando o 0 e o 7 forem recusados, o 3 e o 6 forem aceites, e souberes dizer o que se sabe sobre `lugares` depois do `FIM ENQUANTO`.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Na linha do 2.º teste, `dia` já vale 2 e `stock` já tem somada a primeira entrega: o que muda durante uma iteração só aparece na linha seguinte. Se te baralhares, faz primeiro o trace linha a linha da primeira iteração, como no guia, e compara-o com a linha da tabela que já está feita.

**Exercício 2.** Para cada ciclo, faz as três perguntas das peças: com que valor começa? Em que situação continua? O que muda em cada iteração? A pergunta a que o fragmento não responde é a da peça que falta. Na alínea d), olha para a coluna `talao` nas três linhas: o valor muda?

**Exercício 3.** Copia o `ContarStockBaixo` e muda uma coisa de cada vez: primeiro os nomes das constantes e das variáveis, depois a pergunta do `ESCREVER`, e por fim a condição do `SE`. "Mais de 5 artigos" quer dizer que uma encomenda com 5 artigos exatos ainda vai numa caixa pequena.

**Exercício 4.** O `TotalDeVendas` começa por ler o número de dias. Aqui não precisas dessa leitura, porque o número de trabalhos está na constante: o `PARA` vai de 1 até `NUMERO_DE_TRABALHOS`. O resto tem a mesma forma. Para a alínea c), relê no guia o segundo erro clássico dos totalizadores.

**Exercício 5.** Na tabela, olha para `urgentes` antes e depois de cada iteração em que o `SE` é verdadeiro. Quanto aumentou de cada vez? E quanto devia aumentar, se o que se quer é contar?

**Exercício 6.** Na alínea a), pergunta-te: quando o algoritmo chega ao ciclo, já se sabe quantos trabalhos vão chegar? Na alínea b), copia o `SomarCaixas` e apaga tudo o que tem a ver com `caixas`, que é o contador; depois muda os nomes. Confirma que tens dois `LER paginas`, um antes do `ENQUANTO` e outro mesmo antes do `FIM ENQUANTO`.

**Exercício 7.** A condição do ciclo é a do valor inválido: abaixo do mínimo ou acima do máximo. Escreve-a primeiro à parte e experimenta-a com 0, 1, 6 e 7 antes de a pores no ciclo. Na alínea c), avalia a condição com 6 antes de fazeres mais nada.

**Para ires mais longe.** No Mais longe 1, escreve só a coluna `prateleira`, lado a lado: que tipo de números são todos, e que tipo de número é o 8? No Mais longe 2, para cada prazo urgente, compara o que soma a linha do colega com o que somaria a linha certa. No Mais longe 3, lembra-te de que a sentinela não pode ser um valor que os dados verdadeiros possam ter: que números nunca podem ser um número de devoluções? No Mais longe 4, repara que cada iteração do ciclo só acontece porque o valor lido foi inválido.

## Desafio opcional (30 min)

Volta ao exercício 7 e muda uma só restrição: a pessoa passa a ter no máximo 3 tentativas, contando com a primeira. Se o valor continuar inválido ao fim da terceira tentativa, o algoritmo não pede mais nenhum valor e escreve "Reserva cancelada: foram usadas as 3 tentativas." Se o valor for válido numa das três tentativas, o algoritmo escreve a reserva feita, com o número de lugares. Se fizeste o D de "Para ires mais longe", já tens metade do caminho.

**a)** O ciclo pode agora terminar por duas razões diferentes. Diz quais são e escreve a condição do ciclo. Como a condição mistura `E` com `OU`, usa parênteses para mostrar o que se avalia primeiro, como no guia 03.

**b)** Depois do `FIM ENQUANTO`, o algoritmo tem de saber por qual das duas razões o ciclo terminou, para escrever a mensagem certa. Como é que sabe? Escreve essa parte do algoritmo. Atenção: há uma forma de decidir que parece certa e falha num dos casos de teste da alínea c).

**c)** Monta a tabela de casos esperados, com pelo menos quatro casos: um valor válido à primeira; um valor válido à terceira tentativa; três valores inválidos; e um extremo do intervalo. No caso dos três valores inválidos, confirma com a tabela de iterações que o `LER` é executado exatamente 3 vezes, nem mais uma.

**d)** Desenha o fluxograma, no papel ou no diagrams.net.

Concluíste quando o teu algoritmo passar os quatro casos, incluindo o do valor válido à terceira tentativa.

## Para ires mais longe

Estes exercícios são opcionais e não contam para os 90 minutos. Cada um junta uma dificuldade que os exercícios obrigatórios deixaram de fora de propósito. Faz primeiro os exercícios 1 a 7, e escolhe depois os que quiseres, pela ordem que quiseres.

### Mais longe 1: Um ciclo que salta por cima da saída (15 min)

Num armazém, as prateleiras estão numeradas de 1 a 8, e as de número ímpar ficam no corredor da esquerda. Este algoritmo devia escrever, por ordem, os números das prateleiras do corredor da esquerda:

```text
ALGORITMO PrateleirasDaEsquerda
CONSTANTES
    ULTIMA_PRATELEIRA ← 8
VARIÁVEIS
    prateleira: inteiro
INÍCIO
    prateleira ← 1
    ENQUANTO prateleira != ULTIMA_PRATELEIRA FAZER
        ESCREVER "Prateleira ", prateleira
        prateleira ← prateleira + 2
    FIM ENQUANTO
FIM
```

**a)** Faz a tabela de iterações até ao 6.º teste.

**b)** O ciclo termina? Olhando para os valores que `prateleira` vai tomando, explica porque é que a condição nunca chega a ser falsa (guia, o último caso de [O ciclo que nunca acaba](04-repeticao-e-padroes.md#o-ciclo-que-nunca-acaba)).

**c)** Corrige o algoritmo mudando uma só linha. Diz quantas iterações tem a versão corrigida e com que valor fica `prateleira` depois do ciclo.

**d)** O armazém passa a ter 9 prateleiras, e muda-se a constante para 9. A tua correção escreve todas as prateleiras do corredor da esquerda, incluindo a 9? Se não escrever, encontra outra correção que funcione com 8 e com 9.

### Mais longe 2: Os dados que escondem o erro (7 min)

Volta ao algoritmo do colega, no exercício 5, sem a correção.

**a)** Escreve quatro prazos com os quais esse algoritmo dá o resultado certo.

**b)** Explica numa frase porque é que um colega que só o testasse com esses prazos ficaria convencido de que o algoritmo estava bom.

**c)** Que prazos escolherias para teres a certeza de que o teste apanha o erro? Responde numa frase.

### Mais longe 3: Quando o 0 é um dado verdadeiro (25 min)

Uma loja regista quantos artigos lhe foram devolvidos em cada dia. O funcionário escreve o número de devoluções de cada dia, um dia de cada vez, e não se sabe à partida quantos dias vai registar. Um dia sem devoluções é um dia verdadeiro e tem de entrar nas contas. No fim, o algoritmo mostra quantos dias foram registados, o total de devoluções e a média de devoluções por dia. O princípio do algoritmo, com o valor da sentinela por escolher:

```text
ALGORITMO DevolucoesPorDia
CONSTANTES
    SENTINELA ← ..........
VARIÁVEIS
    devolucoes: inteiro
    diasRegistados: inteiro
    totalDevolucoes: inteiro
    media: real
INÍCIO
    (as tuas instruções)
FIM
```

**a)** Explica porque é que, neste problema, o 0 não pode ser a sentinela. Escolhe outro valor para a sentinela e justifica a escolha numa frase.

**b)** Escreve as instruções que faltam. A média pode ter parte decimal, e por isso calcula-se com `/`.

**c)** O que deve o algoritmo mostrar se o funcionário escrever logo a sentinela? Explica numa frase porque é que, nesse caso, não se pode calcular a média, e corrige o teu algoritmo se for preciso.

**d)** Faz a tabela de iterações quando o funcionário escreve 3, 0, 5, 2 e a sentinela. Escreve antes o resultado que esperas.

### Mais longe 4: Contar as tentativas inválidas (10 min)

Volta ao teu algoritmo do exercício 7.

**a)** Acrescenta um contador das tentativas inválidas, e escreve o seu valor no fim, depois dos lugares reservados. Diz onde fica o aumento do contador, antes, dentro ou depois do ciclo, e com que valor o contador começa.

**b)** Refaz a tabela de iterações com 0, 7 e 3, agora com uma coluna para o contador.

**c)** Qual é o menor número de vezes que o `LER` pode ser executado neste algoritmo? E o maior? Responde numa frase.

## Critérios de conclusão

- [ ] Em cada ciclo que escrevi, sei dizer com que valor começa, em que situação continua e o que muda em cada iteração.
- [ ] As minhas tabelas de iterações têm uma linha por cada teste da condição, com os valores no momento do teste, e a última linha é a do teste que dá falso.
- [ ] Os contadores e os totalizadores começam em 0 e são inicializados antes do ciclo.
- [ ] Sei dizer quando um problema pede um contador (quantos?) e quando pede um totalizador (quanto?).
- [ ] No ciclo com sentinela, a sentinela nunca é somada como se fosse um dado.
- [ ] Escrevi o resultado esperado antes de fazer cada tabela de iterações.
- [ ] Testei o caso de zero voltas no exercício 6 e o valor válido à primeira no exercício 7.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
