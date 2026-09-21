![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Do problema ao algoritmo

UC: UC00245

Blocos: ALG01

Requisitos: UC00245-R01, UC00245-R02, UC00245-K02, UC00245-A03, UC00245-A04, UC00245-P01

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG01, acompanha o [guia](01-do-problema-ao-algoritmo.md) |
| Tempo total | 120 minutos dos 300 do bloco |
| Entrega | Ficha de análise com as quatro perguntas, decomposição e algoritmo, em papel ou em ficheiro de texto |

## Objetivos e conceitos necessários

Vais praticar a análise de um problema antes de o resolver: separar entradas, saídas, restrições e condições, partir o problema em subproblemas e escrever passos sem ambiguidades.

Antes de começares, deves conseguir explicar o que é um algoritmo, o que distingue uma restrição de uma condição, e por que razão uma instrução vaga não determina uma solução. Tudo isso está no guia deste bloco.

Material: papel e caneta ou um editor de texto. Não precisas de computador para programar. Nada nesta ficha se escreve numa linguagem de programação.

Escreve os algoritmos em passos numerados, em português, tal como no exemplo do guia. Pseudocódigo e fluxogramas são o assunto do próximo bloco; aqui não são precisos.

## Exercício 1: Reconhecer e aplicar (25 min)

A cantina da escola recebe todos os dias um pedido de reposição de bebidas. Quem faz o pedido conta o que resta em cada tipo de bebida, sabe quantas unidades cabem na arca e sabe que o fornecedor só entrega em caixas de 12 unidades. Cada tipo de bebida tem um mínimo que deve estar sempre disponível. No fim, é preciso produzir a lista de quantas caixas encomendar de cada tipo.

Responde às quatro perguntas sobre este problema, numa tabela:

| Pergunta | Resposta |
| --- | --- |
| Entradas | |
| Saídas | |
| Restrições | |
| Condições | |

Exemplo do tipo de resultado esperado: para um tipo de bebida qualquer, o resultado é um número de caixas, nunca um número de unidades soltas.

Concluíste quando tiveres pelo menos duas entradas, uma saída, duas restrições e uma condição, e conseguires justificar por que colocaste cada uma nessa coluna e não noutra.

## Exercício 2: Combinar conceitos (30 min)

A biblioteca da escola empresta livros. Alguém escreveu estas instruções para um aluno novo que vai ficar ao balcão:

1. Recebe o cartão do aluno.
2. Confirma se o aluno pode levar mais livros.
3. Procura o livro na prateleira.
4. Regista o empréstimo.
5. Diz ao aluno quando tem de devolver.
6. Se o livro estiver emprestado, resolve a situação.

**a)** Decompõe o processo de empréstimo em subproblemas, com o critério que aprendeste: cada subproblema tem de ter objetivo claro e poder ser verificado sozinho. Escreve entre três e cinco subproblemas e explica numa frase por que paraste nesse nível.

**b)** Várias destas instruções são ambíguas: não dizem o suficiente para serem executadas sem perguntar nada a ninguém. Identifica pelo menos quatro e escreve, para cada uma, a pergunta que ficaste sem resposta.

**c)** Reescreve duas dessas instruções de forma a não deixarem dúvidas. Inventa os números e os limites que forem precisos, desde que fiquem escritos.

Testa também o caso em que o aluno chega ao balcão já com o número máximo de livros levantados: as instruções dizem o que fazer?

Concluíste quando as instruções reescritas puderem ser executadas por alguém que nunca esteve naquela biblioteca.

## Exercício 3: Resolver com autonomia (35 min)

A escola vai emprestar tablets aos alunos durante as aulas. Há 15 tablets numerados. Um aluno pede um tablet no início da aula e devolve-o no fim. Cada tablet tem de ser devolvido pelo mesmo aluno que o levou, e nenhum aluno pode ter mais do que um tablet ao mesmo tempo. No fim da aula, o responsável tem de saber se falta algum tablet e qual.

Produz uma análise completa deste problema:

**a)** A tabela com as quatro perguntas.

**b)** A decomposição em subproblemas.

**c)** O algoritmo, em passos numerados, de dois desses subproblemas: **emprestar um tablet** e **verificar no fim da aula se falta algum**.

Para o segundo vais precisar de dizer que a mesma verificação se repete para cada tablet. Escreve-o em português simples ("verificar cada um dos 15 tablets, um a um") e segue em frente. A forma organizada de escrever repetições aprende-se daqui a dois blocos; aqui basta dizê-lo com clareza.

**d)** Uma simulação numa tabela, à maneira do exemplo do guia, com uma aula em que três alunos levantam tablets e um deles não devolve. Mostra como o estado muda a cada momento.

Justifica, em duas ou três frases, uma decisão que tenhas tomado e que pudesse ter sido tomada de outra forma. Por exemplo: como decidiste qual o tablet a entregar quando há vários livres.

Concluíste quando outra pessoa conseguir seguir os teus passos com a tua simulação e chegar ao mesmo resultado que tu.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Pergunta-te, dado a dado: isto já existe antes de eu começar, ou sou eu que o produzo? O que já existe é entrada, o que produzes é saída. Depois, procura no enunciado as palavras que exprimem limites ("só", "cabem", "mínimo"), porque é aí que costumam estar as restrições.

**Exercício 2.** Para encontrar as ambiguidades, faz a cada instrução três perguntas: quantos? onde? e se não der? A instrução que não responder a nenhuma das três é quase de certeza ambígua.

**Exercício 3.** Começa pelo estado: antes de pensares nos passos, escreve que informação é preciso ter guardada em cada momento para se saber quem tem cada tablet. Quando souberes o que é preciso guardar, os passos aparecem quase sozinhos.

## Desafio opcional (30 min)

Volta ao exercício 3 e muda **uma só** restrição: passa a haver 8 tablets para uma turma de 20 alunos, e por isso pode acontecer um aluno pedir um tablet quando já não há nenhum livre.

Escreve o que muda na tua análise: que condição nova aparece, que passos do algoritmo têm de ser alterados e que passos se mantêm exatamente iguais. Não reescrevas tudo. Identifica a diferença.

Esta é a pergunta que interessa: uma solução bem decomposta tem de aguentar uma mudança destas sem ser toda deitada fora. A tua aguentou?

## Critérios de conclusão

- [ ] Respondi às quatro perguntas em todos os exercícios que as pedem.
- [ ] A minha decomposição tem subproblemas com objetivo claro e verificáveis um a um.
- [ ] Os meus passos não têm palavras vagas: onde há quantidades, há números.
- [ ] Testei o caso normal e pelo menos um caso em que algo corre mal.
- [ ] Escrevi os algoritmos em passos numerados, sem usar notação que ainda não aprendi.
- [ ] Guardei a ficha de análise para usar no próximo bloco.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
