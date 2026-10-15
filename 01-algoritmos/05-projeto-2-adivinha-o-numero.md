![Cabeçalho](../imagens/cabecalho.png)

# Projeto 2: Adivinha o número

Um jogador escreve um número secreto de 1 a 100, e o outro tenta adivinhá-lo, com pistas, em 10 tentativas no máximo. O projeto faz-se em pares, em cerca de duas horas de aula: 70 minutos para a Parte 1 e 56 para a Parte 2.

## Para que serve este projeto

Nos exercícios das fichas treinaste cada coisa à parte: um ciclo, uma validação, um contador, uma tabela de casos, uma depuração. Num problema a sério, tudo isto aparece junto, e é preciso saber por que ordem se faz cada coisa. É para isso que servem os três projetos que fecham a unidade de algoritmos.

Os três seguem o mesmo processo, que é o do exemplo guiado do guia 05, o do inventário:

1. o contrato;
2. a tabela de casos esperados, escrita antes de haver algoritmo;
3. o algoritmo;
4. a tabela de iterações e os testes;
5. se algum teste falhar, a depuração, com o seu registo;
6. por fim, a melhoria, com os passos contados antes e depois.

O passo 6, a melhoria, entra a partir deste projeto.

No projeto 1, o duelo de dados, viste o professor fazer este processo ao quadro, a pensar em voz alta. Neste projeto és tu que o fazes, com um colega, um passo de cada vez, e o professor confirma cada passo antes de avançarem. No projeto 3, a avaliação prática, vais fazê-lo sozinho, num problema novo.

Por isso este projeto é um ensaio. O que interessa é perceber porque se faz cada passo e porque vem por aquela ordem, mesmo que leve tempo. Assim, no dia da avaliação, a ordem já é tua.

O jogo deste projeto traz uma coisa que os exercícios ainda não tinham: um ciclo que pode acabar de duas maneiras diferentes. O jogo acaba quando o jogador acerta, mas também acaba quando se esgotam as tentativas. No fim, o algoritmo tem de saber qual das duas coisas aconteceu, para escrever a mensagem certa. É uma estrutura que aparece em muitos problemas, e que vais voltar a encontrar.

Este projeto fica no teu portefólio e não conta para a avaliação prática, porque é feito com ajuda. O trabalho que fazes nele conta, como o das outras aulas, no empenho e na autonomia. Podes consultá-lo durante a avaliação prática.

## O que precisas de saber

Este projeto não traz nenhuma instrução nova de pseudocódigo. Usa o que aprendeste nos guias anteriores, sobretudo nos guias 03, 04 e 05, juntando-o num problema maior.

- O contrato de um problema, com as quatro perguntas, e as ambiguidades, que se decidem e se escrevem: guia [01 Do problema ao algoritmo](01-do-problema-ao-algoritmo.md).
- A forma de pseudocódigo das aulas e o trace linha a linha: guia [02 Pseudocódigo e fluxogramas](02-pseudocodigo-e-fluxogramas.md).
- A cadeia `Se`, `Senão se`, `Senão`, em que a primeira condição verdadeira ganha: guia [03 Decisões e validação](03-decisoes-e-validacao.md).
- Os operadores `e`, `ou` e `não`, incluindo o `não` à frente de uma variável `bool`, como em `não pago`, do guia 03.
- Os intervalos e o contrário de um intervalo, escrito com `ou`, do guia 03.
- A regra para escrever o contrário de uma condição: guia 03, secção "Operador `não`". Troca-se o `e` pelo `ou`, ou o `ou` pelo `e`, e cada parte pela sua contrária.
- As fronteiras, testadas imediatamente abaixo, em cima e imediatamente acima, do guia 03.
- O `Enquanto` e as suas três peças, a inicialização, a condição e a atualização: guia [04 Repetição e padrões](04-repeticao-e-padroes.md).
- A regra de que a condição de um ciclo diz quando continuar, e não quando parar, do guia 04.
- A tabela de iterações, o contador e a flag, do guia 04.
- A validação repetida, que volta a pedir um valor enquanto ele for inválido: guia 04, secção "Padrão validação repetida".
- A ideia de que, depois de um ciclo, a sua condição é falsa, e isso diz alguma coisa sobre o estado. Está na mesma secção do guia 04.
- O contrato com as decisões sobre as ambiguidades: guia [05 Testar, depurar e melhorar](05-testar-depurar-e-melhorar.md).
- A tabela de casos esperados, com casos normais, de fronteira e inválidos, do guia 05.
- O método de depuração em cinco passos, o registo de depuração e o teste de regressão, do guia 05.
- Os erros da secção "Quatro erros que vais encontrar muitas vezes", do guia 05.
- A diferença entre corrigir a causa e corrigir o sintoma, do guia 05.
- Melhorar sem mudar o que o algoritmo faz, as estratégias para fazer menos passos e a regra para contar passos, do guia 05.

Este projeto faz-se depois da aula em que a validação e a validação repetida são dadas. Se ainda tiveres dúvidas, relê a secção "Padrão validação repetida" do guia 04 antes de começares.

Testar e depurar não tiveram uma aula só para eles. Fizeste-o em todos os exercícios, sempre que experimentaste um algoritmo com valores e corrigiste o que não dava. Neste projeto fazes o mesmo de forma explícita, por escrito, como o guia 05 explica. Cada passo diz em que secção do guia 05 está a ferramenta de que precisas. Se ainda não leste essa secção, lê-a quando chegares ao passo.

## Como vais trabalhar

Trabalham os dois juntos, um passo de cada vez. Em cada passo, um escreve e o outro confere, com o enunciado e com o guia abertos. No passo seguinte, trocam. Os dois têm de conseguir explicar tudo o que está escrito, porque o professor pode fazer a pergunta a qualquer um. No fim, cada um guarda uma cópia do projeto no seu portefólio.

Cada passo acaba com a frase "Mostra ao professor antes de avançar". Quando chegares a essa frase, chamas o professor e mostras o que fizeram. Só passas ao passo seguinte depois de ele o confirmar. Cada passo usa o anterior. Uma decisão esquecida no contrato dá um resultado esperado errado na tabela. E um resultado esperado errado faz-te procurar um erro onde ele não está. Se o professor encontrar alguma coisa a corrigir, não te vai dar a resposta. Vai fazer-te uma pergunta, ou apontar para um caso da tua tabela, e tu corriges e voltas a mostrar. Enquanto esperas, relê a secção do guia de que vais precisar no passo seguinte.

Precisas de papel e lápis, e dos guias 03, 04 e 05 à mão.

O tempo de cada passo, no título dele, é uma estimativa para um par médio. Há passos que vão demorar mais e outros menos. O que conta é fazer cada um com cuidado.

Podes escrever o algoritmo em pseudocódigo, na forma das aulas, ou em frases claras. As frases valem, desde que não deixem dúvidas: quanto, quando, e o que acontece se não der. Não precisas de funções, mas, se quiseres usar alguma, podes. O número secreto não é sorteado. É escrito por uma pessoa, o jogador 1. Assim, cada jogo de teste pode ser repetido exatamente, com os mesmos números, as vezes que for preciso. É isso que torna possível testar e depurar o algoritmo.

## O jogo

> Dois jogadores jogam ao "adivinha o número". Primeiro, o jogador 1 escreve um número secreto de 1 a 100, sem o jogador 2 ver. O jogador 1 escreve sempre um número de 1 a 100.
>
> Depois, o jogador 2 tenta adivinhar o número, e tem no máximo 10 tentativas. Em cada tentativa escreve um número. Se o número estiver fora de 1 a 100, o algoritmo escreve "Esse número não vale. Escreve um número de 1 a 100." e pede outra vez, até o número ser válido. Um número que não vale não conta como tentativa. Se o número for igual ao secreto, o jogador 2 acertou. Se for menor do que o secreto, o algoritmo escreve "Mais alto". Se for maior, escreve "Mais baixo".
>
> O jogo acaba quando o jogador 2 acerta ou quando esgota as 10 tentativas. Se o jogador 2 acertou, o algoritmo escreve no fim "Acertaste à tentativa N!". No lugar do N fica o número da tentativa em que acertou. Se acertou em 7 tentativas ou menos, escreve também "Muito bem!". Se não acertou, escreve "Perdeste! O número era S.", com o número secreto no lugar do S.

As mensagens entre aspas são estas, palavra por palavra. As perguntas que o algoritmo faz antes de cada leitura, como a que pede o número secreto, escolhe-as tu. "Mais alto" quer dizer que o número secreto é mais alto do que o número que o jogador 2 acabou de escrever. "Mais baixo" quer dizer que é mais baixo.

Por exemplo, se o número secreto for 63 e o jogador 2 escrever 50, o algoritmo escreve "Mais alto". Se a seguir o jogador 2 escrever 120, o algoritmo escreve "Esse número não vale. Escreve um número de 1 a 100." e pede outro número. O 120 não conta como tentativa.

## Parte 1: do enunciado ao algoritmo testado (70 min)

### Passo 1: o contrato (12 min)

A ferramenta está no guia 05, no passo 1 do exemplo guiado, e na secção "O resultado esperado decide-se antes de executar".

O contrato é o que diz, sem margem para dúvidas, o que o algoritmo tem de fazer. É dele que vão sair os resultados esperados da tabela do passo 2, e por isso tem de estar completo antes de a tabela começar. Um contrato tem as respostas às quatro perguntas do guia 01. São as entradas que o algoritmo recebe, as saídas que produz, as restrições que tem de cumprir e as condições. As condições são as situações diferentes que podem acontecer.

O contrato faz-se por escrito, mesmo num jogo que parece simples. Quando lês um enunciado, a tua cabeça preenche sozinha o que ele não diz. E preenche-o de uma maneira que pode não ser a do teu colega. Escrever o contrato obriga-te a ver essas lacunas. Quando uma pergunta não tem resposta no enunciado, isso é uma **ambiguidade**, como as que aprendeste a encontrar no guia 01. O contrato decide-a, por escrito, numa linha que começa por "Decisão:" e diz a razão. Uma ambiguidade que fica por decidir volta a aparecer mais à frente, quando tiveres de escrever um resultado esperado e não souberes qual é.

**a)** Escreve as entradas. Para cada uma, diz o tipo, os limites e se o algoritmo a valida ou não, e porquê. Repara que o enunciado trata os dois jogadores de maneira diferente.

**b)** Escreve as saídas: as mensagens que podem aparecer durante o jogo e as que podem aparecer no fim.

**c)** Escreve as restrições, isto é, as regras do jogo que o algoritmo tem de cumprir, com os números do enunciado.

**d)** Escreve as condições: as situações diferentes que podem acontecer numa tentativa e no fim do jogo.

**e)** Há pelo menos uma situação que o enunciado não decide. Para a encontrares, imagina um jogador 2 distraído: o que pode ele escrever que o enunciado não diga como se conta? Quando a encontrares, escreve a decisão e a razão. Para decidires, pensa no que o algoritmo teria de guardar, ao longo do jogo, para tratar essa situação de outra maneira. Pensa também no trabalho que isso dava.

Mostra ao professor antes de avançar: o contrato, com a decisão e a sua razão.

### Passo 2: a tabela de casos esperados, antes do algoritmo (12 min)

A ferramenta está no guia 05, nas secções "Casos normais, de fronteira e inválidos", "Duas maneiras de escolher casos" e "A tabela de casos esperados". Está também no passo 2 do exemplo guiado.

Ainda não há algoritmo, e é de propósito. Os resultados esperados escrevem-se agora, a partir do contrato. Um resultado esperado calculado a olhar para o algoritmo concorda sempre com ele, e então não serve para nada. Quando, no passo 6, executares o algoritmo, é com esta tabela que vais comparar.

Neste jogo, cada caso de teste é um jogo inteiro. Tem o número secreto que o jogador 1 escreve e todos os números que o jogador 2 escreve, pela ordem, incluindo os que não valem. Escreve só os números até o jogo acabar. Se o jogo acaba à terceira tentativa, o caso não tem mais nenhum número depois dessa, porque o algoritmo já não o leria.

Na coluna do resultado esperado, escreve todas as mensagens do jogo, pela ordem em que aparecem, sem as perguntas. Para caber na tabela, podes abreviar a mensagem do número que não vale como "Esse número não vale". Uma pista repetida três ou mais vezes seguidas escreve-se uma vez, com o número de vezes, como "Mais alto (4 vezes)".

Pensa também nas fronteiras do ciclo, que são fáceis de esquecer. O guia 05 lembra que um ciclo tem as suas fronteiras. São o caso zero, em que o ciclo não chega a ter nenhuma iteração, o caso de uma só iteração e o de várias. Neste jogo, o ciclo das tentativas não pode ter zero iterações, porque o jogador 2 escreve sempre pelo menos um número. Mas tem um jogo com o menor número de tentativas e um com o maior. E o jogo com o maior número de tentativas pode acabar de mais do que uma maneira.

**a)** Faz a tabela com as colunas que se preenchem antes de executar, as cinco do guia 05. As entradas ficam divididas em duas, e as colunas são estas: N.º, Tipo, Número secreto, Números escritos pelo jogador 2, Resultado esperado e Porque foi escolhido. Deixa espaço à direita para as duas colunas que se preenchem depois, Resultado obtido e Passou?.

**b)** A tabela tem de ter, pelo menos, casos para estas situações:

- um jogo normal, curto, com pistas dos dois tipos;
- o jogo com o menor número de tentativas;
- o jogo com o maior número de tentativas, de cada uma das maneiras como pode acabar;
- os dois lados da fronteira do "Muito bem!";
- o número que não vale logo fora de cada limite (0 e 101), cada um seguido do válido mais perto (1 e 100);
- dois números que não valem, escritos seguidos;
- a situação que decidiste no passo 1.

Um caso pode testar duas coisas ao mesmo tempo, e isso é bom, desde que a coluna "Porque foi escolhido" diga as duas.

Há duas dicas para não perderes tempo. Nos jogos compridos, escolhe números fáceis de seguir, por exemplo de 10 em 10. Quando dois casos servem para mostrar os dois lados de uma fronteira, faz com que sejam quase iguais e só difiram no fim. Assim, se um passar e o outro falhar, sabes logo que o problema está na fronteira.

Mostra ao professor antes de avançar: a tabela com as colunas de antes de executar preenchidas. Para cada fronteira, diz quais são os casos que ficam de um lado e do outro.

### Passo 3: as peças do algoritmo (8 min)

A ferramenta está no guia 04, nas secções "As três peças de um ciclo", "Padrão validação repetida", "Padrão flag" e "Escolher entre Enquanto e Para". Está também no guia 03, na secção "Operador `não`", que tem a regra para escrever o contrário de uma condição.

Antes de escreveres vinte linhas, decide a estrutura. É o que faz o passo 4 do exemplo guiado do guia 04, que responde às perguntas das peças antes de escrever o pseudocódigo. Uma estrutura decidida com calma escreve-se depressa. Uma estrutura decidida a meio da escrita costuma obrigar a apagar e recomeçar.

Este algoritmo tem duas coisas que ainda não tinhas juntado.

A primeira é um ciclo com duas maneiras de acabar. Até agora, os teus ciclos acabavam por uma razão só: aparecia a sentinela, o valor ficava válido, ou o `Para` chegava ao fim. Neste jogo há duas razões, e qualquer uma delas chega para o jogo acabar. Lembra-te da regra do guia 04. A condição do `Enquanto` diz quando continuar, e não quando parar. Por isso, tens de pensar primeiro em quando o jogo para e, a partir daí, escrever a situação em que continua. E há um cuidado a ter depois do ciclo. Quando o ciclo acaba, sabes que a sua condição deu falso. Num ciclo com uma só razão para acabar, isso diz-te tudo. Num ciclo com duas, diz-te só que pelo menos uma das razões aconteceu, e não diz qual. O algoritmo precisa de saber qual foi, para escrever a mensagem certa.

A segunda é um ciclo dentro de outro ciclo. A validação repetida do guia 04 era um ciclo que pedia um valor até ele ser válido. Quando um ciclo está dentro do corpo de outro, o de dentro faz todas as suas iterações durante uma só iteração do de fora. O de fora só continua para a linha seguinte quando o de dentro tiver acabado. No pseudocódigo, o corpo do ciclo de dentro fica oito espaços para dentro, porque está dentro de dois blocos. Na tabela de iterações do ciclo de fora, o que o ciclo de dentro faz escreve-se na coluna "Durante a iteração".

Um exemplo, noutro contexto. A papelaria do guia 04 recebe dois pedidos, e cada um tem de ter de 1 a 50 unidades. A validação repetida do algoritmo `PedirQuantidadeValida`, do guia 04, fica dentro de um `Para` de dois pedidos:

```text
const QUANTIDADE_MINIMA = 1
const CAPACIDADE_MAXIMA = 50
const NUMERO_DE_PEDIDOS = 2
Para pedido de 1 até NUMERO_DE_PEDIDOS
    Escreve: "Quantidade do pedido ", pedido, " (1 a 50)?"
    int quantidade = ler valor
    Enquanto quantidade < QUANTIDADE_MINIMA ou quantidade > CAPACIDADE_MAXIMA
        Escreve: "Quantidade inválida. Escreve um número de 1 a 50."
        quantidade = ler valor
    Escreve: "Pedido aceite: ", quantidade, " unidades"
```

A pessoa escreve 0, 75, 12 e 30. Antes de leres a tabela, tenta prever: quantas vezes aparece "Quantidade inválida", e que pedidos são aceites?

| Teste | pedido | quantidade | Condição | Durante a iteração |
| --- | ---: | ---: | --- | --- |
| 1.º | 1 | sem valor | `1 <= 2` dá `true` | lê 0; a validação testa `0 < 1 ou 0 > 50`, que dá `true`: escreve "Quantidade inválida. Escreve um número de 1 a 50." e lê 75; testa `75 < 1 ou 75 > 50`, que dá `true`: escreve a mesma mensagem e lê 12; testa `12 < 1 ou 12 > 50`, que dá `false`, e a validação termina; escreve "Pedido aceite: 12 unidades" |
| 2.º | 2 | 12 | `2 <= 2` dá `true` | lê 30; a validação testa `30 < 1 ou 30 > 50`, que dá `false`, e não faz nenhuma iteração; escreve "Pedido aceite: 30 unidades" |
| 3.º | 3 | 30 | `3 <= 2` dá `false` | o ciclo termina |

"Quantidade inválida" aparece duas vezes, as duas na primeira iteração do `Para`, e os dois pedidos são aceites, com 12 e 30 unidades. A validação do primeiro pedido, com as suas duas iterações e três testes, cabe toda numa só linha da tabela do `Para`. O segundo pedido é válido à primeira: a validação testa a condição uma vez e não faz nenhuma iteração. Na linha de cada teste do `Para`, a coluna `quantidade` tem o último valor lido, o que a validação deixou passar.

Responde por escrito, em poucas palavras:

**a)** O enunciado fala em 10 tentativas. Explica numa frase porque é que, mesmo assim, o ciclo das tentativas tem de ser um `Enquanto` e não um `Para`.

**b)** Escreve as duas maneiras de o jogo acabar, cada uma como uma condição que dá `true` quando essa maneira aconteceu.

**c)** Escreve a condição de continuar, a que vai na linha do `Enquanto`.

**d)** Depois do ciclo, como fica o algoritmo a saber por qual das duas maneiras o jogo acabou? Há uma forma de decidir que parece certa, mas falha num dos casos da tua tabela. Diz qual é esse caso.

**e)** Diz onde fica a validação repetida e onde fica a linha que soma 1 às tentativas. Um número que não vale não pode contar.

Mostra ao professor antes de avançar: as cinco respostas.

### Passo 4: o algoritmo (18 min)

A ferramenta está no guia 05, no passo 3 do exemplo guiado, e em todos os exemplos do guia 04.

Agora escreve o algoritmo completo, com as peças que decidiste no passo 3. Se usares pseudocódigo, usa a forma das aulas:

- uma constante, com `const`, para cada número fixo do enunciado;
- o tipo à frente de cada variável na linha onde ela recebe o primeiro valor, e só aí;
- uma leitura dentro de um ciclo onde a variável aparece pela primeira vez leva o tipo, como `int stock = ler valor` (guia 04, "Padrão contador");
- a indentação a mostrar o que está dentro de cada ciclo e de cada `Se`.

Se preferires frases claras, numera-as, e diz em cada repetição que passos se repetem, como no exemplo em frases do guia 04.

Antes de mostrares, confere estas cinco coisas, com o dedo por baixo de cada linha:

- cada variável recebe um valor antes de ser usada pela primeira vez, incluindo as que aparecem na condição do `Enquanto` logo no primeiro teste;
- a validação repetida tem a condição do número que não vale, e o seu corpo volta a ler o número, como no guia 04;
- a linha que soma 1 às tentativas é executada uma vez por cada número válido, e nunca por um número que não vale;
- dentro do ciclo das tentativas, há uma atualização que, mais cedo ou mais tarde, torna a condição falsa;
- a decisão do fim depende da razão por que o ciclo parou, como respondeste no passo 3.

Mostra ao professor antes de avançar: o algoritmo completo.

### Passo 5: a tabela de iterações do caso normal (6 min)

A ferramenta está no guia 04, na secção "A tabela de iterações", e no guia 05, no passo 7 do exemplo guiado.

A tabela de iterações tem uma linha por cada teste da condição do ciclo das tentativas, com a fotografia do estado nesse momento. A última linha é a do teste que dá falso. Lembra-te de que um valor lido durante uma iteração só aparece na coluna dessa variável na linha seguinte.

**a)** Faz a tabela de iterações do teu caso normal, com estas colunas:

- uma para cada variável que muda durante o jogo;
- uma para a condição do ciclo, com o resultado de cada parte e o do conjunto;
- uma para o que acontece durante a iteração: o número lido, o que a validação faz com ele e o que aparece no ecrã.

Não precisas de escrever as perguntas.

**b)** Por baixo da tabela, escreve o que acontece depois do ciclo: que condições são avaliadas, com que resultado, e o que aparece no ecrã.

**c)** Compara o ecrã com o resultado esperado do caso normal, na tabela do passo 2.

Mostra ao professor antes de avançar: a tabela de iterações e a comparação.

### Passo 6: executar a tabela de casos (10 min)

A ferramenta está no guia 05, nas secções "Testar é comparar o obtido com o esperado" e "Duas maneiras de escolher casos".

Agora executa os outros casos da tua tabela. Não precisas de fazer a tabela de iterações de cada um. Segue o algoritmo, tentativa a tentativa, e anota num rascunho o número lido, o valor das tentativas e o que aparece no ecrã. Executa o que está escrito, linha a linha, e não o que achas que o algoritmo devia fazer. O guia 05 explica porquê nos erros frequentes, em "O trace que concorda sempre contigo".

**a)** Para cada caso, preenche as duas colunas que faltam: o resultado obtido e se o teste passou.

**b)** Agora olha para o algoritmo, e não para a tabela. Há alguma linha por onde nenhum caso passou? É a pergunta da caixa branca, do guia 05. Se houver, acrescenta um caso que passe por ela, com o resultado esperado escrito antes de o executares.

Mostra ao professor antes de avançar: a tabela com todas as colunas e a resposta da alínea b).

### Passo 7: depurar o que falhou (4 min, ou mais se for preciso)

A ferramenta está no guia 05, nas secções "Depurar com método" e "Corrigir a causa e não o sintoma". Está também no passo 11 do exemplo guiado, que tem o registo de depuração.

Se algum caso falhou, não mudes linhas ao acaso. Segue os cinco passos do método:

1. escreve o caso que falhou, o esperado e o obtido, e procura o caso mais pequeno que ainda mostra o erro;
2. formula uma hipótese numa frase que possa ser verdadeira ou falsa;
3. verifica-a com o trace desse caso;
4. corrige a causa, com uma alteração de cada vez;
5. volta a executar a tabela inteira.

Escreve tudo no registo de depuração, uma linha por passo. Não apagues a versão com o erro. Escreve a versão corrigida noutra folha, porque o portefólio mostra as duas.

Se nenhum caso falhou, escreve-o por baixo da tabela. O professor pode dar-te um caso que ainda não experimentaste, para veres se o teu algoritmo também passa nele.

Mostra ao professor antes de avançar: o registo de depuração e a versão corrigida, ou a tabela com todos os casos a passar.

## Parte 2: depurar e melhorar o algoritmo de um colega (56 min)

Quando o professor confirmar o teu passo 7, entrega-te duas coisas em papel. A primeira é o algoritmo que um colega de outra turma escreveu para este mesmo jogo. A segunda é o relato de um erro que esse colega observou quando o experimentou com um jogo de teste. O relato diz qual era o número secreto, que números o jogador 2 escreveu, o que apareceu no ecrã e o que devia ter aparecido.

Esse algoritmo não está neste documento. Resolve o mesmo jogo, e lê-lo antes de escreveres o teu tirava-te o mais importante da Parte 1. O mais importante é decidires tu como o ciclo acaba e como o algoritmo sabe porque acabou. Por isso só o recebes depois de teres o teu algoritmo escrito, testado e confirmado.

O colega fez algumas escolhas diferentes das tuas, e isso não quer dizer que estejam erradas. Dois algoritmos diferentes podem estar ambos certos. Para encontrares o erro, não procures as diferenças em relação ao teu algoritmo. Segue o método do guia 05, a partir do erro observado. Guarda a folha que o professor te dá, porque faz parte do teu portefólio.

### Passo 8: ler o algoritmo do colega, reproduzir o erro e procurar o caso mínimo (13 min)

A ferramenta está no guia 05, no primeiro passo de "Depurar com método", e no guia 04, na secção "A tabela de iterações".

Antes de procurares um erro num algoritmo que não escreveste, tens de o perceber. Lê-o pela indentação. Vê onde começa e acaba cada ciclo e que linhas estão dentro de cada `Se`. Vê também o que se executa uma vez só, antes e depois do ciclo das tentativas.

Depois, reproduz o erro. **Reproduzir** um erro é fazê-lo acontecer outra vez, tu próprio, no papel, com o mesmo caso. Enquanto não o reproduzires, não sabes se o relato está certo, e não tens onde verificar uma hipótese.

**a)** Faz a tabela de iterações do jogo relatado, na versão do colega. Usa uma coluna para cada variável que muda durante o jogo e uma para a condição do ciclo das tentativas. Junta uma coluna para o que acontece durante a iteração. Confirma que o ecrã que obténs é o do relato.

**b)** Procura o caso mínimo, que o guia 05 define como o caso mais pequeno que ainda mostra o mesmo erro. Experimenta, na versão do colega, jogos parecidos com o relatado, mas mais curtos. Não precisas de fazer outra tabela de iterações completa. Em cada jogo, segue só o que precisares para saber se o erro aparece ou não.

**c)** Qual é o caso mais pequeno que ainda mostra o erro? Podia ser mais curto? Porquê? Diz também o que se pode simplificar nesse caso.

Mostra ao professor antes de avançar: a tabela de iterações e as respostas às alíneas b) e c).

### Passo 9: hipótese, verificação com o trace e correção (8 min)

A ferramenta está no guia 05, nos passos 2, 3 e 4 de "Depurar com método". Está também nas secções "Quatro erros que vais encontrar muitas vezes" e "Corrigir a causa e não o sintoma".

Uma hipótese diz onde procurar e o que verificar. "O algoritmo do colega tem um erro" não é uma hipótese, porque não diz que instrução, nem com que valores. Uma boa hipótese pode ser deitada abaixo por uma única linha do trace, e é isso que a torna útil.

**a)** Escreve a tua hipótese numa frase que possa ser verdadeira ou falsa.

**b)** Faz o trace linha a linha da parte do algoritmo onde a tua hipótese diz que está o erro. Começa no estado em que o algoritmo lá chega, que tiras da tua tabela de iterações. Usa uma coluna para cada variável que essa parte usa, uma para a condição e o seu resultado e uma para o ecrã. Diz se o trace confirma a hipótese, e qual é a linha que causa o erro. Se a deitar abaixo, formula outra hipótese com o que o trace te mostrou, como manda o guia 05.

**c)** Diz qual dos erros da secção "Quatro erros que vais encontrar muitas vezes", do guia 05, é este.

**d)** Corrige a causa com uma única alteração, na linha que causa o erro, de forma que o algoritmo diga o que o enunciado diz. Escreve a linha corrigida e explica a correção com as palavras do enunciado.

Mostra ao professor antes de avançar: a hipótese, o trace, o nome do erro e a correção.

### Passo 10: teste de regressão e registo de depuração (20 min)

A ferramenta está no guia 05, no passo 5 de "Depurar com método", e no passo 11 do exemplo guiado.

Uma correção pode estragar um caso que antes funcionava. Por isso, depois de corrigir, volta-se a testar tudo, e a isso chama-se **teste de regressão**. A tua tabela de casos da Parte 1 foi escrita a partir do contrato, e não a partir do teu algoritmo. Como o jogo é o mesmo, o contrato é o mesmo, e a tabela serve tal e qual para testar o algoritmo do colega. É uma das vantagens de escrever os casos antes. Uma tabela feita a partir do contrato testa qualquer algoritmo que resolva aquele problema.

**a)** Antes de executares, confirma que a tua tabela tem os dois lados da fronteira onde o erro apareceu. Precisa de um caso em cima da fronteira, como o do relato, e de outro logo do outro lado dela. Se não tiver, acrescenta esses casos agora, com o resultado esperado escrito a partir do contrato, antes de executares.

**b)** Executa a tabela inteira na versão corrigida do algoritmo do colega, como no passo 6, e preenche o resultado obtido e se passou.

**c)** Escreve o registo de depuração desta correção, com as cinco linhas do guia 05. São o erro observado, com o caso mínimo, a hipótese, o que o trace mostrou, a correção feita e o resultado do novo teste.

Mostra ao professor antes de avançar: a tabela executada e o registo de depuração.

### Passo 11: melhorar sem mudar o que o algoritmo faz (8 min)

A ferramenta está no guia 05, nas secções "Melhorar um algoritmo sem mudar o que ele faz" e "Estratégias simples para fazer menos passos". Está também no guia 03, na secção "Condições que não se sobrepõem e que cobrem todos os casos". Nos erros frequentes desse guia, lê "Dois `Se` separados em vez de uma cadeia".

A versão corrigida passa em todos os testes. Agora, e só agora, pergunta-se se ela faz trabalho desnecessário. Há uma parte do corpo do ciclo das tentativas que faz perguntas cujas respostas o algoritmo já conhece. Usa a terceira estratégia do guia 05, não voltar a perguntar o que já se sabe.

Lembra-te da regra principal. A versão melhorada tem de escrever exatamente o mesmo que a corrigida, para qualquer jogo que o contrato aceite. A equivalência mostra-se de duas maneiras, e as duas são precisas: com uma explicação, que cobre todos os jogos, e com testes.

**a)** Escreve a parte do algoritmo que muda, já melhorada. Basta essa parte, porque o resto fica igual.

**b)** Explica, numa ou duas frases, porque é que a versão melhorada escreve sempre o mesmo que a corrigida. A explicação tem de dizer porque é que os casos que juntaste não podem acontecer ao mesmo tempo.

**c)** Volta a testar. Executa na versão melhorada três casos da tua tabela: o caso normal, o caso que mostrou o erro e o que acaba sem acertar. Confirma que dão exatamente o mesmo ecrã que na versão corrigida.

Mostra ao professor antes de avançar: a parte melhorada, a explicação e os três testes.

### Passo 12: contar os passos antes e depois (7 min)

A ferramenta está no guia 05, na secção "Contar passos", e no passo 10 do exemplo guiado.

A regra de contagem do guia, para a teres à mão, é esta:

- conta um passo cada `Escreve:` e cada atribuição executados, incluindo as leituras com `ler valor`;
- conta um passo cada avaliação da condição de um `Se`, de um `Senão se` ou de um `Enquanto`;
- uma condição com `e` ou com `ou` conta um passo;
- conta também a última avaliação de um `Enquanto`, a que dá falso;
- as linhas `const` e o `Senão` não contam.

Não te esqueças do `Enquanto` da validação. Mesmo quando o número é válido à primeira, a sua condição é avaliada uma vez, e essa avaliação conta.

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

## O que fica no teu portefólio

O projeto vai para o portefólio de cada um dos dois elementos do par. Guarda-o na pasta `portefolio-algoritmos`, de que fala a secção "O teu portefólio" do guia 05. Usa um ficheiro por peça, com o nome em minúsculas, com hífenes e sem acentos nem espaços. Os traces feitos em papel também contam. Fotografa-os ou passa-os a limpo.

| Peça | Nome do ficheiro |
| --- | --- |
| O enunciado e o contrato, com a decisão | `adivinha-o-numero-contrato.txt` |
| A tabela de casos, com os resultados obtidos, e a tabela de iterações do caso normal | `adivinha-o-numero-testes.txt` |
| O teu algoritmo e, se o corrigiste, a versão com o erro, a versão corrigida e o registo de depuração | `adivinha-o-numero-algoritmo.txt`, e se for preciso `adivinha-o-numero-algoritmo-com-erro.txt` e `adivinha-o-numero-registo-depuracao.txt` |
| A folha com a versão do colega e o erro observado, a tabela de iterações do erro, o trace, o registo de depuração e o teste de regressão | `adivinha-o-numero-colega-depuracao.txt` |
| A versão melhorada, a explicação da equivalência e a contagem de passos | `adivinha-o-numero-colega-melhorado.txt` |

Confirma, antes de dares o projeto por acabado:

- [ ] A tabela de casos foi escrita antes do algoritmo. Tem as fronteiras do ciclo, as do "Muito bem!" e as do intervalo de 1 a 100.
- [ ] O algoritmo passa em todos os casos da tabela, e consigo explicar como ele sabe, depois do ciclo, porque é que o jogo acabou.
- [ ] O registo de depuração do algoritmo do colega tem as cinco linhas. Outra pessoa consegue perceber o erro e a correção só por ele.
- [ ] Contei os passos das duas versões com a mesma regra, e sei explicar onde está a diferença.

## O que vem a seguir

O projeto 3 é a avaliação prática individual que fecha a unidade de algoritmos, e dura 120 minutos. Vais receber um problema novo, que não é nenhum dos jogos dos projetos 1 e 2. Fazes sozinho o processo que fizeste aqui em par: o contrato, a tabela de casos antes do algoritmo, o algoritmo e os testes. Depois, com um algoritmo escrito por outra pessoa, fazes a depuração, com o registo, e a melhoria, com os passos contados. O que se observa é a lógica e o processo, e não a forma da escrita nem a rapidez. Podes ter contigo o portefólio, com os projetos 1 e 2. As outras regras vêm escritas no enunciado, e o professor mostra-te antes a grelha com os critérios.

A melhor preparação é rever este projeto, sobretudo as respostas do passo 3 e o registo de depuração do passo 10. Percebe também porque é que cada passo vem antes do seguinte.

## Para saber mais

- [A ficha oficial da unidade Desenvolver algoritmos](https://catalogo.snq.gov.pt/ucDetalhe/355272), no Catálogo Nacional de Qualificações: o que a unidade pede, com as palavras do referencial do curso.

![Rodapé](../imagens/rodape.png)
