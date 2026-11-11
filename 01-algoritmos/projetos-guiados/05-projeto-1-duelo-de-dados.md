![Cabeçalho](../../imagens/cabecalho.png)

# Projeto 1: Duelo de dados

Dois jogadores escolhem números de 1 a 6, durante um máximo de cinco rondas, e o duelo acaba logo que alguém ganhe três. O algoritmo diz quem ganhou cada ronda e quem ganhou o duelo. Neste projeto levas um problema do enunciado até um algoritmo testado e corrigido, pelos passos que a avaliação pede. Faz-se com o professor ao quadro: ele escreve, tu respondes às perguntas e escreves tudo nas tuas folhas, a lápis. Para rever: os guias [01](../01-do-problema-ao-algoritmo.md), [02](../02-pseudocodigo.md), [03](../03-decisoes-e-validacao.md) e [04](../04-repeticao-e-padroes.md), e a parte de testar e depurar do [guia 05](../05-testar-depurar-e-melhorar.md#um-algoritmo-que-parece-certo-ainda-não-está-provado).

## O jogo

> Dois jogadores disputam um duelo de até cinco rondas. Em cada ronda, o jogador 1 escolhe um número inteiro de 1 a 6 e escreve-o. Depois, o jogador 2 faz o mesmo. Quem escolher o número maior ganha a ronda. O algoritmo escreve "Ronda para o jogador 1" ou "Ronda para o jogador 2". Se os dois escolherem o mesmo número, escreve "Ronda empatada". O duelo termina logo que um jogador ganha três rondas ou quando se completam cinco rondas. Ganha o duelo quem ganhou mais rondas. O algoritmo escreve então "Ganhou o jogador 1" ou "Ganhou o jogador 2".

Por exemplo, se o jogador 1 escolher 4 e o jogador 2 escolher 2, o algoritmo escreve "Ronda para o jogador 1". Se o jogador 1 escolher 3 e o jogador 2 escolher 6, escreve "Ronda para o jogador 2".

## Passo 1: o contrato

Lê o enunciado duas vezes. Na segunda, de lápis na mão, sublinha os números e as mensagens que o algoritmo tem de escrever. Sublinha também as palavras que dizem quando acontece cada coisa, como "em cada ronda" e "o duelo termina".

Depois, escreve o contrato: as entradas, as saídas, as restrições e as condições, e as decisões sobre o que o enunciado não diz. É dele que saem os resultados esperados do passo 2. Rever: [O contrato do problema: entradas, saídas, restrições e condições](../01-do-problema-ao-algoritmo.md#o-contrato-do-problema-entradas-saídas-restrições-e-condições) e [O que o contrato supõe e o que decide](../03-decisoes-e-validacao.md#o-que-o-contrato-supõe-e-o-que-decide).

Responde a estas perguntas a lápis, na margem da folha:

1. Qual é o menor e o maior número de rondas que o duelo pode ter? Quantos valores são lidos em cada ronda? Por que ordem?
2. Que valores pode ter cada entrada? Pode aparecer um 0, um 7 ou um 2,5? Que palavras do enunciado te deixam responder a isto? O algoritmo não verifica estes números: que suposição escreves nas entradas?
3. Que números do enunciado fixam os limites do jogo e nunca mudam? Como se escreve cada um desses valores no pseudocódigo?
4. O que é que o algoritmo escreve em cada ronda jogada? E o que escreve uma vez, no fim do duelo?
5. Que situações diferentes podem acontecer numa ronda? E no fim do duelo, quando se comparam as rondas que cada jogador ganhou?

### O que o enunciado não diz

A pergunta 5 leva-te a uma situação de que o enunciado não fala. Pensa em todos os finais possíveis, contando as rondas ganhas de cada um. Há algum para o qual a última frase do enunciado não diga o que escrever? Rever: [Instruções ambíguas](../01-do-problema-ao-algoritmo.md#instruções-ambíguas).

6. Que final é esse, e o que diz o enunciado sobre ele?
7. Que decisões possíveis vês? Para cada uma, pensa em duas coisas: é justa para os dois jogadores? Obriga a mudar alguma coisa que o enunciado fixou, como o máximo de rondas?
8. Porque é que esta decisão tem de ficar escrita já, no passo 1, e não depois de o algoritmo estar feito?

Antes de passares ao passo seguinte: o contrato tem as quatro partes, a suposição nas entradas e a decisão numa linha "Decisão:".

## Passo 2: a tabela de casos esperados, antes do algoritmo

Escreve a tabela de casos esperados antes de haver algoritmo. O resultado esperado calcula-se a partir do enunciado e do contrato. Calculado depois de ver o que o algoritmo escreve, era o algoritmo a concordar consigo próprio. Rever: [O resultado esperado decide-se antes de executar](../05-testar-depurar-e-melhorar.md#o-resultado-esperado-decide-se-antes-de-executar) e [A tabela de casos esperados](../05-testar-depurar-e-melhorar.md#a-tabela-de-casos-esperados).

Cada caso é um duelo inteiro. Escreve cada ronda como um par entre parênteses, com o valor do jogador 1 primeiro. O par (4, 2) quer dizer que o jogador 1 escolheu 4 e o jogador 2 escolheu 2. Prepara sempre cinco pares, um por cada ronda possível. Se alguém ganhar três rondas antes, os pares seguintes ficam por ler, e servem para mostrar que o algoritmo para a tempo. A coluna "Rondas lidas" diz quantos pares se leem.

O resultado esperado é a mensagem de cada ronda jogada e a mensagem do fim, sem as perguntas aos jogadores. As rondas abreviam-se: J1 para "Ronda para o jogador 1", J2 para "Ronda para o jogador 2" e E para "Ronda empatada". A mensagem do fim escreve-se por inteiro. Um algoritmo que acerta no fim e escreve mal uma ronda está errado, e só uma tabela com as rondas o mostra. Para calcular o esperado, decide cada ronda pelo enunciado e faz um risco ao lado de quem a ganhou.

| N.º | Tipo | Entradas preparadas, ronda a ronda | Rondas lidas | Resultado esperado | Porque foi escolhido |
| ---: | --- | --- | ---: | --- | --- |

Deixa espaço à direita para as colunas "Resultado obtido" e "Passou?", que se preenchem no passo 5.

Cada caso diz o seu tipo: normal, de fronteira ou inválido. Rever: [Casos normais, de fronteira e inválidos](../05-testar-depurar-e-melhorar.md#casos-normais-de-fronteira-e-inválidos). Este jogo tem fronteiras em três sítios: em cada ronda, no fim do duelo e na paragem à terceira vitória. Não há casos inválidos, porque o contrato diz que essas entradas ficam de fora.

Responde antes de escreveres os casos:

1. Numa ronda, que pares estão no limite entre ganhar e perder a ronda, e quais ficam a um ponto dele?
2. No fim do duelo, que resultado em rondas ganhas está no limite entre um vencedor e o outro? Qual é a menor diferença de rondas ganhas com que um jogador ainda ganha o duelo?
3. O duelo não pode acabar sem se jogar nenhuma ronda. Há algum duelo em que nenhum jogador chega a ganhar uma ronda? O que esperas que o algoritmo escreva nesse duelo?
4. Consegues escrever o resultado esperado de um duelo em que os dois ganharam o mesmo número de rondas sem a decisão do passo 1? Porquê?
5. Que pares preparados ficam por ler quando um jogador chega à terceira vitória? Como verificas que o algoritmo não joga uma ronda a mais?
6. Se ninguém chegar a três vitórias nas cinco rondas, como se decide o vencedor? Pode alguém ganhar com menos de três?
7. Cada mensagem do enunciado aparece no resultado esperado de pelo menos um caso? E a mensagem da decisão do passo 1, se ela criar uma?

Antes de passares ao passo seguinte: a tabela tem paragens à terceira vitória para os dois jogadores e casos que chegam à quinta ronda.

## Passo 3: o algoritmo

Escreve o algoritmo na forma das aulas. A tabela do passo 2 é o alvo: para cada caso, o algoritmo tem de escrever exatamente o resultado esperado. Se não souberes como se escreve uma linha, escreve-a em frases claras. Rever: [A forma do pseudocódigo nas aulas](../02-pseudocodigo.md#a-forma-do-pseudocódigo-nas-aulas) e [Frases claras também valem](../02-pseudocodigo.md#frases-claras-também-valem).

Antes da primeira linha, decompõe o problema em três partes:

- o que se faz uma vez, antes do ciclo;
- o que se repete em cada ronda;
- o que se faz uma vez, depois do ciclo.

As palavras que sublinhaste no passo 1 dizem o que vai para cada parte. Rever: [Decompor um problema em subproblemas](../01-do-problema-ao-algoritmo.md#decompor-um-problema-em-subproblemas).

Antes de cada decisão, responde à pergunta que lhe diz respeito. Rever: [Escolher entre Enquanto e Para](../04-repeticao-e-padroes.md#escolher-entre-enquanto-e-para), [Um ciclo com duas maneiras de acabar](../04-repeticao-e-padroes.md#um-ciclo-com-duas-maneiras-de-acabar) e [O contrário de um intervalo](../03-decisoes-e-validacao.md#o-contrário-de-um-intervalo).

1. `Enquanto` ou `Para`? Sabe-se o número exato de rondas ou apenas o máximo? Em que situações deve o ciclo continuar?
2. O que acontece em cada ronda, e por que ordem? Que linha faz passar à ronda seguinte, e onde fica? Escreve as ações por palavras, antes de pensares em pseudocódigo.
3. Para decidir, no fim, quem ganhou o duelo, o que é que o algoritmo tem de ir guardando ao longo das rondas? Que padrão do guia 04 é este?
4. Além do número da ronda, quantas variáveis dessas são precisas? O enunciado manda escrever quantas rondas ficaram empatadas? Uma variável que é atualizada e nunca é usada faz falta? Decide e justifica.
5. Onde nasce cada uma dessas variáveis, antes do ciclo ou dentro dele? A condição do ciclo precisa desses valores? E se eles voltarem a zero em cada ronda?
6. Os números escolhidos aparecem pela primeira vez dentro do ciclo. Em que linha levam o tipo? Quantas vezes pode essa linha executar-se?
7. Dentro do ciclo, a ronda tem três resultados possíveis. Por que ordem fazes as perguntas, e qual dos três fica no `Senão`? Precisas de escrever a condição desse último, ou o `Senão` chega? Porquê?
8. Onde fica a decisão do duelo, dentro do ciclo ou depois dele? O que aparecia no ecrã se ficasse no sítio errado?
9. Se a decisão do passo 1 criou uma mensagem nova, que ramo do `Se` do fim a escreve?

Antes de passares ao passo seguinte, olha para o algoritmo, e não para a tabela. Há algum ramo de um `Se` por onde nenhum caso passa? É a pergunta da coluna "Com o algoritmo escrito", em [Duas maneiras de escolher casos](../05-testar-depurar-e-melhorar.md#duas-maneiras-de-escolher-casos). Se houver, acrescenta um caso que passe por ele, com o resultado esperado calculado pelo enunciado.

## Passo 4: a tabela de iterações

Faz, na tua folha, a tabela de iterações de um dos casos, com uma linha por cada teste da condição do ciclo. Rever: [A tabela de iterações](../04-repeticao-e-padroes.md#a-tabela-de-iterações).

| Teste | Ronda | Número do jogador 1 | Número do jogador 2 | Rondas ganhas pelo jogador 1 | Rondas ganhas pelo jogador 2 | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | ---: | ---: | --- | --- |
| | | | | | | | |

Na condição, escreve os valores no lugar das variáveis e o resultado. Em "Durante a iteração", escreve o que é lido, que condição da ronda dá `true`, que mensagem aparece e que contador muda.

Responde a estas perguntas à medida que a tabela avança:

1. Se só pudesses fazer a tabela de iterações de um dos casos, qual escolhias? Porquê esse?
2. Para o caso escolhido, quantas rondas vão ser jogadas? Quantas linhas terá a tabela, contando o último teste, que dá `false`?
3. Na primeira linha, que valores têm as colunas dos números escolhidos? Porquê?
4. Depois de uma ronda empatada, que colunas mudam na linha seguinte, e quais ficam iguais?
5. Na última linha, que parte da condição faz o ciclo parar? Quanto vale o número da ronda nesse momento?
6. Depois da última linha, que instruções são executadas, e que mensagem aparece no fim? Bate certo com o resultado esperado que escreveste no passo 2?

Antes de passares ao passo seguinte: a tabela tem a linha do último teste, o que dá `false` e faz sair do ciclo.

## Passo 5: executar os outros casos e completar a tabela

Executa os outros casos, sem uma tabela inteira para cada um. Segue cada ronda pela cadeia de decisões, anota a mensagem e faz um risco no contador que muda. Quando o duelo terminar, aplica a decisão do fim aos riscos e confirma que não leste pares depois da terceira vitória. Rever: [Testar é comparar o obtido com o esperado](../05-testar-depurar-e-melhorar.md#testar-é-comparar-o-obtido-com-o-esperado) e [A tabela de trace](../02-pseudocodigo.md#a-tabela-de-trace).

Preenche, caso a caso, as colunas "Resultado obtido" e "Passou?".

Responde a estas perguntas:

1. Se um caso falhar, onde pode estar o erro? Há dois sítios possíveis.
2. Se descobrires que um resultado esperado estava mal calculado, podes corrigi-lo? De onde tem de vir o valor novo: do enunciado ou do resultado obtido?
3. Todos os casos passarem prova que o algoritmo está certo? Qual dos teus casos apanharia mais erros, se o algoritmo os tivesse, e porquê?

Antes de passares ao passo seguinte: todos os casos têm o resultado obtido e a coluna "Passou?" preenchida.

## Passo 6: depurar o erro

Depura o erro com o método do guia 05, e escreve o registo de depuração, uma linha por passo do método. Se nenhum caso falhou, depura a versão com o erro que aparece no quadro. Guarda as duas versões do algoritmo, a versão com o erro e a corrigida. Rever: [Depurar com método](../05-testar-depurar-e-melhorar.md#depurar-com-método), [Corrigir a causa e não o sintoma](../05-testar-depurar-e-melhorar.md#corrigir-a-causa-e-não-o-sintoma) e [O registo de depuração](../05-testar-depurar-e-melhorar.md#o-registo-de-depuração).

| Passo do método | O que se escreve |
| --- | --- |
| Erro observado | O caso que falhou, o resultado esperado, o resultado obtido e a mensagem que está errada; e o caso mínimo |
| Hipótese | Uma frase sobre a causa, que pode ser verdadeira ou falsa |
| Verificação com o trace | O que a tabela de iterações mostrou: a primeira linha onde uma variável fica com um valor diferente do que devia ter |
| Correção | A instrução que mudou, e onde, mudando o menos possível |
| Novo teste | O resultado de voltar a executar a tabela inteira, e não só o caso que falhou |

Antes da correção, pensa nisto:

1. Dos erros de [Quatro erros que vais encontrar muitas vezes](../05-testar-depurar-e-melhorar.md#quatro-erros-que-vais-encontrar-muitas-vezes), qual te parece mais provável num algoritmo como este? Que caso da tabela o apanhava?
2. Como simplificas um caso, até chegares ao caso mínimo, sem desrespeitar as regras de quando o duelo acaba?
3. A correção que vais escrever explica porque é que o valor ficou errado, ou só o acerta no fim?

## Antes de terminares

Os projetos 1 e 2 não contam para a avaliação prática, porque são feitos com ajuda. O trabalho neles conta no empenho e na autonomia, como o das outras aulas. As folhas de cada projeto ficam no teu portefólio, uma capa, e podes consultá-las na avaliação.

- [ ] O contrato tem as quatro partes e as decisões, com a suposição nas entradas e a decisão numa linha que começa por "Decisão:".
- [ ] A tabela de casos foi escrita antes do algoritmo, e cada caso tem o tipo e a razão da escolha.
- [ ] Cada mensagem do enunciado, e a da decisão, se ela criar uma, aparece no resultado esperado de pelo menos um caso.
- [ ] A tabela tem paragens à terceira vitória para os dois jogadores e casos que chegam à quinta ronda.
- [ ] Nenhum ramo de um `Se` ficou sem caso.
- [ ] A tabela de iterações tem a linha do último teste.
- [ ] Todos os casos têm o resultado obtido e a coluna "Passou?" preenchida.
- [ ] O registo de depuração tem as cinco linhas, e tens a versão com o erro e a corrigida.
- [ ] Na capa do portefólio estão as folhas do projeto: o problema e o contrato, o pseudocódigo, os testes e as correções.

A seguir vem o [projeto 2, Adivinha o número](05-projeto-2-adivinha-o-numero.md), em pares.

![Rodapé](../../imagens/rodape.png)
