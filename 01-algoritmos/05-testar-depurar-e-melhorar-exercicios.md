![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Testar, depurar e melhorar

UC: UC00245

Blocos: ALG05

Requisitos: UC00245-R03, UC00245-R04, UC00245-R05, UC00245-A06, UC00245-A07, UC00245-A08, UC00245-C01, UC00245-C02, UC00245-C03, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG05, acompanha o [guia](05-testar-depurar-e-melhorar.md) |
| Tempo total | 60 minutos dos 300 do bloco, nos exercícios 1 a 4. O fecho do portefólio faz-se na última aula do bloco. O desafio e a secção "Para ires mais longe" são opcionais e ficam fora destes 60 minutos |
| Entrega | A tabela de casos do exercício 1, o registo de depuração do exercício 2, a contagem de passos do exercício 3 e o exercício 4, que ficam no teu portefólio, juntamente com o contrato e o fluxograma do fecho do portefólio |

## Objetivos e conceitos necessários

Vais praticar sozinho o que o guia deste bloco explica: escolher casos de teste antes de executar um algoritmo, encontrar um erro com o método de depuração, contar os passos de um algoritmo e melhorá-lo sem mudar o que ele faz, e, no fim, construir e testar um algoritmo pequeno.

Antes de começares, deves ter lido a teoria e o exemplo explicado do [guia](05-testar-depurar-e-melhorar.md), incluindo os passos 9 e 10 do exemplo, que mostram como se melhora um algoritmo e como se contam os passos. Também deves conseguir fazer uma tabela de iterações, escrever uma cadeia de `SE` e `SENÃO SE`, ler um `PARA` e um ciclo com sentinela, e usar contadores e totalizadores: está tudo nos guias 02, 03 e 04. Cada exercício diz em que secção do guia 05 está a matéria. Se encravares, volta a essa secção antes de olhares para o apoio.

Material: papel e lápis. O diagrams.net, em `https://app.diagrams.net`, só é preciso no fecho do portefólio.

## Como está organizada a ficha

Resolve os exercícios pela ordem. Nos dois primeiros aplicas o que o guia mostrou: no exercício 1 escolhes casos de teste e usas-os para testar um algoritmo curto, e no exercício 2 segues os cinco passos do método de depuração, um passo por alínea. No exercício 3 decides: contas os passos de um algoritmo que já está certo e escreves uma versão que faz menos trabalho. No exercício 4 constróis um algoritmo pequeno do princípio ao fim e testa-lo. Cada exercício treina uma coisa, e cada um usa o que os anteriores treinaram.

Nenhum exercício é o exemplo do inventário com outros números. O exemplo mostra o caminho, e os exercícios pedem-te que o percorras noutros problemas.

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Escolher casos de teste antes de ver o algoritmo, e testá-lo com eles | 10 min |
| 2 | Depurar com o método de cinco passos | 13 min |
| 3 | Contar passos e melhorar um algoritmo sem mudar o que ele faz | 12 min |
| 4 | Construir e testar um algoritmo pequeno | 25 min |
| Total da parte obrigatória | Exercícios 1 a 4 | 60 min |
| Fecho do portefólio | Contrato e fluxograma do exercício 4, na última aula do bloco | 20 min |
| Desafio opcional | Mudar uma restrição de cada vez no algoritmo do exercício 4 | na última aula, para quem não precisar de recuperação |
| Para ires mais longe | Opcional: mais uma fronteira no exercício 1, o caso mínimo e a correção do sintoma no exercício 2, a poupança de cada escalão no exercício 3 e a validação no exercício 4 | fora dos 60 min |

## Exercício 1: Escolher os casos antes de ver o algoritmo (10 min)

A matéria está nas secções "Casos normais, de fronteira e inválidos" e "A tabela de casos esperados" do guia.

A loja de informática marca cada artigo do armazém conforme a quantidade que tem em stock. Com menos de 5 unidades, o artigo fica marcado "Encomendar". Com 5 unidades ou mais, fica marcado "Stock suficiente". Uma quantidade negativa é um erro de contagem, e o algoritmo escreve "Quantidade inválida".

**a)** Sem olhares para o algoritmo que está mais abaixo, escreve a tabela de casos esperados deste problema, com as cinco colunas da tabela do guia: número, tipo, quantidade, resultado esperado e razão da escolha. Tem de ter pelo menos quatro casos: um caso normal, os dois lados da fronteira das 5 unidades e um caso inválido. Tapa o algoritmo com uma folha até acabares esta alínea: o exercício só funciona se a tabela for escrita a partir do enunciado.

**b)** Agora lê o algoritmo e executa-o com cada um dos teus casos. Não precisas do trace linha a linha: basta seguir a cadeia de condições e anotar a primeira que dá verdadeiro, ou o `SENÃO`, se nenhuma der. Acrescenta à tabela as colunas do resultado obtido e de se o teste passou.

```text
ALGORITMO MarcarStock
CONSTANTES
    LIMITE_ENCOMENDA ← 5
VARIÁVEIS
    quantidade: inteiro
INÍCIO
    ESCREVER "Quantidade em stock?"
    LER quantidade
    SE quantidade < 0 ENTÃO
        ESCREVER "Quantidade inválida"
    SENÃO SE quantidade <= LIMITE_ENCOMENDA ENTÃO
        ESCREVER "Encomendar"
    SENÃO
        ESCREVER "Stock suficiente"
    FIM SE
FIM
```

**c)** Que caso da tua tabela revelou o erro? Se a tabela só tivesse casos normais, como 2 e 12, o erro teria aparecido? Explica porquê numa ou duas frases.

Concluíste quando a tua tabela, escrita antes de leres o algoritmo, tiver um caso que falha, e conseguires explicar por que razão só esse caso o podia apanhar.

## Exercício 2: Depurar com método (13 min)

A matéria está nas secções "Depurar com método" e "Quatro erros que vais encontrar muitas vezes" do guia. O registo de depuração está no passo 11 do exemplo.

No armazém da loja, o funcionário regista as entregas do dia. Escreve primeiro quantas entregas houve e depois, para cada entrega, o número de caixas que ela trouxe. O algoritmo deve mostrar o total de caixas recebidas no dia e quantas entregas foram grandes, isto é, de 10 ou mais caixas.

```text
ALGORITMO EntregasDoDia
CONSTANTES
    ENTREGA_GRANDE ← 10
VARIÁVEIS
    numeroEntregas: inteiro
    entrega: inteiro
    caixas: inteiro
    totalCaixas: inteiro
    grandes: inteiro
INÍCIO
    ESCREVER "Quantas entregas houve hoje?"
    LER numeroEntregas
    grandes ← 0
    PARA entrega ← 1 ATÉ numeroEntregas FAZER
        totalCaixas ← 0
        ESCREVER "Caixas da entrega ", entrega, "?"
        LER caixas
        totalCaixas ← totalCaixas + caixas
        SE caixas >= ENTREGA_GRANDE ENTÃO
            grandes ← grandes + 1
        FIM SE
    FIM PARA
    ESCREVER "Total de caixas: ", totalCaixas
    ESCREVER "Entregas grandes: ", grandes
FIM
```

O erro foi observado assim: na segunda-feira houve 2 entregas, a primeira de 12 caixas e a segunda de 4. O algoritmo escreveu "Total de caixas: 4" e "Entregas grandes: 1". O responsável do armazém contou 16 caixas.

Cada alínea é um passo do método, pela ordem do guia, e a resposta a cada uma dá uma linha do registo de depuração do passo 11 do exemplo. Na linha da alínea c), basta escreveres o que a tabela de iterações mostrou. É esse registo que guardas no portefólio.

**a)** Observar o erro. Para cada uma das duas saídas, escreve o resultado esperado e o obtido, e diz qual está errada.

**b)** Formular uma hipótese. Escreve, numa frase que possa ser verdadeira ou falsa, o que achas que causa o erro.

**c)** Verificar com o trace. Faz a tabela de iterações do caso de segunda-feira, com colunas para `entrega`, `caixas`, `totalCaixas` e `grandes` e para a condição escondida do `PARA`, `entrega <= numeroEntregas`. Na coluna do que acontece durante a iteração, escreve cada atribuição a `totalCaixas` com o valor que ela dá. Diz se a tabela confirma a tua hipótese e qual é a instrução que causa o erro.

**d)** Corrigir a causa. Corrige o algoritmo com uma única alteração, e diz qual foi.

**e)** Voltar a testar tudo. O responsável do armazém já tinha escrito estes casos de teste, com o resultado esperado de cada um:

| Caso | Entregas do dia | Resultado esperado |
| ---: | --- | --- |
| 1 | 2 entregas, de 12 e de 4 caixas | Total 16, grandes 1 |
| 2 | 0 entregas | Total 0, grandes 0 |
| 3 | 1 entrega, de 10 caixas | Total 10, grandes 1 |

Executa a tua versão corrigida com os três casos e diz se cada um passa. Lembra-te de que um `PARA` de 1 até 0 não tem nenhuma iteração: é o caso zero do `PARA`.

Concluíste quando o teu registo de depuração permitir a outra pessoa perceber o erro e a correção sem ler o resto das tuas respostas.

## Exercício 3: Contar passos e melhorar sem mudar o resultado (12 min)

A matéria está nas secções "Contar passos" e "Estratégias simples para fazer menos passos" do guia, e nos passos 9 e 10 do exemplo.

A loja separa as encomendas por peso, para escolher a caixa de envio. Até 999 gramas, a encomenda é leve. De 1000 a 4999 gramas, é média. De 5000 gramas para cima, é pesada. O funcionário escreve o peso de cada encomenda, em gramas, e escreve 0 quando acabar. Os pesos escritos são sempre positivos, e por isso não há validação.

```text
ALGORITMO EscaloesDePeso
CONSTANTES
    LIMITE_LEVE ← 1000
    LIMITE_PESADO ← 5000
    SENTINELA ← 0
VARIÁVEIS
    peso: inteiro
    leves: inteiro
    medias: inteiro
    pesadas: inteiro
INÍCIO
    leves ← 0
    medias ← 0
    pesadas ← 0
    ESCREVER "Peso da encomenda em gramas (0 para terminar)?"
    LER peso
    ENQUANTO peso != SENTINELA FAZER
        SE peso < LIMITE_LEVE ENTÃO
            leves ← leves + 1
        FIM SE
        SE peso >= LIMITE_LEVE E peso < LIMITE_PESADO ENTÃO
            medias ← medias + 1
        FIM SE
        SE peso >= LIMITE_PESADO ENTÃO
            pesadas ← pesadas + 1
        FIM SE
        ESCREVER "Peso da encomenda em gramas (0 para terminar)?"
        LER peso
    FIM ENQUANTO
    ESCREVER "Leves: ", leves
    ESCREVER "Médias: ", medias
    ESCREVER "Pesadas: ", pesadas
FIM
```

Este algoritmo já passou em todos os testes da loja: está certo. Agora, e só agora, pergunta-se se faz trabalho desnecessário.

A regra de contagem do guia, para a teres à mão: conta um passo cada `LER`, cada `ESCREVER` e cada atribuição executados, e cada avaliação da condição de um `SE`, de um `SENÃO SE` ou de um `ENQUANTO`, incluindo a última avaliação do `ENQUANTO`, a que dá falso. `SENÃO`, `FIM SE` e `FIM ENQUANTO` não contam.

**a)** Conta os passos do algoritmo para os pesos 500 e 7000, seguidos de 0. Conta por partes, numa tabela como a do passo 10 do exemplo, com uma linha para cada parte: antes do ciclo, cada iteração, a última avaliação da condição do ciclo e depois do ciclo. No fim, soma.

**b)** Em cada iteração, o algoritmo avalia sempre as três condições, mas para um mesmo peso só uma delas pode ser verdadeira. Escreve uma versão melhorada em que as três perguntas formam uma só cadeia, com `SENÃO SE` e `SENÃO`, para o algoritmo não voltar a perguntar o que já sabe. Basta escreveres a cadeia que substitui os três `SE`, que é a única parte que muda.

**c)** Conta os passos da tua versão para o mesmo caso da alínea a), com a mesma regra e a mesma tabela de partes, e calcula a diferença.

**d)** Explica, numa ou duas frases, por que razão a tua versão escreve sempre o mesmo que a original, para qualquer peso positivo.

Concluíste quando tiveres as duas contagens, feitas com a mesma regra, e a explicação.

## Exercício 4: Construir e testar um algoritmo pequeno (25 min)

A matéria está nas secções "A tabela de casos esperados" e "A síntese: sequência, seleção e repetição" do guia, e nos padrões totalizador e sentinela do guia 04. É o exercício que mais se parece com a primeira parte da avaliação prática.

O cartão de cliente da papelaria dá pontos. Por cada compra, o cliente ganha 1 ponto por cada 100 cêntimos completos que gastou: uma compra de 250 cêntimos dá 2 pontos, e uma de 99 cêntimos não dá nenhum. Uma compra de 2000 cêntimos ou mais ganha ainda 10 pontos de bónus. No fim do dia, a funcionária escreve o valor de cada compra feita com cartão, em cêntimos, uma a uma, e escreve 0 quando acabar. Os valores escritos são sempre positivos, e por isso neste exercício não há validação. No fim, o algoritmo mostra o total de pontos atribuídos no dia.

**a)** Antes de escreveres o algoritmo, escreve a tabela de casos esperados, com as cinco colunas do guia. Tem de ter pelo menos três casos: um caso normal, os dois lados da fronteira do bónus e um dia sem compras. Cada caso é uma sequência de valores, terminada no 0 que marca o fim do dia.

**b)** Escreve o algoritmo em pseudocódigo, com uma constante para cada valor fixo do enunciado (os 100 cêntimos, os 2000 cêntimos e os 10 pontos de bónus) e com a constante `SENTINELA`.

**c)** Testa o algoritmo: faz a tabela de iterações do teu caso normal e executa os outros casos da tabela. Acrescenta à tabela as colunas do resultado obtido e de se o teste passou. Se algum caso falhar, corrige o algoritmo com o método do guia, guarda a versão com erro e a versão corrigida, e volta a executar a tabela inteira.

Concluíste quando tiveres a tabela escrita antes do algoritmo, o pseudocódigo e a tabela executada, com todos os casos a passar.

## Fecho do portefólio (última aula, 20 min)

Esta parte não é opcional, mas não conta para os 60 minutos da ficha: faz-se na última aula do bloco, a mesma do checkpoint, porque junta ao exercício 4 as duas peças que lhe faltam para ser o problema completo do teu portefólio. A secção "O teu portefólio" do guia diz como organizar a pasta.

**a)** Escreve o contrato do problema do exercício 4, com as respostas às quatro perguntas do guia 01: entradas, saídas, restrições e condições. Se encontrares alguma ambiguidade no enunciado, escreve a decisão que tomaste.

**b)** Desenha no diagrams.net o fluxograma do teu algoritmo do exercício 4, como aprendeste no laboratório do bloco 04. Guarda o ficheiro `.drawio` e exporta uma imagem PNG. Confirma, figura a figura, que o fluxograma diz exatamente o mesmo que o pseudocódigo.

Concluíste quando o portefólio tiver, para o problema do exercício 4, o enunciado com o contrato, o pseudocódigo, o fluxograma e a tabela de casos executada, e, ao lado, o registo de depuração do exercício 2.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só passa à seguinte se a anterior não tiver chegado.

**Exercício 1.** Desenha a reta dos valores inteiros, de -2 a 8, e marca por cima de cada troço a resposta que o enunciado dá. A fronteira das 5 unidades é o sítio onde a resposta muda de "Encomendar" para "Stock suficiente": testa o último valor de um lado e o primeiro do outro. Para saber de que lado fica o 5, relê o enunciado: "5 unidades ou mais". Na alínea c), pergunta-te se o 2 e o 12 estão perto do sítio onde o algoritmo e o enunciado discordam.

**Exercício 2.** Compara o total obtido, 4, com as caixas de cada entrega. A que entrega corresponde o 4? Isso diz-te o que o totalizador está a fazer. Para a hipótese, relê no guia a secção "Inicialização no sítio errado". Na tabela de iterações, olha para o que acontece a `totalCaixas` logo no início de cada iteração, e não só no momento do teste.

**Exercício 3.** Na alínea a), repara que cada iteração da versão dada avalia sempre os três `SE`, qualquer que seja o peso, e executa exatamente uma atualização: por isso todas as iterações têm o mesmo número de passos. Na alínea b), lembra-te da regra da cadeia de `SENÃO SE`: quando o algoritmo chega à segunda condição, o que é que já sabe sobre o peso? Na alínea c), o `SENÃO` não avalia nenhuma condição, e por isso uma encomenda leve e uma pesada já não fazem o mesmo número de passos.

**Exercício 4.** Decompõe antes de escrever: ler valores até ao 0 e, para cada compra, somar os pontos da compra e decidir o bónus. A estrutura é a do exemplo do inventário: inicialização do total, leitura antecipada, ciclo com sentinela e leitura no fim do corpo. Os pontos de uma compra calculam-se com uma operação do guia 02 que dá o número de vezes que 100 cabe no valor. Na tabela, calcula os pontos de uma compra de 1999 cêntimos e de uma de 2000: a diferença não é só de 1 ponto.

## Desafio opcional: mudar uma restrição de cada vez

Faz-se na última aula, por quem não precisar de recuperação. Volta ao exercício 4, já com todos os testes a passar e com o fluxograma do fecho do portefólio. Vais fazer três mudanças ao enunciado, uma de cada vez, e cada uma a partir da versão original, não da anterior.

1. O bónus passa a exigir compras de 2500 cêntimos ou mais.
2. Os pontos passam a ser 1 por cada 50 cêntimos completos, em vez de 100.
3. As compras acima de 50000 cêntimos passam a ter de ser registadas à mão: o algoritmo escreve "Valor acima do limite" e não lhes dá pontos.

Para cada mudança, e antes de mexer no algoritmo:

**a)** Diz que linhas da tua tabela de casos mudam de resultado esperado, e escreve os novos resultados.

**b)** Diz que casos novos são precisos, e porquê.

Só depois:

**c)** Altera o pseudocódigo e diz quantas linhas mudaram.

**d)** Diz que figuras do fluxograma mudam, e se é preciso acrescentar alguma.

**e)** Executa a tabela inteira na versão alterada.

No fim, compara as três mudanças: qual delas obrigou a acrescentar um ramo novo, e qual mudou mais resultados esperados sem mudar nenhuma estrutura? Escreve a tua conclusão em duas ou três frases.

## Para ires mais longe

Esta secção é opcional e fica fora dos 60 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e quer mais prática, ou para estudar em casa antes da avaliação. Cada exercício continua um dos exercícios obrigatórios com um passo a mais. Os tempos são indicativos.

### Mais longe 1: Corrigir e acrescentar uma fronteira (10 min)

Continua o exercício 1.

**a)** Corrige o algoritmo `MarcarStock` com uma única alteração e volta a executar a tua tabela inteira.

**b)** A loja acrescenta uma terceira marca: com 20 unidades ou mais, o artigo fica marcado "Excesso de stock". Sem escreveres o algoritmo, diz que casos novos a tua tabela precisa, com o resultado esperado de cada um.

Pista: na alínea b), apareceu uma fronteira nova. Quais são os dois valores que ficam um de cada lado dela?

### Mais longe 2: O caso mínimo e a correção do sintoma (10 min)

Continua o exercício 2. A matéria está nas secções "Depurar com método" e "Corrigir a causa e não o sintoma" do guia.

**a)** Executa a versão original de `EntregasDoDia` com uma só entrega, de 12 caixas. O erro aparece? Explica porquê, e diz qual é o caso mais pequeno que ainda mostra o erro no total.

**b)** Um colega propôs outra correção: deixar o ciclo como está e trocar o penúltimo `ESCREVER` por `ESCREVER "Total de caixas: ", totalCaixas * numeroEntregas`. Encontra um caso em que a proposta dele dá o total certo e outro em que dá o total errado. Explica, com as palavras causa e sintoma, por que razão esta proposta não corrige o erro.

Pista: na alínea b), experimenta um dia em que todas as entregas têm o mesmo número de caixas, e depois um em que não têm.

### Mais longe 3: Quanto se poupa em cada escalão (15 min)

Continua o exercício 3.

**a)** Conta os passos de uma iteração com uma encomenda média, por exemplo de 1000 gramas, na versão original e na tua.

**b)** Diz quantos passos a tua versão poupa por cada encomenda leve, por cada média e por cada pesada, e explica porque é que não poupa o mesmo nas três.

**c)** Mostra a equivalência também pelos testes: escreve uma tabela de casos com os dois lados de cada fronteira (999 e 1000, 4999 e 5000) e um dia sem encomendas, e executa-a nas duas versões.

Pista: na alínea b), conta quantas condições a tua cadeia avalia até chegar à atualização de cada escalão.

### Mais longe 4: Validar os valores do cartão (15 min)

Continua o exercício 4. A funcionária pode enganar-se a escrever: um valor negativo é um engano, e o algoritmo escreve "Valor inválido" e ignora-o, sem lhe dar pontos.

**a)** Antes de mexeres no algoritmo, acrescenta à tua tabela um caso com um valor negativo no meio de valores válidos, com o resultado esperado.

**b)** Altera o pseudocódigo do exercício 4 para fazer esta validação.

**c)** Executa a tabela inteira na versão nova.

Pista: a validação vem antes de tudo o resto dentro do ciclo. Os pontos e o bónus só se calculam para compras válidas, e por isso podem ficar dentro do `SENÃO` da validação, com o `SE` do bónus lá dentro.

## Critérios de conclusão

- [ ] Escrevi a tabela de casos do exercício 1 antes de ler o algoritmo.
- [ ] As minhas tabelas têm casos normais e os dois lados de cada fronteira pedida, casos inválidos quando o enunciado os prevê e, quando há um ciclo, o caso zero.
- [ ] O meu registo de depuração do exercício 2 tem as cinco linhas, uma por passo do método.
- [ ] Contei os passos das duas versões do exercício 3 com a mesma regra e expliquei por que razão escrevem o mesmo.
- [ ] No exercício 4, escrevi a tabela de casos antes do algoritmo e executei-a toda.
- [ ] No fecho do portefólio, o fluxograma do exercício 4 diz exatamente o mesmo que o pseudocódigo, figura a figura.
- [ ] Guardei no portefólio as versões com erro e as versões corrigidas, cada uma no seu ficheiro.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
