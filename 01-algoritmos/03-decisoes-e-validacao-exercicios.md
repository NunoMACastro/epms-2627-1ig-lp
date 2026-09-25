![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Decisões e validação

UC: UC00245

Blocos: ALG03

Requisitos: UC00245-R03, UC00245-R04, UC00245-K05, UC00245-K06, UC00245-A05, UC00245-A06, UC00245-C01, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG03, acompanha o [guia](03-decisoes-e-validacao.md) e o [laboratório](03-decisoes-e-validacao-laboratorio.md) |
| Tempo total | 120 minutos dos 300 do bloco: 90 de prática autónoma e 30 de desafio opcional |
| Entrega | As respostas escritas dos exercícios 1, 2, 4 e 5; do exercício 3, a reta, a árvore de casos, a tabela de casos esperados, o pseudocódigo, o fluxograma (ficheiro `.drawio` e imagem PNG) e os traces; o desafio, se o fizeres |

## Objetivos e conceitos necessários

Vais praticar a escrita de condições com comparações e com `E`, `OU` e `NÃO`, a tradução de regras dadas por palavras em intervalos, a validação de entradas, a construção da árvore de casos e da tabela de casos esperados, e a procura da entrada que revela um erro numa decisão.

Antes de começares, deves ter lido a teoria e o exemplo explicado do [guia](03-decisoes-e-validacao.md) e feito o [laboratório](03-decisoes-e-validacao-laboratorio.md). Tudo o que precisas para esta ficha está lá. Se encravares num conceito, volta à secção do guia com esse nome antes de olhares para o apoio.

Material: papel e lápis, e o diagrams.net, em `https://app.diagrams.net/?lang=pt`, para o exercício 3. Guarda os ficheiros na pasta `algoritmos` que usaste nos laboratórios, com nomes em minúsculas, com hífenes e sem acentos.

O único exemplo resolvido deste bloco é o do guia. Nenhum exercício desta ficha é o mesmo problema com outros números: cada um obriga-te a uma decisão que o exemplo não tomou. Resolve-os pela ordem, porque vão ficando mais difíceis. Os dois primeiros treinam peças soltas; o terceiro pede o percurso completo, da reta ao fluxograma; o quarto pede que encontres erros em algoritmos feitos por outros; o quinto junta duas condições independentes.

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Avaliar condições com `E`, `OU`, `NÃO` e parênteses; escrever contrários | 15 min |
| 2 | Passar regras dadas por palavras para intervalos, e assinalar ambiguidades | 15 min |
| 3 | Validar e decidir com um limite que é lido, da reta ao fluxograma | 30 min |
| 4 | Encontrar a entrada que revela o erro | 15 min |
| 5 | Juntar duas condições independentes e validar um texto | 15 min |
| Desafio opcional | Mudar uma regra de cada vez e ver o que muda | 30 min |

## Exercício 1: Avaliar condições (15 min)

Numa papelaria, num dado momento, as variáveis têm estes valores: `stock` vale 12, `quantidade` vale 12, `zona` vale 2 e `resposta` vale `"s"`, com um s minúsculo.

Para cada condição, escreve as comparações com os valores substituídos, o resultado de cada comparação e o resultado final, `VERDADEIRO` ou `FALSO`, como na coluna "Condição e resultado" do trace do guia.

**a)** `quantidade <= stock`

**b)** `quantidade < stock`

**c)** `quantidade > 0 E quantidade <= stock`

**d)** `quantidade > stock OU stock = 0`

**e)** `NÃO (quantidade <= stock)`

**f)** `resposta = "S"`

**g)** `(stock < 5 E quantidade > 10) OU resposta != "N"`

**h)** `stock < 5 E (quantidade > 10 OU resposta != "N")`

**i)** As condições g) e h) têm as mesmas três comparações, pela mesma ordem. Explica numa ou duas frases porque é que o resultado não é o mesmo.

**j)** Escreve o contrário de cada uma destas três condições, sem usar `NÃO`. Depois calcula cada contrário com os valores do início e confirma que dá o oposto da condição original.

1. `quantidade <= stock`
2. `stock >= 5 E stock <= 100`
3. `zona = 1 OU zona = 2`

Concluíste quando tiveres as oito condições calculadas com as contas à vista e os três contrários confirmados com os valores.

## Exercício 2: De palavras para condições (15 min)

Cada frase descreve uma regra de uma loja. Para as frases a) a d):

1. escreve a condição em pseudocódigo, com a variável indicada;
2. diz quais são os limites e se cada um está incluído ou excluído;
3. escreve os casos de teste abaixo, no e acima de cada limite, com a resposta que a condição deve dar em cada um.

**a)** Uma encomenda tem desconto de volume quando tem mais de 100 unidades. Variável: `unidades`.

**b)** Um código de artigo é válido se tiver quatro algarismos. Variável: `codigo`, um inteiro positivo.

**c)** O desconto de fim de época aplica-se aos artigos que estão em armazém há mais de 90 dias e há menos de 365. Variável: `dias`.

**d)** Uma quantidade é recusada quando não está entre 1 e 50, inclusive. Variável: `quantidade`. A condição que escreves é a de recusa.

**e)** Os clientes que fizeram entre 10 e 20 compras este ano recebem um vale de desconto. Variável: `compras`. Esta frase tem um problema que as outras não têm. Diz qual é, escreve a pergunta que farias a quem pediu o algoritmo, e escreve a condição que usarias para cada resposta possível a essa pergunta.

Concluíste quando cada condição tiver os seus casos de teste e tiveres justificado, na alínea b), como chegaste aos dois limites a partir de "quatro algarismos".

## Exercício 3: Aceitar um pedido por quantidade e capacidade (30 min)

> Um armazém de material escolar leva as encomendas às escolas numa carrinha. Antes de aceitar um pedido para a próxima viagem, o funcionário escreve quantas caixas ainda cabem na carrinha, a que se chama a capacidade livre, e quantas caixas tem o pedido. O pedido é aceite se tiver pelo menos 1 caixa e não ultrapassar a capacidade livre. Se o pedido tiver menos de 1 caixa, o algoritmo escreve "Quantidade inválida". Se ultrapassar a capacidade livre, escreve "Pedido recusado: não cabe na carrinha". Nos outros casos, escreve "Pedido aceite". Podes assumir que a capacidade livre escrita pelo funcionário é sempre um inteiro maior ou igual a zero.

O algoritmo lê primeiro a capacidade livre e depois a quantidade de caixas do pedido.

**a)** Escreve o contrato do problema, sem os exemplos concretos (entradas, saídas, restrições e condições), e o domínio de cada entrada.

**b)** Desenha a reta da quantidade de caixas para uma capacidade livre de 40, com as regiões e as fronteiras. Depois responde: se a capacidade livre fosse 25, que fronteira mudava de sítio, e qual ficava onde estava?

**c)** Constrói a árvore de casos e a tabela de casos esperados para uma capacidade livre de 40, com os valores abaixo, no e acima de cada limite. Acrescenta à tabela dois casos com a carrinha cheia, isto é, com capacidade livre 0: um pedido de 0 caixas e um pedido de 1 caixa.

**d)** Escreve o pseudocódigo. Usa uma constante para o número mínimo de caixas de um pedido.

**e)** Desenha o fluxograma no diagrams.net, guarda-o como `fluxograma-aceitar-pedido.drawio` e exporta-o em PNG. Segue com o dedo o caminho de cada caso da tua tabela, como no laboratório.

**f)** Faz o trace completo, instrução a instrução, de dois casos com capacidade livre 40: o pedido de 40 caixas e o pedido de 41 caixas. Para os restantes casos da tabela, faz uma tabela de resumo como a do passo 9 do guia, com o valor de cada condição, o ramo executado e o que aparece no ecrã.

Concluíste quando o resultado de todos os casos do trace coincidir com a tua tabela de casos esperados, e cada caso tiver um caminho, e um só, no teu fluxograma.

## Exercício 4: Encontrar a entrada que revela o erro (15 min)

> Uma loja online de material escolar cobra portes de envio às encomendas de valor inferior a 5000 cêntimos. A partir de 5000 cêntimos, inclusive, os portes são grátis. O valor da encomenda é um número inteiro de cêntimos e tem de ser maior do que zero; se não for, o algoritmo escreve "Valor inválido". As outras duas mensagens são "Paga portes" e "Portes grátis".

Quatro alunos escreveram quatro versões do algoritmo. As versões são diferentes só na seleção. Todas começam e acabam assim:

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

Concluíste quando tiveres uma conclusão para cada versão, apoiada numa entrada concreta e no trace dessa entrada.

## Exercício 5: Duas condições ao mesmo tempo (15 min)

> Uma papelaria dá desconto a quem tiver cartão de cliente ou a quem comprar pelo menos 20 unidades do mesmo artigo. O algoritmo lê a quantidade de unidades, que é um inteiro, e depois a resposta à pergunta "Tem cartão de cliente? (S/N)", que é um texto. A quantidade tem de estar entre 1 e 500, inclusive; se não estiver, o algoritmo escreve "Quantidade inválida". A resposta tem de ser exatamente "S" ou "N"; se não for, escreve "Resposta inválida". Se a quantidade e a resposta estiverem as duas erradas, basta a mensagem da quantidade. Se estiver tudo certo, o algoritmo escreve "Com desconto" ou "Sem desconto".

**a)** Escreve o domínio de cada uma das duas entradas.

**b)** Desenha a árvore de casos, com as perguntas pela ordem que o enunciado indica.

**c)** Escreve a condição de "Resposta inválida" e a condição de desconto, as duas sem usar `NÃO`.

**d)** Constrói a tabela de casos esperados. Tem de incluir: os valores abaixo, no e acima de cada limite da quantidade; as quatro combinações possíveis entre ter ou não ter cartão e comprar menos de 20 ou pelo menos 20 unidades; pelo menos uma resposta inválida; e um caso em que a quantidade e a resposta estão as duas erradas.

**e)** Escreve o pseudocódigo.

Concluíste quando a tua tabela tiver as quatro combinações do desconto e cada ponta da árvore tiver pelo menos um caso. O fluxograma deste exercício é opcional.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Calcula primeiro cada comparação sozinha e escreve o resultado por baixo. Só depois junta os resultados com o `E` ou o `OU`, com as tabelas de verdade do guia. Nas alíneas g) e h), resolve primeiro o que está entre parênteses. Na alínea j), a regra está na secção "Operador NÃO" do guia: troca-se o `E` por `OU`, ou o `OU` por `E`, e cada comparação pelo seu contrário.

**Exercício 2.** Para cada frase, desenha uma reta pequena e marca nela os valores que a frase aceita. Os operadores escolhem-se depois, olhando para os extremos: o extremo está dentro ou fora? Na alínea b), pensa qual é o menor número com quatro algarismos e qual é o maior. Na alínea e), volta à secção "Intervalos" do guia e à forma como o primeiro bloco trata as ambiguidades.

**Exercício 3.** Começa pela reta com a capacidade de 40, e só depois pensa no caso geral. Repara que as duas mensagens de recusa são diferentes: não podes juntá-las numa só condição com `OU`, como o exemplo do guia fez com as duas regiões inválidas. Quando fizeres a árvore, pergunta-te qual das duas recusas deve ser verificada primeiro. Depois testa com os casos da carrinha cheia: a tua cadeia dá o mesmo resultado se trocares a ordem das duas perguntas? A secção "Condições que não se sobrepõem" do guia ajuda a explicar a resposta.

**Exercício 4.** Não tentes adivinhar o erro a olhar para o código. Faz o trace de cada versão com todos os casos da tua tabela e compara o resultado com o esperado, linha a linha. Uma versão sem `SENÃO` no fim pode não escrever nada para alguns valores. Para a versão D, escreve a condição do `NÃO` sem o `NÃO`, com a regra do contrário de uma comparação, e compara-a com a que devia estar lá.

**Exercício 5.** A condição de desconto junta duas perguntas independentes, uma sobre o cartão e outra sobre a quantidade. Escreve a tabela de verdade dessas duas perguntas com casos concretos, como o guia faz na secção "Operador OU". Para a resposta inválida: uma resposta é válida se for "S" ou "N"; escreve essa condição e depois o seu contrário.

## Desafio opcional (30 min)

O desafio muda uma regra de cada vez ao exercício 3. Cada alínea parte do teu algoritmo do exercício 3, e não da alínea anterior. Em cada alínea, diz que linhas do teu pseudocódigo mudam e que casos da tua tabela de casos esperados mudam, saem ou entram.

**a)** O armazém deixa de aceitar pedidos pequenos: um pedido passa a ter de ter pelo menos 5 caixas. Um pedido com menos de 5 caixas continua a receber a mensagem "Quantidade inválida". Quantas linhas do teu pseudocódigo mudam? Que casos novos precisas? O que acontece a um pedido de 5 caixas quando a capacidade livre é 3?

**b)** A carrinha leva no máximo 60 caixas, e por isso a capacidade livre escrita pelo funcionário deixa de ser de confiança: tem de estar entre 0 e 60, inclusive. Se não estiver, o algoritmo escreve "Capacidade inválida" e não analisa o pedido. Onde entra esta nova condição na cadeia, e porquê? Encontra um par de valores, uma capacidade e uma quantidade, que mostre o que corre mal se a puseres no sítio errado. Se a capacidade e a quantidade estiverem as duas erradas, que mensagem escreve o teu algoritmo? Justifica a escolha.

**c)** O armazém passa a aceitar pedidos em parte: se o pedido não couber todo na carrinha, a carrinha leva as caixas que couberem e as outras ficam pendentes para a viagem seguinte. Nesse caso o algoritmo escreve "Aceite em parte: ", seguido do número de caixas que seguem, " caixas; ficam pendentes ", e do número de caixas que ficam. Escreve a nova versão e testa-a com a carrinha cheia, capacidade livre 0, e um pedido de 5 caixas. A mensagem faz sentido? Se não fizer, o que mudavas?

## Critérios de conclusão

- [ ] Calculei cada condição com os valores substituídos e as contas à vista.
- [ ] Escrevi os intervalos com `E` e os seus contrários com `OU`, com o limite do lado certo.
- [ ] Assinalei as regras ambíguas em vez de adivinhar os extremos.
- [ ] Construí a árvore de casos e a tabela de casos esperados antes de escrever o pseudocódigo.
- [ ] A minha tabela tem casos abaixo, no e acima de cada limite, e pelo menos um caso por cada ponta da árvore.
- [ ] Nas minhas seleções, nenhum valor cabe em dois ramos e nenhum valor fica sem ramo.
- [ ] Pus a validação antes de usar os valores.
- [ ] O fluxograma do exercício 3 tem os losangos com `Sim` e `Não`, e os ramos juntam-se antes do fim.
- [ ] Para cada versão errada do exercício 4, mostrei a entrada que revela o erro.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
