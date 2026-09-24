![Cabeçalho](../imagens/cabecalho.png)

# Do problema ao algoritmo

UC: UC00245

Blocos: ALG01

Requisitos: UC00245-R01, UC00245-R02, UC00245-K01, UC00245-K02, UC00245-A01, UC00245-A02, UC00245-A03, UC00245-A04, UC00245-P01

| Identificação | Valor |
| --- | --- |
| Material | M-ALG01, primeiro bloco de Desenvolver algoritmos |
| Fundamento curricular | Unidade de competência UC00245, bloco ALG01 |
| Duração | 180 minutos dos 300 do bloco; os outros 120 estão na [ficha de exercícios](01-do-problema-ao-algoritmo-exercicios.md) |
| Evidência a guardar | Ficha de análise com entradas, saídas, restrições e subproblemas |

## Objetivos

No final deste bloco, serás capaz de:

- explicar por palavras tuas o que é um algoritmo, que propriedades tem de ter e o que distingue a algoritmia da programação;
- reconhecer num problema concreto os quatro princípios do pensamento computacional: decomposição, reconhecimento de padrões, abstração e algoritmo;
- distinguir uma ação do estado que ela altera, e seguir o estado de uma situação passo a passo numa tabela;
- escrever o contrato de um problema: as entradas, as saídas, as restrições e as condições, com exemplos concretos e o resultado esperado de cada um;
- partir um problema grande em subproblemas mais pequenos, que se possam resolver e verificar um a um;
- explicar por que razão uma instrução ambígua não chega para determinar uma solução, e reescrevê-la sem deixar dúvidas.

## O que precisas de saber antes

Nada de programação. Este é o primeiro guia do percurso de algoritmos, por isso não há nenhum guia anterior que tenhas de ter lido. Nada neste bloco se escreve numa linguagem de programação, e nada precisa de um computador a executar código.

Precisas de duas coisas que já trazes da escola. A primeira é ler com atenção: um texto curto, lido duas vezes, a segunda vez com um lápis na mão. A segunda é fazer contas simples com números pequenos: somar, subtrair, multiplicar e comparar, como "18 menos 14 dá 4" ou "4 vezes 4 dá 16".

Se já jogaste os Missionários e Canibais numa aula, vais reconhecer o jogo no segundo exemplo deste guia, e desta vez vais percebê-lo devagar, jogada a jogada. Se não jogaste, não faz mal: o guia explica-o desde o enunciado.

## Material e preparação

Papel e caneta, cartões de papel (ou uma folha cortada em tiras) e, se quiseres passar a limpo a tua análise, um editor de texto.

Para os Missionários e Canibais ajuda ter seis objetos pequenos de dois tipos, por exemplo três clipes e três tampas de caneta, e uma folha com um rio desenhado ao meio. Mexer nos objetos com as mãos enquanto lês torna o exemplo muito mais fácil de seguir.

## Como está organizado o tempo

Este bloco tem 5 horas, que valem 300 minutos de trabalho. Não corresponde a uma aula: as aulas têm 60 minutos, e o teu professor reparte o bloco pelas aulas que existirem.

| Parte | Onde está | Tempo |
| --- | --- | ---: |
| Teoria | Neste guia | 60 min |
| Exemplos explicados | Neste guia | 40 min |
| Prática guiada | Neste guia | 45 min |
| Prática autónoma | Na ficha | 90 min |
| Desafio opcional | Na ficha | 30 min |
| Resumo e checkpoint | Neste guia | 35 min |

A teoria é a parte mais comprida, e o tempo dos exemplos conta com o jogo dos Missionários e Canibais feito na aula. Não tens de decorar a teoria de uma vez. Lê-a com calma, volta a ela quando um exemplo não fizer sentido, e usa os exemplos para confirmar que percebeste.

## Teoria (60 min)

### Programar é dar instruções a quem as cumpre à letra

Um **programa** é um conjunto de instruções que um computador executa, uma de cada vez, pela ordem em que estão escritas. **Programar** é escrever essas instruções.

Para perceberes o que isto implica, imagina que tens de explicar a um robô como se faz uma sandes de manteiga. Dizes "põe manteiga no pão". Uma pessoa percebia logo: abria a embalagem, tirava manteiga com uma faca e espalhava-a numa fatia. O robô não percebe nada disso. Pega na embalagem fechada e pousa-a em cima do pão, que é exatamente o que lhe disseste. Não o fez para te contrariar. Fez o que estava dito, porque é a única coisa que sabe fazer.

Um computador é esse robô. Não adivinha intenções, não completa frases a meio e não pensa "de certeza que ele queria dizer outra coisa". É muito rápido e nunca se cansa, mas faz à letra o que lhe mandam, incluindo os erros.

Nos programas de gestão, que são os que vais aprender a fazer neste curso, isto tem consequências bem concretas. Imagina o programa de stock de uma papelaria com a instrução "quando se vende um artigo, tira uma unidade ao stock". Parece completa. Agora imagina que alguém regista, por engano, a venda de três cadernos de um modelo que já tinha stock zero. O programa tira três unidades, como lhe mandaram, e o stock desse caderno passa a ser menos três. Nenhuma prateleira do mundo tem menos três cadernos. O computador não errou: cumpriu a instrução. Quem errou foi quem a escreveu, porque não pensou no que devia acontecer quando o stock não chega.

É por isso que a parte difícil de programar raramente é a linguagem. A parte difícil é saber, com toda a precisão, o que se quer pedir, incluindo nos casos em que as coisas não correm como é costume. Este bloco trata exatamente disso.

### O que é um algoritmo

Um **algoritmo** é uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.

Cada parte desta definição está lá por uma razão, e vale a pena vê-las uma a uma, com um exemplo de cada vez:

- "Sequência" quer dizer que os passos têm uma ordem, e que trocar a ordem costuma mudar o resultado. Calçar as meias e depois os sapatos são os mesmos dois passos que calçar os sapatos e depois as meias, e o resultado é muito diferente. Num armazém, não se pode dar entrada no stock das caixas recebidas antes de as contar, porque ainda não se sabe quantas são.
- "Finita" quer dizer que acaba, e que está escrito quando acaba. As indicações "anda sempre em frente" nunca te levam à escola, porque não dizem onde parar. Um algoritmo que nunca termina nunca chega a dar a resposta, e por isso não resolve nada.
- "Claro" quer dizer que cada passo só se pode ler de uma maneira. Se dois colegas lerem o mesmo passo e fizerem coisas diferentes, o passo não está claro. Vais ver mais à frente que este é o defeito mais comum de todos, e que tem um nome: ambiguidade.
- "Possível de executar" quer dizer que quem segue o algoritmo consegue fazer o passo com o que tem à frente. "Conta quantas senhas foram entregues hoje" é executável: basta olhar para o número da última senha. "Adivinha quantos clientes vão aparecer amanhã" não é, porque ninguém tem essa informação.
- "Parte de uns dados e chega a um resultado" quer dizer que o algoritmo tem um ponto de partida e um ponto de chegada bem conhecidos. Mais à frente vais dar-lhes os nomes técnicos: entradas e saídas.

Usas algoritmos todos os dias sem lhes chamar isso. Uma receita de bolo parte de ingredientes, segue passos por ordem e chega a um bolo. As instruções de montagem de um móvel partem de peças soltas e chegam a um armário. As indicações que dás a alguém para chegar a tua casa também são um algoritmo, se forem boas.

No mundo da gestão, que é o do teu curso, os algoritmos estão em todo o lado, muitas vezes com o nome de procedimento. Vê, por exemplo, o que faz o funcionário de um armazém quando chega mercadoria de um fornecedor:

1. Contar as caixas que o transportador descarregou.
2. Comparar esse número com o número de caixas escrito na guia de remessa, que é o papel que acompanha a mercadoria e diz o que foi enviado.
3. Se os dois números forem iguais, assinar a guia.
4. Se forem diferentes, escrever na guia quantas caixas chegaram de facto, assinar e avisar o fornecedor da diferença.
5. Dar entrada no stock das caixas que chegaram de facto.

É um algoritmo: tem uma ordem, acaba no passo 5, cada passo diz o que fazer, e parte de dados (as caixas e a guia) para chegar a um resultado (a guia assinada e o stock atualizado). Repara no passo 4: diz o que acontece quando as coisas não correm como é costume. É isso que separa um algoritmo a sério de uma descrição por alto.

Quando olhas para um algoritmo, deves conseguir apontar sempre quatro coisas. Se faltar alguma, o algoritmo ainda não está completo:

1. as entradas, isto é, o que ele recebe;
2. as regras de processamento, isto é, o que faz com o que recebeu;
3. uma saída observável, isto é, o resultado, que tem de se conseguir ver ou verificar;
4. uma condição de paragem, isto é, o momento em que se sabe que terminou.

No algoritmo do armazém, as entradas são as caixas descarregadas e a guia de remessa; as regras são a contagem e a comparação; a saída é a guia assinada e o stock atualizado; a paragem é o passo 5.

A forma mais honesta de testar se um conjunto de passos é mesmo um algoritmo é dá-lo a outra pessoa, que não sabe o que estás a pensar, e ver se ela chega ao mesmo resultado que tu. Se tiver de te perguntar alguma coisa, há um passo que não está claro.

### Algoritmia e programação

A **algoritmia** é o trabalho de pensar, escrever e verificar algoritmos. Não depende de nenhuma linguagem de programação: um algoritmo escreve-se em português, em passos numerados, como o do armazém; num desenho com setas; ou numa notação própria, o pseudocódigo, que vais aprender no próximo bloco.

A **programação** é o trabalho de passar um algoritmo para uma linguagem de programação, como o Python, que o computador consegue executar. Nesta disciplina vais aprender as duas coisas, por esta ordem: primeiro algoritmos, nesta área, e depois Python.

A ordem não é por acaso. Se não sabes que passos resolvem um problema, nenhuma linguagem te ajuda, porque a linguagem só serve para escrever passos que já conheces. E um erro de raciocínio encontrado no papel custa cinco minutos a corrigir, enquanto o mesmo erro escondido no meio de um programa pode custar uma tarde inteira a encontrar. Por isso a ordem certa é sempre a mesma: compreender o problema, estruturar a solução e só depois programar. Quem salta os dois primeiros passos escreve código que não sabe explicar e fica bloqueado em decisões simples.

Há ainda outra razão. O mesmo algoritmo pode ser escrito em muitas linguagens diferentes, e as linguagens mudam ao longo dos anos. O raciocínio que resolve o problema fica. Aprender algoritmia é aprender a parte do trabalho que não fica desatualizada.

### Ação e estado

Esta distinção vai acompanhar-te o ano inteiro, por isso vale a pena percebê-la bem agora.

O **estado** é o conjunto de valores que descrevem uma situação num determinado momento. É uma fotografia: quantas pessoas estão na fila, que senha está a ser atendida, quantos cadernos há na prateleira, agora, antes de mais nada acontecer.

Uma **ação** é um passo que muda o estado: chamar a senha seguinte, vender um caderno, receber uma caixa de um fornecedor.

O marcador de um jogo de futebol é um bom exemplo do dia a dia. O estado é o resultado e o minuto de jogo, por exemplo "2 a 1 ao minuto 60". Um golo é uma ação que muda o estado: depois dele, o marcador passa a "2 a 2" ou a "3 a 1". Se quiseres saber quem está a ganhar, não precisas de rever o jogo todo. Olhas para o estado.

Numa papelaria que atende por senha, o estado podia ser "está a ser atendida a senha 14 e há 6 pessoas à espera". Chamar a senha seguinte é uma ação, e depois dela o estado passa a ser "está a ser atendida a senha 15 e há 5 pessoas à espera". Repara que a ação é sempre a mesma, "chamar a senha seguinte", mas o estado a que ela leva depende do estado de onde parte.

Isto tem uma consequência que vais encontrar muitas vezes: a mesma ação, feita em estados diferentes, pode ter resultados muito diferentes, e às vezes nem faz sentido. Chamar a senha seguinte quando há 6 pessoas à espera é o funcionamento normal. Chamar a senha seguinte quando não há ninguém à espera é chamar em voz alta um número que ninguém tem. Por isso muitos passos de um algoritmo começam por olhar para o estado ("há alguém à espera?") antes de fazer a ação.

A condição de paragem de um algoritmo também é uma pergunta sobre o estado. O atendimento acaba quando o estado for "já não há ninguém à espera e já não se entregam senhas". Um jogo acaba quando o estado for o objetivo.

Para acompanhar o estado ao longo de um algoritmo, usa-se uma tabela com uma coluna para cada valor que interessa e uma linha para cada momento. Cada linha mostra o estado depois de uma ação. Vais usar tabelas destas nos dois exemplos deste guia, e no próximo bloco elas vão ter nome próprio: tabelas de trace.

Quando mais à frente uma solução tua não funcionar, a pergunta que te vai salvar é quase sempre esta: qual era o estado antes deste passo, e qual é o estado depois? Quem só olha para as ações não encontra o erro. Quem olha para o estado encontra, porque um erro é quase sempre um passo depois do qual o estado ficou diferente do que devia.

### Instruções ambíguas

Lê esta instrução de uma receita: "junta sal q.b."

"Q.b." quer dizer "quanto baste". Para uma pessoa que já cozinhou muitas vezes, isto chega. Para quem nunca cozinhou, e para um computador, não é instrução nenhuma: quanto é que basta? Uma pitada? Uma colher? Duas pessoas que sigam esta receita produzem resultados diferentes, e nenhuma delas está a desrespeitar a receita. É isso que significa uma instrução **ambígua**: admite mais do que uma leitura, e por isso não determina uma solução. Se a mesma instrução pode levar a dois resultados, o algoritmo não diz qual deles é o certo.

A ambiguidade aparece de várias formas. Convém conhecê-las pelo nome, porque cada uma se procura de maneira diferente.

A primeira é a palavra vaga, que devia ser um número e não é: "aquece um bocado", "espera um pouco", "se houver muitas pessoas na fila, chama um colega". Quanto tempo é um bocado? Quantas são muitas pessoas? Procura-se pelas palavras típicas: muito, pouco, grande, pequeno, algum, suficiente, q.b.

A segunda é o limite que não diz se inclui a fronteira. Imagina a regra de uma loja: "as encomendas grandes seguem por transportadora". Grande quanto? Corrigida uma vez, a regra passa a "as encomendas com mais de 10 kg seguem por transportadora". Está melhor, mas ainda falta uma coisa: e uma encomenda com exatamente 10 kg? "Mais de 10" deixa-a de fora, mas quem lê à pressa pode achar que a inclui. Fica resolvido quando quem escreve pensa no caso dos 10 kg exatos e o decide de propósito, por exemplo "as encomendas com 10 kg ou mais seguem por transportadora". Os valores que ficam exatamente em cima de um limite chamam-se **casos de fronteira**, e são os que mais erros escondem.

A terceira é a informação que falta. "Liga ao fornecedor": a qual deles, se a loja trabalha com vários, e para que número? "Repõe o artigo em falta": que artigo, se nenhum passo anterior disse qual era? Aqui não há nenhuma palavra vaga para sublinhar. O que há é uma pergunta sem resposta, e só se encontra se, ao ler cada passo, perguntares "tenho tudo o que preciso para fazer isto?".

A quarta é a frase que se pode ler de duas maneiras. "Arredonda o valor": para cima ou para baixo, e com quantas casas decimais? "A encomenda é entregue em 2 dias": dias úteis, ou dias seguidos, contando o fim de semana? As duas leituras são razoáveis, e é exatamente por isso que a frase é perigosa: cada pessoa acha que a sua leitura é a óbvia.

A quinta é a unidade em falta. "Cada caixa leva no máximo 10." Dez quê? Dez livros, ou dez quilos? A resposta muda tudo, e a frase não a dá.

Corrigir uma ambiguidade é quase sempre substituir o que é vago por um número, um limite ou uma regra: "junta 3 gramas de sal", "espera 30 segundos", "se estiverem 8 ou mais pessoas na fila, chama um colega". Às vezes é também acrescentar o que acontece quando a situação não é a normal, como fez o passo 4 do algoritmo do armazém.

Há um cuidado que não podes esquecer. Quando o enunciado não te dá a informação de que precisas, não inventes em silêncio. Pergunta a quem escreveu o enunciado. Se não for possível, toma uma decisão e escreve-a, para que quem ler a tua solução saiba em que pressuposto ela assenta. Uma decisão escrita pode ser discutida e mudada. Uma decisão tomada em silêncio só se descobre quando o resultado sai errado.

A forma mais segura de encontrar ambiguidades não é reler o que escreveste, porque tu sabes o que querias dizer e a tua cabeça preenche as falhas sem dares por isso. É dar as instruções a outra pessoa e pedir-lhe que as execute exatamente como estão escritas, sem te perguntar nada. Cada vez que ela hesitar, ou fizer uma coisa diferente da que esperavas, encontraste uma ambiguidade. Vais fazer isto na prática guiada.

### O contrato do problema: entradas, saídas, restrições e condições

Antes de escrever qualquer passo, responde a quatro perguntas sobre o problema. Esta é a ferramenta mais útil de todo o bloco, e vais usá-la no início de todos os problemas até ao fim do ano.

| Pergunta | O que procuras |
| --- | --- |
| Entradas | Que dados já tenho, ou vou receber, para trabalhar? |
| Saídas | Que resultado tem de ser produzido? |
| Restrições | Que limites e regras fixas a solução tem de respeitar sempre? |
| Condições | Que situações diferentes podem acontecer e obrigam a fazer coisas diferentes? |

Às respostas a estas quatro perguntas junta-se uma lista de exemplos concretos, cada um com o resultado que se espera. Tudo junto, escrito antes de haver algoritmo, chama-se o **contrato do problema**. Vais ver cada parte com calma.

#### Entradas

As **entradas** são os dados que o algoritmo recebe, ou que já existem quando ele começa. Para cada entrada, o contrato diz o que é, que tipo de valor é (um número inteiro, um número com casas decimais, um texto), em que unidade está e que valores são aceitáveis. "Número da senha do cliente, inteiro de 1 a 40" é uma entrada bem descrita. "A senha" não é.

Nem todas as entradas são números escritos num papel. Num atendimento, a chegada de um cliente é uma entrada: é uma coisa que vem de fora e a que o algoritmo tem de responder.

#### Saídas

As **saídas** são o resultado que o algoritmo produz, e têm de ser observáveis: tem de se conseguir ver ou verificar se estão certas. Uma confusão frequente é escrever uma ação no lugar da saída. No armazém, "dar entrada no stock" é uma ação. A saída é o stock atualizado, com o número de caixas de cada artigo, que se consegue ler e conferir.

Para separar entradas de saídas, faz a cada dado esta pergunta: isto já existe antes de eu começar, ou sou eu que o produzo? O que já existe é entrada. O que produzes é saída.

#### Restrições

As **restrições** são os limites e as regras fixas que valem sempre, em todas as vezes que o algoritmo é usado: "a loja só distribui 40 senhas por dia", "há um só balcão", "o armazém só recebe entregas nos dias úteis". Uma restrição não é uma coisa que possa acontecer ou não. Está sempre lá.

Alguns números do enunciado também ficam aqui, apesar de não serem limites. Se o enunciado diz que "cada atendimento demora, em média, 4 minutos", esse valor não é uma entrada, porque ninguém o volta a escrever cada vez que o algoritmo é usado: é uma regra fixa do problema. No próximo bloco estes valores fixos vão ter um nome próprio, constantes.

#### Condições

As **condições** são situações que podem acontecer ou não, e que, quando acontecem, obrigam a fazer uma coisa diferente: "se o cliente chamado não aparecer, passa-se à senha seguinte", "se já não houver senhas, informa-se o cliente". Escrevem-se quase sempre com "se": se isto acontecer, faz-se aquilo; se não acontecer, faz-se outra coisa.

A diferença entre restrição e condição confunde muita gente, por isso repara neste teste. Pergunta: isto vale sempre, em qualquer situação? Se vale, é uma restrição. Pode acontecer numa vez e não acontecer noutra, e muda o caminho quando acontece? Então é uma condição.

Muitas vezes as duas andam juntas, e perceber como ajuda a distingui-las. A restrição "no máximo 40 senhas por dia" vale sempre. Mas é dela que nasce a condição "ainda há senhas, ou já se entregaram as 40?", que é a pergunta que se faz cada vez que chega um cliente. A restrição é a regra. A condição é o momento em que o algoritmo verifica a regra e escolhe o caminho.

#### Exemplos concretos

Os **exemplos concretos** são entradas escolhidas com cuidado, cada uma com a saída que se espera, calculada à mão, sem algoritmo nenhum. Servem para duas coisas. Antes de escreveres o algoritmo, mostram se percebeste o problema: se não consegues calcular à mão o resultado de um exemplo, ainda não o percebeste. Depois de escreveres o algoritmo, servem de teste: o algoritmo tem de dar exatamente aqueles resultados, e se não der, está errado.

Um bom conjunto de exemplos não tem só o caso normal, aquele que toda a gente imagina ao ler o enunciado. Tem também casos de fronteira, com valores em cima dos limites, e casos extremos, que obrigam a tomar decisões que o enunciado não tomou.

#### Um contrato completo: o tempo de espera

Vê as cinco partes a funcionar num problema pequeno.

> Uma papelaria atende os clientes por senha, com um só balcão. Quer pôr um ecrã ao lado da máquina de senhas que mostre a cada cliente quanto tempo vai esperar. Cada atendimento demora, em média, 4 minutos.

As entradas são duas. A primeira é o número da senha do cliente, um número inteiro de 1 a 40. A segunda é o número da última senha chamada, que é a do cliente que está a ser atendido ao balcão, também um número inteiro de 1 a 40. Aqui foi preciso tomar uma decisão: o ecrã só é ligado depois de chamada a primeira senha do dia, e por isso a última senha chamada nunca é zero. A decisão ficou escrita, e com isso o contrato deixa claro que o caso "ainda ninguém foi chamado" não é da conta deste algoritmo.

A saída é a mensagem que aparece no ecrã: um número de minutos, ou uma frase quando não faz sentido mostrar minutos.

As restrições são as regras fixas: cada atendimento conta 4 minutos, e o cliente que está ao balcão conta como um atendimento inteiro. Esta segunda regra também é uma decisão. O ecrã não sabe há quanto tempo começou o atendimento que está a decorrer, e por isso conta-o inteiro, para não prometer ao cliente menos tempo do que ele vai esperar.

As condições são três: a senha do cliente pode ser maior do que a última chamada (ainda tem de esperar), igual (é a vez dele) ou menor (já foi chamada).

Os exemplos concretos, calculados à mão:

| Senha do cliente | Última senha chamada | O ecrã mostra | Porque é que este caso foi escolhido |
| ---: | ---: | --- | --- |
| 18 | 14 | 16 minutos | Caso normal: à frente do cliente estão a senha 14, ao balcão, e as senhas 15, 16 e 17, à espera |
| 15 | 14 | 4 minutos | Logo acima da fronteira: o cliente é o próximo e só espera pelo atendimento que está a decorrer |
| 14 | 14 | É a sua vez | Fronteira: a senha do cliente é igual à última chamada |
| 9 | 14 | A sua senha já foi chamada | Caso extremo: a vez do cliente já passou |

Vale a pena perceber o que cada linha ensina.

A primeira linha é o caso que toda a gente imagina. À frente do cliente da senha 18 estão quatro atendimentos: o da senha 14, que está a decorrer, e os das senhas 15, 16 e 17. São 4 atendimentos de 4 minutos, 16 minutos ao todo. Repara que 18 menos 14 também dá 4: a diferença entre as duas senhas diz quantos atendimentos faltam, precisamente porque decidimos contar inteiro o que está a decorrer.

A segunda linha está logo acima da fronteira entre esperar e ser atendido. O cliente da senha 15 é o próximo, e só tem de esperar que acabe o atendimento que está a decorrer: 4 minutos.

A terceira linha está exatamente em cima da fronteira, e é o momento em que a conta deixa de ser útil. O cliente da senha 14 é o que acabou de ser chamado. 14 menos 14 dá 0, e mostrar "0 minutos" seria verdade, mas o cliente ficaria sem saber que tem de se levantar. O contrato decidiu mostrar uma frase.

A quarta linha é a mais interessante, porque o enunciado não pensou nela. O cliente da senha 9 chegou atrasado, ou distraiu-se, e a vez dele já passou. 9 menos 14 dá menos 5, e 5 vezes 4 dá 20: o ecrã mostraria "menos 20 minutos", o que não é uma resposta que se mostre a ninguém. Sem este exemplo no contrato, o algoritmo faria a conta à mesma e o ecrã mostraria esse disparate. É para isto que servem os casos extremos: obrigam a decidir antes, em vez de descobrir depois.

Repara também no que o contrato não promete. Se um cliente chamado não aparecer, o atendimento dele não demora 4 minutos, e os que estão atrás esperam menos do que o ecrã disse. O ecrã mostra uma previsão, não uma garantia. Escrever isto também faz parte do contrato.

#### Porque se chama contrato

Chama-se contrato porque funciona como um acordo entre duas partes. Quem usa o algoritmo compromete-se a dar entradas dentro dos limites combinados, como uma senha entre 1 e 40. O algoritmo compromete-se a devolver a saída prometida. Se alguém der uma entrada fora do combinado, por exemplo a senha 57, o contrato ou diz o que acontece nesse caso, ou deixa claro que esse caso não está coberto.

A máquina de senhas da papelaria tem um contrato destes, mesmo que ninguém o tenha escrito num papel. A entrada é carregar no botão. A saída é um papel com um número. As restrições dizem que os números sobem de um em um e acabam no 40. Para usares a máquina não precisas de saber como ela funciona por dentro: o contrato basta. É essa a grande vantagem de um contrato bem escrito. Separa o que o algoritmo faz de como o faz, e permite verificar se o algoritmo está certo sem ter de confiar em quem o escreveu.

### Decompor um problema em subproblemas

**Decompor** é partir um problema grande em subproblemas mais pequenos, cada um com um objetivo próprio e suficientemente simples para se resolver e verificar sozinho.

No dia a dia fazes isto sem dar por isso. Organizar uma visita de estudo parece uma tarefa enorme. Partida em "escolher o local e a data", "pedir as autorizações", "tratar do transporte" e "preparar o que se faz lá", cada parte já se consegue pensar. E "tratar do transporte" ainda se parte em "saber quantas pessoas vão", "reservar o autocarro" e "combinar a hora e o local de partida".

Repara agora no problema "organizar o atendimento de uma loja". Assim, inteiro, é difícil de atacar: por onde se começa? Decomposto, fica:

- distribuir senhas a quem chega;
- saber qual é a senha que está a ser atendida;
- chamar a senha seguinte quando o balcão fica livre;
- tratar o caso de alguém não aparecer quando é chamado;
- fechar o atendimento no fim do dia.

Cada um destes já se consegue pensar sozinho. Para distribuir senhas basta saber qual foi a última senha entregue e se ainda há senhas. Não é preciso pensar, ao mesmo tempo, no que acontece quando alguém falta.

Um subproblema não é o mesmo que um passo. Um subproblema é um objetivo, como "chamar a senha seguinte". Os passos são a forma de o atingir, como "comparar a última senha chamada com a última entregue; se forem diferentes, somar 1 e anunciar o número". Primeiro decompõe-se em subproblemas, depois escrevem-se os passos de cada um. Um subproblema pode ter dez passos, e pode ele próprio voltar a ser decomposto se ainda for grande.

Os subproblemas nem sempre são independentes. Às vezes um precisa do que outro produziu: só se consegue chamar a senha seguinte se alguém já tiver distribuído senhas. Quando decompões, vale a pena escrever também esta ordem, porque ela diz por onde começar e o que tem de estar pronto antes de quê.

Uma boa decomposição tem três sinais: cada subproblema tem um objetivo claro, cada subproblema pode ser resolvido e verificado por si só, e o conjunto continua a resolver o problema inicial, sem deixar nada de fora.

Há dois erros opostos. Decompor de menos deixa blocos gigantes que continuam difíceis: "tratar do atendimento" não é um subproblema, é o problema outra vez com outro nome. Decompor de mais produz vinte pedacinhos que já ninguém consegue juntar, como "pegar na caneta" e "olhar para o papel". O critério para saber onde parar é este: para quando cada parte se consegue explicar numa frase e verificar sozinha. Se uma parte ainda te parece difícil, ainda não está decomposta. Se já não consegues dizer para que serve, foste longe de mais.

### Os quatro princípios do pensamento computacional

O **pensamento computacional** é uma forma de pensar sobre problemas que torna a solução possível de executar por outra pessoa ou por uma máquina. Apesar do nome, não se trata de pensar como um computador, e não serve só a quem trabalha com computadores: quem organiza um armazém, planeia um horário ou escreve as regras de um torneio usa esta mesma forma de pensar.

Apresenta-se em quatro princípios: decomposição, reconhecimento de padrões, abstração e algoritmo. Não se usam por ordem, um de cada vez, como numa receita. Usam-se em conjunto, e salta-se de um para outro enquanto se pensa. Já viste dois deles com calma nesta teoria. Falta ver os outros dois e perceber como os quatro encaixam.

#### Decomposição

É o que acabaste de ver: partir o problema em partes que se resolvem e verificam uma a uma. Nos Missionários e Canibais, que vais ver no segundo exemplo, "levar toda a gente para o outro lado" é grande demais para se pensar de uma vez. Partido em "uma travessia de cada vez", e cada travessia partida em "escolher quem vai", "verificar se é permitido" e "atualizar quem está em cada margem", o problema passa a ser uma sequência de decisões pequenas.

#### Reconhecimento de padrões

**Reconhecer padrões** é reparar no que se repete, dentro de um problema ou entre problemas diferentes, para resolver uma vez e aproveitar muitas.

Quando fazes uma soma de números grandes em coluna, repetes o mesmo processo em cada coluna: somar os algarismos, escrever as unidades e levar o transporte para a coluna seguinte. Não aprendeste um método para as centenas e outro para os milhares. Aprendeste um padrão.

Na papelaria, cada cliente que chega passa exatamente pelos mesmos passos para receber a senha. Só muda o número. Reparar nisto significa que só tens de escrever esses passos uma vez. Também há padrões entre problemas diferentes: a fila de uma papelaria, a fila de chamadas de um serviço de apoio técnico e a fila de trabalhos de uma impressora partilhada funcionam da mesma maneira, por ordem de chegada. Quem resolveu uma já tem meio caminho andado nas outras.

O erro típico é ver um padrão onde ele não se aplica sempre. Vais ver na solução dos Missionários e Canibais que quase todas as idas e voltas seguem o ritmo "vão dois, volta um", mas há uma que não segue. Quem confiar no padrão sem verificar cada passo fica bloqueado precisamente aí. Um padrão ajuda a pensar. Não dispensa a verificação.

#### Abstração

**Abstrair** é ficar só com o que interessa para o problema e representá-lo da forma mais simples possível, deixando o resto de fora.

O mapa do metro é o exemplo clássico. Não mostra as distâncias reais, as ruas por cima nem as curvas dos túneis. Mostra as estações, a ordem em que aparecem e onde se muda de linha, que é tudo o que precisas para decidir onde sair. Um mapa com todos os pormenores reais seria mais verdadeiro e muito menos útil.

Para organizar a fila da papelaria, a cor da mochila do cliente, a idade dele e o que vem comprar são irrelevantes. O número da senha não é. Toda a fila pode ser descrita com dois números: a última senha entregue e a última senha chamada.

Há uma pergunta que ajuda a decidir o que fica e o que sai: se este pormenor fosse diferente, a resposta mudava? Se muda, é um **dado relevante** e tem de entrar no problema. Se não muda, é **contexto**: serve para tornar o enunciado agradável de ler, e podes deixá-lo de fora.

O erro típico é abstrair de mais, e deitar fora uma coisa de que precisas. Se a tua descrição da papelaria deixar de fora se o cliente chamado apareceu ou não, deixas de conseguir tratar as faltas, e a loja fica parada à espera de alguém que já foi embora. O erro contrário, guardar tudo por precaução, também existe: perdes-te no meio de pormenores que não interessam. A pergunta "se isto mudasse, a resposta mudava?" protege-te dos dois.

#### Algoritmo

Depois de decompor, de reparar nos padrões e de escolher o que interessa, sobra escrever os passos. É aqui que aparece o algoritmo, tal como foi definido no início desta teoria. Neste bloco os passos escrevem-se em português, numerados. No próximo vais aprender uma notação própria para os escrever com mais rigor.

### As etapas para construir um algoritmo

Tudo o que viste junta-se numa sequência de etapas, que vais seguir nos dois exemplos e em todos os problemas deste ano:

1. Ler o enunciado duas vezes: a primeira para perceber a história, a segunda com um lápis na mão, a sublinhar números, limites e regras.
2. Escrever o contrato: entradas, saídas, restrições, condições e exemplos concretos com o resultado esperado. Se faltar informação, perguntar, ou escrever a decisão tomada.
3. Decompor o problema em subproblemas.
4. Escrever os passos de cada subproblema, com uma ação por passo.
5. Simular os passos com os exemplos concretos, seguindo o estado numa tabela, e confirmar que os resultados batem certo com o contrato.
6. Procurar ambiguidades, de preferência dando os passos a outra pessoa, e corrigi-las.

As etapas não são uma escada que se sobe uma vez. É normal a simulação da etapa 5 mostrar que falta uma condição, e isso obriga a voltar à etapa 2 para a acrescentar ao contrato. Voltar atrás não é sinal de que fizeste mal. É assim que se constrói um algoritmo que funciona.

## Exemplos explicados (40 min)

Os dois exemplos seguem as etapas que acabaste de ver, mas são problemas de natureza diferente, e é por isso que estão os dois aqui. O primeiro, a papelaria, é um processo de gestão que se repete o dia inteiro, com entradas que chegam a qualquer momento: um cliente que entra, um balcão que fica livre. O segundo, os Missionários e Canibais, é um quebra-cabeças: começa sempre da mesma maneira, e a solução é uma sequência de jogadas que leva a um objetivo. O método de análise serve aos dois.

### Exemplo 1: o atendimento por senhas numa papelaria

#### O problema

Uma papelaria atende os clientes por senha. Quando um cliente chega, tira uma senha com um número. Os clientes são atendidos por ordem crescente de senha. A loja tem um único balcão e distribui no máximo 40 senhas por dia. Quando um cliente é chamado e não aparece, a sua senha é descartada e passa-se à seguinte.

Queremos descrever o funcionamento do atendimento de forma suficientemente precisa para que um funcionário novo, no primeiro dia, consiga executá-lo sem perguntar nada.

#### Passo 1: responder às quatro perguntas

| Pergunta | Resposta |
| --- | --- |
| Entradas | Chegada de um cliente; sinal de que o balcão ficou livre; resposta do cliente quando é chamado (aparece ou não aparece) |
| Saídas | Número de senha entregue a cada cliente; número chamado em voz alta; cliente atendido |
| Restrições | Um só balcão; no máximo 40 senhas por dia; atendimento por ordem crescente de senha |
| Condições | Ainda há senhas disponíveis ou já se esgotaram; quando o balcão fica livre, há ou não há alguém à espera; o cliente chamado aparece ou não aparece |

Vê a razão de cada linha.

As entradas deste problema não são números escritos numa folha. São acontecimentos que vêm de fora e a que o atendimento tem de responder: um cliente que entra na loja, o balcão que fica livre, um cliente que responde ou não responde quando ouve o seu número.

As saídas são coisas que se veem: o papel com o número que o cliente leva na mão, o número dito em voz alta, o cliente que foi atendido.

As restrições valem o dia inteiro, faça sol ou chuva, haja muitos clientes ou poucos. Nunca há dois balcões, nunca se entregam 41 senhas, nunca se atende a senha 7 antes da 6.

As condições são bifurcações: vai acontecer uma coisa ou outra, e cada uma leva a passos diferentes. Repara que a primeira condição nasce da restrição das 40 senhas, como viste na teoria. Repara também que a segunda condição não está escrita no enunciado. Encontra-se a pensar no estado: se o balcão fica livre e a fila está vazia, o que se faz? O enunciado não diz, mas o algoritmo tem de dizer.

Neste problema os exemplos concretos não são uma tabela de entradas e saídas, porque as entradas são acontecimentos ao longo do dia. O exemplo concreto é uma manhã de atendimento, com clientes que chegam e um que falta, e vais simulá-la no passo 4.

#### Passo 2: decompor

O problema parte-se em quatro subproblemas:

1. Entregar senha a quem chega.
2. Chamar o próximo quando o balcão fica livre.
3. Tratar a falta de quem não aparece.
4. Fechar o dia quando já não há senhas por atender.

Cada um destes pode ser explicado numa frase e testado sozinho, e juntos resolvem o problema inteiro. É uma boa decomposição.

Porque é que se parou aqui, e não se partiu mais? Porque cada um destes já se consegue escrever em meia dúzia de passos sem pensar nos outros ao mesmo tempo. E porque é que não se ficou por dois subproblemas, "entregar senhas" e "atender"? Porque "atender" ainda esconde duas coisas diferentes: chamar o número e decidir o que fazer se ninguém aparece.

Repara também na ordem entre eles. Chamar o próximo depende de já haver senhas entregues, e tratar a falta só acontece depois de uma chamada. Entregar senha, pelo contrário, pode acontecer a qualquer momento, mesmo enquanto alguém está a ser atendido.

#### Passo 3: escrever os passos

Agora escrevemos o algoritmo em passos numerados, em português, com uma ação por passo. Ainda não é pseudocódigo nem fluxograma: essas duas formas de escrever algoritmos são o assunto do bloco seguinte. Aqui o objetivo é a precisão, não a notação.

Entregar senha:

1. Verificar quantas senhas já foram entregues hoje.
2. Se já foram entregues 40, informar o cliente de que as senhas terminaram e terminar.
3. Caso contrário, somar 1 ao número da última senha entregue.
4. Entregar ao cliente uma senha com esse número.
5. Registar esse número como a última senha entregue.

Repara que o passo 2 é a condição que nasceu da restrição das 40 senhas. E repara na palavra "terminar": quer dizer que, nesse caso, os passos 3 a 5 não se fazem. Sem ela, o funcionário informava o cliente de que as senhas tinham acabado e, logo a seguir, entregava-lhe a senha 41.

Chamar o próximo:

1. Comparar o número da última senha chamada com o número da última senha entregue.
2. Se forem iguais, não há ninguém à espera: o atendimento fica parado até chegar alguém.
3. Caso contrário, somar 1 ao número da última senha chamada e anunciar esse número em voz alta.
4. Esperar 30 segundos pela resposta do cliente.
5. Se o cliente aparecer, atendê-lo e registar esse número como a última senha atendida.
6. Se o cliente não aparecer, registar esse número como descartado e voltar ao passo 1.

O terceiro subproblema, tratar a falta, acabou por caber dentro deste, nos passos 4 a 6, porque só acontece depois de uma chamada. Isto é normal: a decomposição é um plano, e ao escrever os passos percebe-se às vezes que duas partes vivem melhor juntas. O quarto, fechar o dia, não se escreve aqui, para o exemplo não ficar comprido. Experimenta escrevê-lo tu, em três ou quatro passos, e pergunta-te qual é a condição de paragem.

Repara na ordem dos passos 1 e 3 de chamar o próximo: primeiro compara-se, só depois se muda o estado. Se o passo 1 somasse logo 1 e só a seguir se verificasse se havia alguém à espera, o número ficava gasto à mesma quando não havia ninguém, e a senha seguinte a ser entregue nunca chegaria a ser chamada. É um erro fácil de cometer e difícil de ver, e vais procurá-lo no checkpoint do fim deste guia.

#### Passo 4: simular com um caso concreto

Um algoritmo só merece confiança depois de o experimentares com um caso. Vamos seguir o estado ao longo de uma manhã, com quatro clientes. O estado são dois números: a última senha entregue e a última senha chamada.

| Momento | Última senha entregue | Última senha chamada | O que acontece |
| --- | ---: | ---: | --- |
| Abertura | 0 | 0 | A loja abre, ninguém à espera |
| Chegam quatro clientes | 4 | 0 | Cada um recebeu uma senha, da 1 à 4 |
| Balcão livre | 4 | 1 | Chamada a senha 1; o cliente aparece e é atendido |
| Balcão livre | 4 | 2 | Chamada a senha 2; o cliente não aparece; a senha é descartada |
| Ainda livre | 4 | 3 | Chamada a senha 3; o cliente aparece e é atendido |
| Balcão livre | 4 | 4 | Chamada a senha 4; o cliente aparece e é atendido |
| Balcão livre | 4 | 4 | As duas senhas são iguais: ninguém à espera; o atendimento fica parado |

Lê a tabela linha a linha, como se fosses o funcionário.

Na abertura, as duas senhas estão a zero: ainda não se entregou nem se chamou nenhuma. Quando chegam os quatro clientes, o subproblema "entregar senha" corre quatro vezes, e de cada vez a última senha entregue sobe 1: passa a 1, 2, 3 e fica em 4. A tabela mostra só o estado final dessas quatro entregas, para não ficar comprida.

Quando o balcão fica livre pela primeira vez, o passo 1 de "chamar o próximo" compara 0 com 4. São diferentes, logo há alguém à espera, e o passo 3 soma 1 e anuncia a senha 1. O cliente aparece e é atendido.

Na linha seguinte, a senha 2 é chamada e o cliente não aparece. O passo 6 descarta a senha 2 e manda voltar ao passo 1, e é por isso que a linha a seguir diz "ainda livre": o balcão nunca chegou a ficar ocupado. A comparação dá 2 contra 4, há alguém à espera, e chama-se a senha 3.

Depois de atendida a senha 4, a última linha mostra o caso que o enunciado não previa e que o passo 1 trata: a última senha chamada é igual à última senha entregue, e por isso não há ninguém à espera. O estado não muda, e o atendimento fica parado até alguém tirar a senha 5.

Repara em duas coisas. Primeiro, em cada linha muda o estado, não o algoritmo: os passos são sempre os mesmos. Segundo, foi a simulação que nos mostrou que o passo 6 de "chamar o próximo" tinha mesmo de voltar ao passo 1. Sem isso, um cliente que falta deixaria a loja parada para sempre.

#### Passo 5: procurar ambiguidades

Antes de dar o algoritmo por bom, relê-o à procura de instruções que admitam duas leituras. Esta versão já foi corrigida uma vez: o passo 4 de "chamar o próximo" dizia originalmente "esperar um pouco pela resposta do cliente". Quanto é "um pouco"? Dois funcionários diferentes fariam coisas diferentes: um esperava cinco segundos e descartava a senha de quem estava a caminho do balcão, outro esperava cinco minutos com a loja parada. Passou a 30 segundos, e deixou de haver dúvida.

Repara que o número 30 não vem do enunciado. É uma decisão, e como é uma decisão ficou escrita no algoritmo, onde qualquer pessoa a pode ver e discutir.

### Exemplo 2: os Missionários e Canibais

Este é um quebra-cabeças clássico, e é muitas vezes o primeiro problema de algoritmia que se resolve numa aula. Vais segui-lo do enunciado até à solução completa, passo a passo, com as mesmas ferramentas do exemplo anterior.

#### O enunciado

Esta versão tem pormenores a mais de propósito, para praticares a separação entre dados e contexto:

> Numa manhã de verão, três missionários e três canibais chegam à margem esquerda de um rio largo, de águas castanhas e corrente fraca. Querem todos passar para a margem direita. Encontram um pequeno barco de madeira, pintado de vermelho, com dois remos. O barco leva no máximo duas pessoas e não atravessa o rio sozinho. Há um perigo: se, em alguma das margens, os canibais ficarem em maior número do que os missionários, os missionários são atacados e o jogo está perdido. Como é que os seis chegam todos à margem direita?

#### Passo 1: ler duas vezes

A primeira leitura serve para perceber a história: há pessoas de um lado, querem ir para o outro, há um barco pequeno e há um perigo. A segunda leitura faz-se com um lápis na mão, a sublinhar tudo o que parece um número, um limite ou uma regra. Não saltes a segunda leitura. É nela que se encontram as frases curtas que mudam tudo.

#### Passo 2: separar dados de contexto

Para cada pormenor, faz a pergunta da abstração: se isto fosse diferente, a resposta mudava?

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

Repara também numa leitura cuidadosa da regra de segurança. Ela fala de os missionários serem atacados. Numa margem onde não há nenhum missionário, não há ninguém para atacar, e por isso dois canibais sozinhos numa margem não fazem perder o jogo. Só há perigo numa margem onde haja pelo menos um missionário e mais canibais do que missionários.

#### Passo 3: procurar o que falta ou se pode ler de duas maneiras

O enunciado não diz uma coisa importante: quem está dentro do barco conta para alguma das margens? Imagina que o barco chega à margem direita com um canibal. Esse canibal conta como estando na margem direita, ou fica "no barco" e não conta?

As duas leituras são possíveis, e podem dar respostas diferentes. Como viste na teoria, não se inventa em silêncio: toma-se uma decisão e escreve-se. A regra usada nas aulas é esta: quem está no barco conta na margem onde o barco está.

Vê o que isto quer dizer em cada momento de uma travessia:

- Enquanto o barco está encostado à margem esquerda, quem já entrou nele continua a contar na margem esquerda. Entrar no barco não é sair da margem.
- Quando o barco chega à margem direita, quem vai nele passa a contar na margem direita, quer saia do barco quer fique lá dentro. Ficar sentado no barco não protege ninguém.

Voltando ao exemplo: o canibal que chega à margem direita conta como estando na margem direita, mesmo que não ponha um pé em terra.

Esta regra tem uma consequência útil. Entrar no barco não muda as contas de nenhuma margem, porque quem entra continua a contar na margem de onde vai partir. As contas só mudam quando o barco muda de lado. Por isso chega verificar a regra de segurança depois de cada travessia, e é isso que se faz daqui em diante.

Há mais duas perguntas que se respondem com o próprio enunciado. O barco pode levar uma só pessoa? Pode, porque "no máximo duas" inclui uma. O barco pode atravessar vazio? Não, porque não atravessa sozinho.

#### Passo 4: escrever o contrato

| Pergunta | Resposta |
| --- | --- |
| Entradas | A situação inicial: 3 missionários e 3 canibais na margem esquerda, ninguém na margem direita, o barco na margem esquerda |
| Saídas | Uma lista de travessias, em que cada uma diz quem vai no barco e em que sentido, e que termina com as seis pessoas na margem direita |
| Restrições | Em cada travessia vão uma ou duas pessoas; o barco só parte da margem onde está, e por isso as travessias alternam de sentido; depois de cada travessia, em nenhuma margem onde haja pelo menos um missionário pode haver mais canibais do que missionários, contando quem está no barco na margem onde o barco está |
| Condições | Em cada travessia, a hipótese escolhida cumpre ou não cumpre a regra de segurança; a situação a que se chega é nova ou já aconteceu antes; chegou-se ou não ao objetivo |

As restrições são as regras do jogo escritas com rigor, e valem em todas as travessias. As condições são as perguntas que se fazem em cada travessia e que decidem o que se faz a seguir: aceitar a travessia, experimentar outra, ou parar porque se chegou ao fim.

Como exemplos concretos, num jogo destes faz sentido verificar à mão uma ou duas jogadas antes de tentar a solução toda. Levar dois canibais na primeira travessia é permitido: a margem esquerda fica com 3 missionários e 1 canibal, e a direita com 2 canibais e nenhum missionário, pelo que ninguém corre perigo. Levar dois missionários na primeira travessia não é permitido: a margem esquerda fica com 1 missionário e 3 canibais, e a regra falha.

Repara numa diferença em relação à papelaria. Num jogo como este a entrada é sempre a mesma, porque o jogo começa sempre da mesma maneira. Na maior parte dos problemas deste ano, a entrada muda de cada vez que o algoritmo é usado, como a senha de cada cliente, e é por isso que os exemplos concretos do contrato vão ganhar tanta importância.

#### Passo 5: abstrair e escolher o estado

Para acompanhar o jogo não precisas de desenhar o rio. Chega uma representação com três valores: quantos missionários estão na margem esquerda, quantos canibais estão na margem esquerda e de que lado está o barco. A situação inicial escreve-se (3, 3, esquerda) e o objetivo escreve-se (0, 0, direita).

Estes três valores são o estado do jogo, a fotografia de que se falou na teoria. Cada travessia é uma ação que muda o estado. Por exemplo, levar dois canibais a partir do início muda o estado de (3, 3, esquerda) para (3, 1, direita).

Porque é que não se escreve também a margem direita? Porque se deduz: há sempre três missionários ao todo, e por isso os que estão na direita são 3 menos os que estão na esquerda. O mesmo para os canibais. Guardar os dois lados seria guardar a mesma informação duas vezes, e isso abre a porta a um erro chato: escrever 3 missionários na esquerda e 1 na direita, o que daria 4 missionários, que não existem. Uma boa representação guarda o mínimo necessário, e com isso torna alguns erros impossíveis.

E porque é que o lado do barco não pode sair? Porque sem ele deixas de saber quem pode viajar a seguir: só pode viajar quem está na margem onde o barco está. Tirar o lado do barco seria abstrair de mais.

Nas tabelas deste exemplo vais ver as duas margens escritas, porque é mais fácil verificar a regra de segurança com os números à frente. Mas a direita é sempre calculada a partir da esquerda.

#### Passo 6: decompor numa travessia de cada vez

O problema grande é "chegar de (3, 3, esquerda) a (0, 0, direita)". Decompõe-se numa sequência de travessias, e cada travessia decompõe-se nestes passos:

1. Ver em que margem está o barco.
2. Escolher quem vai no barco. Há apenas cinco hipóteses: um missionário, dois missionários, um canibal, dois canibais, ou um missionário e um canibal.
3. Confirmar que essas pessoas estão mesmo na margem onde está o barco.
4. Calcular a nova situação: tirar essas pessoas da margem de partida, pô-las na margem de chegada e mudar o barco de lado.
5. Verificar a regra de segurança nas duas margens.
6. Se a regra falhar, desfazer a travessia e voltar ao passo 2 com outra hipótese.
7. Se a regra se cumprir, confirmar que a nova situação não é uma que já aconteceu antes. Se for, também se volta ao passo 2, porque regressar a uma situação conhecida é andar para trás.
8. Se a nova situação for (0, 0, direita), o jogo está resolvido. Se não for, volta-se ao passo 1 para a travessia seguinte.

O passo 7 merece uma explicação. Sem ele, podias passar a tarde a levar um canibal para a direita e a trazê-lo de volta, sempre dentro das regras e sem nunca avançar. Recusar situações repetidas é o que garante que o processo acaba.

O passo 8 manda voltar ao início e fazer tudo outra vez para a travessia seguinte. Fazer os mesmos passos várias vezes chama-se repetição, e vai ter uma forma própria de se escrever no quarto bloco deste percurso, Repetição e padrões. Por agora, basta dizê-lo em português com clareza, como está acima.

#### Passo 7: reconhecer o padrão da verificação

Os passos 1 a 8 são iguais em todas as travessias. Só mudam os números. É o padrão de que se falou na teoria: aprendes a verificar uma travessia e sabes verificar todas.

Vê o padrão a funcionar logo na primeira travessia, experimentando as cinco hipóteses a partir de (3, 3, esquerda):

| Quem vai | Margem esquerda fica com | Margem direita fica com | A regra cumpre-se? |
| --- | --- | --- | --- |
| 1 missionário | 2 missionários e 3 canibais | 1 missionário | Não: na esquerda, 3 canibais contra 2 missionários |
| 2 missionários | 1 missionário e 3 canibais | 2 missionários | Não: na esquerda, 3 canibais contra 1 missionário |
| 1 canibal | 3 missionários e 2 canibais | 1 canibal | Sim |
| 2 canibais | 3 missionários e 1 canibal | 2 canibais | Sim |
| 1 missionário e 1 canibal | 2 missionários e 2 canibais | 1 missionário e 1 canibal | Sim |

Das cinco hipóteses, duas falham logo. As outras três são permitidas. A solução que se segue começa com dois canibais, mas começar com um missionário e um canibal também leva a uma solução.

#### Passo 8: simular até ao fim

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

A travessia 6 é o momento mais difícil do jogo, e é onde muita gente fica presa na aula. Depois da travessia 5 o barco está na margem direita, que tem 2 missionários e 2 canibais, e a esquerda tem 1 missionário e 1 canibal. Alguém tem de levar o barco de volta. Vê as cinco hipóteses, uma a uma, com o padrão da verificação:

- Se voltar 1 missionário, a direita fica com 1 missionário e 2 canibais. A regra falha.
- Se voltarem 2 missionários, a situação passa a ser a mesma que havia depois da travessia 4. É permitido, mas é andar para trás, e o passo 7 da decomposição recusa-o.
- Se voltar 1 canibal, a esquerda fica com 1 missionário e 2 canibais. A regra falha.
- Se voltarem 2 canibais, a esquerda fica com 1 missionário e 3 canibais. A regra falha.
- Se voltarem 1 missionário e 1 canibal, a esquerda fica com 2 e 2 e a direita com 1 e 1. A regra cumpre-se e a situação é nova.

Só uma hipótese faz avançar, e é a menos intuitiva de todas, porque leva de volta um missionário que tinha acabado de atravessar. É também aqui que o padrão "vão dois, volta um" deixa de funcionar: nas travessias 5 e 6 vão dois e voltam dois. Quem seguisse o padrão sem verificar não encontrava esta saída.

Não há nenhuma solução com menos de 11 travessias. Há quatro sequências diferentes com 11, que diferem nas duas primeiras travessias ou nas duas últimas, e qualquer uma delas é uma solução correta, desde que cumpra o contrato.

#### Passo 9: confirmar a solução contra o contrato

Uma solução não está terminada quando chega ao fim. Está terminada quando se verificou que cumpre o contrato. Para esta, confirma-se o seguinte:

- em todas as travessias vão uma ou duas pessoas;
- os sentidos alternam, a começar na esquerda, e por isso o barco parte sempre da margem onde está;
- em todas as linhas da tabela a regra de segurança se cumpre, nas duas margens;
- a última linha é (0, 0, direita), com toda a gente na margem direita;
- em todas as linhas há 3 missionários e 3 canibais ao todo, somando as duas margens.

Esta última verificação não vem do enunciado e é na mesma muito útil. Se numa linha a soma desse 5 ou 7, terias a certeza de que houve um erro de contas nessa travessia, mesmo antes de verificares a regra. Procurar coisas que têm de se manter sempre iguais é uma forma rápida de apanhar erros, e vais usá-la muitas vezes.

## Prática guiada (45 min)

Nesta prática vais fazer, com a ajuda do professor e dos colegas, o mesmo trabalho que viste nos exemplos: ordenar passos, escrever o contrato, procurar ambiguidades e corrigi-las. Podes trabalhar em pares, se o professor o indicar, mas escreve tudo na tua própria folha.

Vais trabalhar com um conjunto de cartões. Copia cada instrução para um cartão de papel, ou escreve-as numeradas numa folha e recorta-as. Os cartões estão de propósito fora de ordem.

Cartões para preparar uma encomenda de material escolar:

- Verificar se há stock suficiente de todos os artigos pedidos
- Embalar os artigos numa caixa
- Receber o pedido do cliente
- Colar a etiqueta com a morada na caixa
- Imprimir a etiqueta com a morada
- Entregar a caixa ao serviço de transporte
- Retirar os artigos da prateleira
- Avisar o cliente de que a encomenda seguiu
- Se faltar algum artigo, informar o cliente e esperar resposta

### 1. Ordenar os cartões (10 min)

Põe os cartões pela ordem em que as ações têm de acontecer. Mexe neles em cima da mesa até a sequência fazer sentido do princípio ao fim: lê-a em voz baixa, cartão a cartão, e imagina-te a fazer cada ação.

Antes de olhares para a ordem de outro colega, responde por escrito a duas perguntas. A primeira: há algum par de cartões que possa ficar em qualquer ordem, sem estragar o resultado? A segunda: há algum cartão que tenha de vir antes de outro por uma razão concreta? Escreve essa razão numa frase do tipo "o cartão X tem de vir antes do cartão Y porque Y precisa de ...". Esta forma de pensar, "este passo precisa de uma coisa que o anterior produziu", é a que decide a ordem de quase todos os algoritmos.

### 2. Escrever o contrato da encomenda (15 min)

Numa folha, desenha a tabela das quatro perguntas, como a do passo 1 da papelaria, e preenche-a para esta encomenda: que entradas o processo recebe, que saídas produz, que restrições tem de respeitar sempre e que condições podem mudar o caminho. Para cada linha, faz as perguntas da teoria: isto já existe antes de começar, ou sou eu que o produzo? Vale sempre, ou pode acontecer numa vez e não noutra?

Depois escreve dois exemplos concretos, cada um com o resultado esperado: um em que há stock de todos os artigos pedidos, e outro em que falta um artigo. Para cada um, diz por que cartões passa a encomenda e como acaba.

Por fim, escreve a decomposição em três ou quatro subproblemas, cada um com o seu objetivo numa frase.

Esta folha é a tua ficha de análise e a evidência do bloco. Guarda-a: vais precisar dela no bloco seguinte.

### 3. Encontrar as ambiguidades (10 min)

Pelo menos três destes cartões não dizem o suficiente para serem executados sem dúvidas. Encontra três e escreve, para cada um, a pergunta com que ficaste sem resposta.

Usa as cinco formas de ambiguidade da teoria como lista de verificação: há alguma palavra vaga? Algum limite que não diz se inclui a fronteira? Alguma informação em falta? Alguma frase com duas leituras? Alguma unidade em falta? E pensa sempre no que acontece quando a situação não é a normal.

### 4. Corrigir e verificar (10 min)

Escolhe um dos cartões ambíguos e reescreve-o de maneira a não deixar dúvidas. Depois passa-o a um colega e pede-lhe que o execute exatamente como está escrito, sem te perguntar nada. Se ele fizer o que esperavas, a instrução ficou precisa. Se fizer outra coisa, ainda está ambígua, e a culpa é do cartão, não dele. Nesse caso, reescreve-o outra vez e repete a experiência.

### Se estiveres com dificuldade

Começa por usar só cinco cartões, os que descrevem o essencial: receber o pedido, retirar os artigos, embalar, colar a etiqueta e entregar ao transporte. Ordena esses cinco primeiro e só depois acrescenta os restantes quatro, um de cada vez, perguntando a cada um onde é que ele tem de entrar e porquê.

## Erros comuns

| Sintoma | Como investigar | Como prevenir |
| --- | --- | --- |
| Confundir o que entra com o que sai | Pergunta: isto já existe antes de começar, ou é produzido por mim? | Preenche sempre a tabela das quatro perguntas antes dos passos |
| Trocar restrições com condições | Pergunta: isto vale sempre, ou pode acontecer numa vez e não noutra? | Escreve cada condição como uma frase com "se"; se não conseguires, provavelmente é uma restrição |
| Escrever passos que dependem do que tens na cabeça | Dá o algoritmo a um colega e não respondas a perguntas | Cada passo tem de ser executável só com o que está escrito |
| Deixar uma quantidade por dizer | Procura palavras como "muitos", "um pouco", "grande", "q.b." | Substitui a palavra vaga por um número ou por um limite, e decide o que acontece em cima da fronteira |
| Esquecer o caso que corre mal | Pergunta: e se não houver? E se falhar? E se for zero? | Lista as condições antes de escrever os passos, e põe um caso extremo nos exemplos concretos |
| Começar a resolver antes de acabar de ler | Relê o enunciado e procura uma regra que não usaste | Lê duas vezes, a segunda com lápis, antes de fazer seja o que for |
| Omitir uma etapa | Simula numa tabela e procura um passo impossível | Simula sempre, mesmo quando a solução parece óbvia |
| Confiar num padrão sem verificar | Procura o passo em que o padrão deixou de funcionar | Verifica a regra em todos os passos, não só nos que parecem perigosos |
| Decompor de menos | Se um subproblema ainda te parece difícil, não está decomposto | Cada subproblema tem de poder ser verificado sozinho |
| O algoritmo nunca acaba | Procura onde está escrito que termina | Confirma a condição de paragem antes de dar o algoritmo por concluído |

Dois destes erros merecem mais do que uma linha.

Uma etapa omitida é um passo que falta no algoritmo e que não se nota enquanto se pensa só no caso que se tinha em mente. Nos Missionários e Canibais, a etapa que costuma faltar é o regresso do barco. Quem escreve "1. levar dois canibais; 2. levar dois canibais; 3. levar dois missionários" esqueceu-se de que o barco não volta sozinho. A tabela da simulação denuncia o erro de imediato: depois da primeira travessia o barco está na direita, e a segunda travessia diz "esquerda → direita", o que é impossível. Na papelaria, a etapa que costuma faltar é o "voltar ao passo 1" depois de uma falta, e a simulação do passo 4 mostrou-o.

Quando descobres um erro, procura o exemplo mais pequeno que ainda o mostra. Nos Missionários e Canibais, para mostrar o regresso esquecido não é preciso simular o jogo inteiro: bastam duas travessias seguidas no mesmo sentido. Com o exemplo mais pequeno, a causa salta à vista, e depois de corrigires o algoritmo é o primeiro caso que voltas a experimentar, porque é o mais rápido de verificar.

## Resumo e checkpoint (35 min)

Um algoritmo é uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado. A algoritmia, que é pensar, escrever e verificar esses passos, vem antes da programação, que é escrevê-los numa linguagem que o computador executa, porque nenhuma linguagem te ajuda se não souberes que passos resolvem o problema.

Antes de escrever passos, escreve-se o contrato do problema: as entradas, as saídas, as restrições, as condições e exemplos concretos com o resultado esperado, incluindo casos de fronteira e casos extremos. Depois parte-se o problema em subproblemas que se possam verificar um a um. Cada ação muda o estado, e é a seguir o estado numa tabela que se confirma uma solução e se encontram os erros. Uma instrução vaga não é uma instrução: se admite duas leituras, não determina uma solução. Estas ideias têm um nome coletivo, pensamento computacional, e os seus quatro princípios são a decomposição, o reconhecimento de padrões, a abstração e o algoritmo.

Confirma o que já consegues fazer. Para cada ponto, experimenta fazê-lo sem olhar para o guia; se não conseguires, volta à secção correspondente.

- [ ] Consigo explicar o que é um algoritmo e dar um exemplo meu, do dia a dia ou do mundo da gestão, que não esteja neste guia.
- [ ] Consigo explicar a diferença entre algoritmia e programação, e porque é que se aprende primeiro a algoritmia.
- [ ] Consigo separar, num enunciado, o que são entradas, saídas, restrições e condições, e justificar cada escolha.
- [ ] Consigo escrever exemplos concretos com o resultado esperado, incluindo um caso de fronteira e um caso extremo.
- [ ] Consigo partir um problema em subproblemas e explicar por que parei nesse nível.
- [ ] Consigo dar um exemplo meu de decomposição, de padrão e de abstração.
- [ ] Consigo apontar uma instrução ambígua e reescrevê-la sem dúvidas.
- [ ] Consigo seguir um algoritmo passo a passo e dizer qual é o estado em cada momento.
- [ ] Consigo refazer numa folha a solução dos Missionários e Canibais, sem olhar para a tabela, verificando a regra em cada travessia.
- [ ] Consigo explicar porque é que, na travessia 6, a única escolha que faz avançar é levar de volta um missionário e um canibal.

### 1. Explica (10 min)

Em voz alta, ao professor ou a um colega, explica por que razão uma receita que diz "junta sal q.b." não determina uma solução, usando as palavras ambiguidade e estado. Uma pista: pensa no estado do prato no fim, se a receita for seguida por duas pessoas diferentes. Se conseguires explicar isto com um exemplo teu, o objetivo deste bloco está cumprido.

### 2. Testa o algoritmo de um colega (10 min)

Troca com um colega a sequência de cartões que ordenaste e corrigiste na prática guiada. Executa a dele literalmente, sem interpretar e sem lhe perguntar nada, e anota todos os pontos em que tiveste de adivinhar alguma coisa. Depois devolve-lhe a lista. Não é uma crítica: é a única forma de descobrir uma ambiguidade, porque quem escreveu tem a resposta na cabeça e não dá pela falta.

### 3. Encontra o erro (10 min)

Uma loja com um só balcão usa este algoritmo para chamar clientes:

1. Somar 1 ao número da última senha chamada.
2. Se esse número for maior do que o número da última senha entregue, não há ninguém à espera e o atendimento fica parado.
3. Caso contrário, anunciar esse número em voz alta e atender o cliente.

Parece bem e funciona quase sempre. Mas há uma situação em que um cliente com senha nunca chega a ser chamado.

Descobre qual, seguindo o estado passo a passo numa tabela, como a do passo 4 da papelaria, nesta situação: foram entregues 4 senhas, todas as 4 já foram chamadas e atendidas, o balcão fica livre, e só depois disso chega um cliente novo que tira a senha 5.

Escreve em que passo está o erro e como o corrigias. Compara depois com o algoritmo da papelaria, no exemplo 1, que já está corrigido.

### 4. Regista as tuas dificuldades (5 min)

Escreve duas ou três linhas sobre o que te custou mais neste bloco e sobre o que farias de outra maneira se voltasses a começar. Guarda-as: é o que te vai dizer onde insistir.

Evidência a guardar: a tua ficha de análise com as quatro perguntas, os exemplos concretos e a decomposição do problema da encomenda, as ambiguidades que encontraste, o erro que identificaste no algoritmo acima e as tuas notas de dificuldade. Guarda tudo: vais precisar da análise no bloco seguinte, quando aprenderes a escrever a mesma coisa em pseudocódigo e em fluxograma.

## A seguir

A [ficha de exercícios](01-do-problema-ao-algoritmo-exercicios.md) deste bloco ocupa os restantes 120 minutos e é onde vais trabalhar sozinho.

No bloco seguinte, [Pseudocódigo e fluxogramas](02-pseudocodigo-e-fluxogramas.md), vais aprender a escrever algoritmos numa notação própria, o pseudocódigo, e a desenhá-los em fluxograma. O estado, que aqui foram números numa tabela, passa a ter nomes próprios, chamados variáveis: a última senha chamada da papelaria vai chamar-se `ultimaChamada`. E o contrato continua a ser o primeiro passo de todos os problemas: antes de escrever uma única instrução, vais sempre responder às quatro perguntas e escrever os exemplos.

## Referências

Unidade de competência UC00245, *Desenvolver algoritmos*, do referencial de Técnico/a de Informática de Gestão (481RA117), nível 4. A ficha oficial da unidade pode ser consultada no [Catálogo Nacional de Qualificações](https://catalogo.snq.gov.pt/ucDetalhe/355272).

![Rodapé](../imagens/rodape.png)
