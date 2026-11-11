![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Testar, depurar e melhorar

Praticas a escolher casos de teste antes de ver o algoritmo e a depurar com método. Melhoras um algoritmo sem mudar o que ele faz, e escreves e usas funções. Os exercícios 1 a 7 são obrigatórios, e o 8, o contrato do exercício 4, é opcional. Resolves em papel, com os algoritmos em pseudocódigo ou em frases claras que não deixem dúvidas. Para rever: o [guia do tema](../05-testar-depurar-e-melhorar.md).

## Exercício 1: Escolher os casos antes de ver o algoritmo

A loja de informática marca cada artigo do armazém conforme a quantidade que tem em stock. Com menos de 5 unidades, o artigo fica marcado "Encomendar". Com 5 unidades ou mais, fica marcado "Stock suficiente". Uma quantidade negativa é um erro de contagem, e o algoritmo escreve "Quantidade inválida".

**a)** Sem olhares para o algoritmo que está mais abaixo, escreve a tabela de casos esperados deste problema. Usa as colunas do guia: número, tipo, quantidade, resultado esperado e razão da escolha. Tem de ter pelo menos sete casos: um normal, os três casos do limite das 5 unidades e os três do limite da validação.

**b)** Agora lê o algoritmo e executa-o com cada um dos teus casos. Não precisas do trace linha a linha: basta seguir a cadeia e anotar a primeira condição que dá verdadeiro, ou o `Senão`, se nenhuma der. Junta à tabela o resultado obtido e se o teste passou.

```text
const LIMITE_ENCOMENDA = 5
Escreve: "Quantidade em stock? "
int quantidade = ler valor
Se quantidade <= 0
    Escreve: "Quantidade inválida"
Senão se quantidade < LIMITE_ENCOMENDA
    Escreve: "Encomendar"
Senão
    Escreve: "Stock suficiente"
```

**c)** Que caso da tua tabela revelou o erro? Se a tabela só tivesse casos normais, como 2 e 12, o erro teria aparecido? Explica porquê numa ou duas frases.

Rever: [Casos normais, de fronteira e inválidos](../05-testar-depurar-e-melhorar.md#casos-normais-de-fronteira-e-inválidos) e [A tabela de casos esperados](../05-testar-depurar-e-melhorar.md#a-tabela-de-casos-esperados).

<details>
<summary>Pista</summary>

Desenha a reta dos valores inteiros, de -2 a 8, e marca por cima de cada região a resposta que o enunciado dá. O limite da validação é a menor quantidade válida, e o enunciado diz que quantidades são erros de contagem. Na alínea c), pergunta-te se o 2 e o 12 estão perto do sítio onde o algoritmo e o enunciado discordam.

</details>

## Exercício 2: Depurar com método

No armazém da loja, o funcionário regista as entregas do dia. Escreve primeiro quantas entregas houve e depois, para cada entrega, o número de caixas que ela trouxe. O algoritmo deve mostrar o total de caixas recebidas no dia e quantas entregas foram grandes, isto é, de 10 ou mais caixas.

```text
const ENTREGA_GRANDE = 10
Escreve: "Quantas entregas houve hoje? "
int numeroEntregas = ler valor
int totalCaixas = 0
int grandes = 0
Para entrega de 1 até numeroEntregas
    Escreve: "Caixas da entrega ", entrega, "? "
    int caixas = ler valor
    totalCaixas = caixas
    Se caixas >= ENTREGA_GRANDE
        grandes = grandes + 1
Escreve: "Total de caixas: ", totalCaixas
Escreve: "Entregas grandes: ", grandes
```

O erro foi observado assim: na segunda-feira houve 2 entregas, a primeira de 12 caixas e a segunda de 4. O algoritmo escreveu "Total de caixas: 4" e "Entregas grandes: 1". O responsável do armazém contou 16 caixas.

As cinco alíneas são os cinco passos do método, pela ordem do guia, e cada resposta dá uma linha do registo de depuração. Na linha da verificação, escreve só o que a tabela mostrou.

**a)** Observar o erro. Para cada uma das duas saídas, escreve o resultado esperado e o obtido, e diz qual está errada.

**b)** Formular uma hipótese. Escreve, numa frase que possa ser verdadeira ou falsa, o que achas que causa o erro.

**c)** Verificar com o trace. Faz a tabela de iterações do caso de segunda-feira, com colunas para `entrega`, `caixas`, `totalCaixas` e `grandes` e para a condição escondida do `Para`, `entrega <= numeroEntregas`. Na coluna do que acontece durante a iteração, escreve cada atribuição a `totalCaixas` com o valor que ela dá. Diz se a tabela confirma a tua hipótese e, se não confirmar, escreve outra. No fim, diz que instrução causa o erro.

**d)** Corrigir a causa. Corrige o algoritmo mudando uma só instrução, e diz qual foi. Podes escrever o algoritmo corrigido ou descrever a alteração numa frase, desde que se perceba que linha muda e como.

**e)** Voltar a testar tudo. O responsável do armazém já tinha escrito estes casos de teste. Executa a tua versão corrigida com os três, diz se cada um passa e escreve a linha do novo teste.

| Caso | Entregas do dia | Resultado esperado |
| ---: | --- | --- |
| 1 | 2 entregas, de 12 e de 4 caixas | Total 16, grandes 1 |
| 2 | 0 entregas | Total 0, grandes 0 |
| 3 | 1 entrega, de 10 caixas | Total 10, grandes 1 |

Rever: [Depurar com método](../05-testar-depurar-e-melhorar.md#depurar-com-método), [O registo de depuração](../05-testar-depurar-e-melhorar.md#o-registo-de-depuração) e, no guia 04, [Padrão totalizador](../04-repeticao-e-padroes.md#padrão-totalizador).

<details>
<summary>Pista</summary>

Compara o total obtido, 4, com as caixas de cada entrega. A que entrega corresponde o 4? Isso diz-te o que o totalizador está a fazer. Antes de escreveres a hipótese, lê todas as linhas que mexem em `totalCaixas`, e não só a primeira. Na tabela de iterações, escreve em cada atribuição o valor que `totalCaixas` tinha antes e o que fica depois. Na alínea e), quantas vezes se executa o corpo do `Para` no caso 2?

</details>

## Exercício 3: Contar passos e melhorar sem mudar o resultado

A loja separa as encomendas por peso, para escolher a caixa de envio. Até 999 gramas, a encomenda é leve. De 1000 a 4999 gramas, é média. De 5000 gramas para cima, é pesada. O funcionário escreve o peso de cada encomenda, em gramas, e escreve 0 quando acabar. Os pesos escritos são sempre positivos, e por isso não há validação. Este algoritmo já passou em todos os testes da loja:

```text
const LIMITE_LEVE = 1000
const LIMITE_PESADO = 5000
const SENTINELA = 0
int leves = 0
int medias = 0
int pesadas = 0
Escreve: "Peso da encomenda em gramas (0 para terminar)? "
int peso = ler valor
Enquanto peso != SENTINELA
    Se peso < LIMITE_LEVE
        leves = leves + 1
    Se peso >= LIMITE_LEVE e peso < LIMITE_PESADO
        medias = medias + 1
    Se peso >= LIMITE_PESADO
        pesadas = pesadas + 1
    Escreve: "Peso da encomenda em gramas (0 para terminar)? "
    peso = ler valor
Escreve: "Leves: ", leves
Escreve: "Médias: ", medias
Escreve: "Pesadas: ", pesadas
```

Os passos contam-se com a regra do guia. Conta um passo por cada `Escreve:` e por cada atribuição, incluindo as leituras e as linhas onde uma variável nasce com valor. Conta também um por cada condição avaliada, incluindo a última do `Enquanto`. Não contam as linhas `const` nem o `Senão`.

**a)** Conta os passos do algoritmo para os pesos 500 e 7000, seguidos de 0. Conta por partes, nesta tabela, que já tem a primeira linha, e no fim soma:

| Parte | Passos |
| --- | ---: |
| Antes do ciclo: as três atribuições, o `Escreve:` e a leitura | 5 |
| Cada iteração | |
| A última avaliação da condição | |
| Depois do ciclo | |

**b)** Em cada iteração, o algoritmo avalia sempre as três condições, mas para um mesmo peso só uma delas pode ser verdadeira. Escreve uma versão melhorada em que as três perguntas formam uma só cadeia, com `Senão se` e `Senão`. Basta escreveres a cadeia que substitui os três `Se`.

**c)** Conta os passos da tua versão para o mesmo caso da alínea a), com a mesma regra e a mesma tabela de partes. Calcula a diferença.

**d)** Explica porque é que a tua versão escreve sempre o mesmo que a original, para qualquer peso positivo.

Rever: [Contar passos](../05-testar-depurar-e-melhorar.md#contar-passos), [Melhorar um algoritmo sem mudar o que ele faz](../05-testar-depurar-e-melhorar.md#melhorar-um-algoritmo-sem-mudar-o-que-ele-faz) e, no guia 03, [Seleção encadeada](../03-decisoes-e-validacao.md#seleção-encadeada).

<details>
<summary>Pista</summary>

Na alínea a), em cada iteração, conta quantas condições se avaliam e quantas atualizações se fazem. Na alínea b), quando o algoritmo chega à segunda condição da cadeia, o que é que já sabe sobre o peso? Numa cadeia, o `Senão se` e o `Senão` ficam à mesma distância da margem que o primeiro `Se`.

</details>

## Exercício 4: Construir um algoritmo pequeno a partir dos casos de teste

O cartão de cliente da papelaria dá pontos. Por cada compra, o cliente ganha 1 ponto por cada 100 cêntimos completos que gastou. Uma compra de 250 cêntimos dá 2 pontos, e uma de 99 cêntimos não dá nenhum. Uma compra de 2000 cêntimos ou mais ganha ainda 10 pontos de bónus. No fim do dia, a funcionária escreve o valor de cada compra feita com cartão, em cêntimos, uma a uma, e escreve 0 quando acabar. Os valores escritos são sempre positivos, e por isso neste exercício não há validação. No fim, o algoritmo mostra o total de pontos atribuídos no dia.

**a)** Antes de escreveres o algoritmo, escreve a tabela de casos esperados, com as colunas do guia. Tem de ter pelo menos três casos: um normal, um dia sem compras e um com o limite do bónus e o valor logo abaixo. Esses dois valores podem estar no mesmo dia ou em dias separados. Cada caso é uma sequência de valores, terminada no 0 que marca o fim do dia.

**b)** Escreve o algoritmo. Em pseudocódigo, usa a constante `SENTINELA` e uma constante para cada valor fixo: os 100 cêntimos, os 2000 cêntimos e os 10 pontos de bónus.

**c)** Testa o teu algoritmo. Faz a tabela de iterações do teu caso normal e executa os outros casos da tua tabela. Acrescenta-lhe o resultado obtido e se o teste passou. Se algum caso falhar, corrige o algoritmo com o método do guia, guarda as duas versões e volta a executar a tabela inteira.

Rever: [A tabela de casos esperados](../05-testar-depurar-e-melhorar.md#a-tabela-de-casos-esperados), [Depurar com método](../05-testar-depurar-e-melhorar.md#depurar-com-método), no guia 02, [`div` e `resto`](../02-pseudocodigo.md#div-e-resto), e, no guia 04, [Padrão totalizador](../04-repeticao-e-padroes.md#padrão-totalizador) e [Padrão sentinela](../04-repeticao-e-padroes.md#padrão-sentinela).

<details>
<summary>Pista</summary>

Decompõe antes de escrever. É preciso ler valores até ao 0 e, para cada compra, somar os pontos da compra e decidir o bónus. A estrutura é a do exemplo do inventário: a inicialização do total, a leitura antecipada, o ciclo e a leitura no fim do corpo. Os pontos de uma compra calculam-se com uma operação do guia 02 que dá o número de vezes que 100 cabe no valor. Na tabela, calcula os pontos de cada compra em duas partes: os pontos normais e o bónus, se o houver.

</details>

## Exercício 5: Ler uma função e as suas chamadas

A loja online da papelaria escreve, para cada encomenda, o valor e os portes. As encomendas acima de 3000 cêntimos não pagam portes, e as outras pagam 400 cêntimos.

```text
const LIMITE_GRATIS = 3000
const PORTES = 400

Função mostraPortes(numero, valorEncomenda)
    Escreve: "Encomenda ", numero, ": ", valorEncomenda, " cêntimos"
    Se valorEncomenda > LIMITE_GRATIS
        Escreve: "Portes grátis"
    Senão
        Escreve: "Portes: ", PORTES, " cêntimos"

int valorPrimeira = 3500
mostraPortes(1, valorPrimeira)
mostraPortes(2, 2999)
mostraPortes(3, 3000)
```

**a)** Sem fazeres o trace completo, escreve o ecrã que este algoritmo produz, linha a linha, pela ordem em que as linhas aparecem.

**b)** Faz a tabela da chamada `mostraPortes(2, 2999)`, como a tabela da chamada 2 do guia, com uma linha por cada instrução executada. A primeira linha já está feita:

| Passo | Instrução executada | numero | valorEncomenda | Condição e resultado | Ecrã |
| ---: | --- | ---: | ---: | --- | --- |
| 0 | os argumentos passam para os parâmetros | 2 | 2999 | nenhuma | nada |

Rever: [Chamar uma função](../05-testar-depurar-e-melhorar.md#chamar-uma-função), [Parâmetros e argumentos](../05-testar-depurar-e-melhorar.md#parâmetros-e-argumentos), [O que acontece numa chamada](../05-testar-depurar-e-melhorar.md#o-que-acontece-numa-chamada) e [O trace de uma chamada](../05-testar-depurar-e-melhorar.md#o-trace-de-uma-chamada).

<details>
<summary>Pista</summary>

Faz as chamadas uma de cada vez e, antes de cada uma, escreve que valor recebe cada parâmetro. Na chamada 1, o argumento é uma variável, e o que passa para a função é o valor dela. Na chamada 3, o valor é exatamente o do limite, por isso lê o sinal da condição com atenção. Na alínea b), o `Senão` não avalia nenhuma condição, e por isso não tem linha própria na tabela.

</details>

## Exercício 6: Escrever uma função a partir do contrato

A escola organiza uma visita de estudo para várias turmas. Cada turma vai num autocarro de 50 lugares, e a visita de uma turma só se confirma se houver pelo menos 15 alunos inscritos. Para cada turma, escreve-se uma linha com o número de inscritos e outra com a decisão. Este é o contrato da função que faz esse trabalho:

- recebe: o nome da turma, um texto como `"10A"`, e o número de inscritos, um inteiro igual ou maior do que zero, por esta ordem;
- escreve: uma linha como "Turma 10C: 23 inscritos" e, numa segunda linha, a decisão. A decisão é "Visita confirmada" se a turma tiver pelo menos 15 inscritos e não mais do que os 50 lugares do autocarro. Nos outros casos, é "Visita por confirmar";
- exemplo: `mostraVisita("10C", 23)` escreve "Turma 10C: 23 inscritos" e "Visita confirmada".

**a)** Escreve a função `mostraVisita(turma, inscritos)`. Usa uma constante para o mínimo de inscritos e outra para os lugares do autocarro, escritas antes da função.

**b)** Escreve o algoritmo principal, que chama a função para três turmas. São a 10A, com 14 inscritos, a 10B, com 50, e a 10D, com 15.

**c)** Escreve o ecrã que o teu algoritmo produz, com as linhas das três chamadas.

Rever: [Escrever uma função](../05-testar-depurar-e-melhorar.md#escrever-uma-função), [Parâmetros e argumentos](../05-testar-depurar-e-melhorar.md#parâmetros-e-argumentos), [Testar uma função sozinha](../05-testar-depurar-e-melhorar.md#testar-uma-função-sozinha) e, no guia 03, [Intervalos](../03-decisoes-e-validacao.md#intervalos).

<details>
<summary>Pista</summary>

O cabeçalho já está no enunciado. A primeira linha do corpo é um `Escreve:` com várias partes, como o de `mostraStock` no guia. Para a segunda, decide, a partir das palavras do contrato, se 15 e 50 ficam dentro ou fora do intervalo. Na alínea c), duas das três turmas estão em cima de um limite.

</details>

## Exercício 7: Trocar a repetição por uma função

No fim do dia, o bar da escola vê o que ficou por vender de três produtos. Pede mais quando um deles fica abaixo do seu mínimo. O algoritmo do bar está certo, mas tem a mesma parte escrita três vezes:

```text
const MINIMO_SANDES = 5
const MINIMO_SUMOS = 12
const MINIMO_FRUTA = 8
Escreve: "Sandes por vender? "
int sandes = ler valor
Escreve: "Sumos por vender? "
int sumos = ler valor
Escreve: "Peças de fruta por vender? "
int fruta = ler valor
Escreve: "Restam ", sandes, " sandes"
Se sandes < MINIMO_SANDES
    Escreve: "Pedir mais sandes"
Escreve: "Restam ", sumos, " sumos"
Se sumos < MINIMO_SUMOS
    Escreve: "Pedir mais sumos"
Escreve: "Restam ", fruta, " peças de fruta"
Se fruta < MINIMO_FRUTA
    Escreve: "Pedir mais peças de fruta"
```

**a)** Compara os três blocos do fim, linha a linha, e escreve numa frase tudo o que muda de um bloco para o outro.

**b)** Escreve uma função que faz o trabalho de um bloco, e as três chamadas que substituem os três blocos. As constantes e as seis primeiras linhas do algoritmo principal ficam como estão.

**c)** Mostra que a tua versão escreve o mesmo que a original. Usa um dia em que ficaram 5 sandes, 11 sumos e 7 peças de fruta. Escreve as linhas que cada versão escreve depois das três perguntas, e confirma que são iguais.

Rever: [Funções: dar nome a uma parte do algoritmo](../05-testar-depurar-e-melhorar.md#funções-dar-nome-a-uma-parte-do-algoritmo) e [Trocar uma repetição por uma função](../05-testar-depurar-e-melhorar.md#trocar-uma-repetição-por-uma-função).

<details>
<summary>Pista</summary>

Na alínea a), sublinha em cada bloco tudo o que não é igual nos três. Cada coisa sublinhada vai ser um parâmetro. Na alínea b), repara que o texto `" sandes"` tem um espaço antes da palavra. Na função, o espaço fica escrito num texto, e a palavra vem de um parâmetro.

</details>

## Exercício 8: O contrato do exercício 4

Este exercício é opcional. No exercício 4, o enunciado fez de contrato. Escreve agora o contrato do problema, com as respostas às quatro perguntas do guia 01: entradas, saídas, restrições e condições. Se ficar alguma ambiguidade por decidir, escreve a decisão que tomaste e acerta a tabela de casos.

Rever, no guia 01, [O contrato do problema](../01-do-problema-ao-algoritmo.md#o-contrato-do-problema-entradas-saídas-restrições-e-condições).

## Desafios

### Desafio 1: Uma restrição nova

Volta ao exercício 4, com todos os testes a passar. As compras acima de 50000 cêntimos passam a ser registadas à mão. O algoritmo escreve "Valor acima do limite" e não lhes dá pontos.

Antes de mexer no algoritmo:

**a)** Diz que casos da tua tabela mudam de resultado esperado.

**b)** Diz que casos novos são precisos, e porquê.

Só depois:

**c)** Altera o algoritmo e diz quantas linhas mudaram.

**d)** Executa a tabela inteira na versão alterada.

### Desafio 2: O caso mínimo e a correção do sintoma

**a)** Executa a versão original do algoritmo das entregas, a do enunciado do exercício 2, com uma só entrega, de 12 caixas. O erro aparece? Explica porquê, e diz qual é o caso mais pequeno que ainda mostra o erro no total.

**b)** Um colega propôs outra correção: deixar o ciclo como está e trocar o penúltimo `Escreve:` por `Escreve: "Total de caixas: ", totalCaixas * numeroEntregas`. Encontra um caso em que a proposta dá o total certo e outro em que dá o total errado. Explica, com as palavras causa e sintoma, porque é que esta proposta não corrige o erro.

Rever: [Corrigir a causa e não o sintoma](../05-testar-depurar-e-melhorar.md#corrigir-a-causa-e-não-o-sintoma).

<details>
<summary>Pista</summary>

Na alínea b), calcula o que a proposta escreve em vários dias diferentes, e repara em quais acerta.

</details>

### Desafio 3: Quanto se poupa em cada escalão

**a)** Conta os passos de uma iteração com uma encomenda média, por exemplo de 1000 gramas, na versão original do exercício 3 e na tua.

**b)** Diz quantos passos a tua versão poupa por cada encomenda leve, por cada média e por cada pesada. Explica porque é que não poupa o mesmo nas três.

**c)** Mostra a equivalência também pelos testes. Escreve uma tabela de casos com os dois lados de cada fronteira (999 e 1000, 4999 e 5000) e um dia sem encomendas. Executa-a nas duas versões.

<details>
<summary>Pista</summary>

Na alínea b), conta quantas condições a tua cadeia avalia até chegar à atualização de cada escalão.

</details>

### Desafio 4: Dois erros em funções

Cada um destes algoritmos tem um erro. Para cada um, diz o que o algoritmo escreve, qual é a linha com o erro e porquê, e corrige-o.

**a)** A funcionária quer registar uma venda de 5 borrachas e ver quantas ficam.

```text
Função registaVenda(stock, vendidos)
    stock = stock - vendidos
    Escreve: "Vendidos: ", vendidos

int borrachas = 12
registaVenda(borrachas, 5)
Escreve: "Borrachas em stock: ", borrachas
```

**b)** A lista das encomendas devia abrir com a linha "Encomendas do dia", uma só vez.

```text
const LIMITE_GRATIS = 3000
const PORTES = 400

Função mostraPortes(numero, valorEncomenda)
    Escreve: "Encomenda ", numero, ": ", valorEncomenda, " cêntimos"
    Se valorEncomenda > LIMITE_GRATIS
        Escreve: "Portes grátis"
    Senão
        Escreve: "Portes: ", PORTES, " cêntimos"
    Escreve: "Encomendas do dia"

mostraPortes(1, 3500)
mostraPortes(2, 2999)
```

Rever: [Escrever uma função](../05-testar-depurar-e-melhorar.md#escrever-uma-função) e [As variáveis da função são da função](../05-testar-depurar-e-melhorar.md#as-variáveis-da-função-são-da-função).

<details>
<summary>Pista</summary>

Na alínea a), que variáveis existem depois de a chamada acabar? Na alínea b), conta quantas vezes aparece "Encomendas do dia", e em que momentos.

</details>

## Critérios de conclusão

- Escrevi cada tabela de casos antes de ler ou de escrever o algoritmo.
- As minhas tabelas têm casos normais e os casos de cada limite pedido. Têm casos inválidos quando o enunciado os prevê e, num ciclo, o caso de zero voltas.
- O meu registo de depuração do exercício 2 tem os cinco passos. Deixa perceber o erro e a correção a quem não leu o resto.
- No exercício 3, contei os passos das duas versões com a mesma regra.
- Nos exercícios 3 e 7, mostrei que a versão nova escreve o mesmo que a original.
- Nos exercícios 6 e 7, as minhas chamadas têm os argumentos pela ordem dos parâmetros.
- No exercício 4, testei o meu algoritmo com a tabela inteira, e todos os casos passam.

![Rodapé](../../imagens/rodape.png)
