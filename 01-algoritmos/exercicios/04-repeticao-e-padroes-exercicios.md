![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Repetição e padrões

Praticas os ciclos. Segues um ciclo numa tabela de iterações, completas as três peças e escreves ciclos com os cinco padrões do guia. No fim, percorres arrays. Os exercícios 1 a 10 são obrigatórios. Resolves em papel, numa folha que entregas. Escreves cada algoritmo em pseudocódigo ou em frases claras, desde que não deixem dúvidas. Para rever: o [guia do tema](../04-repeticao-e-padroes.md).

## Exercício 1: Seguir um ciclo já escrito

Um armazém tem 20 caixas de papel. Em cada um dos próximos 3 dias chega uma entrega de 15 caixas, e não sai nenhuma. Este algoritmo mostra o stock no fim de cada dia:

```text
const STOCK_INICIAL = 20
const CAIXAS_POR_ENTREGA = 15
const NUMERO_DE_DIAS = 3
int stock = STOCK_INICIAL
int dia = 1
Enquanto dia <= NUMERO_DE_DIAS
    stock = stock + CAIXAS_POR_ENTREGA
    Escreve: "Fim do dia ", dia, ": ", stock, " caixas"
    dia = dia + 1
Escreve: "Stock final: ", stock, " caixas"
```

A tabela de iterações já tem a primeira linha, para veres o formato. Nessa linha só falta o número de caixas que aparece no ecrã:

| Teste | dia | stock | Condição | Durante a iteração |
| --- | ---: | ---: | --- | --- |
| 1.º | 1 | 20 | `1 <= 3` dá `true` | escreve "Fim do dia 1: .......... caixas" |

a) Copia a tabela e completa-a. Escreve o número que falta na primeira linha e acrescenta uma linha por cada teste da condição, até ao teste que dá `false`.

b) Quantas iterações teve o ciclo? Quantas vezes foi testada a condição?

c) Que valores têm `dia` e `stock` depois do ciclo? O que escreve a última instrução do algoritmo?

Rever: [O trace linha a linha do primeiro ciclo](../04-repeticao-e-padroes.md#o-trace-linha-a-linha-do-primeiro-ciclo) e [A tabela de iterações](../04-repeticao-e-padroes.md#a-tabela-de-iterações).

<details>
<summary>Pista</summary>

Cada linha da tabela mostra os valores no momento em que o algoritmo chega ao `Enquanto`, antes de o corpo se executar. Para o número que aparece no ecrã, faz primeiro o trace linha a linha da primeira iteração, com uma coluna para o ecrã. Depois compara-o com a linha da tabela que já está feita.

</details>

## Exercício 2: Completar a peça que falta

Cada um destes três ciclos tem uma linha em branco, marcada com pontos. Para cada um, escreve a linha que falta e diz qual das três peças ela é: a inicialização, a condição ou a atualização.

a) Escrever as etiquetas das caixas de uma encomenda, da caixa 1 à caixa 4, com a constante `const NUMERO_DE_CAIXAS = 4`:

```text
..........
Enquanto caixa <= NUMERO_DE_CAIXAS
    Escreve: "Etiqueta da caixa ", caixa
    caixa = caixa + 1
```

b) Escrever a lista das prateleiras a contar no inventário, da prateleira 1 à 5, com a constante `const ULTIMA_PRATELEIRA = 5`:

```text
int prateleira = 1
Enquanto ..........
    Escreve: "Contar a prateleira ", prateleira
    prateleira = prateleira + 1
```

c) Imprimir os talões numerados de 101 a 103, com as constantes `const PRIMEIRO_TALAO = 101` e `const ULTIMO_TALAO = 103`:

```text
int talao = PRIMEIRO_TALAO
Enquanto talao <= ULTIMO_TALAO
    Escreve: "Talão ", talao
    ..........
```

Rever: [As três peças de um ciclo](../04-repeticao-e-padroes.md#as-três-peças-de-um-ciclo).

<details>
<summary>Pista</summary>

Para cada ciclo, faz as três perguntas das peças: com que valor começa, em que situação continua e o que muda em cada iteração. A pergunta a que o fragmento não responde é a da peça que falta. Olha também para a margem dos pontos: sem indentação, a linha executa-se uma vez, antes do ciclo; com quatro espaços, em todas as iterações.

</details>

## Exercício 3: Escrever um ciclo com um contador

Uma papelaria recebeu hoje 3 encomendas pela internet. Para cada encomenda, o funcionário escreve o número de artigos. Uma encomenda com mais de 5 artigos vai numa caixa grande. O algoritmo conta quantas caixas grandes são precisas, e começa com estas constantes:

```text
const NUMERO_DE_ENCOMENDAS = 3
const LIMITE_CAIXA_PEQUENA = 5
(as tuas instruções)
```

a) Escreve as instruções que faltam, a seguir às constantes. Usa um `Para`, porque se sabe que são 3 encomendas, com `encomenda` como variável de controlo. Usa as variáveis `artigos` e `caixasGrandes`, as duas `int`. O `ContarStockBaixo` do guia é um bom ponto de partida.

b) Escreve quantas caixas grandes esperas para encomendas de 5, 9 e 7 artigos. Depois faz a tabela de iterações, com colunas para `encomenda`, `artigos` e `caixasGrandes`, e confirma o resultado.

c) Imagina que a linha que aumenta `caixasGrandes` ficava alinhada com o `Se`. Quantas caixas grandes dava o algoritmo com 5, 9 e 7 artigos? Explica numa frase.

Rever: [Padrão contador](../04-repeticao-e-padroes.md#padrão-contador).

<details>
<summary>Pista</summary>

Copia o `ContarStockBaixo` e muda uma coisa de cada vez. Primeiro os nomes das constantes e das variáveis, depois a pergunta do `Escreve:`, e por fim a condição do `Se`. Para a condição, relê o parágrafo que vem logo a seguir à tabela do `ContarStockBaixo`, e faz a mesma pergunta com a regra deste enunciado.

</details>

## Exercício 4: Escrever um ciclo com um totalizador

Numa gráfica houve, durante a manhã, 3 trabalhos de impressão. Para cada trabalho, o funcionário escreve o número de páginas impressas. O funcionário quer ir vendo quantas páginas já se imprimiram. Depois de cada trabalho, o algoritmo mostra as páginas impressas até esse momento, e no fim mostra o total de páginas da manhã. O algoritmo começa assim:

```text
const NUMERO_DE_TRABALHOS = 3
(as tuas instruções)
```

a) Completa o algoritmo com um `Para` e um totalizador. Usa as variáveis `paginas` e `totalPaginas`, as duas `int`, e `trabalho` como variável de controlo. Podes partir do `TotalDeVendas`, mas aqui o número de trabalhos já está numa constante.

b) Escreve o que esperas ver no ecrã para trabalhos de 12, 40 e 8 páginas, depois de cada trabalho e no fim. Depois faz a tabela de iterações, com colunas para `trabalho`, `paginas` e `totalPaginas`, e confirma o resultado.

c) Imagina que a linha que escreve as páginas impressas até agora passava para antes da soma, dentro do `Para`. Com os mesmos trabalhos, que números aparecem depois de cada trabalho?

Rever: [Padrão totalizador](../04-repeticao-e-padroes.md#padrão-totalizador).

<details>
<summary>Pista</summary>

O `TotalDeVendas` começa por ler o número de dias. Aqui não precisas dessa leitura, porque o `Para` vai de 1 até `NUMERO_DE_TRABALHOS`. Para as páginas impressas até cada momento, confirma na tabela o que o teu algoritmo mostra depois de cada trabalho. Têm de ser os números que escreveste na alínea b). Na alínea c), refaz a tabela com a linha no sítio novo.

</details>

## Exercício 5: Descobrir porque é que um contador conta mal

Uma loja tem 4 encomendas por expedir. Uma encomenda é urgente se o prazo de entrega for de 2 dias ou menos. Um colega escreveu este algoritmo para contar as encomendas urgentes, mas o resultado não bate certo:

```text
const NUMERO_DE_ENCOMENDAS = 4
const PRAZO_URGENTE = 2
int urgentes = 0
Para encomenda de 1 até NUMERO_DE_ENCOMENDAS
    Escreve: "Prazo de entrega da encomenda ", encomenda, ", em dias?"
    int prazo = ler valor
    Se prazo <= PRAZO_URGENTE
        urgentes = urgentes + prazo
Escreve: "Encomendas urgentes: ", urgentes
```

a) Faz a tabela de iterações com os prazos 3, 1, 2 e 5, com colunas para `encomenda`, `prazo` e `urgentes`. O que aparece no ecrã no fim?

b) Conta à mão, olhando só para os quatro prazos, quantas encomendas são urgentes. O resultado do algoritmo coincide?

c) Qual é a linha errada? Diz numa frase que padrão ela segue e qual devia seguir.

d) Escreve a linha corrigida e diz o que o ecrã passa a mostrar com os mesmos prazos.

Rever: [Padrão contador](../04-repeticao-e-padroes.md#padrão-contador) e [Padrão totalizador](../04-repeticao-e-padroes.md#padrão-totalizador).

<details>
<summary>Pista</summary>

Na tabela, vê quanto aumenta `urgentes` em cada iteração em que o `Se` dá `true`.

</details>

## Exercício 6: Escrever um ciclo com sentinela

À tarde, na mesma gráfica do exercício 4, ninguém sabe quantos trabalhos vão chegar. O funcionário escreve o número de páginas de cada trabalho à medida que o trabalho fica pronto, e escreve 0 quando a gráfica fecha. Nenhum trabalho tem 0 páginas, e por isso o 0 serve de sentinela. O algoritmo mostra o total de páginas do dia inteiro. São as da tarde e as 60 da manhã, que já se conhecem e estão numa constante:

```text
const SENTINELA = 0
const PAGINAS_DA_MANHA = 60
(as tuas instruções)
```

a) Se o funcionário escrevesse no início quantos trabalhos houve à tarde, que ciclo usavas, e porquê? E como ele não sabe, que ciclo usas? Responde em duas frases.

b) Escreve as instruções que faltam, com a leitura antecipada antes do ciclo e a leitura do valor seguinte no fim do corpo. Usa as variáveis `paginas` e `totalPaginas`, as duas `int`. O `SomarCaixas` ajuda, sem o contador de caixas, porque aqui não se pede o número de trabalhos.

c) Escreve o total do dia que esperas e faz a tabela de iterações em dois casos. No primeiro, o funcionário escreve 40, 8 e 0. No segundo, escreve logo 0, porque à tarde não houve trabalhos.

Rever: [Escolher entre Enquanto e Para](../04-repeticao-e-padroes.md#escolher-entre-enquanto-e-para) e [Padrão sentinela](../04-repeticao-e-padroes.md#padrão-sentinela).

<details>
<summary>Pista</summary>

Na alínea b), copia o `SomarCaixas`, apaga tudo o que tem a ver com `caixas` e muda os nomes. Confirma que lês `paginas` nos dois sítios do padrão sentinela. Para as 60 páginas da manhã, experimenta a tua versão com os dois casos da alínea c), sobretudo com o da tarde sem trabalhos.

</details>

## Exercício 7: Escrever uma validação repetida

Uma loja de informática organiza oficinas gratuitas, numa sala com 20 lugares, todos livres antes desta inscrição. Cada inscrição pode reservar de 1 a 6 lugares. O algoritmo pede o número de lugares e, enquanto o valor não for válido, escreve uma mensagem com o intervalo aceite e pede outra vez. No fim, escreve quantos lugares ficaram reservados e quantos ficam livres na sala. As constantes já estão escritas:

```text
const MINIMO_DE_LUGARES = 1
const MAXIMO_DE_LUGARES = 6
const LUGARES_DA_SALA = 20
(as tuas instruções)
```

a) Acaba o algoritmo, com a variável `lugares`, que é `int`. Como no `PedirQuantidadeValida`, a condição do ciclo descreve o valor inválido.

b) Faz a tabela de iterações quando a pessoa escreve 0, depois 7 e depois 3, e escreve o que aparece no ecrã no fim.

c) A pessoa escreve logo 6. Responde numa frase: quantas iterações tem o ciclo, e o que aparece no ecrã?

Rever: [Padrão validação repetida](../04-repeticao-e-padroes.md#padrão-validação-repetida) e [O contrário de um intervalo](../03-decisoes-e-validacao.md#o-contrário-de-um-intervalo).

<details>
<summary>Pista</summary>

A condição do ciclo é a do valor inválido, abaixo do mínimo ou acima do máximo. Escreve-a primeiro à parte e experimenta-a com 0, 1, 6 e 7 antes de a pores no ciclo. Na alínea c), avalia a condição com 6 antes de fazeres mais nada. Para os lugares livres, confirma a tua versão com os casos das alíneas b) e c). O número de lugares livres tem de corresponder aos lugares que ficaram mesmo reservados.

</details>

## Exercício 8: Somar com o para cada

A papelaria guardou num array as unidades de cadernos vendidas em cada um dos quatro dias em que esteve aberta esta semana:

```text
vendas = [4, 0, 7, 0]
```

a) Escreve um algoritmo que some as quatro vendas com o para cada e escreva o total. No mesmo ciclo, o algoritmo conta os dias em que não se vendeu nenhum caderno, e escreve também esse número. Usa a variável `venda` no para cada, `totalVendido`, que é `int`, para o totalizador, e `diasSemVendas`, também `int`, para a contagem.

b) Escreve o total e o número de dias sem vendas que esperas. Depois faz a tabela de iterações, com uma linha por iteração. Cada linha tem o valor de `venda` e os de `totalVendido` e `diasSemVendas` no fim da iteração.

c) A papelaria passou a abrir também ao sábado, e as vendas da semana são agora `[4, 0, 7, 0, 3]`. Que linhas do teu algoritmo mudam, e que resultados dá?

Rever: [Percorrer um array com o para cada](../04-repeticao-e-padroes.md#percorrer-um-array-com-o-para-cada), [Padrão totalizador](../04-repeticao-e-padroes.md#padrão-totalizador) e [Padrão contador](../04-repeticao-e-padroes.md#padrão-contador).

<details>
<summary>Pista</summary>

O totalizador começa em 0 antes do ciclo e, dentro dele, soma a variável do para cada. Para os dias sem vendas, conta-os primeiro à mão no array. Depois confirma que a coluna `diasSemVendas` acaba nesse número e só muda nas linhas certas.

</details>

## Exercício 9: Mudar só alguns elementos

Na mesma papelaria, os preços de quatro artigos estão num array, em cêntimos:

```text
precos = [250, 100, 120, 60]
```

A partir de amanhã, os artigos que custam mais de 100 cêntimos sobem 10 cêntimos, e os outros ficam com o mesmo preço. Um colega escreveu este algoritmo:

```text
precos = [250, 100, 120, 60]
Para cada preco em precos
    Se preco > 100
        preco = preco + 10
Escreve: precos[0], " ", precos[1], " ", precos[2], " ", precos[3]
```

a) Reescreve o algoritmo com o `Para` e o índice, para os preços mudarem mesmo no array. Usa uma constante `N_PRECOS` para o número de preços, como o guia faz com `N_NOTAS`, e diz o que o ecrã passa a mostrar.

b) Faz a tabela de iterações do teu `Para`, com `i`, a condição do `Se` e o array no fim de cada iteração.

Rever: [O para cada não muda o array](../04-repeticao-e-padroes.md#o-para-cada-não-muda-o-array) e [Percorrer um array com o índice](../04-repeticao-e-padroes.md#percorrer-um-array-com-o-índice).

<details>
<summary>Pista</summary>

A linha `preco = preco + 10` do colega muda a cópia ou o elemento? Na alínea a), parte da versão com o índice do guia e põe o `Se` dentro do `Para`. A linha que soma fica oito espaços para dentro. Lembra-te de que o último índice de um array com 4 elementos é o 3.

</details>

## Exercício 10: Saber se há alguma encomenda pesada

As encomendas com mais de 10 kg só se levam com o carrinho. Os pesos das encomendas de hoje, em quilos, estão num array:

```text
pesos = [3, 10, 12, 8]
```

O algoritmo diz se hoje é preciso o carrinho, isto é, se há pelo menos uma encomenda com mais de 10 kg.

a) Escreve o algoritmo com uma flag `bool` chamada `precisaCarrinho`, a partir do `HaProdutoSemStock`. O algoritmo escreve "É preciso o carrinho" ou "Não é preciso o carrinho".

b) Escreve a resposta que esperas e faz a tabela de iterações, como a do guia. Tem o peso, a condição do `Se` e a flag no fim de cada iteração.

c) Um colega escreveu a linha `bool precisaCarrinho = false` dentro do ciclo, logo a seguir ao `Para cada`. Com o mesmo array, que resposta dá o algoritmo dele? Explica numa frase.

Rever: [Padrão flag](../04-repeticao-e-padroes.md#padrão-flag).

<details>
<summary>Pista</summary>

Copia o `HaProdutoSemStock` e muda o array, o nome da flag, a condição do `Se` e as duas mensagens. Antes de escreveres a condição, escreve ao lado de cada peso do array se essa encomenda precisa do carrinho, pela regra do enunciado. Na alínea c), segue a flag do colega peso a peso e vê com que valor fica depois do último.

</details>

## Desafios

### Desafio 1: Contar as tentativas inválidas

Volta ao teu algoritmo do exercício 7.

a) Acrescenta um contador das tentativas inválidas, e escreve o seu valor no fim, depois dos lugares reservados. Diz onde fica o aumento do contador, antes, dentro ou depois do ciclo, e com que valor o contador começa.

b) Refaz a tabela de iterações com 0, 7 e 3, agora com uma coluna para o contador.

c) Qual é o menor número de vezes que a leitura de `lugares` pode ser executada neste algoritmo? E o maior? Responde numa frase.

Rever: [Padrão contador](../04-repeticao-e-padroes.md#padrão-contador) e [Padrão validação repetida](../04-repeticao-e-padroes.md#padrão-validação-repetida).

<details>
<summary>Pista</summary>

Repara que cada iteração do ciclo só acontece porque o valor lido foi inválido.

</details>

### Desafio 2: Três tentativas no máximo

Volta ao exercício 7 e muda uma só restrição: a pessoa passa a ter no máximo 3 tentativas, contando com a primeira. Se o valor continuar inválido ao fim da terceira tentativa, o algoritmo não pede mais nenhum valor. Escreve "Reserva cancelada: foram usadas as 3 tentativas." e termina. Se o valor for válido numa das três tentativas, o algoritmo escreve a reserva feita, com o número de lugares. Nesse caso, escreve também os lugares livres na sala.

a) O ciclo pode agora terminar por duas razões diferentes. Diz quais são e escreve a condição do ciclo. Como a condição mistura `e` com `ou`, usa parênteses para mostrar o que se avalia primeiro.

b) Depois do ciclo, o algoritmo tem de saber por qual das duas razões o ciclo terminou, para escrever a mensagem certa. Como é que sabe? Escreve essa parte do algoritmo. Atenção: há uma forma de decidir que parece certa e falha num dos casos de teste da alínea c).

c) Monta a tabela de casos esperados, com pelo menos quatro casos. Tem de ter um valor válido à primeira, um valor válido à terceira tentativa, três valores inválidos e um extremo do intervalo. No caso dos três valores inválidos, confirma com a tabela de iterações que a leitura é executada exatamente 3 vezes, nem mais uma.

Rever: [Padrão validação repetida](../04-repeticao-e-padroes.md#padrão-validação-repetida), [Um ciclo com duas maneiras de acabar](../04-repeticao-e-padroes.md#um-ciclo-com-duas-maneiras-de-acabar) e [Misturar `e` e `ou`](../03-decisoes-e-validacao.md#misturar-e-e-ou).

<details>
<summary>Pista</summary>

Se fizeste o desafio 1, já contas as tentativas. Depois do ciclo, qual das duas condições de paragem é verdadeira?

</details>

### Desafio 3: Um ciclo que salta por cima da saída

Num armazém, as prateleiras estão numeradas de 1 a 8, e as de número ímpar ficam no corredor da esquerda. Este algoritmo devia escrever, por ordem, os números das prateleiras do corredor da esquerda:

```text
const ULTIMA_PRATELEIRA = 8
int prateleira = 1
Enquanto prateleira != ULTIMA_PRATELEIRA
    Escreve: "Prateleira ", prateleira
    prateleira = prateleira + 2
```

a) Faz a tabela de iterações até ao 6.º teste.

b) O ciclo termina? Olha para os valores que `prateleira` vai tomando, e explica porque é que a condição nunca chega a ser falsa.

c) Corrige o algoritmo mudando uma só linha. Diz quantas iterações tem a versão corrigida e com que valor fica `prateleira` depois do ciclo.

d) O armazém passa a ter 9 prateleiras, e muda-se a constante para 9. A tua correção escreve todas as prateleiras do corredor da esquerda, incluindo a 9? Se não escrever, encontra outra correção que funcione com 8 e com 9.

Rever: [O ciclo que nunca acaba](../04-repeticao-e-padroes.md#o-ciclo-que-nunca-acaba).

<details>
<summary>Pista</summary>

Escreve só a coluna `prateleira`, lado a lado. Que tipo de números são todos, e que tipo de número é o 8?

</details>

### Desafio 4: Quando o 0 é um dado verdadeiro

Uma loja regista quantos artigos lhe foram devolvidos em cada dia. O funcionário escreve o número de devoluções de cada dia, um dia de cada vez, e não se sabe à partida quantos dias vai registar. Um dia sem devoluções é um dia verdadeiro e tem de entrar nas contas. No fim, o algoritmo mostra quantos dias foram registados, o total de devoluções e a média de devoluções por dia. O princípio do algoritmo, com o valor da sentinela por escolher:

```text
const SENTINELA = ..........
(as tuas instruções)
```

As variáveis chamam-se `devolucoes`, `diasRegistados` e `totalDevolucoes`, que são `int`, e `media`, que é `float`.

a) Explica porque é que, neste problema, o 0 não pode ser a sentinela. Escolhe outro valor para a sentinela e justifica a escolha numa frase.

b) Escreve o resto do algoritmo. A média pode ter parte decimal, e por isso calcula-se com `/`.

c) O que deve o algoritmo mostrar se o funcionário escrever logo a sentinela? Explica numa frase porque é que, nesse caso, não se pode calcular a média, e corrige o teu algoritmo se for preciso.

d) Faz a tabela de iterações quando o funcionário escreve 3, 0, 5, 2 e a sentinela. Escreve antes o resultado que esperas.

Rever: [Padrão sentinela](../04-repeticao-e-padroes.md#padrão-sentinela).

<details>
<summary>Pista</summary>

A sentinela não pode ser um valor que os dados verdadeiros possam ter. Que números nunca podem ser um número de devoluções?

</details>

## Critérios de conclusão

- Em cada tabela de iterações, as linhas mostram o estado no momento do teste, e a última é a do teste que dá `false`.
- Nas tabelas do para cada, há uma linha por elemento, com os valores no fim da iteração.
- Em cada algoritmo que escrevi, escrevi o resultado esperado antes de fazer a tabela de iterações.
- Em cada ciclo que escrevi, sei dizer com que valor começa, em que situação continua e o que muda em cada iteração.
- Os meus contadores e totalizadores começam antes do ciclo, com o valor certo para o caso de zero voltas.
- Sei dizer quando um problema pede um contador e quando pede um totalizador.
- No ciclo com sentinela, a sentinela nunca é somada como se fosse um dado, e testei o caso de zero voltas.
- Na validação repetida, a condição do ciclo descreve o valor inválido, e testei um valor válido à primeira.
- Quando percorro um array pelo índice, o último índice que uso é o número de elementos menos 1, e só mudo o array pelo índice.
- A minha flag começa `false` antes do ciclo, só muda para `true` e só a leio depois do ciclo.

![Rodapé](../../imagens/rodape.png)
