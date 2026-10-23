![Cabeçalho](../imagens/cabecalho.png)

# Projeto 1: Duelo de dados

Dois jogadores escolhem números inteiros entre 1 e 6 durante um máximo de cinco rondas. O duelo termina logo que alguém ganha três rondas. O algoritmo diz quem ganhou cada ronda e quem ganhou o duelo. O projeto faz-se na aula, com o professor ao quadro. Escreves no caderno ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## Para que servem os três projetos

Até aqui, cada exercício treinou uma coisa de cada vez: um ciclo, uma cadeia de decisões, um contador, uma tabela de casos. Um projeto junta tudo isso num problema só e leva-o do enunciado até um algoritmo testado. É um salto grande. Por isso, a unidade de algoritmos acaba com três projetos, em vez de um só. Cada um é um pouco mais difícil do que o anterior.

| Projeto | Como se faz |
| --- | --- |
| 1, duelo de dados | O professor resolve-o ao quadro, a pensar em voz alta; tu acompanhas, respondes e escreves no caderno |
| 2, adivinha o número | Em pares, um passo de cada vez, com o professor a confirmar cada passo antes do seguinte |
| 3, avaliação prática | Individual, com um problema novo, numa prova de 120 minutos |

Os três seguem o mesmo processo, sempre pela mesma ordem:

1. o contrato;
2. a tabela de casos esperados, escrita antes do algoritmo;
3. o algoritmo;
4. a tabela de iterações e os testes;
5. a depuração, com o seu registo.

No projeto 2 e na avaliação junta-se mais um passo: melhorar o algoritmo e contar os passos antes e depois. Este projeto ainda não o tem. É este processo que a avaliação observa, e por isso vais fazê-lo duas vezes com ajuda antes de o fazeres sozinho.

A tabela de casos vem antes do algoritmo, e o passo 2 recorda-te porquê. O guia 05 explica-o na secção "O resultado esperado decide-se antes de executar". Os testes vêm depois do algoritmo, porque só se pode executar o que já está escrito. E a depuração vem no fim, porque só se procura um erro depois de um teste o mostrar.

Este é o primeiro projeto, e é o teu primeiro contacto com um projeto completo e com a forma que a avaliação vai pedir.

Os projetos 1 e 2 ficam no teu portefólio e não contam para a avaliação prática, porque são feitos com ajuda. O trabalho que fazes neles conta, como o das outras aulas, no empenho e na autonomia. Mas vais poder consultá-los durante a avaliação, e por isso vale a pena que o caderno fique completo e arrumado. Não esperes encontrar lá a resposta da avaliação. Cada projeto pede decisões que os anteriores não pediram, e a avaliação não é uma cópia deste projeto nem do projeto 2. O que vais poder aproveitar é a forma de trabalhar, passo a passo.

## O que precisas de saber

Este projeto não traz matéria nova. Usa o que está nos guias 01 a 04 e nas partes do guia 05 sobre testar e depurar. Cada passo deste documento diz onde está explicada a ferramenta de que precisa.

- O contrato de um problema e as suas quatro perguntas: guia [01 Do problema ao algoritmo](01-do-problema-ao-algoritmo.md). Está na secção "O contrato do problema: entradas, saídas, restrições e condições".
- As ambiguidades de um enunciado: guia 01, secção "Instruções ambíguas". Quando o enunciado não diz o que acontece numa situação, não se inventa em silêncio. Decide-se, e escreve-se a decisão.
- A decomposição de um problema em partes mais pequenas: guia 01, secção "Decompor um problema em subproblemas".
- As variáveis, com o tipo à frente na linha onde nascem, e as constantes, escritas com `const`: guia [02 Pseudocódigo e fluxogramas](02-pseudocodigo-e-fluxogramas.md).
- A leitura com `ler valor` e a escrita no ecrã com `Escreve:`, do guia 02.
- O trace, em que se executa um algoritmo à mão, instrução a instrução, do guia 02.
- As comparações e a cadeia `Se`, `Senão se`, `Senão`: guia [03 Decisões e validação](03-decisoes-e-validacao.md).
- A regra da cadeia, em que a primeira condição verdadeira ganha e o `Senão` apanha tudo o que sobra, do guia 03.
- As fronteiras e a tabela de casos esperados, do guia 03.
- O `Enquanto`, com a inicialização antes do ciclo, a condição e a atualização dentro do ciclo: guia [04 Repetição e padrões](04-repeticao-e-padroes.md).
- As condições com `e`, que só são verdadeiras quando todas as partes são verdadeiras: guia [03 Decisões e validação](03-decisoes-e-validacao.md).
- A pergunta que decide entre `Enquanto` e `Para`: guia 04, secção "Escolher entre Enquanto e Para".
- O padrão contador: guia 04, secção "Padrão contador".
- A tabela de iterações, do guia 04. Cada linha é a fotografia do estado no momento em que o ciclo testa a condição.
- Testar e depurar: guia [05 Testar, depurar e melhorar](05-testar-depurar-e-melhorar.md). Está da secção "Testar é comparar o obtido com o esperado" à secção "Corrigir a causa e não o sintoma".
- O exemplo guiado do guia 05, o do inventário da papelaria. Os passos 1 a 7 seguem o mesmo processo deste projeto, e o passo 11 mostra um registo de depuração completo.

As partes do guia 05 sobre melhorar e contar passos, e a parte das funções, não são precisas aqui.

Testar e depurar não tiveram uma aula só para eles. Foste fazendo as duas coisas em cada exercício, sempre que experimentavas um algoritmo com valores e corrigias o que não batia certo. Neste projeto fazes o mesmo, mas por escrito e com a forma que a avaliação pede. Essa forma tem três partes: a tabela de casos escrita antes do algoritmo, o obtido ao lado do esperado e o registo de cada correção. Se ainda não leste as secções do guia 05, não faz mal. O professor recorda cada ferramenta no passo em que ela aparece, e depois da aula podes relê-las com calma.

Neste projeto não há arrays, funções nem validação de dados. No passo 1 vais perceber porque é que a validação não faz falta.

## Como vais trabalhar

Não tens de resolver este projeto sozinho. O professor resolve-o contigo, no quadro, a pensar em voz alta. O teu trabalho é acompanhar cada passo e pensar nas perguntas antes de o professor avançar. Respondes quando ele perguntar, e escreves no caderno tudo o que fica no quadro.

Muitas vezes o professor vai parar e perguntar o que se faz a seguir. É nesse momento que se aprende, porque és tu que decides antes de veres a decisão escrita. Uma resposta errada dita em voz alta, numa aula destas, não custa nada e ajuda a turma inteira. Muitas vezes é o erro que outros também iam cometer.

Precisas só do caderno e de um lápis.

Em cada ronda, os jogadores escolhem os números e escrevem-nos pela ordem combinada: primeiro o jogador 1, depois o jogador 2. O algoritmo compara os dois números, conta as rondas ganhas e decide o resultado do duelo. Para testar, escreves uma lista de valores e usas sempre essa lista. Assim, podes repetir o mesmo caso e comparar os resultados.

No fim, guardas o projeto no teu portefólio de algoritmos. A secção "O que fica no teu portefólio", no fim deste documento, diz que peças guardas e com que nomes.

## O jogo

> Dois jogadores disputam um duelo de até cinco rondas. Em cada ronda, o jogador 1 escolhe um número inteiro entre 1 e 6 e escreve-o. Depois, o jogador 2 faz o mesmo. Quem escolher o número maior ganha a ronda. O algoritmo escreve "Ronda para o jogador 1" ou "Ronda para o jogador 2". Se os dois escolherem o mesmo número, escreve "Ronda empatada". O duelo termina logo que um jogador ganha três rondas ou quando se completam cinco rondas. Ganha o duelo quem ganhou mais rondas. O algoritmo escreve então "Ganhou o jogador 1" ou "Ganhou o jogador 2".

Por exemplo, o jogador 1 escolhe 4 e o jogador 2 escolhe 2. Nessa ronda, o algoritmo escreve "Ronda para o jogador 1". Se o jogador 1 escolher 3 e o jogador 2 escolher 6, escreve "Ronda para o jogador 2".

Lê o enunciado duas vezes. Na primeira leitura, percebe o jogo. Na segunda, de lápis na mão, sublinha os números e as mensagens que o algoritmo tem de escrever. Sublinha também as palavras que dizem quando acontece cada coisa, como "em cada ronda" e "o duelo termina". São essas palavras que vão decidir, no passo 3, o que fica dentro do ciclo e o que fica fora dele.

Antes do passo 1, inventa um duelo com o colega do lado. Preparem valores para até cinco rondas, em duas colunas, uma por jogador. Respeitem a paragem quando alguém alcança a terceira vitória. Decidam, só com o enunciado, o que o algoritmo devia escrever em cada ronda e no fim. Guardem esse duelo. Pode vir a ser um dos vossos casos de teste, e pode também levar-vos à pergunta que o passo 1 vai fazer.

## Passo 1: o contrato

O contrato vem primeiro porque diz exatamente o que o algoritmo tem de fazer, antes de se pensar em como o vai fazer. O enunciado está escrito para pessoas, e as pessoas preenchem as falhas sem dar por isso. O contrato transforma-o em respostas precisas, e é dele que vão sair os resultados esperados do passo 2. Como o guia 05 explica, o enunciado e o contrato são a única autoridade sobre o que o algoritmo deve fazer. Sem contrato, os resultados esperados seriam palpites, e um teste que compara o obtido com um palpite não prova nada.

O professor escreve o contrato no quadro, parte a parte, e tu copias. O contrato tem cinco partes: as respostas às quatro perguntas do guia 01 e as decisões. A tabela seguinte mostra-as. A coluna da direita não é a resposta. Diz o que cada parte tem de responder.

| Parte do contrato | O que tem de responder |
| --- | --- |
| Entradas | Que valores o algoritmo recebe, quantos são, por que ordem chegam, de que tipo são, entre que limites ficam e porquê |
| Saídas | O que o algoritmo escreve e em que momento: durante o jogo e no fim |
| Restrições | As regras fixas, que valem em todos os duelos, incluindo os valores do enunciado que nunca mudam e que vão ser constantes |
| Condições | As situações diferentes que podem acontecer numa ronda e no fim do duelo, e que obrigam o algoritmo a fazer coisas diferentes |
| Decisões | O que o enunciado não diz e tem de ser decidido, cada coisa numa frase que começa por "Decisão:" |

Pensa nestas perguntas antes de o professor avançar, e escreve as tuas respostas a lápis, na margem do caderno:

1. Qual é o menor e o maior número de rondas que o duelo pode ter? Quantos valores são lidos em cada ronda? Por que ordem?
2. Que valores pode ter cada entrada? Pode aparecer um 0, um 7 ou um 2,5? Que palavras do enunciado te deixam responder a isto?
3. Que números do enunciado fixam os limites do jogo e nunca mudam? Como se escreve cada um desses valores no pseudocódigo?
4. O que é que o algoritmo escreve em cada ronda jogada? E o que escreve uma vez, no fim do duelo?
5. Que situações diferentes podem acontecer numa ronda? E no fim do duelo, quando se comparam as rondas que cada jogador ganhou?

### O que o enunciado não diz

A pergunta 5 leva-te a uma situação de que o enunciado não fala. Pensa em todos os finais possíveis, contando as rondas ganhas de cada um. Há algum para o qual a última frase do enunciado não diga o que escrever?

É uma ambiguidade do tipo a que o guia 01 chama informação que falta. Não há nenhuma palavra vaga para sublinhar, mas há uma pergunta sem resposta. E é das mais perigosas, porque um algoritmo escrito sem pensar nela não se queixa. Escreve qualquer coisa no fim, e essa coisa depende da forma como calhou ficar escrita a última decisão do algoritmo. Não depende de alguém ter pensado no que era justo.

O guia 01 diz o que fazer. Não se inventa em silêncio. Pergunta-se a quem escreveu o enunciado. Se não for possível, toma-se uma decisão e escreve-se no contrato. Assim, quem ler a solução sabe em que pressuposto ela assenta. Na aula, quem escreveu o enunciado está ali, e a decisão toma-se em conjunto, no quadro.

6. Que final é esse, e o que diz o enunciado sobre ele?
7. Que decisões possíveis vês? Para cada uma, pensa em duas coisas: é justa para os dois jogadores? Obriga a mudar alguma coisa que o enunciado fixou, como o máximo de rondas?
8. Porque é que esta decisão tem de ficar escrita já, no passo 1, e não depois de o algoritmo estar feito?

### A suposição que dispensa a validação

No guia 01, na secção "Porque se chama contrato", viste que o contrato é um acordo entre duas partes. Quem usa o algoritmo compromete-se a dar entradas dentro do combinado. O algoritmo compromete-se a dar a saída prometida. Se alguém der uma entrada fora do combinado, há duas hipóteses. Ou o contrato diz o que acontece nesse caso, ou deixa claro que esse caso não está coberto.

Validar uma entrada é verificar se o valor é aceitável e decidir o que fazer quando não é. É matéria que vais trabalhar antes do projeto 2, e o projeto 2 vai precisar dela. Este projeto pode dispensá-la, desde que o contrato diga porquê, numa frase escrita. A resposta à pergunta 2 é o sítio onde essa frase nasce. Neste projeto, o contrato supõe que os jogadores cumprem o combinado: escolhem e escrevem apenas números inteiros entre 1 e 6. O algoritmo não verifica essa suposição. Se alguém escrever 0, 7 ou 2,5, esse caso fica fora do contrato.

Uma frase destas, no contrato, chama-se uma **suposição**: uma coisa que o contrato dá como certa e que o algoritmo não verifica. Escreve-a nas entradas, ao pé dos valores a que diz respeito. Uma suposição escrita é honesta, porque quem lê o contrato fica a saber em que condições o algoritmo funciona. Uma suposição que ninguém escreveu é um erro escondido. Só se descobre no dia em que a coisa dada como certa falha. No exemplo guiado do guia 05, o do inventário, o contrato tem uma suposição destas sobre o stock do início do dia. Procura-a no passo 1 desse exemplo.

Repara que a suposição e a decisão são coisas diferentes. A decisão escolhe o que o algoritmo faz numa situação que pode mesmo acontecer. A suposição diz que uma situação não vai acontecer, e porquê.

## Passo 2: a tabela de casos esperados, antes do algoritmo

Este passo faz-se sem algoritmo nenhum, e é de propósito. O guia 05 explica porquê, na secção "O resultado esperado decide-se antes de executar". Se calculares o resultado esperado depois de ver o que o algoritmo escreve, o teu cérebro aceita o resultado porque o viu escrito. Estás a perguntar ao algoritmo se ele concorda consigo próprio. Escrito antes, a partir do enunciado e do contrato, o resultado esperado fica à espera do obtido, e qualquer diferença salta à vista. Os casos escritos antes de haver algoritmo são os testes de caixa preta do guia 05. Como ainda não há algoritmo para olhar, não herdas os pontos cegos de quem o vai escrever. São os casos em que essa pessoa não pensou.

Neste jogo, cada caso de teste descreve um duelo inteiro, com dois valores por ronda jogada. Para os escreveres depressa e sem confusões, escreve cada ronda como um par entre parênteses, com o valor do jogador 1 primeiro. O par (4, 2) quer dizer que o jogador 1 escolheu 4 e o jogador 2 escolheu 2. Um caso pode preparar cinco pares, pela ordem das rondas. Se alguém ganhar três rondas antes do fim dessa lista, os pares restantes ficam por ler. Indica na tabela quantas rondas devem ser jogadas.

O resultado esperado de um caso é tudo o que o algoritmo tem de escrever, além das perguntas aos jogadores. São a mensagem de cada ronda jogada e a mensagem do fim. Para caber na tabela, podes abreviar as mensagens das rondas:

- J1 quer dizer "Ronda para o jogador 1";
- J2 quer dizer "Ronda para o jogador 2";
- E quer dizer "Ronda empatada".

A mensagem do fim escreve-se por inteiro. Não deixes as mensagens das rondas de fora. Um algoritmo que acerta no fim e escreve mal uma ronda está errado, e só uma tabela com as rondas o mostra.

Para calcular o resultado esperado de um caso não precisas de algoritmo nenhum. Decide cada ronda pelo enunciado, faz um risco ao lado do jogador que a ganhou e, no fim, compara os riscos dos dois.

A tabela tem as colunas do guia 05 e uma coluna para as rondas lidas. Estas seis preenchem-se agora:

| N.º | Tipo | Entradas preparadas, ronda a ronda | Rondas lidas | Resultado esperado | Porque foi escolhido |
| ---: | --- | --- | ---: | --- | --- |

As duas últimas, "Resultado obtido" e "Passou?", acrescentam-se no passo 5, depois de executar.

Para escolher os casos, usa os tipos do guia 05, na secção "Casos normais, de fronteira e inválidos". Um caso normal é um duelo típico, dos que se imaginam ao ler o enunciado. Um caso de fronteira está no sítio onde a resposta do algoritmo muda. Este jogo tem fronteiras nas comparações. Há a comparação dos dois números de cada ronda e, no fim, a comparação das rondas ganhas. Há também a fronteira da paragem: chegar à terceira vitória antes da quinta ronda. A tabela tem de testar a paragem antecipada para ambos os jogadores e a chegada ao limite de rondas.

Nesta tabela não vão aparecer casos do tipo inválido. Não é esquecimento, e não pode parecer esquecimento a quem ler o teu portefólio. Uma tabela sem casos inválidos só está completa se o contrato disser que essas entradas ficam fora do combinado. O contrato não garante que ninguém se engana; apenas deixa claro o que o algoritmo cobre. Se o contrato não o disser, falta uma linha à tabela, ou falta uma frase ao contrato. Quando o professor escrever a tabela, confirma que a razão ficou escrita no passo 1.

Antes de o professor avançar, pensa nestas perguntas:

1. Numa ronda, onde é que a resposta muda de "Ronda para o jogador 1" para "Ronda para o jogador 2"? Que par de valores fica exatamente em cima dessa fronteira, e que pares ficam imediatamente de um lado e do outro?
2. No fim do duelo, onde é que a resposta muda de um vencedor para o outro? Que duelo fica exatamente em cima dessa fronteira? E qual é a menor diferença de rondas ganhas com que um jogador ainda ganha o duelo?
3. O duelo não pode acabar sem se jogar nenhuma ronda. Há algum duelo em que nenhum jogador chega a ganhar uma ronda? O que esperas que o algoritmo escreva nesse duelo?
4. Consegues escrever o resultado esperado de um duelo em que os dois ganharam o mesmo número de rondas sem a decisão do passo 1? Porquê?
5. Que valores preparados devem ficar por ler se um jogador alcançar a terceira vitória? Como verificas que o algoritmo não joga uma ronda a mais?
6. Se ninguém chegar a três vitórias nas cinco rondas, como se decide o vencedor? Pode alguém ganhar com menos de três?
7. Olha para a tua tabela. Cada mensagem do enunciado aparece no resultado esperado de pelo menos um caso? E a mensagem que a decisão do passo 1 vier a criar?

## Passo 3: o algoritmo

Agora, e só agora, escreve-se o algoritmo. A tabela de casos do passo 2 é o alvo. O algoritmo tem de escrever, para cada caso, exatamente o resultado esperado que lá está.

Antes de escrever a primeira linha, decompõe o problema, como aprendeste no guia 01. Quase todos os algoritmos com um ciclo têm três partes:

- o que se faz uma vez, antes do ciclo;
- o que se repete, uma vez por iteração;
- o que se faz uma vez, depois do ciclo.

As palavras que sublinhaste no enunciado, as que dizem quando acontece cada coisa, dizem-te o que vai para cada parte. No pseudocódigo, é a indentação que mostra essa separação. O que está indentado por baixo do `Enquanto` repete-se, e o que está encostado à margem executa-se uma vez só. Na secção "Quatro erros que vais encontrar muitas vezes", o guia 05 mostra como uma linha que muda de indentação muda o algoritmo.

O professor escreve o algoritmo no quadro na forma de pseudocódigo das aulas, e tu copias. Lembra-te de como é essa forma:

- não tem cabeçalho nem linhas de início e de fim;
- as constantes escrevem-se com `const`;
- cada variável tem o tipo à frente na linha onde nasce, e não o tem daí para a frente;
- os blocos marcam-se só pela indentação, com quatro espaços por nível.

Se preferires, podes escrever ao lado o mesmo algoritmo em frases claras. Também vale, aqui e na avaliação, desde que não deixe dúvidas: quanto, quando, e o que acontece se não der.

Pensa nestas perguntas antes de o professor avançar:

1. `Enquanto` ou `Para`? Sabe-se o número exato de rondas ou apenas o máximo? Em que situações deve o ciclo continuar? (Guia 04, "Escolher entre Enquanto e Para".)
2. O que acontece em cada ronda, e por que ordem? Onde se prepara a ronda seguinte? Escreve as ações por palavras antes de pensares em pseudocódigo.
3. Para decidir, no fim, quem ganhou o duelo, o que é que o algoritmo tem de ir guardando ao longo das rondas? Que padrão do guia 04 é este?
4. Quantos contadores são precisos? O enunciado manda escrever quantas rondas ficaram empatadas? Um contador que é atualizado e nunca é usado faz falta? Decide e justifica.
5. Onde nasce cada contador, antes do ciclo ou dentro dele? A condição do ciclo precisa desses valores? E se eles voltarem a zero em cada ronda?
6. Os números escolhidos aparecem pela primeira vez dentro do ciclo. Em que linha levam o tipo? Quantas vezes pode essa linha executar-se? (Guia 04, "Padrão contador".)
7. Dentro do ciclo, a ronda tem três resultados possíveis. Por que ordem fazes as perguntas, e qual dos três fica no `Senão`? Precisas de escrever a condição desse último, ou o `Senão` chega? Porquê?
8. Onde fica a decisão do duelo, dentro do ciclo ou depois dele? O que aparecia no ecrã se ficasse no sítio errado?
9. Que ramo da decisão do fim existe só por causa da decisão do passo 1?

Com o algoritmo escrito, faz a pergunta da caixa branca, do guia 05, na secção "Duas maneiras de escolher casos". Há algum ramo de um `Se` por onde nenhum caso da tabela passa? Se houver, acrescenta um caso que passe por ele, com o resultado esperado calculado pelo enunciado, como os outros.

## Passo 4: a tabela de iterações

Um pseudocódigo não corre num computador. Executá-lo é fazer o teste de mesa do guia 05, à mão. Para um ciclo, a forma mais curta é a tabela de iterações do guia 04. Tem uma linha por cada teste da condição do ciclo. Cada linha tem a fotografia do estado nesse momento, a condição com os valores substituídos e o que acontece durante a iteração seguinte. No `Enquanto`, a condição está escrita na primeira linha do ciclo. Na tabela, substitui as variáveis pelos valores de cada teste e mostra por que razão o ciclo continua ou termina.

O professor escolhe um dos casos da tabela, normalmente o que passa por mais ramos do algoritmo. Faz a tabela de iterações no quadro, com a turma a dizer cada valor antes de ele o escrever. A tabela tem estas colunas:

- uma para o número da ronda;
- uma para cada valor lido;
- uma para cada contador;
- a da condição;
- a do que acontece durante a iteração.

Nesta última coluna escreve-se o que é lido, que condição da ronda dá verdadeiro, que mensagem aparece e que contador muda. Lembra-te da regra do guia 04. As colunas mostram o estado no momento do teste. Por isso, um valor lido durante uma iteração só aparece na sua coluna na linha seguinte.

Pensa nestas perguntas antes de o professor avançar:

1. Se só pudesses fazer a tabela de iterações de um dos casos, qual escolhias? Porquê esse?
2. Para o caso escolhido, quantas rondas vão ser jogadas? Quantas linhas terá a tabela, contando o último teste, que dá falso?
3. Na primeira linha, que valores têm as colunas dos números escolhidos? Porquê?
4. Depois de uma ronda empatada, que colunas mudam na linha seguinte, e quais ficam iguais?
5. Na última linha, que parte da condição faz o ciclo parar? Quanto vale o número da ronda nesse momento?
6. Depois da última linha, que instruções são executadas, e que mensagem aparece no fim? Bate certo com o resultado esperado que escreveste no passo 2?

## Passo 5: executar os outros casos e completar a tabela

A tabela de iterações prova que o algoritmo funciona para um caso, e não diz nada sobre os outros. É por isso que se executam todos os casos da tabela do passo 2, e não só aquele de que se fez o trace.

Não precisas de uma tabela de iterações inteira para cada caso. Segue cada ronda pela cadeia de decisões, anota a mensagem que o algoritmo escreve e faz um risco no contador que muda. Quando o duelo terminar, aplica a decisão do fim aos riscos que tens. Confirma também que não leste pares depois da terceira vitória. Mas executa o que está escrito, e não o que achas que o algoritmo devia fazer. É essa a diferença entre um teste e uma confirmação do que já pensavas. O guia 05 avisa para isto nos erros frequentes, em "O trace que concorda sempre contigo". Depois, acrescenta à tabela as duas colunas que faltavam, "Resultado obtido" e "Passou?", e preenche-as caso a caso.

Pensa nestas perguntas antes de o professor avançar:

1. Se um caso falhar, onde pode estar o erro? Há dois sítios possíveis, e o guia 05 diz quais na secção "Testar é comparar o obtido com o esperado".
2. Se descobrires que um resultado esperado estava mal calculado, podes corrigi-lo? De onde tem de vir o valor novo: do enunciado ou do resultado obtido?
3. Depois de executares todos os casos, todos os ramos do algoritmo foram percorridos por pelo menos um deles?

## Passo 6: depurar, ou escolher o caso que dá mais confiança

Este passo tem dois caminhos, e o que se segue depende do passo 5.

### Se algum caso falhou: o registo de depuração

Um teste que falha é útil, como diz o guia 05. O erro apareceu no caderno, e não no meio de um jogo a sério. Agora procura-se a causa com o método do guia 05, da secção "Depurar com método". São cinco passos, sempre pela mesma ordem:

1. observar e reproduzir o erro;
2. formular uma hipótese;
3. verificá-la com o trace;
4. corrigir a causa;
5. voltar a testar tudo.

Cada passo do método dá uma linha do registo de depuração, como no passo 11 do exemplo guiado do guia 05. A coluna da direita diz o que se escreve em cada linha:

| Passo do método | O que se escreve |
| --- | --- |
| Erro observado | O caso que falhou, o resultado esperado, o resultado obtido e qual das mensagens está errada; e o caso mínimo, se o encontrares |
| Hipótese | Uma frase sobre a causa, que pode ser verdadeira ou falsa |
| Verificação com o trace | O que a tabela de iterações mostrou: a primeira linha onde uma variável fica com um valor diferente do que devia ter |
| Correção | A instrução que mudou, e onde, mudando o menos possível |
| Novo teste | O resultado de voltar a executar a tabela inteira, e não só o caso que falhou |

Se a versão do quadro passar em todos os casos à primeira, o professor pode mostrar uma versão com um erro. É um erro que costuma aparecer em algoritmos destes, e fazem juntos o registo. Guarda as duas versões, a com erro e a corrigida. No portefólio, a versão com erro é a prova de que o encontraste.

Pensa nestas perguntas antes de o professor avançar:

1. Dos erros da secção "Quatro erros que vais encontrar muitas vezes", do guia 05, qual te parece mais provável num algoritmo como este? Que caso da tabela o apanhava?
2. O guia 05 manda procurar o caso mínimo, o mais pequeno que ainda mostra o erro. Como simplificas um caso sem desrespeitar as regras de paragem?
3. A correção que vais escrever explica porque é que o valor ficou errado, ou só o acerta no fim? (Guia 05, "Corrigir a causa e não o sintoma".)

### Se nenhum caso falhou: o caso que dá mais confiança

Todos os casos passarem é bom sinal, mas não prova que o algoritmo está certo. Prova que está certo nos casos que testaste. A pergunta que fica é qual dos teus casos te dá mais confiança, isto é, qual deles apanharia mais erros se o algoritmo os tivesse. Responde-se por escrito, numa ou duas frases, com o número do caso e a razão. A razão diz por que ramos do algoritmo ele passa e que erros ele mostraria.

Pensa nestas perguntas antes de o professor avançar:

1. Que caso passa por mais ramos do algoritmo, contando os da ronda e os do fim?
2. Pega nos erros da secção "Quatro erros que vais encontrar muitas vezes", do guia 05, e imagina cada um deles neste algoritmo. O caso que escolheste apanhava cada um?
3. Há algum erro que só um dos teus casos apanhava? O que é que isso te diz sobre a tabela inteira?

## O que fica no teu portefólio

O portefólio de algoritmos é a pasta que o guia 05 descreve na secção "O teu portefólio". Para este projeto, guarda:

- o enunciado do jogo;
- o contrato, com a suposição e a decisão;
- a tabela de casos esperados, com os resultados obtidos e a coluna "Passou?";
- o algoritmo;
- a tabela de iterações;
- se seguiste o primeiro caminho do passo 6, o registo de depuração, com a versão com erro e a versão corrigida;
- se seguiste o segundo caminho, a explicação do caso que dá mais confiança.

Usa nomes de ficheiro como os do guia 05, em minúsculas, com hífenes e sem acentos nem espaços: `duelo-de-dados-contrato.txt`, `duelo-de-dados-pseudocodigo.txt`, `duelo-de-dados-testes.txt` e `duelo-de-dados-depuracao.txt`. Cada versão do algoritmo fica no seu ficheiro, e a versão com erro chama-se `duelo-de-dados-pseudocodigo-com-erro.txt`. As páginas do caderno também contam. Fotografa-as ou passa-as a limpo, e junta-as às peças a que pertencem.

Antes de fechares o caderno, confirma:

- [ ] O contrato tem as cinco partes: as quatro respostas e as decisões. A suposição sobre os números escolhidos está nas entradas. A decisão sobre o que o enunciado não dizia está numa frase que começa por "Decisão:".
- [ ] A tabela de casos foi escrita antes do algoritmo, e cada caso tem a razão da escolha.
- [ ] Cada mensagem do enunciado, e a da decisão, aparece no resultado esperado de pelo menos um caso.
- [ ] A tabela de iterações tem a linha do último teste, o que dá falso e faz sair do ciclo.
- [ ] Todos os casos têm o resultado obtido e a coluna "Passou?" preenchida.
- [ ] Tens o registo de depuração, com as duas versões do algoritmo, ou a explicação do caso que dá mais confiança.

## O que vem a seguir

O [projeto 2](05-projeto-2-adivinha-o-numero.md) é o jogo de adivinhar um número. Faz-se em pares, um passo de cada vez, com o professor a confirmar cada passo antes de passares ao seguinte. Vem depois das aulas da validação de dados e da validação repetida, porque vai precisar das duas. Segue o mesmo processo deste projeto e junta-lhe o passo que aqui ficou de fora. Esse passo é melhorar o algoritmo e contar os passos antes e depois, com a regra da secção "Contar passos" do guia 05.

Depois vem a avaliação prática: individual, com 120 minutos e um problema novo, que o professor entrega no dia. O processo é o mesmo dos dois projetos, e podes consultar os dois no teu portefólio. Antes da avaliação, o professor mostra-te a grelha com os critérios.

Até lá, os exercícios 1 a 4 da [ficha do tema 05](05-testar-depurar-e-melhorar-exercicios.md) treinam estes passos um de cada vez. Treinam também o da melhoria, que o projeto 2 vai pedir. Neles, escolhes casos antes de ver o algoritmo, depuras com método, contas passos e constróis um algoritmo a partir dos casos.

![Rodapé](../imagens/rodape.png)
