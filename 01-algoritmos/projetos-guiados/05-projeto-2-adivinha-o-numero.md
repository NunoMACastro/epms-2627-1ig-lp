![Cabeçalho](../../imagens/cabecalho.png)

# Projeto 2: Adivinha o número

Um jogador escreve um número secreto de 1 a 100, e o outro tenta adivinhá-lo, com pistas, em 10 tentativas no máximo. A Parte 1 repete o processo do projeto 1. A Parte 2 junta-lhe a depuração do algoritmo de um colega, a melhoria desse algoritmo e a contagem dos passos antes e depois. Fazes em pares, em várias aulas, em folhas e a lápis. Em cada passo, cada um escreve na sua folha, o outro confere, e mostram ao professor antes de avançar. Para rever: os guias [01](../01-do-problema-ao-algoritmo.md), [02](../02-pseudocodigo.md), [03](../03-decisoes-e-validacao.md), [04](../04-repeticao-e-padroes.md) e [05](../05-testar-depurar-e-melhorar.md), e o [projeto 1](05-projeto-1-duelo-de-dados.md).

## O jogo

> Dois jogadores jogam ao "adivinha o número". Primeiro, o jogador 1 escreve um número secreto, sempre de 1 a 100, sem o jogador 2 ver.
>
> Depois, o jogador 2 tenta adivinhar o número, e tem no máximo 10 tentativas. Em cada tentativa escreve um número. Se o número estiver fora de 1 a 100, o algoritmo escreve "Esse número não vale. Escreve um número de 1 a 100." e pede outra vez, até o número ser válido. Um número que não vale não conta como tentativa. Se o número for igual ao secreto, o jogador 2 acertou. Se for menor do que o secreto, o algoritmo escreve "Mais alto". Se for maior, escreve "Mais baixo".
>
> O jogo acaba quando o jogador 2 acerta ou quando esgota as 10 tentativas. Se o jogador 2 acertou, o algoritmo escreve no fim "Acertaste à tentativa N!". No lugar do N fica o número da tentativa em que acertou. Se acertou em 7 tentativas ou menos, escreve a seguir "Muito bem!". Se não acertou, escreve "Perdeste! O número era S.", com o número secreto no lugar do S.

As mensagens entre aspas são estas, palavra por palavra. As perguntas antes de cada leitura escolhe-as tu. "Mais alto" quer dizer que o número secreto é mais alto do que o número que o jogador 2 acabou de escrever.

Por exemplo, se o número secreto for 63 e o jogador 2 escrever 50, o algoritmo escreve "Mais alto". Se a seguir escrever 120, o algoritmo escreve "Esse número não vale. Escreve um número de 1 a 100." e pede outro número. O 120 não conta como tentativa.

## Parte 1: do enunciado ao algoritmo testado

### Passo 1: o contrato

Escreve o contrato antes de começares a tabela do passo 2, porque é dele que saem os resultados esperados. Tem as quatro partes e as decisões, como no projeto 1, e cada decisão leva a sua razão. Rever: [O contrato do problema: entradas, saídas, restrições e condições](../01-do-problema-ao-algoritmo.md#o-contrato-do-problema-entradas-saídas-restrições-e-condições), [O que o contrato supõe e o que decide](../03-decisoes-e-validacao.md#o-que-o-contrato-supõe-e-o-que-decide) e [o passo 1 do projeto 1](05-projeto-1-duelo-de-dados.md#passo-1-o-contrato).

**a)** Escreve as entradas. Para cada uma, diz o tipo, os limites e se o algoritmo a valida ou não, e porquê. Repara que o enunciado trata os dois jogadores de maneira diferente.

**b)** Escreve as saídas: as mensagens que podem aparecer durante o jogo e as que podem aparecer no fim.

**c)** Escreve as restrições, isto é, as regras do jogo que o algoritmo tem de cumprir, com os números do enunciado.

**d)** Escreve as condições: as situações diferentes que podem acontecer numa tentativa e no fim do jogo.

**e)** Há pelo menos uma situação que o enunciado não decide. Para a encontrares, imagina um jogador 2 distraído: o que pode ele escrever que o enunciado não diga como se conta? Escreve a decisão e a razão. Para decidires, pensa no que o algoritmo teria de guardar, ao longo do jogo, para tratar essa situação de outra maneira. Pensa também no trabalho que isso dava.

Mostra ao professor antes de avançar: o contrato, com a decisão e a sua razão.

### Passo 2: a tabela de casos esperados, antes do algoritmo

Escreve a tabela de casos esperados a partir do contrato, antes de haver algoritmo. Rever: [Casos normais, de fronteira e inválidos](../05-testar-depurar-e-melhorar.md#casos-normais-de-fronteira-e-inválidos), [A tabela de casos esperados](../05-testar-depurar-e-melhorar.md#a-tabela-de-casos-esperados) e [o passo 2 do projeto 1](05-projeto-1-duelo-de-dados.md#passo-2-a-tabela-de-casos-esperados-antes-do-algoritmo).

Cada caso é um jogo inteiro: o número secreto e todos os números que o jogador 2 escreve, pela ordem, incluindo os que não valem. Ao contrário dos pares do projeto 1, cada número depende da pista anterior. Por isso, o caso só tem os números até o jogo acabar, e um algoritmo que peça mais um número falhou.

O resultado esperado tem todas as mensagens do jogo, pela ordem, sem as perguntas. Podes abreviar a mensagem do número que não vale como "Esse número não vale". Uma pista repetida três ou mais vezes seguidas escreve-se uma vez, com o número de vezes, como "Mais alto (4 vezes)".

Neste jogo, o ciclo das tentativas não pode ter zero voltas, porque o jogador 2 escreve sempre pelo menos um número.

**a)** Faz a tabela com as colunas N.º, Tipo, Número secreto, Números escritos pelo jogador 2, Resultado esperado e Porque foi escolhido. Deixa espaço à direita para as duas colunas que se preenchem depois de executar, Resultado obtido e Passou?.

**b)** A tabela tem de ter, pelo menos, casos para estas situações:

- um jogo normal, curto, com pistas dos dois tipos;
- o jogo com o menor número de tentativas;
- o jogo com o maior número de tentativas, de cada uma das maneiras como pode acabar;
- os dois lados da fronteira do "Muito bem!";
- os casos de fronteira de cada limite do intervalo de 1 a 100;
- dois números que não valem, escritos seguidos;
- a situação que decidiste no passo 1.

Um caso pode testar duas coisas ao mesmo tempo, desde que a coluna "Porque foi escolhido" diga as duas. Nos jogos compridos, escolhe números fáceis de seguir, por exemplo de 10 em 10. Quando dois casos mostram os dois lados de uma fronteira, faz com que só difiram no fim. Se um passar e o outro falhar, o problema está na fronteira.

Mostra ao professor antes de avançar: a tabela preenchida até ao resultado esperado e, para cada fronteira, os casos de um lado e do outro.

### Passo 3: as peças do algoritmo

Antes de escreveres o algoritmo, decide a estrutura, como o exemplo guiado do guia 04 faz em [As peças do ciclo](../04-repeticao-e-padroes.md#as-peças-do-ciclo). Este algoritmo tem um ciclo com duas maneiras de acabar, como o do projeto 1, e uma validação repetida dentro desse ciclo. Rever: [Um ciclo com duas maneiras de acabar](../04-repeticao-e-padroes.md#um-ciclo-com-duas-maneiras-de-acabar), [Um ciclo dentro de outro](../04-repeticao-e-padroes.md#um-ciclo-dentro-de-outro), [Padrão flag](../04-repeticao-e-padroes.md#padrão-flag) e [Escolher entre Enquanto e Para](../04-repeticao-e-padroes.md#escolher-entre-enquanto-e-para).

Responde por escrito, em poucas palavras:

**a)** O enunciado fala em 10 tentativas. Explica numa frase porque é que, mesmo assim, o ciclo das tentativas tem de ser um `Enquanto` e não um `Para`.

**b)** Escreve as duas maneiras de o jogo acabar, cada uma como uma condição que dá `true` quando essa maneira aconteceu.

**c)** Escreve a condição de continuar, a que vai na linha do `Enquanto`.

**d)** Depois do ciclo, como fica o algoritmo a saber por qual das duas maneiras o jogo acabou? Há uma forma de decidir que parece certa e falha num dos casos da tua tabela. Escreve essa forma e o caso em que falha.

**e)** Diz onde fica a validação repetida e onde fica a linha que soma 1 às tentativas. Um número que não vale não pode contar.

Mostra ao professor antes de avançar: as cinco respostas.

### Passo 4: o algoritmo

Escreve o algoritmo completo, na forma das aulas, com as peças que decidiste no passo 3. Os números fixos do enunciado são constantes. Uma linha de que não te lembres pode ficar em frases. Rever: [A forma do pseudocódigo nas aulas](../02-pseudocodigo.md#a-forma-do-pseudocódigo-nas-aulas) e [Frases claras também valem](../02-pseudocodigo.md#frases-claras-também-valem).

Antes de mostrares, confere estas cinco coisas, com o dedo por baixo de cada linha:

- cada variável recebe um valor antes de ser usada pela primeira vez, incluindo as que aparecem na condição do `Enquanto` logo no primeiro teste;
- a validação repetida tem a condição do número que não vale, e o seu corpo volta a ler o número;
- a linha que soma 1 às tentativas é executada uma vez por cada número válido, e nunca por um número que não vale;
- dentro do ciclo das tentativas, há uma atualização que, mais cedo ou mais tarde, torna a condição falsa;
- a decisão do fim depende da razão por que o ciclo parou, como respondeste no passo 3.

Mostra ao professor antes de avançar: o algoritmo completo.

### Passo 5: a tabela de iterações do caso normal

A tabela de iterações tem uma linha por cada teste da condição do ciclo das tentativas. A última é a do teste que dá `false`. Um valor lido durante uma iteração só aparece na coluna dessa variável na linha seguinte. Rever: [A tabela de iterações](../04-repeticao-e-padroes.md#a-tabela-de-iterações).

**a)** Faz a tabela de iterações do teu caso normal, com estas colunas:

| Teste | Uma coluna por cada variável que muda | Condição, com cada parte e o conjunto | Durante a iteração |
| --- | --- | --- | --- |
| | | | |

Em "Durante a iteração", escreve o número lido, o que a validação faz com ele e o que aparece no ecrã.

**b)** Por baixo da tabela, escreve o que acontece depois do ciclo: que condições são avaliadas, com que resultado, e o que aparece no ecrã.

**c)** Compara o ecrã com o resultado esperado do caso normal, na tabela do passo 2.

Mostra ao professor antes de avançar: a tabela de iterações e a comparação.

### Passo 6: executar a tabela de casos

Executa os outros casos da tua tabela, sem uma tabela de iterações para cada um. Segue o algoritmo tentativa a tentativa, e anota num rascunho o número lido, o valor das tentativas e o que aparece no ecrã. Executa o que está escrito, linha a linha, e não o que achas que o algoritmo devia fazer. Rever: [Testar é comparar o obtido com o esperado](../05-testar-depurar-e-melhorar.md#testar-é-comparar-o-obtido-com-o-esperado) e [A tabela de trace](../02-pseudocodigo.md#a-tabela-de-trace).

**a)** Para cada caso, preenche as duas colunas que faltam: o resultado obtido e se o teste passou.

**b)** Agora olha para o algoritmo, e não para a tabela. Há alguma linha por onde nenhum caso passou? Esta é a segunda pergunta de [Duas maneiras de escolher casos](../05-testar-depurar-e-melhorar.md#duas-maneiras-de-escolher-casos). Se houver, acrescenta um caso que passe por ela, com o resultado esperado escrito antes de o executares.

Mostra ao professor antes de avançar: a tabela com todas as colunas e a resposta da alínea b).

### Passo 7: depurar o que falhou

Se algum caso falhou, não mudes linhas ao acaso. Segue os cinco passos do método e escreve o registo de depuração, uma linha por passo, como no projeto 1. Não apagues a versão com o erro: escreve a corrigida noutra folha, porque o portefólio guarda as duas. Rever: [Depurar com método](../05-testar-depurar-e-melhorar.md#depurar-com-método), [O registo de depuração](../05-testar-depurar-e-melhorar.md#o-registo-de-depuração) e [o passo 6 do projeto 1](05-projeto-1-duelo-de-dados.md#passo-6-depurar-o-erro).

Se nenhum caso falhou, escreve-o por baixo da tabela. O professor pode dar-te um caso que ainda não experimentaste, para veres se o teu algoritmo também passa nele.

Mostra ao professor antes de avançar: o registo de depuração e a versão corrigida, ou a tabela com todos os casos a passar.

## Parte 2: depurar e melhorar o algoritmo de um colega

Quando o professor confirmar o teu passo 7, entrega-te duas coisas em papel. A primeira é o algoritmo que um colega de outra turma escreveu para este mesmo jogo. A segunda é o relato de um erro que esse colega observou. Diz o número secreto, os números que o jogador 2 escreveu, o que apareceu no ecrã e o que devia ter aparecido.

O colega fez algumas escolhas diferentes das tuas, e isso não quer dizer que estejam erradas: dois algoritmos diferentes podem estar ambos certos. Para encontrares o erro, não procures as diferenças em relação ao teu. Parte do erro observado e segue o método. Guarda a folha que o professor te dá, porque vai para o portefólio.

### Passo 8: ler o algoritmo do colega, reproduzir o erro e procurar o caso mínimo

Antes de procurares um erro num algoritmo que não escreveste, tens de o perceber. Lê-o pela indentação. Vê onde começa e acaba cada ciclo e que linhas estão dentro de cada `Se`. Vê também o que se executa uma vez só, antes e depois do ciclo das tentativas. Rever: [Depurar com método](../05-testar-depurar-e-melhorar.md#depurar-com-método) e [A tabela de iterações](../04-repeticao-e-padroes.md#a-tabela-de-iterações).

Depois, reproduz o erro: faz com que ele aconteça outra vez, no papel, com o mesmo caso. Enquanto não o reproduzires, não sabes se o relato está certo, e não tens onde verificar uma hipótese.

**a)** Faz a tabela de iterações do jogo relatado, na versão do colega, com as colunas da tabela do passo 5. Confirma que o ecrã que obténs é o do relato.

**b)** Procura o caso mínimo: experimenta, na versão do colega, jogos parecidos com o relatado, mas mais curtos. Não precisas de outra tabela de iterações completa. Em cada jogo, segue só o que precisares para saber se o erro aparece ou não.

**c)** Qual é o caso mais pequeno que ainda mostra o erro? Podia ser mais curto? Porquê? Diz também o que se pode simplificar nesse caso.

Mostra ao professor antes de avançar: a tabela de iterações e as respostas às alíneas b) e c).

### Passo 9: hipótese, verificação com o trace e correção

Uma hipótese diz onde procurar e o que verificar. "O algoritmo do colega tem um erro" não é uma hipótese, porque não diz que instrução, nem com que valores. Uma boa hipótese pode ser deitada abaixo por uma única linha do trace. Rever: [Depurar com método](../05-testar-depurar-e-melhorar.md#depurar-com-método), [Quatro erros que vais encontrar muitas vezes](../05-testar-depurar-e-melhorar.md#quatro-erros-que-vais-encontrar-muitas-vezes), [Corrigir a causa e não o sintoma](../05-testar-depurar-e-melhorar.md#corrigir-a-causa-e-não-o-sintoma) e [A tabela de trace](../02-pseudocodigo.md#a-tabela-de-trace).

**a)** Escreve a tua hipótese numa frase que possa ser verdadeira ou falsa.

**b)** Faz o trace linha a linha da parte do algoritmo onde a tua hipótese diz que está o erro. Começa no estado em que o algoritmo lá chega, que tiras da tua tabela de iterações. Usa estas colunas:

| Passo | Instrução executada | Uma coluna por cada variável que essa parte usa | Condição e resultado | Ecrã |
| ---: | --- | --- | --- | --- |
| | | | | |

Diz se o trace confirma a hipótese, e qual é a linha que causa o erro. Se a deitar abaixo, formula outra com o que o trace te mostrou.

**c)** Diz qual dos quatro erros do guia 05 é este.

**d)** Corrige a causa com uma única alteração, na linha que causa o erro, de forma que o algoritmo diga o que o enunciado diz. Escreve a linha corrigida e explica a correção com as palavras do enunciado.

Mostra ao professor antes de avançar: a hipótese, o trace, o nome do erro e a correção.

### Passo 10: teste de regressão e registo de depuração

Uma correção pode estragar um caso que antes funcionava, e por isso volta-se a testar tudo: é o teste de regressão. A tua tabela da Parte 1 foi escrita a partir do contrato, e não a partir do teu algoritmo. Como o jogo é o mesmo, serve tal e qual para testar o algoritmo do colega. Rever: [Depurar com método](../05-testar-depurar-e-melhorar.md#depurar-com-método) e [O registo de depuração](../05-testar-depurar-e-melhorar.md#o-registo-de-depuração).

**a)** Executa a tabela inteira na versão corrigida do algoritmo do colega, como no passo 6, e preenche o resultado obtido e se passou.

**b)** Escreve o registo de depuração desta correção, com as cinco linhas. Outra pessoa tem de perceber o erro e a correção só pelo registo.

Mostra ao professor antes de avançar: a tabela executada e o registo de depuração.

### Passo 11: melhorar sem mudar o que o algoritmo faz

A versão corrigida passa em todos os testes. Agora pergunta-se se faz trabalho desnecessário. Há uma parte do corpo do ciclo das tentativas que faz perguntas cujas respostas o algoritmo já conhece. Usa a terceira maneira de fazer menos passos do guia 05: não voltar a perguntar o que já se sabe. Rever: [Melhorar um algoritmo sem mudar o que ele faz](../05-testar-depurar-e-melhorar.md#melhorar-um-algoritmo-sem-mudar-o-que-ele-faz), [Seleção encadeada](../03-decisoes-e-validacao.md#seleção-encadeada) e [Condições que não se sobrepõem e que cobrem todos os casos](../03-decisoes-e-validacao.md#condições-que-não-se-sobrepõem-e-que-cobrem-todos-os-casos).

A versão melhorada tem de escrever exatamente o mesmo que a corrigida, para qualquer jogo que o contrato aceite. A equivalência mostra-se de duas maneiras, e as duas são precisas: com uma explicação, que cobre todos os jogos, e com testes.

**a)** Escreve a parte do algoritmo que muda, já melhorada. Basta essa parte, porque o resto fica igual.

**b)** Explica, numa ou duas frases, porque é que a cadeia escreve sempre o mesmo que os três `Se`.

**c)** Volta a testar. Executa na versão melhorada três casos da tua tabela: o caso normal, o caso que mostrou o erro e o que acaba sem acertar. Confirma que dão exatamente o mesmo ecrã que na versão corrigida.

Mostra ao professor antes de avançar: a parte melhorada, a explicação e os três testes.

### Passo 12: contar os passos antes e depois

Conta com a regra do guia 05. Uma condição com `e` ou com `ou` conta um passo. Não te esqueças do `Enquanto` da validação. Mesmo quando o número é válido à primeira, a sua condição é avaliada uma vez, e essa avaliação conta. Rever: [Contar passos](../05-testar-depurar-e-melhorar.md#contar-passos).

Conta os passos de um jogo curto: o número secreto é 30, e o jogador 2 escreve 50, 20 e 30.

**a)** Conta os passos da versão corrigida e da versão melhorada, por partes. Faz uma tabela com uma coluna para cada versão e uma linha para cada parte:

- antes do ciclo;
- uma iteração com "Mais baixo";
- uma iteração com "Mais alto";
- a iteração em que o jogador acerta;
- a última avaliação da condição do ciclo;
- depois do ciclo.

Cada iteração conta a avaliação do `Enquanto` que a abre.

**b)** Soma as partes deste jogo nas duas versões e calcula a diferença.

**c)** Diz, numa frase, em que tipo de iteração a versão melhorada poupa mais passos, e porquê.

Mostra ao professor antes de avançar: a tabela de partes, os dois totais e a resposta da alínea c).

## Antes de terminares

O projeto fica no portefólio de cada um dos dois, ao lado do projeto 1: as tuas folhas e a folha do colega, na capa. Não conta para a avaliação prática, mas podes consultá-lo nela.

- [ ] O contrato tem a decisão e a razão.
- [ ] A tabela de casos foi escrita antes do algoritmo, com as fronteiras do ciclo, do "Muito bem!" e do intervalo de 1 a 100.
- [ ] O algoritmo passa em todos os casos da tabela.
- [ ] A resposta d) do passo 3 diz como o algoritmo sabe porque é que o jogo acabou.
- [ ] O registo de depuração do algoritmo do colega tem as cinco linhas, e percebe-se o erro e a correção só por ele.
- [ ] Depois da correção, a tabela inteira foi executada outra vez.
- [ ] A versão melhorada dá o mesmo ecrã, e os passos das duas versões foram contados com a mesma regra.
- [ ] Na capa do portefólio estão as folhas do projeto: o problema e o contrato, o pseudocódigo, os testes, as correções e a contagem de passos.
- [ ] A folha do colega também está na capa, com a depuração e a versão melhorada.

O projeto 3 é a avaliação prática: individual, com um problema novo e o mesmo processo.

![Rodapé](../../imagens/rodape.png)
