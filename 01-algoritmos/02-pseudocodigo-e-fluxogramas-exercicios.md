![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Pseudocódigo e fluxogramas

Ficha do tema Pseudocódigo e fluxogramas, do módulo Desenvolver algoritmos. Praticas as peças do tema uma de cada vez, até escreveres e testares um algoritmo teu. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](02-pseudocodigo-e-fluxogramas.md). Antes de começares, deves ter lido as secções da matéria e o exemplo guiado. Cada exercício diz em que secção do guia está a matéria. Se encravares, volta a essa secção antes de olhares para o apoio. O [laboratório](02-pseudocodigo-e-fluxogramas-laboratorio.md) é de fluxogramas e é opcional, e nenhum exercício obrigatório desta ficha precisa dele. Só a parte B do desafio, que também é de fluxogramas, usa o que lá se aprende.

## Como trabalhar

Resolve os exercícios pela ordem. Nos quatro primeiros aplicas o que o guia mostrou, uma peça de cada vez: os tipos, o trace, as atribuições e as expressões. Nos dois seguintes decides. No exercício 5 decides que função predefinida serve em cada situação. No exercício 6 segues um algoritmo inteiro e decides qual de duas versões de uma conta está certa. No último constróis um algoritmo teu, com as peças que os anteriores treinaram.

Nenhum exercício é o exemplo guiado do guia com outros números. O exemplo mostra o caminho, e os exercícios pedem-te que o percorras noutros problemas.

Todos os algoritmos desta ficha são sequenciais: as instruções executam-se sempre todas, pela mesma ordem, sem o algoritmo ter de escolher entre caminhos. Quando um exercício te pedir para escrever instruções ou um algoritmo, podes escrevê-los em pseudocódigo, na forma das aulas, ou em frases claras. O que conta é a lógica, e que as frases não deixem dúvidas: quanto, quando e o que acontece se não der. A secção "Frases claras também valem" do guia mostra a diferença entre frases que deixam dúvidas e frases que não deixam.

| Exercício | O que treina | Parte |
| --- | --- | --- |
| 1 | Escolher o tipo de dados de um valor e justificar a escolha | Obrigatória |
| 2 | Fazer o trace de uma sequência de atribuições | Obrigatória |
| 3 | Reconhecer atribuições certas e erradas | Obrigatória |
| 4 | Calcular expressões pela ordem das operações | Obrigatória |
| 5 | Escolher e usar a função predefinida certa | Obrigatória |
| 6 | Seguir um algoritmo completo com uma tabela de trace | Obrigatória |
| 7 | Escrever um algoritmo, em pseudocódigo ou em frases claras, e testá-lo | Obrigatória |
| Desafio | Trocar os valores de duas variáveis e mudar uma regra; a parte B, o fluxograma do exercício 7 na aplicação, só quando o professor o indicar | Opcional |
| Para ires mais longe | Casos que enganam nos tipos, nas atribuições e nas expressões, e um problema novo | Opcional |

Precisas de papel quadriculado e lápis. O diagrams.net, em `https://app.diagrams.net/?lang=pt`, só é preciso para a parte B do desafio. Essa parte é de fluxogramas, e só se faz quando o professor o indicar. Nesse caso, guarda o ficheiro na pasta `algoritmos` do laboratório, com um nome em minúsculas, com hífenes e sem acentos.

O que entregas:

- as respostas escritas e as tabelas de trace dos exercícios 1 a 6;
- o algoritmo do exercício 7, com a tabela das três entradas;
- se o professor indicar a parte B do desafio e a fizeres, os ficheiros `.drawio` e `.png` do fluxograma.

## Exercício 1: Escolher o tipo de dados

A matéria está na secção "Tipos de dados" do guia.

Diz que tipo de dados usarias para guardar cada um destes valores, `int`, `float`, `string` ou `bool`. Justifica cada escolha numa frase que fale do que vais fazer com o valor. Um exemplo é a temperatura de uma sala, como 21,5 graus. A justificação pode ser esta: "`float`, porque vou fazer contas com ela, como a média do dia, e a parte decimal conta".

**a)** O número de alunos inscritos numa visita de estudo.

**b)** O preço de uma resma de papel, que custa 4,99 euros.

**c)** O nome de um fornecedor.

**d)** Se um artigo está em promoção ou não.

Concluíste quando cada valor tiver um tipo e uma frase que diga porquê.

## Exercício 2: Fazer o trace de atribuições

A matéria está nas secções "Atribuição: dar um valor não é perguntar se é igual" e "A tabela de trace" do guia.

Uma papelaria regista o stock de um artigo e as vendas do dia com esta sequência de quatro atribuições:

```text
int stock = 50
int vendas = 12
stock = stock - vendas
vendas = vendas + 8
```

**a)** Antes de fazeres o trace, escreve com que valor achas que `stock` fica no fim.

**b)** Faz o trace. A tabela tem uma coluna para o passo, uma para a instrução, uma para cada variável e uma para o ecrã. Começa no passo 0, antes de qualquer instrução. Como nenhuma instrução escreve no ecrã, essa coluna fica com "nada" em todas as linhas.

**c)** No passo 4, `vendas` passou a valer outro número. O valor de `stock` mudou nesse passo? Explica numa frase, a partir do que a atribuição faz.

**d)** Nesta segunda versão, as duas últimas instruções estão pela ordem contrária:

```text
int stock = 50
int vendas = 12
vendas = vendas + 8
stock = stock - vendas
```

Os passos 0, 1 e 2 do trace são iguais aos da alínea b), e podes copiá-los. Faz só os passos 3 e 4 e diz com que valor fica `stock`. Explica numa frase porque é que não é o mesmo valor da alínea b).

Concluíste quando os dois traces estiverem completos, com todas as variáveis em cada linha, e os tiveres comparado com a previsão da alínea a).

## Exercício 3: Atribuições certas e erradas

A matéria está no fim da secção "Atribuição: dar um valor não é perguntar se é igual" do guia. Está também nas secções "Constantes" e "Onde nasce uma variável, e com que tipo".

Um algoritmo começa com estas cinco linhas, que criam uma constante e quatro variáveis:

```text
const LIMITE_DE_SENHAS = 40
int caixas = 0
int total = 1000
int preco = 150
bool pago = true
```

Imagina que cada uma das linhas seguintes vem logo a seguir a estas cinco. Cada linha vê-se sozinha, sem as outras: antes de cada uma, `total` vale 1000, `preco` vale 150 e `pago` vale `true`. Para cada linha, escreve "certa" ou "errada". Se estiver certa, escreve o valor com que a variável da esquerda fica. Se estiver errada, explica numa frase porquê. Por exemplo, para a linha `preco = 350`: certa, `preco` fica com 350.

| Linha | Instrução |
| ---: | --- |
| 1 | `caixas = 5` |
| 2 | `pago = 0` |
| 3 | `total = total + preco` |
| 4 | `LIMITE_DE_SENHAS = 50` |
| 5 | `pago = false` |

Concluíste quando cada linha certa tiver o seu valor e cada linha errada tiver uma frase que diga o que está mal.

## Exercício 4: Calcular expressões

A matéria está na secção "Expressões aritméticas" do guia.

Calcula o valor de cada expressão e escreve o tipo do resultado, `int` ou `float`. Faz as contas à mão, pela ordem das operações. Num resultado `float`, escreve a parte decimal.

| N.º | Expressão | Valor | Tipo |
| ---: | --- | --- | --- |
| 1 | `3 + 4 * 5` | | |
| 2 | `(3 + 4) * 5` | | |
| 3 | `23 div 4` | | |
| 4 | `23 resto 4` | | |
| 5 | `23 / 4` | | |

Concluíste quando as cinco expressões tiverem valor e tipo, e tiveres confirmado as linhas 3 e 4 com a verificação do guia. O divisor vezes o resultado do `div`, mais o `resto`, tem de dar 23.

## Exercício 5: Usar as funções predefinidas

A matéria está na secção "Funções predefinidas" do guia.

Em cada alínea escreves duas coisas. A primeira é a linha onde nasce a variável que recebe o resultado, com o tipo à frente e a função predefinida certa. A segunda é o valor com que a variável fica. Cada uma das quatro funções, `abs`, `arredondar`, `truncar` e `raiz`, serve numa só alínea.

Exemplo do formato, com uma conta sem função: `int totalAPagar = quantidade * preco`; com `quantidade` a valer 3 e `preco` a valer 150, `totalAPagar` fica com 450.

**a)** A variável `tempoEmHoras`, do tipo `float`, vale `3.75`. É o tempo, em horas, que demorou a contagem do stock de um armazém. Guarda em `horasCompletas` o número de horas completas.

**b)** A variável `mediaDeVendas`, do tipo `float`, vale `14.6`. É a média de cadernos vendidos por dia numa semana. Guarda em `mediaArredondada` o número inteiro de cadernos mais próximo dessa média.

**c)** Numa loja com senhas, está a ser atendida a senha guardada em `senhaAtual`, e um cliente tem a senha guardada em `senhaCliente`. Guarda em `distancia` a diferença entre os números das duas senhas, sem sinal, seja qual for a maior. Usa `senhaAtual` a valer 42 e `senhaCliente` a valer 57.

**d)** A variável `area` vale `196`. É a área, em metros quadrados, de um armazém com a forma de um quadrado. Guarda em `lado` o comprimento do lado do armazém, em metros.

Concluíste quando cada alínea tiver a linha, com o tipo e a função, e o valor, e cada função tiver sido usada uma vez.

## Exercício 6: Seguir um algoritmo completo

A matéria está nas secções "Ler e escrever" e "A tabela de trace" do guia. O passo 5 do exemplo guiado é o modelo do trace.

Lê com atenção este algoritmo, que calcula o peso de uma encomenda para envio:

```text
const PESO_DA_CAIXA_VAZIA = 200
Escreve: "Quantos artigos leva a encomenda? "
int artigos = ler valor
Escreve: "Quanto pesa cada artigo, em gramas? "
int pesoPorArtigo = ler valor
int pesoTotal = artigos * pesoPorArtigo + PESO_DA_CAIXA_VAZIA
Escreve: "Peso total em gramas: ", pesoTotal
```

**a)** Faz o trace completo para uma encomenda de 3 artigos de 150 gramas cada, com uma coluna por variável e uma para o ecrã. Mostra todas as linhas, e não só o resultado.

**b)** Um colega escreveu a conta do peso assim:

```text
int pesoTotal = artigos * (pesoPorArtigo + PESO_DA_CAIXA_VAZIA)
```

Calcula o resultado da versão dele para os mesmos 3 artigos de 150 gramas.

**c)** A encomenda vai toda numa só caixa. Qual das duas versões está certa, a do algoritmo ou a do colega? Explica numa frase.

Concluíste quando o teu trace mostrar o valor de todas as variáveis em cada linha e tiveres escolhido a versão certa com uma razão.

## Exercício 7: Escrever um algoritmo teu

A matéria está na secção "A forma do pseudocódigo nas aulas" do guia. O exemplo guiado das caixas de cadernos tem a mesma forma que este problema.

A cantina da escola compra leite em grades de 24 pacotes. O fornecedor também vende pacotes soltos. Uma grade custa 1440 cêntimos e um pacote solto custa 70 cêntimos. Dado o número de pacotes de que a cantina precisa, queremos saber quantas grades completas compra e quantos pacotes soltos compra além dessas grades. Queremos saber também quanto vai pagar ao todo.

O contrato já está feito, para te concentrares no algoritmo:

| Pergunta | Resposta |
| --- | --- |
| Entradas | O número de pacotes de que a cantina precisa, um inteiro igual ou maior do que zero |
| Saídas | O número de grades completas, o número de pacotes soltos, entre 0 e 23, e o total a pagar em cêntimos, os três inteiros |
| Restrições | Uma grade tem sempre 24 pacotes e custa 1440 cêntimos; um pacote solto custa 70 cêntimos |
| Condições | Não há caminhos alternativos: os passos são sempre os mesmos |

**a)** Escreve o algoritmo em pseudocódigo ou em frases claras, sem deixar dúvidas. Usa constantes para os três valores fixos. Se escreveres em frases, dá um nome a cada valor fixo e diz quanto vale. Antes de leres o número de pacotes, escreve a pergunta.

**b)** Segue o teu algoritmo, instrução a instrução, e preenche esta tabela para 100 e para 24 pacotes:

| Pacotes necessários | Grades | Pacotes soltos | Total a pagar, em cêntimos |
| ---: | ---: | ---: | ---: |
| 100 | | | |
| 24 | | | |

**c)** Escolhe uma terceira entrada que teste uma situação diferente das duas anteriores. Acrescenta-a à tabela e explica numa frase o que ela testa.

Concluíste quando o teu algoritmo não deixar dúvidas, usar as três constantes, ler antes de calcular e escrever os três resultados no fim. A tabela tem de ter as três entradas.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Para cada valor, faz a pergunta do guia: vou fazer contas com este valor? Se não, é quase sempre texto. Se sim, a parte decimal interessa? E se o valor for só a resposta a uma pergunta de sim ou não, o tipo é outro. Num valor em dinheiro, relê no guia a nota sobre o dinheiro.

**Exercício 2.** Faz o trace por linhas, e não por variáveis. Numa atribuição, calcula primeiro o lado direito com os valores da linha de cima, e só depois guarda o resultado na variável da esquerda. Para a alínea c), relê no guia a primeira consequência da atribuição.

**Exercício 3.** Interpreta cada linha, com a palavra "recebe" no lugar do `=`. O que está à esquerda do `=` pode receber um valor? Depois volta às cinco primeiras linhas e vê como nasceu o nome que está à esquerda.

**Exercício 4.** Faz primeiro os parênteses, depois as multiplicações e as divisões, incluindo `div` e `resto`, e só no fim as somas. Para o `div` e o `resto`, pensa em 23 lápis arrumados em caixas de 4: quantas caixas se enchem, e quantos lápis sobram? E lembra-te de que `/` dá sempre um `float`.

**Exercício 5.** Para cada alínea, pergunta-te primeiro o que queres fazer ao número, por palavras tuas. Só depois procura, na tabela das funções do guia, a função que faz isso. Cada função serve numa só alínea. Se uma te parecer servir em duas, relê o que cada uma faz às casas decimais. Para o tipo da variável, vê na mesma tabela o tipo que a função devolve.

**Exercício 6.** Tem o passo 5 do exemplo guiado aberto ao lado, porque o trace faz-se da mesma maneira. Na alínea b), faz primeiro a conta que está dentro dos parênteses. Na alínea c), faz as contas das duas versões para uma encomenda de 2 artigos, e pensa em quantas caixas leva esse envio.

**Exercício 7.** Começa pelo pseudocódigo das caixas de cadernos do guia, porque aqui também há uma quantidade, uma divisão inteira e um resto. Se uma linha não te sair em pseudocódigo, escreve-a em frases claras e continua. A diferença é que no fim há um preço a calcular. Escreve primeiro só as grades e os soltos, e acrescenta o total depois de isso funcionar. Na alínea c), relê os três casos de teste do passo 1 do exemplo guiado. O que é que 100 e 24 já testam, e o que falta testar?

**Desafio, parte A.** Relê a troca que falha, na secção da atribuição do guia, e a pergunta que vem logo a seguir a ela.

## Desafio opcional

O desafio tem três partes independentes, e podes fazê-las pela ordem que quiseres. As partes B e C partem do teu algoritmo do exercício 7. A parte B é de fluxogramas, e só a fazes quando o professor o indicar.

### Parte A: trocar os valores de duas variáveis

A matéria está na secção "Atribuição: dar um valor não é perguntar se é igual" do guia, onde há uma troca que falha.

Duas variáveis inteiras começam assim:

```text
int caixaA = 12
int caixaB = 30
```

Escreve as instruções que trocam os valores das duas, de forma que no fim `caixaA` valha 30 e `caixaB` valha 12. Podes usar uma variável a mais, se precisares, com o tipo escrito na linha onde aparece pela primeira vez. Faz o trace da tua solução, desde as duas linhas acima, para mostrar que funciona.

### Parte B: o fluxograma do exercício 7 na aplicação (só quando o professor o indicar)

Esta parte é opcional mesmo dentro do desafio, e só a fazes quando o professor o indicar. A matéria está na secção "Os símbolos do fluxograma" do guia e no laboratório.

Desenha no diagrams.net o fluxograma do teu algoritmo do exercício 7. Guarda-o como `fluxograma-compra-de-leite.drawio` e verifica-o com a lista da fase 4 do laboratório, adaptada a este algoritmo. Depois exporta a imagem, com o nome `fluxograma-compra-de-leite.png`.

### Parte C: o fornecedor muda as grades

O fornecedor passa a vender grades de 12 pacotes em vez de 24, e a grade passa a custar 780 cêntimos. O pacote solto continua a custar 70 cêntimos.

**a)** Quantas linhas do teu pseudocódigo precisam de mudar? E se, em vez de constantes, tivesses escrito os números 24 e 1440 diretamente nas contas, quantos sítios terias de procurar e mudar?

**b)** Se fizeste a parte B, o fluxograma precisa de ser redesenhado, ou basta mudar o texto de algumas figuras? Justifica.

**c)** Refaz a tabela de resultados para 100 pacotes com os valores novos.

É esta a razão por que se dá nome aos valores fixos. Uma mudança de fornecedor não devia obrigar a reler o algoritmo todo à procura de números soltos.

## Para ires mais longe

Esta secção é opcional. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e o desafio e quer mais prática, ou para estudar em casa. Os primeiros itens tratam casos que costumam enganar, um ou dois de cada vez, e é por isso que não entraram na parte obrigatória. O último é um problema novo.

### Mais longe 1: Três valores com o tipo menos óbvio

Continua o exercício 1. A matéria está na secção "Tipos de dados" do guia, sobretudo no parágrafo sobre o número de telefone.

Diz o tipo de cada valor e justifica a escolha numa frase:

**a)** O peso de uma encomenda, em quilogramas, como 2,35.

**b)** O código postal de uma loja, como 4000-123.

**c)** O código de barras de um artigo, com 13 algarismos.

### Mais longe 2: Um número entre aspas

Continua o exercício 3. A matéria está no parágrafo do guia sobre o número `12` e o texto `"12"`.

A variável `quantidade` nasceu mais acima, assim: `int quantidade = 0`. Das duas linhas seguintes, uma está certa e a outra está errada. Diz qual é qual e explica a diferença numa frase.

```text
quantidade = 12
quantidade = "12"
```

### Mais longe 3: Expressões que enganam

Continua os exercícios 4 e 5. A matéria está nas secções "Expressões aritméticas" e "Funções predefinidas" do guia, nos parágrafos sobre os casos que enganam.

As expressões vêm aos pares, e cada par esconde um engano diferente. Calcula o valor e o tipo de cada uma e, para cada par, diz numa frase qual é o engano.

| Par | Expressão | Valor | Tipo |
| ---: | --- | --- | --- |
| 1 | `30 - 10 - 5` | | |
| 1 | `40 / 8 / 2` | | |
| 2 | `4 div 23` | | |
| 2 | `4 resto 23` | | |
| 3 | `arredondar(4.5)` | | |
| 3 | `arredondar(4.49)` | | |
| 4 | `truncar(-8.99)` | | |
| 4 | `arredondar(-8.99)` | | |
| 5 | `raiz(36 + 64)` | | |
| 5 | `raiz(36) + raiz(64)` | | |

### Mais longe 4: A encomenda sem artigos

Continua o exercício 6.

**a)** Qual é o resultado do algoritmo do exercício 6 para 0 artigos de 150 gramas? O algoritmo está errado, ou está certo e apenas a responder a uma pergunta que ninguém queria fazer?

**b)** `pesoTotal` é um peso, e mesmo assim nasce como `int`. Porque é que, neste algoritmo, isso não é um problema?

### Mais longe 5: Quando os soltos saem mais caros

Continua o exercício 7 e a parte C do desafio.

Com as grades de 24 pacotes a 1440 cêntimos, há casos em que os pacotes soltos saem mais caros do que uma grade inteira. E a grade ainda traz mais pacotes. Encontra um desses casos e mostra as contas. Com as grades de 12 pacotes a 780 cêntimos, isso ainda pode acontecer? Justifica com contas.

### Mais longe 6: Os autocarros da visita de estudo

Um problema novo, para escreveres de raiz. A matéria é a mesma do exercício 7.

Uma visita de estudo é feita em autocarros, todos com a mesma capacidade. Dado o número de alunos que vão à visita e a capacidade de cada autocarro, queremos saber quantos autocarros ficam completamente cheios. Queremos saber também quantos alunos vão no autocarro que sobra e quantos lugares livres ficam nesse autocarro.

**a)** Escreve o algoritmo completo, em pseudocódigo ou em frases claras. Decide se a capacidade é uma constante ou um dado que se lê, e justifica a decisão numa frase.

**b)** Escolhe três entradas que testem situações diferentes, explica numa frase porque escolheste cada uma, e faz a tabela de resultados.

**c)** Há pelo menos uma situação em que a fórmula dos lugares livres dá um resultado estranho. Descobre qual é e explica porque acontece. Não precisas de a resolver, porque as ferramentas para isso são do guia 03: descobri-la é que conta. Se não a encontrares, experimenta um número de alunos que encha exatamente dois autocarros.

## Critérios de conclusão

- [ ] Escolhi o tipo de cada valor pelo que vou fazer com ele, e justifiquei.
- [ ] Nos traces, copiei em cada linha os valores da linha de cima e mudei só o que a instrução muda.
- [ ] Reconheci as atribuições erradas e expliquei o que está mal em cada uma.
- [ ] Calculei as expressões pela ordem das operações e escrevi o tipo de cada resultado.
- [ ] Usei cada função predefinida com o argumento entre parênteses e dei à variável o tipo que a função devolve.
- [ ] No meu algoritmo, cada variável tem um tipo coerente, escrito na linha onde nasce, e os valores fixos têm nome de constante.
- [ ] O meu algoritmo lê os dados, faz as contas e escreve os resultados, por esta ordem.
- [ ] Testei o meu algoritmo com três entradas que testam coisas diferentes.
- [ ] Se fiz a parte B do desafio, o fluxograma e o pseudocódigo dizem a mesma coisa, e guardei o `.drawio` e o `.png`.

## Autoavaliação

1. O que já consegues fazer sozinho, sem voltar ao guia?
2. O que te custou mais neste tema? Foram os tipos, as contas, as funções predefinidas, escrever o pseudocódigo, ler o fluxograma ou fazer o trace?
3. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
