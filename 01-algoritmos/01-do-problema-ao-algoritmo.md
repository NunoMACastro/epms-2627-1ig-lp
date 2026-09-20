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

- distinguir os dados que já conheces, o resultado que te é pedido e os passos necessários para lá chegar;
- identificar as restrições e as condições que uma solução tem de respeitar;
- partir um problema grande em subproblemas mais pequenos;
- explicar por que razão uma instrução ambígua não chega para determinar uma solução.

## Pré-requisitos e preparação

Não precisas de saber programar. Nada neste bloco exige um computador a correr código. Precisas de saber ler um enunciado com atenção e de fazer contas simples.

Material: papel e caneta, cartões de papel (ou um papel cortado em tiras) e um editor de texto para passar a limpo a tua análise.

## Como está organizado o tempo

Este bloco tem **5 horas**, que valem 300 minutos de trabalho. Não corresponde a uma aula: o teu professor reparte-o pelas sessões que existirem.

| Parte | Onde está | Tempo |
| --- | --- | ---: |
| Teoria | Neste guia | 30 min |
| Exemplo explicado | Neste guia | 30 min |
| Prática guiada | Neste guia | 60 min |
| Prática autónoma | Na ficha | 90 min |
| Desafio opcional | Na ficha | 30 min |
| Resumo e checkpoint | Neste guia | 60 min |

## Teoria — 30 min

### O que é um algoritmo

Um **algoritmo** é uma sequência finita e não ambígua de passos que transforma dados de entrada num resultado.

Cada palavra desta definição está lá por uma razão:

- **sequência**: os passos têm uma ordem, e trocar a ordem costuma mudar o resultado;
- **finita**: tem de acabar, e tu tens de saber quando acaba;
- **não ambígua**: cada passo só pode ser entendido de uma maneira;
- **transforma entradas num resultado**: há algo que entra, algo que acontece e algo que sai.

Usas algoritmos todos os dias sem lhes chamar isso. As instruções para chegar de tua casa à escola são um algoritmo. Uma receita de bolo é um algoritmo. As regras de um jogo de cartas são um algoritmo. A diferença entre esses e os que vais escrever nesta disciplina é só uma: os teus vão ter de ser suficientemente precisos para que outra pessoa, que não sabe o que tu estás a pensar, chegue exatamente ao mesmo resultado.

Um algoritmo útil tem sempre quatro coisas:

1. **entradas bem definidas** — o que recebes, e de que tipo;
2. **regras de processamento** — o que fazes com o que recebeste;
3. **uma saída observável** — o resultado, que tem de ser visível;
4. **uma condição de paragem** — o momento em que se sabe que terminou.

Sem paragem garantida não há algoritmo útil. Se as instruções para chegares à escola fossem "anda sempre em frente", nunca chegavas: falta a condição que diz quando parar.

### Ação e estado

Esta distinção vai acompanhar-te o ano inteiro, por isso vale a pena percebê-la bem agora.

Uma **ação** é uma coisa que se faz: chamar a senha seguinte, somar dois números, riscar um nome de uma lista.

O **estado** é a fotografia da situação num determinado momento: quantas pessoas estão na fila, qual é o número que está a ser atendido, quanto dinheiro está na caixa.

Uma ação muda o estado. Antes de chamar a senha seguinte, o estado é "está a ser atendida a senha 14 e há 6 pessoas à espera". Depois dessa ação, o estado é "está a ser atendida a senha 15 e há 5 pessoas à espera".

Quando mais à frente uma solução tua não funcionar, a pergunta que te vai salvar é quase sempre esta: **qual era o estado antes deste passo e qual é o estado depois?** Quem só olha para as ações não encontra o erro; quem olha para o estado encontra.

### Quando uma instrução é ambígua

Lê esta instrução de uma receita: *"junta sal q.b."*

Para uma pessoa que já cozinhou, isto chega. Para um computador, isto não é instrução nenhuma: quanto é "q.b."? Uma pitada? Uma colher? Duas pessoas que sigam esta receita produzem resultados diferentes, e nenhuma das duas está a desrespeitar a receita. É isso que significa uma instrução **ambígua**: admite mais do que uma leitura, e por isso não determina uma solução.

Outros exemplos do mesmo problema:

- "aquece um bocado" — quanto tempo, a que temperatura?
- "se houver muitas pessoas na fila, abre outra caixa" — quantas são "muitas"?
- "arredonda o valor" — para cima, para baixo, para quantas casas?

Corrigir uma ambiguidade é quase sempre substituir uma palavra vaga por um número, um limite ou uma regra: *"junta 3 gramas de sal"*, *"se estiverem 8 ou mais pessoas na fila, abre outra caixa"*.

### Entradas, saídas, restrições e condições

Antes de escrever qualquer passo, responde a quatro perguntas sobre o problema. Esta é a ferramenta mais útil de todo o bloco.

| Pergunta | O que procuras |
| --- | --- |
| **Entradas** | Que dados já tenho ou vou receber? |
| **Saídas** | Que resultado tem de ser produzido? |
| **Restrições** | Que limites a solução tem de respeitar sempre? |
| **Condições** | Que situações diferentes podem acontecer e exigem tratamento diferente? |

A diferença entre restrição e condição confunde muita gente, por isso repara: uma **restrição** é um limite que vale sempre ("a loja só tem 40 senhas por dia"); uma **condição** é uma situação que pode acontecer ou não e que muda o que se faz ("se o cliente não tiver senha, tem de tirar uma primeiro").

### Decompor

**Decompor** é partir um problema grande em subproblemas mais pequenos, cada um deles com objetivo próprio.

Repara no problema "organizar o atendimento de uma loja". Assim, inteiro, é difícil de atacar. Decomposto, fica:

- distribuir senhas a quem chega;
- saber qual é a senha que está a ser atendida;
- chamar a senha seguinte quando um posto fica livre;
- tratar o caso de alguém não aparecer quando é chamado;
- fechar o atendimento no fim do dia.

Uma boa decomposição tem três sinais: cada subproblema tem um objetivo claro, cada subproblema pode ser resolvido e verificado por si só, e o conjunto continua a resolver o problema inicial.

Há dois erros simétricos. Decompor **de menos** deixa blocos gigantes que continuam difíceis ("tratar do atendimento" não é um subproblema, é o problema outra vez). Decompor **de mais** produz vinte pedacinhos que já ninguém consegue juntar ("pegar na caneta", "olhar para o papel").

### Os quatro princípios

Tudo o que viste até aqui tem um nome coletivo: **pensamento computacional**. São quatro princípios, e já usaste três deles nesta página:

1. **Decomposição** — partir o problema em partes.
2. **Reconhecimento de padrões** — reparar que este problema se parece com outro que já resolveste, e reaproveitar a abordagem.
3. **Abstração** — deixar de fora o que não interessa para o problema. Para organizar a fila, a cor da mochila do cliente é irrelevante; o número da senha não é.
4. **Algoritmos** — escrever os passos precisos que resolvem o problema.

Isto não depende de linguagem nenhuma, e é por isso que este bloco vem antes de escreveres a primeira linha de código. A ordem correta é sempre a mesma: **compreender o problema, estruturar a solução e só depois programar**. Quem salta os dois primeiros passos escreve código que não sabe explicar e bloqueia em decisões simples.

## Exemplo explicado — 30 min

### O problema

Uma papelaria atende os clientes por senha. Quando um cliente chega, tira uma senha com um número. Os clientes são atendidos por ordem crescente de senha. A loja tem um único balcão e distribui no máximo 40 senhas por dia. Quando um cliente é chamado e não aparece, a sua senha é descartada e passa-se à seguinte.

Queremos descrever o funcionamento do atendimento de forma suficientemente precisa para que um funcionário novo, no primeiro dia, consiga executá-lo sem perguntar nada.

### Passo 1 — Responder às quatro perguntas

| Pergunta | Resposta |
| --- | --- |
| Entradas | Chegada de um cliente; sinal de que o balcão ficou livre; resposta do cliente quando é chamado |
| Saídas | Número de senha entregue a cada cliente; número chamado em voz alta; cliente atendido |
| Restrições | Um só balcão; no máximo 40 senhas por dia; atendimento por ordem crescente de senha |
| Condições | O cliente chamado aparece ou não aparece; ainda há senhas disponíveis ou já se esgotaram |

Repara que as restrições são limites que valem o dia inteiro, e que as condições são bifurcações: vai acontecer uma coisa ou outra, e cada uma leva a passos diferentes.

### Passo 2 — Decompor

O problema parte-se em quatro subproblemas:

1. **Entregar senha** a quem chega.
2. **Chamar o próximo** quando o balcão fica livre.
3. **Tratar a falta** de quem não aparece.
4. **Fechar o dia** quando já não há senhas por atender.

Cada um destes pode ser explicado e testado sozinho, e juntos resolvem o problema inteiro. É uma boa decomposição.

### Passo 3 — Escrever os passos

Agora escrevemos o algoritmo em passos numerados, em português, com uma ação por passo. Ainda **não** é pseudocódigo nem fluxograma: essas duas formas de escrever algoritmos são o assunto do bloco seguinte. Aqui o objetivo é a precisão, não a notação.

**Entregar senha:**

1. Verificar quantas senhas já foram entregues hoje.
2. Se já foram entregues 40, informar o cliente de que as senhas terminaram e terminar.
3. Caso contrário, somar 1 ao número da última senha entregue.
4. Entregar ao cliente uma senha com esse número.
5. Registar esse número como a última senha entregue.

**Chamar o próximo:**

1. Comparar o número da última senha chamada com o número da última senha entregue.
2. Se forem iguais, não há ninguém à espera: o atendimento fica parado até chegar alguém.
3. Caso contrário, somar 1 ao número da última senha chamada e anunciar esse número em voz alta.
4. Esperar 30 segundos pela resposta do cliente.
5. Se o cliente aparecer, atendê-lo e registar esse número como a última senha atendida.
6. Se o cliente não aparecer, registar esse número como descartado e voltar ao passo 1.

Repara na ordem dos passos 1 e 3: primeiro compara-se, só depois se muda o estado. Se o passo 1 somasse logo 1 e só a seguir se verificasse se havia alguém à espera, o número ficava gasto à mesma quando não havia ninguém — e a senha seguinte a ser entregue nunca chegaria a ser chamada. É um erro fácil de cometer e difícil de ver, e vais procurá-lo na consolidação.

### Passo 4 — Simular com um caso concreto

Um algoritmo só merece confiança depois de o experimentares com um caso. Vamos seguir o estado ao longo de uma manhã, com quatro clientes.

| Momento | Última senha entregue | Última senha chamada | O que acontece |
| --- | ---: | ---: | --- |
| Abertura | 0 | 0 | A loja abre, ninguém à espera |
| Chegam quatro clientes | 4 | 0 | Cada um recebeu uma senha, da 1 à 4 |
| Balcão livre | 4 | 1 | Chamada a senha 1; o cliente aparece e é atendido |
| Balcão livre | 4 | 2 | Chamada a senha 2; o cliente **não** aparece; a senha é descartada |
| Ainda livre | 4 | 3 | Chamada a senha 3; o cliente aparece e é atendido |

Repara em duas coisas. Primeiro, em cada linha muda o estado, não o algoritmo: os passos são sempre os mesmos. Segundo, foi a simulação que nos mostrou que o passo 6 de "chamar o próximo" tinha mesmo de voltar ao passo 1 — sem isso, um cliente que falta deixaria a loja parada para sempre.

### Passo 5 — Procurar ambiguidades

Antes de dar o algoritmo por bom, relê-o à procura de instruções que admitam duas leituras. Esta versão já foi corrigida uma vez: o passo 4 dizia originalmente *"esperar um pouco pela resposta do cliente"*. Quanto é "um pouco"? Dois funcionários diferentes fariam coisas diferentes. Passou a **30 segundos**, e deixou de haver dúvida.

## Prática guiada — 60 min

Vais trabalhar com um conjunto de cartões. Copia cada instrução para um cartão de papel, ou escreve-as numeradas numa folha e recorta.

**Cartões — preparar uma encomenda de material escolar:**

- Verificar se há stock suficiente de todos os artigos pedidos
- Embalar os artigos numa caixa
- Receber o pedido do cliente
- Colar a etiqueta com a morada na caixa
- Imprimir a etiqueta com a morada
- Entregar a caixa ao serviço de transporte
- Retirar os artigos da prateleira
- Avisar o cliente de que a encomenda seguiu
- Se faltar algum artigo, informar o cliente e esperar resposta

**1. Ordenar — 15 min.** Põe os cartões pela ordem em que as ações têm de acontecer. Antes de olhares para a ordem de outro colega, responde por escrito: há algum par de cartões que possa ficar em qualquer ordem, sem estragar o resultado? E há algum cartão que **tenha** de vir antes de outro por uma razão concreta? Escreve essa razão.

**2. Analisar o problema — 15 min.** Preenche para esta encomenda a tabela das quatro perguntas — entradas, saídas, restrições e condições — e escreve a decomposição em subproblemas. Esta é a folha que vais guardar como evidência do bloco.

**3. Encontrar as ambiguidades — 15 min.** Pelo menos três destes cartões não dizem o suficiente para serem executados sem dúvidas. Encontra três e escreve, para cada um, a pergunta que ficaste sem resposta. Uma pista: pensa sempre em quantidades, limites e no que acontece quando a situação não é a normal.

**4. Corrigir e verificar — 15 min.** Escolhe um dos cartões ambíguos e reescreve-o de maneira a não deixar dúvidas. Depois passa-o a um colega e pede-lhe que o execute exatamente como está escrito, sem te perguntar nada. Se ele fizer o que esperavas, a instrução ficou precisa. Se ele fizer outra coisa, ainda está ambígua — e a culpa é do cartão, não dele.

**Se estiveres com dificuldade.** Começa por usar só cinco cartões, os que descrevem o essencial: receber o pedido, retirar os artigos, embalar, colar a etiqueta e entregar ao transporte. Ordena esses cinco primeiro e só depois acrescenta os restantes quatro, um de cada vez, perguntando a cada um onde é que ele tem de entrar e porquê.

## Erros comuns

| Sintoma | Como investigar | Como prevenir |
| --- | --- | --- |
| Confundir o que entra com o que sai | Pergunta: isto já existe antes de começar, ou é produzido por mim? | Preenche sempre a tabela das quatro perguntas antes dos passos |
| Escrever passos que dependem do que tens na cabeça | Dá o algoritmo a um colega e não respondas a perguntas | Cada passo tem de ser executável só com o que está escrito |
| Deixar uma quantidade por dizer | Procura palavras como "muitos", "um pouco", "grande", "q.b." | Substitui a palavra vaga por um número ou por um limite |
| Esquecer o caso que corre mal | Pergunta: e se não houver? e se falhar? e se for zero? | Lista as condições antes de escrever os passos |
| Decompor de menos | Se um subproblema ainda te parece difícil, não está decomposto | Cada subproblema tem de poder ser verificado sozinho |
| O algoritmo nunca acaba | Procura onde está escrito que termina | Confirma a condição de paragem antes de dar por concluído |

## Resumo e checkpoint — 60 min

Um algoritmo é uma sequência finita e não ambígua de passos que transforma entradas num resultado. Antes de escrever passos, responde a quatro perguntas — entradas, saídas, restrições e condições — e parte o problema em subproblemas que possas verificar um a um. Cada ação muda o estado, e é a olhar para o estado que se encontram os erros. Uma instrução vaga não é uma instrução: se admite duas leituras, não determina uma solução.

Confirma o que já consegues fazer:

- [ ] Consigo separar, num enunciado, o que são entradas, saídas, restrições e condições.
- [ ] Consigo partir um problema em subproblemas e explicar por que parei nesse nível.
- [ ] Consigo apontar uma instrução ambígua e reescrevê-la sem dúvidas.
- [ ] Consigo seguir um algoritmo passo a passo e dizer qual é o estado em cada momento.

### 1. Explica — 15 min

Em voz alta, ao professor ou a um colega, explica por que razão uma receita que diz "junta sal q.b." não determina uma solução, usando as palavras ambiguidade e estado. Se conseguires explicar isso com um exemplo teu, o objetivo deste bloco está cumprido.

### 2. Testa o algoritmo de um colega — 20 min

Troca com um colega o algoritmo que escreveste na prática guiada. Executa o dele literalmente, sem interpretar e sem lhe perguntar nada, e anota todos os pontos em que tiveste de adivinhar alguma coisa. Depois devolve-lhe a lista. Não é uma crítica: é a única forma de descobrir uma ambiguidade, porque quem escreveu tem a resposta na cabeça e não dá pela falta.

### 3. Encontra o erro — 15 min

Uma loja com um só balcão usa este algoritmo para chamar clientes:

1. Somar 1 ao número da última senha chamada.
2. Se esse número for maior do que o número da última senha entregue, não há ninguém à espera e o atendimento fica parado.
3. Caso contrário, anunciar esse número em voz alta e atender o cliente.

Parece bem e funciona quase sempre. Mas há uma situação em que um cliente com senha nunca chega a ser chamado.

Descobre qual, seguindo o estado passo a passo nesta situação: foram entregues 4 senhas, todas as 4 já foram chamadas e atendidas, o balcão fica livre, e só depois disso chega um cliente novo que tira a senha 5.

Escreve em que passo está o erro e como o corrigias. Compara depois com o algoritmo da secção do exemplo, que já está corrigido.

### 4. Regista as tuas dificuldades — 10 min

Escreve duas ou três linhas sobre o que te custou mais neste bloco e sobre o que farias de outra maneira se voltasses a começar. Guarda-as: é o que te vai dizer onde insistir.

**Evidência a guardar:** a tua ficha de análise com as quatro perguntas e a decomposição do problema da encomenda, as ambiguidades que encontraste, o erro que identificaste no algoritmo acima e as tuas notas de dificuldade. Guarda tudo: vais precisar da análise no bloco seguinte, quando aprenderes a escrever a mesma coisa em pseudocódigo e em fluxograma.

## A seguir

A [ficha de exercícios](01-do-problema-ao-algoritmo-exercicios.md) deste bloco ocupa os restantes 120 minutos e é onde vais trabalhar sozinho.

## Referências

Unidade de competência UC00245, *Desenvolver algoritmos*, do referencial de Técnico/a de Informática de Gestão (481RA117), nível 4. A ficha oficial da unidade pode ser consultada no [Catálogo Nacional de Qualificações](https://catalogo.snq.gov.pt/ucDetalhe/355272).
