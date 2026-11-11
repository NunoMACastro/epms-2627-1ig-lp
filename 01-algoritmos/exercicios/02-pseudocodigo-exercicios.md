![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Pseudocódigo

Praticas as peças do pseudocódigo uma de cada vez: os tipos, as atribuições, as contas, as funções predefinidas e o trace. No fim, escreves e testas um algoritmo teu. Os exercícios 1 a 7 são obrigatórios. Resolves em papel, numa folha que entregas. Escreves os algoritmos em pseudocódigo, na forma das aulas, ou em frases claras que não deixem dúvidas. Para rever: o [guia do tema](../02-pseudocodigo.md).

## Exercício 1: O tipo de quatro valores

Diz que tipo usarias para guardar cada valor, `int`, `float`, `string` ou `bool`. Justifica cada escolha numa frase que fale do que vais fazer com o valor. Um exemplo é a temperatura de uma sala, como 21,5 graus. A justificação pode ser esta: "`float`, porque vou fazer contas com ela, como a média do dia, e a parte decimal conta".

a) O número de páginas de um caderno.

b) O preço de um pacote de 500 folhas de papel, que custa 4,99 euros.

c) O número do cartão de estudante de um aluno, como 0451.

d) Se um artigo está em promoção ou não.

Rever: [Tipos de dados](../02-pseudocodigo.md#tipos-de-dados).

<details>
<summary>Pista</summary>

Para cada valor, pergunta: vou fazer contas com ele? Se não, é quase sempre texto. Se sim, a parte decimal interessa? Se o valor é só a resposta a uma pergunta de sim ou não, o tipo é outro. Num valor em dinheiro, relê no guia o parágrafo sobre o dinheiro.

</details>

## Exercício 2: O stock e as vendas do dia

Uma papelaria regista o stock de um artigo e as vendas do dia com esta sequência de quatro atribuições:

```text
int stock = 50
int vendas = 12
stock = stock - vendas
vendas = vendas + 8
```

a) Antes de fazeres o trace, escreve com que valor achas que `stock` fica no fim.

b) Copia esta tabela e completa os passos 2 a 4. Os passos 0 e 1 já estão feitos. Nenhuma instrução escreve no ecrã, e essa coluna fica com "nada" em todas as linhas.

| Passo | Instrução executada | stock | vendas | Ecrã |
| ---: | --- | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | nada |
| 1 | `int stock = 50` | 50 | sem valor | nada |
| 2 | `int vendas = 12` | | | |
| 3 | `stock = stock - vendas` | | | |
| 4 | `vendas = vendas + 8` | | | |

c) No passo 4, `vendas` passa a valer outro número. O valor de `stock` mudou nesse passo? Explica numa frase, a partir do que a atribuição faz.

d) Nesta segunda versão, as duas últimas instruções estão pela ordem contrária:

```text
int stock = 50
int vendas = 12
vendas = vendas + 8
stock = stock - vendas
```

Os passos 0, 1 e 2 do trace são iguais aos da alínea b). Faz só os passos 3 e 4 e diz com que valor fica `stock`. Explica numa frase porque é que não é o mesmo valor da alínea b).

Rever: [A atribuição copia o valor](../02-pseudocodigo.md#a-atribuição-copia-o-valor) e [A tabela de trace](../02-pseudocodigo.md#a-tabela-de-trace).

<details>
<summary>Pista</summary>

Faz o trace por linhas, e não por variáveis. Numa atribuição, calcula primeiro o lado direito com os valores da linha de cima, e só depois guarda o resultado na variável da esquerda.

</details>

## Exercício 3: Atribuições certas e erradas

Um algoritmo começa com estas cinco linhas, que criam uma constante e quatro variáveis:

```text
const LIMITE_DE_SENHAS = 40
int caixas = 0
int total = 1000
int preco = 150
bool pago = true
```

Experimenta cada linha da tabela sozinha, logo a seguir às cinco de cima, sem as outras linhas da tabela. Para cada uma, escreve "certa" ou "errada". Se estiver certa, diz com que valor fica a variável da esquerda. Se estiver errada, explica porquê numa frase. Por exemplo, para `preco = 350`: certa, `preco` fica com 350.

| Linha | Instrução |
| ---: | --- |
| 1 | `caixas = 5` |
| 2 | `pago = 0` |
| 3 | `total = total + preco` |
| 4 | `LIMITE_DE_SENHAS = 50` |
| 5 | `pago = false` |
| 6 | `caixas = "5"` |

Rever: [Atribuição: dar um valor não é perguntar se é igual](../02-pseudocodigo.md#atribuição-dar-um-valor-não-é-perguntar-se-é-igual), [Tipos de dados](../02-pseudocodigo.md#tipos-de-dados) e [Constantes](../02-pseudocodigo.md#constantes).

<details>
<summary>Pista</summary>

Lê cada linha com a palavra "recebe" no lugar do `=`. O que está à esquerda do `=` pode receber um valor? Depois, volta às cinco primeiras linhas e vê como nasceu o nome que está à esquerda, e com que tipo.

</details>

## Exercício 4: Cinco expressões, com valor e tipo

Calcula à mão o valor de cada expressão, pela ordem das operações, e escreve o tipo do resultado, `int` ou `float`. Num resultado `float`, escreve a parte decimal. Confirma as linhas 3 e 4 com a verificação do guia: o divisor vezes o `div`, mais o `resto`, tem de dar 23.

| N.º | Expressão | Valor | Tipo |
| ---: | --- | --- | --- |
| 1 | `3 + 4 * 5` | | |
| 2 | `(3 + 4) * 5` | | |
| 3 | `23 div 4` | | |
| 4 | `23 resto 4` | | |
| 5 | `(23 - 23 resto 4) / 4` | | |

Rever: [Expressões aritméticas](../02-pseudocodigo.md#expressões-aritméticas).

<details>
<summary>Pista</summary>

Faz primeiro os parênteses, depois as multiplicações e as divisões, incluindo `div` e `resto`, e só no fim as somas. Para o `div` e o `resto`, pensa em 23 lápis arrumados em caixas de 4: quantas caixas se enchem, e quantos lápis sobram? Para o tipo, relê no guia o que dá cada operação.

</details>

## Exercício 5: Uma função predefinida para cada situação

Em cada alínea, escreves duas coisas. A primeira é a linha onde nasce a variável que recebe o resultado, com o tipo à frente e a função predefinida certa. A segunda é o valor com que a variável fica. Cada uma das quatro funções, `abs`, `arredondar`, `truncar` e `raiz`, serve numa só alínea.

Exemplo do formato, com uma conta sem função: `int totalAPagar = quantidade * preco`; com `quantidade` a valer 3 e `preco` a valer 150, `totalAPagar` fica com 450.

a) A Rita tem 15,8 anos, guardados em `idadeExata`, do tipo `float`. Numa ficha de inscrição, a idade escreve-se em anos feitos. Guarda em `idade` a idade que a Rita escreve na ficha.

b) Numa pauta, as médias aparecem sem casas decimais: 14,6 aparece como 15, e 14,4 aparece como 14. A variável `mediaFinal`, do tipo `float`, vale `14.6`. Guarda em `notaDaPauta` o valor que aparece na pauta.

c) Numa loja com senhas, está a ser atendida a senha guardada em `senhaAtual`, do tipo `int`, que vale 42. Um cliente tem a senha guardada em `senhaCliente`, do tipo `int`, que vale 57. Guarda em `distancia` quantos números separam as duas senhas. A conta tem de dar o mesmo resultado se trocares as duas senhas de lugar.

d) Um tabuleiro de xadrez é quadrado e tem 64 casas ao todo, guardadas em `casas`, do tipo `int`. Guarda em `casasPorFila` quantas casas tem cada fila do tabuleiro.

Rever: [Funções predefinidas](../02-pseudocodigo.md#funções-predefinidas).

<details>
<summary>Pista</summary>

Para cada alínea, pergunta-te primeiro o que queres fazer ao número, por palavras tuas. Só depois procura, na tabela das funções do guia, a função que faz isso. Se uma função te parecer servir em duas alíneas, relê o que cada uma faz às casas decimais. Para o tipo da variável, vê na mesma tabela o tipo que a função devolve. Na alínea d), um tabuleiro quadrado tem tantas filas como casas em cada fila.

</details>

## Exercício 6: O peso de uma encomenda

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

a) Faz o trace completo para uma encomenda de 3 artigos de 150 gramas cada, com uma coluna por variável e uma para o ecrã. Mostra todas as linhas, e não só o resultado.

b) Um colega escreveu a conta do peso assim:

```text
int pesoTotal = artigos * (pesoPorArtigo + PESO_DA_CAIXA_VAZIA)
```

Calcula o resultado da versão dele para os mesmos 3 artigos de 150 gramas.

c) A encomenda vai toda numa só caixa. Qual das duas versões está certa, a do algoritmo ou a do colega? Explica numa frase.

Rever: [Ler e escrever](../02-pseudocodigo.md#ler-e-escrever), [A ordem das operações](../02-pseudocodigo.md#a-ordem-das-operações), [A tabela de trace](../02-pseudocodigo.md#a-tabela-de-trace) e [O trace de três entradas](../02-pseudocodigo.md#o-trace-de-três-entradas).

<details>
<summary>Pista</summary>

O trace faz-se como o de 30 cadernos, no exemplo guiado do guia. Na alínea b), faz primeiro a conta que está dentro dos parênteses. Na alínea c), faz as contas das duas versões para uma encomenda de 2 artigos, e pensa em quantas caixas leva esse envio.

</details>

## Exercício 7: O leite da cantina

A cantina da escola compra leite em grades de 24 pacotes. O fornecedor também vende pacotes soltos. Uma grade custa 1440 cêntimos e um pacote solto custa 70 cêntimos. Dado o número de pacotes de que a cantina precisa, queremos saber quantas grades completas compra e quantos pacotes soltos compra além dessas grades. Queremos saber também quanto vai pagar ao todo.

O contrato já está feito, para te concentrares no algoritmo:

| Pergunta | Resposta |
| --- | --- |
| Entradas | O número de pacotes de que a cantina precisa, um inteiro igual ou maior do que zero |
| Saídas | O número de grades completas, o número de pacotes soltos, entre 0 e 23, e o total a pagar em cêntimos, os três inteiros |
| Restrições | Uma grade tem sempre 24 pacotes e custa 1440 cêntimos; um pacote solto custa 70 cêntimos |
| Condições | Não há caminhos alternativos: os passos são sempre os mesmos |

a) Escreve o algoritmo, sem deixar dúvidas. Usa constantes para os três valores fixos. Se escreveres em frases, dá um nome a cada valor fixo e diz quanto vale. Antes de leres o número de pacotes, escreve a pergunta.

b) Segue o teu algoritmo à mão, instrução a instrução, em rascunho. Na folha, preenche esta tabela para 100 e para 24 pacotes:

| Pacotes necessários | Grades | Pacotes soltos | Total a pagar, em cêntimos |
| ---: | ---: | ---: | ---: |
| 100 | | | |
| 24 | | | |

c) Escolhe uma terceira entrada que teste uma situação diferente das duas anteriores. Acrescenta-a à tabela e explica numa frase o que ela testa.

Rever: [A forma do pseudocódigo nas aulas](../02-pseudocodigo.md#a-forma-do-pseudocódigo-nas-aulas) e [Exemplo guiado: as caixas de cadernos](../02-pseudocodigo.md#exemplo-guiado-as-caixas-de-cadernos).

<details>
<summary>Pista</summary>

Começa pelo pseudocódigo das caixas de cadernos do guia, porque aqui também há uma quantidade, uma divisão inteira e um resto. A diferença é que no fim há um preço a calcular. Escreve primeiro só as grades e os soltos, e acrescenta o total depois de isso funcionar. Na alínea c), relê os três casos de teste do contrato do exemplo guiado. O que é que 100 e 24 já testam, e o que falta testar?

</details>

## Desafios

### Desafio 1: Trocar os valores de duas variáveis

Duas variáveis inteiras começam assim:

```text
int caixaA = 12
int caixaB = 30
```

Escreve as instruções que trocam os valores das duas, de forma que no fim `caixaA` valha 30 e `caixaB` valha 12. Podes usar uma variável a mais, se precisares, com o tipo escrito na linha onde aparece pela primeira vez. Faz o trace da tua solução, desde as duas linhas acima, para mostrar que funciona.

Rever: [O valor antigo perde-se](../02-pseudocodigo.md#o-valor-antigo-perde-se).

<details>
<summary>Pista</summary>

Relê a troca que falha, no guia. Depois pensa no que farias com dois copos cheios, um de sumo e outro de água, se quisesses trocar os líquidos de copo.

</details>

### Desafio 2: O fornecedor muda as grades

O fornecedor do exercício 7 passa a vender grades de 12 pacotes em vez de 24, e a grade passa a custar 780 cêntimos. O pacote solto continua a custar 70 cêntimos.

a) Quantas linhas do teu pseudocódigo precisam de mudar? E se, em vez de constantes, tivesses escrito os números 24 e 1440 diretamente nas contas, quantos sítios terias de procurar e mudar?

b) Refaz a tabela de resultados para 100 pacotes com os valores novos.

c) Volta às grades antigas, de 24 pacotes a 1440 cêntimos. Há casos em que os pacotes soltos saem mais caros do que uma grade inteira, que ainda traz mais pacotes. Encontra um desses casos e mostra as contas. Com as grades novas, isso ainda pode acontecer? Justifica com contas.

Rever: [Constantes](../02-pseudocodigo.md#constantes).

### Desafio 3: A encomenda sem artigos

a) Qual é o resultado do algoritmo do exercício 6 para 0 artigos de 150 gramas? O resultado faz sentido? Explica.

b) `pesoTotal` é um peso, e mesmo assim nasce como `int`. Porque é que, neste algoritmo, isso não é um problema?

Rever: [Tipos de dados](../02-pseudocodigo.md#tipos-de-dados).

### Desafio 4: Os autocarros da visita de estudo

Uma visita de estudo é feita em autocarros, todos com a mesma capacidade. Dado o número de alunos que vão à visita e a capacidade de cada autocarro, queremos saber quantos autocarros ficam completamente cheios. Queremos saber também quantos alunos vão no último autocarro, o que não vai cheio, e quantos lugares livres ficam nesse autocarro.

a) Escreve o algoritmo completo. Decide se a capacidade é uma constante ou um dado que se lê, e justifica a decisão numa frase.

b) Escolhe três entradas que testem situações diferentes, explica numa frase porque escolheste cada uma, e faz a tabela de resultados.

c) Há pelo menos uma situação em que a fórmula dos lugares livres dá um resultado estranho. Descobre qual é e explica porque acontece. Não precisas de a resolver.

Rever: [Expressões aritméticas](../02-pseudocodigo.md#expressões-aritméticas) e [Exemplo guiado: as caixas de cadernos](../02-pseudocodigo.md#exemplo-guiado-as-caixas-de-cadernos).

<details>
<summary>Pista</summary>

Na alínea c), experimenta os três tipos de caso de teste do exemplo guiado.

</details>

## Critérios de conclusão

- Escolhi o tipo de cada valor pelo que vou fazer com ele, e justifiquei.
- Nos traces, copiei em cada linha os valores da linha de cima e mudei só o que a instrução muda.
- Reconheci as atribuições erradas e expliquei o que está mal em cada uma.
- Calculei as expressões pela ordem das operações e escrevi o tipo de cada resultado.
- Usei cada função predefinida com o argumento entre parênteses e dei à variável o tipo que a função devolve.
- No meu algoritmo, cada variável tem um tipo coerente, escrito na linha onde nasce, e os valores fixos têm nome de constante.
- O meu algoritmo lê os dados, faz as contas e escreve os resultados, por esta ordem.
- Testei o meu algoritmo com três entradas que testam coisas diferentes.

![Rodapé](../../imagens/rodape.png)
