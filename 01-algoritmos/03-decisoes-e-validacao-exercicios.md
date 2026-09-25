![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Decisões e validação

UC: UC00245

Blocos: ALG03

Requisitos: UC00245-R03, UC00245-R04, UC00245-K05, UC00245-K06, UC00245-A05, UC00245-A06, UC00245-C01, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG03, acompanha o [guia](03-decisoes-e-validacao.md) e o [laboratório](03-decisoes-e-validacao-laboratorio.md) |
| Tempo total | 120 minutos dos 300 do bloco: 90 de prática autónoma, nos exercícios 1 a 5, e 30 de desafio opcional. A secção "Para ires mais longe" também é opcional e fica fora destes 120 minutos |
| Entrega | As respostas escritas dos exercícios 1, 2 e 3; do exercício 4, a reta, a árvore de casos e a tabela de casos esperados; do exercício 5, o pseudocódigo, o fluxograma (ficheiro `.drawio` e imagem PNG) e a mensagem a que chegaste em cada caso; o desafio e os exercícios de "Para ires mais longe", se os fizeres |

## Objetivos e conceitos necessários

Vais praticar a avaliação de condições com valores concretos, com comparações e com `E`, `OU` e `NÃO`, a passagem de regras escritas por palavras para intervalos e casos de teste, e a construção de um algoritmo que aceita ou recusa um pedido, desde a reta até ao fluxograma.

Antes de começares, deves ter lido a teoria e o exemplo explicado do [guia](03-decisoes-e-validacao.md) e feito o [laboratório](03-decisoes-e-validacao-laboratorio.md). Tudo o que precisas para esta ficha está lá, e cada exercício diz em que secção do guia está a matéria. Se encravares, volta a essa secção antes de olhares para o apoio.

Material: papel e lápis, e o diagrams.net, em `https://app.diagrams.net/?lang=pt`, para o exercício 5. Guarda os ficheiros na pasta `algoritmos` que usaste nos laboratórios, com nomes em minúsculas, com hífenes e sem acentos.

## Como está organizada a ficha

Resolve os exercícios pela ordem. Nos dois primeiros aplicas o que o guia mostrou: calculas condições com valores concretos, primeiro comparações simples e depois condições com `E`, `OU` e `NÃO`. No terceiro decides: passas regras escritas por palavras para condições e escolhes os casos de teste de cada limite. Nos dois últimos constróis um algoritmo do princípio ao fim: no exercício 4 planeias a decisão de um pedido, e no exercício 5 escreves o pseudocódigo e desenhas o fluxograma. Cada exercício treina uma coisa, e cada um usa o que os anteriores treinaram.

Nenhum exercício é o exemplo explicado do guia com outros números. O exemplo mostra o caminho, e os exercícios pedem-te que o percorras noutros problemas.

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Calcular comparações simples, incluindo o valor que fica no limite | 10 min |
| 2 | Calcular condições com `E`, `OU` e `NÃO` | 15 min |
| 3 | Passar regras dadas por palavras para condições e escolher os casos de teste | 20 min |
| 4 | Planear a decisão de um pedido: reta, árvore de casos e tabela de casos esperados | 15 min |
| 5 | Escrever o pseudocódigo desse pedido e desenhar o fluxograma na aplicação | 30 min |
| Total da parte obrigatória | Exercícios 1 a 5 | 90 min |
| Desafio opcional | Mudar uma regra de cada vez ao algoritmo do exercício 5 | 30 min |
| Para ires mais longe | Opcional: parênteses, contrários de condições com `E` e `OU`, limites que a frase não diz, textos com maiúsculas e várias versões de um algoritmo | fora dos 120 min |

## Exercício 1: Calcular comparações (10 min)

A matéria está nas secções "Operadores de comparação" e "O sinal de igual passou a perguntar" do guia.

Numa papelaria, um funcionário está a registar um pedido de cadernos. Neste momento, `stock` vale 6, `quantidade` vale 6 e `resposta` vale `"N"`, que foi o que o cliente respondeu à pergunta "Quer saco? (S/N)".

Nas alíneas a) a d), escreve a comparação com os valores substituídos e o resultado, `VERDADEIRO` ou `FALSO`. Por exemplo, a condição `stock > 0` fica `6 > 0`, e o resultado é `VERDADEIRO`.

**a)** `quantidade <= stock`

**b)** `quantidade < stock`

**c)** `stock != 0`

**d)** `resposta = "S"`

**e)** Depois de calculares as quatro condições, quanto vale `stock`? Explica numa frase porquê.

Concluíste quando tiveres as quatro condições calculadas com os valores à vista e a frase da alínea e).

## Exercício 2: Juntar condições com E, OU e NÃO (15 min)

A matéria está nas secções "Operador E", "Operador OU" e "Operador NÃO" do guia. Tem as tabelas de verdade à vista.

Copia as tabelas para a folha e preenche-as. Em cada linha, calcula primeiro a comparação sozinha e só depois o resultado final, como o guia faz quando lê as tabelas de verdade linha a linha. A primeira linha da alínea a) já está preenchida, para veres o formato.

**a)** O armazém só prepara um pedido se o cliente o tiver confirmado e se houver stock que chegue. O stock do artigo é 20. A variável `confirmado` é do tipo `lógico`, e a condição é `confirmado E quantidade <= stock`.

| confirmado | quantidade | `quantidade <= stock` | `confirmado E quantidade <= stock` |
| --- | ---: | --- | --- |
| `VERDADEIRO` | 8 | `8 <= 20` é VERDADEIRO | VERDADEIRO E VERDADEIRO dá VERDADEIRO |
| `VERDADEIRO` | 25 | | |
| `FALSO` | 8 | | |
| `FALSO` | 25 | | |

**b)** A papelaria põe um artigo na lista de compras ao fornecedor se o stock estiver abaixo de 5 ou se houver uma reserva de um cliente por satisfazer. A variável `reservado` é do tipo `lógico`, e a condição é `stock < 5 OU reservado`.

| stock | reservado | `stock < 5` | `stock < 5 OU reservado` |
| ---: | --- | --- | --- |
| 3 | `FALSO` | | |
| 12 | `FALSO` | | |
| 12 | `VERDADEIRO` | | |
| 3 | `VERDADEIRO` | | |

**c)** Com o stock a valer 20, o funcionário quer um aviso quando um pedido não cabe no stock, e escreveu a condição `NÃO (quantidade <= stock)`.

1. Calcula-a com `quantidade` a valer 25 e com `quantidade` a valer 20.
2. Escreve a mesma condição sem `NÃO`, com a tabela dos contrários da secção "Operador NÃO", e confirma que dá os mesmos dois resultados.

Concluíste quando as duas tabelas estiverem preenchidas com as contas à vista e tiveres a condição da alínea c) escrita sem `NÃO`.

## Exercício 3: De palavras para condições (20 min)

A matéria está nas secções "Intervalos", "A reta com as regiões", "O contrário de um intervalo" e "Fronteiras e casos de teste" do guia.

Cada alínea descreve uma regra de uma loja. Os casos de teste de um limite são três: o valor imediatamente abaixo, o próprio limite e o valor imediatamente acima. Escreve cada caso com o resultado que a condição dá, no formato "valor: resultado", por exemplo "7: VERDADEIRO".

**a)** Uma encomenda tem desconto de volume quando tem mais de 100 unidades. Variável: `unidades`. Escreve a condição de desconto, diz se o 100 está incluído ou excluído, e escreve os três casos de teste deste limite.

**b)** Um cliente pode reservar de 1 a 12 exemplares de um livro escolar, inclusive. Variável: `exemplares`. Escreve a condição de uma reserva aceite, diz quais são os dois limites e se estão incluídos, e escreve os seis casos de teste, três por cada limite.

**c)** Escreve a condição de uma reserva recusada, isto é, com um número de exemplares fora do intervalo da alínea b). Calcula-a para os mesmos seis casos e confirma que dá sempre o contrário da condição da alínea b).

**d)** A regra "os clientes que fizeram entre 10 e 20 compras este ano recebem um vale de desconto" não chega para escrever a condição. Diz o que falta saber e escreve a pergunta que farias a quem pediu o algoritmo. Não escrevas a condição.

Concluíste quando as condições das alíneas a), b) e c) tiverem os seus casos de teste, cada um com o resultado, e tiveres a pergunta da alínea d).

## Exercício 4: Planear a decisão de um pedido (15 min)

A matéria está nas secções "Validar os dados antes de os usar" e "A árvore de casos e a tabela de casos esperados" do guia. Os passos 2, 3 e 4 do exemplo explicado são o modelo deste exercício.

> Um armazém de material escolar leva as encomendas às escolas numa carrinha. Antes de aceitar um pedido para a próxima viagem, o funcionário escreve quantas caixas ainda cabem na carrinha, a que se chama a capacidade livre, e depois quantas caixas tem o pedido. O pedido é aceite se tiver pelo menos 1 caixa e não ultrapassar a capacidade livre. Se o pedido tiver menos de 1 caixa, o algoritmo escreve "Quantidade inválida". Se ultrapassar a capacidade livre, escreve "Pedido recusado: não cabe na carrinha". Nos outros casos, escreve "Pedido aceite". Podes assumir que a capacidade livre escrita pelo funcionário é sempre um inteiro maior ou igual a zero, e por isso o algoritmo não a valida.

Neste exercício ainda não escreves o algoritmo. Preparas o que te vai permitir escrevê-lo e testá-lo no exercício 5.

**a)** Desenha a reta da quantidade de caixas do pedido para uma capacidade livre de 40, com as regiões, a resposta de cada região e as fronteiras, como no passo 2 do exemplo explicado.

**b)** Desenha a árvore de casos, como no passo 3. Ao lado de cada pergunta, escreve a condição em pseudocódigo. A primeira pergunta é a da validação da quantidade.

**c)** Constrói a tabela de casos esperados para uma capacidade livre de 40, com o valor abaixo, o próprio limite e o valor acima de cada limite, como no passo 4. Acrescenta um sétimo caso, com a carrinha cheia: capacidade livre 0 e um pedido de 1 caixa.

Concluíste quando cada ponta da árvore tiver pelo menos um caso na tabela e cada limite tiver os seus três casos.

## Exercício 5: Escrever e desenhar o algoritmo do pedido (30 min)

Continuas o problema do exercício 4, com a tua árvore e a tua tabela ao lado. A matéria está nos passos 6 e 8 do exemplo explicado e no laboratório.

**a)** Escreve o pseudocódigo. O algoritmo lê primeiro a capacidade livre e depois a quantidade de caixas do pedido. Usa uma constante para o número mínimo de caixas de um pedido. A cadeia de `SE`, `SENÃO SE` e `SENÃO` segue a tua árvore, pergunta a pergunta.

**b)** Desenha o fluxograma no diagrams.net e guarda-o na pasta `algoritmos` como `fluxograma-aceitar-pedido.drawio`. Não precisas de começar do zero: abre o `fluxograma-classificar-nota.drawio` do laboratório, guarda uma cópia com o nome novo (Ficheiro, Guardar como...), muda os textos e acrescenta as figuras que faltam para a segunda leitura. Exporta a imagem em PNG, com o nome `fluxograma-aceitar-pedido.png`.

**c)** Segue com o dedo, no teu fluxograma, o caminho de cada um dos sete casos da tabela do exercício 4, como na parte 4 do laboratório. Para cada caso, escreve a mensagem a que chegaste e confirma que é a que a tabela espera.

Concluíste quando os sete casos chegarem, cada um por um só caminho, à mensagem que a tua tabela espera.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Lê cada operador em voz alta antes de calcular: `<` lê-se "é menor do que" e `<=` lê-se "é menor ou igual a". Com dois valores iguais, só um destes dois operadores dá verdadeiro. Na alínea d), compara os dois textos carácter a carácter. Na alínea e), pensa no que muda o valor de uma variável: uma pergunta ou uma atribuição?

**Exercício 2.** Calcula primeiro a comparação e escreve o resultado na terceira coluna. Depois procura, na tabela de verdade do guia, a linha que tem os mesmos dois valores. O `E` só dá verdadeiro quando as duas partes são verdadeiras, e o `OU` só dá falso quando as duas são falsas. Na alínea c), calcula primeiro o que está dentro dos parênteses e só depois aplica o `NÃO`.

**Exercício 3.** Desenha uma reta pequena para cada regra e marca os valores que a regra aceita. "Mais de 100" não inclui o 100. "De 1 a 12, inclusive" inclui os dois extremos. Para a condição de recusa, olha para a reta: um valor está fora quando está abaixo do limite de baixo ou acima do limite de cima. Na alínea d), pergunta-te se quem fez exatamente 10 compras recebe o vale. A frase responde?

**Exercício 4.** A reta tem três regiões e duas fronteiras, como a das senhas no guia. A fronteira de cima está na capacidade livre, que é lida, e não num número fixo: se a capacidade livre fosse 25, estaria entre o 25 e o 26. As duas recusas têm mensagens diferentes, e por isso são duas pontas diferentes na árvore, e não uma só pergunta com `OU`, como no exemplo do guia. Na tabela, os dois limites são o 1 e o 40.

**Exercício 5.** Compara a tua árvore com a do passo 3 do guia: tem a mesma forma, com duas perguntas e três pontas. O pseudocódigo tem então a mesma forma do passo 6, com um `SE`, um `SENÃO SE`, um `SENÃO` e um só `FIM SE`. A segunda condição compara duas variáveis, a quantidade e a capacidade. No fluxograma, conta as figuras antes de desenhar: cada instrução entre `INÍCIO` e `FIM`, tirando o `SENÃO` e o `FIM SE`, dá uma figura, e o Início e o Fim dão mais duas.

## Desafio opcional (30 min)

O desafio muda uma regra de cada vez ao problema dos exercícios 4 e 5. Cada alínea parte do teu algoritmo do exercício 5, e não da alínea anterior. Em cada alínea, diz que linhas do teu pseudocódigo mudam e que casos da tua tabela de casos esperados mudam, saem ou entram.

**a)** O armazém deixa de aceitar pedidos pequenos: um pedido passa a ter de ter pelo menos 5 caixas. Um pedido com menos de 5 caixas continua a receber a mensagem "Quantidade inválida". Quantas linhas do teu pseudocódigo mudam? Que casos novos precisas? O que acontece a um pedido de 5 caixas quando a capacidade livre é 3?

**b)** A carrinha leva no máximo 60 caixas, e por isso a capacidade livre escrita pelo funcionário deixa de ser de confiança: tem de estar entre 0 e 60, inclusive. Se não estiver, o algoritmo escreve "Capacidade inválida" e não analisa o pedido. Onde entra esta nova condição na cadeia, e porquê? Encontra um par de valores, uma capacidade e uma quantidade, que mostre o que corre mal se a puseres no sítio errado. Se a capacidade e a quantidade estiverem as duas erradas, que mensagem escreve o teu algoritmo? Justifica a escolha.

**c)** O armazém passa a aceitar pedidos em parte: se o pedido não couber todo na carrinha, a carrinha leva as caixas que couberem e as outras ficam pendentes para a viagem seguinte. Nesse caso o algoritmo escreve "Aceite em parte: ", seguido do número de caixas que seguem, " caixas; ficam pendentes ", e do número de caixas que ficam. Escreve a nova versão e testa-a com a carrinha cheia, capacidade livre 0, e um pedido de 5 caixas. A mensagem faz sentido? Se não fizer, o que mudavas?

## Para ires mais longe

Esta secção é opcional e fica fora dos 120 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e o desafio e quer mais prática, ou para estudar em casa. Cada exercício trata um caso que costuma enganar, e é por isso que não entrou na parte obrigatória. Os tempos são indicativos.

### Mais longe 1: Parênteses que mudam o resultado (10 min)

A matéria está na secção "Misturar E e OU" do guia.

Num dado momento, `stock` vale 12, `quantidade` vale 15 e `reservado` vale `VERDADEIRO`. As duas condições seguintes têm as mesmas três partes, pela mesma ordem, mas os parênteses estão em sítios diferentes.

**a)** Calcula `(stock < 5 E quantidade > 10) OU reservado`, com as contas à vista.

**b)** Calcula `stock < 5 E (quantidade > 10 OU reservado)`, com as contas à vista.

**c)** Explica numa ou duas frases porque é que os dois resultados não são iguais.

Pista: resolve primeiro o que está entre parênteses e escreve o resultado por baixo. Só depois aplica o operador que ficou de fora dos parênteses.

### Mais longe 2: O contrário de uma condição com E ou com OU (10 min)

A matéria está no fim da secção "Operador NÃO" do guia: troca-se o `E` por `OU`, ou o `OU` por `E`, e cada comparação pela sua contrária.

**a)** Uma encomenda é entregue pela carrinha da loja se a zona de entrega for a 1 ou a 2: `zona = 1 OU zona = 2`. Escreve, sem usar `NÃO`, a condição de uma encomenda que não é entregue pela carrinha.

**b)** Um artigo vai para a montra da papelaria se houver stock e se custar 5 euros ou menos: `stock > 0 E preco <= 5`, com o preço em euros, num número inteiro. Escreve, sem usar `NÃO`, a condição de um artigo que não vai para a montra.

**c)** Confirma as duas respostas com valores: na alínea a), com `zona` a valer 2 e a valer 3; na alínea b), com `stock` 7 e `preco` 3, com `stock` 0 e `preco` 3, e com `stock` 7 e `preco` 8. Em cada caso, a condição original e a tua têm de dar resultados opostos.

Pista: se na alínea a) escreveste `zona != 1 OU zona != 2`, calcula-a com a zona 2. Dá o contrário da original?

### Mais longe 3: Limites que a frase não diz (10 min)

A matéria está nas secções "Intervalos" e "Fronteiras e casos de teste" do guia.

**a)** Um código de artigo é válido se tiver quatro algarismos. Variável: `codigo`, um inteiro positivo. A frase não diz nenhum número. Descobre os dois limites e explica numa frase como chegaste a eles.

**b)** Escreve a condição de código válido e os seis casos de teste, cada um com o resultado da condição.

**c)** Volta à regra das compras da alínea d) do exercício 3. Há quatro respostas possíveis à tua pergunta, conforme o 10 e o 20 contem ou não. Para cada uma, escreve a condição que usarias.

Pista: na alínea a), qual é o menor número que se escreve com quatro algarismos? E o maior?

### Mais longe 4: Respostas em texto (15 min)

A matéria está no fim da secção "Operadores de comparação" do guia, que explica quando dois textos são iguais.

Um algoritmo pergunta "Tem cartão de cliente? (S/N)" e guarda a resposta na variável `cartao`, do tipo `texto`. Só são respostas válidas os textos `"S"` e `"N"`, exatamente assim, com maiúscula.

**a)** Calcula `cartao = "S"` para cada uma destas respostas: `"S"`, `"s"` e `"Sim"`.

**b)** Escreve a condição de uma resposta válida. Depois escreve, sem usar `NÃO`, a condição de uma resposta inválida.

**c)** Calcula a tua condição de resposta inválida para `"S"`, `"N"`, `"s"` e `"X"`.

**d)** A papelaria dá desconto a quem tiver cartão de cliente ou a quem comprar pelo menos 20 unidades do mesmo artigo. Escreve a condição de desconto, com as variáveis `cartao` e `quantidade`, e calcula-a para estes quatro casos: 19 unidades com `"N"`, 20 com `"N"`, 19 com `"S"` e 20 com `"S"`.

Pista: na alínea b), uma resposta é válida se for `"S"` ou se for `"N"`. A inválida é o contrário, e o contrário de um `OU` é um `E`, com cada comparação trocada pela sua contrária.

### Mais longe 5: Quatro versões do mesmo algoritmo (30 min)

A matéria está nas secções "Fronteiras e casos de teste" e "Erros comuns" do guia.

> Uma loja online de material escolar cobra portes de envio às encomendas de valor inferior a 5000 cêntimos. A partir de 5000 cêntimos, inclusive, os portes são grátis. O valor da encomenda é um número inteiro de cêntimos e tem de ser maior do que zero; se não for, o algoritmo escreve "Valor inválido". As outras duas mensagens são "Paga portes" e "Portes grátis".

Quatro alunos escreveram quatro versões do algoritmo. Pode haver versões certas e versões erradas. As versões são diferentes só na seleção. Todas começam e acabam assim:

```text
ALGORITMO PortesDeEnvio
CONSTANTES
    LIMITE_PORTES_GRATIS ← 5000
VARIÁVEIS
    valor: inteiro
INÍCIO
    ESCREVER "Valor da encomenda em cêntimos?"
    LER valor
    (aqui entra a seleção de cada versão)
FIM
```

Versão A:

```text
    SE valor < 0 ENTÃO
        ESCREVER "Valor inválido"
    SENÃO SE valor < LIMITE_PORTES_GRATIS ENTÃO
        ESCREVER "Paga portes"
    SENÃO
        ESCREVER "Portes grátis"
    FIM SE
```

Versão B:

```text
    SE valor <= 0 ENTÃO
        ESCREVER "Valor inválido"
    SENÃO SE valor < LIMITE_PORTES_GRATIS ENTÃO
        ESCREVER "Paga portes"
    SENÃO SE valor > LIMITE_PORTES_GRATIS ENTÃO
        ESCREVER "Portes grátis"
    FIM SE
```

Versão C:

```text
    SE valor >= LIMITE_PORTES_GRATIS ENTÃO
        ESCREVER "Portes grátis"
    SENÃO SE valor <= 0 ENTÃO
        ESCREVER "Valor inválido"
    SENÃO
        ESCREVER "Paga portes"
    FIM SE
```

Versão D:

```text
    SE valor <= 0 ENTÃO
        ESCREVER "Valor inválido"
    SENÃO SE NÃO (valor > LIMITE_PORTES_GRATIS) ENTÃO
        ESCREVER "Paga portes"
    SENÃO
        ESCREVER "Portes grátis"
    FIM SE
```

**a)** Antes de olhares com atenção para as versões, constrói a tabela de casos esperados deste problema, a partir do enunciado, com os valores abaixo, no e acima de cada limite.

**b)** Faz o trace de cada versão com os casos da tua tabela. Para cada versão, diz se está certa ou errada. Se estiver errada, indica uma entrada que o mostre, o que a versão escreve com essa entrada e o que devia escrever, e qual é a condição responsável. Se achares que está certa, diz com que casos a testaste.

**c)** Uma das versões não segue o conselho do guia de pôr a validação em primeiro lugar. Está errada por causa disso? Justifica com os casos que testaste, e explica porque é que o conselho do guia continua a ser bom.

Pista: não tentes adivinhar o erro a olhar para o código. Faz o trace de cada versão com todos os casos da tua tabela e compara o resultado com o esperado, linha a linha. Uma versão sem `SENÃO` no fim pode não escrever nada para alguns valores. Para a versão D, escreve a condição do `NÃO` sem o `NÃO`, com a tabela dos contrários do guia, e compara-a com a que devia estar lá.

## Critérios de conclusão

- [ ] Calculei cada condição com os valores substituídos e as contas à vista.
- [ ] Nas condições com `E` e com `OU`, calculei cada parte antes de as juntar.
- [ ] Escrevi os intervalos com `E` e as condições de recusa com `OU`, com cada extremo incluído ou excluído conforme a regra.
- [ ] Assinalei a regra ambígua em vez de adivinhar os extremos.
- [ ] Construí a reta, a árvore de casos e a tabela de casos esperados antes de escrever o pseudocódigo.
- [ ] A minha tabela tem casos abaixo, no e acima de cada limite, e pelo menos um caso por cada ponta da árvore.
- [ ] Pus a validação antes de usar os valores.
- [ ] O fluxograma do exercício 5 tem os losangos com `Sim` e `Não`, e os ramos juntam-se antes do fim.
- [ ] Cada caso da minha tabela chegou, por um só caminho, à mensagem esperada.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
