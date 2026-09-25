![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Testar, depurar e melhorar

UC: UC00245

Blocos: ALG05

Requisitos: UC00245-R03, UC00245-R04, UC00245-R05, UC00245-A06, UC00245-A07, UC00245-A08, UC00245-C01, UC00245-C02, UC00245-C03, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG05, acompanha o [guia](05-testar-depurar-e-melhorar.md) |
| Tempo total | 60 minutos dos 300 do bloco; o desafio opcional faz-se na última aula, por quem não precisar de recuperação |
| Entrega | A tabela de casos do exercício 1, o registo de depuração do exercício 2, a contagem de passos do exercício 3 e o problema completo do exercício 4, que ficam no teu portefólio |

## Objetivos e conceitos necessários

Vais praticar sozinho o que o guia deste bloco explica: escolher casos de teste antes de executar, encontrar um erro com método, corrigir a causa e não o sintoma, melhorar um algoritmo contando os passos, e, no último exercício, construir e testar um algoritmo completo de raiz.

Antes de começares, deves conseguir fazer um trace linha a linha e uma tabela de iterações, escrever uma cadeia de `SE` e `SENÃO SE`, usar `ENQUANTO` com sentinela e leitura antecipada, usar `PARA`, e usar contadores e totalizadores. Está tudo nos guias 02, 03 e 04. O método de teste e de depuração, as quatro famílias de erros, a regra de contagem de passos e as estratégias de melhoria estão no guia 05.

Material: papel e lápis, e a aplicação diagrams.net para o fluxograma do exercício 4.

Nenhum dos quatro exercícios repete o exemplo do inventário. Cada um obriga a uma decisão que o exemplo não tomou, e é essa decisão que está a ser treinada. Se ficares preso, usa a secção de apoio no fim, uma pista de cada vez.

## Exercício 1: Escolher os casos antes de ver o algoritmo (10 min)

A loja de informática classifica cada artigo do armazém pela quantidade em stock. Com menos de 5 unidades, o artigo fica em "Encomendar já". De 5 a 19 unidades, fica em "Stock normal". Com 20 ou mais unidades, fica em "Excesso de stock". Uma quantidade negativa é um erro de contagem, e o algoritmo escreve "Quantidade inválida".

**a)** Sem olhares para o algoritmo que está mais abaixo, escreve a tabela de casos esperados deste problema, com as cinco colunas do guia: número, tipo, quantidade, resultado esperado e razão da escolha. Tem de ter pelo menos dois casos normais, os dois lados de cada fronteira e pelo menos um caso inválido. Se estás a trabalhar sozinho, tapa o algoritmo com uma folha até acabares esta alínea: o exercício só funciona se a tabela for escrita a partir do enunciado.

**b)** Agora lê o algoritmo e executa-o com cada um dos teus casos. Não precisas do trace linha a linha: basta seguir a cadeia de condições e anotar qual é a primeira que dá verdadeiro. Acrescenta à tabela as colunas do resultado obtido e de se o teste passou.

```text
ALGORITMO ClassificarStock
CONSTANTES
    LIMITE_ENCOMENDA ← 5
    LIMITE_EXCESSO ← 20
VARIÁVEIS
    quantidade: inteiro
INÍCIO
    ESCREVER "Quantidade em stock?"
    LER quantidade
    SE quantidade < 0 ENTÃO
        ESCREVER "Quantidade inválida"
    SENÃO SE quantidade < LIMITE_ENCOMENDA ENTÃO
        ESCREVER "Encomendar já"
    SENÃO SE quantidade > LIMITE_EXCESSO ENTÃO
        ESCREVER "Excesso de stock"
    SENÃO
        ESCREVER "Stock normal"
    FIM SE
FIM
```

**c)** Que caso ou casos da tua tabela revelaram o erro? Se a tabela só tivesse as quantidades 2, 10 e 50, o erro teria aparecido? Explica porquê numa ou duas frases.

**d)** Corrige a causa com uma única alteração e volta a executar a tabela inteira.

Concluíste quando a tua tabela, escrita antes de leres o algoritmo, tiver um caso que falha, e conseguires explicar por que razão só um tipo de caso o podia apanhar.

## Exercício 2: Depurar com método (15 min)

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

O erro foi observado assim: na segunda-feira houve 3 entregas, de 4, 12 e 7 caixas. O algoritmo escreveu "Total de caixas: 7" e "Entregas grandes: 1". O responsável do armazém contou 23 caixas.

**a)** Para cada uma das duas saídas, escreve o resultado esperado e o obtido, e diz qual está errada.

**b)** Encontra o caso mínimo: o caso mais pequeno que ainda mostra o erro no total. Experimenta primeiro com uma só entrega e explica por que razão uma só entrega não chega para ver o erro.

**c)** Escreve uma hipótese sobre a causa, numa frase que possa ser verdadeira ou falsa.

**d)** Faz a tabela de iterações do caso de segunda-feira, como no guia 04, com colunas para `entrega`, `caixas`, `totalCaixas` e `grandes` e a condição escondida do `PARA`, `entrega <= numeroEntregas`. Na coluna do que acontece durante a iteração, escreve cada atribuição a `totalCaixas` com o valor que ela dá. Diz se a tabela confirma a tua hipótese e qual é a instrução que causa o erro.

**e)** Corrige a causa com uma única alteração.

**f)** Um colega propôs outra correção: deixar o ciclo como está e trocar o penúltimo `ESCREVER` por `ESCREVER "Total de caixas: ", totalCaixas * numeroEntregas`. Encontra um caso em que a proposta dele dá o total certo e outro em que dá o total errado. Explica, com as palavras causa e sintoma, por que razão esta proposta não corrige o erro.

**g)** Faz o teste de regressão da tua versão corrigida com uma tabela de pelo menos quatro casos, que tem de incluir um dia sem entregas e uma entrega de exatamente 10 caixas. Lembra-te de que um `PARA` de 1 até 0 tem zero iterações: é o caso zero do `PARA`. Depois responde: o que escrevia a versão original num dia sem entregas, e porquê?

**h)** Escreve o registo de depuração deste erro, com as cinco linhas do guia: erro observado, hipótese, verificação com o trace, correção e novo teste.

Concluíste quando o teu registo de depuração permitir a outra pessoa perceber o erro e a correção sem ler o resto das tuas respostas.

## Exercício 3: Contar passos e melhorar sem mudar o resultado (10 min)

A loja separa as encomendas por peso, para escolher a caixa de envio. Até 999 gramas, a encomenda é leve. De 1000 a 4999 gramas, é média. De 5000 gramas para cima, é pesada. O funcionário escreve o peso de cada encomenda, em gramas, e escreve 0 quando acabar. Neste exercício os pesos escritos são sempre positivos, e por isso não há validação.

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

**a)** Escreve uma tabela de casos esperados com os dois lados de cada fronteira e um dia sem encomendas. Executa o algoritmo com esses casos e confirma que está certo. Um algoritmo só se melhora depois de passar em todos os testes.

**b)** Conta os passos do algoritmo para os pesos 500, 1000 e 7000, seguidos de 0. Conta por partes, como no guia: antes do ciclo, cada iteração, a última avaliação da condição e depois do ciclo.

**c)** Em cada iteração, quantas condições são avaliadas? Para um mesmo peso, quantas delas podem ser verdadeiras ao mesmo tempo? O que é que estas duas respostas dizem sobre o trabalho que o algoritmo faz?

**d)** Escreve uma versão melhorada que não volte a perguntar o que já se sabe. A versão nova tem de escrever exatamente o mesmo que a original, para qualquer peso positivo.

**e)** Conta os passos da tua versão para o mesmo caso da alínea b) e calcula a diferença. Depois diz quantos passos a tua versão poupa por cada encomenda leve, por cada média e por cada pesada, e explica porque é que não poupa o mesmo nas três.

**f)** Mostra que as duas versões são equivalentes das duas maneiras que o guia explica: executando a tua tabela de casos na versão nova, e explicando por palavras por que razão a alteração não pode mudar nenhum resultado.

Concluíste quando tiveres as duas contagens, feitas com a mesma regra, e a explicação da equivalência.

## Exercício 4: Construir e testar um algoritmo completo (25 min)

Este exercício não tem nenhum exemplo parecido nos guias. É para construíres do princípio, e é o que mais se parece com a primeira parte da avaliação prática. Se não o acabares na aula, acaba-o antes da avaliação.

O cartão de cliente da papelaria dá pontos. Por cada compra, o cliente ganha 1 ponto por cada 100 cêntimos completos que gastou: uma compra de 250 cêntimos dá 2 pontos, e uma de 99 cêntimos não dá nenhum. Uma compra de 2000 cêntimos ou mais ganha ainda 10 pontos de bónus. No fim do dia, a funcionária escreve o valor de cada compra feita com cartão, em cêntimos, uma a uma, e escreve 0 quando acabar. Um valor negativo é um engano: o algoritmo escreve "Valor inválido" e ignora-o. No fim, o algoritmo mostra o número de compras válidas, o total de pontos atribuídos no dia e quantas compras receberam bónus.

**a)** Escreve o contrato: entradas, saídas, restrições e condições. Se encontrares alguma ambiguidade, escreve a decisão que tomaste.

**b)** Escreve a tabela de casos esperados, antes de escreveres o algoritmo. Tem de ter um caso normal, os dois lados da fronteira dos 100 cêntimos, os dois lados da fronteira do bónus, um valor inválido no meio de valores válidos e um dia sem compras.

**c)** Escreve o algoritmo em pseudocódigo, com constantes para os três valores fixos do enunciado e para a sentinela, como aprendeste no guia 04.

**d)** Desenha o fluxograma no diagrams.net, guarda o ficheiro `.drawio` e exporta uma imagem PNG. Confirma, figura a figura, que corresponde ao pseudocódigo.

**e)** Faz a tabela de iterações do teu caso normal, e executa os restantes casos da tabela. Acrescenta à tabela as colunas do resultado obtido e de se o teste passou.

**f)** Se algum caso falhar, depura com o método do guia e escreve o registo de depuração. Guarda a versão com o erro e a versão corrigida, cada uma no seu ficheiro. Se nenhum caso falhar, escreve numa frase qual dos teus casos te deu mais confiança e porquê.

Concluíste quando tiveres, para este problema, as cinco peças do portefólio: o problema com o contrato, o pseudocódigo, o fluxograma, os testes e, se houve, as correções.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só passa à seguinte se a anterior não tiver chegado.

**Exercício 1.** Desenha a reta dos valores inteiros, de -2 a 22, e marca por cima de cada troço a resposta que o enunciado dá. As fronteiras são os sítios onde a resposta muda: são três. Para cada uma, testa o último valor de um lado e o primeiro do outro. Na alínea c), compara o resultado do algoritmo com o do enunciado precisamente no valor onde os dois discordam, e pergunta-te se algum dos valores 2, 10 e 50 está perto desse sítio.

**Exercício 2.** Compara o total obtido, 7, com as caixas de cada entrega. A que entrega corresponde o 7? Isso diz-te o que o totalizador está a fazer. Para a hipótese, pensa no que o guia diz sobre onde se inicializa um totalizador. Na tabela de iterações, olha para o que acontece a `totalCaixas` logo no início de cada iteração, e não só no momento do teste. Na alínea f), experimenta um dia em que todas as entregas têm o mesmo número de caixas, e depois um em que não têm.

**Exercício 3.** Na alínea c), pega num peso leve e segue o algoritmo: depois de somar 1 a `leves`, o algoritmo ainda faz mais alguma pergunta? Alguma dessas perguntas pode dar verdadeiro? Na alínea d), lembra-te da regra da cadeia de `SENÃO SE`: quando o algoritmo chega à segunda condição, o que é que já sabe sobre o peso? Na alínea e), conta quantas condições a tua versão avalia para cada tipo de encomenda: o `SENÃO` não avalia nenhuma.

**Exercício 4.** Decompõe antes de escrever: ler valores até ao 0, separar os inválidos, e, para cada compra válida, contar a compra, somar os pontos e decidir o bónus. Os pontos de uma compra calculam-se com uma operação do guia 02 que dá o número de vezes que 100 cabe no valor. O bónus é uma decisão que só se toma para compras válidas: pode ficar dentro do ramo das compras válidas, como um `SE` dentro de um `SENÃO`. Na tabela, pergunta-te quanto dá 1999 cêntimos e quanto dá 2000, e confirma que a diferença não é só de 1 ponto.

## Desafio opcional: mudar uma restrição de cada vez

Volta ao exercício 4, já com todos os testes a passar. Vais fazer três mudanças ao enunciado, uma de cada vez, e cada uma a partir da versão original, não da anterior.

1. O bónus passa a exigir compras de 2500 cêntimos ou mais.
2. Os pontos passam a ser 1 por cada 50 cêntimos completos, em vez de 100.
3. As compras acima de 50000 cêntimos passam a ter de ser registadas à mão: o algoritmo escreve "Valor acima do limite" e não as conta, nem em compras nem em pontos.

Para cada mudança, e antes de mexer no algoritmo:

**a)** Diz que linhas da tua tabela de casos mudam de resultado esperado, e escreve os novos resultados.

**b)** Diz que casos novos são precisos, e porquê.

Só depois:

**c)** Altera o pseudocódigo e diz quantas linhas mudaram.

**d)** Diz que figuras do fluxograma mudam, e se é preciso acrescentar alguma.

**e)** Executa a tabela inteira na versão alterada.

No fim, compara as três mudanças: qual delas obrigou a acrescentar um ramo novo, e qual mudou mais resultados esperados sem mudar nenhuma estrutura? Escreve a tua conclusão em duas ou três frases.

## Critérios de conclusão

- [ ] Escrevi a tabela de casos do exercício 1 antes de ler o algoritmo.
- [ ] As minhas tabelas têm casos normais, os dois lados de cada fronteira e casos inválidos, e, quando há um ciclo, o caso zero.
- [ ] O meu registo de depuração do exercício 2 tem as cinco linhas e explica a diferença entre a causa e o sintoma.
- [ ] Contei os passos das duas versões do exercício 3 com a mesma regra, e mostrei que são equivalentes com testes e com uma explicação.
- [ ] No exercício 4, o pseudocódigo e o fluxograma dizem exatamente a mesma coisa, figura a instrução.
- [ ] Guardei no portefólio as versões com erro e as versões corrigidas, cada uma no seu ficheiro.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
