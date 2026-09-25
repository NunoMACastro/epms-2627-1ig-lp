![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Do problema ao algoritmo

UC: UC00245

Blocos: ALG01

Requisitos: UC00245-R01, UC00245-R02, UC00245-K02, UC00245-A03, UC00245-A04, UC00245-P01

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG01, acompanha o [guia](01-do-problema-ao-algoritmo.md) |
| Tempo total | 120 minutos dos 300 do bloco: 90 de prática autónoma e 30 de desafio opcional |
| Entrega | Ficha de análise com as quatro perguntas, exemplos concretos, decomposição e algoritmo, em papel ou em ficheiro de texto |

## Objetivos e conceitos necessários

Vais praticar a análise de um problema antes de o resolver: escrever o contrato do problema (entradas, saídas, restrições, condições e exemplos concretos com o resultado esperado), partir o problema em subproblemas e escrever passos sem ambiguidades.

Antes de começares, deves conseguir explicar o que é um algoritmo, o que distingue uma restrição de uma condição, o que é um caso de fronteira e por que razão uma instrução vaga não determina uma solução. Tudo isso está no guia deste bloco: se alguma destas ideias não estiver clara, volta à secção correspondente da teoria antes de começar.

Material: papel e caneta, ou um editor de texto. Não precisas de computador para programar. Nada nesta ficha se escreve numa linguagem de programação.

Escreve os algoritmos em passos numerados, em português, tal como no exemplo da papelaria, com uma ação por passo. Pseudocódigo e fluxogramas são o assunto do próximo bloco; aqui não são precisos.

Os exercícios vão do mais simples para o mais completo. O primeiro pede só o contrato de um problema. O segundo pede que decomponhas um processo e encontres o que está mal escrito nele. O terceiro pede a análise completa de um problema novo, do contrato até à simulação. Fá-los por esta ordem.

## Exercício 1: Escrever o contrato de um problema (30 min)

A cantina da escola recebe todos os dias um pedido de reposição de bebidas. Quem faz o pedido conta o que resta em cada tipo de bebida, sabe quantas unidades cabem na arca e sabe que o fornecedor só entrega em caixas de 12 unidades. Cada tipo de bebida tem um mínimo que deve estar sempre disponível. No fim, é preciso produzir a lista de quantas caixas encomendar de cada tipo.

a) Responde às quatro perguntas sobre este problema, numa tabela:

| Pergunta | Resposta |
| --- | --- |
| Entradas | |
| Saídas | |
| Restrições | |
| Condições | |

Um exemplo do tipo de resultado esperado: para um tipo de bebida qualquer, o resultado é um número de caixas, nunca um número de unidades soltas.

Concluíste a alínea a) quando tiveres pelo menos duas entradas, uma saída, duas restrições e uma condição, e conseguires justificar por que colocaste cada uma nessa coluna e não noutra.

b) A cantina decidiu a regra para a água: encomenda-se o menor número de caixas que faz a água chegar pelo menos ao mínimo, que é de 20 garrafas. Na arca há espaço para 30 garrafas de água, e não cabe nem mais uma. O fornecedor só entrega caixas de 12 garrafas.

Escreve os exemplos concretos do contrato para a água. Para cada um dos quatro casos seguintes, calcula à mão quantas caixas se encomendam e com quantas garrafas a arca fica depois da entrega:

- restam 12 garrafas;
- restam 0 garrafas;
- restam 20 garrafas;
- restam 19 garrafas.

Organiza os resultados numa tabela com quatro colunas: garrafas que restam, caixas a encomendar, garrafas depois da entrega e porque é que o caso interessa (caso normal, caso de fronteira ou caso extremo). Escreve as contas que fizeste, e não só o resultado.

Um destes quatro casos obriga-te a tomar uma decisão que a regra da cantina não toma. Descobre qual, explica numa ou duas frases onde está o problema e escreve a decisão que tomarias. Não há uma só decisão certa, mas a tua tem de ficar escrita e justificada.

Concluíste a alínea b) quando tiveres os quatro casos calculados, cada um classificado, e a decisão escrita para o caso que a regra não resolve.

## Exercício 2: Decompor e encontrar ambiguidades (25 min)

A biblioteca da escola empresta livros. Alguém escreveu estas instruções para um aluno novo que vai ficar ao balcão:

1. Recebe o cartão do aluno.
2. Confirma se o aluno pode levar mais livros.
3. Procura o livro na prateleira.
4. Regista o empréstimo.
5. Diz ao aluno quando tem de devolver.
6. Se o livro estiver emprestado, resolve a situação.

a) Decompõe o processo de empréstimo em subproblemas, com o critério que aprendeste: cada subproblema tem de ter objetivo claro e poder ser verificado sozinho. Escreve entre três e cinco subproblemas, cada um com o seu objetivo numa frase, e explica numa frase por que paraste nesse nível.

b) Várias destas instruções são ambíguas: não dizem o suficiente para serem executadas sem perguntar nada a ninguém. Identifica pelo menos quatro e escreve, para cada uma, a pergunta com que ficaste sem resposta. Lembra-te de que a ambiguidade não é só a palavra vaga: também há informação que falta, frases com duas leituras e limites por definir.

c) Reescreve duas dessas instruções de forma a não deixarem dúvidas. Inventa os números e os limites que forem precisos, desde que fiquem escritos.

Testa também o caso em que o aluno chega ao balcão já com o número máximo de livros levantados: as instruções dizem o que fazer? Se não dizem, a tua reescrita da instrução 2 tem de o dizer.

Concluíste quando as instruções reescritas puderem ser executadas por alguém que nunca esteve naquela biblioteca.

## Exercício 3: Analisar um problema com autonomia (35 min)

A escola vai emprestar tablets aos alunos durante as aulas. Há 15 tablets numerados. Um aluno pede um tablet no início da aula e devolve-o no fim. Cada tablet tem de ser devolvido pelo mesmo aluno que o levou, e nenhum aluno pode ter mais do que um tablet ao mesmo tempo. No fim da aula, o responsável tem de saber se falta algum tablet e qual.

Produz uma análise completa deste problema:

a) A tabela com as quatro perguntas.

b) A decomposição em subproblemas.

c) O algoritmo, em passos numerados, de um desses subproblemas: emprestar um tablet.

d) Uma simulação numa tabela, à maneira do passo 4 da papelaria, com uma aula em que três alunos levantam tablets e um deles não devolve. Usa uma coluna para o momento, uma ou mais colunas para o estado dos tablets (quantos estão livres e quem tem cada um dos que não estão) e uma coluna para o que acontece. Identifica os alunos por letras (A, B, C) e nunca pelo nome de um colega. Mostra como o estado muda a cada momento.

Justifica, em duas ou três frases, uma decisão que tenhas tomado e que pudesse ter sido tomada de outra forma. Por exemplo: como decidiste qual o tablet a entregar quando há vários livres.

Concluíste quando outra pessoa conseguir seguir os teus passos com a tua simulação e chegar ao mesmo resultado que tu.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

Exercício 1, alínea a). Pergunta-te, dado a dado: isto já existe antes de eu começar, ou sou eu que o produzo? O que já existe é entrada, o que produzes é saída. Depois, procura no enunciado as palavras que exprimem limites ("só", "cabem", "mínimo"), porque é aí que costumam estar as restrições. Para as condições, procura situações que possam acontecer num dia e não acontecer noutro.

Exercício 1, alínea b). Para cada caso, faz três contas por esta ordem: quantas garrafas faltam para chegar ao mínimo; quantas caixas de 12 são precisas para cobrir essa falta, lembrando que não se encomendam meias caixas; com quantas garrafas a arca fica depois. Depois compara esse último número com o espaço da arca.

Exercício 2. Para encontrar as ambiguidades, faz a cada instrução três perguntas: quantos? onde? e se não der? A instrução que não responder a nenhuma das três é quase de certeza ambígua. E faz ainda uma quarta: tenho tudo o que preciso para fazer isto?

Exercício 3. Começa pelo estado: antes de pensares nos passos, escreve que informação é preciso ter guardada em cada momento para se saber quem tem cada tablet. Quando souberes o que é preciso guardar, os passos aparecem quase sozinhos.

## Desafio opcional (30 min)

Volta ao exercício 3 e muda uma só restrição: passa a haver 8 tablets para uma turma de 20 alunos, e por isso pode acontecer um aluno pedir um tablet quando já não há nenhum livre.

Escreve o que muda na tua análise: que condição nova aparece, que passos do algoritmo têm de ser alterados e que passos se mantêm exatamente iguais. Não reescrevas tudo. Identifica a diferença.

Esta é a pergunta que interessa: uma solução bem decomposta tem de aguentar uma mudança destas sem ser toda deitada fora. A tua aguentou?

## Para ires mais longe

Esta secção é opcional e fica fora dos 120 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e o desafio e quer mais prática, ou para estudar em casa. Os tempos são indicativos.

### Mais longe 1: Mais dois casos para a água (10 min)

Volta à água do exercício 1 b) e calcula mais dois casos: restam 5 garrafas e restam 25 garrafas. No caso de 5, confirma que as caixas que encomendas fazem mesmo a água chegar ao mínimo. No caso de 25, decide se é um caso normal ou extremo, e justifica.

### Mais longe 2: Verificar no fim da aula (15 min)

Volta aos tablets do exercício 3 e escreve o algoritmo, em passos numerados, do segundo subproblema: verificar no fim da aula se falta algum tablet e qual. Vais precisar de dizer que a mesma verificação se repete para cada tablet. Escreve-o em português simples ("verificar cada um dos 15 tablets, um a um"). A forma organizada de escrever repetições aprende-se no quarto bloco deste percurso, Repetição e padrões; aqui basta dizê-lo com clareza.

## Critérios de conclusão

- [ ] Respondi às quatro perguntas em todos os exercícios que as pedem.
- [ ] Escrevi exemplos concretos com o resultado calculado à mão, incluindo pelo menos um caso de fronteira e um caso extremo.
- [ ] A minha decomposição tem subproblemas com objetivo claro e verificáveis um a um.
- [ ] Os meus passos não têm palavras vagas: onde há quantidades, há números.
- [ ] Testei o caso normal e pelo menos um caso em que algo corre mal.
- [ ] Escrevi as decisões que tomei onde o enunciado não dizia o que fazer.
- [ ] Escrevi os algoritmos em passos numerados, sem usar notação que ainda não aprendi.
- [ ] Guardei a ficha de análise para usar no próximo bloco.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
