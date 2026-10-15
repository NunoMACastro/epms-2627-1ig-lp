![Cabeçalho](../imagens/cabecalho.png)

# Do problema ao algoritmo

Módulo Desenvolver algoritmos. Este guia mostra como se pensa um problema antes de o resolver. Explica o que é um algoritmo e como se escreve o contrato de um problema. Explica também como se parte um problema em partes mais pequenas e como se encontram as instruções que deixam dúvidas. Lê-se em cerca de 100 minutos, e não precisa de ser de uma vez. Para praticar, há a [ficha de exercícios](01-do-problema-ao-algoritmo-exercicios.md) deste tema.

Este é o primeiro tema da área de algoritmos, e não precisas de saber nada de programação. Neste tema, nada se escreve numa linguagem de programação, e nada precisa de um computador a executar código. Trabalhas em papel, e os algoritmos escrevem-se em português, em passos numerados. A forma própria de os escrever, o pseudocódigo, é o assunto do tema seguinte. Não tens de decorar tudo de uma vez. Lê com calma, volta à explicação quando um exemplo não fizer sentido, e usa os exemplos para confirmar que percebeste.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Programar é dar instruções a quem as cumpre à letra
4. O que é um algoritmo
5. Algoritmia e programação
6. Ação e estado
7. Instruções ambíguas
8. O contrato do problema: entradas, saídas, restrições e condições
9. Decompor um problema em subproblemas
10. Os quatro princípios do pensamento computacional
11. As etapas para construir um algoritmo
12. Exemplo guiado: o atendimento por senhas numa papelaria
13. Exemplo guiado: os Missionários e Canibais
14. Erros frequentes
15. Palavras novas deste guia
16. Verificar o que aprendeste
17. O que vem a seguir
18. Para saber mais

## O que vais aprender

No fim deste guia, consegues:

- explicar por palavras tuas o que é um algoritmo, que propriedades tem de ter e o que distingue a algoritmia da programação;
- reconhecer num problema concreto os quatro princípios do pensamento computacional: decomposição, reconhecimento de padrões, abstração e algoritmo;
- distinguir uma ação do estado que ela altera, e seguir o estado de uma situação passo a passo numa tabela;
- escrever o contrato de um problema: as entradas, as saídas, as restrições e as condições, com exemplos concretos e o resultado esperado de cada um;
- partir um problema grande em subproblemas mais pequenos, que se possam resolver e verificar um a um;
- explicar porque é que uma instrução ambígua não chega para determinar uma solução, e reescrevê-la sem deixar dúvidas.

## O que já sabes e vais usar

- Ler com atenção um texto curto, do ensino básico. Neste guia vais ler cada enunciado duas vezes, a segunda com um lápis na mão.
- Fazer contas simples com números pequenos, da matemática do ensino básico: somar, subtrair, multiplicar e comparar. Por exemplo, "18 menos 14 dá 4" ou "4 vezes 4 dá 16".

Se já jogaste os Missionários e Canibais numa aula, vais reconhecer o jogo no segundo exemplo guiado deste guia. Desta vez vais percebê-lo devagar, jogada a jogada. Se não jogaste, não faz mal, porque o guia explica-o desde o enunciado.

## Programar é dar instruções a quem as cumpre à letra

Um **programa** é um conjunto de instruções que um computador executa, uma de cada vez, pela ordem em que estão escritas. Chama-se **programar** a escrever essas instruções.

Para perceberes o que isto implica, imagina que tens de explicar a um robô como se faz uma sandes de manteiga. Dizes "põe manteiga no pão". Uma pessoa percebia logo: abria a embalagem, tirava manteiga com uma faca e espalhava-a numa fatia. O robô não percebe nada disso. Pega na embalagem fechada e pousa-a em cima do pão, que é exatamente o que lhe disseste. Não o fez para te contrariar. Fez o que estava dito, porque é a única coisa que sabe fazer.

Um computador é esse robô. Não adivinha intenções, não completa frases a meio e não pensa "de certeza que ele queria dizer outra coisa". É muito rápido e nunca se cansa, mas faz à letra o que lhe mandam, incluindo os erros.

Nos programas de gestão, de que trata o teu curso, isto tem consequências bem concretas. Imagina o programa de stock de uma papelaria com a instrução "quando se vende um artigo, tira uma unidade ao stock". Parece completa. Agora imagina que alguém regista, por engano, a venda de três cadernos de um modelo que já tinha stock zero. O programa tira três unidades, como lhe mandaram, e o stock desse caderno passa a ser menos três. Nenhuma prateleira do mundo tem menos três cadernos. O computador não errou, porque cumpriu a instrução. Quem errou foi quem a escreveu, porque não pensou no que devia acontecer quando o stock não chega.

É por isso que a parte difícil de programar raramente é a linguagem. A parte difícil é saber, com toda a precisão, o que se quer pedir. E isso inclui os casos em que as coisas não correm como é costume. Este tema trata disso.

## O que é um algoritmo

Usas algoritmos todos os dias, sem lhes chamar isso. Uma receita de bolo parte de ingredientes, segue passos por ordem e chega a um bolo. As instruções de montagem de um móvel partem de peças soltas e chegam a um armário. As indicações que dás a alguém para chegar a tua casa também são um algoritmo, se forem boas.

Um **algoritmo** é uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.

Cada parte desta definição está lá por uma razão. Vê-as uma a uma, com um exemplo de cada vez:

- "Sequência" quer dizer que os passos têm uma ordem, e que trocar a ordem costuma mudar o resultado. Calçar as meias e depois os sapatos são os mesmos dois passos que calçar os sapatos e depois as meias. O resultado é muito diferente. Num armazém, não se pode dar entrada no stock das caixas recebidas antes de as contar, porque ainda não se sabe quantas são. A razão da ordem é quase sempre esta. Um passo precisa de uma coisa que o anterior produziu.
- "Finita" quer dizer que acaba, e que está escrito quando acaba. As indicações "anda sempre em frente" nunca te levam à escola, porque não dizem onde parar. Um algoritmo que nunca termina nunca chega a dar a resposta, e por isso não resolve nada.
- "Claro" quer dizer que cada passo só se pode ler de uma maneira. Se dois colegas lerem o mesmo passo e fizerem coisas diferentes, o passo não está claro. Este é o defeito mais comum de todos, e tem um nome, ambiguidade, que a secção "Instruções ambíguas" explica.
- "Possível de executar" quer dizer que quem segue o algoritmo consegue fazer o passo com o que tem à frente. "Conta quantas senhas foram entregues hoje" é executável, porque basta olhar para o número da última senha. "Adivinha quantos clientes vão aparecer amanhã" não é, porque ninguém tem essa informação.
- "Parte de uns dados e chega a um resultado" quer dizer que se sabe bem de onde o algoritmo parte e onde chega. Na secção do contrato, vais dar-lhes os nomes técnicos: entradas e saídas.

No mundo da gestão, que é o do teu curso, os algoritmos estão em todo o lado, muitas vezes com o nome de procedimento. Vê, por exemplo, o que faz o funcionário de um armazém quando chega mercadoria de um fornecedor. A mercadoria vem acompanhada de uma **guia de remessa**, que é o papel que diz o que foi enviado. O funcionário faz assim:

1. Contar as caixas que o transportador descarregou.
2. Comparar esse número com o número de caixas escrito na guia de remessa.
3. Se os dois números forem iguais, assinar a guia.
4. Se forem diferentes, escrever na guia quantas caixas chegaram de facto, assinar e avisar o fornecedor da diferença.
5. Dar entrada no stock das caixas que chegaram de facto.

É um algoritmo. Tem uma ordem e acaba no passo 5. Cada passo diz o que fazer. Parte de dados, as caixas e a guia, para chegar a um resultado, a guia assinada e o stock atualizado. Repara no passo 4. Diz o que acontece quando as coisas não correm como é costume. É isso que separa um algoritmo a sério de uma descrição por alto.

Quando olhas para um algoritmo, deves conseguir apontar sempre estas quatro coisas:

1. as entradas, isto é, o que ele recebe;
2. as regras de processamento, isto é, o que faz com o que recebeu;
3. uma saída observável, isto é, o resultado, que tem de se conseguir ver ou verificar;
4. uma **condição de paragem**, isto é, o momento em que se sabe que terminou.

Se faltar alguma, o algoritmo ainda não está completo. No algoritmo do armazém, as entradas são as caixas descarregadas e a guia de remessa. As regras são a contagem e a comparação. A saída é a guia assinada e o stock atualizado. A paragem é o passo 5.

Há uma forma honesta de testar se um conjunto de passos é mesmo um algoritmo. Dá-o a outra pessoa, que não sabe o que estás a pensar, e vê se ela chega ao mesmo resultado que tu. Se tiver de te perguntar alguma coisa, há um passo que não está claro.

## Algoritmia e programação

A **algoritmia** é o trabalho de pensar, escrever e verificar algoritmos. Não depende de nenhuma linguagem de programação. Um algoritmo pode escrever-se em português, em passos numerados, como o do armazém, ou num desenho com setas. Pode também escrever-se numa notação própria, o pseudocódigo, que vais aprender no tema seguinte.

A **programação** é o trabalho de passar um algoritmo para uma linguagem de programação, como o Python, que o computador consegue executar. Nesta disciplina vais aprender as duas coisas, por esta ordem: primeiro algoritmos, nesta área, e depois Python.

A ordem não é por acaso. Se não sabes que passos resolvem um problema, nenhuma linguagem te ajuda, porque a linguagem só serve para escrever passos que já conheces. E um erro de raciocínio encontrado no papel custa cinco minutos a corrigir. O mesmo erro, escondido no meio de um programa, pode custar uma tarde inteira a encontrar. Por isso a ordem certa é sempre a mesma: compreender o problema, estruturar a solução e só depois programar. Quem salta os dois primeiros passos escreve código que não sabe explicar e fica bloqueado em decisões simples.

Há ainda outra razão. O mesmo algoritmo pode ser escrito em muitas linguagens diferentes, e as linguagens mudam ao longo dos anos. O raciocínio que resolve o problema fica. Aprender algoritmia é aprender a parte do trabalho que não fica desatualizada.

## Ação e estado

Esta distinção vai acompanhar-te o ano inteiro, e por isso merece ser bem percebida desde já.

O **estado** é o conjunto de valores que descrevem uma situação num determinado momento. É uma fotografia: quantas pessoas estão na fila, que senha está a ser atendida, quantos cadernos há na prateleira, agora, antes de mais nada acontecer.

Uma **ação** é um passo que muda o estado: chamar a senha seguinte, vender um caderno, receber uma caixa de um fornecedor.

O marcador de um jogo de futebol é um bom exemplo do dia a dia. O estado é o resultado e o minuto de jogo, por exemplo "2 a 1 ao minuto 60". Um golo é uma ação que muda o estado. Depois dele, o marcador passa a "2 a 2" ou a "3 a 1". Se quiseres saber quem está a ganhar, não precisas de rever o jogo todo. Olhas para o estado.

Numa papelaria que atende por senha, o estado podia ser "está a ser atendida a senha 14 e há 6 pessoas à espera". Chamar a senha seguinte é uma ação. Depois dela, o estado passa a ser "está a ser atendida a senha 15 e há 5 pessoas à espera". Repara que a ação é sempre a mesma, "chamar a senha seguinte", mas o estado a que ela leva depende do estado de onde parte.

Isto tem uma consequência que vais encontrar muitas vezes. A mesma ação, feita em estados diferentes, pode ter resultados muito diferentes, e às vezes nem faz sentido. Chamar a senha seguinte quando há 6 pessoas à espera é o funcionamento normal. Chamar a senha seguinte quando não há ninguém à espera é chamar em voz alta um número que ninguém tem. Por isso muitos passos de um algoritmo começam por olhar para o estado ("há alguém à espera?") antes de fazer a ação.

A condição de paragem de um algoritmo também é uma pergunta sobre o estado. O atendimento acaba quando o estado for "já não há ninguém à espera e já não se entregam senhas". Um jogo acaba quando o estado for o objetivo.

Para acompanhar o estado ao longo de um algoritmo, usa-se uma tabela. Tem uma coluna para cada valor que interessa e uma linha para cada momento. Cada linha mostra o estado depois de uma ação. Vais usar tabelas destas nos dois exemplos guiados deste guia. No tema seguinte, vão ter nome próprio: tabelas de trace, da palavra inglesa que quer dizer rasto.

Quando, mais à frente, uma solução tua não funcionar, a pergunta mais útil é quase sempre esta. Qual era o estado antes deste passo, e qual é o estado depois? Quem só olha para as ações não encontra o erro. Quem olha para o estado encontra, porque um erro é quase sempre um passo depois do qual o estado ficou diferente do que devia.

## Instruções ambíguas

Lê esta instrução de uma receita: "junta sal q.b."

"Q.b." quer dizer "quanto baste". Para uma pessoa que já cozinhou muitas vezes, isto chega. Para quem nunca cozinhou, e para um computador, não é instrução nenhuma. Quanto é que basta? Uma pitada? Uma colher? Duas pessoas que sigam esta receita produzem resultados diferentes, e nenhuma delas está a desrespeitar a receita. É isso que significa uma instrução **ambígua**: admite mais do que uma leitura, e por isso não determina uma solução. Se a mesma instrução pode levar a dois resultados, o algoritmo não diz qual deles é o certo. A este defeito chama-se **ambiguidade**.

A ambiguidade aparece de cinco formas. Cada uma procura-se de maneira diferente, e por isso ajuda conhecê-las pelo nome.

A primeira é a palavra vaga, que devia ser um número e não é. Por exemplo, "aquece um bocado", "espera um pouco" ou "se houver muitas pessoas na fila, chama um colega". Quanto tempo é um bocado? Quantas são muitas pessoas? Procura-se pelas palavras típicas: muito, pouco, grande, pequeno, algum, suficiente, q.b.

A segunda é o limite que não diz se inclui a fronteira. Imagina a regra de uma loja: "as encomendas grandes seguem por transportadora". Grande quanto? Corrigida uma vez, a regra passa a "as encomendas com mais de 10 kg seguem por transportadora". Está melhor, mas ainda falta uma coisa. E uma encomenda com exatamente 10 kg? "Mais de 10" deixa-a de fora, mas quem lê à pressa pode achar que a inclui. Fica resolvido quando quem escreve pensa no caso dos 10 kg exatos e o decide de propósito. Por exemplo, "as encomendas com 10 kg ou mais seguem por transportadora". Os valores que ficam exatamente em cima de um limite chamam-se **casos de fronteira**, e são os que mais erros escondem.

A terceira é a informação que falta. "Liga ao fornecedor": a qual deles, se a loja trabalha com vários, e para que número? "Repõe o artigo em falta": que artigo, se nenhum passo anterior disse qual era? Aqui não há nenhuma palavra vaga para sublinhar. O que há é uma pergunta sem resposta. Só a encontras se, ao ler cada passo, perguntares "tenho tudo o que preciso para fazer isto?".

A quarta é a frase que se pode ler de duas maneiras. "Arredonda o valor": para cima ou para baixo, e com quantas casas decimais? "A encomenda é entregue em 2 dias": dias úteis, ou dias seguidos, contando o fim de semana? As duas leituras são razoáveis, e é por isso que a frase é perigosa. Cada pessoa acha que a sua leitura é a óbvia.

A quinta é a unidade em falta. "Cada caixa leva no máximo 10." Dez quê? Dez livros, ou dez quilos? A resposta muda tudo, e a frase não a dá.

Quando procurares ambiguidades num texto, usa as cinco formas como lista de verificação. Há alguma palavra vaga? Algum limite que não diz se inclui a fronteira? Alguma informação em falta? Alguma frase com duas leituras? Alguma unidade em falta? E pensa sempre no que acontece quando a situação não é a normal.

Corrigir uma ambiguidade é quase sempre substituir o que é vago por um número, um limite ou uma regra. Por exemplo, "junta 3 gramas de sal", "espera 30 segundos" ou "se estiverem 8 ou mais pessoas na fila, chama um colega". Também pode ser preciso acrescentar o que acontece quando a situação não é a normal, como fez o passo 4 do algoritmo do armazém.

Há um cuidado que não podes esquecer. Quando o enunciado não te dá a informação de que precisas, não inventes em silêncio. Pergunta a quem escreveu o enunciado. Se não for possível, toma uma decisão e escreve-a, para que quem ler a tua solução saiba de que decisão ela parte. Uma decisão escrita pode ser discutida e mudada. Uma decisão tomada em silêncio só se descobre quando o resultado sai errado.

Reler o que escreveste ajuda pouco a encontrar ambiguidades. Tu sabes o que querias dizer, e a tua cabeça preenche as falhas sem dares por isso. A forma mais segura é dar as instruções a outra pessoa e pedir-lhe que as execute exatamente como estão escritas, sem te perguntar nada. Cada vez que ela hesitar, ou fizer uma coisa diferente da que esperavas, encontraste uma ambiguidade. A culpa é da instrução, e não de quem a executou. Experimenta-o com um colega, sempre que escreveres instruções para outra pessoa seguir.

## O contrato do problema: entradas, saídas, restrições e condições

Antes de escrever qualquer passo, responde a quatro perguntas sobre o problema. Esta é a ferramenta mais útil de todo o tema, e vais usá-la no início de todos os problemas até ao fim do ano.

| Pergunta | O que procuras |
| --- | --- |
| Entradas | Que dados já tenho, ou vou receber, para trabalhar? |
| Saídas | Que resultado tem de ser produzido? |
| Restrições | Que limites e regras fixas a solução tem de respeitar sempre? |
| Condições | Que situações diferentes podem acontecer e obrigam a fazer coisas diferentes? |

Às respostas a estas quatro perguntas junta-se uma lista de exemplos concretos, cada um com o resultado que se espera. Tudo junto, escrito antes de haver algoritmo, chama-se o **contrato do problema**. Vais ver cada parte com calma.

### Entradas

As **entradas** são os dados que o algoritmo recebe, ou que já existem quando ele começa. Para cada entrada, o contrato diz o que é e que tipo de valor tem. O valor pode ser um número inteiro, um número com casas decimais ou um texto. O contrato diz também em que unidade está e que valores são aceitáveis. "Número da senha do cliente, inteiro de 1 a 40" é uma entrada bem descrita. "A senha" não é.

Nem todas as entradas são números escritos num papel. Num atendimento, a chegada de um cliente é uma entrada. É uma coisa que vem de fora e a que o algoritmo tem de responder.

### Saídas

As **saídas** são o resultado que o algoritmo produz, e têm de ser observáveis: tem de se conseguir ver ou verificar se estão certas. Uma confusão frequente é escrever uma ação no lugar da saída. No armazém, "dar entrada no stock" é uma ação. A saída é o stock atualizado, com o número de caixas de cada artigo, que se consegue ler e conferir.

Para separar entradas de saídas, faz a cada dado esta pergunta. Isto já existe antes de eu começar, ou sou eu que o produzo? O que já existe é entrada. O que produzes é saída. Para não as trocares, preenche sempre a tabela das quatro perguntas antes de escreveres os passos.

### Restrições

As **restrições** são os limites e as regras fixas que valem sempre, em todas as vezes que o algoritmo é usado. Por exemplo, "a loja só distribui 40 senhas por dia", "há um só balcão" ou "o armazém só recebe entregas nos dias úteis". Uma restrição não é uma coisa que possa acontecer ou não. Está sempre lá.

Alguns números do enunciado também ficam aqui, apesar de não serem limites. Imagina que o enunciado diz que "cada atendimento demora, em média, 4 minutos". Esse valor não é uma entrada, porque ninguém o volta a escrever cada vez que o algoritmo é usado. É uma regra fixa do problema. No tema seguinte, estes valores fixos vão ter um nome próprio: constantes.

### Condições

As **condições** são situações que podem acontecer ou não, e que, quando acontecem, obrigam a fazer uma coisa diferente. Por exemplo, "se o cliente chamado não aparecer, passa-se à senha seguinte" ou "se já não houver senhas, informa-se o cliente". Escrevem-se quase sempre com "se": se isto acontecer, faz-se aquilo; se não acontecer, faz-se outra coisa.

A diferença entre restrição e condição confunde muita gente, por isso repara neste teste. Pergunta-te se isto vale sempre, em qualquer situação. Se vale, é uma restrição. Pode acontecer numa vez e não acontecer noutra, e muda o caminho quando acontece? Então é uma condição. Há outro teste rápido. Se não conseguires escrever uma condição como uma frase com "se", provavelmente é uma restrição.

Muitas vezes as duas andam juntas, e perceber como ajuda a distingui-las. A restrição "no máximo 40 senhas por dia" vale sempre. Mas é dela que nasce a condição "ainda há senhas, ou já se entregaram as 40?". É a pergunta que se faz cada vez que chega um cliente. A restrição é a regra. A condição é o momento em que o algoritmo verifica a regra e escolhe o caminho.

### Exemplos concretos

Os **exemplos concretos** são entradas escolhidas com cuidado, cada uma com a saída que se espera, calculada à mão, sem algoritmo nenhum. Servem para duas coisas. Antes de escreveres o algoritmo, mostram se percebeste o problema. Se não consegues calcular à mão o resultado de um exemplo, ainda não o percebeste. Depois de escreveres o algoritmo, servem de teste. O algoritmo tem de dar exatamente aqueles resultados, e se não der, está errado.

Um bom conjunto de exemplos não tem só o **caso normal**, aquele que toda a gente imagina ao ler o enunciado. Tem também casos de fronteira, com valores em cima dos limites, e **casos extremos**, que obrigam a tomar decisões que o enunciado não tomou.

### Um contrato completo: o tempo de espera

Vê as cinco partes a funcionar num problema pequeno.

> Uma papelaria atende os clientes por senha, com um só balcão. Quer pôr um ecrã ao lado da máquina de senhas que mostre a cada cliente quanto tempo vai esperar. Cada atendimento demora, em média, 4 minutos.

As entradas são duas. A primeira é o número da senha do cliente, um número inteiro de 1 a 40. A segunda é o número da última senha chamada, que é a do cliente que está a ser atendido ao balcão. Também é um número inteiro de 1 a 40. Aqui foi preciso tomar uma decisão. O ecrã só é ligado depois de chamada a primeira senha do dia, e por isso a última senha chamada nunca é zero. A decisão ficou escrita, e com isso o contrato deixa claro que o caso "ainda ninguém foi chamado" não é da conta deste algoritmo.

A saída é a mensagem que aparece no ecrã: um número de minutos, ou uma frase quando não faz sentido mostrar minutos.

As restrições são as regras fixas: cada atendimento conta 4 minutos, e o cliente que está ao balcão conta como um atendimento inteiro. Esta segunda regra também é uma decisão. O ecrã não sabe há quanto tempo começou o atendimento que está a decorrer. Por isso conta-o inteiro, para não prometer ao cliente menos tempo do que ele vai esperar.

As condições são três. A senha do cliente pode ser maior do que a última chamada, e o cliente ainda tem de esperar. Pode ser igual, e é a vez dele. Ou pode ser menor, e a senha dele já foi chamada.

Os exemplos concretos, calculados à mão, são estes:

| Senha do cliente | Última senha chamada | O ecrã mostra | Porque é que este caso foi escolhido |
| ---: | ---: | --- | --- |
| 18 | 14 | 16 minutos | Caso normal: à frente do cliente estão a senha 14, ao balcão, e as senhas 15, 16 e 17, à espera |
| 15 | 14 | 4 minutos | Logo acima da fronteira: o cliente é o próximo e só espera pelo atendimento que está a decorrer |
| 14 | 14 | É a sua vez | Fronteira: a senha do cliente é igual à última chamada |
| 9 | 14 | A sua senha já foi chamada | Caso extremo: a vez do cliente já passou |

Cada linha ensina uma coisa diferente.

A primeira linha é o caso que toda a gente imagina. O cliente da senha 18 tem quatro atendimentos à frente. São o da senha 14, que está a decorrer, e os das senhas 15, 16 e 17. São 4 atendimentos de 4 minutos, 16 minutos ao todo. Repara que 18 menos 14 também dá 4. A diferença entre as duas senhas diz quantos atendimentos faltam, precisamente porque decidimos contar inteiro o que está a decorrer.

A segunda linha está logo acima da fronteira entre esperar e ser atendido. O cliente da senha 15 é o próximo, e só tem de esperar que acabe o atendimento que está a decorrer: 4 minutos.

A terceira linha está exatamente em cima da fronteira, e é o momento em que a conta deixa de ser útil. O cliente da senha 14 é o que acabou de ser chamado. 14 menos 14 dá 0, e mostrar "0 minutos" seria verdade, mas o cliente ficaria sem saber que tem de se levantar. O contrato decidiu mostrar uma frase.

A quarta linha é a mais interessante, porque o enunciado não pensou nela. O cliente da senha 9 chegou atrasado, ou distraiu-se, e a vez dele já passou. A conta daria 9 menos 14, que é menos 5, e menos 5 vezes 4, que é menos 20. O ecrã mostraria "menos 20 minutos", o que não é uma resposta que se mostre a ninguém. Sem este exemplo no contrato, o algoritmo faria a conta à mesma e o ecrã mostraria esse disparate. É para isto que servem os casos extremos. Obrigam a decidir antes, em vez de descobrir depois.

Repara também no que o contrato não promete. Se um cliente chamado não aparecer, o atendimento dele não demora 4 minutos, e os que estão atrás esperam menos do que o ecrã disse. O ecrã mostra uma previsão, e não uma garantia. Escrever isto também faz parte do contrato.

### Porque se chama contrato

Chama-se contrato porque funciona como um acordo entre duas partes. Quem usa o algoritmo compromete-se a dar entradas dentro dos limites combinados, como uma senha entre 1 e 40. O algoritmo compromete-se a devolver a saída prometida. E se alguém der uma entrada fora do combinado, por exemplo a senha 57? Nesse caso, o contrato diz o que acontece, ou deixa claro que esse caso não está coberto.

A máquina de senhas da papelaria tem um contrato destes, mesmo que ninguém o tenha escrito num papel. A entrada é carregar no botão. A saída é um papel com um número. As restrições dizem que os números sobem de um em um e acabam no 40. Para usares a máquina, não precisas de saber como ela funciona por dentro, porque o contrato basta. É essa a grande vantagem de um contrato bem escrito. Separa o que o algoritmo faz de como o faz. E permite verificar se o algoritmo está certo sem ter de confiar em quem o escreveu.

## Decompor um problema em subproblemas

**Decompor** é partir um problema grande em subproblemas mais pequenos, cada um com um objetivo próprio e suficientemente simples para se resolver e verificar sozinho.

No dia a dia fazes isto sem dar por isso. Organizar uma visita de estudo parece uma tarefa enorme. Agora parte-a em quatro: "escolher o local e a data", "pedir as autorizações", "tratar do transporte" e "preparar o que se faz lá". Cada parte já se consegue pensar. E "tratar do transporte" ainda se parte em "saber quantas pessoas vão", "reservar o autocarro" e "combinar a hora e o local de partida".

Repara agora no problema "organizar o atendimento de uma loja". Assim, inteiro, é difícil de atacar. Por onde se começa? Decomposto, fica assim:

- distribuir senhas a quem chega;
- saber qual é a senha que está a ser atendida;
- chamar a senha seguinte quando o balcão fica livre;
- tratar o caso de alguém não aparecer quando é chamado;
- fechar o atendimento no fim do dia.

Cada um destes já se consegue pensar sozinho. Para distribuir senhas, basta saber qual foi a última senha entregue e se ainda há senhas. Não é preciso pensar, ao mesmo tempo, no que acontece quando alguém falta.

Um subproblema não é o mesmo que um passo. Um subproblema é um objetivo, como "chamar a senha seguinte". Os passos são a forma de o atingir. Por exemplo, "comparar a última senha chamada com a última entregue; se forem diferentes, somar 1 e anunciar o número". Primeiro decompõe-se em subproblemas, depois escrevem-se os passos de cada um. Um subproblema pode ter dez passos, e pode ele próprio voltar a ser decomposto se ainda for grande.

Os subproblemas nem sempre são independentes. Há casos em que um precisa do que outro produziu. Só se consegue chamar a senha seguinte se alguém já tiver distribuído senhas. Quando decompões, escreve também esta ordem, porque ela diz por onde começar e o que tem de estar pronto antes de quê.

Uma boa decomposição tem três sinais:

- cada subproblema tem um objetivo claro;
- cada subproblema pode ser resolvido e verificado por si só;
- o conjunto continua a resolver o problema inicial, sem deixar nada de fora.

Há dois erros opostos. Decompor de menos deixa blocos gigantes que continuam difíceis: "tratar do atendimento" não é um subproblema, é o problema outra vez com outro nome. Decompor de mais produz vinte pedacinhos que já ninguém consegue juntar, como "pegar na caneta" e "olhar para o papel". Há um critério para saber onde parar. Para de decompor quando cada parte se consegue explicar numa frase e verificar sozinha. Se uma parte ainda te parece difícil, ainda não está decomposta. Se já não consegues dizer para que serve, foste longe de mais.

## Os quatro princípios do pensamento computacional

O **pensamento computacional** é uma forma de pensar sobre problemas que torna a solução possível de executar por outra pessoa ou por uma máquina. Apesar do nome, não se trata de pensar como um computador. Também não serve só a quem trabalha com computadores. Quem organiza um armazém, planeia um horário ou escreve as regras de um torneio usa esta mesma forma de pensar.

Apresenta-se em quatro princípios: decomposição, reconhecimento de padrões, abstração e algoritmo. Não se usam por ordem, um de cada vez, como numa receita. Usam-se em conjunto, e salta-se de um para outro enquanto se pensa. Já viste dois deles com calma neste guia. Falta ver os outros dois e perceber como os quatro encaixam.

### Decomposição

É o que acabaste de ver: partir o problema em partes que se resolvem e verificam uma a uma. Nos Missionários e Canibais, que vais ver no segundo exemplo guiado, o objetivo é "levar toda a gente para o outro lado". É grande demais para se pensar de uma vez. Parte-se em "uma travessia de cada vez". Cada travessia parte-se outra vez em "escolher quem vai", "verificar se é permitido" e "atualizar quem está em cada margem". Assim, o problema passa a ser uma sequência de decisões pequenas.

### Reconhecimento de padrões

**Reconhecer padrões** é reparar no que se repete, dentro de um problema ou entre problemas diferentes, para resolver uma vez e aproveitar muitas.

Quando fazes uma soma de números grandes em coluna, repetes o mesmo processo em cada coluna. Somas os algarismos, escreves as unidades e levas o transporte para a coluna seguinte. Não aprendeste um método para as centenas e outro para os milhares. Aprendeste um padrão.

Na papelaria, cada cliente que chega passa exatamente pelos mesmos passos para receber a senha. Só muda o número. Reparar nisto significa que só tens de escrever esses passos uma vez. Também há padrões entre problemas diferentes. Pensa na fila de uma papelaria, na fila de chamadas de um serviço de apoio técnico e na fila de trabalhos de uma impressora partilhada. As três funcionam da mesma maneira, por ordem de chegada. Quem resolveu uma já tem meio caminho andado nas outras.

O erro típico é ver um padrão onde ele não se aplica sempre. Na solução dos Missionários e Canibais, quase todas as idas e voltas seguem o ritmo "vão dois, volta um". Mas há uma que não segue. Quem confiar no padrão sem verificar cada passo fica bloqueado precisamente aí. Um padrão ajuda a pensar. Não dispensa a verificação. Quando uma solução que seguia um padrão encrava, procura o passo em que o padrão deixou de funcionar. Para não te acontecer, verifica a regra em todos os passos, e não só nos que parecem perigosos.

### Abstração

**Abstrair** é ficar só com o que interessa para o problema e representá-lo da forma mais simples possível, deixando o resto de fora.

O mapa do metro é o exemplo clássico. Não mostra as distâncias reais, as ruas por cima nem as curvas dos túneis. Mostra as estações, a ordem em que aparecem e onde se muda de linha, que é tudo o que precisas para decidir onde sair. Um mapa com todos os pormenores reais seria mais verdadeiro e muito menos útil.

Para organizar a fila da papelaria, a cor da mochila do cliente, a idade dele e o que vem comprar são irrelevantes. O número da senha não é. Toda a fila pode ser descrita com dois números: a última senha entregue e a última senha chamada.

Há uma pergunta que ajuda a decidir o que fica e o que sai. Se este pormenor fosse diferente, a resposta mudava? Se muda, é um **dado relevante** e tem de entrar no problema. Se não muda, é **contexto**. Serve para tornar o enunciado agradável de ler, e podes deixá-lo de fora.

O erro típico é abstrair de mais, e deitar fora uma coisa de que precisas. Imagina que a tua descrição da papelaria deixa de fora se o cliente chamado apareceu ou não. Deixas de conseguir tratar as faltas, e a loja fica parada à espera de alguém que já foi embora. O erro contrário também existe. Quem guarda tudo por precaução perde-se no meio de pormenores que não interessam. A pergunta "se isto mudasse, a resposta mudava?" protege-te dos dois.

### Algoritmo

Depois de decompor, de reparar nos padrões e de escolher o que interessa, sobra escrever os passos. É aqui que aparece o algoritmo, tal como foi definido na secção "O que é um algoritmo". Neste tema, os passos escrevem-se em português, numerados. No tema seguinte, vais aprender uma notação própria para os escrever com mais rigor.

## As etapas para construir um algoritmo

Tudo o que viste junta-se numa sequência de etapas, que vais seguir nos dois exemplos guiados e em todos os problemas deste ano:

1. Ler o enunciado duas vezes: a primeira para perceber a história, a segunda com um lápis na mão, a sublinhar números, limites e regras.
2. Escrever o contrato: entradas, saídas, restrições, condições e exemplos concretos com o resultado esperado. Se faltar informação, perguntar, ou escrever a decisão tomada.
3. Decompor o problema em subproblemas.
4. Escrever os passos de cada subproblema, com uma ação por passo.
5. Simular os passos com os exemplos concretos, seguindo o estado numa tabela, e confirmar que os resultados batem certo com o contrato.
6. Procurar ambiguidades, de preferência dando os passos a outra pessoa, e corrigi-las.

**Simular**, na etapa 5, quer dizer seguir os passos com um caso concreto, como se fosses quem os executa, e anotar o estado numa tabela.

As etapas seguem-se por ordem, mas muitas vezes é preciso voltar a uma etapa anterior. É normal a simulação da etapa 5 mostrar que falta uma condição, e isso obriga a voltar à etapa 2 para a acrescentar ao contrato. Voltar atrás é sinal de que estás a verificar o teu trabalho, e é assim que se constrói um algoritmo que funciona.

Os dois exemplos guiados que se seguem aplicam estas etapas a problemas de natureza diferente, e é por isso que estão os dois aqui. O primeiro, a papelaria, é um processo de gestão que se repete o dia inteiro. As entradas chegam a qualquer momento, como um cliente que entra ou um balcão que fica livre. O segundo, os Missionários e Canibais, é um quebra-cabeças. Começa sempre da mesma maneira, e a solução é uma sequência de jogadas que leva a um objetivo. O método de análise serve aos dois.

## Exemplo guiado: o atendimento por senhas numa papelaria

### O problema

Uma papelaria atende os clientes por senha. Quando um cliente chega, tira uma senha com um número. Os clientes são atendidos por ordem crescente de senha. A loja tem um único balcão e distribui no máximo 40 senhas por dia. Quando um cliente é chamado e não aparece, a sua senha é descartada e passa-se à seguinte.

Queremos descrever o funcionamento do atendimento de forma suficientemente precisa para que um funcionário novo, no primeiro dia, consiga executá-lo sem perguntar nada.

### Passo 1: responder às quatro perguntas

| Pergunta | Resposta |
| --- | --- |
| Entradas | Chegada de um cliente; sinal de que o balcão ficou livre; resposta do cliente quando é chamado (aparece ou não aparece) |
| Saídas | Número de senha entregue a cada cliente; número chamado em voz alta; cliente atendido |
| Restrições | Um só balcão; no máximo 40 senhas por dia; atendimento por ordem crescente de senha |
| Condições | Ainda há senhas disponíveis ou já se esgotaram; quando o balcão fica livre, há ou não há alguém à espera; o cliente chamado aparece ou não aparece |

Vê a razão de cada linha.

As entradas deste problema não são números escritos numa folha. São acontecimentos que vêm de fora e a que o atendimento tem de responder. Um cliente entra na loja, o balcão fica livre, um cliente responde ou não responde quando ouve o seu número.

As saídas são coisas que se veem. São o papel com o número que o cliente leva na mão, o número dito em voz alta e o cliente que foi atendido.

As restrições valem o dia inteiro, faça sol ou chuva, haja muitos clientes ou poucos. Nunca há dois balcões, nunca se entregam 41 senhas, nunca se atende a senha 7 antes da 6.

As condições são bifurcações, isto é, pontos em que o caminho se divide. Vai acontecer uma coisa ou outra, e cada uma leva a passos diferentes. Repara que a primeira condição nasce da restrição das 40 senhas, como viste na secção do contrato. Repara também que a segunda condição não está escrita no enunciado. Encontra-se a pensar no estado. Se o balcão fica livre e a fila está vazia, o que se faz? O enunciado não diz, mas o algoritmo tem de dizer.

Neste problema, os exemplos concretos não são uma tabela de entradas e saídas, porque as entradas são acontecimentos ao longo do dia. O exemplo concreto é uma manhã de atendimento, com clientes que chegam e um que falta, e vais simulá-la no passo 4.

### Passo 2: decompor

O problema parte-se em quatro subproblemas:

1. Entregar senha a quem chega.
2. Chamar o próximo quando o balcão fica livre.
3. Tratar a falta de quem não aparece.
4. Fechar o dia quando já não há senhas por atender.

Cada um destes pode ser explicado numa frase e testado sozinho, e juntos resolvem o problema inteiro. É uma boa decomposição.

Porque é que se parou aqui, e não se partiu mais? Porque cada um destes já se consegue escrever em meia dúzia de passos, sem pensar nos outros ao mesmo tempo. E porque é que não se ficou por dois subproblemas, "entregar senhas" e "atender"? Porque "atender" ainda esconde duas coisas diferentes: chamar o número e decidir o que fazer se ninguém aparece.

Repara também na ordem entre eles. Chamar o próximo depende de já haver senhas entregues, e tratar a falta só acontece depois de uma chamada. Entregar senha, pelo contrário, pode acontecer a qualquer momento, mesmo enquanto alguém está a ser atendido.

### Passo 3: escrever os passos

Agora escrevemos o algoritmo em passos numerados, em português, com uma ação por passo. Ainda não é pseudocódigo nem fluxograma. Essas duas formas de escrever algoritmos são o assunto do tema seguinte. Aqui, o objetivo é a precisão, e não a notação.

Entregar senha:

1. Verificar quantas senhas já foram entregues hoje.
2. Se já foram entregues 40, informar o cliente de que as senhas terminaram e terminar.
3. Caso contrário, somar 1 ao número da última senha entregue.
4. Entregar ao cliente uma senha com esse número.
5. Registar esse número como a última senha entregue.

Repara que o passo 2 é a condição que nasceu da restrição das 40 senhas. E repara na palavra "terminar". Quer dizer que, nesse caso, os passos 3 a 5 não se fazem. Sem ela, o funcionário informava o cliente de que as senhas tinham acabado e, logo a seguir, entregava-lhe a senha 41.

Chamar o próximo:

1. Comparar o número da última senha chamada com o número da última senha entregue.
2. Se forem iguais, não há ninguém à espera: o atendimento fica parado até chegar alguém.
3. Caso contrário, somar 1 ao número da última senha chamada e anunciar esse número em voz alta.
4. Esperar 30 segundos pela resposta do cliente.
5. Se o cliente aparecer, atendê-lo e registar esse número como a última senha atendida.
6. Se o cliente não aparecer, registar esse número como descartado e voltar ao passo 1.

O terceiro subproblema, tratar a falta, acabou por caber dentro deste, nos passos 4 a 6, porque só acontece depois de uma chamada. Isto é normal. A decomposição é um plano, e ao escrever os passos percebe-se, às vezes, que duas partes vivem melhor juntas. O quarto, fechar o dia, não se escreve aqui, para o exemplo não ficar comprido. Experimenta escrevê-lo tu, em três ou quatro passos, e pergunta-te qual é a condição de paragem.

Lê com atenção os seis passos de chamar o próximo. Em "Verificar o que aprendeste", no fim deste guia, vais encontrar um algoritmo parecido. Esconde um erro fácil de cometer e difícil de ver, e é com este que o vais comparar.

### Passo 4: simular com um caso concreto

Um algoritmo só merece confiança depois de o experimentares com um caso. Vamos seguir o estado ao longo de uma manhã, com quatro clientes. O estado são dois números: a última senha entregue e a última senha chamada.

Antes de leres a tabela, tenta prever. Chegam quatro clientes, e o da senha 2 não aparece quando é chamado. No fim da manhã, quanto valem os dois números do estado? E o que acontece da última vez que o balcão fica livre?

| Momento | Última senha entregue | Última senha chamada | O que acontece |
| --- | ---: | ---: | --- |
| Abertura | 0 | 0 | A loja abre, ninguém à espera |
| Chegam quatro clientes | 4 | 0 | Cada um recebeu uma senha, da 1 à 4 |
| Balcão livre | 4 | 1 | Chamada a senha 1; o cliente aparece e é atendido |
| Balcão livre | 4 | 2 | Chamada a senha 2; o cliente não aparece; a senha é descartada |
| Ainda livre | 4 | 3 | Chamada a senha 3; o cliente aparece e é atendido |
| Balcão livre | 4 | 4 | Chamada a senha 4; o cliente aparece e é atendido |
| Balcão livre | 4 | 4 | As duas senhas são iguais: ninguém à espera; o atendimento fica parado |

No fim da manhã, as duas senhas valem 4. Da última vez que o balcão fica livre, o atendimento fica parado, porque já não há ninguém à espera.

Lê a tabela linha a linha, como se fosses o funcionário.

Na abertura, as duas senhas estão a zero, porque ainda não se entregou nem se chamou nenhuma. Quando chegam os quatro clientes, o subproblema "entregar senha" corre quatro vezes. De cada vez, a última senha entregue sobe 1: passa a 1, 2, 3 e fica em 4. A tabela mostra só o estado final dessas quatro entregas, para não ficar comprida.

Quando o balcão fica livre pela primeira vez, o passo 1 de "chamar o próximo" compara 0 com 4. São diferentes, logo há alguém à espera, e o passo 3 soma 1 e anuncia a senha 1. O cliente aparece e é atendido.

Na linha seguinte, a senha 2 é chamada e o cliente não aparece. O passo 6 descarta a senha 2 e manda voltar ao passo 1. É por isso que a linha a seguir diz "ainda livre", porque o balcão nunca chegou a ficar ocupado. A comparação dá 2 contra 4, há alguém à espera, e chama-se a senha 3.

Depois de atendida a senha 4, a última linha mostra o caso que o enunciado não previa. É o passo 1 que o trata. A última senha chamada é igual à última senha entregue, e por isso não há ninguém à espera. O estado não muda, e o atendimento fica parado até alguém tirar a senha 5.

Repara em duas coisas. Primeiro, em cada linha muda o estado, e não o algoritmo, porque os passos são sempre os mesmos. Segundo, foi a simulação que nos mostrou que o passo 6 de "chamar o próximo" tinha mesmo de voltar ao passo 1. Sem isso, um cliente que falta deixaria a loja parada para sempre.

### Passo 5: procurar ambiguidades

Antes de dar o algoritmo por bom, relê-o à procura de instruções que admitam duas leituras. Esta versão já foi corrigida uma vez. O passo 4 de "chamar o próximo" dizia "esperar um pouco pela resposta do cliente". Quanto é "um pouco"? Dois funcionários diferentes fariam coisas diferentes. Um esperava cinco segundos e descartava a senha de quem estava a caminho do balcão. Outro esperava cinco minutos, com a loja parada. Passou a 30 segundos, e deixou de haver dúvida.

Repara que o número 30 não vem do enunciado. É uma decisão, e como é uma decisão ficou escrita no algoritmo, onde qualquer pessoa a pode ver e discutir.

## Exemplo guiado: os Missionários e Canibais

Este é um quebra-cabeças clássico, e é muitas vezes o primeiro problema de algoritmia que se resolve numa aula. Vais segui-lo do enunciado até à solução completa, passo a passo, com as mesmas ferramentas do exemplo anterior.

Para seguires este exemplo, ajuda ter seis objetos pequenos de dois tipos, como três clipes e três tampas de caneta. Junta-lhes uma folha com um rio desenhado ao meio. Mexer nos objetos com as mãos enquanto lês torna o exemplo muito mais fácil de seguir.

### O enunciado

Esta versão tem pormenores a mais de propósito, para praticares a separação entre dados e contexto:

> Numa manhã de verão, três missionários e três canibais chegam à margem esquerda de um rio largo, de águas castanhas e corrente fraca. Querem todos passar para a margem direita. Encontram um pequeno barco de madeira, pintado de vermelho, com dois remos. O barco leva no máximo duas pessoas e não atravessa o rio sozinho. Há um perigo. Se, em alguma das margens, os canibais ficarem em maior número do que os missionários, os missionários são atacados e o jogo está perdido. Como é que os seis chegam todos à margem direita?

### Passo 1: ler duas vezes

A primeira leitura serve para perceber a história. Há pessoas de um lado, querem ir para o outro, há um barco pequeno e há um perigo. A segunda leitura faz-se com um lápis na mão, a sublinhar tudo o que parece um número, um limite ou uma regra. Não saltes a segunda leitura. É nela que se encontram as frases curtas que mudam tudo.

### Passo 2: separar dados de contexto

Para cada pormenor, faz a pergunta da abstração. Se isto fosse diferente, a resposta mudava?

| Pormenor do enunciado | É um dado? | Porquê |
| --- | --- | --- |
| "Numa manhã de verão" | Não | De noite ou no inverno, as travessias seriam as mesmas |
| "três missionários e três canibais" | Sim | Com outras quantidades o problema muda. Com quatro e quatro, por exemplo, deixa de ter solução com este barco |
| "margem esquerda" e "margem direita" | Sim | Dizem de onde se parte e onde se quer chegar |
| "rio largo, de águas castanhas e corrente fraca" | Não | Nada disto muda quem pode viajar com quem |
| "barco de madeira, pintado de vermelho, com dois remos" | Não | A cor, o material e os remos não mudam as travessias |
| "leva no máximo duas pessoas" | Sim | Limita cada travessia a uma ou duas pessoas |
| "não atravessa o rio sozinho" | Sim | Obriga a que alguém traga o barco de volta sempre que é preciso |
| "se os canibais ficarem em maior número do que os missionários" | Sim | É a regra que decide se uma travessia é permitida |

A frase "não atravessa o rio sozinho" é curta e discreta, e parece um pormenor. É ela que obriga a que haja viagens de regresso com alguém dentro. Sem ela, o barco podia voltar vazio e bastavam três viagens com pessoas, todas da esquerda para a direita. Quem lê só uma vez costuma passar por cima desta frase.

Repara também numa leitura cuidadosa da regra de segurança. Ela fala de os missionários serem atacados. Numa margem onde não há nenhum missionário, não há ninguém para atacar. Por isso, dois canibais sozinhos numa margem não fazem perder o jogo. Só há perigo numa margem onde haja pelo menos um missionário e mais canibais do que missionários.

### Passo 3: procurar o que falta ou se pode ler de duas maneiras

O enunciado não diz uma coisa importante. Quem está dentro do barco conta para alguma das margens? Imagina que o barco chega à margem direita com um canibal. Esse canibal conta como estando na margem direita, ou fica "no barco" e não conta?

As duas leituras são possíveis, e podem dar respostas diferentes. Como viste na secção "Instruções ambíguas", não se inventa em silêncio. Toma-se uma decisão e escreve-se. A regra usada nas aulas é esta. Quem está no barco conta na margem onde o barco está. Enquanto o barco está encostado a uma margem, quem vai nele conta nessa margem, quer esteja dentro do barco quer em terra.

Vê o que isto quer dizer em cada momento de uma travessia:

- Enquanto o barco está encostado à margem esquerda, quem já entrou nele continua a contar na margem esquerda. Entrar no barco não é sair da margem.
- Quando o barco chega à margem direita, quem vai nele passa a contar na margem direita, quer saia do barco quer fique lá dentro. Ficar sentado no barco não protege ninguém.

Voltando ao exemplo, o canibal que chega à margem direita conta como estando na margem direita, mesmo que não ponha um pé em terra.

Esta regra tem uma consequência útil. Entrar no barco não muda as contas de nenhuma margem, porque quem entra continua a contar na margem de onde vai partir. As contas só mudam quando o barco muda de lado. Por isso chega verificar a regra de segurança depois de cada travessia, e é isso que se faz daqui em diante.

Há mais duas perguntas que se respondem com o próprio enunciado. O barco pode levar uma só pessoa? Pode, porque "no máximo duas" inclui uma. O barco pode atravessar vazio? Não, porque não atravessa sozinho.

### Passo 4: escrever o contrato

| Pergunta | Resposta |
| --- | --- |
| Entradas | A situação inicial: 3 missionários e 3 canibais na margem esquerda, ninguém na margem direita, o barco na margem esquerda |
| Saídas | Uma lista de travessias, em que cada uma diz quem vai no barco e em que sentido, e que termina com as seis pessoas na margem direita |
| Restrições | Em cada travessia vão uma ou duas pessoas; o barco só parte da margem onde está, e por isso as travessias alternam de sentido; depois de cada travessia, em nenhuma margem onde haja pelo menos um missionário pode haver mais canibais do que missionários, contando quem está no barco na margem onde o barco está |
| Condições | Em cada travessia, a hipótese escolhida cumpre ou não cumpre a regra de segurança; a situação a que se chega é nova ou já aconteceu antes; chegou-se ou não ao objetivo |

As restrições são as regras do jogo escritas com rigor, e valem em todas as travessias. As condições são as perguntas que se fazem em cada travessia e que decidem o que se faz a seguir. Pode ser aceitar a travessia, experimentar outra, ou parar porque se chegou ao fim.

Como exemplos concretos, num jogo destes faz sentido verificar à mão uma ou duas jogadas antes de tentar a solução toda. Levar dois canibais na primeira travessia é permitido. A margem esquerda fica com 3 missionários e 1 canibal, e a direita com 2 canibais e nenhum missionário. Ninguém corre perigo. Levar dois missionários na primeira travessia não é permitido. A margem esquerda fica com 1 missionário e 3 canibais, e a regra falha.

Repara numa diferença em relação à papelaria. Num jogo como este, a entrada é sempre a mesma, porque o jogo começa sempre da mesma maneira. Na maior parte dos problemas deste ano, a entrada muda de cada vez que o algoritmo é usado, como a senha de cada cliente. É por isso que os exemplos concretos do contrato vão ganhar tanta importância.

### Passo 5: abstrair e escolher o estado

Para acompanhar o jogo, não precisas de desenhar o rio. Chega uma representação com três valores: quantos missionários estão na margem esquerda, quantos canibais estão na margem esquerda e de que lado está o barco. A situação inicial escreve-se (3, 3, esquerda), e o objetivo escreve-se (0, 0, direita).

Estes três valores são o estado do jogo, a fotografia de que se falou na secção "Ação e estado". Cada travessia é uma ação que muda o estado. Por exemplo, levar dois canibais a partir do início muda o estado de (3, 3, esquerda) para (3, 1, direita).

Porque é que não se escreve também a margem direita? Porque se deduz. Há sempre três missionários ao todo, e por isso os que estão na direita são 3 menos os que estão na esquerda. O mesmo para os canibais. Guardar os dois lados seria guardar a mesma informação duas vezes. E isso torna possível um erro chato, como escrever 3 missionários na esquerda e 1 na direita. Dava 4 missionários, que não existem. Uma boa representação guarda o mínimo necessário, e com isso torna alguns erros impossíveis.

E porque é que o lado do barco não pode sair? Porque, sem ele, deixas de saber quem pode viajar a seguir. Só pode viajar quem está na margem onde o barco está. Tirar o lado do barco seria abstrair de mais.

Nas tabelas deste exemplo vais ver as duas margens escritas, porque é mais fácil verificar a regra de segurança com os números à frente. Mas a direita é sempre calculada a partir da esquerda.

### Passo 6: decompor numa travessia de cada vez

O problema grande é "chegar de (3, 3, esquerda) a (0, 0, direita)". Decompõe-se numa sequência de travessias, e cada travessia decompõe-se nestes passos:

1. Ver em que margem está o barco.
2. Escolher quem vai no barco. Há apenas cinco hipóteses: um missionário, dois missionários, um canibal, dois canibais, ou um missionário e um canibal.
3. Confirmar que essas pessoas estão mesmo na margem onde está o barco.
4. Calcular a nova situação: tirar essas pessoas da margem de partida, pô-las na margem de chegada e mudar o barco de lado.
5. Verificar a regra de segurança nas duas margens.
6. Se a regra falhar, desfazer a travessia e voltar ao passo 2 com outra hipótese.
7. Se a regra se cumprir, confirmar que a nova situação não é uma que já aconteceu antes. Se for, também se volta ao passo 2, porque regressar a uma situação conhecida é andar para trás.
8. Se a nova situação for (0, 0, direita), o jogo está resolvido. Se não for, volta-se ao passo 1 para a travessia seguinte.

O passo 7 merece uma explicação. Sem ele, podias passar a tarde a levar um canibal para a direita e a trazê-lo de volta. Estavas sempre dentro das regras, e nunca avançavas. Recusar situações repetidas é o que garante que o processo acaba.

O passo 8 manda voltar ao início e fazer tudo outra vez para a travessia seguinte. Fazer os mesmos passos várias vezes chama-se **repetição**. Vai ter uma forma própria de se escrever no tema 04, Repetição e padrões. Por agora, basta dizê-lo em português com clareza, como está acima.

### Passo 7: reconhecer o padrão da verificação

Os passos 1 a 8 são iguais em todas as travessias. Só mudam os números. É o padrão de que se falou na secção dos quatro princípios. Aprendes a verificar uma travessia e sabes verificar todas.

Vê o padrão a funcionar logo na primeira travessia, experimentando as cinco hipóteses a partir de (3, 3, esquerda):

| Quem vai | Margem esquerda fica com | Margem direita fica com | A regra cumpre-se? |
| --- | --- | --- | --- |
| 1 missionário | 2 missionários e 3 canibais | 1 missionário | Não: na esquerda, 3 canibais contra 2 missionários |
| 2 missionários | 1 missionário e 3 canibais | 2 missionários | Não: na esquerda, 3 canibais contra 1 missionário |
| 1 canibal | 3 missionários e 2 canibais | 1 canibal | Sim |
| 2 canibais | 3 missionários e 1 canibal | 2 canibais | Sim |
| 1 missionário e 1 canibal | 2 missionários e 2 canibais | 1 missionário e 1 canibal | Sim |

Das cinco hipóteses, duas falham logo. As outras três são permitidas. A solução que se segue começa com dois canibais, mas começar com um missionário e um canibal também leva a uma solução.

### Passo 8: simular até ao fim

Esta é a solução completa. Cada linha é o estado depois de uma travessia. A coluna da direita mostra a verificação da regra, feita em todas as linhas e não só nas que parecem perigosas.

| Travessia | Quem vai no barco | Sentido | Margem esquerda | Margem direita | A regra cumpre-se? |
| ---: | --- | --- | --- | --- | --- |
| início | ninguém | o barco está na esquerda | 3 M, 3 C | 0 M, 0 C | Sim |
| 1 | 2 canibais | esquerda → direita | 3 M, 1 C | 0 M, 2 C | Sim: na direita não há missionários |
| 2 | 1 canibal | direita → esquerda | 3 M, 2 C | 0 M, 1 C | Sim |
| 3 | 2 canibais | esquerda → direita | 3 M, 0 C | 0 M, 3 C | Sim: na direita não há missionários |
| 4 | 1 canibal | direita → esquerda | 3 M, 1 C | 0 M, 2 C | Sim |
| 5 | 2 missionários | esquerda → direita | 1 M, 1 C | 2 M, 2 C | Sim: empates são permitidos |
| 6 | 1 missionário e 1 canibal | direita → esquerda | 2 M, 2 C | 1 M, 1 C | Sim |
| 7 | 2 missionários | esquerda → direita | 0 M, 2 C | 3 M, 1 C | Sim: na esquerda não há missionários |
| 8 | 1 canibal | direita → esquerda | 0 M, 3 C | 3 M, 0 C | Sim |
| 9 | 2 canibais | esquerda → direita | 0 M, 1 C | 3 M, 2 C | Sim |
| 10 | 1 canibal | direita → esquerda | 0 M, 2 C | 3 M, 1 C | Sim |
| 11 | 2 canibais | esquerda → direita | 0 M, 0 C | 3 M, 3 C | Sim, e é o objetivo |

Na tabela, M quer dizer missionários e C quer dizer canibais.

A travessia 6 é o momento mais difícil do jogo, e é onde muita gente fica presa. Depois da travessia 5, o barco está na margem direita, que tem 2 missionários e 2 canibais. A esquerda tem 1 missionário e 1 canibal. Alguém tem de levar o barco de volta. Antes de leres a explicação, experimenta tu as cinco hipóteses, com os objetos, e tenta perceber porque é que quatro delas não servem. Depois confirma com a lista, uma hipótese de cada vez, com o padrão da verificação:

- Se voltar 1 missionário, a direita fica com 1 missionário e 2 canibais. A regra falha.
- Se voltarem 2 missionários, a situação passa a ser a mesma que havia depois da travessia 4. É permitido, mas é andar para trás, e o passo 7 da decomposição recusa-o.
- Se voltar 1 canibal, a esquerda fica com 1 missionário e 2 canibais. A regra falha.
- Se voltarem 2 canibais, a esquerda fica com 1 missionário e 3 canibais. A regra falha.
- Se voltarem 1 missionário e 1 canibal, a esquerda fica com 2 e 2 e a direita com 1 e 1. A regra cumpre-se e a situação é nova.

Só uma hipótese faz avançar, e é a menos intuitiva de todas, porque leva de volta um missionário que tinha acabado de atravessar. É também aqui que o padrão "vão dois, volta um" deixa de funcionar. Na travessia 5 vão dois, e na 6 voltam dois. Quem seguisse o padrão sem verificar não encontrava esta saída.

Não há nenhuma solução com menos de 11 travessias. Há quatro sequências diferentes com 11 travessias, e só diferem nas duas primeiras e nas duas últimas. Qualquer uma delas é uma solução correta, porque todas cumprem o contrato.

### Passo 9: confirmar a solução contra o contrato

Uma solução não está terminada quando chega ao fim. Está terminada quando se verificou que cumpre o contrato. Para esta, confirma-se o seguinte:

- em todas as travessias vão uma ou duas pessoas;
- os sentidos alternam, a começar na esquerda, e por isso o barco parte sempre da margem onde está;
- em todas as linhas da tabela a regra de segurança se cumpre, nas duas margens;
- a última linha é (0, 0, direita), com toda a gente na margem direita;
- em todas as linhas há 3 missionários e 3 canibais ao todo, somando as duas margens.

Esta última verificação não vem do enunciado e é na mesma muito útil. Se numa linha a soma desse 5 ou 7, terias a certeza de que houve um erro de contas nessa travessia. Sabias isso mesmo antes de verificares a regra. Procurar coisas que têm de se manter sempre iguais é uma forma rápida de apanhar erros, e vais usá-la muitas vezes.

## Erros frequentes

Os erros típicos de cada ideia estão explicados na secção dela, como trocar uma restrição por uma condição ou confiar num padrão sem verificar. Aqui ficam os erros que podem aparecer em qualquer problema, e em qualquer etapa.

### Passos que dependem do que tens na cabeça

Vê-se quando outra pessoa tenta seguir os teus passos. Hesita, pergunta, ou faz uma coisa diferente da que esperavas. Acontece porque tu sabes o que querias dizer, e a tua cabeça preenche as falhas sem dares por isso. Para corrigir, dá o algoritmo a um colega e não respondas a perguntas. Cada pergunta que ele te fizer aponta para um passo que ainda não está completo. Cada passo tem de se poder executar só com o que está escrito.

### Esquecer o caso que corre mal

Vê-se quando o algoritmo funciona com o caso que imaginaste e dá um disparate quando alguma coisa falha. Já viste dois disparates destes neste guia: o stock de menos três cadernos e o ecrã a mostrar menos 20 minutos. Acontece porque, ao ler um enunciado, toda a gente imagina primeiro o caso normal. Para corrigir, pergunta "e se não houver? E se falhar? E se for zero?". Escreve as condições antes dos passos, e põe um caso extremo nos exemplos concretos.

### Começar a resolver antes de acabar de ler

Vê-se quando a solução não usa uma regra do enunciado. Nos Missionários e Canibais, por exemplo, há quem tente devolver o barco vazio, porque não leu "não atravessa o rio sozinho". Acontece porque a primeira leitura só apanha a história, e as frases curtas passam despercebidas. Para corrigir, relê o enunciado e procura uma regra que não usaste. Para que não aconteça, lê sempre duas vezes, a segunda com um lápis na mão, antes de fazeres seja o que for.

### Omitir uma etapa

Vê-se na simulação, que chega a um passo impossível. Uma etapa omitida é um passo que falta no algoritmo. Não se nota enquanto se pensa só no caso que se tinha em mente.

Nos Missionários e Canibais, a etapa que costuma faltar é o regresso do barco. Quem escreve "1. levar dois canibais; 2. levar dois canibais; 3. levar dois missionários" esqueceu-se de que o barco não volta sozinho. A tabela da simulação denuncia o erro de imediato. Depois da primeira travessia, o barco está na direita, e a segunda travessia diz "esquerda → direita", o que é impossível. Na papelaria, a etapa que costuma faltar é o "voltar ao passo 1" depois de uma falta, e a simulação do passo 4 mostrou-o.

Para que não aconteça, simula sempre numa tabela, mesmo quando a solução parece óbvia. Para corrigir, procura o exemplo mais pequeno que ainda mostra o erro. Nos Missionários e Canibais, para mostrar o regresso esquecido, não é preciso simular o jogo inteiro. Bastam duas travessias seguidas no mesmo sentido. Com o exemplo mais pequeno, a causa salta à vista. Depois de corrigires o algoritmo, é o primeiro caso que voltas a experimentar, porque é o mais rápido de verificar.

### O algoritmo nunca acaba

Vê-se ao simular. Os passos repetem-se sem fim, e nunca se chega à saída. Nos Missionários e Canibais, seria levar um canibal para a direita e trazê-lo de volta, uma e outra vez. Acontece quando falta a condição de paragem, ou quando ela nunca chega a cumprir-se. Para corrigir, procura onde está escrito que o algoritmo termina. Confirma a condição de paragem antes de dares o algoritmo por concluído.

## Palavras novas deste guia

- Programa: um conjunto de instruções que um computador executa, uma de cada vez, pela ordem em que estão escritas.
- Programar: escrever as instruções de um programa.
- Algoritmo: uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.
- Guia de remessa: o papel que acompanha a mercadoria e diz o que foi enviado.
- Condição de paragem: o momento em que se sabe que o algoritmo terminou; é uma pergunta sobre o estado.
- Algoritmia: o trabalho de pensar, escrever e verificar algoritmos.
- Programação: o trabalho de passar um algoritmo para uma linguagem de programação, que o computador consegue executar.
- Estado: o conjunto de valores que descrevem uma situação num determinado momento, como uma fotografia.
- Ação: um passo que muda o estado.
- Instrução ambígua: uma instrução que admite mais do que uma leitura, e por isso não determina uma solução.
- Ambiguidade: o defeito de uma instrução ambígua.
- Caso de fronteira: um valor que fica exatamente em cima de um limite.
- Contrato do problema: as entradas, as saídas, as restrições, as condições e os exemplos concretos, escritos antes de haver algoritmo.
- Entradas: os dados que o algoritmo recebe, ou que já existem quando ele começa.
- Saídas: o resultado que o algoritmo produz, que tem de se conseguir ver ou verificar.
- Restrições: os limites e as regras fixas que valem sempre, em todas as vezes que o algoritmo é usado.
- Condições: situações que podem acontecer ou não e que, quando acontecem, obrigam a fazer uma coisa diferente.
- Exemplos concretos: entradas escolhidas com cuidado, cada uma com a saída esperada, calculada à mão.
- Caso normal: o caso que toda a gente imagina ao ler o enunciado.
- Caso extremo: um caso que obriga a tomar uma decisão que o enunciado não tomou.
- Decompor: partir um problema grande em subproblemas mais pequenos.
- Subproblema: uma parte de um problema, com um objetivo próprio, que se resolve e verifica sozinha.
- Pensamento computacional: uma forma de pensar sobre problemas que torna a solução possível de executar por outra pessoa ou por uma máquina.
- Reconhecer padrões: reparar no que se repete, dentro de um problema ou entre problemas diferentes, para resolver uma vez e aproveitar muitas.
- Abstrair: ficar só com o que interessa para o problema e representá-lo da forma mais simples possível.
- Dado relevante: um pormenor do enunciado que, se fosse diferente, mudava a resposta.
- Contexto: um pormenor do enunciado que não muda a resposta e só o torna agradável de ler.
- Simular: seguir os passos com um caso concreto, como se fosses quem os executa, e anotar o estado numa tabela.
- Repetição: fazer os mesmos passos várias vezes.

## Verificar o que aprendeste

Responde sem olhar para o guia. Se não conseguires responder a uma pergunta, volta à secção dela.

1. O que é um algoritmo? Dá um exemplo teu, do dia a dia ou do mundo da gestão, que não esteja neste guia.
2. Qual é a diferença entre algoritmia e programação? Porque é que se aprende primeiro a algoritmia?
3. Qual é a diferença entre uma ação e o estado? Dá um exemplo de cada, tirado de uma situação tua.
4. Explica, por palavras tuas, porque é que uma receita que diz "junta sal q.b." não determina uma solução. Usa as palavras ambiguidade e estado. Uma pista: pensa no estado do prato no fim, se a receita for seguida por duas pessoas diferentes. Se conseguires explicá-lo com um exemplo teu, cumpriste o objetivo deste tema.
5. Escreve uma instrução ambígua que já tenhas ouvido ou lido. Diz qual das cinco formas de ambiguidade ela tem, e reescreve-a sem deixar dúvidas.
6. Como distingues uma restrição de uma condição? Dá um exemplo de cada, tirado do mesmo problema.
7. Num contrato, porque é que o caso normal não chega? Para que servem os casos de fronteira e os casos extremos?
8. Como sabes que já partiste um problema em subproblemas suficientes, e que não foste longe de mais?
9. Dá um exemplo teu de decomposição, outro de reconhecimento de padrões e outro de abstração.
10. Refaz numa folha a solução dos Missionários e Canibais, sem olhar para a tabela. Verifica a regra de segurança depois de cada travessia.
11. Porque é que, na travessia 6, a única escolha que faz avançar é levar de volta um missionário e um canibal?
12. Uma loja com um só balcão usa este algoritmo para chamar clientes:

    1. Somar 1 ao número da última senha chamada.
    2. Se esse número for maior do que o número da última senha entregue, não há ninguém à espera e o atendimento fica parado.
    3. Caso contrário, anunciar esse número em voz alta e atender o cliente.

    Parece bem, e funciona quase sempre. Mas há uma situação em que um cliente com senha nunca chega a ser chamado. Segue o estado passo a passo numa tabela, como a do passo 4 do primeiro exemplo guiado. A situação é esta. Foram entregues 4 senhas, e as 4 já foram chamadas e atendidas. O balcão fica livre, e só depois disso chega um cliente novo, que tira a senha 5. Em que passo está o erro, e como o corrigias? Compara depois com o algoritmo da papelaria, que já está corrigido.

13. Escreve duas ou três linhas sobre o que te custou mais neste tema, e sobre o que farias de outra maneira se voltasses a começar. Guarda-as, porque te dizem onde tens de insistir.

## O que vem a seguir

Para praticar este tema, faz a [ficha de exercícios](01-do-problema-ao-algoritmo-exercicios.md). Este tema não tem laboratório, porque tudo se faz em papel. O tema seguinte é [Pseudocódigo e fluxogramas](02-pseudocodigo-e-fluxogramas.md).

No tema seguinte vais aprender a escrever algoritmos numa notação própria, o pseudocódigo, e a lê-los num desenho com figuras e setas, o fluxograma. O estado, que aqui foram números numa tabela, passa a ter nomes próprios, chamados variáveis. A senha que está a ser atendida na papelaria vai chamar-se `senhaAtual`, e o número de pessoas à espera, `pessoasAEspera`. Os valores fixos do problema, como os 4 minutos de cada atendimento, passam a chamar-se constantes. E as tabelas do estado passam a chamar-se tabelas de trace.

O contrato continua a ser o primeiro passo de todos os problemas. Antes de escrever uma única instrução, vais sempre responder às quatro perguntas e escrever os exemplos. Guarda as análises que fizeres neste tema, na aula e na ficha, porque vais precisar delas no tema seguinte.

## Para saber mais

- [Desenvolver algoritmos, no Catálogo Nacional de Qualificações](https://catalogo.snq.gov.pt/ucDetalhe/355272): a ficha oficial desta unidade do teu curso, com as competências que ela pede.

![Rodapé](../imagens/rodape.png)
