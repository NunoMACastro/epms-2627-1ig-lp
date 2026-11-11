![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Decisões e validação

Praticas as condições, os operadores lógicos, os intervalos e as fronteiras, até escreveres e testares um algoritmo que aceita ou recusa um pedido. Os exercícios 1 a 5 são obrigatórios, e o 5 continua o 4. Resolves em papel, numa folha que entregas, com os algoritmos em pseudocódigo ou em frases claras que não deixem dúvidas. Para rever: o [guia do tema](../03-decisoes-e-validacao.md).

## Exercício 1: Calcular comparações

Numa papelaria, um funcionário está a registar um pedido de cadernos. Neste momento, `stock` vale 6, `quantidade` vale 6 e `resposta` vale `"N"`. Foi o que o cliente respondeu à pergunta "Quer saco? (S/N)".

Nas alíneas a) a d), escreve a comparação com os valores no lugar das variáveis e o resultado, `true` ou `false`. Por exemplo, `stock > 0` fica `6 > 0`, e o resultado é `true`.

a) `quantidade <= stock`

b) `quantidade < stock`

c) `stock != 0`

d) `resposta == "S"`

e) Com `stock` a valer 6, as alíneas a) e b) deram resultados diferentes. Que outros valores de `quantidade` fazem as duas darem resultados diferentes? Experimenta pelo menos três valores e explica o que descobriste.

Rever: [Operadores de comparação](../03-decisoes-e-validacao.md#operadores-de-comparação) e [Fronteiras e casos de teste](../03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste).

<details>
<summary>Pista</summary>

Lê cada operador por palavras antes de calcular. O `<` lê-se "é menor do que", e o `<=` lê-se "é menor ou igual a". Na alínea d), compara os dois textos carácter a carácter. Na alínea e), experimenta um valor abaixo de 6, o próprio 6 e um valor acima.

</details>

## Exercício 2: Juntar condições com `e`, `ou` e `não`

Copia as duas tabelas para a folha e preenche-as. Em cada linha, calcula primeiro a comparação sozinha, e só depois o resultado final. A primeira linha da alínea a) já está feita, para veres a forma.

a) O armazém só prepara um pedido se o cliente o tiver confirmado e se houver stock que chegue. O stock do artigo é 20. A variável `confirmado` é do tipo `bool`, e a condição é `confirmado e quantidade <= stock`.

| confirmado | quantidade | `quantidade <= stock` | `confirmado e quantidade <= stock` |
| --- | ---: | --- | --- |
| `true` | 8 | `8 <= 20` dá `true` | `true e true` dá `true` |
| `true` | 25 | | |
| `false` | 8 | | |
| `false` | 25 | | |

b) Um artigo vai para a lista de compras ao fornecedor se o stock estiver abaixo de 5. Também vai se houver uma reserva de um cliente por satisfazer. A variável `reservado` é do tipo `bool`, e a condição é `stock < 5 ou reservado`.

| stock | reservado | `stock < 5` | `stock < 5 ou reservado` |
| ---: | --- | --- | --- |
| 3 | `false` | | |
| 12 | `false` | | |
| 12 | `true` | | |
| 3 | `true` | | |

c) Com o stock a valer 20, o funcionário quer um aviso quando um pedido não cabe no stock. Escreveu a condição `não (quantidade <= stock)`.

1. Calcula-a com `quantidade` a valer 25 e com `quantidade` a valer 20.
2. Escreve a mesma condição sem `não`, e confirma que dá os mesmos dois resultados.

Rever: [Operador `e`](../03-decisoes-e-validacao.md#operador-e), [Operador `ou`](../03-decisoes-e-validacao.md#operador-ou) e [Operador `não`](../03-decisoes-e-validacao.md#operador-não).

<details>
<summary>Pista</summary>

Escreve primeiro o resultado da comparação na terceira coluna. Depois procura, na tabela de verdade do guia, a linha com os mesmos dois valores. Na alínea c), calcula primeiro o que está dentro dos parênteses, e só depois aplica o `não`.

</details>

## Exercício 3: De palavras para condições

Cada alínea descreve uma regra de uma loja. Escreve cada caso de teste com o resultado da condição, na forma "valor: resultado", como "7: true".

a) Uma encomenda tem desconto de volume quando tem mais de 100 unidades. Variável: `unidades`. Escreve a condição de desconto, diz se o 100 está incluído ou excluído, e escreve os três casos de teste deste limite.

b) Uma encomenda vai pelo correio normal se pesar pelo menos 2 kg e menos de 10 kg. Variável: `peso`, um número inteiro de quilogramas. Escreve a condição do correio normal e diz quais são os dois limites e se estão incluídos. Depois escreve os seis casos de teste, três por cada limite.

c) Escreve a condição de uma encomenda que não vai pelo correio normal, isto é, com um peso fora do intervalo da alínea b). Calcula-a para os mesmos seis casos e confirma que dá sempre o contrário da condição da alínea b).

d) A regra "os clientes que fizeram entre 10 e 20 compras este ano recebem um vale de desconto" não chega para escrever a condição. Diz o que falta saber e escreve a pergunta que farias a quem pediu o algoritmo. Não escrevas a condição.

Rever: [Intervalos](../03-decisoes-e-validacao.md#intervalos), [O contrário de um intervalo](../03-decisoes-e-validacao.md#o-contrário-de-um-intervalo) e [Fronteiras e casos de teste](../03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste).

<details>
<summary>Pista</summary>

Desenha uma reta pequena para cada regra e marca os valores que a regra aceita. Em cada extremo, lê a regra com o próprio número: uma encomenda de exatamente 10 kg pesa "menos de 10 kg"? Para a alínea c), marca na reta os valores que ficam de fora, e pergunta-te que comparações os descrevem.

</details>

## Exercício 4: Planear a decisão de um pedido

> Um armazém de material escolar leva as encomendas às escolas numa carrinha. Antes de aceitar um pedido para a próxima viagem, o funcionário escreve quantas caixas ainda cabem na carrinha. A esse número chama-se a capacidade livre. Depois escreve quantas caixas tem o pedido. O pedido é aceite se tiver pelo menos 1 caixa e não ultrapassar a capacidade livre. Se o pedido tiver menos de 1 caixa, o algoritmo escreve "Quantidade inválida". Se ultrapassar a capacidade livre, escreve "Pedido recusado: não cabe na carrinha". Nos outros casos, escreve "Pedido aceite". Podes assumir que a capacidade livre escrita pelo funcionário é sempre um inteiro maior ou igual a zero. Por isso, o algoritmo não a valida.

Neste exercício ainda não escreves o algoritmo. Preparas o que te vai deixar escrevê-lo e testá-lo no exercício 5.

a) Desenha a reta da quantidade de caixas do pedido para uma capacidade livre de 40, como a [reta da escala](../03-decisoes-e-validacao.md#a-reta-da-escala) do exemplo guiado. Marca as regiões, a resposta de cada região e as fronteiras.

b) Desenha a árvore de casos, como a [árvore da nota](../03-decisoes-e-validacao.md#a-árvore-da-nota). Ao lado de cada pergunta, escreve a condição, em pseudocódigo ou numa frase clara. A primeira pergunta é a da validação da quantidade.

c) Constrói a tabela de casos esperados para uma capacidade livre de 40. Usa o valor abaixo, o próprio limite e o valor acima de cada limite. Acrescenta um sétimo caso, com a carrinha cheia: capacidade livre 0 e um pedido de 1 caixa.

Rever: [A reta com as regiões](../03-decisoes-e-validacao.md#a-reta-com-as-regiões), [Validar os dados antes de os usar](../03-decisoes-e-validacao.md#validar-os-dados-antes-de-os-usar) e [A árvore de casos e a tabela de casos esperados](../03-decisoes-e-validacao.md#a-árvore-de-casos-e-a-tabela-de-casos-esperados).

<details>
<summary>Pista</summary>

Começa pela reta, e marca os sítios onde a resposta muda. Um desses sítios depende de um valor que o funcionário escreve. Experimenta desenhar a reta também para uma capacidade livre de 25, e vê o que muda. Para a árvore, sublinha no enunciado as mensagens que o algoritmo pode escrever. Depois compara com a árvore da nota: porque é que lá as duas regiões inválidas foram parar à mesma ponta?

</details>

## Exercício 5: Escrever o algoritmo do pedido e segui-lo com quatro casos

Continuas o problema do exercício 4, com a tua árvore e a tua tabela ao lado.

a) Escreve o algoritmo, em pseudocódigo ou em frases claras. O algoritmo lê primeiro a capacidade livre e depois a quantidade de caixas do pedido. Em pseudocódigo, usa uma constante para o número mínimo de caixas de um pedido. A cadeia de `Se`, `Senão se` e `Senão` segue a tua árvore, pergunta a pergunta. Em frases, segue a árvore pela mesma ordem, e diz os limites e o que acontece em cada caso.

b) Segue o teu algoritmo com quatro casos da tua tabela do exercício 4. São o valor imediatamente abaixo do limite de baixo, o limite de cima, o valor imediatamente acima dele e a carrinha cheia. Faz uma tabela de resumo, como a do trace dos casos de fronteira, no exemplo guiado. Para cada caso, escreve o valor de cada condição avaliada, `true` ou `false`, o ramo executado e a mensagem que aparece. Quando uma condição não chega a ser avaliada, escreve "não é avaliada". No fim, compara cada mensagem com a que a tua tabela espera. Se algum caso não coincidir, encontra a condição responsável e corrige-a.

Rever: [O pseudocódigo](../03-decisoes-e-validacao.md#o-pseudocódigo), [O trace dos casos de fronteira](../03-decisoes-e-validacao.md#o-trace-dos-casos-de-fronteira) e [Comparar com o previsto](../03-decisoes-e-validacao.md#comparar-com-o-previsto).

<details>
<summary>Pista</summary>

Cada pergunta da tua árvore é uma condição da cadeia, pela mesma ordem. Cada ponta é um ramo, com a sua mensagem recuada por baixo. Escreve primeiro as duas leituras, pela ordem que o enunciado pede. Na alínea b), calcula primeiro a condição do `Se`. Só passas à do `Senão se` se a do `Se` der `false`, e só chegas ao `Senão` se as duas derem `false`.

</details>

## Desafios

### Desafio 1: Uma regra nova de cada vez

Cada alínea muda uma regra ao problema dos exercícios 4 e 5, e parte do teu algoritmo do exercício 5, e não da alínea anterior. Em cada alínea, diz que linhas do teu algoritmo mudam e que casos da tua tabela de casos esperados mudam, saem ou entram.

a) O armazém deixa de aceitar pedidos pequenos: um pedido passa a ter de ter pelo menos 5 caixas. Um pedido com menos de 5 caixas continua a receber a mensagem "Quantidade inválida". Quantas linhas do teu algoritmo mudam? Que casos novos precisas? O que acontece a um pedido de 5 caixas quando a capacidade livre é 3?

b) A carrinha leva no máximo 60 caixas. A capacidade livre escrita pelo funcionário pode agora vir errada, e o algoritmo passa a confirmá-la: tem de estar entre 0 e 60, inclusive. Se não estiver, o algoritmo escreve "Capacidade inválida" e não analisa o pedido. Onde entra esta nova condição na cadeia, e porquê? Encontra um par de valores, uma capacidade e uma quantidade, que mostre o que corre mal se a puseres no sítio errado. Se a capacidade e a quantidade estiverem as duas erradas, que mensagem escreve o teu algoritmo? Justifica a escolha.

c) O armazém passa a aceitar pedidos em parte. Se o pedido não couber todo na carrinha, a carrinha leva as caixas que couberem, e as outras ficam pendentes para a viagem seguinte. Nesse caso, o algoritmo escreve "Aceite em parte: ", seguido do número de caixas que seguem, " caixas; ficam pendentes ", e do número de caixas que ficam. Escreve a nova versão e testa-a com a carrinha cheia, capacidade livre 0, e um pedido de 5 caixas. A mensagem faz sentido? Se não fizer, o que mudavas?

Rever: [Validar os dados antes de os usar](../03-decisoes-e-validacao.md#validar-os-dados-antes-de-os-usar), [Seleção encadeada](../03-decisoes-e-validacao.md#seleção-encadeada) e, para a mensagem com contas da alínea c), [Ler e escrever](../02-pseudocodigo.md#ler-e-escrever), no guia 02.

### Desafio 2: O contrário de uma condição com `e` ou com `ou`

a) Uma encomenda é entregue pela carrinha da loja se a zona de entrega for a 1 ou a 2: `zona == 1 ou zona == 2`. Escreve, sem usar `não`, a condição de uma encomenda que não é entregue pela carrinha.

b) Um artigo vai para a montra da papelaria se houver stock e se custar 5 euros ou menos. O preço guarda-se em cêntimos, e a condição é `stock > 0 e precoEmCentimos <= 500`. Escreve, sem usar `não`, a condição de um artigo que não vai para a montra.

c) Confirma as duas respostas com valores. Na alínea a), com `zona` a valer 2 e a valer 3. Na alínea b), com `stock` 7 e `precoEmCentimos` 300, com `stock` 0 e `precoEmCentimos` 300, e com `stock` 7 e `precoEmCentimos` 800. Em cada caso, a condição original e a tua têm de dar resultados opostos.

Rever: [Operador `não`](../03-decisoes-e-validacao.md#operador-não) e [O contrário de um intervalo](../03-decisoes-e-validacao.md#o-contrário-de-um-intervalo).

<details>
<summary>Pista</summary>

Se na alínea a) escreveste `zona != 1 ou zona != 2`, calcula-a com a zona 2. Dá o contrário da original?

</details>

### Desafio 3: Limites que a frase não diz

a) Uma encomenda é de tamanho médio quando o número de unidades tem três algarismos. Variável: `unidades`, um inteiro positivo. A frase não diz nenhum número. Descobre os dois limites e explica numa frase como chegaste a eles.

b) Escreve a condição de uma encomenda de tamanho médio e os seis casos de teste, cada um com o resultado da condição.

c) Volta à regra das compras da alínea d) do exercício 3. Há quatro respostas possíveis à tua pergunta, conforme o 10 e o 20 contem ou não. Para cada uma, escreve a condição que usarias.

Rever: [Intervalos](../03-decisoes-e-validacao.md#intervalos) e [Fronteiras e casos de teste](../03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste).

<details>
<summary>Pista</summary>

Na alínea a), qual é o menor número que se escreve com três algarismos? E o maior?

</details>

### Desafio 4: Quatro versões do mesmo algoritmo

> Uma loja online de material escolar cobra portes de envio às encomendas de valor inferior a 5000 cêntimos. A partir de 5000 cêntimos, inclusive, os portes são grátis. O valor da encomenda é um número inteiro de cêntimos e tem de ser maior do que zero. Se não for, o algoritmo escreve "Valor inválido". As outras duas mensagens são "Paga portes" e "Portes grátis".

a) Antes de leres as versões, constrói a tabela de casos esperados deste problema, a partir do enunciado. Usa os valores abaixo, no e acima de cada limite.

Quatro alunos escreveram quatro versões do algoritmo. Pode haver versões certas e versões erradas. As versões são diferentes só na seleção. Todas começam com estas três linhas, e a seleção de cada versão vem logo a seguir:

```text
const LIMITE_PORTES_GRATIS = 5000
Escreve: "Valor da encomenda em cêntimos? "
int valorEncomenda = ler valor
```

Versão A:

```text
Se valorEncomenda < 0
    Escreve: "Valor inválido"
Senão se valorEncomenda < LIMITE_PORTES_GRATIS
    Escreve: "Paga portes"
Senão
    Escreve: "Portes grátis"
```

Versão B:

```text
Se valorEncomenda <= 0
    Escreve: "Valor inválido"
Senão se valorEncomenda < LIMITE_PORTES_GRATIS
    Escreve: "Paga portes"
Senão se valorEncomenda > LIMITE_PORTES_GRATIS
    Escreve: "Portes grátis"
```

Versão C:

```text
Se valorEncomenda >= LIMITE_PORTES_GRATIS
    Escreve: "Portes grátis"
Senão se valorEncomenda <= 0
    Escreve: "Valor inválido"
Senão
    Escreve: "Paga portes"
```

Versão D:

```text
Se valorEncomenda <= 0
    Escreve: "Valor inválido"
Senão se não (valorEncomenda > LIMITE_PORTES_GRATIS)
    Escreve: "Paga portes"
Senão
    Escreve: "Portes grátis"
```

b) Faz o trace de cada versão com os casos da tua tabela. Para cada versão, diz se está certa ou errada. Se estiver errada, indica uma entrada que o mostre, o que a versão escreve com essa entrada e o que devia escrever. Diz também qual é a condição responsável. Se achares que está certa, diz com que casos a testaste.

c) Uma das versões não segue o conselho do guia de pôr a validação em primeiro lugar. Está errada por causa disso? Justifica com os casos que testaste, e explica porque é que o conselho do guia continua a ser bom.

Rever: [Fronteiras e casos de teste](../03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste), [Condições que não se sobrepõem e que cobrem todos os casos](../03-decisoes-e-validacao.md#condições-que-não-se-sobrepõem-e-que-cobrem-todos-os-casos) e [A validação vem primeiro](../03-decisoes-e-validacao.md#a-validação-vem-primeiro).

<details>
<summary>Pista</summary>

Não tentes adivinhar o erro a olhar para o código. Faz o trace de cada versão com todos os casos da tua tabela e compara o resultado com o esperado, linha a linha. Para a versão D, escreve a condição do `não` sem o `não`, com a tabela das contrárias do guia. Depois compara-a com a que devia estar lá.

</details>

## Critérios de conclusão

- Calculei cada condição com os valores substituídos e as contas à vista.
- Nas condições com `e` e com `ou`, calculei cada parte antes de as juntar.
- Escrevi os intervalos com `e` e as condições de recusa com `ou`, com cada extremo incluído ou excluído conforme a regra.
- Assinalei a regra ambígua em vez de adivinhar os extremos.
- Fiz a reta, a árvore de casos e a tabela de casos esperados antes de escrever o algoritmo.
- A minha tabela tem casos abaixo, no e acima de cada limite, e pelo menos um caso por cada ponta da árvore.
- Pus a validação antes de usar os valores.
- Segui o meu algoritmo com os quatro casos do exercício 5, e cada um chegou, por um só ramo, à mensagem esperada.

![Rodapé](../../imagens/rodape.png)
