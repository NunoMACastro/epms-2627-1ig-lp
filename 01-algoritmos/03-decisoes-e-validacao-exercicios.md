![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Decisões e validação

Ficha do tema Decisões e validação, do módulo Desenvolver algoritmos. Praticas as condições, os intervalos e as fronteiras, até escreveres e testares um algoritmo que aceita ou recusa um pedido. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](03-decisoes-e-validacao.md) e o [laboratório](03-decisoes-e-validacao-laboratorio.md). Antes de começares, deves ter lido as secções da matéria e o exemplo guiado do guia. Cada exercício diz em que secção do guia está a matéria. Se encravares, volta a essa secção antes de olhares para o apoio. O laboratório é de fluxogramas e é opcional, e nenhum exercício obrigatório desta ficha precisa dele.

## Como trabalhar

Resolve os exercícios pela ordem. Nos dois primeiros aplicas o que o guia mostrou. Calculas condições com valores concretos, primeiro comparações simples e depois condições com `e`, `ou` e `não`. No terceiro decides. Passas regras escritas por palavras para condições e escolhes os casos de teste de cada limite. Nos dois últimos constróis um algoritmo do princípio ao fim. No exercício 4 planeias a decisão de um pedido, e no exercício 5 escreves o algoritmo e segues com ele quatro casos da tua tabela. Cada exercício treina uma coisa, e cada um usa o que os anteriores treinaram.

Nenhum exercício é o exemplo guiado do guia com outros números. O exemplo mostra o caminho, e os exercícios pedem-te que o percorras noutros problemas.

| Exercício | O que treina | Parte |
| --- | --- | --- |
| 1 | Calcular comparações simples, incluindo o valor que fica no limite | Obrigatória |
| 2 | Calcular condições com `e`, `ou` e `não` | Obrigatória |
| 3 | Passar regras dadas por palavras para condições e escolher os casos de teste | Obrigatória |
| 4 | Planear a decisão de um pedido: reta, árvore de casos e tabela de casos esperados | Obrigatória |
| 5 | Escrever o algoritmo desse pedido e segui-lo com quatro casos de teste | Obrigatória |
| Desafio | Mudar uma regra de cada vez ao algoritmo do exercício 5 | Opcional |
| Para ires mais longe | Os casos que costumam enganar, os outros três casos do exercício 5, o fluxograma do exercício 5 e testar o algoritmo de um colega | Opcional |

Precisas de papel e lápis. O diagrams.net, em `https://app.diagrams.net/?lang=pt`, só é preciso para o fluxograma do exercício 5, no Mais longe 7. Esse exercício só o fazes quando o professor o indicar. Nesse caso, guarda os ficheiros na pasta `algoritmos`, com nomes em minúsculas, com hífenes e sem acentos.

O que entregas:

- as respostas escritas dos exercícios 1, 2 e 3;
- do exercício 4, a reta, a árvore de casos e a tabela de casos esperados;
- do exercício 5, o algoritmo e a tabela com a mensagem a que chega cada um dos quatro casos;
- o desafio e os exercícios de "Para ires mais longe", se os fizeres.

## Exercício 1: Calcular comparações

A matéria está nas secções "Operadores de comparação" e "Dois sinais de igual para perguntar" do guia.

Numa papelaria, um funcionário está a registar um pedido de cadernos. Neste momento, `stock` vale 6, `quantidade` vale 6 e `resposta` vale `"N"`, que foi o que o cliente respondeu à pergunta "Quer saco? (S/N)".

Nas alíneas a) a d), escreve a comparação com os valores substituídos e o resultado, `true` ou `false`. Por exemplo, a condição `stock > 0` fica `6 > 0`, e o resultado é `true`.

**a)** `quantidade <= stock`

**b)** `quantidade < stock`

**c)** `stock != 0`

**d)** `resposta == "S"`

**e)** Depois de calculares as quatro condições, quanto vale `stock`? Explica numa frase porquê.

Concluíste quando tiveres as quatro condições calculadas com os valores à vista e a frase da alínea e).

## Exercício 2: Juntar condições com `e`, `ou` e `não`

A matéria está nas secções "Operador `e`", "Operador `ou`" e "Operador `não`" do guia. Tem as tabelas de verdade à vista.

Copia as tabelas para a folha e preenche-as. Em cada linha, calcula primeiro a comparação sozinha e só depois o resultado final. É o que o guia faz quando lê as tabelas de verdade linha a linha. A primeira linha da alínea a) já está preenchida, para veres o formato.

**a)** O armazém só prepara um pedido se o cliente o tiver confirmado e se houver stock que chegue. O stock do artigo é 20. A variável `confirmado` é do tipo `bool`, e a condição é `confirmado e quantidade <= stock`.

| confirmado | quantidade | `quantidade <= stock` | `confirmado e quantidade <= stock` |
| --- | ---: | --- | --- |
| `true` | 8 | `8 <= 20` dá `true` | `true e true` dá `true` |
| `true` | 25 | | |
| `false` | 8 | | |
| `false` | 25 | | |

**b)** Um artigo vai para a lista de compras ao fornecedor se o stock estiver abaixo de 5. Também vai, se houver uma reserva de um cliente por satisfazer. A variável `reservado` é do tipo `bool`, e a condição é `stock < 5 ou reservado`.

| stock | reservado | `stock < 5` | `stock < 5 ou reservado` |
| ---: | --- | --- | --- |
| 3 | `false` | | |
| 12 | `false` | | |
| 12 | `true` | | |
| 3 | `true` | | |

**c)** Com o stock a valer 20, o funcionário quer um aviso quando um pedido não cabe no stock, e escreveu a condição `não (quantidade <= stock)`.

1. Calcula-a com `quantidade` a valer 25 e com `quantidade` a valer 20.
2. Escreve a mesma condição sem `não`, com a tabela dos contrários da secção "Operador `não`", e confirma que dá os mesmos dois resultados.

Concluíste quando as duas tabelas estiverem preenchidas com as contas à vista e tiveres a condição da alínea c) escrita sem `não`.

## Exercício 3: De palavras para condições

A matéria está nas secções "Intervalos", "A reta com as regiões", "O contrário de um intervalo" e "Fronteiras e casos de teste" do guia.

Cada alínea descreve uma regra de uma loja. Os casos de teste de um limite são três: o valor imediatamente abaixo, o próprio limite e o valor imediatamente acima. Escreve cada caso com o resultado que a condição dá, no formato "valor: resultado", por exemplo "7: true".

**a)** Uma encomenda tem desconto de volume quando tem mais de 100 unidades. Variável: `unidades`. Escreve a condição de desconto, diz se o 100 está incluído ou excluído, e escreve os três casos de teste deste limite.

**b)** Um cliente pode reservar de 1 a 12 exemplares de um livro escolar, inclusive. Variável: `exemplares`. Escreve a condição de uma reserva aceite e diz quais são os dois limites e se estão incluídos. Depois escreve os seis casos de teste, três por cada limite.

**c)** Escreve a condição de uma reserva recusada, isto é, com um número de exemplares fora do intervalo da alínea b). Calcula-a para os mesmos seis casos e confirma que dá sempre o contrário da condição da alínea b).

**d)** A regra "os clientes que fizeram entre 10 e 20 compras este ano recebem um vale de desconto" não chega para escrever a condição. Diz o que falta saber e escreve a pergunta que farias a quem pediu o algoritmo. Não escrevas a condição.

Concluíste quando as condições das alíneas a), b) e c) tiverem os seus casos de teste, cada um com o resultado. Na alínea d), basta a pergunta.

## Exercício 4: Planear a decisão de um pedido

A matéria está nas secções "Validar os dados antes de os usar" e "A árvore de casos e a tabela de casos esperados" do guia. Os passos 2, 3 e 4 do exemplo guiado são o modelo deste exercício.

> Um armazém de material escolar leva as encomendas às escolas numa carrinha. Antes de aceitar um pedido para a próxima viagem, o funcionário escreve quantas caixas ainda cabem na carrinha. A esse número chama-se a capacidade livre. Depois escreve quantas caixas tem o pedido. O pedido é aceite se tiver pelo menos 1 caixa e não ultrapassar a capacidade livre. Se o pedido tiver menos de 1 caixa, o algoritmo escreve "Quantidade inválida". Se ultrapassar a capacidade livre, escreve "Pedido recusado: não cabe na carrinha". Nos outros casos, escreve "Pedido aceite". Podes assumir que a capacidade livre escrita pelo funcionário é sempre um inteiro maior ou igual a zero. Por isso, o algoritmo não a valida.

Neste exercício ainda não escreves o algoritmo. Preparas o que te vai permitir escrevê-lo e testá-lo no exercício 5.

**a)** Desenha a reta da quantidade de caixas do pedido para uma capacidade livre de 40, como no passo 2 do exemplo guiado. Marca as regiões, a resposta de cada região e as fronteiras.

**b)** Desenha a árvore de casos, como no passo 3. Ao lado de cada pergunta, escreve a condição, em pseudocódigo ou numa frase clara. A primeira pergunta é a da validação da quantidade.

**c)** Constrói a tabela de casos esperados para uma capacidade livre de 40, como no passo 4. Usa o valor abaixo, o próprio limite e o valor acima de cada limite. Acrescenta um sétimo caso, com a carrinha cheia: capacidade livre 0 e um pedido de 1 caixa.

Concluíste quando cada ponta da árvore tiver pelo menos um caso na tabela e cada limite tiver os seus três casos.

## Exercício 5: Escrever o algoritmo do pedido e segui-lo com quatro casos

Continuas o problema do exercício 4, com a tua árvore e a tua tabela ao lado. A matéria está nos passos 6, 9 e 10 do exemplo guiado.

**a)** Escreve o algoritmo, em pseudocódigo ou em frases claras. O algoritmo lê primeiro a capacidade livre e depois a quantidade de caixas do pedido. Em pseudocódigo, usa uma constante para o número mínimo de caixas de um pedido. Faz a cadeia de `Se`, `Senão se` e `Senão` seguir a tua árvore, pergunta a pergunta. Em frases, segue a árvore pela mesma ordem. Confirma que cada frase diz os limites e o que acontece em cada caso, sem deixar dúvidas.

**b)** Segue o teu algoritmo com quatro dos sete casos da tabela do exercício 4. Com a capacidade livre de 40, são os pedidos de 0, de 40 e de 41 caixas. O quarto é o caso da carrinha cheia, com capacidade livre 0 e um pedido de 1 caixa. Cada um destes quatro casos está junto de uma fronteira, e o da carrinha cheia é o único com outra capacidade livre. Usa uma tabela de resumo como a do passo 9 do exemplo guiado. Para cada caso, escreve o valor de cada condição avaliada, `true` ou `false`, o ramo executado e a mensagem que aparece no ecrã. Quando uma condição não chega a ser avaliada, escreve "não é avaliada". No fim, compara cada mensagem com a que a tua tabela espera, como no passo 10. Se algum caso não coincidir, diz qual é a condição responsável e corrige-a. Os outros três casos da tabela ficam para o Mais longe 6, que é opcional.

Concluíste quando os quatro casos chegarem, cada um por um só ramo, à mensagem que a tua tabela espera.

## Apoio

Usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

- Exercício 1: interpreta cada operador antes de calcular. O `<` lê-se "é menor do que" e o `<=` lê-se "é menor ou igual a". Na alínea d), o `==` lê-se "é igual a?"; compara os dois textos carácter a carácter. Na alínea e), lembra-te do que muda o valor de uma variável.
- Exercício 2: calcula primeiro a comparação e escreve o resultado na terceira coluna. Depois procura, na tabela de verdade do guia, a linha que tem os mesmos dois valores. O `e` só dá verdadeiro quando as duas partes são verdadeiras, e o `ou` só dá falso quando as duas são falsas. Na alínea c), calcula primeiro o que está dentro dos parênteses e só depois aplica o `não`.
- Exercício 3: desenha uma reta pequena para cada regra e marca os valores que a regra aceita. Em cada extremo, lê a regra com o próprio número: por exemplo, um cliente com exatamente 18 anos tem "mais de 18 anos"? Para a condição de recusa, marca na reta os valores que ficam de fora e pergunta-te que comparações os descrevem. Na alínea d), volta ao fim da secção "Intervalos" do guia.
- Exercício 4: começa pela reta, e marca os sítios onde a resposta muda. Um desses sítios depende de um valor que o funcionário escreve. Experimenta desenhar a reta também para uma capacidade livre de 25, e vê o que muda. Para a árvore, sublinha no enunciado as mensagens que o algoritmo pode escrever. Depois compara com o passo 3 do exemplo guiado. Porque é que lá as duas regiões inválidas foram parar à mesma ponta?
- Exercício 5: o pseudocódigo segue a tua árvore. Cada pergunta da árvore é uma condição da cadeia, pela mesma ordem, e cada ponta é um ramo, com a sua mensagem indentada por baixo. O `Senão se` e o `Senão` ficam encostados à margem, na coluna do `Se`. Escreve primeiro as leituras, pela ordem que o enunciado pede. Na alínea b), faz como no passo 9 do exemplo guiado. Para cada caso, calcula primeiro a condição do `Se`. Só se ela der `false` é que calculas a do `Senão se`, e só se as duas derem `false` é que chegas ao `Senão`.

## Desafio opcional

O desafio muda uma regra de cada vez ao problema dos exercícios 4 e 5. Cada alínea parte do teu algoritmo do exercício 5, e não da alínea anterior. Em cada alínea, diz que linhas do teu algoritmo mudam e que casos da tua tabela de casos esperados mudam, saem ou entram.

**a)** O armazém deixa de aceitar pedidos pequenos: um pedido passa a ter de ter pelo menos 5 caixas. Um pedido com menos de 5 caixas continua a receber a mensagem "Quantidade inválida". Quantas linhas do teu algoritmo mudam? Que casos novos precisas? O que acontece a um pedido de 5 caixas quando a capacidade livre é 3?

**b)** A carrinha leva no máximo 60 caixas. O algoritmo passa a confirmar também a capacidade livre que o funcionário escreve. Tem de estar entre 0 e 60, inclusive. Se não estiver, o algoritmo escreve "Capacidade inválida" e não analisa o pedido. Onde entra esta nova condição na cadeia, e porquê? Encontra um par de valores, uma capacidade e uma quantidade, que mostre o que corre mal se a puseres no sítio errado. Se a capacidade e a quantidade estiverem as duas erradas, que mensagem escreve o teu algoritmo? Justifica a escolha.

**c)** O armazém passa a aceitar pedidos em parte. Se o pedido não couber todo na carrinha, a carrinha leva as caixas que couberem, e as outras ficam pendentes para a viagem seguinte. Nesse caso, o algoritmo escreve "Aceite em parte: ", seguido do número de caixas que seguem, " caixas; ficam pendentes ", e do número de caixas que ficam. Escreve a nova versão e testa-a com a carrinha cheia, capacidade livre 0, e um pedido de 5 caixas. A mensagem faz sentido? Se não fizer, o que mudavas?

## Para ires mais longe

Esta secção é opcional. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e o desafio e quer mais prática, ou para estudar em casa. Os cinco primeiros exercícios tratam casos que costumam enganar, e é por isso que não entraram na parte obrigatória. O sexto acaba o exercício 5 com os casos que ficaram fora da parte obrigatória. O sétimo é de fluxogramas, e só o fazes quando o professor o indicar. O oitavo faz-se com um colega.

### Mais longe 1: Parênteses que mudam o resultado

A matéria está na secção "Misturar `e` e `ou`" do guia.

Num dado momento, `stock` vale 12, `quantidade` vale 15 e `reservado` vale `true`. As duas condições seguintes têm as mesmas três partes, pela mesma ordem, mas os parênteses estão em sítios diferentes.

**a)** Calcula `(stock < 5 e quantidade > 10) ou reservado`, com as contas à vista.

**b)** Calcula `stock < 5 e (quantidade > 10 ou reservado)`, com as contas à vista.

**c)** Explica numa ou duas frases porque é que os dois resultados não são iguais.

Pista: resolve primeiro o que está entre parênteses e escreve o resultado por baixo. Só depois aplica o operador que ficou de fora dos parênteses.

### Mais longe 2: O contrário de uma condição com `e` ou com `ou`

A matéria está no fim da secção "Operador `não`" do guia. Troca-se o `e` por `ou`, ou o `ou` por `e`, e cada comparação pela sua contrária.

**a)** Uma encomenda é entregue pela carrinha da loja se a zona de entrega for a 1 ou a 2: `zona == 1 ou zona == 2`. Escreve, sem usar `não`, a condição de uma encomenda que não é entregue pela carrinha.

**b)** Um artigo vai para a montra da papelaria se houver stock e se custar 5 euros ou menos. O preço guarda-se em cêntimos, e a condição é `stock > 0 e precoEmCentimos <= 500`. Escreve, sem usar `não`, a condição de um artigo que não vai para a montra.

**c)** Confirma as duas respostas com valores. Na alínea a), com `zona` a valer 2 e a valer 3. Na alínea b), com `stock` 7 e `precoEmCentimos` 300, com `stock` 0 e `precoEmCentimos` 300, e com `stock` 7 e `precoEmCentimos` 800. Em cada caso, a condição original e a tua têm de dar resultados opostos.

Pista: se na alínea a) escreveste `zona != 1 ou zona != 2`, calcula-a com a zona 2. Dá o contrário da original?

### Mais longe 3: Limites que a frase não diz

A matéria está nas secções "Intervalos" e "Fronteiras e casos de teste" do guia.

**a)** Uma encomenda é de tamanho médio quando o número de unidades tem três algarismos. Variável: `unidades`, um inteiro positivo. A frase não diz nenhum número. Descobre os dois limites e explica numa frase como chegaste a eles.

**b)** Escreve a condição de uma encomenda de tamanho médio e os seis casos de teste, cada um com o resultado da condição.

**c)** Volta à regra das compras da alínea d) do exercício 3. Há quatro respostas possíveis à tua pergunta, conforme o 10 e o 20 contem ou não. Para cada uma, escreve a condição que usarias.

Pista: na alínea a), qual é o menor número que se escreve com três algarismos? E o maior?

### Mais longe 4: Respostas em texto

A matéria está no fim da secção "Operadores de comparação" do guia, que explica quando dois textos são iguais.

Um algoritmo pergunta "Tem cartão de cliente? (S/N)" e guarda a resposta na variável `cartao`, do tipo `string`. Só são respostas válidas os textos `"S"` e `"N"`, exatamente assim, com maiúscula.

**a)** Calcula `cartao == "S"` para cada uma destas respostas: `"S"`, `"s"` e `"Sim"`.

**b)** Escreve a condição de uma resposta válida. Depois escreve, sem usar `não`, a condição de uma resposta inválida.

**c)** Calcula a tua condição de resposta inválida para `"S"`, `"N"`, `"s"` e `"X"`.

**d)** A papelaria dá desconto a quem tiver cartão de cliente ou a quem comprar pelo menos 20 unidades do mesmo artigo. Escreve a condição de desconto, com as variáveis `cartao` e `quantidade`. Depois calcula-a para estes quatro casos: 19 unidades com `"N"`, 20 com `"N"`, 19 com `"S"` e 20 com `"S"`.

Pista: na alínea b), quantas respostas são válidas? Para a inválida, usa a regra do fim da secção "Operador `não`" do guia.

### Mais longe 5: Quatro versões do mesmo algoritmo

A matéria está nas secções "Fronteiras e casos de teste" e "Erros frequentes" do guia.

> Uma loja online de material escolar cobra portes de envio às encomendas de valor inferior a 5000 cêntimos. A partir de 5000 cêntimos, inclusive, os portes são grátis. O valor da encomenda é um número inteiro de cêntimos e tem de ser maior do que zero. Se não for, o algoritmo escreve "Valor inválido". As outras duas mensagens são "Paga portes" e "Portes grátis".

Quatro alunos escreveram quatro versões do algoritmo. Pode haver versões certas e versões erradas. As versões são diferentes só na seleção. Todas começam com estas três linhas, e a seleção de cada versão vem logo a seguir:

```text
const LIMITE_PORTES_GRATIS = 5000
Escreve: "Valor da encomenda em cêntimos?"
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

**a)** Antes de olhares com atenção para as versões, constrói a tabela de casos esperados deste problema, a partir do enunciado. Usa os valores abaixo, no e acima de cada limite.

**b)** Faz o trace de cada versão com os casos da tua tabela. Para cada versão, diz se está certa ou errada. Se estiver errada, indica uma entrada que o mostre, o que a versão escreve com essa entrada e o que devia escrever. Diz também qual é a condição responsável. Se achares que está certa, diz com que casos a testaste.

**c)** Uma das versões não segue o conselho do guia de pôr a validação em primeiro lugar. Está errada por causa disso? Justifica com os casos que testaste, e explica porque é que o conselho do guia continua a ser bom.

Pista: não tentes adivinhar o erro a olhar para o código. Faz o trace de cada versão com todos os casos da tua tabela e compara o resultado com o esperado, linha a linha. Uma versão sem `Senão` no fim pode não escrever nada para alguns valores. Para a versão D, escreve a condição do `não` sem o `não`, com a tabela dos contrários do guia. Depois compara-a com a que devia estar lá.

### Mais longe 6: Os outros três casos do exercício 5

A matéria está nos passos 9 e 10 do exemplo guiado do guia.

Na alínea b) do exercício 5 seguiste o teu algoritmo com quatro dos sete casos da tabela do exercício 4. Ficaram de fora três, todos com a capacidade livre de 40: os pedidos de 1, de 2 e de 39 caixas.

**a)** Segue o teu algoritmo com estes três casos, na mesma tabela de resumo do exercício 5. Para cada caso, escreve o valor de cada condição avaliada, `true`, `false` ou "não é avaliada". Escreve também o ramo executado e a mensagem que aparece no ecrã.

**b)** Compara cada mensagem com a que a tua tabela de casos esperados tem para esse caso. Se algum caso não coincidir, diz qual é a condição responsável e corrige-a.

Pista: faz como no exercício 5. Calcula primeiro a condição do `Se`. Só se ela der `false` é que calculas a do `Senão se`, e só se as duas derem `false` é que chegas ao `Senão`.

### Mais longe 7: O fluxograma do exercício 5

Este exercício é de fluxogramas, e só o fazes quando o professor o indicar. A matéria está no passo 8 do exemplo guiado do guia e no [laboratório](03-decisoes-e-validacao-laboratorio.md).

**a)** Desenha o fluxograma do teu algoritmo do exercício 5 no diagrams.net e guarda-o na pasta `algoritmos` como `fluxograma-aceitar-pedido.drawio`. Se fizeste o laboratório, não precisas de começar do zero. Abre o `fluxograma-classificar-nota.drawio`. Na barra de menus, escolhe "Ficheiro", "Abrir de" e o sítio onde o guardaste. Guarda uma cópia com o nome novo (Ficheiro, Guardar como...). Depois muda os textos e acrescenta as figuras que faltam para a segunda leitura. Exporta a imagem em PNG, com o nome `fluxograma-aceitar-pedido.png`.

**b)** Segue com o dedo, no teu fluxograma, o caminho de cada um dos sete casos da tabela do exercício 4. Faz como na fase 3 do laboratório. Para cada caso, escreve a mensagem a que chegaste e confirma que é a mesma da tua tabela de casos esperados.

Pista: conta as figuras antes de desenhar. Cada linha do pseudocódigo dá uma figura, tirando as linhas `const` e o `Senão`, e o Início e o Fim dão mais duas.

### Mais longe 8: Testar o algoritmo de um colega

A matéria está nos passos 4, 9 e 10 do exemplo guiado do guia.

Pede a um colega o algoritmo que ele escreveu no exercício 5, em pseudocódigo ou em frases. Usa a tabela de casos esperados que tu construíste no exercício 4, com os sete casos. Foi feita a partir do enunciado, antes de veres o algoritmo dele, e é isso que a torna um bom teste.

**a)** Segue o algoritmo do teu colega com cada um dos teus sete casos. Usa uma tabela de resumo como a do passo 9 do exemplo guiado. Para cada caso, escreve o valor de cada condição avaliada, o ramo executado e o que aparece no ecrã.

**b)** Devolve-lhe a tabela preenchida, com o resultado esperado e o resultado obtido lado a lado, e não apenas a conclusão. Se algum caso não coincidir, aponta a condição responsável.

## Critérios de conclusão

- [ ] Calculei cada condição com os valores substituídos e as contas à vista.
- [ ] Nas condições com `e` e com `ou`, calculei cada parte antes de as juntar.
- [ ] Escrevi os intervalos com `e` e as condições de recusa com `ou`, com cada extremo incluído ou excluído conforme a regra.
- [ ] Assinalei a regra ambígua em vez de adivinhar os extremos.
- [ ] Construí a reta, a árvore de casos e a tabela de casos esperados antes de escrever o algoritmo.
- [ ] A minha tabela tem casos abaixo, no e acima de cada limite, e pelo menos um caso por cada ponta da árvore.
- [ ] Pus a validação antes de usar os valores.
- [ ] Segui o meu algoritmo com os quatro casos do exercício 5, e cada um chegou, por um só ramo, à mensagem esperada.
- [ ] Se fiz o Mais longe 7, cada losango do meu fluxograma tem `Sim` e `Não`, e os ramos juntam-se antes do fim.

## Autoavaliação

1. O que já consegues fazer sozinho, sem voltar ao guia?
2. O que te custou mais nesta ficha? Foram as tabelas de verdade, pôr o limite do lado certo, a ordem da cadeia ou a árvore de casos?
3. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
