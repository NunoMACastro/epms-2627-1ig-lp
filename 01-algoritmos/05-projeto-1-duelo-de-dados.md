![Cabeçalho](../imagens/cabecalho.png)

# Projeto 1: Duelo de dados

UC: UC00245

Blocos: ALG05

Requisitos: UC00245-R03, UC00245-R05, UC00245-A07, UC00245-C01, UC00245-C03, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Projeto 1 de 3 da UC de algoritmos, bloco ALG05 |
| Fundamento curricular | Unidade de competência UC00245, bloco ALG05 |
| Duração | Cerca de 60 minutos em aula, com o professor ao quadro |
| Como se faz | O professor resolve o projeto ao quadro, a pensar em voz alta. Tu acompanhas, pensas nas perguntas de cada passo antes de ele avançar, respondes quando ele perguntar e escreves no caderno tudo o que fica no quadro |
| Evidência a guardar | No portefólio: o enunciado, o contrato, a tabela de casos com os resultados obtidos, o algoritmo, a tabela de iterações e o registo de depuração, ou a explicação do caso que dá mais confiança |

## Para que servem os três projetos

Até aqui, cada exercício treinou uma coisa de cada vez: um ciclo, uma cadeia de decisões, um contador, uma tabela de casos. Um projeto junta tudo isso num problema só e leva-o do enunciado até um algoritmo testado. É um salto grande, e por isso a unidade de algoritmos acaba com três projetos, cada um um pouco mais difícil do que o anterior, em vez de um só.

| Projeto | Como se faz | Tempo |
| --- | --- | --- |
| 1, duelo de dados | O professor resolve-o ao quadro, a pensar em voz alta; tu acompanhas, respondes e escreves no caderno | Cerca de 60 minutos |
| 2, adivinha o número | Em pares, um passo de cada vez, com o professor a confirmar cada passo antes do seguinte | Cerca de 120 minutos |
| 3, avaliação prática | Individual, com um problema novo | 120 minutos |

Os três seguem o mesmo processo, sempre pela mesma ordem: o contrato, a tabela de casos esperados escrita antes do algoritmo, o algoritmo, a tabela de iterações e os testes, e a depuração com o seu registo. No projeto 2 e na avaliação junta-se mais um passo, que este projeto ainda não tem: melhorar o algoritmo e contar os passos antes e depois. É este processo que a avaliação observa, e por isso vais fazê-lo duas vezes com ajuda antes de o fazeres sozinho.

Este é o primeiro, e é o teu primeiro contacto com um projeto completo e com a forma que a avaliação vai pedir. Não tens de o resolver sozinho: o professor resolve-o contigo, no quadro. O teu trabalho é acompanhar cada passo, pensar nas perguntas antes de o professor avançar, responder quando ele perguntar e escrever no caderno o que fica no quadro. Muitas vezes o professor vai parar e perguntar o que se faz a seguir. É nesse momento que se aprende, porque és tu que decides antes de veres a decisão escrita. Uma resposta errada dita em voz alta, numa aula destas, não custa nada e ajuda a turma inteira, porque muitas vezes é o erro que outros também iam cometer.

Os projetos 1 e 2 ficam no teu portefólio e não contam para a nota, porque são feitos com ajuda. Mas vais poder consultá-los durante a avaliação, e por isso vale a pena que o caderno fique completo e arrumado. Não esperes encontrar lá a resposta da avaliação: cada projeto pede decisões que os anteriores não pediram, e a avaliação não é uma cópia deste projeto nem do projeto 2. O que vais poder aproveitar é a forma de trabalhar, passo a passo.

## O que precisas de saber antes

Este projeto não traz matéria nova. Usa o que está nos guias 01 a 04 e nas partes do guia 05 sobre testar e depurar, e cada passo deste documento diz onde está explicada a ferramenta de que precisa.

Do [guia 01, Do problema ao algoritmo](01-do-problema-ao-algoritmo.md), vais usar o contrato de um problema, com as respostas às quatro perguntas (entradas, saídas, restrições e condições), e a regra das ambiguidades: quando o enunciado não diz o que acontece numa situação, não se inventa em silêncio, decide-se e escreve-se a decisão. Está nas secções "Instruções ambíguas" e "O contrato do problema".

Do [guia 02, Pseudocódigo e fluxogramas](02-pseudocodigo-e-fluxogramas.md), vais usar as variáveis, com o tipo à frente na linha onde nascem, as constantes, escritas com `const`, a leitura com `ler valor`, a escrita com `Escreve:` e o trace, em que se executa um algoritmo à mão, instrução a instrução.

Do [guia 03, Decisões e validação](03-decisoes-e-validacao.md), vais usar as comparações, a cadeia `Se`, `Senão se`, `Senão`, em que a primeira condição verdadeira ganha e o `Senão` apanha tudo o que sobra, as fronteiras e a tabela de casos esperados.

Do [guia 04, Repetição e padrões](04-repeticao-e-padroes.md), vais usar o `Para` na forma `Para i de 1 até n`, com a sua condição escondida, a pergunta que decide entre `Enquanto` e `Para`, o padrão contador e a tabela de iterações, em que cada linha é a fotografia do estado no momento em que o ciclo testa a condição.

Do [guia 05, Testar, depurar e melhorar](05-testar-depurar-e-melhorar.md), vais usar a teoria sobre testar e depurar, da secção "Testar é comparar o obtido com o esperado" até à secção "Corrigir a causa e não o sintoma", e o exemplo explicado do inventário da papelaria, cujos passos 1 a 7 seguem o mesmo processo deste projeto e cujo passo 11 mostra um registo de depuração completo. As partes do guia 05 sobre melhorar e contar passos, e a parte das funções, não são precisas aqui.

Testar e depurar não tiveram uma aula só para eles. Foste fazendo as duas coisas em cada exercício, sempre que experimentavas um algoritmo com valores e corrigias o que não batia certo. Neste projeto fazes o mesmo, mas por escrito e com a forma que a avaliação pede: a tabela de casos escrita antes do algoritmo, os resultados obtidos ao lado dos esperados e o registo de cada correção. Se ainda não leste as secções do guia 05, não faz mal. O professor recorda cada ferramenta no passo em que ela aparece, e depois da aula podes relê-las com calma.

Neste projeto não há arrays, funções nem validação de dados. No passo 1 vais perceber porque é que a validação não faz falta.

## Material e preparação

O caderno e um lápis. Não precisas de dados na aula, e há uma boa razão para isso.

O algoritmo deste projeto não lança dados. São os jogadores que lançam dados verdadeiros, e cada um escreve o valor que saiu. O algoritmo só faz o que é preciso fazer com esses valores: comparar, contar e decidir. Se fosse o algoritmo a inventar os valores, cada execução dava um duelo diferente, e um caso de teste nunca se podia repetir: quando um resultado parecesse errado, não havia maneira de voltar a ver o mesmo duelo para procurar o erro. Assim, cada caso de teste é uma lista de valores escrita por ti, e executa-se as vezes que quiseres, sempre com o mesmo resultado.

## Como está organizado o tempo

| Parte | O que se faz | Tempo |
| --- | --- | ---: |
| Início | Para que servem os três projetos, e o enunciado do jogo | 3 min |
| Passo 1 | O contrato, com a decisão sobre o que o enunciado não diz | 7 min |
| Passo 2 | A tabela de casos esperados, antes do algoritmo | 10 min |
| Passo 3 | O algoritmo | 15 min |
| Passo 4 | A tabela de iterações de um dos casos | 8 min |
| Passo 5 | Executar os outros casos e completar a tabela | 7 min |
| Passo 6 | O registo de depuração, se algum caso falhar; se nenhum falhar, o caso que dá mais confiança | 7 min |
| Fecho | O que fica no portefólio | 3 min |
| Total | | 60 min |

A ordem dos passos não é um capricho. A tabela de casos vem antes do algoritmo pela razão que o guia 05 explica na secção "O resultado esperado decide-se antes de executar", e que o passo 2 recorda. Os testes vêm depois do algoritmo porque só se pode executar o que já está escrito. E a depuração vem no fim porque só se procura um erro depois de um teste o mostrar.

## O jogo

> Dois jogadores fazem um duelo de dados de cinco rondas. Em cada ronda, cada jogador lança um dado verdadeiro, de seis faces, e escreve o valor que saiu: primeiro o jogador 1, depois o jogador 2. Quem tirar mais ganha a ronda, e o algoritmo escreve "Ronda para o jogador 1" ou "Ronda para o jogador 2"; se os dois tirarem o mesmo, escreve "Ronda empatada". No fim das cinco rondas, ganha o duelo quem tiver ganho mais rondas, e o algoritmo escreve "Ganhou o jogador 1" ou "Ganhou o jogador 2".

Lê o enunciado duas vezes. Na primeira leitura, percebe o jogo. Na segunda, de lápis na mão, sublinha os números, as mensagens que o algoritmo tem de escrever e as palavras que dizem quando acontece cada coisa, como "em cada ronda" e "no fim das cinco rondas". São essas palavras que vão decidir, no passo 3, o que fica dentro do ciclo e o que fica fora dele.

Antes do passo 1, inventa um duelo com o colega do lado: cinco rondas, com valores à vossa escolha, escritos em duas colunas, uma por jogador. Decidam, só com o enunciado, o que o algoritmo devia escrever em cada ronda e no fim. Guardem esse duelo. Pode vir a ser um dos vossos casos de teste, e pode também levar-vos à pergunta que o passo 1 vai fazer.

## Passo 1: o contrato (7 min)

O contrato vem primeiro porque diz exatamente o que o algoritmo tem de fazer, antes de se pensar em como o vai fazer. O enunciado está escrito para pessoas, e as pessoas preenchem as falhas sem dar por isso. O contrato transforma-o em respostas precisas, e é dele que vão sair os resultados esperados do passo 2. Como o guia 05 explica, o enunciado e o contrato são a única autoridade sobre o que o algoritmo deve fazer. Sem contrato, os resultados esperados seriam palpites, e um teste que compara o obtido com um palpite não prova nada.

O professor escreve o contrato no quadro, parte a parte, e tu copias. O contrato tem as cinco partes da tabela seguinte. A coluna da direita não é a resposta: diz o que cada parte tem de responder.

| Parte do contrato | O que tem de responder |
| --- | --- |
| Entradas | Que valores o algoritmo recebe, quantos são, por que ordem chegam, de que tipo são, entre que limites ficam e porquê |
| Saídas | O que o algoritmo escreve e em que momento: durante o jogo e no fim |
| Restrições | As regras fixas, que valem em todos os duelos, incluindo os valores do enunciado que nunca mudam e que vão ser constantes |
| Condições | As situações diferentes que podem acontecer numa ronda e no fim do duelo, e que obrigam o algoritmo a fazer coisas diferentes |
| Decisões | O que o enunciado não diz e tem de ser decidido, cada coisa numa frase que começa por "Decisão:" |

Pensa nestas perguntas antes de o professor avançar, e escreve as tuas respostas a lápis, na margem do caderno:

1. Quantos valores escreve cada jogador ao longo de um duelo? E os dois juntos? Por que ordem chegam ao algoritmo?
2. Que valores pode ter cada entrada? Pode aparecer um 0, um 7 ou um 2,5? Que palavras do enunciado te deixam responder a isto?
3. Há algum número no enunciado que nunca muda de um duelo para outro? Como é que se escreve um valor destes no pseudocódigo?
4. O que é que o algoritmo escreve durante o jogo, e quantas vezes? E o que escreve no fim?
5. Que situações diferentes podem acontecer numa ronda? E no fim do duelo, quando se comparam as rondas que cada jogador ganhou?

### O que o enunciado não diz

A pergunta 5 leva-te a uma situação de que o enunciado não fala. Imagina este duelo: o jogador 1 ganha duas rondas, o jogador 2 ganha outras duas e a quinta fica empatada. Ou este: as cinco rondas ficam empatadas. Relê a última frase do enunciado e tenta dizer o que o algoritmo escreve no fim de cada um destes duelos.

É uma ambiguidade do tipo a que o guia 01 chama informação que falta: não há nenhuma palavra vaga para sublinhar, há uma pergunta sem resposta. E é das mais perigosas, porque um algoritmo escrito sem pensar nela não se queixa. Escreve qualquer coisa no fim, e essa coisa depende da forma como calhou ficar escrita a última decisão do algoritmo, e não de alguém ter pensado no que era justo.

O guia 01 diz o que fazer: não se inventa em silêncio. Pergunta-se a quem escreveu o enunciado e, se não for possível, toma-se uma decisão e escreve-se no contrato, para que quem ler a solução saiba em que pressuposto ela assenta. Na aula, quem escreveu o enunciado está ali, e a decisão toma-se em conjunto, no quadro.

6. O que diz o enunciado sobre um duelo em que os dois jogadores ganharam o mesmo número de rondas?
7. Que decisões possíveis vês? Para cada uma, pensa em duas coisas: é justa para os dois jogadores? Obriga a mudar alguma coisa que o enunciado fixou, como o número de rondas?
8. Porque é que esta decisão tem de ficar escrita já, no passo 1, e não depois de o algoritmo estar feito?

### A suposição que dispensa a validação

No guia 01, na secção "Porque se chama contrato", viste que o contrato é um acordo: quem usa o algoritmo compromete-se a dar entradas dentro do combinado, e o algoritmo compromete-se a dar a saída prometida. Se alguém der uma entrada fora do combinado, o contrato ou diz o que acontece nesse caso, ou deixa claro que esse caso não está coberto.

Validar uma entrada, isto é, verificar se o valor é aceitável e decidir o que fazer quando não é, é matéria que vais trabalhar antes do projeto 2, e o projeto 2 vai precisar dela. Este projeto pode dispensá-la, desde que o contrato diga porquê, numa frase escrita. A resposta à pergunta 2 é o sítio onde essa frase nasce: repara na forma como o enunciado descreve o dado e de onde vem cada valor que o jogador escreve.

Uma frase destas, no contrato, chama-se uma **suposição**: uma coisa que o contrato dá como certa e que o algoritmo não verifica. Uma suposição escrita é honesta, porque quem lê o contrato fica a saber em que condições o algoritmo funciona. Uma suposição que ninguém escreveu é um erro à espera de acontecer, que só se descobre no dia em que a coisa dada como certa falha. No exemplo do inventário do guia 05, o contrato tem uma suposição destas sobre o stock do início do dia; procura-a no passo 1 desse exemplo.

Repara que a suposição e a decisão são coisas diferentes. A decisão escolhe o que o algoritmo faz numa situação que pode mesmo acontecer. A suposição diz que uma situação não vai acontecer, e porquê.

## Passo 2: a tabela de casos esperados, antes do algoritmo (10 min)

Este passo faz-se sem algoritmo nenhum, e é de propósito. O guia 05 explica porquê na secção "O resultado esperado decide-se antes de executar": se calculares o resultado esperado depois de ver o que o algoritmo escreve, o teu cérebro aceita o resultado porque o viu escrito, e estás a perguntar ao algoritmo se ele concorda consigo próprio. Escrito antes, a partir do enunciado e do contrato, o resultado esperado fica à espera do obtido, e qualquer diferença salta à vista. Os casos escritos antes de haver algoritmo são os testes de caixa preta do guia 05: como ainda não há algoritmo para olhar, não herdas os pontos cegos de quem o vai escrever.

Neste jogo, cada caso de teste é um duelo inteiro: dez valores, dois por ronda. Para os escreveres depressa e sem confusões, escreve cada ronda como um par entre parênteses, com o valor do jogador 1 primeiro. O par (4, 2) quer dizer que o jogador 1 tirou 4 e o jogador 2 tirou 2. Um caso são cinco pares, pela ordem das rondas.

O resultado esperado de um caso é tudo o que o algoritmo tem de escrever, além das perguntas aos jogadores: a mensagem de cada uma das cinco rondas e a mensagem do fim. Para caber na tabela, podes abreviar as mensagens das rondas como J1, J2 e E, para "Ronda para o jogador 1", "Ronda para o jogador 2" e "Ronda empatada", e escrever a mensagem do fim por inteiro. Não deixes as mensagens das rondas de fora: um algoritmo que acerta no fim e escreve mal uma ronda está errado, e só uma tabela com as rondas o mostra.

Para calcular o resultado esperado de um caso não precisas de algoritmo nenhum. Decide cada ronda pelo enunciado, faz um risco ao lado do jogador que a ganhou e, no fim, compara os riscos dos dois.

A tabela tem as colunas do guia 05. As cinco primeiras preenchem-se agora:

| N.º | Tipo | Entradas, ronda a ronda | Resultado esperado | Porque foi escolhido |
| ---: | --- | --- | --- | --- |

As duas últimas, "Resultado obtido" e "Passou?", acrescentam-se no passo 5, depois de executar.

Para escolher os casos, usa os tipos do guia 05, na secção "Casos normais, de fronteira e inválidos". Um caso normal é um duelo típico, dos que se imaginam ao ler o enunciado. Um caso de fronteira está no sítio onde a resposta do algoritmo muda, e este jogo tem fronteiras em dois sítios diferentes: dentro de cada ronda, quando se comparam os dois dados, e no fim do duelo, quando se comparam as rondas ganhas. No quadro, a tabela vai ter cerca de seis casos.

Nesta tabela não vão aparecer casos do tipo inválido. Não é esquecimento, e não pode parecer esquecimento a quem ler o teu portefólio. Uma tabela sem casos inválidos só está completa se o contrato disser porque é que não há entradas inválidas; se o contrato não o disser, falta uma linha à tabela, ou falta uma frase ao contrato. Quando o professor escrever a tabela, confirma que a razão ficou escrita no passo 1.

Antes de o professor avançar, pensa nestas perguntas:

1. Numa ronda, onde é que a resposta muda de "Ronda para o jogador 1" para "Ronda para o jogador 2"? Que par de valores fica exatamente em cima dessa fronteira, e que pares ficam imediatamente de um lado e do outro?
2. No fim do duelo, onde é que a resposta muda de um vencedor para o outro? Que duelo fica exatamente em cima dessa fronteira? E qual é a menor diferença de rondas ganhas com que um jogador ainda ganha o duelo?
3. Um `Para` de 1 até 5 tem sempre cinco iterações, por isso este jogo não tem o caso zero do guia 04. Há algum duelo em que nenhum jogador chega a ganhar uma ronda? O que esperas que o algoritmo escreva nesse duelo?
4. Consegues escrever o resultado esperado de um duelo em que os dois ganharam o mesmo número de rondas sem a decisão do passo 1? Porquê?
5. A ordem pela qual as rondas são ganhas pode mudar o vencedor do duelo? Que duelo escolherias para mostrar que um algoritmo não se deixa enganar pelo que aconteceu na última ronda?
6. Para ganhar o duelo, um jogador precisa de ganhar três rondas? Pode alguém ganhar com menos?
7. Olha para a tua tabela: cada mensagem do enunciado, e a mensagem que a decisão do passo 1 vier a criar, aparece no resultado esperado de pelo menos um caso?

## Passo 3: o algoritmo (15 min)

Agora, e só agora, escreve-se o algoritmo. A tabela de casos do passo 2 é o alvo: o algoritmo tem de escrever, para cada caso, exatamente o resultado esperado que lá está.

Antes de escrever a primeira linha, decompõe o problema, como aprendeste no guia 01. Quase todos os algoritmos com um ciclo têm três partes: o que se faz uma vez, antes do ciclo; o que se repete, uma vez por iteração; e o que se faz uma vez, depois do ciclo. As palavras que sublinhaste no enunciado, as que dizem quando acontece cada coisa, dizem-te o que vai para cada parte. No pseudocódigo, é a indentação que mostra essa separação: o que está indentado por baixo do `Para` repete-se, e o que está encostado à margem executa-se uma vez só. O guia 05 mostra, nos quatro erros frequentes, como uma linha que muda de indentação muda o que o algoritmo faz.

O professor escreve o algoritmo no quadro na forma de pseudocódigo das aulas, e tu copias: sem cabeçalho nem linhas de início e de fim, as constantes com `const`, cada variável com o tipo à frente na linha onde nasce e sem ele daí para a frente, e os blocos marcados só pela indentação, quatro espaços por nível. Se preferires, podes escrever ao lado o mesmo algoritmo em frases claras. Também vale, aqui e na avaliação, desde que não deixe dúvidas: quanto, quando, e o que acontece se não der.

Pensa nestas perguntas antes de o professor avançar:

1. `Enquanto` ou `Para`? Antes de o ciclo começar, já se sabe quantas vezes ele se vai repetir? (Guia 04, "Escolher entre Enquanto e Para".)
2. O que acontece em cada ronda, e por que ordem? Escreve as ações por palavras, uma por linha, antes de pensares em pseudocódigo.
3. Para decidir, no fim, quem ganhou o duelo, o que é que o algoritmo tem de ir guardando ao longo das rondas? Que padrão do guia 04 é este?
4. Quantos contadores são precisos? O enunciado manda escrever quantas rondas ficaram empatadas? Um contador que é atualizado e nunca é usado faz falta? Decide e justifica.
5. Onde nasce cada contador, antes do ciclo ou dentro dele? O que acontecia se nascesse dentro? (Guia 05, "Inicialização no sítio errado".)
6. Os valores dos dados aparecem pela primeira vez dentro do ciclo. Em que linha levam o tipo, e porque é que essa linha se escreve uma vez e se executa cinco? (Guia 04, "Padrão contador", a linha `int stock = ler valor`.)
7. Dentro do ciclo, a ronda tem três resultados possíveis. Por que ordem fazes as perguntas, e qual dos três fica no `Senão`? Precisas de escrever a condição desse último, ou o `Senão` chega? Porquê?
8. Onde fica a decisão do duelo: dentro do ciclo ou depois dele? O que aparecia no ecrã se ficasse no sítio errado?
9. Que ramo da decisão do fim existe só por causa da decisão do passo 1?

Com o algoritmo escrito, faz a pergunta da caixa branca do guia 05, na secção "Duas maneiras de escolher casos": há algum ramo de um `Se` por onde nenhum caso da tabela passa? Se houver, acrescenta um caso que passe por ele, com o resultado esperado calculado pelo enunciado, como os outros.

## Passo 4: a tabela de iterações (8 min)

Um pseudocódigo não corre num computador. Executá-lo é fazer o teste de mesa do guia 05, à mão. Para um ciclo, a forma mais curta é a tabela de iterações do guia 04: uma linha por cada teste da condição do ciclo, com a fotografia do estado nesse momento, a condição com os valores substituídos e o que acontece durante a iteração que começa a seguir. No `Para`, a condição é a que está escondida na primeira linha, "a variável de controlo ainda não passou do limite", e escreve-se na tabela por extenso, com os valores.

O professor escolhe um dos casos da tabela, normalmente o que passa por mais ramos do algoritmo, e faz a tabela de iterações no quadro, com a turma a dizer cada valor antes de ele o escrever. A tabela tem uma coluna para a variável do `Para`, uma para cada valor lido, uma para cada contador, a coluna da condição e a coluna do que acontece durante a iteração, onde se escreve o que é lido, que condição da ronda dá verdadeiro, que mensagem aparece e que contador muda. Lembra-te da regra do guia 04: as colunas mostram o estado no momento do teste, e por isso um valor lido durante uma iteração só aparece na sua coluna na linha seguinte.

Pensa nestas perguntas antes de o professor avançar:

1. Se só pudesses fazer a tabela de iterações de um dos casos, qual escolhias? Porquê esse?
2. Antes de começar: quantas linhas vai ter a tabela? Porquê esse número, e não o número de rondas?
3. Na primeira linha, que valores têm as colunas dos dados? Porquê?
4. Depois de uma ronda empatada, que colunas mudam na linha seguinte, e quais ficam iguais?
5. Quanto vale a variável do `Para` na última linha? Pode usar-se esse valor depois do ciclo? (Guia 04, regra 4 do `Para`.)
6. Depois da última linha, que instruções são executadas, e que mensagem aparece no fim? Bate certo com o resultado esperado que escreveste no passo 2?

## Passo 5: executar os outros casos e completar a tabela (7 min)

A tabela de iterações prova que o algoritmo funciona para um caso, e não diz nada sobre os outros. É por isso que se executam todos os casos da tabela do passo 2, e não só aquele de que se fez o trace.

Não precisas de uma tabela de iterações inteira para cada caso. Segue cada ronda pela cadeia de decisões, anota a mensagem que o algoritmo escreve, faz um risco no contador que muda e, depois da quinta ronda, aplica a decisão do fim aos riscos que tens. Mas executa o que está escrito, e não o que achas que o algoritmo devia fazer: é essa a diferença entre um teste e uma confirmação do que já pensavas, e está na tabela de erros comuns do guia 05. Depois, acrescenta à tabela as duas colunas que faltavam, "Resultado obtido" e "Passou?", e preenche-as caso a caso.

Pensa nestas perguntas antes de o professor avançar:

1. Se um caso falhar, onde pode estar o erro? Há dois sítios possíveis, e o guia 05 diz quais na secção "Testar é comparar o obtido com o esperado".
2. Se descobrires que um resultado esperado estava mal calculado, podes corrigi-lo? De onde tem de vir o valor novo: do enunciado ou do resultado obtido?
3. Depois de executares todos os casos, todos os ramos do algoritmo foram percorridos por pelo menos um deles?

## Passo 6: depurar, ou escolher o caso que dá mais confiança (7 min)

Este passo tem dois caminhos, e o que se segue depende do passo 5.

### Se algum caso falhou: o registo de depuração

Um teste que falha é útil, como diz o guia 05: o erro apareceu no caderno, e não no meio de um jogo a sério. Agora procura-se a causa com o método da secção "Depurar com método" do guia 05, com os cinco passos sempre pela mesma ordem: observar e reproduzir o erro, formular uma hipótese, verificá-la com o trace, corrigir a causa e voltar a testar tudo. Cada passo do método dá uma linha do registo de depuração, como no passo 11 do exemplo do inventário. A coluna da direita diz o que se escreve em cada linha:

| Passo do método | O que se escreve |
| --- | --- |
| Erro observado | O caso que falhou, o resultado esperado, o resultado obtido e qual das mensagens está errada; e o caso mínimo, se o encontrares |
| Hipótese | Uma frase sobre a causa, que pode ser verdadeira ou falsa |
| Verificação com o trace | O que a tabela de iterações mostrou: a primeira linha onde uma variável fica com um valor diferente do que devia ter |
| Correção | A instrução que mudou, e onde, mudando o menos possível |
| Novo teste | O resultado de voltar a executar a tabela inteira, e não só o caso que falhou |

Se a versão do quadro passar em todos os casos à primeira, o professor pode mostrar uma versão com um erro que costuma aparecer em algoritmos destes, para fazerem juntos um registo. Guarda as duas versões, a com erro e a corrigida: no portefólio, a versão com erro é a prova de que o encontraste.

Pensa nestas perguntas antes de o professor avançar:

1. Dos quatro erros frequentes do guia 05, qual te parece mais provável num algoritmo como este? Que caso da tabela o apanhava?
2. O guia 05 manda procurar o caso mínimo, o mais pequeno que ainda mostra o erro. Neste jogo não se podem tirar rondas, porque são sempre cinco. Como é que tornas um caso mais simples?
3. A correção que vais escrever explica porque é que o valor ficou errado, ou só o acerta no fim? (Guia 05, "Corrigir a causa e não o sintoma".)

### Se nenhum caso falhou: o caso que dá mais confiança

Todos os casos passarem é bom sinal, mas não prova que o algoritmo está certo: prova que está certo nos casos que testaste. A pergunta que fica é qual dos teus casos te dá mais confiança, isto é, qual deles apanharia mais erros se o algoritmo os tivesse. Responde-se por escrito, numa ou duas frases, com o número do caso e a razão: por que ramos do algoritmo ele passa, e que erros frequentes ele mostraria.

Pensa nestas perguntas antes de o professor avançar:

1. Que caso passa por mais ramos do algoritmo, contando os da ronda e os do fim?
2. Pega nos quatro erros frequentes do guia 05 e imagina cada um deles neste algoritmo. O caso que escolheste apanhava cada um?
3. Há algum erro que só um dos teus casos apanhava? O que é que isso te diz sobre a tabela inteira?

## O que fica no teu portefólio (3 min)

O portefólio de algoritmos é a pasta que o guia 05 descreve na secção "O teu portefólio". Para este projeto, guarda o enunciado do jogo; o contrato, com a suposição e a decisão; a tabela de casos esperados, com os resultados obtidos e a coluna "Passou?"; o algoritmo; a tabela de iterações; e, conforme o caminho do passo 6, o registo de depuração, com a versão com erro e a versão corrigida, ou a explicação do caso que dá mais confiança.

Usa nomes de ficheiro como os do guia 05, em minúsculas, com hífenes e sem acentos nem espaços: `duelo-de-dados-contrato`, `duelo-de-dados-pseudocodigo`, `duelo-de-dados-testes` e `duelo-de-dados-depuracao`. Cada versão do algoritmo fica no seu ficheiro. As páginas do caderno também contam: fotografa-as ou passa-as a limpo, e junta-as às peças a que pertencem.

Antes de fechares o caderno, confirma:

- [ ] O contrato tem as quatro respostas, a suposição sobre os valores dos dados e a decisão sobre o que o enunciado não dizia, cada uma escrita numa frase.
- [ ] A tabela de casos foi escrita antes do algoritmo, e cada caso tem a razão da escolha.
- [ ] Cada mensagem do enunciado, e a da decisão, aparece no resultado esperado de pelo menos um caso.
- [ ] A tabela de iterações tem a linha do último teste, o que dá falso e faz sair do ciclo.
- [ ] Todos os casos têm o resultado obtido e a coluna "Passou?" preenchida.
- [ ] Tens o registo de depuração, com as duas versões do algoritmo, ou a explicação do caso que dá mais confiança.

## A seguir

O projeto 2 é o jogo de adivinhar um número. Faz-se em pares, um passo de cada vez, com o professor a confirmar cada passo antes de passares ao seguinte, e leva cerca de 120 minutos. Vem depois das aulas da validação de dados e da validação repetida, porque vai precisar das duas. Segue o mesmo processo deste projeto e junta-lhe o passo que aqui ficou de fora: melhorar o algoritmo e contar os passos antes e depois, com a regra da secção "Contar passos" do guia 05.

Depois vem a avaliação prática: individual, com 120 minutos e um problema novo, que o professor entrega no dia. O processo é o mesmo dos dois projetos, e podes consultar os dois no teu portefólio. Antes da avaliação, o professor mostra-te a grelha com os critérios.

Até lá, os exercícios 1 a 4 da [ficha do guia 05](05-testar-depurar-e-melhorar-exercicios.md) treinam, um de cada vez, os passos deste projeto e o da melhoria, que o projeto 2 vai pedir: escolher casos antes de ver o algoritmo, depurar com método, contar passos e construir um algoritmo a partir dos casos.

![Rodapé](../imagens/rodape.png)
