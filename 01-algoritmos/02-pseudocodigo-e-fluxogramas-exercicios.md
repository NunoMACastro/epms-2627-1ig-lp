# Ficha de exercícios — Pseudocódigo e fluxogramas

UC: UC00245

Blocos: ALG02

Requisitos: UC00245-R02, UC00245-R03, UC00245-R04, UC00245-K03, UC00245-K04, UC00245-K06, UC00245-A05, UC00245-A06, UC00245-C01, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG02, acompanha o [guia](02-pseudocodigo-e-fluxogramas.md) |
| Tempo total | 120 minutos dos 300 do bloco |
| Entrega | Pseudocódigo, ficheiros dos fluxogramas e tabelas de trace |

## Objetivos e conceitos necessários

Vais praticar a escrita de algoritmos em pseudocódigo, o desenho dos mesmos algoritmos em fluxograma e a verificação da execução por trace.

Antes de começares, deves conseguir declarar variáveis com o tipo certo, distinguir uma atribuição de uma comparação, usar `LER` e `ESCREVER`, e usar `DIV` e `RESTO`. Está tudo no guia deste bloco.

Material: papel quadriculado e a aplicação de desenho de diagramas.

Todos os algoritmos desta ficha são **sequenciais**: as instruções executam-se sempre todas, pela mesma ordem, sem o algoritmo ter de escolher entre caminhos. Não precisas do losango.

## Exercício 1 — Reconhecer e aplicar — 25 min

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

**a)** Diz que tipo tem cada variável e justifica numa frase a escolha de `pesoTotal`.

**b)** Faz o trace completo, com uma coluna por variável, para `artigos` igual a 3 e `pesoPorArtigo` igual a 150. Mostra todas as linhas, não só o resultado.

**c)** Preenche a tabela de resultados para estas três entradas:

| artigos | pesoPorArtigo | pesoTotal |
| ---: | ---: | ---: |
| 3 | 150 | |
| 0 | 150 | |
| 10 | 25 | |

**d)** A terceira linha tem um caso que vale a pena discutir: o que significa o resultado quando não há artigos nenhuns? O algoritmo está errado, ou está certo e apenas a responder a uma pergunta que ninguém queria fazer?

Concluíste quando o teu trace mostrar o valor de todas as variáveis em cada linha e conseguires justificar a resposta à alínea d).

## Exercício 2 — Combinar conceitos — 30 min

A cantina compra leite em grades de 24 pacotes. O fornecedor também vende pacotes soltos. Uma grade custa 1440 cêntimos e um pacote solto custa 70 cêntimos.

Dado o número de pacotes de que a cantina precisa, queremos saber quantas grades completas compra, quantos pacotes soltos compra além dessas grades, e quanto vai pagar ao todo.

**a)** Responde às quatro perguntas — entradas, saídas, restrições e condições — como aprendeste no bloco anterior.

**b)** Escreve o algoritmo em pseudocódigo, com as constantes e as variáveis declaradas e os tipos certos. Usa constantes para os três valores fixos do enunciado.

**c)** Desenha o fluxograma correspondente na aplicação de diagramas e guarda o ficheiro.

**d)** Faz o trace para 100 pacotes e verifica que o fluxograma, percorrido figura a figura, dá exatamente o mesmo resultado que o pseudocódigo.

Testa também 24 pacotes e 10 pacotes.

Concluíste quando as duas representações disserem a mesma coisa e o trace o confirmar.

## Exercício 3 — Resolver com autonomia — 35 min

Uma visita de estudo é feita em autocarros, todos com a mesma capacidade. Dado o número de alunos que vão à visita e a capacidade de cada autocarro, queremos saber quantos autocarros ficam completamente cheios, quantos alunos vão no autocarro que sobra e quantos lugares livres ficam nesse autocarro.

**a)** As quatro perguntas.

**b)** O pseudocódigo completo, com constantes, variáveis, tipos e as instruções pela ordem certa.

**c)** O fluxograma, desenhado na aplicação.

**d)** O trace de três entradas à tua escolha. Escolhe-as de propósito, e explica numa frase por que escolheste cada uma — não sirvam as três para testar a mesma coisa.

**e)** Há pelo menos uma situação em que a tua fórmula dos lugares livres dá um resultado estranho. Descobre qual é, escreve por que acontece e explica o que seria preciso para a resolver. Não precisas de a resolver: as ferramentas para isso são do bloco seguinte. Descobri-la é que conta.

Concluíste quando outra pessoa conseguir executar o teu pseudocódigo com as tuas três entradas e chegar aos mesmos valores.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só a seguinte se a anterior não tiver chegado.

**Exercício 1.** Faz o trace por linhas, não por variáveis: percorre o algoritmo de cima para baixo e, em cada linha, copia os valores que não mudaram e atualiza só o que mudou. Para a alínea d), calcula primeiro e pensa depois no significado.

**Exercício 2.** Começa pelo exemplo dos cadernos do guia, que tem a mesma forma: uma quantidade, uma divisão inteira e um resto. A diferença é que aqui há um preço a multiplicar no fim. Escreve primeiro só as grades e os soltos; acrescenta o custo depois de isso funcionar.

**Exercício 3.** Se `alunos DIV capacidade` te dá os autocarros cheios, o que é que `alunos RESTO capacidade` te dá? E se souberes quantos alunos vão no último autocarro, quantos lugares sobram nele? Para a alínea e), experimenta um número de alunos que seja exatamente igual a dois autocarros cheios.

## Desafio opcional — 30 min

Volta ao exercício 2 e muda uma só coisa: o fornecedor passa a vender grades de 12 pacotes em vez de 24, e a grade passa a custar 780 cêntimos.

**a)** Quantas linhas do teu pseudocódigo precisam de ser alteradas?

**b)** E se, em vez de teres usado constantes, tivesses escrito os números 24 e 1440 diretamente nas contas — quantos sítios terias de procurar e mudar? Conta-os no teu próprio algoritmo, imaginando-o escrito dessa maneira.

**c)** O fluxograma precisa de ser redesenhado, ou basta mudar o texto de algumas figuras? Justifica.

É esta a razão por que se dá nome aos valores fixos. Uma mudança de fornecedor não devia obrigar a reler o algoritmo todo à procura de números soltos.

## Critérios de conclusão

- [ ] Declarei todas as variáveis com um tipo coerente com o que guardam.
- [ ] Usei constantes para os valores fixos, em vez de números escritos nas contas.
- [ ] Usei a seta para dar valores e não usei o sinal de igual para isso.
- [ ] O pseudocódigo e o fluxograma dizem exatamente a mesma coisa, figura a instrução.
- [ ] Os fluxogramas têm um início, pelo menos um fim, e nenhuma seta sem destino.
- [ ] Fiz o trace com três entradas escolhidas de propósito, e não três parecidas.
- [ ] Guardei os ficheiros dos fluxogramas.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:
