![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Testar, depurar e melhorar

Ficha do tema Testar, depurar e melhorar, da unidade de algoritmos. Praticas a escolher casos de teste, a depurar com método e a melhorar um algoritmo, contando os passos. Constróis também um algoritmo a partir dos casos escritos antes dele, e escreves e usas funções. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](05-testar-depurar-e-melhorar.md), com as secções de testar, depurar e melhorar e o exemplo guiado. Lê também os passos 8 e 9 do exemplo, que mostram como se melhora um algoritmo e como se contam os passos. Para os exercícios 5 a 7, precisas da parte das funções do guia.

Precisas ainda de saber fazer uma tabela de iterações e escrever uma cadeia de `Se` e `Senão se`. E de saber ler um `Para` e um ciclo com sentinela, e usar contadores e totalizadores. Está tudo nos guias [02](02-pseudocodigo.md), [03](03-decisoes-e-validacao.md) e [04](04-repeticao-e-padroes.md). O exercício 6 usa um intervalo com `e`, do guia 03.

Cada exercício diz em que secção do guia 05 está a matéria. Se encravares, volta a essa secção antes de olhares para o apoio.

## Como trabalhar

A parte obrigatória são os exercícios 1 a 7. Os exercícios 5 a 7 são das funções. O 5 e o 6 fazem-se na aula das funções, e o 7 também, se houver tempo. Se não houver, fica para casa. Os exercícios 1 a 4 são prática para casa, ou para quando acabares um projeto mais cedo. O tempo de aula deste tema vai para os dois projetos guiados. O exercício 8, o fecho do portefólio, o desafio e a secção "Para ires mais longe" são opcionais.

Resolve os exercícios 1 a 4 pela ordem. Nos dois primeiros aplicas o que o guia mostrou. No exercício 1 escolhes casos de teste e usas-os para testar um algoritmo curto. No exercício 2 segues os quatro primeiros passos do método de depuração, um passo por alínea. O quinto passo, voltar a testar tudo, está no Mais longe 5, que é opcional. No exercício 3 já és tu a decidir. Contas os passos de um algoritmo que já está certo e escreves uma versão que faz menos trabalho. No exercício 4 constróis um algoritmo pequeno do princípio ao fim, a partir da tabela de casos que escreves antes dele. Testá-lo com essa tabela é a alínea b) do exercício 8. Cada exercício treina uma coisa, e cada um usa o que os anteriores treinaram.

Os exercícios 5 a 7 são das funções e não dependem dos quatro primeiros. No exercício 5 lês uma função e as suas chamadas. No 6 escreves uma função a partir do contrato, e no 7 trocas uma parte repetida por uma função. Se o professor o indicar, podes fazê-los antes dos outros, logo depois de leres a parte das funções do guia.

Nenhum exercício é o exemplo do inventário, ou o exemplo do stock da parte das funções, com outros números. Os exemplos mostram o caminho, e os exercícios pedem-te que o percorras noutros problemas.

| Exercício | O que treina | Parte |
| --- | --- | --- |
| 1 | Escolher casos de teste antes de ver o algoritmo, e testá-lo com eles | Obrigatória |
| 2 | Depurar com os quatro primeiros passos do método: observar, formular uma hipótese, verificar com o trace e corrigir a causa | Obrigatória |
| 3 | Contar passos e melhorar um algoritmo sem mudar o que ele faz | Obrigatória |
| 4 | Construir um algoritmo pequeno a partir da tabela de casos escrita antes dele | Obrigatória |
| 5 | Ler uma função e prever o que as suas chamadas escrevem | Obrigatória |
| 6 | Escrever uma função a partir do seu contrato e chamá-la | Obrigatória |
| 7 | Trocar uma parte repetida por uma função, sem mudar o que o algoritmo escreve | Obrigatória |
| 8 | O fecho do portefólio: o contrato e o teste do algoritmo do exercício 4 | Opcional |
| Desafio | Mudar uma restrição de cada vez no algoritmo do exercício 4 | Opcional, depois do exercício 8 |
| Para ires mais longe | Mais uma fronteira no exercício 1, o caso mínimo e a correção do sintoma no exercício 2, a poupança de cada escalão no exercício 3, a validação no exercício 4, o teste de regressão do exercício 2 e dois erros em funções | Opcional |

Os algoritmos que a ficha te dá estão na forma de pseudocódigo das aulas. A indentação mostra o que está dentro de cada `Se`, de cada `Enquanto` e de cada `Para`. Quando fores tu a escrever um algoritmo, ou uma parte dele, podes usar essa forma ou frases claras. Basta que não deixem dúvidas sobre quanto, quando e o que acontece se não der. O que conta é a lógica.

Precisas de papel e lápis.

O portefólio deste tema são os dois projetos guiados. Os exercícios desta ficha também podem lá ficar:

- a tabela de casos do exercício 1;
- o registo de depuração do exercício 2;
- a contagem de passos do exercício 3;
- o exercício 4, completado no exercício 8 com o contrato e a tabela de casos executada.

A secção "O teu portefólio" do guia diz como organizar a pasta.

## Exercício 1: Escolher os casos antes de ver o algoritmo

A matéria está nas secções "Casos normais, de fronteira e inválidos" e "A tabela de casos esperados" do guia.

A loja de informática marca cada artigo do armazém conforme a quantidade que tem em stock. Com menos de 5 unidades, o artigo fica marcado "Encomendar". Com 5 unidades ou mais, fica marcado "Stock suficiente". Uma quantidade negativa é um erro de contagem, e o algoritmo escreve "Quantidade inválida".

**a)** Sem olhares para o algoritmo que está mais abaixo, escreve a tabela de casos esperados deste problema. Usa as cinco colunas da tabela do guia: número, tipo, quantidade, resultado esperado e razão da escolha. Tem de ter pelo menos quatro casos: um caso normal, os dois lados da fronteira das 5 unidades e um caso inválido. Os dois lados são o último valor que dá "Encomendar" e o primeiro que dá "Stock suficiente". Tapa o algoritmo com uma folha até acabares esta alínea. O exercício só funciona se a tabela for escrita a partir do enunciado.

**b)** Agora lê o algoritmo e executa-o com cada um dos teus casos. Não precisas do trace linha a linha. Basta seguir a cadeia de condições e anotar a primeira que dá verdadeiro, ou o `Senão`, se nenhuma der. Acrescenta à tabela as colunas do resultado obtido e de se o teste passou.

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

## Exercício 2: Depurar com método

A matéria está na secção "Depurar com método" do guia e no padrão totalizador do guia 04. O registo de depuração está no passo 10 do exemplo guiado.

No armazém da loja, o funcionário regista as entregas do dia. Escreve primeiro quantas entregas houve e depois, para cada entrega, o número de caixas que ela trouxe. O algoritmo deve mostrar o total de caixas recebidas no dia e quantas entregas foram grandes, isto é, de 10 ou mais caixas.

```text
const ENTREGA_GRANDE = 10
Escreve: "Quantas entregas houve hoje?"
int numeroEntregas = ler valor
int totalCaixas = 0
int grandes = 0
Para entrega de 1 até numeroEntregas
    Escreve: "Caixas da entrega ", entrega, "?"
    int caixas = ler valor
    totalCaixas = caixas
    Se caixas >= ENTREGA_GRANDE
        grandes = grandes + 1
Escreve: "Total de caixas: ", totalCaixas
Escreve: "Entregas grandes: ", grandes
```

O erro foi observado assim: na segunda-feira houve 2 entregas, a primeira de 12 caixas e a segunda de 4. O algoritmo escreveu "Total de caixas: 4" e "Entregas grandes: 1". O responsável do armazém contou 16 caixas.

As quatro alíneas são os quatro primeiros passos do método, pela ordem do guia. A resposta a cada uma dá uma linha do registo de depuração, como o do passo 10 do exemplo guiado. Na linha da alínea c), basta escreveres o que a tabela de iterações mostrou. O quinto passo, voltar a testar tudo, está no Mais longe 5, que é opcional. Se o fizeres, junta ao registo a linha do novo teste. É esse registo que guardas no portefólio.

**a)** Observar o erro. Para cada uma das duas saídas, escreve o resultado esperado e o obtido, e diz qual está errada.

**b)** Formular uma hipótese. Escreve, numa frase que possa ser verdadeira ou falsa, o que achas que causa o erro.

**c)** Verificar com o trace. Faz a tabela de iterações do caso de segunda-feira, com colunas para `entrega`, `caixas`, `totalCaixas` e `grandes` e para a condição escondida do `Para`, `entrega <= numeroEntregas`. Na coluna do que acontece durante a iteração, escreve cada atribuição a `totalCaixas` com o valor que ela dá. Diz se a tabela confirma a tua hipótese. Se não a confirmar, escreve outra, com o que a tabela mostrou. No fim, diz qual é a instrução que causa o erro.

**d)** Corrigir a causa. Corrige o algoritmo com uma única alteração, e diz qual foi. Podes escrever o algoritmo corrigido ou descrever a alteração numa frase, desde que se perceba exatamente que linha muda e para onde.

## Exercício 3: Contar passos e melhorar sem mudar o resultado

A matéria está nas secções "Contar passos" e "Estratégias simples para fazer menos passos" do guia, e nos passos 8 e 9 do exemplo guiado.

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

Repara que os três `Se` estão à mesma distância da margem e nenhum tem `Senão`. São três perguntas separadas, uma a seguir à outra, e não uma cadeia.

Este algoritmo já passou em todos os testes da loja, e está certo. Agora, e só agora, pergunta-se se faz trabalho desnecessário.

Tens aqui a regra de contagem do guia, para a teres à mão:

- conta um passo cada `Escreve:` e cada atribuição executados, incluindo as leituras com `ler valor`;
- conta um passo cada avaliação da condição de um `Se`, de um `Senão se` ou de um `Enquanto`. Conta também a última avaliação do `Enquanto`, a que dá falso;
- as linhas `const` e o `Senão` não contam.

**a)** Conta os passos do algoritmo para os pesos 500 e 7000, seguidos de 0. Conta por partes, numa tabela como a do passo 9 do exemplo guiado. A tabela tem uma linha para cada parte: antes do ciclo, cada iteração, a última avaliação da condição do ciclo e depois do ciclo. No fim, soma.

**b)** Em cada iteração, o algoritmo avalia sempre as três condições, mas para um mesmo peso só uma delas pode ser verdadeira. Escreve uma versão melhorada em que as três perguntas formam uma só cadeia, com `Senão se` e `Senão`. Assim, o algoritmo não volta a perguntar o que já sabe. Basta escreveres a cadeia que substitui os três `Se`, que é a única parte que muda, em pseudocódigo ou em frases claras.

**c)** Conta os passos da tua versão para o mesmo caso da alínea a), com a mesma regra e a mesma tabela de partes. Calcula a diferença.

**d)** Explica, numa ou duas frases, por que razão a tua versão escreve sempre o mesmo que a original, para qualquer peso positivo.

## Exercício 4: Construir um algoritmo pequeno a partir dos casos de teste

A matéria está nas secções "A tabela de casos esperados" e "A síntese: sequência, seleção e repetição" do guia. Está também nos padrões totalizador e sentinela do guia 04. Junto com o teste que lhe fazes no exercício 8, é o exercício que mais se parece com a primeira parte da avaliação prática.

O cartão de cliente da papelaria dá pontos. Por cada compra, o cliente ganha 1 ponto por cada 100 cêntimos completos que gastou. Uma compra de 250 cêntimos dá 2 pontos, e uma de 99 cêntimos não dá nenhum. Uma compra de 2000 cêntimos ou mais ganha ainda 10 pontos de bónus. No fim do dia, a funcionária escreve o valor de cada compra feita com cartão, em cêntimos, uma a uma, e escreve 0 quando acabar. Os valores escritos são sempre positivos, e por isso neste exercício não há validação. No fim, o algoritmo mostra o total de pontos atribuídos no dia.

**a)** Antes de escreveres o algoritmo, escreve a tabela de casos esperados, com as cinco colunas do guia. Tem de ter pelo menos três casos: um caso normal, um caso com os dois lados da fronteira do bónus e um dia sem compras. Os dois lados do bónus podem estar no mesmo dia ou em dias separados. Cada caso é uma sequência de valores, terminada no 0 que marca o fim do dia.

**b)** Escreve o algoritmo, em pseudocódigo ou em frases claras que não deixem dúvidas. Se usares pseudocódigo, usa a constante `SENTINELA` e uma constante para cada valor fixo do enunciado. Os valores fixos são os 100 cêntimos, os 2000 cêntimos e os 10 pontos de bónus.

Testar o algoritmo com a tabela que escreveste é a alínea b) do exercício 8, que é opcional.

## Exercício 5: Ler uma função e as suas chamadas

A matéria está na parte das funções do guia. Está nas secções "Chamar uma função", "Parâmetros e argumentos", "O que acontece numa chamada" e "O trace de uma chamada".

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

**b)** Faz a tabela da chamada `mostraPortes(2, 2999)`, como a tabela da chamada 2 do guia. Tem uma linha para os argumentos que passam para os parâmetros e uma linha por cada instrução executada. As colunas são `numero`, `valorEncomenda`, a condição e o seu resultado, e o ecrã.

## Exercício 6: Escrever uma função a partir do contrato

A matéria está na parte das funções do guia, nas secções "Escrever uma função", "Parâmetros e argumentos" e "Testar uma função sozinha". O intervalo com `e` está no guia 03.

A escola organiza uma visita de estudo para várias turmas. O autocarro tem 50 lugares, e a visita de uma turma só se confirma se houver pelo menos 15 alunos inscritos. Para cada turma, escreve-se uma linha com o número de inscritos e outra com a decisão. Este é o contrato da função que faz esse trabalho:

- recebe: o nome da turma, um texto como `"10A"`, e o número de inscritos, um inteiro igual ou maior do que zero, por esta ordem;
- escreve: uma linha como "Turma 10C: 23 inscritos" e, numa segunda linha, a decisão. A decisão é "Visita confirmada" se a turma tiver pelo menos 15 inscritos e não mais do que os 50 lugares do autocarro. Nos outros casos, é "Visita por confirmar";
- exemplo: `mostraVisita("10C", 23)` escreve "Turma 10C: 23 inscritos" e "Visita confirmada".

**a)** Escreve a função `mostraVisita(turma, inscritos)`. Usa uma constante para o mínimo de inscritos e outra para os lugares do autocarro, escritas antes da função.

**b)** Escreve o algoritmo principal, que chama a função para três turmas. As turmas são a 10A, com 14 inscritos, a 10B, com 50, e a 10D, com 15.

**c)** Escreve o ecrã que o teu algoritmo produz, com as linhas das três chamadas.

## Exercício 7: Trocar a repetição por uma função

A matéria está na parte das funções do guia, nas secções "Uma parte que se repete" e "Trocar uma repetição por uma função". Está também na secção "Melhorar um algoritmo sem mudar o que ele faz".

No fim do dia, o bar da escola vê o que ficou por vender de três produtos. Pede mais quando um deles fica abaixo do seu mínimo. O algoritmo de que o bar se serve está certo, mas tem a mesma parte escrita três vezes:

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

**c)** Mostra que a tua versão escreve o mesmo que a original. Imagina um dia em que ficaram 5 sandes, 11 sumos e 7 peças de fruta. Escreve as linhas que a versão original escreve depois das três perguntas, e as que a tua versão escreve, e confirma que são iguais.

## Exercício 8: Fecho do portefólio, opcional

Os problemas completos do teu portefólio são os dois projetos deste tema. Este fecho é opcional. Junta ao exercício 4 as duas peças que lhe faltam para ser mais um problema completo: o contrato e os testes. É um bom treino antes da avaliação. Podes fazê-lo em casa ou quando acabares um projeto mais cedo. A secção "O teu portefólio" do guia diz como organizar a pasta.

**a)** No exercício 4, o enunciado fez de contrato. Escreve agora o contrato do problema, com as respostas às quatro perguntas do guia 01: entradas, saídas, restrições e condições. Escrevê-lo mostra se ficou alguma ambiguidade por decidir. Se ficar, escreve a decisão que tomaste e acerta a tabela antes de testar.

**b)** Testa o algoritmo do exercício 4. Faz a tabela de iterações do teu caso normal e executa os outros casos da tua tabela. Acrescenta à tabela as colunas do resultado obtido e de se o teste passou. Se algum caso falhar, corrige o algoritmo com o método do guia. Guarda a versão com erro e a versão corrigida, e volta a executar a tabela inteira.

## Apoio

Usa estas pistas pela ordem em que aparecem, e só passa à seguinte se a anterior não tiver chegado.

- Exercício 1: desenha a reta dos valores inteiros, de -2 a 8, e marca por cima de cada troço a resposta que o enunciado dá. A fronteira das 5 unidades é o sítio onde a resposta muda de "Encomendar" para "Stock suficiente". Testa o último valor de um lado e o primeiro do outro. Para saber de que lado fica o 5, relê o enunciado: "5 unidades ou mais". Na alínea c), pergunta-te se o 2 e o 12 estão perto do sítio onde o algoritmo e o enunciado discordam.
- Exercício 2: compara o total obtido, 4, com as caixas de cada entrega. A que entrega corresponde o 4? Isso diz-te o que o totalizador está a fazer. Antes de escreveres a hipótese, lê todas as linhas que mexem em `totalCaixas`, e não só a primeira. Na tabela de iterações, escreve em cada atribuição o valor que `totalCaixas` tinha antes e o que fica depois. Não te fiques pelo valor no momento do teste.
- Exercício 3: na alínea a), repara que cada iteração da versão dada avalia sempre os três `Se`, qualquer que seja o peso. E executa exatamente uma atualização. Por isso, todas as iterações têm o mesmo número de passos. Na alínea b), lembra-te da regra da cadeia de `Senão se`. Quando o algoritmo chega à segunda condição, o que é que já sabe sobre o peso? Numa cadeia, o `Senão se` e o `Senão` ficam à mesma distância da margem que o primeiro `Se`. Cada atualização fica indentada por baixo da sua pergunta. Na alínea c), conta à parte uma iteração com a encomenda leve e uma com a encomenda pesada. Lembra-te de que o `Senão` não conta como passo.
- Exercício 4: decompõe antes de escrever. É preciso ler valores até ao 0 e, para cada compra, somar os pontos da compra e decidir o bónus. A estrutura é a do exemplo do inventário: inicialização do total, leitura antecipada, ciclo com sentinela e leitura no fim do corpo. Os pontos de uma compra calculam-se com uma operação do guia 02 que dá o número de vezes que 100 cabe no valor. Na tabela, calcula os pontos de cada compra em duas partes: os pontos normais e o bónus, se o houver.
- Exercício 5: faz as chamadas uma de cada vez e, antes de cada uma, escreve que valor recebe cada parâmetro. Na chamada 1, o argumento é uma variável, e o que passa para a função é o valor dela. Na chamada 3, o valor é exatamente o do limite, por isso lê o sinal da condição com atenção. Na alínea b), o `Senão` não avalia nenhuma condição, e por isso não tem linha própria na tabela. É a mesma razão por que não conta como passo, na secção "Contar passos" do guia.
- Exercício 6: o cabeçalho já está no enunciado. A primeira linha do corpo é um `Escreve:` com várias partes, como o de `mostraStock` no guia. Para a segunda, relê no guia 03 como se escreve um intervalo com `e`. Depois decide, a partir das palavras do contrato, se 15 e 50 ficam dentro ou fora do intervalo. Na alínea c), duas das três turmas estão em cima de um limite.
- Exercício 7: na alínea a), sublinha em cada bloco tudo o que não é igual nos três. Cada coisa sublinhada vai ser um parâmetro, como na secção "Trocar uma repetição por uma função" do guia. Na alínea b), repara que o texto `" sandes"` tem um espaço antes da palavra. Na função, o espaço fica escrito num texto, e a palavra vem de um parâmetro.

## Desafio opcional

O desafio é mudar uma restrição de cada vez. Volta ao exercício 4, já com o contrato e os testes do exercício 8, e com todos os testes a passar. Vais fazer três mudanças ao enunciado, uma de cada vez, e cada uma a partir da versão original, não da anterior.

1. O bónus passa a exigir compras de 2500 cêntimos ou mais.
2. Os pontos passam a ser 1 por cada 50 cêntimos completos, em vez de 100.
3. As compras acima de 50000 cêntimos passam a ter de ser registadas à mão. O algoritmo escreve "Valor acima do limite" e não lhes dá pontos.

Para cada mudança, e antes de mexer no algoritmo:

**a)** Diz que linhas da tua tabela de casos mudam de resultado esperado, e escreve os novos resultados.

**b)** Diz que casos novos são precisos, e porquê.

Só depois:

**c)** Altera o algoritmo e diz quantas linhas mudaram.

**d)** Executa a tabela inteira na versão alterada.

No fim, compara as três mudanças: qual delas obrigou a acrescentar um ramo novo, e qual mudou mais resultados esperados sem mudar nenhuma estrutura? Escreve a tua conclusão em duas ou três frases.

## Para ires mais longe

Esta secção é opcional. Não precisas de fazer nada daqui para concluíres a ficha. Serve para quem terminou a parte obrigatória e quer mais prática, ou para estudar em casa antes da avaliação. Cada exercício continua um dos exercícios obrigatórios com um passo a mais.

### Mais longe 1: Corrigir e acrescentar uma fronteira

Continua o exercício 1.

**a)** Corrige o algoritmo do exercício 1 com uma única alteração e volta a executar a tua tabela inteira.

**b)** A loja acrescenta uma terceira marca: com 20 unidades ou mais, o artigo fica marcado "Excesso de stock". Sem escreveres o algoritmo, diz que casos novos a tua tabela precisa, com o resultado esperado de cada um.

Pista: na alínea b), apareceu uma fronteira nova. Quais são os dois valores que ficam um de cada lado dela?

### Mais longe 2: O caso mínimo e a correção do sintoma

Continua o exercício 2. A matéria está nas secções "Depurar com método" e "Corrigir a causa e não o sintoma" do guia.

**a)** Executa a versão original do algoritmo das entregas, a do enunciado do exercício 2, com uma só entrega, de 12 caixas. O erro aparece? Explica porquê, e diz qual é o caso mais pequeno que ainda mostra o erro no total.

**b)** Um colega propôs outra correção: deixar o ciclo como está e trocar o penúltimo `Escreve:` por `Escreve: "Total de caixas: ", totalCaixas * numeroEntregas`. Encontra um caso em que a proposta dele dá o total certo e outro em que dá o total errado. Explica, com as palavras causa e sintoma, por que razão esta proposta não corrige o erro.

Pista: na alínea b), experimenta um dia em que todas as entregas têm o mesmo número de caixas, e depois um em que não têm.

### Mais longe 3: Quanto se poupa em cada escalão

Continua o exercício 3.

**a)** Conta os passos de uma iteração com uma encomenda média, por exemplo de 1000 gramas, na versão original e na tua.

**b)** Diz quantos passos a tua versão poupa por cada encomenda leve, por cada média e por cada pesada. Explica porque é que não poupa o mesmo nas três.

**c)** Mostra a equivalência também pelos testes. Escreve uma tabela de casos com os dois lados de cada fronteira (999 e 1000, 4999 e 5000) e um dia sem encomendas. Executa-a nas duas versões.

Pista: na alínea b), conta quantas condições a tua cadeia avalia até chegar à atualização de cada escalão.

### Mais longe 4: Validar os valores do cartão

Continua o exercício 4. A funcionária pode enganar-se a escrever. Um valor negativo é um engano, e o algoritmo escreve "Valor inválido" e ignora-o, sem lhe dar pontos.

**a)** Antes de mexeres no algoritmo, acrescenta à tua tabela um caso com um valor negativo no meio de valores válidos, com o resultado esperado.

**b)** Altera o algoritmo do exercício 4 para fazer esta validação, em pseudocódigo ou em frases claras.

**c)** Executa a tabela inteira na versão nova.

Pista: a validação vem antes de tudo o resto dentro do ciclo. Os pontos e o bónus só se calculam para compras válidas. Por isso, podem ficar indentados por baixo do `Senão` da validação. O `Se` do bónus fica lá dentro, e a sua atualização um nível mais à direita.

### Mais longe 5: Voltar a testar tudo nas entregas

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

### Mais longe 6: Dois erros em funções

Continua o exercício 5. Cada um destes algoritmos tem um erro, e nenhum dos dois é um dos erros com funções que o guia mostra. Para cada um:

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

**b)** É o algoritmo do exercício 5, com um erro de escrita. Não lê nada.

```text
const LIMITE_GRATIS = 3000
const PORTES = 400

Função mostraPortes(numero, valorEncomenda)
    Escreve: "Encomenda ", numero, ": ", valorEncomenda, " cêntimos"
    Se valorEncomena >= LIMITE_GRATIS
        Escreve: "Portes grátis"
    Senão
        Escreve: "Portes: ", PORTES, " cêntimos"

int valorPrimeira = 3500
mostraPortes(1, valorPrimeira)
mostraPortes(2, 2999)
mostraPortes(3, 3000)
```

Pista: faz o trace, linha a linha, até à primeira linha que usa uma variável que, nesse momento, ainda não tem valor ou não existe. Na alínea b), compara letra a letra os nomes do cabeçalho com os do corpo.

## Critérios de conclusão

- [ ] Exercício 1: escrevi a tabela de casos antes de ler o algoritmo, e ela tem um caso que falha. Sei explicar por que razão só esse caso podia apanhar o erro.
- [ ] As minhas tabelas têm casos normais e os dois lados de cada fronteira pedida. Têm casos inválidos quando o enunciado os prevê e, quando há um ciclo, o caso zero.
- [ ] Exercício 2: o meu registo de depuração tem uma linha por cada passo do método que fiz. São as quatro das alíneas e, se fiz o Mais longe 5, a do novo teste. Outra pessoa percebe por ele o erro e a correção, sem ler o resto das minhas respostas.
- [ ] Exercício 3: contei os passos das duas versões com a mesma regra, e expliquei por que razão escrevem o mesmo.
- [ ] Exercício 4: escrevi a tabela de casos antes do algoritmo, e escrevi o algoritmo.
- [ ] Exercício 5: o meu ecrã tem as linhas das três chamadas pela ordem certa. A tabela da chamada 2 mostra que caminho a função seguiu.
- [ ] Exercício 6: a minha função cumpre o contrato nas três chamadas, incluindo as duas turmas que estão em cima dos limites.
- [ ] Exercício 7: a minha versão tem uma função e três chamadas, e escreve, no dia da alínea c), exatamente as mesmas linhas que a original.
- [ ] Nos exercícios 5 a 7, as minhas chamadas têm os argumentos pela ordem dos parâmetros.
- [ ] Se fiz o exercício 8, o portefólio tem o enunciado do exercício 4 com o contrato, o algoritmo e a tabela de casos executada. Todos os casos passam. Tem também, ao lado, o registo de depuração do exercício 2.
- [ ] Se guardei exercícios no portefólio, guardei as versões com erro e as versões corrigidas, cada uma no seu ficheiro.

## Autoavaliação

1. O que já consegues fazer sozinho?
2. Que dificuldade tiveste, e o que fizeste para a resolver?
3. Qual dos exercícios te obrigou a pensar mais antes de escrever, e porquê?

![Rodapé](../imagens/rodape.png)
