![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Do problema ao algoritmo

Ficha do tema Do problema ao algoritmo, do módulo Desenvolver algoritmos. Praticas a análise de um problema antes de o resolver: o contrato, a decomposição e os passos sem ambiguidades. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](01-do-problema-ao-algoritmo.md). Este tema não tem laboratório.

Antes de começares, deves conseguir explicar:

- o que é um algoritmo (secção "O que é um algoritmo");
- o que distingue uma restrição de uma condição (secção "O contrato do problema: entradas, saídas, restrições e condições");
- o que é um caso de fronteira (secção "Instruções ambíguas");
- porque é que uma instrução vaga não determina uma solução (a mesma secção).

Se alguma destas ideias não estiver clara, volta à secção do guia que a explica antes de começares.

## Como trabalhar

Resolve os exercícios pela ordem, em papel ou num editor de texto. Não precisas de computador para programar, porque nada nesta ficha se escreve numa linguagem de programação. Escreve os algoritmos em passos numerados, em português, como no exemplo guiado da papelaria. Cada passo faz uma só coisa, ou uma verificação com o que se faz em cada caso. O pseudocódigo e os fluxogramas são o assunto do tema seguinte, e aqui não são precisos.

Os exercícios vão do mais simples para o mais completo. O primeiro pede só o contrato de um problema. O segundo pede que decomponhas um processo e encontres o que está mal escrito nele. O terceiro pede a análise completa de um problema novo, do contrato até à simulação.

| Exercício | O que treina | Parte |
| --- | --- | --- |
| 1 | Escrever o contrato de um problema, com os exemplos concretos | Obrigatória |
| 2 | Decompor um processo e encontrar as instruções ambíguas | Obrigatória |
| 3 | Analisar um problema novo, do contrato à simulação | Obrigatória |
| Desafio | Mudar uma restrição do exercício 3 | Opcional |
| Para ires mais longe | Mais dois casos da água e o algoritmo de verificar os tablets no fim da aula | Opcional |

Entregas a tua ficha de análise, em papel ou num ficheiro de texto. É a folha onde escreves, para cada exercício, as quatro perguntas, os exemplos concretos, a decomposição e os algoritmos. Guarda-a, porque vais precisar dela no tema seguinte.

## Exercício 1: Escrever o contrato de um problema

A cantina da escola recebe todos os dias um pedido de reposição de bebidas. Quem faz o pedido conta o que resta em cada tipo de bebida. Sabe quantas unidades de cada tipo cabem na arca, e sabe que o fornecedor só entrega em caixas de 12 unidades. Cada tipo de bebida tem um mínimo que deve estar sempre disponível. A cantina pode mudar o mínimo de cada tipo quando quiser. No fim, é preciso produzir a lista de quantas caixas encomendar de cada tipo.

a) Responde às quatro perguntas sobre este problema, numa tabela:

| Pergunta | Resposta |
| --- | --- |
| Entradas | |
| Saídas | |
| Restrições | |
| Condições | |

Repara no tipo de resultado que se espera. Para cada tipo de bebida, o resultado é um número de caixas, e nunca um número de unidades soltas.

Concluíste a alínea a) quando tiveres pelo menos duas entradas, uma saída, duas restrições e uma condição. Tens também de conseguir justificar porque puseste cada uma nessa coluna, e não noutra.

b) A cantina decidiu a regra para a água. Encomenda-se o menor número de caixas que faz a água chegar pelo menos ao mínimo, que é de 20 garrafas. Na arca há espaço para 30 garrafas de água, e não cabe nem mais uma. O fornecedor só entrega caixas de 12 garrafas.

Escreve os exemplos concretos do contrato para a água. Para cada um dos quatro casos seguintes, calcula à mão quantas caixas se encomendam e com quantas garrafas a arca fica depois da entrega:

- restam 12 garrafas;
- restam 0 garrafas;
- restam 20 garrafas;
- restam 19 garrafas.

Organiza os resultados numa tabela com quatro colunas: garrafas que restam, caixas a encomendar, garrafas depois da entrega e porque é que o caso interessa. Na última coluna, diz se é um caso normal, um caso de fronteira ou um caso extremo. Um caso pode ter duas classificações; diz porquê. Escreve as contas que fizeste, e não só o resultado.

Um destes quatro casos obriga-te a tomar uma decisão que a regra da cantina não toma. Descobre qual, explica numa ou duas frases onde está o problema e escreve a decisão que tomarias. Não há uma só decisão certa, mas a tua tem de ficar escrita e justificada.

Concluíste a alínea b) quando tiveres os quatro casos calculados, cada um classificado, e a decisão escrita para o caso que a regra não resolve.

## Exercício 2: Decompor e encontrar ambiguidades

A biblioteca da escola empresta livros. Alguém escreveu estas instruções para um aluno novo que vai ficar ao balcão:

1. Recebe o cartão do aluno.
2. Confirma se o aluno pode levar mais livros.
3. Procura o livro na prateleira.
4. Regista o empréstimo.
5. Diz ao aluno quando tem de devolver.
6. Se o livro estiver emprestado, resolve a situação.

a) Decompõe o processo de empréstimo em subproblemas, com o critério que aprendeste. Cada subproblema tem de ter um objetivo claro e poder ser verificado sozinho. Escreve entre três e cinco subproblemas, cada um com o seu objetivo numa frase, e explica numa frase porque paraste nesse nível.

b) Várias destas instruções são ambíguas, porque não dizem o suficiente para serem executadas sem perguntar nada a ninguém. Identifica pelo menos quatro e escreve, para cada uma, a pergunta com que ficaste sem resposta. Lembra-te de que a ambiguidade não é só a palavra vaga. Também há informação que falta, frases com duas leituras e limites por definir.

c) Reescreve a instrução 2 e mais uma à tua escolha, de forma a não deixarem dúvidas. Inventa os números e os limites que forem precisos, desde que fiquem escritos.

Testa também o caso em que o aluno chega ao balcão já com o número máximo de livros levantados. As instruções dizem o que fazer? Se não dizem, a tua reescrita da instrução 2 tem de o dizer.

Concluíste quando as instruções reescritas puderem ser executadas por alguém que nunca esteve naquela biblioteca.

## Exercício 3: Analisar um problema com autonomia

A escola vai emprestar tablets aos alunos durante as aulas. Há 15 tablets numerados. Um aluno pede um tablet no início da aula e devolve-o no fim. Cada tablet tem de ser devolvido pelo mesmo aluno que o levou, e nenhum aluno pode ter mais do que um tablet ao mesmo tempo. No fim da aula, o responsável tem de saber se falta algum tablet e qual.

Produz uma análise completa deste problema:

a) A tabela com as quatro perguntas.

b) A decomposição em subproblemas.

c) O algoritmo, em passos numerados, de um desses subproblemas: emprestar um tablet.

d) Uma simulação numa tabela, como a do passo 4 do exemplo guiado da papelaria. Simula uma aula em que três alunos levantam tablets e um deles não devolve. Usa uma coluna para o momento e uma coluna para o que acontece. Para o estado dos tablets, usa uma ou mais colunas, com quantos estão livres e quem tem cada um dos que não estão. Identifica os alunos por letras (A, B, C), e nunca pelo nome de um colega. Mostra como o estado muda a cada momento.

Justifica, em duas ou três frases, uma decisão que tenhas tomado e que pudesse ter sido tomada de outra forma. Por exemplo, como decidiste qual o tablet a entregar quando há vários livres.

Concluíste quando outra pessoa conseguir seguir os teus passos com a tua simulação e chegar ao mesmo resultado que tu.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e só passa à seguinte se a anterior não tiver chegado.

- Exercício 1, alínea a): pergunta-te, dado a dado, se isso já existe antes de começares ou se és tu que o produzes. O que já existe é entrada, e o que produzes é saída. Depois, procura no enunciado as palavras que exprimem limites ("só", "cabem", "mínimo"), porque é aí que costumam estar as restrições. Para as condições, procura situações que possam acontecer num dia e não acontecer noutro.
- Exercício 1, alínea b): para cada caso, faz três contas, por esta ordem:
  1. quantas garrafas faltam para chegar ao mínimo;
  2. quantas caixas de 12 são precisas para cobrir essa falta, lembrando que não se encomendam meias caixas;
  3. com quantas garrafas a arca fica depois.

  Depois, compara esse último número com o espaço da arca.
- Exercício 2: para encontrares as ambiguidades, faz a cada instrução três perguntas. Quantos? Onde? E se não der? Se alguma das três ficar sem resposta, a instrução é quase de certeza ambígua. Faz ainda uma quarta pergunta: tenho tudo o que preciso para fazer isto?
- Exercício 3: começa pelo estado. Antes de pensares nos passos, escreve que informação é preciso ter guardada em cada momento para se saber quem tem cada tablet. Quando souberes o que é preciso guardar, os passos aparecem quase sozinhos.

## Desafio opcional

Volta ao exercício 3 e muda uma só restrição. Passa a haver 8 tablets para uma turma de 20 alunos.

Escreve o que muda na tua análise. Diz que condição nova aparece, que passos do algoritmo têm de ser alterados e que passos se mantêm exatamente iguais. Não reescrevas tudo. Identifica a diferença.

No fim, responde à pergunta que interessa. Uma solução bem decomposta tem de aguentar uma mudança destas sem ser toda deitada fora. A tua aguentou?

## Para ires mais longe

Esta secção é opcional. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e o desafio e quer mais prática, ou para estudar em casa.

### Mais longe 1: Mais dois casos para a água

Volta à água do exercício 1 b) e calcula mais dois casos: restam 5 garrafas e restam 25 garrafas. No caso de 5, confirma que as caixas que encomendas fazem mesmo a água chegar ao mínimo. No caso de 25, decide se é um caso normal ou extremo, e justifica.

### Mais longe 2: Verificar no fim da aula

Volta aos tablets do exercício 3. Escreve o algoritmo, em passos numerados, do subproblema que verifica, no fim da aula, se falta algum tablet e qual. Vais precisar de dizer que a mesma verificação se repete para cada tablet. Escreve-o em português simples, como "verificar cada um dos 15 tablets, um a um". A forma organizada de escrever repetições aprende-se no tema 04, Repetição e padrões. Aqui, basta dizê-lo com clareza.

## Critérios de conclusão

- [ ] Respondi às quatro perguntas em todos os exercícios que as pedem.
- [ ] Escrevi exemplos concretos com o resultado calculado à mão, incluindo pelo menos um caso de fronteira e um caso extremo.
- [ ] A minha decomposição tem subproblemas com um objetivo claro e verificáveis um a um.
- [ ] Os meus passos não têm palavras vagas, e onde há quantidades há números.
- [ ] Testei o caso normal e pelo menos um caso em que algo corre mal.
- [ ] Escrevi as decisões que tomei onde o enunciado não dizia o que fazer.
- [ ] Escrevi os algoritmos em passos numerados, sem usar notação que ainda não aprendi.
- [ ] Guardei a ficha de análise para usar no tema seguinte.

## Autoavaliação

1. O que já consegues fazer sozinho, sem voltar ao guia?
2. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
