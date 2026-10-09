![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Testar, depurar e melhorar

UC: UC00245

Blocos: ALG05

Requisitos: UC00245-R03, UC00245-R04, UC00245-R05, UC00245-A06, UC00245-A07, UC00245-A08, UC00245-C01, UC00245-C02, UC00245-C03, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | Ficha do bloco ALG05, acompanha o [guia](05-testar-depurar-e-melhorar.md) |
| Tempo total | 99 minutos: 60 nos exercícios 1 a 4 e 39 nos exercícios 5 a 7, das funções, que entraram no bloco depois de ele estar planeado. O fecho do portefólio, com o contrato e o teste do algoritmo do exercício 4, faz-se na última aula do bloco. O desafio e a secção "Para ires mais longe" são opcionais e ficam fora destes 99 minutos |
| Entrega | A tabela de casos do exercício 1, o registo de depuração do exercício 2, a contagem de passos do exercício 3 e o exercício 4, que ficam no teu portefólio, juntamente com o contrato e a tabela de casos executada do fecho do portefólio e, se o professor o indicar, o fluxograma |

## Objetivos e conceitos necessários

Vais praticar sozinho o que o guia deste bloco explica: escolher casos de teste antes de executar um algoritmo, encontrar um erro com o método de depuração, contar os passos de um algoritmo e melhorá-lo sem mudar o que ele faz, e, no fim, construir um algoritmo pequeno a partir de uma tabela de casos escrita antes dele. Testar esse algoritmo com a tabela fica para o fecho do portefólio, na última aula do bloco. Nos exercícios 5 a 7 praticas a parte das funções do guia: ler uma função e as suas chamadas, escrever uma função a partir do seu contrato e trocar uma parte repetida por uma função.

Antes de começares, deves ter lido a teoria e o exemplo explicado do [guia](05-testar-depurar-e-melhorar.md), incluindo os passos 9 e 10 do exemplo, que mostram como se melhora um algoritmo e como se contam os passos. Também deves conseguir fazer uma tabela de iterações, escrever uma cadeia de `Se` e `Senão se`, ler um `Para` e um ciclo com sentinela, e usar contadores e totalizadores: está tudo nos guias 02, 03 e 04. Para os exercícios 5 a 7, precisas da parte das funções do guia 05 e do intervalo com `e` do guia 03. Cada exercício diz em que secção do guia 05 está a matéria. Se encravares, volta a essa secção antes de olhares para o apoio.

Os algoritmos que a ficha te dá estão na forma de pseudocódigo das aulas, em que a indentação mostra o que está dentro de cada `Se`, de cada `Enquanto` e de cada `Para`. Quando fores tu a escrever um algoritmo, ou uma parte dele, podes usar essa forma ou frases claras, desde que não deixem dúvidas sobre quanto, quando e o que acontece se não der. O que conta é a lógica.

Material: papel e lápis. O diagrams.net, em `https://app.diagrams.net`, só é preciso na alínea b) do fecho do portefólio, que é de fluxogramas e só se faz quando o professor o indicar.

## Como está organizada a ficha

Resolve os exercícios pela ordem. Nos dois primeiros aplicas o que o guia mostrou: no exercício 1 escolhes casos de teste e usas-os para testar um algoritmo curto, e no exercício 2 segues os quatro primeiros passos do método de depuração, um passo por alínea; o quinto, voltar a testar tudo, está no Mais longe 5, que é opcional. No exercício 3 decides: contas os passos de um algoritmo que já está certo e escreves uma versão que faz menos trabalho. No exercício 4 constróis um algoritmo pequeno do princípio ao fim, a partir da tabela de casos que escreves antes dele; testá-lo com essa tabela é a alínea c) do fecho do portefólio. Cada exercício treina uma coisa, e cada um usa o que os anteriores treinaram.

Os exercícios 5 a 7 são das funções e não dependem dos quatro primeiros. No exercício 5 lês uma função e as suas chamadas, no 6 escreves uma função a partir do contrato e no 7 trocas uma parte repetida por uma função. Se o professor o indicar, podes fazê-los antes dos outros, logo depois de leres a parte das funções do guia.

Nenhum exercício é o exemplo do inventário, ou o exemplo do stock da parte das funções, com outros números. Os exemplos mostram o caminho, e os exercícios pedem-te que o percorras noutros problemas.

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Escolher casos de teste antes de ver o algoritmo, e testá-lo com eles | 10 min |
| 2 | Depurar com os quatro primeiros passos do método: observar, formular uma hipótese, verificar com o trace e corrigir a causa | 13 min |
| 3 | Contar passos e melhorar um algoritmo sem mudar o que ele faz | 12 min |
| 4 | Construir um algoritmo pequeno a partir da tabela de casos escrita antes dele | 25 min |
| 5 | Ler uma função e prever o que as suas chamadas escrevem | 10 min |
| 6 | Escrever uma função a partir do seu contrato e chamá-la | 14 min |
| 7 | Trocar uma parte repetida por uma função, sem mudar o que o algoritmo escreve | 15 min |
| Total da parte obrigatória | Exercícios 1 a 7 | 99 min |
| Fecho do portefólio | Contrato e teste do algoritmo do exercício 4, na última aula do bloco; o fluxograma, só quando o professor o indicar | 13 min, ou 25 com o fluxograma |
| Desafio opcional | Mudar uma restrição de cada vez no algoritmo do exercício 4 | na última aula, para quem não precisar de recuperação |
| Para ires mais longe | Opcional: mais uma fronteira no exercício 1, o caso mínimo e a correção do sintoma no exercício 2, a poupança de cada escalão no exercício 3, a validação no exercício 4, o teste de regressão do exercício 2 e dois erros em funções | fora dos 99 min |

## Exercício 1: Escolher os casos antes de ver o algoritmo (10 min)

A matéria está nas secções "Casos normais, de fronteira e inválidos" e "A tabela de casos esperados" do guia.

A loja de informática marca cada artigo do armazém conforme a quantidade que tem em stock. Com menos de 5 unidades, o artigo fica marcado "Encomendar". Com 5 unidades ou mais, fica marcado "Stock suficiente". Uma quantidade negativa é um erro de contagem, e o algoritmo escreve "Quantidade inválida".

**a)** Sem olhares para o algoritmo que está mais abaixo, escreve a tabela de casos esperados deste problema, com as cinco colunas da tabela do guia: número, tipo, quantidade, resultado esperado e razão da escolha. Tem de ter pelo menos quatro casos: um caso normal, os dois lados da fronteira das 5 unidades e um caso inválido. Tapa o algoritmo com uma folha até acabares esta alínea: o exercício só funciona se a tabela for escrita a partir do enunciado.

**b)** Agora lê o algoritmo e executa-o com cada um dos teus casos. Não precisas do trace linha a linha: basta seguir a cadeia de condições e anotar a primeira que dá verdadeiro, ou o `Senão`, se nenhuma der. Acrescenta à tabela as colunas do resultado obtido e de se o teste passou.

```text
const LIMITE_ENCOMENDA = 5
Escreve: "Quantidade em stock?"
int quantidade = ler valor
Se quantidade < 0
    Escreve: "Quantidade inválida"
Senão se quantidade <= LIMITE_ENCOMENDA
    Escreve: "Encomendar"
Senão
    Escreve: "Stock suficiente"
```

**c)** Que caso da tua tabela revelou o erro? Se a tabela só tivesse casos normais, como 2 e 12, o erro teria aparecido? Explica porquê numa ou duas frases.

Concluíste quando a tua tabela, escrita antes de leres o algoritmo, tiver um caso que falha, e conseguires explicar por que razão só esse caso o podia apanhar.

## Exercício 2: Depurar com método (13 min)

A matéria está nas secções "Depurar com método" e "Quatro erros que vais encontrar muitas vezes" do guia. O registo de depuração está no passo 11 do exemplo.

No armazém da loja, o funcionário regista as entregas do dia. Escreve primeiro quantas entregas houve e depois, para cada entrega, o número de caixas que ela trouxe. O algoritmo deve mostrar o total de caixas recebidas no dia e quantas entregas foram grandes, isto é, de 10 ou mais caixas.

```text
const ENTREGA_GRANDE = 10
Escreve: "Quantas entregas houve hoje?"
int numeroEntregas = ler valor
int grandes = 0
Para entrega de 1 até numeroEntregas
    int totalCaixas = 0
    Escreve: "Caixas da entrega ", entrega, "?"
    int caixas = ler valor
    totalCaixas = totalCaixas + caixas
    Se caixas >= ENTREGA_GRANDE
        grandes = grandes + 1
Escreve: "Total de caixas: ", totalCaixas
Escreve: "Entregas grandes: ", grandes
```

O erro foi observado assim: na segunda-feira houve 2 entregas, a primeira de 12 caixas e a segunda de 4. O algoritmo escreveu "Total de caixas: 4" e "Entregas grandes: 1". O responsável do armazém contou 16 caixas.

As quatro alíneas são os quatro primeiros passos do método, pela ordem do guia, e a resposta a cada uma dá uma linha do registo de depuração do passo 11 do exemplo. Na linha da alínea c), basta escreveres o que a tabela de iterações mostrou. O quinto passo, voltar a testar tudo, está no Mais longe 5, que é opcional; se o fizeres, junta ao registo a linha do novo teste. É esse registo que guardas no portefólio.

**a)** Observar o erro. Para cada uma das duas saídas, escreve o resultado esperado e o obtido, e diz qual está errada.

**b)** Formular uma hipótese. Escreve, numa frase que possa ser verdadeira ou falsa, o que achas que causa o erro.

**c)** Verificar com o trace. Faz a tabela de iterações do caso de segunda-feira, com colunas para `entrega`, `caixas`, `totalCaixas` e `grandes` e para a condição escondida do `Para`, `entrega <= numeroEntregas`. Na coluna do que acontece durante a iteração, escreve cada atribuição a `totalCaixas` com o valor que ela dá. Diz se a tabela confirma a tua hipótese e qual é a instrução que causa o erro.

**d)** Corrigir a causa. Corrige o algoritmo com uma única alteração, e diz qual foi. Podes escrever o algoritmo corrigido ou descrever a alteração numa frase, desde que se perceba exatamente que linha muda e para onde.

Concluíste quando o teu registo de depuração permitir a outra pessoa perceber o erro e a correção sem ler o resto das tuas respostas.

## Exercício 3: Contar passos e melhorar sem mudar o resultado (12 min)

A matéria está nas secções "Contar passos" e "Estratégias simples para fazer menos passos" do guia, e nos passos 9 e 10 do exemplo.

A loja separa as encomendas por peso, para escolher a caixa de envio. Até 999 gramas, a encomenda é leve. De 1000 a 4999 gramas, é média. De 5000 gramas para cima, é pesada. O funcionário escreve o peso de cada encomenda, em gramas, e escreve 0 quando acabar. Os pesos escritos são sempre positivos, e por isso não há validação.

```text
const LIMITE_LEVE = 1000
const LIMITE_PESADO = 5000
const SENTINELA = 0
int leves = 0
int medias = 0
int pesadas = 0
Escreve: "Peso da encomenda em gramas (0 para terminar)?"
int peso = ler valor
Enquanto peso != SENTINELA
    Se peso < LIMITE_LEVE
        leves = leves + 1
    Se peso >= LIMITE_LEVE e peso < LIMITE_PESADO
        medias = medias + 1
    Se peso >= LIMITE_PESADO
        pesadas = pesadas + 1
    Escreve: "Peso da encomenda em gramas (0 para terminar)?"
    peso = ler valor
Escreve: "Leves: ", leves
Escreve: "Médias: ", medias
Escreve: "Pesadas: ", pesadas
```

Repara que os três `Se` estão à mesma distância da margem e nenhum tem `Senão`: são três perguntas separadas, uma a seguir à outra, e não uma cadeia.

Este algoritmo já passou em todos os testes da loja: está certo. Agora, e só agora, pergunta-se se faz trabalho desnecessário.

A regra de contagem do guia, para a teres à mão: conta um passo cada `Escreve:` e cada atribuição executados, incluindo as leituras com `ler valor`, e cada avaliação da condição de um `Se`, de um `Senão se` ou de um `Enquanto`, incluindo a última avaliação do `Enquanto`, a que dá falso. As linhas `const` e o `Senão` não contam.

**a)** Conta os passos do algoritmo para os pesos 500 e 7000, seguidos de 0. Conta por partes, numa tabela como a do passo 10 do exemplo, com uma linha para cada parte: antes do ciclo, cada iteração, a última avaliação da condição do ciclo e depois do ciclo. No fim, soma.

**b)** Em cada iteração, o algoritmo avalia sempre as três condições, mas para um mesmo peso só uma delas pode ser verdadeira. Escreve uma versão melhorada em que as três perguntas formam uma só cadeia, com `Senão se` e `Senão`, para o algoritmo não voltar a perguntar o que já sabe. Basta escreveres a cadeia que substitui os três `Se`, que é a única parte que muda, em pseudocódigo ou em frases claras.

**c)** Conta os passos da tua versão para o mesmo caso da alínea a), com a mesma regra e a mesma tabela de partes, e calcula a diferença.

**d)** Explica, numa ou duas frases, por que razão a tua versão escreve sempre o mesmo que a original, para qualquer peso positivo.

Concluíste quando tiveres as duas contagens, feitas com a mesma regra, e a explicação.

## Exercício 4: Construir um algoritmo pequeno a partir dos casos de teste (25 min)

A matéria está nas secções "A tabela de casos esperados" e "A síntese: sequência, seleção e repetição" do guia, e nos padrões totalizador e sentinela do guia 04. Junto com o teste que lhe fazes no fecho do portefólio, é o exercício que mais se parece com a primeira parte da avaliação prática.

O cartão de cliente da papelaria dá pontos. Por cada compra, o cliente ganha 1 ponto por cada 100 cêntimos completos que gastou: uma compra de 250 cêntimos dá 2 pontos, e uma de 99 cêntimos não dá nenhum. Uma compra de 2000 cêntimos ou mais ganha ainda 10 pontos de bónus. No fim do dia, a funcionária escreve o valor de cada compra feita com cartão, em cêntimos, uma a uma, e escreve 0 quando acabar. Os valores escritos são sempre positivos, e por isso neste exercício não há validação. No fim, o algoritmo mostra o total de pontos atribuídos no dia.

**a)** Antes de escreveres o algoritmo, escreve a tabela de casos esperados, com as cinco colunas do guia. Tem de ter pelo menos três casos: um caso normal, os dois lados da fronteira do bónus e um dia sem compras. Cada caso é uma sequência de valores, terminada no 0 que marca o fim do dia.

**b)** Escreve o algoritmo, em pseudocódigo ou em frases claras que não deixem dúvidas. Se usares pseudocódigo, usa uma constante para cada valor fixo do enunciado (os 100 cêntimos, os 2000 cêntimos e os 10 pontos de bónus) e a constante `SENTINELA`.

Concluíste quando tiveres a tabela de casos, escrita antes do algoritmo, e o algoritmo. Testar o algoritmo com essa tabela é a alínea c) do fecho do portefólio.

## Exercício 5: Ler uma função e as suas chamadas (10 min)

A matéria está nas secções "Chamar uma função", "Parâmetros e argumentos", "O que acontece numa chamada" e "O trace de uma chamada" da parte das funções do guia.

A loja online da papelaria escreve, para cada encomenda, o valor e os portes. As encomendas de 3000 cêntimos ou mais não pagam portes; as outras pagam 400 cêntimos.

```text
const LIMITE_GRATIS = 3000
const PORTES = 400

Função mostraPortes(numero, valorEncomenda)
    Escreve: "Encomenda ", numero, ": ", valorEncomenda, " cêntimos"
    Se valorEncomenda >= LIMITE_GRATIS
        Escreve: "Portes grátis"
    Senão
        Escreve: "Portes: ", PORTES, " cêntimos"

int valorPrimeira = 3500
mostraPortes(1, valorPrimeira)
mostraPortes(2, 2999)
mostraPortes(3, 3000)
```

**a)** Sem fazeres o trace completo, escreve o ecrã que este algoritmo produz, linha a linha, pela ordem em que as linhas aparecem.

**b)** Faz a tabela da chamada `mostraPortes(2, 2999)`, como a tabela da chamada 2 do guia: uma linha para os argumentos que passam para os parâmetros e uma linha por cada instrução executada, com colunas para `numero`, `valorEncomenda`, a condição e o seu resultado, e o ecrã.

Concluíste quando o teu ecrã tiver as linhas das três chamadas pela ordem certa, e a tabela da chamada 2 mostrar que caminho a função seguiu.

## Exercício 6: Escrever uma função a partir do contrato (14 min)

A matéria está nas secções "Escrever uma função", "Parâmetros e argumentos" e "Testar uma função sozinha" da parte das funções do guia. O intervalo com `e` está no guia 03.

A escola organiza uma visita de estudo para várias turmas. O autocarro tem 50 lugares, e a visita de uma turma só se confirma se houver pelo menos 15 alunos inscritos. Para cada turma, escreve-se uma linha com o número de inscritos e outra com a decisão. Este é o contrato da função que faz esse trabalho:

- recebe: o nome da turma, um texto como `"10A"`, e o número de alunos inscritos, um inteiro igual ou maior do que zero, por esta ordem;
- escreve: uma linha como "Turma 10C: 23 inscritos" e, numa segunda linha, "Visita confirmada" se a turma tiver pelo menos 15 inscritos e não mais do que os 50 lugares do autocarro, ou "Visita por confirmar" nos outros casos;
- exemplo: `mostraVisita("10C", 23)` escreve "Turma 10C: 23 inscritos" e "Visita confirmada".

**a)** Escreve a função `mostraVisita(turma, inscritos)`. Usa uma constante para o mínimo de inscritos e outra para os lugares do autocarro, escritas antes da função.

**b)** Escreve o algoritmo principal, que chama a função para três turmas: a 10A, com 14 inscritos, a 10B, com 50, e a 10D, com 15.

**c)** Escreve o ecrã que o teu algoritmo produz, com as linhas das três chamadas.

Concluíste quando a tua função cumprir o contrato nas três chamadas, incluindo as duas turmas que estão em cima dos limites.

## Exercício 7: Trocar a repetição por uma função (15 min)

A matéria está nas secções "Uma parte que se repete" e "Trocar uma repetição por uma função" da parte das funções do guia, e na secção "Melhorar um algoritmo sem mudar o que ele faz" da teoria.

No fim do dia, o bar da escola vê o que ficou por vender de três produtos e pede mais quando fica abaixo do mínimo de cada um. O algoritmo de que o bar se serve está certo, mas tem a mesma parte escrita três vezes:

```text
const MINIMO_SANDES = 5
const MINIMO_SUMOS = 12
const MINIMO_FRUTA = 8
Escreve: "Sandes por vender?"
int sandes = ler valor
Escreve: "Sumos por vender?"
int sumos = ler valor
Escreve: "Peças de fruta por vender?"
int fruta = ler valor
Escreve: "Restam ", sandes, " sandes"
Se sandes < MINIMO_SANDES
    Escreve: "Pedir mais sandes"
Escreve: "Restam ", sumos, " sumos"
Se sumos < MINIMO_SUMOS
    Escreve: "Pedir mais sumos"
Escreve: "Restam ", fruta, " peças de fruta"
Se fruta < MINIMO_FRUTA
    Escreve: "Pedir mais peças de fruta"
```

**a)** Compara os três blocos do fim, linha a linha, e escreve numa frase tudo o que muda de um bloco para o outro.

**b)** Escreve uma função que faz o trabalho de um bloco, e as três chamadas que substituem os três blocos. As constantes e as seis primeiras linhas do algoritmo principal ficam como estão.

**c)** Mostra que a tua versão escreve o mesmo que a original. Num dia em que ficaram 5 sandes, 11 sumos e 7 peças de fruta, escreve as linhas que a versão original escreve depois das três perguntas, e as que a tua versão escreve, e confirma que são iguais.

Concluíste quando a tua versão tiver uma função e três chamadas, e escrever, no dia da alínea c), exatamente as mesmas linhas que a original.

## Fecho do portefólio (última aula, 13 min, ou 25 com o fluxograma)

As alíneas a) e c) não são opcionais, mas não contam para os 99 minutos da ficha: fazem-se na última aula do bloco, a mesma do checkpoint, porque juntam ao exercício 4 as duas peças que lhe faltam para ser o problema completo do teu portefólio, o contrato e os testes. Se acabares a ficha antes do fim da aula, podes fazer logo a alínea c). A alínea b) é de fluxogramas, e só a fazes quando o professor o indicar. A secção "O teu portefólio" do guia diz como organizar a pasta.

**a)** Escreve o contrato do problema do exercício 4, com as respostas às quatro perguntas do guia 01: entradas, saídas, restrições e condições. Se encontrares alguma ambiguidade no enunciado, escreve a decisão que tomaste.

**b)** Só quando o professor o indicar: desenha no diagrams.net o fluxograma do teu algoritmo do exercício 4, como no laboratório do bloco 04. Guarda o ficheiro `.drawio` e exporta uma imagem PNG. Confirma, figura a figura, que o fluxograma diz exatamente o mesmo que o algoritmo que escreveste.

**c)** Testa o algoritmo do exercício 4: faz a tabela de iterações do teu caso normal e executa os outros casos da tua tabela. Acrescenta à tabela as colunas do resultado obtido e de se o teste passou. Se algum caso falhar, corrige o algoritmo com o método do guia, guarda a versão com erro e a versão corrigida, e volta a executar a tabela inteira.

Concluíste quando o portefólio tiver, para o problema do exercício 4, o enunciado com o contrato, o algoritmo e a tabela de casos executada, com todos os casos a passar, e, ao lado, o registo de depuração do exercício 2. Se o professor tiver indicado a alínea b), o fluxograma também.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só passa à seguinte se a anterior não tiver chegado.

**Exercício 1.** Desenha a reta dos valores inteiros, de -2 a 8, e marca por cima de cada troço a resposta que o enunciado dá. A fronteira das 5 unidades é o sítio onde a resposta muda de "Encomendar" para "Stock suficiente": testa o último valor de um lado e o primeiro do outro. Para saber de que lado fica o 5, relê o enunciado: "5 unidades ou mais". Na alínea c), pergunta-te se o 2 e o 12 estão perto do sítio onde o algoritmo e o enunciado discordam.

**Exercício 2.** Compara o total obtido, 4, com as caixas de cada entrega. A que entrega corresponde o 4? Isso diz-te o que o totalizador está a fazer. Para a hipótese, relê no guia a secção "Inicialização no sítio errado". Na tabela de iterações, olha para o que acontece a `totalCaixas` logo no início de cada iteração, e não só no momento do teste.

**Exercício 3.** Na alínea a), repara que cada iteração da versão dada avalia sempre os três `Se`, qualquer que seja o peso, e executa exatamente uma atualização: por isso todas as iterações têm o mesmo número de passos. Na alínea b), lembra-te da regra da cadeia de `Senão se`: quando o algoritmo chega à segunda condição, o que é que já sabe sobre o peso? Numa cadeia, o `Senão se` e o `Senão` ficam à mesma distância da margem que o primeiro `Se`, e cada atualização fica indentada por baixo da sua pergunta. Na alínea c), o `Senão` não avalia nenhuma condição, e por isso uma encomenda leve e uma pesada já não fazem o mesmo número de passos.

**Exercício 4.** Decompõe antes de escrever: ler valores até ao 0 e, para cada compra, somar os pontos da compra e decidir o bónus. A estrutura é a do exemplo do inventário: inicialização do total, leitura antecipada, ciclo com sentinela e leitura no fim do corpo. Os pontos de uma compra calculam-se com uma operação do guia 02 que dá o número de vezes que 100 cabe no valor. Na tabela, calcula os pontos de uma compra de 1999 cêntimos e de uma de 2000: a diferença não é só de 1 ponto.

**Exercício 5.** Faz as chamadas uma de cada vez e, antes de cada uma, escreve que valor recebe cada parâmetro. Na chamada 1, o argumento é uma variável: o que passa para a função é o valor dela. Na chamada 3, o valor é exatamente o do limite: lê o sinal da condição com atenção. Na alínea b), o `Senão` não avalia nenhuma condição, e por isso não tem linha própria na tabela: é a mesma razão por que não conta como passo, na secção "Contar passos" do guia.

**Exercício 6.** O cabeçalho já está no enunciado. A primeira linha do corpo é um `Escreve:` com várias partes, como o de `mostraStock` no guia. Para a segunda, relê no guia 03 como se escreve um intervalo com `e`, e decide, a partir das palavras do contrato, se 15 e 50 ficam dentro ou fora do intervalo. Na alínea c), duas das três turmas estão em cima de um limite.

**Exercício 7.** Na alínea a), sublinha em cada bloco tudo o que não é igual nos três. Cada coisa sublinhada vai ser um parâmetro, como na secção "Trocar uma repetição por uma função" do guia. Na alínea b), repara que o texto `" sandes"` tem um espaço antes da palavra: na função, o espaço fica escrito num texto, e a palavra vem de um parâmetro.

## Desafio opcional: mudar uma restrição de cada vez

Faz-se na última aula, por quem não precisar de recuperação. Volta ao exercício 4, já com o contrato e os testes do fecho do portefólio, e com todos os testes a passar. Vais fazer três mudanças ao enunciado, uma de cada vez, e cada uma a partir da versão original, não da anterior.

1. O bónus passa a exigir compras de 2500 cêntimos ou mais.
2. Os pontos passam a ser 1 por cada 50 cêntimos completos, em vez de 100.
3. As compras acima de 50000 cêntimos passam a ter de ser registadas à mão: o algoritmo escreve "Valor acima do limite" e não lhes dá pontos.

Para cada mudança, e antes de mexer no algoritmo:

**a)** Diz que linhas da tua tabela de casos mudam de resultado esperado, e escreve os novos resultados.

**b)** Diz que casos novos são precisos, e porquê.

Só depois:

**c)** Altera o algoritmo e diz quantas linhas mudaram.

**d)** Só se fizeste o fluxograma do fecho do portefólio: diz que figuras do fluxograma mudam, e se é preciso acrescentar alguma.

**e)** Executa a tabela inteira na versão alterada.

No fim, compara as três mudanças: qual delas obrigou a acrescentar um ramo novo, e qual mudou mais resultados esperados sem mudar nenhuma estrutura? Escreve a tua conclusão em duas ou três frases.

## Para ires mais longe

Esta secção é opcional e fica fora dos 99 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e quer mais prática, ou para estudar em casa antes da avaliação. Cada exercício continua um dos exercícios obrigatórios com um passo a mais. Os tempos são indicativos.

### Mais longe 1: Corrigir e acrescentar uma fronteira (10 min)

Continua o exercício 1.

**a)** Corrige o algoritmo do exercício 1 com uma única alteração e volta a executar a tua tabela inteira.

**b)** A loja acrescenta uma terceira marca: com 20 unidades ou mais, o artigo fica marcado "Excesso de stock". Sem escreveres o algoritmo, diz que casos novos a tua tabela precisa, com o resultado esperado de cada um.

Pista: na alínea b), apareceu uma fronteira nova. Quais são os dois valores que ficam um de cada lado dela?

### Mais longe 2: O caso mínimo e a correção do sintoma (10 min)

Continua o exercício 2. A matéria está nas secções "Depurar com método" e "Corrigir a causa e não o sintoma" do guia.

**a)** Executa a versão original do algoritmo das entregas, a do enunciado do exercício 2, com uma só entrega, de 12 caixas. O erro aparece? Explica porquê, e diz qual é o caso mais pequeno que ainda mostra o erro no total.

**b)** Um colega propôs outra correção: deixar o ciclo como está e trocar o penúltimo `Escreve:` por `Escreve: "Total de caixas: ", totalCaixas * numeroEntregas`. Encontra um caso em que a proposta dele dá o total certo e outro em que dá o total errado. Explica, com as palavras causa e sintoma, por que razão esta proposta não corrige o erro.

Pista: na alínea b), experimenta um dia em que todas as entregas têm o mesmo número de caixas, e depois um em que não têm.

### Mais longe 3: Quanto se poupa em cada escalão (15 min)

Continua o exercício 3.

**a)** Conta os passos de uma iteração com uma encomenda média, por exemplo de 1000 gramas, na versão original e na tua.

**b)** Diz quantos passos a tua versão poupa por cada encomenda leve, por cada média e por cada pesada, e explica porque é que não poupa o mesmo nas três.

**c)** Mostra a equivalência também pelos testes: escreve uma tabela de casos com os dois lados de cada fronteira (999 e 1000, 4999 e 5000) e um dia sem encomendas, e executa-a nas duas versões.

Pista: na alínea b), conta quantas condições a tua cadeia avalia até chegar à atualização de cada escalão.

### Mais longe 4: Validar os valores do cartão (15 min)

Continua o exercício 4. A funcionária pode enganar-se a escrever: um valor negativo é um engano, e o algoritmo escreve "Valor inválido" e ignora-o, sem lhe dar pontos.

**a)** Antes de mexeres no algoritmo, acrescenta à tua tabela um caso com um valor negativo no meio de valores válidos, com o resultado esperado.

**b)** Altera o algoritmo do exercício 4 para fazer esta validação, em pseudocódigo ou em frases claras.

**c)** Executa a tabela inteira na versão nova.

Pista: a validação vem antes de tudo o resto dentro do ciclo. Os pontos e o bónus só se calculam para compras válidas, e por isso podem ficar indentados por baixo do `Senão` da validação, com o `Se` do bónus lá dentro e a sua atualização um nível mais à direita.

### Mais longe 5: Voltar a testar tudo nas entregas (4 min)

Continua o exercício 2, com a tua versão corrigida. É o quinto passo do método, "Voltar a testar tudo", da secção "Depurar com método" do guia.

O responsável do armazém já tinha escrito estes casos de teste, com o resultado esperado de cada um:

| Caso | Entregas do dia | Resultado esperado |
| ---: | --- | --- |
| 1 | 2 entregas, de 12 e de 4 caixas | Total 16, grandes 1 |
| 2 | 0 entregas | Total 0, grandes 0 |
| 3 | 1 entrega, de 10 caixas | Total 10, grandes 1 |

**a)** Executa a tua versão corrigida com os três casos e diz se cada um passa. Lembra-te de que um `Para` de 1 até 0 não tem nenhuma iteração: é o caso zero do `Para`.

**b)** Escreve a última linha do teu registo de depuração, a do novo teste.

Pista: no caso 2, o corpo do `Para` não chega a ser executado. Os dois `Escreve:` do fim mostram então os valores que as variáveis tinham antes do ciclo.

### Mais longe 6: Dois erros em funções (10 min)

Continua os exercícios 5 e 6. Cada um destes algoritmos tem um erro, e nenhum dos dois é um dos erros frequentes da parte das funções do guia. Para cada um:

- diz o que acontece quando o algoritmo é executado, com as entradas indicadas;
- diz qual é a linha com o erro e porquê;
- corrige-o com uma única alteração.

**a)** A funcionária escreve 6 quando o algoritmo pergunta pelas borrachas.

```text
const STOCK_MINIMO = 10

Função mostraStock(artigo, quantidade)
    Escreve: "Stock de ", artigo, ": ", quantidade
    Se quantidade < STOCK_MINIMO
        Escreve: "Encomendar ", artigo

Escreve: "Borrachas em stock?"
mostraStock("borrachas", borrachas)
int borrachas = ler valor
```

**b)** Este algoritmo não lê nada.

```text
const MINIMO_ALUNOS = 15
const LUGARES_AUTOCARRO = 50

Função mostraVisita(turma, inscritos)
    Escreve: "Turma ", turma, ": ", inscritos, " inscritos"
    Se inscrito >= MINIMO_ALUNOS e inscrito <= LUGARES_AUTOCARRO
        Escreve: "Visita confirmada"
    Senão
        Escreve: "Visita por confirmar"

mostraVisita("10C", 23)
```

Pista: faz o trace, linha a linha, e para na primeira linha que usa uma variável que, nesse momento, ainda não tem valor ou não existe. Na alínea b), compara letra a letra os nomes do cabeçalho com os do corpo.

## Critérios de conclusão

- [ ] Escrevi a tabela de casos do exercício 1 antes de ler o algoritmo.
- [ ] As minhas tabelas têm casos normais e os dois lados de cada fronteira pedida, casos inválidos quando o enunciado os prevê e, quando há um ciclo, o caso zero.
- [ ] O meu registo de depuração do exercício 2 tem uma linha por cada passo do método que fiz: as quatro das alíneas e, se fiz o Mais longe 5, a do novo teste.
- [ ] Contei os passos das duas versões do exercício 3 com a mesma regra e expliquei por que razão escrevem o mesmo.
- [ ] No exercício 4, escrevi a tabela de casos antes do algoritmo e, no fecho do portefólio, executei-a toda.
- [ ] No fecho do portefólio, escrevi o contrato do exercício 4 e, se o professor indicou o fluxograma, ele diz exatamente o mesmo que o algoritmo que escrevi, figura a figura.
- [ ] Guardei no portefólio as versões com erro e as versões corrigidas, cada uma no seu ficheiro.
- [ ] Nos exercícios 5 a 7, as minhas chamadas têm os argumentos pela ordem dos parâmetros, e a minha função do exercício 6 cumpre o contrato nas turmas que estão em cima dos limites.
- [ ] No exercício 7, mostrei com as linhas do ecrã que a minha versão com a função escreve o mesmo que a original.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
