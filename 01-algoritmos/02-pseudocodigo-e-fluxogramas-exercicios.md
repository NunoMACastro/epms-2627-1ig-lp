![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Pseudocódigo e fluxogramas

UC: UC00245

Blocos: ALG02

Requisitos: UC00245-R02, UC00245-R03, UC00245-R04, UC00245-K03, UC00245-K04, UC00245-K05, UC00245-K06, UC00245-A05, UC00245-A06, UC00245-C01, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG02, acompanha o [guia](02-pseudocodigo-e-fluxogramas.md) e o [laboratório](02-pseudocodigo-e-fluxogramas-laboratorio.md) |
| Tempo total | 120 minutos dos 300 do bloco: 90 de prática autónoma e 30 de desafio opcional. A secção "Para ires mais longe" é opcional e fica fora destes 120 minutos |
| Entrega | Respostas escritas, tabelas de trace e o pseudocódigo do exercício 7; se fizeres a parte B do desafio, os ficheiros `.drawio` e `.png` do fluxograma |

## Objetivos e conceitos necessários

Vais praticar, sem ajuda, as peças que o bloco ensinou, uma de cada vez: escolher o tipo de dados de um valor, fazer o trace de uma sequência de atribuições, reconhecer uma atribuição mal escrita, calcular expressões e usar as funções predefinidas. Depois segues um algoritmo completo, que já está escrito, e no fim escreves um algoritmo teu.

Antes de começares, deves ter estudado o [guia](02-pseudocodigo-e-fluxogramas.md) deste bloco e feito o [laboratório](02-pseudocodigo-e-fluxogramas-laboratorio.md). Tudo o que precisas para esta ficha está no guia, e cada exercício diz em que secção está a matéria. Se encravares, volta a essa secção antes de olhares para o apoio.

Material: papel quadriculado e lápis. O diagrams.net, em `https://app.diagrams.net/?lang=pt`, só é preciso para a parte B do desafio. Guarda esse ficheiro na pasta `algoritmos` que usaste no laboratório, com um nome em minúsculas, com hífenes e sem acentos.

Todos os algoritmos desta ficha são sequenciais: as instruções executam-se sempre todas, pela mesma ordem, sem o algoritmo ter de escolher entre caminhos.

## Como está organizada a ficha

Resolve os exercícios pela ordem. Nos quatro primeiros aplicas o que o guia mostrou, uma peça de cada vez: os tipos, o trace, as atribuições e as expressões. Nos dois seguintes decides: no exercício 5, que função predefinida serve em cada situação; no exercício 6, segues um algoritmo inteiro e decides qual de duas versões de uma conta está certa. No último constróis um algoritmo teu, com as peças que os anteriores treinaram.

Nenhum exercício é o exemplo explicado do guia com outros números. O exemplo mostra o caminho, e os exercícios pedem-te que o percorras noutros problemas.

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Escolher o tipo de dados de um valor e justificar a escolha | 10 min |
| 2 | Fazer o trace de uma sequência de atribuições | 15 min |
| 3 | Reconhecer atribuições certas e erradas | 10 min |
| 4 | Calcular expressões pela ordem das operações | 10 min |
| 5 | Escolher e usar a função predefinida certa | 12 min |
| 6 | Seguir um algoritmo completo com uma tabela de trace | 12 min |
| 7 | Escrever um algoritmo em pseudocódigo e testá-lo | 21 min |
| Total da parte obrigatória | Exercícios 1 a 7 | 90 min |
| Desafio opcional | Trocar os valores de duas variáveis, desenhar na aplicação o fluxograma do exercício 7 e mudar uma regra | 30 min |
| Para ires mais longe | Opcional: casos que enganam nos tipos, nas atribuições e nas expressões, e um problema novo | fora dos 120 min |

## Exercício 1: Escolher o tipo de dados (10 min)

A matéria está na secção "Tipos de dados" do guia.

Diz que tipo de dados usarias para guardar cada um destes valores, `inteiro`, `real`, `texto` ou `lógico`, e justifica cada escolha numa frase que fale do que vais fazer com o valor. Por exemplo, para a temperatura de uma sala, como 21,5 graus: `real`, porque vou fazer contas com ela, como a média do dia, e a parte decimal conta.

**a)** O número de alunos inscritos numa visita de estudo.

**b)** O preço de uma resma de papel, em cêntimos.

**c)** O nome de um fornecedor.

**d)** Se um artigo está em promoção ou não.

Concluíste quando cada valor tiver um tipo e uma frase que diga porquê.

## Exercício 2: Fazer o trace de atribuições (15 min)

A matéria está nas secções "Atribuição: dar um valor não é perguntar se é igual" e "A tabela de trace" do guia.

Uma papelaria regista o stock de um artigo e as vendas do dia com esta sequência de quatro atribuições:

```text
stock ← 50
vendas ← 12
stock ← stock - vendas
vendas ← vendas + 8
```

**a)** Antes de fazeres o trace, escreve com que valor achas que `stock` fica no fim.

**b)** Faz o trace. A tabela tem uma coluna para o passo, uma para a instrução, uma para cada variável e uma para o ecrã, e começa no passo 0, antes de qualquer instrução. Como nenhuma instrução escreve no ecrã, essa coluna fica com "nada" em todas as linhas.

**c)** No passo 4, `vendas` passou a valer outro número. O valor de `stock` mudou nesse passo? Explica numa frase, a partir do que a atribuição faz.

**d)** Nesta segunda versão, as duas últimas instruções estão pela ordem contrária:

```text
stock ← 50
vendas ← 12
vendas ← vendas + 8
stock ← stock - vendas
```

Os passos 0, 1 e 2 do trace são iguais aos da alínea b), e podes copiá-los. Faz só os passos 3 e 4 e diz com que valor fica `stock`. Explica numa frase porque é que não é o mesmo valor da alínea b).

Concluíste quando os dois traces mostrarem o valor de todas as variáveis em cada linha e tiveres comparado o resultado com a tua previsão da alínea a).

## Exercício 3: Atribuições certas e erradas (10 min)

A matéria está no fim da secção "Atribuição: dar um valor não é perguntar se é igual" e na secção "Constantes" do guia.

Um algoritmo tem estas declarações:

```text
CONSTANTES
    LIMITE_DE_SENHAS ← 40
VARIÁVEIS
    caixas: inteiro
    total: inteiro
    preco: inteiro
    pago: lógico
```

Imagina que, antes de cada uma das linhas seguintes, `total` vale 1000 e `preco` vale 150. Cada linha vê-se sozinha, sem as outras. Para cada uma, escreve "certa" ou "errada". Se estiver certa, escreve o valor com que a variável da esquerda fica. Se estiver errada, explica numa frase porquê. Por exemplo, para a linha `preco ← 350`: certa, `preco` fica com 350.

| Linha | Instrução |
| ---: | --- |
| 1 | `caixas ← 5` |
| 2 | `5 ← caixas` |
| 3 | `total ← total + preco` |
| 4 | `LIMITE_DE_SENHAS ← 50` |
| 5 | `pago ← FALSO` |

Concluíste quando cada linha certa tiver o seu valor e cada linha errada tiver uma frase que diga o que está mal.

## Exercício 4: Calcular expressões (10 min)

A matéria está na secção "Expressões aritméticas" do guia.

Calcula o valor de cada expressão e escreve o tipo do resultado, `inteiro` ou `real`. Faz as contas à mão, pela ordem das operações. Num resultado real, escreve a parte decimal.

| N.º | Expressão | Valor | Tipo |
| ---: | --- | --- | --- |
| 1 | `3 + 4 * 5` | | |
| 2 | `(3 + 4) * 5` | | |
| 3 | `23 DIV 4` | | |
| 4 | `23 RESTO 4` | | |
| 5 | `23 / 4` | | |

Concluíste quando as cinco expressões tiverem valor e tipo, e tiveres confirmado as linhas 3 e 4 com a verificação do guia: o divisor vezes o resultado do `DIV`, mais o `RESTO`, tem de dar 23.

## Exercício 5: Usar as funções predefinidas (12 min)

A matéria está na secção "Funções predefinidas" do guia.

Em cada alínea escreves três coisas: a declaração da variável que recebe o resultado, com o tipo; a atribuição, com a função predefinida certa; e o valor com que a variável fica. Cada uma das quatro funções, `ABS`, `ARREDONDAR`, `TRUNCAR` e `RAIZ`, serve numa só alínea.

Exemplo do formato, com uma conta sem função: `totalAPagar: inteiro`; `totalAPagar ← quantidade * preco`; com `quantidade` a valer 3 e `preco` a valer 150, `totalAPagar` fica com 450.

**a)** A variável real `tempoEmHoras` vale `3.75`: é o tempo, em horas, que demorou a contagem do stock de um armazém. Guarda em `horasCompletas` o número de horas completas.

**b)** A variável real `mediaDeVendas` vale `14.6`: é a média de cadernos vendidos por dia numa semana. Guarda em `mediaArredondada` o número inteiro de cadernos mais próximo dessa média.

**c)** Numa loja com senhas, está a ser atendida a senha guardada em `senhaAtual`, e um cliente tem a senha guardada em `senhaCliente`. Guarda em `distancia` quantas senhas os separam, sem sinal, seja qual for a maior. Usa `senhaAtual` a valer 42 e `senhaCliente` a valer 57.

**d)** A variável `area` vale `225`: é a área, em metros quadrados, de um armazém com a forma de um quadrado. Guarda em `lado` o comprimento do lado do armazém, em metros.

Concluíste quando cada alínea tiver a declaração, a atribuição e o valor, e cada função tiver sido usada uma vez.

## Exercício 6: Seguir um algoritmo completo (12 min)

A matéria está nas secções "Ler e escrever" e "A tabela de trace" do guia. O passo 5 do exemplo explicado é o modelo do trace.

Lê este algoritmo com atenção:

```text
ALGORITMO EnvioDeEncomenda
CONSTANTES
    PESO_DA_CAIXA_VAZIA ← 200
VARIÁVEIS
    artigos: inteiro
    pesoPorArtigo: inteiro
    pesoTotal: inteiro
INÍCIO
    ESCREVER "Quantos artigos leva a encomenda?"
    LER artigos
    ESCREVER "Quanto pesa cada artigo, em gramas?"
    LER pesoPorArtigo
    pesoTotal ← artigos * pesoPorArtigo + PESO_DA_CAIXA_VAZIA
    ESCREVER "Peso total em gramas: ", pesoTotal
FIM
```

**a)** Faz o trace completo para uma encomenda de 3 artigos de 150 gramas cada, com uma coluna por variável e uma para o ecrã. Mostra todas as linhas, e não só o resultado.

**b)** Um colega escreveu a conta do peso assim:

```text
    pesoTotal ← artigos * (pesoPorArtigo + PESO_DA_CAIXA_VAZIA)
```

Calcula o resultado da versão dele para os mesmos 3 artigos de 150 gramas.

**c)** A encomenda vai toda numa só caixa. Qual das duas versões está certa, a do algoritmo ou a do colega? Explica numa frase.

Concluíste quando o teu trace mostrar o valor de todas as variáveis em cada linha e tiveres escolhido a versão certa com uma razão.

## Exercício 7: Escrever um algoritmo teu (21 min)

A matéria está na secção "A convenção de pseudocódigo desta disciplina" do guia, e o exemplo explicado dos cadernos tem a mesma forma que este problema.

A cantina da escola compra leite em grades de 24 pacotes. O fornecedor também vende pacotes soltos. Uma grade custa 1440 cêntimos e um pacote solto custa 70 cêntimos. Dado o número de pacotes de que a cantina precisa, queremos saber quantas grades completas compra, quantos pacotes soltos compra além dessas grades, e quanto vai pagar ao todo.

O contrato já está feito, para te concentrares no pseudocódigo:

| Pergunta | Resposta |
| --- | --- |
| Entradas | O número de pacotes de que a cantina precisa, um inteiro igual ou maior do que zero |
| Saídas | O número de grades completas, o número de pacotes soltos, entre 0 e 23, e o total a pagar em cêntimos, os três inteiros |
| Restrições | Uma grade tem sempre 24 pacotes e custa 1440 cêntimos; um pacote solto custa 70 cêntimos |
| Condições | Não há caminhos alternativos: os passos são sempre os mesmos |

**a)** Escreve o algoritmo em pseudocódigo, segundo a convenção do guia: o nome, as constantes, as variáveis com o tipo, e as instruções entre `INÍCIO` e `FIM`. Usa constantes para os três valores fixos. Antes do `LER`, escreve a pergunta.

**b)** Segue o teu algoritmo, instrução a instrução, e preenche esta tabela para 100 e para 24 pacotes:

| Pacotes necessários | Grades | Pacotes soltos | Total a pagar, em cêntimos |
| ---: | ---: | ---: | ---: |
| 100 | | | |
| 24 | | | |

**c)** Escolhe uma terceira entrada que teste uma situação diferente das duas anteriores. Acrescenta-a à tabela e explica numa frase o que ela testa.

Concluíste quando o teu pseudocódigo seguir a convenção, usar as três constantes, ler antes de calcular e escrever os três resultados no fim, e a tabela tiver as três entradas.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Para cada valor, faz a pergunta do guia: vou fazer contas com este valor? Se não, é quase sempre texto. Se sim, a parte decimal interessa? E se a resposta ao valor for só sim ou não, o tipo é outro.

**Exercício 2.** Faz o trace por linhas, e não por variáveis. Numa atribuição, calcula primeiro o lado direito com os valores da linha de cima, e só depois guarda o resultado na variável da esquerda. Para a alínea c), relê no guia a primeira consequência da atribuição: copia um valor, não cria uma ligação.

**Exercício 3.** Lê cada linha em voz alta, com a palavra "recebe" no lugar da seta. O que está à esquerda da seta pode receber um valor? Olha também para as declarações: nem todos os nomes estão na lista das variáveis.

**Exercício 4.** Faz primeiro os parênteses, depois as multiplicações e as divisões, incluindo `DIV` e `RESTO`, e só no fim as somas. Para o `DIV` e o `RESTO`, pensa em 23 lápis arrumados em caixas de 4: quantas caixas se enchem, e quantos lápis sobram? E lembra-te de que `/` dá sempre um real.

**Exercício 5.** Para cada alínea, pergunta-te o que queres fazer ao número: cortar as casas decimais, ir ao inteiro mais próximo, tirar o sinal, ou encontrar o lado de um quadrado a partir da área. Cada uma destas quatro coisas é uma das funções. Para o tipo, relê a coluna "Tipo do resultado" da tabela das funções, no guia.

**Exercício 6.** Tem o passo 5 do exemplo explicado aberto ao lado: o trace faz-se da mesma maneira. Na alínea b), faz primeiro a conta que está dentro dos parênteses. Na alínea c), compara as duas contas e pergunta-te quantas vezes cada versão soma o peso da caixa.

**Exercício 7.** Começa pelo pseudocódigo dos cadernos do guia: aqui também há uma quantidade, uma divisão inteira e um resto. A diferença é que no fim há um preço a calcular. Escreve primeiro só as grades e os soltos, e acrescenta o total depois de isso funcionar. Na alínea c), relê os três casos de teste do passo 1 do exemplo: o que é que 100 e 24 já testam, e o que falta testar?

**Desafio, parte A.** Relê a troca que falha, na secção da atribuição do guia, e pensa em dois copos cheios, um de sumo e outro de água: para trocar os líquidos de copo precisas de um terceiro copo.

## Desafio opcional (30 min)

O desafio tem três partes independentes, e podes fazê-las pela ordem que quiseres. As partes B e C partem do teu algoritmo do exercício 7.

### Parte A: trocar os valores de duas variáveis (10 min)

A matéria está na secção "Atribuição: dar um valor não é perguntar se é igual" do guia, onde há uma troca que falha.

Duas variáveis inteiras começam assim:

```text
caixaA ← 12
caixaB ← 30
```

Escreve as instruções que trocam os valores das duas, de forma que no fim `caixaA` valha 30 e `caixaB` valha 12. Podes usar uma variável a mais, se precisares, e tens de a declarar com o tipo certo. Faz o trace da tua solução, desde as duas linhas acima, para mostrar que funciona.

### Parte B: o fluxograma do exercício 7 na aplicação (15 min)

A matéria está na secção "Os símbolos do fluxograma" do guia e no laboratório.

Desenha no diagrams.net o fluxograma do teu algoritmo do exercício 7. Guarda-o como `fluxograma-compra-de-leite.drawio`, verifica-o com a lista da parte 6 do laboratório, adaptada a este algoritmo, e exporta a imagem com o nome `fluxograma-compra-de-leite.png`.

### Parte C: o fornecedor muda as grades (5 min)

O fornecedor passa a vender grades de 12 pacotes em vez de 24, e a grade passa a custar 780 cêntimos. O pacote solto continua a custar 70 cêntimos.

**a)** Quantas linhas do teu pseudocódigo precisam de mudar? E se, em vez de constantes, tivesses escrito os números 24 e 1440 diretamente nas contas, quantos sítios terias de procurar e mudar?

**b)** Se fizeste a parte B, o fluxograma precisa de ser redesenhado, ou basta mudar o texto de algumas figuras? Justifica.

**c)** Refaz a tabela de resultados para 100 pacotes com os valores novos.

É esta a razão por que se dá nome aos valores fixos: uma mudança de fornecedor não devia obrigar a reler o algoritmo todo à procura de números soltos.

## Para ires mais longe

Esta secção é opcional e fica fora dos 120 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e o desafio e quer mais prática, ou para estudar em casa. Os primeiros itens tratam casos que costumam enganar, um ou dois de cada vez, e é por isso que não entraram na parte obrigatória. O último é um problema novo. Os tempos são indicativos.

### Mais longe 1: Três valores com o tipo menos óbvio (10 min)

Continua o exercício 1. A matéria está na secção "Tipos de dados" do guia, sobretudo no parágrafo sobre o número de telefone.

Diz o tipo de cada valor e justifica a escolha numa frase:

**a)** O peso de uma encomenda, em quilogramas, como 2,35.

**b)** O código postal de uma loja, como 4000-123.

**c)** O código de barras de um artigo, com 13 algarismos.

### Mais longe 2: Um número entre aspas (5 min)

Continua o exercício 3. A matéria está no parágrafo do guia sobre o número `12` e o texto `"12"`.

A variável `quantidade` está declarada como `inteiro`. Das duas linhas seguintes, uma está certa e a outra está errada. Diz qual é qual e explica a diferença numa frase.

```text
quantidade ← 12
quantidade ← "12"
```

### Mais longe 3: Expressões que enganam (15 min)

Continua os exercícios 4 e 5. A matéria está nas secções "Expressões aritméticas" e "Funções predefinidas" do guia, nos parágrafos sobre os casos que enganam.

As expressões vêm aos pares, e cada par esconde um engano diferente. Calcula o valor e o tipo de cada uma e, para cada par, diz numa frase qual é o engano.

| Par | Expressão | Valor | Tipo |
| ---: | --- | --- | --- |
| 1 | `30 - 10 - 5` | | |
| 1 | `40 / 8 / 2` | | |
| 2 | `4 DIV 23` | | |
| 2 | `4 RESTO 23` | | |
| 3 | `ARREDONDAR(4.5)` | | |
| 3 | `ARREDONDAR(4.49)` | | |
| 4 | `TRUNCAR(-8.99)` | | |
| 4 | `ARREDONDAR(-8.99)` | | |
| 5 | `RAIZ(36 + 64)` | | |
| 5 | `RAIZ(36) + RAIZ(64)` | | |

### Mais longe 4: A encomenda sem artigos (10 min)

Continua o exercício 6.

**a)** Qual é o resultado do algoritmo `EnvioDeEncomenda` para 0 artigos de 150 gramas? O algoritmo está errado, ou está certo e apenas a responder a uma pergunta que ninguém queria fazer?

**b)** `pesoTotal` é um peso, e mesmo assim está declarado como inteiro. Porque é que, neste algoritmo, isso não é um problema?

### Mais longe 5: Quando os soltos saem mais caros (10 min)

Continua o exercício 7 e a parte C do desafio.

Com as grades de 24 pacotes a 1440 cêntimos, há casos em que a cantina paga pelos pacotes soltos mais do que pagaria por uma grade inteira, que ainda traz mais pacotes. Encontra um desses casos e mostra as contas. Com as grades de 12 pacotes a 780 cêntimos, isso ainda pode acontecer? Justifica com contas.

### Mais longe 6: Os autocarros da visita de estudo (30 min)

Um problema novo, para escreveres de raiz. A matéria é a mesma do exercício 7.

Uma visita de estudo é feita em autocarros, todos com a mesma capacidade. Dado o número de alunos que vão à visita e a capacidade de cada autocarro, queremos saber quantos autocarros ficam completamente cheios, quantos alunos vão no autocarro que sobra e quantos lugares livres ficam nesse autocarro.

**a)** Escreve o pseudocódigo completo. Decide se a capacidade é uma constante ou um dado que se lê, e justifica a decisão numa frase.

**b)** Escolhe três entradas que testem situações diferentes, explica numa frase porque escolheste cada uma, e faz a tabela de resultados.

**c)** Há pelo menos uma situação em que a fórmula dos lugares livres dá um resultado estranho. Descobre qual é e explica porque acontece. Não precisas de a resolver, porque as ferramentas para isso são do guia 03: descobri-la é que conta. Se não a encontrares, experimenta um número de alunos que encha exatamente dois autocarros.

## Critérios de conclusão

- [ ] Escolhi o tipo de cada valor pelo que vou fazer com ele, e justifiquei.
- [ ] Nos traces, copiei em cada linha os valores da linha de cima e mudei só o que a instrução muda.
- [ ] Reconheci as atribuições erradas e expliquei o que está mal em cada uma.
- [ ] Calculei as expressões pela ordem das operações e escrevi o tipo de cada resultado.
- [ ] Usei cada função predefinida com o argumento entre parênteses e declarei a variável com o tipo que a função devolve.
- [ ] No meu algoritmo, declarei todas as variáveis com um tipo coerente e usei constantes para os valores fixos.
- [ ] O meu algoritmo lê os dados, faz as contas e escreve os resultados, por esta ordem.
- [ ] Testei o meu algoritmo com três entradas que testam coisas diferentes.
- [ ] Se fiz a parte B do desafio, o fluxograma e o pseudocódigo dizem a mesma coisa, e guardei o `.drawio` e o `.png`.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
