![Cabeçalho](../imagens/cabecalho.png)

# Decisões e validação

Neste guia, os algoritmos passam a escolher o caminho conforme os dados. Escreves condições, juntas condições com `e`, `ou` e `não`, e escolhes os casos de teste nos limites de cada decisão. No fim, o algoritmo já recusa os valores que não fazem sentido. Trabalhas em papel.

Usa a comparação, o tipo `bool` e a tabela de trace do tema 02, e os limites que deixam dúvidas do tema 01. Rever: [Comparar não é atribuir](02-pseudocodigo.md#comparar-não-é-atribuir), [Tipos de dados](02-pseudocodigo.md#tipos-de-dados), [A tabela de trace](02-pseudocodigo.md#a-tabela-de-trace) e [Instruções ambíguas](01-do-problema-ao-algoritmo.md#instruções-ambíguas). Para praticar: [ficha de exercícios](exercicios/03-decisoes-e-validacao-exercicios.md).

## Neste guia

1. [Algoritmos que escolhem o caminho](#algoritmos-que-escolhem-o-caminho)
2. [Condições](#condições)
3. [Operadores de comparação](#operadores-de-comparação)
4. [Dois sinais de igual para perguntar](#dois-sinais-de-igual-para-perguntar)
5. [Seleção simples](#seleção-simples)
6. [Seleção composta](#seleção-composta)
7. [Seleção encadeada](#seleção-encadeada)
8. [Operador `e`](#operador-e)
9. [Operador `ou`](#operador-ou)
10. [Operador `não`](#operador-não)
11. [Misturar `e` e `ou`](#misturar-e-e-ou)
12. [Intervalos](#intervalos)
13. [A reta com as regiões](#a-reta-com-as-regiões)
14. [O contrário de um intervalo](#o-contrário-de-um-intervalo)
15. [Condições que não se sobrepõem e que cobrem todos os casos](#condições-que-não-se-sobrepõem-e-que-cobrem-todos-os-casos)
16. [Fronteiras e casos de teste](#fronteiras-e-casos-de-teste)
17. [Validar os dados antes de os usar](#validar-os-dados-antes-de-os-usar)
18. [O que o contrato supõe e o que decide](#o-que-o-contrato-supõe-e-o-que-decide)
19. [A árvore de casos e a tabela de casos esperados](#a-árvore-de-casos-e-a-tabela-de-casos-esperados)
20. [Exemplo guiado: classificar a nota de um teste](#exemplo-guiado-classificar-a-nota-de-um-teste)

## Algoritmos que escolhem o caminho

O algoritmo das caixas de cadernos, do guia 02, fazia sempre as mesmas contas. Com 30 cadernos, dava 2 caixas e 6 cadernos soltos. Com -30, fazia as mesmas contas, e o resultado não tinha sentido. O contrato diz que -30 não é uma entrada válida, mas o algoritmo não tinha forma de o verificar.

Numa loja, quase nada funciona assim. Um pedido só é aceite se houver stock. Uma encomenda só tem portes grátis a partir de um certo valor. O que o algoritmo faz passa a depender dos dados que recebe.

No dia a dia, decides assim muitas vezes: "se estiver a chover, levo o guarda-chuva". A frase tem uma pergunta de sim ou não, e o que fazer quando a resposta é sim. Os algoritmos deste guia decidem da mesma maneira.

## Condições

No guia 01, uma condição era uma situação que pode acontecer ou não e que muda o que se faz. Agora, passa a escrever-se dentro do algoritmo. Uma **condição** é uma pergunta cuja resposta só pode ser sim ou não. "O stock é maior do que zero?" é uma condição. "Qual é o stock?" não é, porque a resposta é um número.

Num algoritmo, a resposta a uma condição é um valor do tipo `bool`, `true` ou `false`. No meio do texto, diz-se verdadeiro e falso. Uma conta dá um número, e uma condição dá um `bool`. `7 + 3` dá `10`, e `7 == 10` dá `false`.

A resposta depende só do valor que as variáveis têm quando a condição é avaliada. Com `stock` a valer 0, a resposta a "o stock é maior do que zero?" é não. Pode estar para chegar uma entrega, mas o algoritmo só vê o estado, e o estado diz 0.

## Operadores de comparação

As condições mais simples comparam dois valores, com um de seis operadores. A tabela mostra o resultado de cada um com `quantidade` a valer 10:

| Operador | Pergunta | Exemplo | Com quantidade a valer 10 |
| --- | --- | --- | --- |
| `==` | é igual a? | `quantidade == 10` | `true` |
| `!=` | é diferente de? | `quantidade != 10` | `false` |
| `<` | é menor do que? | `quantidade < 10` | `false` |
| `<=` | é menor ou igual a? | `quantidade <= 10` | `true` |
| `>` | é maior do que? | `quantidade > 10` | `false` |
| `>=` | é maior ou igual a? | `quantidade >= 10` | `true` |

Na Matemática, escreves ≤, ≥ e ≠. Aqui usam-se `<=`, `>=` e `!=`, que estão no teclado e são os mesmos do Python. O ponto de exclamação de `!=` quer dizer "não": não igual.

Os textos também se comparam, com `==` e `!=`. `resposta == "S"` pergunta se `resposta` guarda exatamente o texto `"S"`. Dois textos só são iguais com os mesmos caracteres, pela mesma ordem, e as maiúsculas contam. `"s"` e `"S"` são textos diferentes, e `"Sim"` e `"S"` também.

## Dois sinais de igual para perguntar

No guia 02, viste que `=` dá um valor e `==` pergunta. Numa condição, a pergunta "é igual a?" escreve-se sempre com dois sinais. `stock == 0` lê-se "o stock é igual a 0?".

O engano mais comum é escrever a condição com um só sinal, `Se stock = 0`. Lida por palavras, diz "stock recebe 0", que é uma ordem, e não uma pergunta.

Avaliar uma condição não muda nenhuma variável. Depois de se perguntar `stock == 0`, `stock` continua com o valor que tinha. Só uma atribuição, com um só `=`, muda o valor de uma variável.

<details>
<summary>Para ires mais longe: uma condição guardada numa variável</summary>

Os dois sinais podem aparecer na mesma linha:

```text
bool semStock = stock == 0
```

Como em qualquer atribuição, calcula-se primeiro o lado direito, que aqui é uma comparação. O resultado, `true` ou `false`, fica guardado em `semStock`. Com o stock a 0, `semStock` fica com `true`. Com o stock a 7, fica com `false`. Em nenhum dos casos o stock muda.

</details>

## Seleção simples

Uma papelaria quer um aviso quando um artigo está quase a acabar, e só nesse caso. Uma **seleção** é uma instrução que escolhe o que executar conforme uma condição. A mais simples executa um bloco, um grupo de linhas seguidas, quando a condição é verdadeira, e não faz nada quando é falsa:

```text
Se condição
    instruções que só se executam se a condição for verdadeira
```

A linha do `Se` tem a condição. As instruções que dependem dela escrevem-se por baixo, recuadas quatro espaços. Esse recuo chama-se **indentação**, e é a única marca do que fica dentro do `Se`. Nenhuma palavra fecha o bloco. Ele acaba na primeira linha que volta a ficar alinhada com o `Se`, e essa linha já está fora.

No aviso, o valor de `stock` foi lido mais acima, numa parte do algoritmo que aqui não se mostra. Prevê o que aparece no ecrã com o stock a 3 e com o stock a 12.

```text
Se stock < 5
    Escreve: "Atenção: stock baixo"
Escreve: "Verificação concluída"
```

A tabela de trace ganha uma coluna, "Condição e resultado". Na linha do `Se`, mostra a condição com o valor no lugar da variável, e o que ela dá. Com o stock a 3:

| Passo | Instrução executada | stock | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes da seleção | 3 | nenhuma | nada |
| 1 | `Se stock < 5` | 3 | `3 < 5` dá `true` | nada |
| 2 | `Escreve: "Atenção: stock baixo"` | 3 | nenhuma | Atenção: stock baixo |
| 3 | `Escreve: "Verificação concluída"` | 3 | nenhuma | Verificação concluída |

Com o stock a 12:

| Passo | Instrução executada | stock | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes da seleção | 12 | nenhuma | nada |
| 1 | `Se stock < 5` | 12 | `12 < 5` dá `false` | nada |
| 2 | `Escreve: "Verificação concluída"` | 12 | nenhuma | Verificação concluída |

Com 3, a condição é verdadeira, e aparece o aviso. Com 12, é falsa, e o aviso é saltado. Nos dois casos aparece "Verificação concluída", porque essa linha está alinhada com o `Se`, fora da seleção.

A indentação muda o que o algoritmo faz. Esta versão tem as mesmas palavras, mas a última linha também está recuada:

```text
Se stock < 5
    Escreve: "Atenção: stock baixo"
    Escreve: "Verificação concluída"
```

Agora, as duas mensagens estão dentro da seleção. Com o stock a 3, aparecem as duas. Com o stock a 12, não aparece nada. A diferença são quatro espaços no início de uma linha. Por isso, recua só o que depende da condição, e deixa o resto alinhado com o `Se`.

## Seleção composta

No guia 01, "se houver muitas pessoas" era uma palavra vaga. A papelaria deste guia fixou o número: abre um segundo balcão quando há mais de 8 pessoas na fila. Quando não há, fica com um só balcão. São duas respostas, e cada uma tem de aparecer no seu caso.

A **seleção composta** escolhe entre dois blocos, um para quando a condição é verdadeira e outro para quando é falsa:

```text
Se condição
    instruções para quando a condição é verdadeira
Senão
    instruções para quando a condição é falsa
```

Cada um destes caminhos chama-se **ramo**. O `Senão` escreve-se alinhado com o `Se` a que pertence, e cada ramo fica recuado por baixo da linha que o abre.

```text
Se pessoasNaFila > 8
    Escreve: "Abrir o segundo balcão"
Senão
    Escreve: "Manter um só balcão"
```

| pessoasNaFila | Condição e resultado | Ramo executado | Ecrã |
| ---: | --- | --- | --- |
| 12 | `12 > 8` dá `true` | o do `Se` | Abrir o segundo balcão |
| 5 | `5 > 8` dá `false` | o do `Senão` | Manter um só balcão |
| 8 | `8 > 8` dá `false` | o do `Senão` | Manter um só balcão |

Com exatamente 8 pessoas, `8 > 8` é falso, e fica um só balcão. A regra diz "mais de 8", e 8 não é mais de 8. Numa seleção composta, executa-se sempre um dos dois ramos, e só um.

## Seleção encadeada

Um artigo pode estar esgotado, ter stock baixo ou ter stock normal. São três respostas, e a seleção composta só tem dois ramos. A **seleção encadeada** acrescenta condições com `Senão se`, umas a seguir às outras:

```text
Se condição1
    instruções para quando a condição1 é verdadeira
Senão se condição2
    instruções para quando a condição1 é falsa e a condição2 é verdadeira
Senão
    instruções para quando todas as condições são falsas
```

Funciona com três regras:

1. As condições avaliam-se por ordem, de cima para baixo.
2. A primeira condição verdadeira ganha. Executa-se o seu ramo, e o algoritmo salta para depois da cadeia. As condições abaixo dela nem são avaliadas.
3. Se nenhuma for verdadeira, executa-se o ramo do `Senão`. Sem `Senão`, não se executa nada.

Prevê o que aparece com o stock a 3, a 9 e a 0.

```text
Se stock == 0
    Escreve: "Esgotado"
Senão se stock < 5
    Escreve: "Stock baixo"
Senão
    Escreve: "Stock normal"
```

| stock | `stock == 0` | `stock < 5` | Ramo executado | Ecrã |
| ---: | --- | --- | --- | --- |
| 3 | `3 == 0` dá `false` | `3 < 5` dá `true` | o do `Senão se` | Stock baixo |
| 9 | `9 == 0` dá `false` | `9 < 5` dá `false` | o do `Senão` | Stock normal |
| 0 | `0 == 0` dá `true` | não é avaliada | o do `Se` | Esgotado |

O caso que interessa é o 0. A segunda condição também seria verdadeira, porque 0 é menor do que 5. Nunca chega a ser avaliada, porque a primeira já ganhou. Por isso, um artigo esgotado não aparece também como "Stock baixo".

Das regras sai uma consequência. Quando o algoritmo avalia a segunda condição, já sabe que a primeira é falsa. Ao perguntar `stock < 5`, já se sabe que o stock não é 0.

O `Senão se` e o `Senão` escrevem-se alinhados com o `Se`, e é isso que mostra que continuam a mesma cadeia. Uma linha alinhada com o `Se` que não comece por `Senão se` nem por `Senão` já está fora da cadeia. Numa cadeia executa-se, no máximo, um ramo. Com `Senão` no fim, executa-se sempre exatamente um.

<details>
<summary>Para ires mais longe: uma decisão dentro de outra</summary>

A mesma escolha pode escrever-se com um `Se` inteiro dentro de um ramo de outro `Se`. Chama-se decisão aninhada, porque fica dentro da outra, como num ninho. Vais encontrá-la em algoritmos escritos por outras pessoas:

```text
Se stock == 0
    Escreve: "Esgotado"
Senão
    Se stock < 5
        Escreve: "Stock baixo"
    Senão
        Escreve: "Stock normal"
```

Há dois níveis de indentação. Um `Senão` pertence ao `Se` mais próximo que está na mesma coluna, acima dele. O `Senão` da linha 3 é do `Se` da linha 1, e o da linha 6 é do `Se` da linha 4. O `Se` de dentro, com os seus dois ramos, ocupa todo o ramo do `Senão` de fora.

Com o stock a 0, a 3 e a 9, esta versão escreve o mesmo que a cadeia: "Esgotado", "Stock baixo" e "Stock normal". Com o stock a 0, a pergunta de dentro nem é feita, porque está no outro ramo. A cadeia com `Senão se` diz o mesmo com menos indentação, e os exercícios deste tema usam só cadeias.

</details>

## Operador `e`

Uma loja online envia um pedido no próprio dia se estiver pago e tiver chegado antes das 15 horas. São duas perguntas, e as duas contam. Os **operadores lógicos** `e`, `ou` e `não` juntam ou invertem condições. Escrevem-se em minúsculas.

O estado do pagamento está numa variável `pago`, do tipo `bool`, e a hora de chegada numa variável `hora`, do tipo `int`:

```text
pago e hora < 15
```

As comparações calculam-se sempre antes do `e`, do `ou` e do `não`: primeiro `hora < 15`, e só depois o `e`. `pago` entra sozinho, sem comparação, porque já vale `true` ou `false`. Escrever `pago == true` dava o mesmo, com mais letras.

Chamando A a `pago` e B a `hora < 15`, `A e B` só é verdadeira quando as duas são verdadeiras. Basta uma ser falsa para o conjunto ser falso. Uma tabela que mostra o resultado de um operador em todas as combinações possíveis chama-se **tabela de verdade**:

| A: `pago` | B: `hora < 15` | `A e B` | Um pedido assim |
| --- | --- | --- | --- |
| `true` | `true` | `true` | pago, chegou às 10 horas: sai hoje |
| `true` | `false` | `false` | pago, chegou às 16 horas: chegou tarde |
| `false` | `true` | `false` | por pagar, chegou às 10 horas |
| `false` | `false` | `false` | por pagar, chegou às 16 horas |

## Operador `ou`

A papelaria mudou a regra da fila. Abre o segundo balcão se houver mais de 8 pessoas ou se a espera passar de 10 minutos. Os minutos de espera estão na variável `espera`:

```text
pessoasNaFila > 8 ou espera > 10
```

`A ou B` é verdadeira quando pelo menos uma das duas é verdadeira. Só é falsa quando são as duas falsas:

| A: `pessoasNaFila > 8` | B: `espera > 10` | `A ou B` | Uma fila assim |
| --- | --- | --- | --- |
| `true` | `true` | `true` | 12 pessoas e 15 minutos |
| `true` | `false` | `true` | 12 pessoas e 4 minutos: comprida, mas anda |
| `false` | `true` | `true` | 5 pessoas e 15 minutos: curta, mas parada |
| `false` | `false` | `false` | 5 pessoas e 4 minutos |

Repara na primeira linha. Com as duas partes verdadeiras, o `ou` dá verdadeiro. Em português, "ou" às vezes quer dizer "um ou outro, mas não os dois", como em "sopa ou sobremesa". O `ou` dos algoritmos é o de "pagar com dinheiro ou com cartão". Quem tem os dois continua a poder pagar.

## Operador `não`

`não A` troca o valor de `A`. Se `A` é verdadeiro, dá falso, e se `A` é falso, dá verdadeiro:

| A: `stock > 0` | `não (stock > 0)` |
| --- | --- |
| `true` | `false` |
| `false` | `true` |

Quase sempre se escreve o mesmo sem `não`, trocando a comparação pela contrária. `não (stock > 0)` é o mesmo que `stock <= 0`. O contrário de "maior do que 0" não é "menor do que 0", porque o 0 também tem de caber nele. Ao trocar o sentido de uma comparação, o limite muda de lado:

| Condição | A sua contrária |
| --- | --- |
| `a == b` | `a != b` |
| `a != b` | `a == b` |
| `a < b` | `a >= b` |
| `a <= b` | `a > b` |
| `a > b` | `a <= b` |
| `a >= b` | `a < b` |

## Misturar `e` e `ou`

A loja online passou a enviar no próprio dia também os pedidos urgentes, marcados numa variável `urgente`, do tipo `bool`. Há duas maneiras de pôr os parênteses:

```text
(pago e hora < 15) ou urgente
pago e (hora < 15 ou urgente)
```

Prevê o que dá cada uma com um pedido urgente, por pagar, que chegou às 10 horas.

- Na primeira, o parêntese dá falso, porque `pago` é falso. Depois, falso `ou` verdadeiro dá verdadeiro, e o pedido sai hoje, mesmo por pagar.
- Na segunda, o parêntese dá verdadeiro. Depois, falso `e` verdadeiro dá falso, e o pedido não sai, porque não está pago.

As mesmas três partes dão resultados diferentes. A certa depende do que o enunciado diz sobre os pedidos urgentes por pagar, e, se não disser, pergunta-se. Sempre que misturares `e` com `ou`, põe parênteses a mostrar o que se avalia primeiro.

## Intervalos

Na papelaria do guia 01, o número de uma senha só faz sentido de 1 a 40. Um conjunto de valores entre dois limites chama-se **intervalo**. Os dois limites são os **extremos** do intervalo, e cada um pode estar incluído ou excluído.

Num algoritmo, um intervalo escreve-se com duas comparações ligadas por `e`:

```text
senha >= 1 e senha <= 40
```

Lê-se "a senha é maior ou igual a 1 e menor ou igual a 40". Leva `e` porque o valor tem de cumprir as duas partes. O 45 cumpre a primeira e falha a segunda, e o 0 cumpre a segunda e falha a primeira. Com `ou`, a condição deixava de separar. Qualquer número cumpre uma das partes, e o 45 passava, por ser maior ou igual a 1.

Os operadores escolhem-se pelo que o enunciado diz de cada extremo. No guia 01, viste que "mais de 10 kg" deixa dúvidas a quem lê. Nos enunciados destes guias, cada expressão tem uma só leitura:

| O enunciado diz | Operador | O limite conta? |
| --- | --- | --- |
| mais de, acima de | `>` | não |
| pelo menos, a partir de, ou mais | `>=` | sim |
| menos de, abaixo de, inferior a | `<` | não |
| até, no máximo, não ultrapassa, ou menos | `<=` | sim |
| entre | | não se sabe: pergunta |

"De 1 a 40, inclusive" leva `>=` e `<=`. Se o enunciado não disser se um extremo conta, é uma ambiguidade: não adivinhes, pergunta. Quando escreves um enunciado, usa uma destas expressões, para ninguém hesitar.

Há uma forma que parece natural e que nas aulas não se usa, `1 <= senha <= 40`. Muitas linguagens avaliam uma comparação de cada vez. Calculam `1 <= senha`, que dá `true` ou `false`, e depois comparam esse resultado com 40, o que não faz sentido. Por isso, escreve as duas comparações, cada uma com os seus dois valores. Por palavras, também serve: "a senha está entre 1 e 40, incluindo o 1 e o 40".

<details>
<summary>Para ires mais longe: os intervalos na Matemática</summary>

Na Matemática, os intervalos escrevem-se com parênteses retos. [1, 40] são os números de 1 a 40, com os dois extremos incluídos. Um extremo incluído diz-se fechado, e um extremo excluído diz-se aberto. Na notação portuguesa, o extremo aberto leva o parêntese virado para fora: [1, 40[ inclui o 1 e exclui o 40. Em Python, `1 <= senha <= 40` funciona, mas nas aulas escrevem-se as duas comparações, como na algoritmia.

</details>

## A reta com as regiões

A forma mais segura de pensar num intervalo é desenhá-lo. Desenha-se uma reta com os valores possíveis e marcam-se os limites. Por cima de cada pedaço da reta, escreve-se a resposta que o algoritmo dá. Cada pedaço chama-se **região**. Para o número da senha:

```text
       inválida    |              válida              |    inválida
  ...  -1    0     |   1    2    3   ...   39    40   |   41    42  ...
                   ↑                                  ↑
              entre 0 e 1                        entre 40 e 41
```

A reta tem três regiões. Os sítios onde se passa de uma região para a outra, marcados com as setas, são as **fronteiras**. Aqui há duas, entre o 0 e o 1 e entre o 40 e o 41. Numa fronteira, a resposta do algoritmo muda.

## O contrário de um intervalo

Muitas vezes interessa o contrário: a senha não está no intervalo de 1 a 40. Um valor está fora quando está abaixo do limite de baixo ou acima do limite de cima:

```text
senha < 1 ou senha > 40
```

O contrário de uma condição com `e` ou com `ou` tem uma regra. O `e` passa a `ou`, ou o `ou` passa a `e`, e cada parte passa à sua contrária, pela tabela do operador `não`. Aqui, `>= 1` passou a `< 1`, e `<= 40` passou a `> 40`, com o limite a mudar de lado.

Leva `ou` porque, para estar fora, basta falhar um dos lados. O 0 está fora por estar abaixo de 1, e o 45 por estar acima de 40. Escrita com `e`, a condição pedia um número abaixo de 1 e acima de 40 ao mesmo tempo. Esse número não existe, e `senha < 1 e senha > 40` nunca é verdadeira. Uma validação com ela nunca apanhava nada.

A mesma regra serve fora dos intervalos. O pedido que não sai hoje é o contrário de `pago e hora < 15`:

```text
(não pago) ou hora >= 15
```

O contrário de `pago` é `não pago`, e os parênteses mostram que o `não` se aplica só a `pago`. Lê-se assim: o pedido não sai hoje se não estiver pago, ou se tiver chegado às 15 horas ou depois.

## Condições que não se sobrepõem e que cobrem todos os casos

Quando uma seleção separa os valores em grupos, há duas propriedades a confirmar. A primeira é que as condições não se sobrepõem: nenhum valor pertence a dois grupos. Com "stock baixo até 10, inclusive" e "stock normal a partir de 10, inclusive", o 10 ficava nos dois.

A segunda é que as condições cobrem todos os casos: cada valor pertence a algum grupo. Com "stock baixo abaixo de 10" e "stock normal acima de 10", o 10 não ficava em nenhum, e não tinha resposta.

As duas confirmam-se na reta. Cada valor tem de cair numa região, e numa só.

Numa seleção encadeada, a sobreposição fica escondida. Como a primeira condição verdadeira ganha, um valor que pertencia a dois grupos vai, sem aviso, para o que está escrito primeiro. Se não era isso que o enunciado pedia, o algoritmo está errado, e nada no ecrã o mostra. Por isso, a reta faz-se sempre.

## Fronteiras e casos de teste

Os erros de uma decisão escondem-se nas fronteiras. `senha <= 40` e `senha < 40` dão o mesmo para 39, para 41 e para qualquer valor longe do 40. Só discordam no 40. Quem testa com 20 e com 50 nunca descobre que escreveu o operador errado.

Daí a regra para escolher os casos de teste de uma decisão. Para cada limite, testa o valor imediatamente abaixo, o próprio limite e o valor imediatamente acima. Com inteiros, os vizinhos estão a uma unidade de distância. Para o limite 40, são o 39, o 40 e o 41. Para o limite 1, são o 0, o 1 e o 2.

O próprio limite é o caso de fronteira do guia 01, e os dois vizinhos completam os três casos. Cada um apanha um erro diferente. A condição certa é `senha <= 40`, e as outras três têm um erro cada:

| senha | `senha <= 40` (a certa) | `senha < 40` | `senha <= 41` | `senha == 40` |
| ---: | --- | --- | --- | --- |
| 39 | `true` | `true` | `true` | `false`, erra |
| 40 | `true` | `false`, erra | `true` | `true` |
| 41 | `false` | `false` | `true`, erra | `false` |

O 40 apanha o igual esquecido, e o 41 apanha o limite posto uma unidade ao lado. O 39 apanha um `==` no lugar de `<=`. Os dois primeiros erros nunca aparecem com valores do meio, porque só se notam na fronteira. Um algoritmo testado só no meio das regiões parece quase sempre certo.

## Validar os dados antes de os usar

Um algoritmo de notas recebe 100, escrito por engano em vez de 10, e classifica-o como positiva. Um algoritmo de stock recebe um pedido de -10 cadernos e aumenta o stock, em vez de o diminuir. Os dois dão respostas erradas com ar de certas.

No guia 01, cada entrada do contrato tinha os valores aceitáveis, como "número da senha, um inteiro de 1 a 40". Rever: [Entradas e saídas](01-do-problema-ao-algoritmo.md#entradas-e-saídas). Esse conjunto de valores chama-se o **domínio** da entrada. O domínio da quantidade de um pedido são os inteiros a partir de 1. O de uma resposta de sim ou não são os textos `"S"` e `"N"`. Uma entrada é válida quando pertence ao domínio, e inválida quando não pertence.

**Validar** uma entrada é verificar se é válida antes de a usar, e recusá-la com uma mensagem se não for. Faz-se sempre da mesma maneira:

1. Escreve o domínio de cada entrada, com os limites e se cada um conta.
2. Escreve a condição que apanha os valores fora do domínio. Se o domínio é um intervalo, é o contrário do intervalo, com `ou`.
3. Põe a validação antes de qualquer conta ou decisão que use o valor.
4. No ramo do inválido, escreve uma mensagem que diga o que está errado, e não uses o valor para mais nada.

Nesta fase, assume-se que um `ler valor` para uma variável `int` recebe sempre um número inteiro. A validação é o primeiro ramo de uma cadeia, e o resto do algoritmo fica nos outros ramos. Com uma entrada inválida, só aparece a mensagem.

## O que o contrato supõe e o que decide

O inteiro que o `ler valor` recebe não se valida: assume-se. Uma **suposição** é uma coisa que o contrato dá como certa e que, por isso, o algoritmo não valida. Escreve-se nas entradas do contrato, ao pé dos valores a que diz respeito. Assim, quem lê o contrato sabe em que condições o algoritmo funciona. Uma suposição que ninguém escreveu é um erro escondido.

Uma loja conta o stock de manhã, e é esse número que o algoritmo lê. O contrato pode dizer: "o stock vem da contagem da loja e nunca é negativo, e por isso não se valida". Se alguém escrever -5, esse caso fica fora do contrato.

O contrato guarda também as decisões sobre o que o enunciado não diz, as ambiguidades do guia 01. Rever: [Instruções ambíguas](01-do-problema-ao-algoritmo.md#instruções-ambíguas). Cada uma escreve-se numa linha que começa por "Decisão:". Não é um `Se` do algoritmo: é uma escolha de quem escreve o contrato, feita antes de haver algoritmo.

| No contrato | O que diz | Exemplo |
| --- | --- | --- |
| Suposição | Que uma situação não vai acontecer; o algoritmo não a verifica | O stock vem da contagem da loja e nunca é negativo |
| Decisão | O que o algoritmo faz numa situação que pode acontecer e que o enunciado não resolve | Decisão: as senhas "entre 1 e 40" incluem o 1 e o 40 |

## A árvore de casos e a tabela de casos esperados

Antes de escreveres o pseudocódigo de uma decisão, há duas ferramentas que mostram se a percebeste.

A **árvore de casos** mostra as perguntas que o algoritmo faz, pela ordem, e onde vai parar cada resposta. Cada resposta leva a outra pergunta ou a um resultado. Cada ponta da árvore, onde já não há perguntas, é um resultado possível. Para a classificação do stock:

```text
Pergunta 1: stock == 0?
├── Sim → "Esgotado"
└── Não → Pergunta 2: stock < 5?
          ├── Sim → "Stock baixo"
          └── Não → "Stock normal"
```

A árvore tem três pontas, e a cadeia tem três ramos, pela mesma ordem. Se o pseudocódigo tiver mais ramos, ou menos, do que a árvore tem pontas, um dos dois está errado.

A **tabela de casos esperados** é a lista das entradas de teste. Cada uma tem o resultado que o algoritmo deve dar e a razão da escolha. Já a conheces do guia 02, com os casos de teste das [caixas de cadernos](02-pseudocodigo.md#o-contrato). Numa decisão, segue duas regras:

- cada ponta da árvore tem pelo menos um caso, para todos os caminhos serem percorridos;
- cada limite dá três casos: abaixo, no limite e acima.

A tabela constrói-se antes do algoritmo, a partir do enunciado. Com o algoritmo à frente, é fácil escolher resultados que concordam com ele, e a tabela deixa de apanhar erros. A árvore diz que caminhos existem, e a tabela diz com que valores se testa cada um.

## Exemplo guiado: classificar a nota de um teste

### O problema

> Um professor quer um algoritmo para classificar os testes. O algoritmo lê a nota, um número inteiro de 0 a 20. Uma nota de 10 ou mais é "Positiva", e uma nota abaixo de 10 é "Negativa". Uma nota fora da escala não se classifica: o algoritmo escreve "Nota inválida".

### O contrato

| Pergunta | Resposta |
| --- | --- |
| Entradas | A nota do teste, um número inteiro; os valores aceitáveis vão de 0 a 20 |
| Saídas | Uma só de três mensagens: "Positiva", "Negativa" ou "Nota inválida" |
| Restrições | A escala vai de 0 a 20, com os dois extremos incluídos |
| Condições | A nota pode estar fora da escala; dentro dela, pode ser de 10 ou mais, ou abaixo de 10 |

O algoritmo lê qualquer inteiro que lhe escrevam, e é ele que verifica se o valor pertence à escala. O domínio da nota são os inteiros de 0 a 20. Ao limite que separa duas respostas dentro da escala chama-se **limiar**. O limiar de positiva é 10, e "10 ou mais" quer dizer que o 10 já é positiva.

### A reta da escala

```text
     inválida   |         negativa         |          positiva          |   inválida
  ...  -2   -1  |   0   1   2  ...  8   9  |  10  11  12  ...  19  20   |  21  22  ...
                ↑                          ↑                            ↑
           entre -1 e 0               entre 9 e 10                entre 20 e 21
```

A reta tem quatro regiões e três fronteiras. Cada inteiro cai numa região, e numa só. As condições vão cobrir todos os casos sem se sobreporem.

### A árvore da nota

A primeira pergunta é a da validação. Não faz sentido perguntar se uma nota é positiva antes de saber se é uma nota.

```text
Pergunta 1: a nota está fora da escala?  (nota < 0 ou nota > 20)
├── Sim → "Nota inválida"
└── Não → Pergunta 2: a nota é 10 ou mais?  (nota >= 10)
          ├── Sim → "Positiva"
          └── Não → "Negativa"
```

As duas regiões inválidas da reta, a de baixo e a de cima, dão a mesma resposta. Por isso, são uma só ponta, apanhada por uma única pergunta com `ou`. A árvore tem três pontas, uma por mensagem.

### Os casos de teste, antes do algoritmo

Os limites são o 0, o 10 e o 20, e cada um dá três casos. Os resultados esperados saem do enunciado e da reta:

| Nota | Resultado esperado | Porque se escolheu |
| ---: | --- | --- |
| -1 | Nota inválida | Imediatamente abaixo do limite 0 |
| 0 | Negativa | O limite 0, que é uma nota válida |
| 1 | Negativa | Imediatamente acima do limite 0 |
| 9 | Negativa | Imediatamente abaixo do limiar 10 |
| 10 | Positiva | O limiar, que o enunciado diz ser positiva |
| 11 | Positiva | Imediatamente acima do limiar |
| 19 | Positiva | Imediatamente abaixo do limite 20 |
| 20 | Positiva | O limite 20, que é uma nota válida |
| 21 | Nota inválida | Imediatamente acima do limite 20 |

As três pontas da árvore têm casos, e cada limite tem os seus três vizinhos.

### As condições

A nota é inválida se estiver abaixo de 0, a constante `NOTA_MINIMA`, ou acima de 20, a constante `NOTA_MAXIMA`. É o contrário do intervalo da escala:

```text
nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
```

A nota é positiva se for 10 ou mais, a constante `LIMIAR_POSITIVA`, com o 10 incluído:

```text
nota >= LIMIAR_POSITIVA
```

A condição de positiva não precisa de `nota <= 20`. Vai ficar num `Senão se`, logo a seguir à validação. Quando o algoritmo lá chega, já sabe que a nota é válida, e por isso que está entre 0 e 20. A negativa não precisa de condição, porque é tudo o que sobra para o `Senão`.

### O pseudocódigo

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10
Escreve: "Nota do teste (inteiro de 0 a 20)? "
int nota = ler valor
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Senão se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

Os limites da escala e o limiar são constantes, porque são regras do enunciado: se o limiar mudar, muda-se uma linha. `nota` é `int`, porque o enunciado diz que a nota é inteira. A pergunta diz a escala, para quem usa o algoritmo saber o que escrever.

Em frases claras, o mesmo algoritmo também vale:

> Pergunta a nota do teste, um inteiro de 0 a 20, e lê-a. Se a nota for menor do que 0 ou maior do que 20, escreve "Nota inválida". Se não, e se for 10 ou mais, escreve "Positiva". Nos outros casos, escreve "Negativa".

As frases dizem os limites com números e o que acontece no 10. "Se a nota for boa, escreve Positiva" não chegava, porque não diz a partir de quanto uma nota é boa.

### A validação vem primeiro

Imagina a cadeia a começar pela positiva, depois das mesmas constantes e da mesma leitura. Prevê o que esta versão escreve com a nota 21 e com a nota -1.

```text
Se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Senão
    Escreve: "Negativa"
```

Com 21, a primeira condição, `21 >= 10`, é verdadeira. A primeira verdadeira ganha, e aparece "Positiva". A validação nunca chega a ser avaliada, e uma nota que não existe foi classificada.

Com -1, esta versão responde bem. `-1 >= 10` é falso, passa-se à validação, que é verdadeira, e aparece "Nota inválida". Quem testasse só o -1 ficava convencido de que a validação funcionava. É por isso que a tabela tem um caso inválido de cada lado da escala.

### O trace dos casos de fronteira

As três linhas `const` não têm passo nem coluna, porque só dão nome a valores fixos. Com a nota 10, o limiar:

| Passo | Instrução executada | nota | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | nada |
| 1 | `Escreve: "Nota do teste (inteiro de 0 a 20)? "` | sem valor | nenhuma | Nota do teste (inteiro de 0 a 20)? |
| 2 | `int nota = ler valor` | 10 | nenhuma | a pessoa escreve 10 |
| 3 | `Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA` | 10 | `10 < 0` dá `false`, `10 > 20` dá `false`; `false ou false` dá `false` | nada |
| 4 | `Senão se nota >= LIMIAR_POSITIVA` | 10 | `10 >= 10` dá `true` | nada |
| 5 | `Escreve: "Positiva"` | 10 | nenhuma | Positiva |

No passo 3, a validação é falsa, e passa-se ao `Senão se`. No passo 4, a condição é verdadeira, e executa-se o seu ramo. O `Senão` e a sua mensagem não aparecem na tabela, porque não foram executados.

Os outros casos seguem o mesmo raciocínio. Nesta tabela de resumo, cada linha é o trace de uma entrada, com o valor de cada comparação, o ramo e o ecrã:

| nota | `nota < NOTA_MINIMA` | `nota > NOTA_MAXIMA` | Validação (`ou`) | `nota >= LIMIAR_POSITIVA` | Ramo executado | Ecrã |
| ---: | --- | --- | --- | --- | --- | --- |
| -1 | `true` | `false` | `true` | não é avaliada | o do `Se` | Nota inválida |
| 0 | `false` | `false` | `false` | `false` | o do `Senão` | Negativa |
| 1 | `false` | `false` | `false` | `false` | o do `Senão` | Negativa |
| 9 | `false` | `false` | `false` | `false` | o do `Senão` | Negativa |
| 10 | `false` | `false` | `false` | `true` | o do `Senão se` | Positiva |
| 11 | `false` | `false` | `false` | `true` | o do `Senão se` | Positiva |
| 19 | `false` | `false` | `false` | `true` | o do `Senão se` | Positiva |
| 20 | `false` | `false` | `false` | `true` | o do `Senão se` | Positiva |
| 21 | `false` | `true` | `true` | não é avaliada | o do `Se` | Nota inválida |

Cada caso de fronteira explica-se pelo operador do seu limite:

- O 0 é negativa, e não inválida, porque `0 < 0` é falso. O -1 é inválido porque `-1 < 0` é verdadeiro.
- O 10 é positiva, e não negativa, porque o operador é `>=`, e `10 >= 10` é verdadeiro. O 9 é negativa porque `9 >= 10` é falso.
- O 20 é positiva, e não inválida, porque `20 > 20` é falso. O 21 é inválido porque `21 > 20` é verdadeiro.

### Comparar com o previsto

A coluna "Ecrã" da tabela de resumo coincide com o resultado esperado dos nove casos de teste, e o algoritmo cumpre o contrato.

## Erros frequentes

### Limiar sem o igual

Com `nota > LIMIAR_POSITIVA` na condição de positiva, a nota 10 aparece como negativa, e o enunciado diz que é positiva. Só o 10 mostra o erro. Com 9 e com 11, as duas versões dão o mesmo, e quem testou com 5 e com 15 deu o algoritmo por certo. Acontece por ler "10 ou mais" como "mais de 10". Corrige-se voltando ao enunciado: "10 ou mais" inclui o 10, e o operador é `>=`.

### Dois `Se` separados em vez de uma cadeia

A validação ficou num `Se` sozinho, e a classificação noutro `Se`, logo a seguir:

```text
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

Com 21, aparecem duas mensagens, "Nota inválida" e "Positiva". Com -1, aparecem "Nota inválida" e "Negativa". Com as notas válidas funciona, e quem só testa notas válidas não dá por nada.

A única diferença para o exemplo guiado está na terceira linha, que aqui começa por `Se`, e lá por `Senão se`. Um `Se` encostado à margem começa uma seleção nova, que se avalia sempre, mesmo depois de a primeira ter apanhado a nota inválida. Quando só um dos resultados deve acontecer, escreve-se uma só cadeia: um `Se` no princípio, e depois `Senão se` e `Senão`.

### Um `Senão se` ou um `Senão` desalinhado do seu `Se`

Um `Senão` aparece mais recuado, ou menos, do que o `Se`. Quem lê não sabe a que `Se` ele pertence, e o algoritmo deixa de ter uma só leitura. Acontece por descuido, sobretudo numa cadeia comprida. Para o encontrares, põe o dedo no `Se` e desce a direito. O `Senão se` e o `Senão` da mesma cadeia começam por baixo do dedo. Para o corrigires, alinha-os com o seu `Se`, e recua quatro espaços o que está dentro de cada ramo.

## Palavras novas deste guia

- Condição: uma pergunta cuja resposta só pode ser sim ou não; num algoritmo, dá `true` ou `false`.
- Seleção: uma instrução que escolhe o que executar conforme uma condição.
- Indentação: o recuo de quatro espaços que marca as instruções que ficam dentro de um bloco.
- Seleção composta: a seleção que escolhe entre dois blocos, um para quando a condição é verdadeira e outro para quando é falsa.
- Ramo: cada um dos caminhos que uma seleção pode seguir; no pseudocódigo, o que está recuado por baixo da linha que o abre.
- Seleção encadeada: a seleção que acrescenta condições com `Senão se`; a primeira condição verdadeira ganha.
- Operadores lógicos: `e`, `ou` e `não`, que juntam condições numa condição maior.
- Tabela de verdade: uma tabela que mostra o resultado de um operador em todas as combinações possíveis.
- Intervalo: um conjunto de valores entre dois limites.
- Extremos: os dois limites de um intervalo; cada um pode estar incluído ou excluído.
- Região: cada pedaço da reta dos valores, com a resposta que o algoritmo dá aos valores que lá caem.
- Fronteira: o sítio da reta onde se passa de uma região para outra, e onde a resposta do algoritmo muda.
- Domínio: o conjunto dos valores aceitáveis de uma entrada.
- Validar: verificar se uma entrada é válida antes de a usar, e recusá-la com uma mensagem se não for.
- Suposição: uma coisa que o contrato dá como certa e que, por isso, o algoritmo não valida.
- Árvore de casos: o desenho das perguntas que o algoritmo faz, pela ordem, e de onde vai parar cada resposta.
- Tabela de casos esperados: a lista das entradas de teste, cada uma com o resultado que o algoritmo deve dar e a razão da escolha.
- Limiar: o limite que separa duas respostas dentro da escala, como o 10 entre negativa e positiva.

## O que vem a seguir

No tema seguinte, [Repetição e padrões](04-repeticao-e-padroes.md), o algoritmo passa a repetir instruções, por exemplo para voltar a pedir uma nota até ela ser válida.

![Rodapé](../imagens/rodape.png)
