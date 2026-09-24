![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Pseudocódigo e fluxogramas

UC: UC00245

Blocos: ALG02

Requisitos: UC00245-R02, UC00245-R03, UC00245-R04, UC00245-K03, UC00245-K04, UC00245-K05, UC00245-K06, UC00245-A05, UC00245-A06, UC00245-C01, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG02, acompanha o [guia](02-pseudocodigo-e-fluxogramas.md) e o [laboratório](02-pseudocodigo-e-fluxogramas-laboratorio.md) |
| Tempo total | 120 minutos dos 300 do bloco: 90 de prática autónoma e 30 de desafio opcional |
| Entrega | Respostas escritas, pseudocódigo, tabelas de trace e os ficheiros `.drawio` e `.png` dos fluxogramas |

## Objetivos e conceitos necessários

Vais praticar, sem ajuda, tudo o que o bloco ensinou: escolher tipos de dados, distinguir uma atribuição de uma comparação, calcular expressões com as funções predefinidas, escrever algoritmos em pseudocódigo, desenhá-los em fluxograma e verificar a execução com uma tabela de trace.

Antes de começares, deves ter estudado o guia deste bloco e feito o laboratório. Do guia precisas de tudo: tipos, atribuição, `LER` e `ESCREVER`, expressões com `DIV` e `RESTO`, as quatro funções predefinidas, a convenção de pseudocódigo, os símbolos do fluxograma e a tabela de trace. Do laboratório precisas de saber desenhar, guardar e exportar um fluxograma no diagrams.net.

Material: papel quadriculado, lápis e o diagrams.net, em `https://app.diagrams.net/?lang=pt`. Guarda os ficheiros na pasta `algoritmos` que usaste no laboratório, com nomes em minúsculas, com hífenes e sem acentos.

Todos os algoritmos desta ficha são sequenciais: as instruções executam-se sempre todas, pela mesma ordem, sem o algoritmo ter de escolher entre caminhos. Não precisas do losango.

Os exercícios estão por ordem de dificuldade. Os dois primeiros treinam peças soltas; o terceiro pede que leias e sigas um algoritmo feito; o quarto e o quinto pedem que construas um algoritmo completo.

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Tipos e atribuição | 15 min |
| 2 | Expressões e funções predefinidas | 15 min |
| 3 | Ler um algoritmo e fazer o trace | 15 min |
| 4 | Construir um algoritmo, o fluxograma e o trace | 20 min |
| 5 | Resolver com autonomia e escolher os testes | 25 min |
| Desafio | Mudar uma regra e ver o que muda | 30 min |

## Exercício 1: Tipos e atribuição (15 min)

**a)** Diz que tipo de dados usarias para guardar cada um destes valores, e justifica cada escolha numa frase:

1. o número de alunos inscritos numa visita de estudo;
2. o preço de uma resma de papel, em cêntimos;
3. o nome de um fornecedor;
4. o código postal de uma loja, como 4000-123;
5. o código de barras de um artigo, com 13 algarismos;
6. o peso de uma encomenda, em quilogramas, como 2,35;
7. se um artigo está em promoção ou não;
8. a média das vendas diárias de uma semana.

**b)** Faz o trace desta sequência de atribuições, com uma coluna por variável e uma linha por instrução:

```text
    stock ← 50
    vendas ← 12
    stock ← stock - vendas
    reposicao ← stock + 20
    vendas ← vendas + 8
    stock ← stock - vendas
```

No fim, responde: `reposicao` ficou igual ao valor final de `stock` mais 20? Explica porquê, a partir do que a atribuição faz.

**c)** Um algoritmo tem estas declarações:

```text
CONSTANTES
    LIMITE_DE_SENHAS ← 40
VARIÁVEIS
    caixas: inteiro
    total: inteiro
    preco: inteiro
    quantidade: inteiro
    pago: lógico
    nome: texto
```

Para cada uma das linhas seguintes, diz se é uma atribuição correta, uma comparação ou um erro. Se for um erro, explica-o numa frase. Se for uma comparação, diz o que ela responde quando `caixas` vale 5 e `total` vale 1000.

| Linha | Instrução |
| ---: | --- |
| 1 | `caixas ← 5` |
| 2 | `caixas = 5` |
| 3 | `5 ← caixas` |
| 4 | `total ← total + preco` |
| 5 | `total + preco ← total` |
| 6 | `pago ← FALSO` |
| 7 | `LIMITE_DE_SENHAS ← 50` |
| 8 | `total = total + 1` |
| 9 | `nome ← "Papelaria Central"` |
| 10 | `quantidade ← "12"` |

**d)** Duas variáveis começam assim:

```text
    caixaA ← 12
    caixaB ← 30
```

Escreve as instruções que trocam os valores das duas, de forma que no fim `caixaA` valha 30 e `caixaB` valha 12. Podes usar uma variável a mais, se precisares, e tens de a declarar com o tipo certo. Faz o trace da tua solução, desde as duas linhas acima, para mostrar que funciona.

Concluíste quando cada tipo tiver uma justificação que fale do que se faz com o valor, e quando a tua troca funcionar no trace.

## Exercício 2: Expressões e funções predefinidas (15 min)

**a)** Calcula o valor de cada expressão e escreve o tipo do resultado, inteiro ou real. Faz as contas à mão, pela ordem das operações. Num resultado real, escreve sempre a parte decimal, mesmo que seja `.0`.

| N.º | Expressão | Valor | Tipo |
| ---: | --- | --- | --- |
| 1 | `3 + 4 * 5` | | |
| 2 | `(3 + 4) * 5` | | |
| 3 | `30 - 10 - 5` | | |
| 4 | `40 / 8 / 2` | | |
| 5 | `23 DIV 4` | | |
| 6 | `23 RESTO 4` | | |
| 7 | `23 / 4` | | |
| 8 | `4 RESTO 23` | | |
| 9 | `9 DIV 2` | | |
| 10 | `ARREDONDAR(9 / 2)` | | |
| 11 | `ABS(6 - 11)` | | |
| 12 | `ARREDONDAR(4.5)` | | |
| 13 | `ARREDONDAR(4.49)` | | |
| 14 | `TRUNCAR(8.99)` | | |
| 15 | `TRUNCAR(-8.99)` | | |
| 16 | `RAIZ(36 + 64)` | | |
| 17 | `RAIZ(36) + RAIZ(64)` | | |

Depois escolhe as duas expressões da tabela que achas que enganam mais gente e explica, para cada uma, qual é o engano.

**b)** Escreve uma atribuição para cada situação. Para cada uma, escreve também a declaração da variável que recebe o resultado, com o tipo que escolheste, e o valor que ela fica a ter com os valores de teste indicados.

1. A variável `horasCompletas` deve ficar com o número de horas completas de um trabalho cuja duração, em horas, está na variável real `tempoEmHoras`. Testa com `tempoEmHoras` igual a 3.75.
2. A variável `mediaArredondada` deve ficar com a média de duas notas inteiras, `nota1` e `nota2`, arredondada às unidades. Testa com `nota1` igual a 13 e `nota2` igual a 14.
3. A variável `distancia` deve ficar com o número de senhas que separam a senha que está a ser atendida, `senhaAtual`, da senha de um cliente, `senhaCliente`, sem sinal, seja qual for a maior. Testa com `senhaAtual` igual a 42 e `senhaCliente` igual a 57.
4. A variável `lado` deve ficar com o comprimento, em metros, do lado de um armazém quadrado cuja área, em metros quadrados, está na variável `area`. Testa com `area` igual a 225.

Concluíste quando cada atribuição usar a função certa, com os parênteses no sítio certo, e o valor de teste estiver calculado.

## Exercício 3: Ler um algoritmo e fazer o trace (15 min)

Lê este algoritmo com atenção:

```text
ALGORITMO EnvioDeEncomenda
CONSTANTES
    PESO_DA_CAIXA_VAZIA ← 200
VARIÁVEIS
    artigos: inteiro
    pesoPorArtigo: inteiro
    pesoTotal: inteiro
INÍCIO
    ESCREVER "Quantos artigos leva a encomenda?"
    LER artigos
    ESCREVER "Quanto pesa cada artigo, em gramas?"
    LER pesoPorArtigo
    pesoTotal ← artigos * pesoPorArtigo + PESO_DA_CAIXA_VAZIA
    ESCREVER "Peso total em gramas: ", pesoTotal
FIM
```

**a)** Justifica numa frase porque é que `pesoTotal` pode ser inteiro, sendo um peso.

**b)** Faz o trace completo, com uma coluna por variável e uma para o ecrã, para `artigos` igual a 3 e `pesoPorArtigo` igual a 150. Mostra todas as linhas, e não só o resultado.

**c)** Preenche a tabela de resultados para estas três entradas:

| artigos | pesoPorArtigo | pesoTotal |
| ---: | ---: | ---: |
| 3 | 150 | |
| 0 | 150 | |
| 10 | 25 | |

**d)** A segunda linha tem um caso que vale a pena discutir: o que significa o resultado quando não há artigos nenhuns? O algoritmo está errado, ou está certo e apenas a responder a uma pergunta que ninguém queria fazer?

**e)** Um colega escreveu a conta assim:

```text
    pesoTotal ← artigos * (pesoPorArtigo + PESO_DA_CAIXA_VAZIA)
```

Calcula o resultado da versão dele com 3 artigos de 150 gramas e compara com o da alínea b). Qual das duas versões está certa? Explica a diferença pela ordem das operações e pelo que o problema pede.

Concluíste quando o teu trace mostrar o valor de todas as variáveis em cada linha e conseguires justificar as respostas às alíneas d) e e).

## Exercício 4: Construir um algoritmo completo (20 min)

A cantina compra leite em grades de 24 pacotes. O fornecedor também vende pacotes soltos. Uma grade custa 1440 cêntimos e um pacote solto custa 70 cêntimos.

Dado o número de pacotes de que a cantina precisa, queremos saber quantas grades completas compra, quantos pacotes soltos compra além dessas grades, e quanto vai pagar ao todo.

**a)** Escreve o contrato: responde às quatro perguntas (entradas, saídas, restrições e condições).

**b)** Escreve o algoritmo em pseudocódigo, com as constantes e as variáveis declaradas e os tipos certos. Usa constantes para os três valores fixos do enunciado.

**c)** Desenha o fluxograma na aplicação, guarda o ficheiro com o nome `fluxograma-compra-de-leite.drawio` e exporta a imagem PNG.

**d)** Faz o trace completo para 100 pacotes e verifica que o fluxograma, percorrido figura a figura, dá exatamente o mesmo resultado que o pseudocódigo. Depois preenche só a tabela de resultados para 24 pacotes e para 10 pacotes.

Concluíste quando as duas representações disserem a mesma coisa e o trace o confirmar.

## Exercício 5: Resolver com autonomia (25 min)

Uma visita de estudo é feita em autocarros, todos com a mesma capacidade. Dado o número de alunos que vão à visita e a capacidade de cada autocarro, queremos saber quantos autocarros ficam completamente cheios, quantos alunos vão no autocarro que sobra e quantos lugares livres ficam nesse autocarro.

**a)** O contrato, com as quatro perguntas.

**b)** O pseudocódigo completo, com constantes se houver valores fixos, variáveis, tipos e as instruções pela ordem certa. Decide se a capacidade é uma constante ou um dado que se lê, e justifica a decisão numa frase.

**c)** O fluxograma, desenhado na aplicação, guardado como `fluxograma-autocarros-da-visita.drawio` e exportado em PNG.

**d)** O trace de três entradas à tua escolha. Escolhe-as de propósito, e explica numa frase porque escolheste cada uma. As três não podem servir para testar a mesma coisa.

**e)** Há pelo menos uma situação em que a tua fórmula dos lugares livres dá um resultado estranho. Descobre qual é, escreve porque acontece e explica o que seria preciso para a resolver. Não precisas de a resolver: as ferramentas para isso são do bloco seguinte. Descobri-la é que conta.

Concluíste quando outra pessoa conseguir executar o teu pseudocódigo com as tuas três entradas e chegar aos mesmos valores.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Na alínea a), pergunta sempre: vou fazer contas com este valor? E a parte decimal interessa? Na alínea b), faz o trace por linhas, não por variáveis: em cada linha, copia os valores que não mudaram e atualiza só o que mudou. Na alínea c), lê cada linha em voz alta: é uma ordem ou uma pergunta? E o que está à esquerda da seta pode receber um valor? Na alínea d), relê a troca falhada da secção da atribuição, no guia, e pensa nos dois copos: para trocar os líquidos precisas de um terceiro copo.

**Exercício 2.** Na alínea a), faz primeiro os parênteses, depois as multiplicações e divisões da esquerda para a direita, e só depois as somas e subtrações. Para as funções, relê os casos que enganam de cada uma, no guia. Na alínea b), decide primeiro que função serve: cortar as casas decimais, arredondar, tirar o sinal ou calcular uma raiz. Na média, pensa no que tem de ser dividido por dois.

**Exercício 3.** Para a alínea d), calcula primeiro e pensa depois no significado. Para a alínea e), faz as duas contas com os mesmos valores e pergunta-te qual delas soma o peso da caixa uma vez só.

**Exercício 4.** Começa pelo exemplo dos cadernos do guia, que tem a mesma forma: uma quantidade, uma divisão inteira e um resto. A diferença é que aqui há um preço a multiplicar no fim. Escreve primeiro só as grades e os soltos; acrescenta o custo depois de isso funcionar.

**Exercício 5.** Se `alunos DIV capacidade` te dá os autocarros cheios, o que é que `alunos RESTO capacidade` te dá? E se souberes quantos alunos vão no último autocarro, quantos lugares sobram nele? Para a alínea e), experimenta um número de alunos que seja exatamente igual a dois autocarros cheios.

## Desafio opcional (30 min)

Volta ao exercício 4 e muda uma só coisa: o fornecedor passa a vender grades de 12 pacotes em vez de 24, e a grade passa a custar 780 cêntimos. O pacote solto continua a 70 cêntimos.

**a)** Quantas linhas do teu pseudocódigo precisam de ser alteradas?

**b)** E se, em vez de teres usado constantes, tivesses escrito os números 24 e 1440 diretamente nas contas? Conta quantos sítios terias de procurar e mudar no teu próprio algoritmo, imaginando-o escrito dessa maneira.

**c)** O fluxograma precisa de ser redesenhado, ou basta mudar o texto de algumas figuras? Justifica.

**d)** Refaz a tabela de resultados para 100 pacotes com os valores novos.

**e)** Com as grades de 24 do exercício 4, há casos em que a cantina paga pelos pacotes soltos mais do que pagaria por uma grade inteira, que ainda traz mais pacotes. Encontra um desses casos e mostra as contas. Com as grades novas, de 12 pacotes a 780 cêntimos, isso ainda pode acontecer? Justifica com contas.

É esta a razão por que se dá nome aos valores fixos. Uma mudança de fornecedor não devia obrigar a reler o algoritmo todo à procura de números soltos.

## Critérios de conclusão

- [ ] Escolhi o tipo de cada valor pelo que vou fazer com ele, e justifiquei.
- [ ] Usei a seta para dar valores e nunca usei o sinal de igual para isso.
- [ ] Calculei as expressões pela ordem das operações e usei as funções predefinidas com os parênteses no sítio certo.
- [ ] Declarei todas as variáveis com um tipo coerente com o que guardam.
- [ ] Usei constantes para os valores fixos, em vez de números escritos nas contas.
- [ ] O pseudocódigo e o fluxograma dizem exatamente a mesma coisa, figura a figura e instrução a instrução.
- [ ] Os fluxogramas têm um início, pelo menos um fim, e nenhuma seta sem destino.
- [ ] Fiz o trace com três entradas escolhidas de propósito, e não três parecidas.
- [ ] Guardei os ficheiros `.drawio` e exportei as imagens dos fluxogramas.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
