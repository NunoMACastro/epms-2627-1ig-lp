![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Do problema ao algoritmo

Praticas a análise de um problema antes de o resolver: o contrato, a decomposição e os passos sem ambiguidades. Os exercícios 1 a 3 são obrigatórios. Resolves em papel, numa folha que entregas, a tua ficha de análise. Os algoritmos escrevem-se em passos numerados, em português. Para rever: o [guia do tema](../01-do-problema-ao-algoritmo.md).

## Exercício 1: O contrato da reposição de bebidas

A cantina da escola recebe todos os dias um pedido de reposição de bebidas. Quem faz o pedido conta o que resta em cada tipo de bebida. Sabe quantas unidades de cada tipo cabem na arca, e sabe que o fornecedor só entrega em caixas de 12 unidades. Cada tipo de bebida tem um mínimo que deve estar sempre disponível, e a cantina pode mudar esse mínimo quando quiser. No fim, é preciso produzir a lista de quantas caixas encomendar de cada tipo.

a) Responde às quatro perguntas sobre este problema, numa tabela com as entradas, as saídas, as restrições e as condições. Tens de conseguir justificar porque puseste cada coisa nessa coluna, e não noutra.

b) Para a água, a regra é encomendar o menor número de caixas que faz a água chegar pelo menos ao mínimo, de 20 garrafas. Na arca cabem no máximo 30 garrafas de água, e o fornecedor só entrega caixas de 12. Calcula à mão quantas caixas se encomendam e com quantas garrafas a arca fica, nestes quatro casos: restam 12, 0, 20 e 19 garrafas. Numa tabela, diz também se cada caso é normal, de fronteira ou extremo, e porquê; um caso pode ter duas classificações. Escreve as contas.

c) Um destes casos obriga-te a tomar uma decisão que a regra da cantina não toma. Diz qual, onde está o problema e que decisão tomarias, com a razão.

Rever: [O contrato do problema](../01-do-problema-ao-algoritmo.md#o-contrato-do-problema-entradas-saídas-restrições-e-condições), [Exemplos concretos](../01-do-problema-ao-algoritmo.md#exemplos-concretos) e [Instruções ambíguas](../01-do-problema-ao-algoritmo.md#instruções-ambíguas).

<details>
<summary>Pista</summary>

Na alínea a), pergunta-te, dado a dado, se já existe antes de começares ou se és tu que o produzes. Pergunta-te também se pode mudar de uma vez para a outra. Na alínea b), faz três contas por caso: quantas garrafas faltam, quantas caixas cobrem essa falta, sem meias caixas, e com quantas a arca fica.

</details>

## Exercício 2: Decompor e encontrar ambiguidades

A biblioteca da escola empresta livros. Alguém escreveu estas instruções para um aluno novo que vai ficar ao balcão:

1. Recebe o cartão do aluno.
2. Confirma se o aluno pode levar mais livros.
3. Procura o livro na prateleira.
4. Regista o empréstimo.
5. Diz ao aluno quando tem de devolver.
6. Se o livro estiver emprestado, resolve a situação.

a) Decompõe o processo de empréstimo em três a cinco subproblemas, cada um com o seu objetivo numa frase. Diz também porque paraste nesse nível.

b) Encontra pelo menos quatro instruções ambíguas e escreve, para cada uma, a pergunta com que ficaste sem resposta.

c) Reescreve a instrução 2 e mais uma à tua escolha, sem deixar dúvidas. Inventa os números e os limites que forem precisos, desde que fiquem escritos. A tua instrução 2 tem de dizer o que fazer a um aluno que chega já com o número máximo de livros.

Rever: [Decompor um problema em subproblemas](../01-do-problema-ao-algoritmo.md#decompor-um-problema-em-subproblemas) e [Instruções ambíguas](../01-do-problema-ao-algoritmo.md#instruções-ambíguas).

<details>
<summary>Pista</summary>

Faz a cada instrução as perguntas da coluna "A pergunta que a apanha", na tabela das formas de ambiguidade do guia.

</details>

## Exercício 3: Os tablets da aula

A escola empresta tablets aos alunos durante as aulas. Há 15 tablets numerados, um para cada aluno da turma. Um aluno pede um tablet no início da aula e devolve-o no fim. Cada tablet tem de ser devolvido pelo mesmo aluno que o levou, e nenhum aluno pode ter mais do que um tablet ao mesmo tempo. No fim da aula, o responsável tem de saber se falta algum tablet e qual.

a) A tabela das quatro perguntas.

b) A decomposição em subproblemas.

c) O algoritmo, em passos numerados, do subproblema "emprestar um tablet".

d) Uma simulação numa tabela, como a do exemplo guiado da papelaria, de uma aula em que três alunos levantam tablets e um não devolve. As colunas dizem o momento, o que acontece e o estado dos tablets: quantos estão livres e quem tem cada um dos outros. Identifica os alunos por letras, como A, B e C.

e) Uma decisão que tomaste e que podia ser outra, em duas ou três frases.

Rever: [Ação e estado](../01-do-problema-ao-algoritmo.md#ação-e-estado), [As etapas para construir um algoritmo](../01-do-problema-ao-algoritmo.md#as-etapas-para-construir-um-algoritmo) e [Etapa 5: simular com um caso concreto](../01-do-problema-ao-algoritmo.md#etapa-5-simular-com-um-caso-concreto).

<details>
<summary>Pista</summary>

Começa pelo estado. Antes dos passos, escreve o que é preciso ter guardado em cada momento para se saber quem tem cada tablet. Depois, os passos de emprestar aparecem quase sozinhos.

</details>

## Desafios

### Desafio 1: Menos tablets do que alunos

Volta ao exercício 3 e muda uma só restrição: a turma passa a ter 20 alunos, e os tablets continuam a ser 15. Diz que condição nova aparece, que passos do algoritmo mudam e quais ficam iguais, sem reescrever tudo. No fim, responde: a tua decomposição aguentou a mudança?

### Desafio 2: Mais dois casos para a água

Calcula mais dois casos da água do exercício 1: restam 5 garrafas e restam 25 garrafas. No caso de 5, confirma que as caixas chegam ao mínimo. No caso de 25, diz se é normal ou extremo, e porquê.

### Desafio 3: Verificar no fim da aula

Escreve, em passos numerados, o subproblema dos tablets que verifica, no fim da aula, se falta algum e qual. A mesma verificação repete-se para cada tablet: diz-o em português simples, como "verificar cada um dos 15 tablets, um a um".

## Critérios de conclusão

- Respondi às quatro perguntas nos exercícios 1 e 3, e sei justificar cada coluna.
- Os exemplos da água têm as contas, a classificação e a decisão escrita para o caso que a regra não resolve.
- A decomposição tem subproblemas com um objetivo claro, verificáveis um a um.
- As instruções reescritas e o algoritmo dos tablets não têm palavras vagas, e onde há quantidades há números.
- A simulação dos tablets mostra o estado a mudar a cada momento, também no aluno que não devolve.

![Rodapé](../../imagens/rodape.png)
