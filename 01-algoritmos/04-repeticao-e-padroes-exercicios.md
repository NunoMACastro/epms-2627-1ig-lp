![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Repetição e padrões

UC: UC00245

Blocos: ALG04

Requisitos: UC00245-R03, UC00245-R04, UC00245-R05, UC00245-K05, UC00245-K06, UC00245-A05, UC00245-A06, UC00245-A07, UC00245-C01, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG04, acompanha o [guia](04-repeticao-e-padroes.md) e o [laboratório](04-repeticao-e-padroes-laboratorio.md) |
| Tempo total | 120 minutos dos 300 do bloco: 90 de prática autónoma e 30 de desafio |
| Entrega | Pseudocódigo, tabelas de iterações e conjuntos de testes de cada exercício; fluxogramas pedidos |

## Objetivos e conceitos necessários

Vais praticar sem ajuda o que o guia explicou: encontrar e corrigir erros em ciclos, e construir ciclos com os quatro padrões, o contador, o totalizador, a sentinela e a validação repetida. Em todos os exercícios vais ter de justificar as três peças de cada ciclo: com que valor começa, em que situação continua e o que muda em cada iteração.

Antes de começares, deves conseguir escrever um `ENQUANTO` e um `PARA`, fazer uma tabela de iterações e reconhecer os quatro padrões. Está tudo no [guia](04-repeticao-e-padroes.md). Também vais precisar do que aprendeste no guia 03: comparações, `E`, `OU`, intervalos e fronteiras.

Material: papel quadriculado e lápis; o diagrams.net, para os fluxogramas que quiseres desenhar na aplicação.

Nenhum destes exercícios é o exemplo do guia com outros números. Cada um obriga-te a uma decisão que o exemplo não tomou, e é essa decisão que interessa. Quando um exercício te pedir para justificar, a justificação vale tanto como o algoritmo.

Uma regra para todos os exercícios: escreve o resultado esperado de cada caso de teste **antes** de fazeres a tabela de iterações. Se só o escreveres depois, a tabela concorda sempre contigo e não te ensina nada.

## Exercício 1: Corrigir a atualização de um contador (15 min)

Uma loja tem 6 encomendas por expedir. Uma encomenda é urgente se o prazo de entrega for de 2 dias ou menos. Um colega escreveu este algoritmo para contar as encomendas urgentes:

```text
ALGORITMO EncomendasUrgentes
CONSTANTES
    NUMERO_DE_ENCOMENDAS ← 6
    PRAZO_URGENTE ← 2
VARIÁVEIS
    encomenda: inteiro
    prazo: inteiro
    urgentes: inteiro
INÍCIO
    urgentes ← 0
    PARA encomenda ← 1 ATÉ NUMERO_DE_ENCOMENDAS FAZER
        ESCREVER "Prazo de entrega da encomenda ", encomenda, ", em dias?"
        LER prazo
        SE prazo <= PRAZO_URGENTE ENTÃO
            urgentes ← urgentes + prazo
        FIM SE
    FIM PARA
    ESCREVER "Encomendas urgentes: ", urgentes
FIM
```

**a)** Faz a tabela de iterações com os prazos 3, 1, 2, 5, 2 e 7, com uma coluna para `encomenda`, uma para `prazo` e uma para `urgentes`. O que aparece no ecrã no fim?

**b)** Conta à mão, olhando só para os seis prazos, quantas encomendas são urgentes. O resultado do algoritmo coincide? Diz qual é a linha errada. Essa linha segue o padrão contador ou o padrão totalizador? Qual dos dois devia seguir, e porquê?

**c)** Corrige a linha e refaz a tabela de iterações. Confirma que o resultado passa a ser o que contaste à mão.

**d)** Escreve seis prazos para os quais a versão errada, a do colega, dá o resultado certo. Depois explica porque é que um colega que só tivesse testado o algoritmo com esses seis prazos ficaria convencido de que ele estava bom.

Concluíste quando conseguires explicar, numa frase, a diferença entre as duas versões da linha, e mostrar um teste que a apanha e um teste que a esconde.

## Exercício 2: Corrigir um ciclo infinito num trace (20 min)

Num armazém, as prateleiras estão numeradas de 1 a 20. As de número ímpar ficam no corredor da esquerda. Este algoritmo devia escrever, por ordem, os números das prateleiras do corredor da esquerda:

```text
ALGORITMO PrateleirasDaEsquerda
CONSTANTES
    ULTIMA_PRATELEIRA ← 20
VARIÁVEIS
    prateleira: inteiro
INÍCIO
    prateleira ← 1
    ENQUANTO prateleira != ULTIMA_PRATELEIRA FAZER
        ESCREVER "Prateleira ", prateleira
        prateleira ← prateleira + 2
    FIM ENQUANTO
FIM
```

Um colega começou a tabela de iterações:

| Teste | prateleira | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 != 20` é VERDADEIRO | escreve "Prateleira 1" |
| 2.º | 3 | `3 != 20` é VERDADEIRO | escreve "Prateleira 3" |
| 3.º | 5 | `5 != 20` é VERDADEIRO | escreve "Prateleira 5" |

**a)** Copia a tabela e continua-a até ao 12.º teste.

**b)** O ciclo termina? Justifica sem continuares a tabela para sempre: olhando para os valores que `prateleira` vai tomando, explica por palavras porque é que a condição nunca chega a ser falsa.

**c)** Diz qual das três peças do ciclo está errada, respondendo às três perguntas das peças para este ciclo.

**d)** Propõe uma correção, mudando uma única linha. Faz a tabela de iterações da versão corrigida e diz quantas iterações há e com que valor fica `prateleira` depois do ciclo.

**e)** O armazém vai passar a ter 21 prateleiras, e para isso basta mudar a constante para 21. A tua correção continua a escrever todas as prateleiras do corredor da esquerda, incluindo a 21? Testa-a com a constante a 21. Se não continuar, escolhe outra correção que funcione com 20 e com 21 prateleiras, e explica porque é que essa é a melhor.

Concluíste quando a tua correção funcionar com 20 e com 21 prateleiras e conseguires explicar porquê.

## Exercício 3: Contador e totalizador num ciclo contado (20 min)

Ao fim do dia, o funcionário de uma papelaria regista os talões de venda. Primeiro escreve quantos talões vai registar, um número inteiro igual ou maior do que 0. Depois escreve o valor de cada talão, em cêntimos. No fim, o algoritmo mostra o total faturado, em cêntimos, e quantos talões foram de compras grandes. Uma compra grande é uma compra de 5000 cêntimos ou mais.

**a)** Escreve o contrato, respondendo às quatro perguntas: entradas, saídas, restrições e condições.

**b)** Este ciclo escreve-se com `ENQUANTO` ou com `PARA`? Justifica com a pergunta que o guia ensina para fazer esta escolha. Repara que o exemplo explicado do guia fez a escolha contrária: diz o que é diferente neste problema.

**c)** Escreve o algoritmo em pseudocódigo, com constantes para os valores fixos do enunciado e com as variáveis declaradas e com os tipos certos.

**d)** Desenha o fluxograma, no papel ou no diagrams.net.

**e)** Monta a tabela de casos esperados, com pelo menos três casos, escolhidos de propósito, com o resultado esperado de cada um escrito antes do trace: o caso de zero voltas, um caso que teste a fronteira das compras grandes, e o caso normal com 4 talões de 1250, 5000, 830 e 7420 cêntimos. Faz a tabela de iterações do caso normal.

**f)** Justifica o valor inicial, a condição de saída e a atualização do teu ciclo, e o valor inicial de cada uma das variáveis que contam ou somam.

Concluíste quando os resultados obtidos coincidirem com os esperados nos três casos, e o caso de zero voltas não escrever nada sem sentido.

## Exercício 4: Escolher a sentinela (20 min)

Uma loja regista quantos artigos lhe foram devolvidos em cada dia de funcionamento. O funcionário escreve o número de devoluções de cada dia, um dia de cada vez, e não se sabe à partida quantos dias vai registar. Um dia sem devoluções é um dia verdadeiro e tem de entrar nas contas. No fim, o algoritmo mostra quantos dias foram registados, o total de devoluções e a média de devoluções por dia.

**a)** Explica porque é que, neste problema, o 0 não pode ser a sentinela. Escolhe uma sentinela e justifica a escolha.

**b)** Escreve o algoritmo em pseudocódigo. A média pode ter parte decimal: que tipo tem a variável da média, e que operação usas para a calcular?

**c)** O que deve o algoritmo mostrar se a primeira coisa que o funcionário escrever for logo a sentinela? Explica porque é que, nesse caso, não se pode simplesmente calcular a média, e escreve no algoritmo o que acontece nesse caso.

**d)** Faz a tabela de iterações quando o funcionário escreve 3, 0, 5, 2 e a sentinela. Escreve antes o resultado esperado.

**e)** O funcionário engana-se e escreve -5, um número negativo que não é a tua sentinela. O que faz o teu algoritmo com esse valor? Descreve uma forma de escrever a condição do ciclo que trate de maneira diferente esse engano, e diz qual das duas formas preferes e porquê.

Concluíste quando o teu algoritmo der a média certa no caso da alínea d) e uma mensagem com sentido no caso da alínea c), sem nunca dividir por zero.

## Exercício 5: Validação repetida com contador de tentativas (15 min)

Uma loja de informática organiza workshops gratuitos. Cada inscrição pode reservar de 1 a 6 lugares. O algoritmo pede o número de lugares a reservar e, enquanto o valor não for válido, escreve uma mensagem que diz o intervalo aceite e pede de novo. No fim, mostra quantos lugares ficaram reservados e quantas tentativas inválidas houve antes de o valor ser aceite.

**a)** Escreve o algoritmo em pseudocódigo. Diz onde fica o contador das tentativas inválidas (antes do ciclo, dentro dele ou depois dele), com que valor começa e porquê.

**b)** Monta a tabela de casos esperados, com pelo menos três casos, incluindo um em que o ciclo não chega a começar e um que teste um dos extremos do intervalo. Faz a tabela de iterações quando a pessoa escreve 0, depois 7 e depois 3.

**c)** Qual é o menor número de vezes que o `LER` pode ser executado neste algoritmo? E o maior? Justifica as duas respostas.

Concluíste quando o teu conjunto de testes tiver um caso com zero iterações e o contador der a resposta certa nele.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Na tabela, olha para o valor de `urgentes` antes e depois de cada iteração em que o `SE` é verdadeiro. Quanto aumentou de cada vez? E quanto devia aumentar, se o que se quer é contar? Para a alínea d), escreve todos os prazos que contam como urgentes e, para cada um, quanto é que a linha do colega soma a `urgentes` e quanto somaria a linha corrigida.

**Exercício 2.** Escreve só a coluna `prateleira` dos doze testes, lado a lado. Que tipo de números são todos? E o 20? Na alínea e), faz a tabela da tua correção com a constante a 21 e olha para o último número escrito.

**Exercício 3.** Quando o algoritmo chega ao ciclo, o número de talões já foi lido? Volta à tabela da secção "Escolher entre ENQUANTO e PARA" do guia. Para a fronteira, lê outra vez a frase "5000 cêntimos ou mais".

**Exercício 4.** Uma sentinela não pode ser um valor que os dados verdadeiros possam ter. Que valores nunca podem ser um número de devoluções? Para a média, lembra-te do que acontece quando se divide por zero, e do `SE` do guia 03.

**Exercício 5.** Parte do algoritmo `PedirQuantidadeValida` do guia e muda o intervalo. Depois pergunta-te: o que é uma tentativa inválida, em termos das instruções do algoritmo? Em que sítio do algoritmo se sabe que uma tentativa foi inválida?

## Desafio (30 min)

Volta ao exercício 5 e muda uma só restrição: a pessoa passa a ter no máximo 3 tentativas, contando com a primeira. Se o valor continuar inválido ao fim da terceira tentativa, o algoritmo não pede mais nenhum valor e escreve "Reserva cancelada: foram usadas as 3 tentativas." Se o valor for válido numa das três tentativas, o algoritmo escreve a reserva feita, com o número de lugares.

**a)** O ciclo pode agora terminar por duas razões diferentes. Diz quais são. Escreve a condição do ciclo, lembrando-te de que, quando se mistura `E` com `OU`, se usam parênteses para mostrar o que se avalia primeiro.

**b)** Depois do `FIM ENQUANTO`, o algoritmo tem de saber por qual das duas razões o ciclo terminou, para escrever a mensagem certa. Como é que sabe? Escreve essa parte do algoritmo. Atenção: há uma forma de decidir que parece certa e falha num dos casos de teste da alínea c).

**c)** Monta a tabela de casos esperados, com pelo menos quatro casos: um valor válido à primeira; um valor válido à terceira tentativa; três valores inválidos; e um extremo do intervalo. No caso das três tentativas inválidas, confirma com a tabela de iterações que o `LER` é executado exatamente 3 vezes, nem mais uma.

**d)** Desenha o fluxograma, no papel ou no diagrams.net.

Concluíste quando o teu algoritmo passar os quatro casos, incluindo o do valor válido à terceira tentativa.

## Critérios de conclusão

- [ ] Em cada ciclo que escrevi, sei dizer com que valor começa, em que situação continua e o que muda em cada iteração.
- [ ] Os contadores e os totalizadores começam em 0 e são inicializados antes do ciclo.
- [ ] Nos ciclos com sentinela, a sentinela nunca é contada nem somada.
- [ ] Escrevi o resultado esperado de cada caso de teste antes de fazer a tabela de iterações.
- [ ] Os meus conjuntos de testes têm o caso de zero voltas e as fronteiras, e não só casos normais.
- [ ] Escolhi entre `ENQUANTO` e `PARA` com a pergunta do guia, e sei justificar a escolha.
- [ ] Os meus fluxogramas têm a seta de volta a chegar ao losango da condição.
- [ ] Nenhum dos meus algoritmos divide por zero, nem aceita um valor fora do contrato sem o dizer.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
