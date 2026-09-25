![Cabeçalho](../imagens/cabecalho.png)

# Repetição e padrões

UC: UC00245

Blocos: ALG04

Requisitos: UC00245-R03, UC00245-R04, UC00245-R05, UC00245-K05, UC00245-K06, UC00245-A05, UC00245-A06, UC00245-A07, UC00245-C01, UC00245-C02, UC00245-P02

| Identificação | Valor |
| --- | --- |
| Material | M-ALG04, quarto bloco de Desenvolver algoritmos |
| Fundamento curricular | Unidade de competência UC00245, bloco ALG04 |
| Duração | 120 minutos dos 300 do bloco neste guia (teoria, exemplo explicado e consolidação); a prática guiada, 60 minutos, está no [laboratório](04-repeticao-e-padroes-laboratorio.md); a prática autónoma e o desafio, 120 minutos, estão na [ficha de exercícios](04-repeticao-e-padroes-exercicios.md) |
| Evidência a guardar | Tabela de iterações, algoritmo e conjunto de testes do exemplo e da ficha; fluxograma do exemplo desenhado no laboratório |

## Objetivos

No final deste bloco, serás capaz de:

- escrever um ciclo `ENQUANTO` com as suas três peças, a inicialização, a condição e a atualização, e explicar para que serve cada uma;
- seguir a execução de um ciclo numa tabela, primeiro instrução a instrução e depois iteração a iteração, e dizer quantas vezes o ciclo se repete e com que valores termina;
- reconhecer num trace um ciclo que nunca começa e um ciclo que nunca acaba, e dizer qual das três peças o provoca;
- escrever um ciclo contado com `PARA` e reescrevê-lo com `ENQUANTO`;
- usar quatro padrões que vão aparecer em quase todos os algoritmos que escreveres daqui para a frente: o contador, o totalizador, a sentinela e a validação repetida;
- escolher entre `ENQUANTO` e `PARA` e justificar a escolha;
- desenhar um ciclo em fluxograma, com a seta que volta atrás até ao losango da condição.

## O que precisas de saber antes

Este guia foi escrito antes de a matéria ser dada, e parte do princípio de que já trabalhaste os três guias anteriores desta área. Não vais aprender aqui nada dessa matéria outra vez: vais usá-la. Por isso, antes de começares, confirma que consegues fazer o que está nesta lista.

Do [guia 01, Do problema ao algoritmo](01-do-problema-ao-algoritmo.md), vais usar o contrato de um problema, as respostas às quatro perguntas (entradas, saídas, restrições e condições), com exemplos concretos e o resultado esperado de cada um. Vais usar também a ideia de estado: o conjunto de valores que descrevem uma situação num determinado momento, como uma fotografia. Neste guia, essa fotografia vai ser tirada muitas vezes seguidas.

Do [guia 02, Pseudocódigo e fluxogramas](02-pseudocodigo-e-fluxogramas.md), vais usar quase tudo: variáveis e constantes, os tipos `inteiro`, `real`, `texto` e `lógico`, a atribuição com seta, `LER` e `ESCREVER`, a forma de um algoritmo com `ALGORITMO`, `CONSTANTES`, `VARIÁVEIS`, `INÍCIO` e `FIM`, os símbolos do fluxograma e a tabela de trace, com uma coluna por variável. Há uma linha desse guia que tem de te parecer perfeitamente natural, porque vais escrevê-la dezenas de vezes neste:

```text
total ← total + 5
```

Lê-se "total recebe o valor que total tem agora, mais 5". Primeiro calcula-se o lado direito, com o valor atual, e depois guarda-se o resultado na mesma variável. Se esta linha ainda te fizer confusão, volta ao guia 02 antes de continuares.

Do [guia 03, Decisões e validação](03-decisoes-e-validacao.md), vais usar as condições, que só podem dar `VERDADEIRO` ou `FALSO`, as comparações (`=`, `!=`, `<`, `<=`, `>`, `>=`), os operadores `E`, `OU` e `NÃO`, a regra de pôr parênteses sempre que se mistura `E` com `OU`, a seleção com `SE`, `SENÃO SE` e `SENÃO`, o losango do fluxograma com as saídas `Sim` e `Não`, os intervalos (por exemplo, `quantidade >= 1 E quantidade <= 50`), o contrário de um intervalo, escrito com `OU`, e a validação de uma entrada antes de a usar. Vais usar também as fronteiras e a tabela de casos esperados, com casos abaixo, no e acima de cada limite, escrita antes do algoritmo.

Dos laboratórios dos blocos [02](02-pseudocodigo-e-fluxogramas-laboratorio.md) e [03](03-decisoes-e-validacao-laboratorio.md), vais precisar de saber usar o diagrams.net: guardar no computador, desenhar as figuras, ligá-las com setas, escrever `Sim` e `Não` nas saídas de um losango e exportar uma imagem.

## Material e preparação

Papel quadriculado e lápis, porque as tabelas deste guia se fazem primeiro à mão. Para o laboratório, o computador com o diagrams.net aberto em `https://app.diagrams.net/?lang=pt`, e a pasta `algoritmos` onde guardaste os fluxogramas dos blocos anteriores.

## Como está organizado o tempo

Este bloco tem **5 horas**, ou seja 300 minutos, distribuídos por três documentos com o mesmo número: este guia, que se lê e estuda; o laboratório, que se segue passo a passo no computador; e a ficha, que se resolve sem ajuda.

| Parte | Onde está | Tempo |
| --- | --- | ---: |
| Teoria | Neste guia | 30 min |
| Exemplo explicado | Neste guia | 30 min |
| Prática guiada | No [laboratório](04-repeticao-e-padroes-laboratorio.md) | 60 min |
| Prática autónoma | Na [ficha](04-repeticao-e-padroes-exercicios.md) | 90 min |
| Desafio | Na [ficha](04-repeticao-e-padroes-exercicios.md) | 30 min |
| Consolidação | Neste guia | 60 min |

A teoria é longa para ler em 30 minutos, e é de propósito. Em aula, o professor vai explicá-la por partes, com traces no quadro. Depois, este guia fica contigo para voltares a ler com calma, e cada secção explica o mesmo assunto por mais do que um caminho.

## Teoria (30 min)

### A mesma instrução cem vezes

Lembras-te da papelaria que atende os clientes por senha, dos guias anteriores? Distribuía no máximo 40 senhas por dia. Imagina que o movimento cresceu, e que agora a máquina imprime todas as manhãs, antes de a loja abrir, as senhas do dia, numeradas de 1 a 100. Com o que aprendeste até agora, o algoritmo que imprime as senhas seria assim:

```text
ESCREVER "Senha ", 1
ESCREVER "Senha ", 2
ESCREVER "Senha ", 3
(e assim por diante, uma linha por senha, até)
ESCREVER "Senha ", 100
```

Cem linhas quase iguais. Tem três problemas, e o terceiro é o mais grave.

O primeiro é o tamanho. Cem linhas escrevem-se, mas ninguém as consegue ler com atenção, e um engano na linha 57 passa despercebido.

O segundo é a mudança. Se amanhã a loja precisar de 150 senhas, alguém tem de acrescentar cinquenta linhas. Se precisar de 20, alguém tem de apagar oitenta. O algoritmo não se adapta: tem de ser reescrito.

O terceiro é o que torna esta forma impossível em muitos problemas. Imagina que, em vez de imprimir senhas, o algoritmo tem de ler as quantidades dos pedidos que chegam a uma papelaria ao longo do dia. Quantos `LER` escreves? Não sabes. Há dias com 3 pedidos e dias com 40. Nenhum número fixo de linhas serve para todos os dias.

Olha outra vez para as cem linhas das senhas. São todas iguais, exceto num pormenor: o número, que aumenta 1 de uma linha para a seguinte. Reparar nesta regularidade é o que permite resolver o problema. Se conseguirmos dizer ao algoritmo "escreve uma senha, aumenta o número, e volta a fazer o mesmo até chegares à última", as cem linhas passam a ser quatro. E, se o número de senhas estiver numa constante, passar de 100 para 150 senhas é mudar um único valor.

É isso que este guia ensina: a escrever instruções que se repetem, e a controlar quantas vezes se repetem.

### Um ciclo volta atrás e pergunta outra vez

Fazes repetições destas todos os dias, sem lhes dares esse nome. "Enquanto houver pratos na banca, lava um prato." "Enquanto houver clientes na fila, atende o próximo." "Enquanto a massa não estiver lisa, amassa mais um minuto."

Todas estas frases têm a mesma forma, com três partes. Há uma pergunta cuja resposta é sim ou não: há pratos na banca? Há uma ação que se faz quando a resposta é sim: lavar um prato. E há uma consequência escondida, que é a mais importante de todas: a ação muda a resposta à pergunta. Cada prato lavado sai da banca. Mais cedo ou mais tarde, a banca fica vazia, a resposta passa a ser não, e paras.

Pensa no que aconteceria se lavar um prato não o tirasse da banca. A pergunta teria sempre a mesma resposta, e ficarias a lavar o mesmo prato para sempre. Parece uma brincadeira, mas é exatamente o erro mais frequente de quem começa a escrever repetições, e vais vê-lo com números mais à frente.

Num algoritmo, a uma parte que se executa várias vezes seguidas chama-se **ciclo**, e a cada uma dessas execuções chama-se **iteração**. Na conversa de todos os dias diz-se também uma volta do ciclo, e vais ouvir as duas palavras: se o algoritmo lava três pratos, o ciclo teve três iterações, ou deu três voltas.

Até agora, cada instrução dos teus algoritmos executava-se no máximo uma vez. Numa sequência, cada instrução executa-se exatamente uma vez. Numa seleção, uma instrução dentro de um `SE` executa-se uma vez ou nenhuma. Com os ciclos, pela primeira vez, a mesma instrução pode executar-se muitas vezes, e é por isso que o trace vai ser ainda mais importante do que era.

### ENQUANTO: repetir enquanto a condição for verdadeira

No pseudocódigo desta disciplina, a repetição escreve-se assim:

```text
ENQUANTO condição FAZER
    instruções que se repetem
FIM ENQUANTO
```

A `condição` é uma condição como as do guia 03: uma pergunta cuja resposta só pode ser `VERDADEIRO` ou `FALSO`. Às instruções entre `ENQUANTO` e `FIM ENQUANTO` chama-se **corpo do ciclo**, e escrevem-se com mais quatro espaços de indentação, como as de dentro de um `SE`.

O `ENQUANTO` funciona com quatro regras, e as quatro são importantes:

1. Quando o algoritmo chega à linha do `ENQUANTO`, avalia a condição, com os valores que as variáveis têm nesse momento.
2. Se a condição for verdadeira, executa o corpo do ciclo, de cima para baixo, até chegar ao `FIM ENQUANTO`.
3. Ao chegar ao `FIM ENQUANTO`, o algoritmo não continua para baixo. Volta à linha do `ENQUANTO` e avalia outra vez a condição, agora com os valores que as variáveis têm depois de o corpo ter sido executado. E recomeça na regra 2.
4. Se a condição for falsa, o corpo é saltado, e o algoritmo continua na instrução que está a seguir ao `FIM ENQUANTO`.

Compara com o `SE` do guia 03. O `SE` avalia a condição uma vez e segue em frente. O `ENQUANTO` avalia a condição, executa o corpo e, no fim, volta atrás para perguntar outra vez. Uma boa forma de o pensar: um `ENQUANTO` é um `SE` que, no fim do bloco, volta a subir para fazer a mesma pergunta.

Há duas consequências destas regras que convém fixar desde já.

A primeira: **a condição do `ENQUANTO` diz quando continuar, e não quando parar**. "Enquanto houver pratos na banca" descreve a situação em que se continua a lavar. O ciclo para quando essa condição deixa de ser verdadeira. Quando escreveres um ciclo, pergunta-te "em que situação quero continuar?", e escreve essa situação. Quem escreve a situação em que quer parar obtém um ciclo que faz exatamente o contrário do que queria.

A segunda: a condição só é avaliada na linha do `ENQUANTO`. Se, a meio do corpo, as variáveis mudarem de forma a tornar a condição falsa, o corpo não é interrompido. Continua até ao `FIM ENQUANTO`, e só no teste seguinte o ciclo termina.

Este é o algoritmo das senhas, escrito com um ciclo. Para o trace ficar curto, a constante vale 3. Para imprimir as cem senhas, bastaria mudá-la para 100.

```text
ALGORITMO DistribuirSenhas
CONSTANTES
    ULTIMA_SENHA ← 3
VARIÁVEIS
    senha: inteiro
INÍCIO
    senha ← 1
    ENQUANTO senha <= ULTIMA_SENHA FAZER
        ESCREVER "Senha ", senha
        senha ← senha + 1
    FIM ENQUANTO
    ESCREVER "Fim da distribuição"
FIM
```

Lê-o por palavras: a senha começa em 1; enquanto a senha for menor ou igual à última, escreve-se a senha e passa-se à seguinte; quando se ultrapassar a última, escreve-se que a distribuição acabou.

### As três peças de um ciclo

Todos os ciclos que terminam têm três peças. Se faltar uma delas, ou se uma estiver errada, o ciclo não faz o que devia, e é quase sempre assim que os ciclos falham. Por isso vale a pena dar nome a cada uma.

A **inicialização** é a instrução, ou as instruções, que dão o valor inicial às variáveis que a condição e o corpo vão usar. Fica antes do `ENQUANTO`. No algoritmo das senhas é `senha ← 1`. Sem ela, a primeira vez que a condição fosse avaliada estaria a comparar uma variável sem valor, e o algoritmo não teria forma de saber se deve entrar no ciclo.

A **condição** é a pergunta que decide se se faz mais uma iteração. Fica na linha do `ENQUANTO`. No algoritmo das senhas é `senha <= ULTIMA_SENHA`. Diz em que situação se continua.

A **atualização** é a instrução, dentro do corpo, que muda a variável de que a condição depende, e que aproxima o ciclo do fim. No algoritmo das senhas é `senha ← senha + 1`. Cada iteração aumenta a senha em 1, e por isso, mais cedo ou mais tarde, a senha ultrapassa a última e a condição passa a ser falsa. É a atualização que tira o prato da banca.

O resto do corpo é o trabalho que o ciclo faz em cada iteração. Nas senhas é o `ESCREVER`.

Para cada ciclo que escreveres, vais responder a três perguntas, uma por peça. São as perguntas que vais ter de saber justificar no fim deste bloco:

1. Com que valor começa, e porquê esse? (a inicialização)
2. Em que situação continua, e quando é que deixa de continuar? (a condição)
3. O que muda em cada iteração, e essa mudança aproxima o fim? (a atualização)

No algoritmo das senhas: começa em 1 porque a primeira senha é a 1; continua enquanto a senha for menor ou igual a 3, e deixa de continuar quando a senha chegar a 4; em cada iteração a senha aumenta 1, e por isso aproxima-se de 4.

### O trace linha a linha do primeiro ciclo

O trace de um ciclo faz-se com as mesmas regras que aprendeste no guia 02: uma coluna por variável, uma linha por instrução executada, e em cada linha copias os valores da linha de cima e mudas só o que essa instrução muda. Há duas novidades.

A primeira é uma coluna para a condição. Na linha em que o algoritmo passa pelo `ENQUANTO`, escreves a condição com os valores substituídos e o resultado: "`1 <= 3` é VERDADEIRO". Quando a condição tem um `E` ou um `OU`, escreves primeiro o resultado de cada comparação e depois o do conjunto, como no guia 03. As constantes não têm coluna, porque nunca mudam, mas o seu valor aparece nas condições.

A segunda é que a mesma instrução pode aparecer várias vezes na tabela, uma por cada vez que é executada. A tabela segue a ordem em que as instruções são executadas, e não a ordem em que estão escritas. Depois da última instrução do corpo, a linha seguinte da tabela é outra vez a do `ENQUANTO`, porque é para lá que o `FIM ENQUANTO` manda o algoritmo.

Este é o trace completo do algoritmo das senhas:

| Passo | Instrução executada | senha | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | nada |
| 1 | `senha ← 1` | 1 | nenhuma | nada |
| 2 | `ENQUANTO senha <= ULTIMA_SENHA FAZER` | 1 | `1 <= 3` é VERDADEIRO | nada |
| 3 | `ESCREVER "Senha ", senha` | 1 | nenhuma | Senha 1 |
| 4 | `senha ← senha + 1` | 2 | nenhuma | nada |
| 5 | `ENQUANTO senha <= ULTIMA_SENHA FAZER` | 2 | `2 <= 3` é VERDADEIRO | nada |
| 6 | `ESCREVER "Senha ", senha` | 2 | nenhuma | Senha 2 |
| 7 | `senha ← senha + 1` | 3 | nenhuma | nada |
| 8 | `ENQUANTO senha <= ULTIMA_SENHA FAZER` | 3 | `3 <= 3` é VERDADEIRO | nada |
| 9 | `ESCREVER "Senha ", senha` | 3 | nenhuma | Senha 3 |
| 10 | `senha ← senha + 1` | 4 | nenhuma | nada |
| 11 | `ENQUANTO senha <= ULTIMA_SENHA FAZER` | 4 | `4 <= 3` é FALSO | nada |
| 12 | `ESCREVER "Fim da distribuição"` | 4 | nenhuma | Fim da distribuição |

Lê a tabela devagar, linha a linha, e compara cada linha com a de cima.

No passo 1, a inicialização dá a `senha` o valor 1. No passo 2, o algoritmo chega ao `ENQUANTO` pela primeira vez, e a condição `1 <= 3` é verdadeira, por isso entra no corpo. No passo 3 escreve "Senha 1", e no passo 4 a atualização faz a senha passar de 1 para 2.

No passo 5 acontece o que é novo. O algoritmo chegou ao `FIM ENQUANTO` e voltou atrás, à linha do `ENQUANTO`. Avalia a condição outra vez, agora com `senha` a valer 2. `2 <= 3` continua a ser verdadeiro, e o corpo executa-se mais uma vez, nos passos 6 e 7. O mesmo acontece nos passos 8 a 10, com a senha a valer 3.

No passo 11, a senha já vale 4. `4 <= 3` é falso. Pela regra 4, o corpo é saltado e o algoritmo continua a seguir ao `FIM ENQUANTO`, no passo 12, onde escreve que a distribuição acabou.

Conta agora as linhas do `ENQUANTO`: são quatro, nos passos 2, 5, 8 e 11. Três deram verdadeiro e uma deu falso. O corpo executou-se três vezes, portanto o ciclo teve três iterações. Isto é sempre assim num ciclo que termina: **há sempre mais um teste da condição do que iterações**, porque o último teste é o que dá falso e faz o ciclo parar.

Repara também no valor final de `senha`: é 4, e não 3. O ciclo não para quando escreve a última senha. Para quando a senha ultrapassa a última, porque é só nessa altura que a condição fica falsa. É uma surpresa para muita gente e é uma pergunta frequente em testes: depois do ciclo, quanto vale a variável?

Se a constante valesse 100, o algoritmo teria 100 iterações e 101 testes da condição, e esta tabela teria 303 passos. O algoritmo, esse, continuaria a ter as mesmas linhas.

### A tabela de iterações

Uma tabela com 303 passos não é prática. Depois de perceberes como um ciclo se executa instrução a instrução, podes usar uma tabela mais curta, a que se chama **tabela de iterações**. Tem uma linha por cada teste da condição, e não por cada instrução.

Cada linha da tabela de iterações mostra:

- o número do teste (1.º, 2.º, 3.º...);
- o valor de cada variável no momento em que o algoritmo chega ao `ENQUANTO` e vai testar a condição, como se tirasses uma fotografia do estado nesse instante;
- a condição, com os valores substituídos, e o resultado;
- o que acontece durante a iteração que começa a seguir: o que é escrito no ecrã e o que é lido. Na linha em que a condição é falsa, escreve-se que o ciclo termina.

Para o algoritmo das senhas:

| Teste | senha | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` é VERDADEIRO | escreve "Senha 1" |
| 2.º | 2 | `2 <= 3` é VERDADEIRO | escreve "Senha 2" |
| 3.º | 3 | `3 <= 3` é VERDADEIRO | escreve "Senha 3" |
| 4.º | 4 | `4 <= 3` é FALSO | o ciclo termina |

Cada linha desta tabela resume um grupo de linhas da tabela anterior. O 1.º teste corresponde aos passos 2 a 4, o 2.º aos passos 5 a 7, o 3.º aos passos 8 a 10, e o 4.º ao passo 11. A tabela de iterações não mostra os passos um a um, mas mostra tudo o que interessa para perceber o ciclo: com que valores começa cada iteração, quantas iterações há, e com que valores o ciclo termina. Os valores finais estão sempre na última linha, a do teste que dá falso.

A tabela de iterações é a evidência pedida neste bloco. Sempre que te pedirem o trace de um ciclo, é esta tabela que se espera, a não ser que te peçam explicitamente o trace linha a linha. Um conselho: nos primeiros ciclos que fizeres, faz primeiro o trace linha a linha e só depois a tabela de iterações, para veres que as duas dizem o mesmo.

### A seta que volta ao losango

No fluxograma, um ciclo desenha-se com o losango que já conheces do guia 03, e com uma seta nova: uma seta que volta atrás, para cima, até ao losango da condição.

```mermaid
flowchart TD
    A([Início]) --> B["senha ← 1"]
    B --> C{"senha <= ULTIMA_SENHA?"}
    C -->|Sim| D[/ESCREVER senha/]
    D --> E["senha ← senha + 1"]
    E --> C
    C -->|Não| F[/ESCREVER fim da distribuição/]
    F --> Z([Fim])
```

Segue o percurso com o dedo. Do início passas pela inicialização, `senha ← 1`, e chegas ao losango. Se a condição for verdadeira, sais pelo `Sim`, escreves a senha, fazes a atualização, e a seta leva-te de volta ao losango, para perguntares outra vez. Se a condição for falsa, sais pelo `Não`, escreves a mensagem final e terminas. Para fazer a distribuição de três senhas, o dedo passa quatro vezes pelo losango, tantas quantas as linhas da tabela de iterações.

Compara figura a figura com o pseudocódigo. O losango é a linha do `ENQUANTO`. O caminho do `Sim` é o corpo do ciclo. A seta que volta ao losango é o `FIM ENQUANTO`, que manda voltar ao teste. O caminho do `Não` é o que vem depois do `FIM ENQUANTO`. Nos fluxogramas destes guias, o texto entre aspas de um `ESCREVER` é abreviado para caber na figura; no pseudocódigo está completo.

Há três coisas a reter sobre esta seta.

A primeira: a seta de volta vai sempre ao losango da condição. Se voltasse ao retângulo da inicialização, `senha ← 1`, a senha voltaria a valer 1 em cada iteração e o ciclo nunca acabaria. Se voltasse para depois do losango, direto ao `ESCREVER`, a condição nunca mais seria avaliada, e o ciclo também nunca acabaria. O losango é o único sítio onde o ciclo decide se continua, e por isso é lá que a seta tem de chegar em todas as iterações.

A segunda: é a seta que sobe que te diz que há um ciclo. Num fluxograma só com sequência e seleção, as setas andam sempre para baixo, e os dois ramos de um `SE` juntam-se mais abaixo. Quando vês uma seta a subir até um losango, estás a ver uma repetição.

A terceira: o desenho tem de ser inequívoco. A seta de volta chega ao losango por um lado diferente daquele por onde chega a seta de cima, não cruza as outras setas, e o `Sim` e o `Não` ficam escritos nas saídas do losango e não na seta de volta. É esta a técnica nova que vais praticar no diagrams.net, no laboratório deste bloco.

### O ciclo que nunca começa

Se a condição for falsa logo no primeiro teste, o corpo não se executa nenhuma vez. Diz-se que o ciclo tem zero iterações.

Às vezes isto é um erro. Imagina que alguém escreveu a condição do algoritmo das senhas ao contrário:

```text
ALGORITMO DistribuirSenhasCondicaoTrocada
CONSTANTES
    ULTIMA_SENHA ← 3
VARIÁVEIS
    senha: inteiro
INÍCIO
    senha ← 1
    ENQUANTO senha > ULTIMA_SENHA FAZER
        ESCREVER "Senha ", senha
        senha ← senha + 1
    FIM ENQUANTO
    ESCREVER "Fim da distribuição"
FIM
```

A tabela de iterações tem uma única linha:

| Teste | senha | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 > 3` é FALSO | o ciclo termina |

No primeiro teste, `1 > 3` é falso, e o algoritmo salta diretamente para depois do `FIM ENQUANTO`. No ecrã aparece "Fim da distribuição" e mais nada: não foi impressa nenhuma senha. Quem escreveu isto pensou em quando o ciclo devia parar (quando a senha passa a última) e escreveu essa situação no `ENQUANTO`, que é o sítio onde se escreve quando continuar. É a primeira consequência das regras do `ENQUANTO` a fazer estragos.

Outras vezes, um ciclo com zero iterações é exatamente o que deve acontecer. Se o algoritmo conta os pedidos que chegaram hoje a uma papelaria, e hoje não chegou nenhum, o ciclo não deve executar-se nenhuma vez, e a resposta certa é "0 pedidos". Vais ver este caso no exemplo explicado.

Daqui sai uma regra de teste que vais usar sempre: **testa o caso em que o ciclo devia ter zero iterações**, e confirma que o algoritmo dá uma resposta com sentido, como 0, e não uma resposta disparatada ou uma mensagem que não devia aparecer. A este caso chama-se o **caso de zero voltas**, porque o ciclo não chega a dar nenhuma volta.

### O ciclo que nunca acaba

Um **ciclo infinito** é um ciclo cuja condição nunca chega a ser falsa. O corpo executa-se, volta-se ao teste, a condição continua verdadeira, e assim para sempre.

O algoritmo não dá nenhum aviso. Num computador, um programa com um ciclo infinito fica parado a trabalhar, ou a escrever a mesma coisa no ecrã, até alguém o interromper à força. No papel, o trace mostra o problema com toda a clareza, e é por isso que o trace é a melhor ferramenta para encontrar ciclos infinitos.

A causa mais frequente é esquecer a atualização:

```text
ALGORITMO SenhasSemAtualizacao
CONSTANTES
    ULTIMA_SENHA ← 3
VARIÁVEIS
    senha: inteiro
INÍCIO
    senha ← 1
    ENQUANTO senha <= ULTIMA_SENHA FAZER
        ESCREVER "Senha ", senha
    FIM ENQUANTO
    ESCREVER "Fim da distribuição"
FIM
```

As primeiras linhas da tabela de iterações:

| Teste | senha | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` é VERDADEIRO | escreve "Senha 1" |
| 2.º | 1 | `1 <= 3` é VERDADEIRO | escreve "Senha 1" |
| 3.º | 1 | `1 <= 3` é VERDADEIRO | escreve "Senha 1" |
| 4.º | 1 | `1 <= 3` é VERDADEIRO | escreve "Senha 1" |
| 5.º | 1 | `1 <= 3` é VERDADEIRO | escreve "Senha 1" |

E assim para sempre. Olha para a coluna `senha`: vale 1 em todos os testes. A fotografia do estado, tirada cada vez que o algoritmo chega ao `ENQUANTO`, é sempre igual. Como o corpo não lê nada e parte sempre do mesmo estado, faz sempre as mesmas coisas e volta sempre ao mesmo estado. A condição dá sempre verdadeiro, e o ecrã enche-se de "Senha 1". Num ciclo que não lê nada no corpo, **se a fotografia se repetir, o ciclo é infinito**.

Há outras três formas de chegar ao mesmo resultado, e todas se reconhecem pela mesma pergunta.

A atualização pode estar escrita, mas no sítio errado, depois do `FIM ENQUANTO`:

```text
    senha ← 1
    ENQUANTO senha <= ULTIMA_SENHA FAZER
        ESCREVER "Senha ", senha
    FIM ENQUANTO
    senha ← senha + 1
```

A linha existe, mas está fora do corpo, e por isso só seria executada depois de o ciclo acabar, o que nunca acontece. Para o ciclo, é como se ela não existisse. A indentação ajuda a ver este erro: a atualização tem de estar alinhada com as outras instruções do corpo.

A atualização pode andar no sentido errado. Com `senha ← senha - 1` em vez de `senha ← senha + 1`:

| Teste | senha | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` é VERDADEIRO | escreve "Senha 1" |
| 2.º | 0 | `0 <= 3` é VERDADEIRO | escreve "Senha 0" |
| 3.º | -1 | `-1 <= 3` é VERDADEIRO | escreve "Senha -1" |
| 4.º | -2 | `-2 <= 3` é VERDADEIRO | escreve "Senha -2" |
| 5.º | -3 | `-3 <= 3` é VERDADEIRO | escreve "Senha -3" |

Aqui a fotografia não se repete: a senha muda em todas as iterações. Mas muda no sentido errado. Afasta-se de 4, que é o valor que tornaria a condição falsa, e cada número negativo continua a ser menor ou igual a 3. Não basta que a variável mude. Tem de mudar na direção da saída.

E a atualização pode saltar por cima do valor de saída. Uma condição escrita com `!=`, do tipo "enquanto a variável for diferente de 10", só fica falsa se a variável valer exatamente 10 num dos testes. Se a variável começar em 1 e aumentar 2 em cada iteração, passa por 9 e por 11, mas nunca por 10, e o ciclo nunca acaba.

A pergunta que apanha os quatro casos é sempre a mesma, e é a terceira das três perguntas das peças: **em cada iteração, a variável da condição muda, e aproxima-se de um valor que torna a condição falsa?** Se a resposta for não, o ciclo é infinito.

### PARA: a forma curta do ciclo contado

O ciclo das senhas tem uma forma muito comum. Uma variável começa em 1, a condição pergunta se ela ainda não passou de um certo número, e a atualização aumenta-a 1 em cada iteração. A um ciclo em que se sabe, antes de começar, quantas iterações vai ter, chama-se **ciclo contado**.

Os ciclos contados são tão frequentes que têm uma forma curta de escrever, o `PARA`:

```text
PARA senha ← 1 ATÉ ULTIMA_SENHA FAZER
    ESCREVER "Senha ", senha
FIM PARA
```

Lê-se "para a senha de 1 até à última senha, escreve a senha". Compara com o `ENQUANTO` que faz exatamente o mesmo:

```text
senha ← 1
ENQUANTO senha <= ULTIMA_SENHA FAZER
    ESCREVER "Senha ", senha
    senha ← senha + 1
FIM ENQUANTO
```

As três peças estão lá todas, mas no `PARA` estão escondidas na primeira linha. A inicialização é o `senha ← 1` do cabeçalho. A condição é o `ATÉ ULTIMA_SENHA`, que quer dizer "continua enquanto `senha <= ULTIMA_SENHA`". A atualização é feita pelo `FIM PARA`: ao chegar lá, a senha aumenta 1 e o algoritmo volta ao teste. À variável que o `PARA` controla chama-se **variável de controlo**.

O `PARA` desta disciplina segue quatro regras:

1. A variável de controlo avança sempre de 1 em 1.
2. Dentro do corpo, não se muda a variável de controlo nem o limite. O `PARA` trata disso sozinho. Se precisares de mudar a variável a meio, o ciclo não é contado, e deves usar `ENQUANTO`.
3. Se o limite for menor do que o valor inicial, por exemplo `PARA dia ← 1 ATÉ 0 FAZER`, o corpo executa-se zero vezes, porque `1 <= 0` é falso logo no primeiro teste. É o caso de zero voltas do `PARA`.
4. Depois do `FIM PARA`, não se usa o valor da variável de controlo. No `ENQUANTO` equivalente ela ficaria com o limite mais 1, mas há linguagens em que fica com outro valor, incluindo o Python, que vais aprender a seguir. Nesta disciplina, a variável de controlo só se usa dentro do ciclo.

Em muitos livros, a variável de controlo chama-se `i`. É um costume antigo e aceita-se, mas um nome que diga o que se está a contar (`senha`, `dia`, `produto`) torna o algoritmo mais fácil de ler.

O algoritmo completo, com `PARA`:

```text
ALGORITMO DistribuirSenhasComPara
CONSTANTES
    ULTIMA_SENHA ← 3
VARIÁVEIS
    senha: inteiro
INÍCIO
    PARA senha ← 1 ATÉ ULTIMA_SENHA FAZER
        ESCREVER "Senha ", senha
    FIM PARA
    ESCREVER "Fim da distribuição"
FIM
```

A tabela de iterações é igual à do `ENQUANTO`, e é essa a prova de que os dois algoritmos são equivalentes:

| Teste | senha | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` é VERDADEIRO | escreve "Senha 1" |
| 2.º | 2 | `2 <= 3` é VERDADEIRO | escreve "Senha 2" |
| 3.º | 3 | `3 <= 3` é VERDADEIRO | escreve "Senha 3" |
| 4.º | 4 | `4 <= 3` é FALSO | o ciclo termina |

A condição que aparece na tabela é a condição escondida do `PARA`, `senha <= ULTIMA_SENHA`.

A grande vantagem do `PARA` é que não te podes esquecer da inicialização nem da atualização, porque estão no cabeçalho. É muito mais difícil escrever um `PARA` infinito do que um `ENQUANTO` infinito. A desvantagem é que só serve quando se sabe quantas vezes o ciclo se vai repetir antes de ele começar.

No fluxograma, o `PARA` desenha-se como o `ENQUANTO` equivalente: um retângulo com a inicialização, o losango com a condição `senha <= ULTIMA_SENHA?`, o corpo, um retângulo com a atualização `senha ← senha + 1` e a seta de volta ao losango. Alguns livros usam uma figura especial para o `PARA`; nesta disciplina não se usa, para que o desenho mostre as três peças.

### Padrão contador

Um **padrão** é uma forma de resolver um pequeno problema que aparece vezes sem conta, em algoritmos diferentes. Aprende-se uma vez, e depois reconhece-se e reutiliza-se. Os quatro padrões desta secção e das seguintes vão aparecer em quase todos os algoritmos que escreveres até ao fim do ano, também em Python.

O primeiro é o contador. Um **contador** é uma variável que conta quantas vezes uma coisa aconteceu. Segue três regras:

1. Começa em 0, antes do ciclo. Antes de se contar o que quer que seja, já se contaram zero coisas.
2. Sempre que a coisa acontece, aumenta 1: `contador ← contador + 1`.
3. Só se lê o resultado depois do ciclo. Durante o ciclo, o contador tem uma contagem parcial.

Porquê 0 e não 1? Pensa num porteiro que conta as pessoas que entram numa sala. Antes de alguém entrar, a contagem é zero. Se começasse em 1, todas as contagens ficariam com uma pessoa a mais, e numa sala onde não entrou ninguém diria que entrou uma. É o género de erro que só se encontra testando o caso de zero voltas.

Se o `contador ← contador + 1` estiver diretamente no corpo do ciclo, conta todas as iterações. Se estiver dentro de um `SE`, conta só as iterações em que a condição do `SE` é verdadeira. É esta segunda forma a mais útil: contar quantos valores cumprem uma regra.

Exemplo. Uma loja quer saber quantos dos seus 5 produtos têm o stock abaixo do mínimo de 10 unidades, para os encomendar. O algoritmo lê o stock de cada produto e conta os que estão abaixo do mínimo:

```text
ALGORITMO ContarStockBaixo
CONSTANTES
    NUMERO_DE_PRODUTOS ← 5
    STOCK_MINIMO ← 10
VARIÁVEIS
    produto: inteiro
    stock: inteiro
    produtosAbaixoDoMinimo: inteiro
INÍCIO
    produtosAbaixoDoMinimo ← 0
    PARA produto ← 1 ATÉ NUMERO_DE_PRODUTOS FAZER
        ESCREVER "Stock do produto ", produto, "?"
        LER stock
        SE stock < STOCK_MINIMO ENTÃO
            produtosAbaixoDoMinimo ← produtosAbaixoDoMinimo + 1
        FIM SE
    FIM PARA
    ESCREVER "Produtos abaixo do mínimo: ", produtosAbaixoDoMinimo
FIM
```

Como se sabe, antes de o ciclo começar, que há 5 produtos, o ciclo é contado e escreve-se com `PARA`. O contador começa em 0 antes do ciclo, e o seu aumento está dentro do `SE`, porque só se contam os produtos abaixo do mínimo.

Tabela de iterações com os stocks 12, 4, 10, 0 e 9. Para a tabela caber no ecrã, as perguntas que aparecem antes de cada `LER` não estão na última coluna. Lembra-te de que as colunas mostram o estado no momento do teste: o stock lido numa iteração só aparece na coluna `stock` na linha seguinte.

| Teste | produto | stock | produtosAbaixoDoMinimo | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 1 | sem valor | 0 | `1 <= 5` é VERDADEIRO | lê 12 |
| 2.º | 2 | 12 | 0 | `2 <= 5` é VERDADEIRO | lê 4 |
| 3.º | 3 | 4 | 1 | `3 <= 5` é VERDADEIRO | lê 10 |
| 4.º | 4 | 10 | 1 | `4 <= 5` é VERDADEIRO | lê 0 |
| 5.º | 5 | 0 | 2 | `5 <= 5` é VERDADEIRO | lê 9 |
| 6.º | 6 | 9 | 3 | `6 <= 5` é FALSO | o ciclo termina |

O contador aumentou três vezes: com 4, com 0 e com 9. Não aumentou com 12, que está acima do mínimo, nem com 10, que é o próprio mínimo. `10 < 10` é falso: dez não é menor do que dez. O enunciado diz "abaixo do mínimo", e um produto com exatamente o mínimo não está abaixo dele. É a regra das fronteiras do guia 03, agora dentro de um ciclo: o 9, o 10 e o 12 foram escolhidos de propósito.

### Padrão totalizador

Um **totalizador** é uma variável que vai somando valores ao longo das iterações. Também se chama **acumulador**, e é esse o nome que vais encontrar mais vezes em Python. Segue três regras, parecidas com as do contador:

1. Começa em 0, antes do ciclo. A soma de nada é zero.
2. Em cada iteração, soma-se o valor: `total ← total + valor`.
3. Só se lê o resultado depois do ciclo.

A diferença para o contador está na regra 2. O contador soma 1, seja qual for o valor. O totalizador soma o próprio valor. O contador responde à pergunta "quantos?", e o totalizador responde à pergunta "quanto?". Se leres as quantidades de três pedidos, 12, 30 e 50, o contador de pedidos fica com 3 e o totalizador de unidades fica com 92.

Exemplo. Uma loja quer saber o total das vendas de vários dias. No início, o funcionário diz quantos dias quer somar, e depois escreve as vendas de cada dia, em cêntimos. Os valores em dinheiro estão em cêntimos pela razão que viste no guia 02: são números inteiros, e as contas com inteiros são exatas.

```text
ALGORITMO TotalDeVendas
VARIÁVEIS
    dias: inteiro
    dia: inteiro
    vendasDoDia: inteiro
    totalVendas: inteiro
INÍCIO
    ESCREVER "Quantos dias queres somar?"
    LER dias
    totalVendas ← 0
    PARA dia ← 1 ATÉ dias FAZER
        ESCREVER "Vendas do dia ", dia, ", em cêntimos?"
        LER vendasDoDia
        totalVendas ← totalVendas + vendasDoDia
    FIM PARA
    ESCREVER "Total vendido: ", totalVendas, " cêntimos"
FIM
```

Repara que o número de dias só se conhece durante a execução, quando o funcionário o escreve. Mesmo assim, o ciclo é contado: quando o algoritmo chega ao `PARA`, o valor de `dias` já foi lido, e por isso já se sabe quantas iterações vai haver. É isso que conta para escolher o `PARA`.

Tabela de iterações com 3 dias e as vendas 1250, 800 e 2100 (sem as perguntas):

| Teste | dia | vendasDoDia | totalVendas | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 1 | sem valor | 0 | `1 <= 3` é VERDADEIRO | lê 1250 |
| 2.º | 2 | 1250 | 1250 | `2 <= 3` é VERDADEIRO | lê 800 |
| 3.º | 3 | 800 | 2050 | `3 <= 3` é VERDADEIRO | lê 2100 |
| 4.º | 4 | 2100 | 4150 | `4 <= 3` é FALSO | o ciclo termina |

O total começou em 0, passou a 1250, depois a 2050 e depois a 4150. Em cada linha, o novo total é o total da linha de cima mais o valor lido nessa iteração. Se o funcionário escrever 0 dias, o `PARA` faz zero iterações, e o algoritmo escreve "Total vendido: 0 cêntimos", que é a resposta certa.

Há dois erros clássicos com totalizadores, e os dois são erros de inicialização.

O primeiro é esquecer a inicialização, apagando a linha `totalVendas ← 0`. Na primeira iteração, o algoritmo tenta calcular `totalVendas + vendasDoDia` com `totalVendas` sem valor. É o erro do guia 02, uma variável usada antes de receber valor, agora dentro de um ciclo. O trace para nessa linha: não se consegue somar 1250 a uma caixa vazia.

O segundo é pôr a inicialização dentro do ciclo:

```text
    PARA dia ← 1 ATÉ dias FAZER
        totalVendas ← 0
        ESCREVER "Vendas do dia ", dia, ", em cêntimos?"
        LER vendasDoDia
        totalVendas ← totalVendas + vendasDoDia
    FIM PARA
```

Com os mesmos dados:

| Teste | dia | vendasDoDia | totalVendas | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 1 | sem valor | sem valor | `1 <= 3` é VERDADEIRO | lê 1250 |
| 2.º | 2 | 1250 | 1250 | `2 <= 3` é VERDADEIRO | lê 800 |
| 3.º | 3 | 800 | 800 | `3 <= 3` é VERDADEIRO | lê 2100 |
| 4.º | 4 | 2100 | 2100 | `4 <= 3` é FALSO | o ciclo termina |

Repara na primeira linha: como a inicialização saiu de antes do ciclo, o total ainda não tem valor no primeiro teste. Depois, em cada iteração, o total volta a zero antes de se somar o valor do dia, e por isso nunca guarda mais do que um dia. O algoritmo escreve "Total vendido: 2100 cêntimos", que são só as vendas do último dia. A regra a fixar: **o que se inicializa dentro do ciclo recomeça em cada iteração**. Os contadores e os totalizadores inicializam-se sempre antes do ciclo.

Com um totalizador e um contador no mesmo ciclo consegues calcular médias: a soma a dividir pelo número de valores. Vais precisar de cuidado com o caso em que o contador fica em zero, porque não se pode dividir por zero.

### Padrão sentinela

Volta ao problema dos pedidos de uma papelaria. O funcionário vai escrevendo as quantidades dos pedidos à medida que chegam, e ninguém sabe, antes de o ciclo começar, quantos vão ser. Não há um número de dias para ler no início. O `PARA` não serve.

A solução é combinar um valor especial que quer dizer "acabou". Quem escreve os dados escreve esse valor no fim, e o algoritmo, quando o lê, sabe que não há mais dados. A este valor chama-se **sentinela**. É como a última pessoa de uma fila levar uma placa a dizer "sou a última": quem atende não precisa de contar a fila, só precisa de parar quando vir a placa.

A sentinela tem de cumprir duas regras. Não pode ser um valor que os dados verdadeiros possam ter: se fosse, o algoritmo pararia no meio dos dados. E quem escreve os dados tem de saber qual é, e por isso a pergunta do `ESCREVER` diz-lho. Nesta disciplina, a sentinela é sempre uma constante com nome, `SENTINELA`, para o algoritmo dizer o que ela é.

Um ciclo com sentinela tem sempre esta forma, e cada peça tem uma razão:

- a inicialização inclui ler o primeiro valor antes do ciclo. A esta leitura antes do ciclo chama-se **leitura antecipada**;
- a condição é "o valor lido não é a sentinela";
- o corpo trata o valor e, como última instrução, lê o valor seguinte. Essa leitura no fim do corpo é a atualização: é ela que muda a variável da condição.

Porquê ler antes do ciclo e no fim do corpo, e não no princípio do corpo? Porque cada valor tem de passar pela condição antes de ser tratado. Com esta forma, o valor lido vai sempre direto para o teste. Se for um dado, entra no corpo e é tratado. Se for a sentinela, a condição dá falso e o ciclo termina, sem a sentinela ter sido tratada como um dado.

Exemplo. Num armazém, um funcionário regista o peso, em quilogramas, de cada caixa descarregada de um camião, e escreve 0 quando o camião fica vazio. Nenhuma caixa pesa 0 kg, e por isso o 0 serve de sentinela. No fim, o algoritmo diz quantas caixas foram descarregadas e quanto pesam ao todo.

```text
ALGORITMO SomarCaixas
CONSTANTES
    SENTINELA ← 0
VARIÁVEIS
    peso: inteiro
    caixas: inteiro
    pesoTotal: inteiro
INÍCIO
    caixas ← 0
    pesoTotal ← 0
    ESCREVER "Peso da caixa em kg (0 para terminar)?"
    LER peso
    ENQUANTO peso != SENTINELA FAZER
        caixas ← caixas + 1
        pesoTotal ← pesoTotal + peso
        ESCREVER "Peso da caixa em kg (0 para terminar)?"
        LER peso
    FIM ENQUANTO
    ESCREVER "Caixas descarregadas: ", caixas
    ESCREVER "Peso total: ", pesoTotal, " kg"
FIM
```

Tens aqui um contador (`caixas`) e um totalizador (`pesoTotal`) no mesmo ciclo. No fluxograma, a leitura antecipada fica antes do losango e a leitura do valor seguinte fica no fim do corpo, mesmo antes da seta de volta:

```mermaid
flowchart TD
    A([Início]) --> B["caixas ← 0"]
    B --> C["pesoTotal ← 0"]
    C --> D[/ESCREVER pergunta/]
    D --> E[/LER peso/]
    E --> F{"peso != SENTINELA?"}
    F -->|Sim| G["caixas ← caixas + 1"]
    G --> H["pesoTotal ← pesoTotal + peso"]
    H --> I[/ESCREVER pergunta/]
    I --> J[/LER peso/]
    J --> F
    F -->|Não| K[/ESCREVER caixas/]
    K --> L[/ESCREVER pesoTotal/]
    L --> Z([Fim])
```

Percorre-o com o dedo: as duas inicializações, a pergunta e a primeira leitura, e depois o losango. Enquanto o peso não for a sentinela, sais pelo `Sim`, contas a caixa, somas o peso, lês o peso seguinte e a seta leva-te ao losango, onde esse novo peso é testado. Quando o peso lido for 0, sais pelo `Não` e escreves os dois resultados.

Tabela de iterações com os pesos 18, 25, 7 e, no fim, a sentinela 0 (sem as perguntas):

| Teste | peso | caixas | pesoTotal | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 18 | 0 | 0 | `18 != 0` é VERDADEIRO | lê 25 |
| 2.º | 25 | 1 | 18 | `25 != 0` é VERDADEIRO | lê 7 |
| 3.º | 7 | 2 | 43 | `7 != 0` é VERDADEIRO | lê 0 |
| 4.º | 0 | 3 | 50 | `0 != 0` é FALSO | o ciclo termina |

Três iterações e quatro testes. A sentinela aparece no último teste, faz a condição dar falso, e nada é feito com ela: não é contada nem somada. Se o primeiro valor escrito for logo 0, porque o camião vinha vazio, o ciclo tem zero iterações e o algoritmo escreve 0 caixas e 0 kg. É o caso de zero voltas, e a resposta está certa.

Agora o erro que este padrão existe para evitar. Quem ainda não conhece a leitura antecipada costuma pôr a leitura no princípio do corpo. Como a condição precisa de um valor no primeiro teste, inventa um valor qualquer para o peso, só para entrar no ciclo:

```text
ALGORITMO SomarCaixasSemLeituraAntecipada
CONSTANTES
    SENTINELA ← 0
VARIÁVEIS
    peso: inteiro
    caixas: inteiro
    pesoTotal: inteiro
INÍCIO
    caixas ← 0
    pesoTotal ← 0
    peso ← 1
    ENQUANTO peso != SENTINELA FAZER
        ESCREVER "Peso da caixa em kg (0 para terminar)?"
        LER peso
        caixas ← caixas + 1
        pesoTotal ← pesoTotal + peso
    FIM ENQUANTO
    ESCREVER "Caixas descarregadas: ", caixas
    ESCREVER "Peso total: ", pesoTotal, " kg"
FIM
```

Com os mesmos dados:

| Teste | peso | caixas | pesoTotal | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 1 | 0 | 0 | `1 != 0` é VERDADEIRO | lê 18 |
| 2.º | 18 | 1 | 18 | `18 != 0` é VERDADEIRO | lê 25 |
| 3.º | 25 | 2 | 43 | `25 != 0` é VERDADEIRO | lê 7 |
| 4.º | 7 | 3 | 50 | `7 != 0` é VERDADEIRO | lê 0 |
| 5.º | 0 | 4 | 50 | `0 != 0` é FALSO | o ciclo termina |

O algoritmo escreve "Caixas descarregadas: 4", quando foram três. Na quarta iteração, o 0 foi lido e, antes de a condição o poder testar, foi contado como caixa e somado ao peso. O peso total dá 50, que está certo, mas só por coincidência: somar 0 não muda nada. Se a sentinela fosse -1, a mesma versão errada somava também o -1, e o peso total dava 49. Um algoritmo que acerta por coincidência está errado na mesma. O próprio `peso ← 1` já era um sinal de alarme: um valor inventado, que não vem de lado nenhum, só para convencer a condição a deixar entrar.

### Padrão validação repetida

No guia 03 aprendeste a validar uma entrada com um `SE`: se o valor for inválido, escreve-se uma mensagem. Mas depois dessa mensagem o algoritmo ficava sem um valor válido para trabalhar, e a única coisa que podia fazer era terminar. Quem se enganou tinha de começar tudo de novo.

Com um ciclo, dá para fazer melhor: pedir o valor outra vez, e outra, até ser válido. A isto chama-se **validação repetida**. É um ciclo cuja condição é "o valor é inválido", e cujo corpo escreve uma mensagem de erro e lê o valor outra vez.

Exemplo. A papelaria só aceita pedidos de 1 a 50 unidades. O algoritmo pede a quantidade até ela estar nesse intervalo:

```text
ALGORITMO PedirQuantidadeValida
CONSTANTES
    QUANTIDADE_MINIMA ← 1
    CAPACIDADE_MAXIMA ← 50
VARIÁVEIS
    quantidade: inteiro
INÍCIO
    ESCREVER "Quantidade do pedido (1 a 50)?"
    LER quantidade
    ENQUANTO quantidade < QUANTIDADE_MINIMA OU quantidade > CAPACIDADE_MAXIMA FAZER
        ESCREVER "Quantidade inválida. Escreve um número de 1 a 50."
        LER quantidade
    FIM ENQUANTO
    ESCREVER "Pedido aceite: ", quantidade, " unidades"
FIM
```

As três peças, uma a uma. A inicialização é a primeira leitura, antes do ciclo, como na sentinela. A condição é a de valor inválido, que no guia 03 aprendeste a escrever como o contrário do intervalo, com `OU`: a quantidade é inválida se estiver abaixo do mínimo ou acima do máximo. A atualização é o `LER` dentro do corpo, que substitui o valor inválido por um valor novo.

A mensagem de erro diz o intervalo. Quem se enganou fica a saber o que tem de escrever, e não apenas que errou.

No fluxograma, a validação repetida tem a mesma forma do ciclo com sentinela: uma leitura antes do losango e outra no fim do corpo, mesmo antes da seta de volta. O que muda é a condição do losango e o que o corpo faz com o valor.

```mermaid
flowchart TD
    A([Início]) --> B[/ESCREVER pergunta/]
    B --> C[/LER quantidade/]
    C --> D{"quantidade < QUANTIDADE_MINIMA OU quantidade > CAPACIDADE_MAXIMA?"}
    D -->|Sim| E[/ESCREVER quantidade inválida/]
    E --> F[/LER quantidade/]
    F --> D
    D -->|Não| G[/ESCREVER pedido aceite/]
    G --> Z([Fim])
```

Descrição do percurso: depois da pergunta e da primeira leitura, o losango pergunta se a quantidade é inválida. Se for, sai pelo `Sim`, escreve a mensagem de erro, lê outra quantidade e a seta volta ao losango, que testa o valor novo. Quando a quantidade for válida, sai pelo `Não`, escreve que o pedido foi aceite e termina. Repara que aqui o `Sim` é o caminho do erro: o ciclo continua enquanto o valor for inválido.

Tabela de iterações quando a pessoa escreve 0, depois 75 e depois 12:

| Teste | quantidade | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 0 | `0 < 1 OU 0 > 50` é VERDADEIRO | escreve "Quantidade inválida. Escreve um número de 1 a 50."; lê 75 |
| 2.º | 75 | `75 < 1 OU 75 > 50` é VERDADEIRO | escreve "Quantidade inválida. Escreve um número de 1 a 50."; lê 12 |
| 3.º | 12 | `12 < 1 OU 12 > 50` é FALSO | o ciclo termina |

E quando a pessoa escreve logo um valor válido, 12:

| Teste | quantidade | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 12 | `12 < 1 OU 12 > 50` é FALSO | o ciclo termina |

Neste segundo caso, o ciclo nunca começa, e está certo: não há nada a corrigir, e não aparece nenhuma mensagem de erro.

Este ciclo é diferente dos anteriores num ponto. O número de iterações não depende do algoritmo, depende da pessoa. Se ela escrever valores inválidos durante uma hora, o ciclo repete-se durante uma hora. Isso não é um ciclo infinito: o ciclo termina assim que aparecer um valor válido, e a atualização, o `LER`, existe em todas as iterações.

O mais útil deste padrão está no que acontece depois do `FIM ENQUANTO`. Quando o algoritmo lá chega, a condição do ciclo acabou de dar falso, e por isso tens a certeza de que a quantidade está entre 1 e 50. O resto do algoritmo pode usá-la sem voltar a verificar. É uma ideia que vale para todos os ciclos: **depois de um ciclo, a sua condição é falsa**, e isso diz-te alguma coisa sobre o estado.

### Escolher entre ENQUANTO e PARA

A escolha faz-se com uma pergunta: **antes de o ciclo começar, já se sabe quantas vezes ele se vai repetir?** Se sim, o ciclo é contado, e usa-se `PARA`. Se não, porque o fim depende de alguma coisa que só acontece durante o ciclo, como um valor lido, usa-se `ENQUANTO`.

"Antes de o ciclo começar" é o momento em que o algoritmo chega ao ciclo, e não o momento em que escreves o algoritmo. É por isso que o total de vendas usa `PARA`: quando escreves o algoritmo não sabes quantos dias vão ser, mas quando o algoritmo chega ao ciclo esse número já foi lido.

| Situação | Ciclo | Porquê |
| --- | --- | --- |
| Imprimir as senhas de 1 a 100 | `PARA` | Sabe-se que são 100 antes de começar |
| Ler o stock dos 5 produtos da loja | `PARA` | São sempre 5 |
| Somar as vendas de um número de dias que o funcionário escreve no início | `PARA` | O número é lido antes de o ciclo começar |
| Ler pedidos até aparecer o 0 | `ENQUANTO` | Só se sabe que acabou quando aparece a sentinela |
| Pedir a quantidade até ser válida | `ENQUANTO` | Depende do que a pessoa escrever |
| Juntar dinheiro até chegar ao preço de um objeto | `ENQUANTO` | Depende dos valores que forem entrando |

Todo o `PARA` se pode escrever como um `ENQUANTO`, e viste como. O contrário não é verdade: um ciclo com sentinela ou com validação repetida não se escreve com `PARA`, porque não há um número de iterações para pôr no `ATÉ`. Se estiveres em dúvida, o `ENQUANTO` funciona sempre, mas obriga-te a escrever as três peças à mão, com mais oportunidades de errar. Quando o ciclo é contado, o `PARA` é a escolha mais segura.

> Para saberes mais (leitura opcional, não sai nos exercícios). Há linguagens com um ciclo que testa a condição no fim do corpo, e não no princípio, e que por isso se executa sempre pelo menos uma vez. Em alguns livros aparece escrito como `REPETIR ... ATÉ`. Nesta unidade não se usa: tudo o que ele faz consegue-se com `ENQUANTO`, como viste na validação repetida, e o Python, que vais aprender a seguir, também não o tem.

## Exemplo explicado (30 min): contar pedidos válidos e totalizar unidades

Este exemplo junta tudo o que viste: um ciclo com sentinela, um `SE` com um intervalo dentro do ciclo, dois contadores e um totalizador.

### Passo 1: O enunciado

> Uma papelaria recebe pedidos de material ao longo do dia. Cada pedido tem uma quantidade de unidades. A papelaria só aceita pedidos de 1 a 50 unidades, porque 50 é o máximo que a carrinha de entregas leva numa viagem. Uma quantidade negativa é um engano de escrita e também é recusada. O funcionário escreve a quantidade de cada pedido, um de cada vez, e escreve 0 quando já não há mais pedidos. Cada pedido recusado é assinalado no momento em que é escrito. No fim, o algoritmo mostra quantos pedidos válidos houve, quantas unidades somam os pedidos válidos e quantos pedidos foram recusados.

### Passo 2: O contrato

O contrato vem antes do pseudocódigo, como em todos os guias anteriores: as respostas às quatro perguntas.

| Pergunta | Resposta |
| --- | --- |
| Entradas | Uma sequência de quantidades de pedidos, números inteiros, que acaba com um 0 |
| Saídas | Uma mensagem por cada pedido recusado, no momento em que é escrito; no fim, o número de pedidos válidos, o total de unidades dos pedidos válidos e o número de pedidos recusados |
| Restrições | Um pedido é válido se tiver de 1 a 50 unidades, os dois extremos incluídos; o 0 não é um pedido, é o sinal de fim |
| Condições | Cada pedido é válido ou recusado; os pedidos repetem-se até aparecer o 0 |

Há uma pergunta que vale a pena fazer já: o que acontece a um pedido recusado? O enunciado diz que é assinalado e contado, e que os outros pedidos continuam. Um pedido errado não impede o funcionário de escrever o seguinte. Isto decide a forma do algoritmo, como vais ver no passo 4.

### Passo 3: A tabela de casos esperados

Como no guia 03, a tabela de casos esperados faz-se agora, a partir do enunciado, antes de haver algoritmo. Assim, quando fizeres o trace, tens com o que comparar.

| Caso | Quantidades escritas | Válidos | Unidades | Recusados | Porque é que este caso foi escolhido |
| --- | --- | ---: | ---: | ---: | --- |
| A | 12, 60, 30, -4, 50, 0 | 3 | 92 | 2 | O caso normal, com válidos e recusados dos dois lados do intervalo |
| B | 0 | 0 | 0 | 0 | O caso de zero voltas: nenhum pedido no dia |
| C | 1, 50, 51, 0 | 2 | 51 | 1 | As fronteiras: o 1 e o 50 são válidos, o 51 não |
| D | 75, 0 | 0 | 0 | 1 | Só pedidos recusados |

No caso A, os válidos são o 12, o 30 e o 50, que somam 92 unidades. O 60 e o -4 são recusados. No caso C, o 1 e o 50 são válidos, e somam 51, e o 51 é recusado. O caso B é o que mais algoritmos apanha: com zero pedidos, a resposta tem de ser zero em tudo, sem mensagens de pedido recusado.

### Passo 4: As peças do ciclo, uma a uma

Primeira decisão: `ENQUANTO` ou `PARA`? Antes de o ciclo começar, não se sabe quantos pedidos vai haver. Só se sabe que acabou quando aparece o 0. É o padrão sentinela, com `ENQUANTO`.

A inicialização tem duas partes. Os três resultados, `pedidosValidos`, `pedidosRecusados` e `totalUnidades`, começam em 0, porque antes do primeiro pedido não se contou nem somou nada. E a primeira quantidade é lida antes do ciclo, a leitura antecipada, porque a condição precisa dela logo no primeiro teste.

A condição é `quantidade != SENTINELA`: continua-se enquanto a quantidade lida não for o 0.

A atualização é a leitura da quantidade seguinte, no fim do corpo. É ela que muda a variável da condição, e é ela que um dia traz o 0.

O trabalho de cada iteração é decidir se o pedido é válido. É um intervalo do guia 03, com os dois extremos incluídos: `quantidade >= QUANTIDADE_MINIMA E quantidade <= CAPACIDADE_MAXIMA`. Se for válido, conta-se nos válidos e soma-se ao total. Se não for, conta-se nos recusados e assinala-se.

Porque é que a validade é um `SE`, e não uma validação repetida? Porque o enunciado não manda corrigir o pedido errado. Manda assinalá-lo, contá-lo e seguir para o próximo. Uma validação repetida obrigaria o funcionário a corrigir aquele pedido antes de poder escrever o seguinte, e isso seria outro requisito. É o enunciado que decide, e não a vontade de usar o padrão mais recente.

### Passo 5: O pseudocódigo

```text
ALGORITMO ContarPedidosValidos
CONSTANTES
    SENTINELA ← 0
    QUANTIDADE_MINIMA ← 1
    CAPACIDADE_MAXIMA ← 50
VARIÁVEIS
    quantidade: inteiro
    pedidosValidos: inteiro
    pedidosRecusados: inteiro
    totalUnidades: inteiro
INÍCIO
    pedidosValidos ← 0
    pedidosRecusados ← 0
    totalUnidades ← 0
    ESCREVER "Quantidade do pedido (0 para terminar)?"
    LER quantidade
    ENQUANTO quantidade != SENTINELA FAZER
        SE quantidade >= QUANTIDADE_MINIMA E quantidade <= CAPACIDADE_MAXIMA ENTÃO
            pedidosValidos ← pedidosValidos + 1
            totalUnidades ← totalUnidades + quantidade
        SENÃO
            pedidosRecusados ← pedidosRecusados + 1
            ESCREVER "Pedido recusado: ", quantidade, " unidades"
        FIM SE
        ESCREVER "Quantidade do pedido (0 para terminar)?"
        LER quantidade
    FIM ENQUANTO
    ESCREVER "Pedidos válidos: ", pedidosValidos
    ESCREVER "Total de unidades: ", totalUnidades
    ESCREVER "Pedidos recusados: ", pedidosRecusados
FIM
```

As decisões deste pseudocódigo, uma a uma:

1. A sentinela e os limites do intervalo são constantes. São regras do enunciado, e assim cada condição diz o que está a verificar. Se a carrinha passar a levar 60 unidades, muda-se uma linha.
2. As quatro variáveis são `inteiro`. Quantidades de unidades e contagens de pedidos não têm parte decimal.
3. Os dois contadores e o totalizador são inicializados a 0 antes do ciclo, e nunca dentro dele.
4. A pergunta diz qual é a sentinela. Quem usa o algoritmo tem de saber como se termina.
5. A mesma pergunta e o mesmo `LER` aparecem duas vezes: antes do ciclo, como leitura antecipada, e no fim do corpo, como atualização. Não é repetição por descuido. É a forma do padrão sentinela.
6. O `SE` fica dentro do ciclo, e tem o seu próprio `FIM SE`, antes da leitura seguinte. A indentação mostra os dois níveis: o que está dentro do `SE` tem oito espaços, o que está dentro do ciclo e fora do `SE` tem quatro.
7. Os resultados só são escritos depois do `FIM ENQUANTO`, quando as contagens estão completas. A única coisa escrita durante o ciclo é a mensagem de pedido recusado, porque o enunciado pede que seja no momento.

### Passo 6: O fluxograma

```mermaid
flowchart TD
    A([Início]) --> B["pedidosValidos ← 0"]
    B --> C["pedidosRecusados ← 0"]
    C --> D["totalUnidades ← 0"]
    D --> E[/ESCREVER pergunta/]
    E --> F[/LER quantidade/]
    F --> G{"quantidade != SENTINELA?"}
    G -->|Sim| H{"quantidade >= QUANTIDADE_MINIMA E quantidade <= CAPACIDADE_MAXIMA?"}
    H -->|Sim| I["pedidosValidos ← pedidosValidos + 1"]
    I --> J["totalUnidades ← totalUnidades + quantidade"]
    H -->|Não| K["pedidosRecusados ← pedidosRecusados + 1"]
    K --> L[/ESCREVER pedido recusado/]
    J --> M[/ESCREVER pergunta/]
    L --> M
    M --> N[/LER quantidade/]
    N --> G
    G -->|Não| O[/ESCREVER pedidosValidos/]
    O --> P[/ESCREVER totalUnidades/]
    P --> Q[/ESCREVER pedidosRecusados/]
    Q --> Z([Fim])
```

Descrição do percurso, para quem não vê o desenho. Do início, o caminho passa pelas três inicializações, pela pergunta e pela primeira leitura, e chega ao primeiro losango, o do ciclo. Se a quantidade não for a sentinela, sai pelo `Sim` e chega ao segundo losango, o do `SE`. Pelo `Sim` do segundo losango, conta o pedido válido e soma as unidades. Pelo `Não`, conta o pedido recusado e escreve a mensagem. Os dois ramos juntam-se na pergunta seguinte, que corresponde ao `FIM SE`. Segue-se a leitura da quantidade seguinte, e a seta volta ao primeiro losango. Quando a quantidade lida for a sentinela, o primeiro losango sai pelo `Não` e o caminho passa pelas três escritas finais até ao fim.

Repara na diferença entre os dois losangos. O do `SE` tem dois ramos que descem e se juntam mais abaixo. O do ciclo tem um ramo, o `Sim`, que acaba por subir de volta a ele, e um ramo, o `Não`, que é a saída do ciclo. Tudo o que está entre o `Sim` do primeiro losango e a seta que sobe é o corpo do ciclo. É este fluxograma que vais desenhar no laboratório.

### Passo 7: O trace linha a linha de um caso curto

Primeiro, o trace completo de um caso curto, para veres o `SE` a funcionar dentro do ciclo. O funcionário escreve 12, depois 60, e depois 0.

| Passo | Instrução executada | quantidade | pedidosValidos | pedidosRecusados | totalUnidades | Condição e resultado | Ecrã |
| ---: | --- | ---: | ---: | ---: | ---: | --- | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | sem valor | nenhuma | nada |
| 1 | `pedidosValidos ← 0` | sem valor | 0 | sem valor | sem valor | nenhuma | nada |
| 2 | `pedidosRecusados ← 0` | sem valor | 0 | 0 | sem valor | nenhuma | nada |
| 3 | `totalUnidades ← 0` | sem valor | 0 | 0 | 0 | nenhuma | nada |
| 4 | `ESCREVER "Quantidade do pedido (0 para terminar)?"` | sem valor | 0 | 0 | 0 | nenhuma | Quantidade do pedido (0 para terminar)? |
| 5 | `LER quantidade` | 12 | 0 | 0 | 0 | nenhuma | a pessoa escreve 12 |
| 6 | `ENQUANTO quantidade != SENTINELA FAZER` | 12 | 0 | 0 | 0 | `12 != 0` é VERDADEIRO | nada |
| 7 | `SE quantidade >= QUANTIDADE_MINIMA E quantidade <= CAPACIDADE_MAXIMA ENTÃO` | 12 | 0 | 0 | 0 | `12 >= 1` é VERDADEIRO, `12 <= 50` é VERDADEIRO; VERDADEIRO E VERDADEIRO dá VERDADEIRO | nada |
| 8 | `pedidosValidos ← pedidosValidos + 1` | 12 | 1 | 0 | 0 | nenhuma | nada |
| 9 | `totalUnidades ← totalUnidades + quantidade` | 12 | 1 | 0 | 12 | nenhuma | nada |
| 10 | `ESCREVER "Quantidade do pedido (0 para terminar)?"` | 12 | 1 | 0 | 12 | nenhuma | Quantidade do pedido (0 para terminar)? |
| 11 | `LER quantidade` | 60 | 1 | 0 | 12 | nenhuma | a pessoa escreve 60 |
| 12 | `ENQUANTO quantidade != SENTINELA FAZER` | 60 | 1 | 0 | 12 | `60 != 0` é VERDADEIRO | nada |
| 13 | `SE quantidade >= QUANTIDADE_MINIMA E quantidade <= CAPACIDADE_MAXIMA ENTÃO` | 60 | 1 | 0 | 12 | `60 >= 1` é VERDADEIRO, `60 <= 50` é FALSO; VERDADEIRO E FALSO dá FALSO | nada |
| 14 | `pedidosRecusados ← pedidosRecusados + 1` | 60 | 1 | 1 | 12 | nenhuma | nada |
| 15 | `ESCREVER "Pedido recusado: ", quantidade, " unidades"` | 60 | 1 | 1 | 12 | nenhuma | Pedido recusado: 60 unidades |
| 16 | `ESCREVER "Quantidade do pedido (0 para terminar)?"` | 60 | 1 | 1 | 12 | nenhuma | Quantidade do pedido (0 para terminar)? |
| 17 | `LER quantidade` | 0 | 1 | 1 | 12 | nenhuma | a pessoa escreve 0 |
| 18 | `ENQUANTO quantidade != SENTINELA FAZER` | 0 | 1 | 1 | 12 | `0 != 0` é FALSO | nada |
| 19 | `ESCREVER "Pedidos válidos: ", pedidosValidos` | 0 | 1 | 1 | 12 | nenhuma | Pedidos válidos: 1 |
| 20 | `ESCREVER "Total de unidades: ", totalUnidades` | 0 | 1 | 1 | 12 | nenhuma | Total de unidades: 12 |
| 21 | `ESCREVER "Pedidos recusados: ", pedidosRecusados` | 0 | 1 | 1 | 12 | nenhuma | Pedidos recusados: 1 |

Os passos 1 a 5 são a inicialização: três variáveis a zero, a pergunta e a leitura antecipada. No passo 6, a condição do ciclo é testada pela primeira vez, com a quantidade 12, e é verdadeira.

A primeira iteração vai do passo 7 ao passo 11. No passo 7, o `SE` avalia o intervalo com 12, e as duas comparações são verdadeiras. Executa-se o ramo do `ENTÃO`: o contador de válidos passa a 1 e o total passa a 12. O ramo do `SENÃO` não aparece na tabela porque não foi executado. Nos passos 10 e 11, a pergunta e a leitura do valor seguinte, 60.

No passo 12, o algoritmo voltou ao `ENQUANTO`. `60 != 0` é verdadeiro, e começa a segunda iteração. Agora o `SE` dá falso, porque 60 é maior do que 50, e executa-se o ramo do `SENÃO`: o contador de recusados passa a 1 e aparece a mensagem. O total não muda, porque o ramo que soma não foi executado.

No passo 18, a quantidade lida é o 0, e `0 != 0` é falso. O ciclo termina. O 0 não passou pelo `SE`, não foi contado nem somado. Os passos 19 a 21 escrevem os resultados.

### Passo 8: A tabela de iterações do caso normal

Agora o caso A, com a tabela de iterações. As perguntas não estão na última coluna.

| Teste | quantidade | pedidosValidos | pedidosRecusados | totalUnidades | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| 1.º | 12 | 0 | 0 | 0 | `12 != 0` é VERDADEIRO | lê 60 |
| 2.º | 60 | 1 | 0 | 12 | `60 != 0` é VERDADEIRO | escreve "Pedido recusado: 60 unidades"; lê 30 |
| 3.º | 30 | 1 | 1 | 12 | `30 != 0` é VERDADEIRO | lê -4 |
| 4.º | -4 | 2 | 1 | 42 | `-4 != 0` é VERDADEIRO | escreve "Pedido recusado: -4 unidades"; lê 50 |
| 5.º | 50 | 2 | 2 | 42 | `50 != 0` é VERDADEIRO | lê 0 |
| 6.º | 0 | 3 | 2 | 92 | `0 != 0` é FALSO | o ciclo termina |

Lê a tabela linha a linha e explica cada mudança pela instrução que a provocou. É isto que vais ter de fazer no checkpoint do bloco.

No 1.º teste, o estado é o da inicialização: a quantidade 12, lida antes do ciclo, e tudo o resto a zero. Durante essa iteração, o 12 é válido, e por isso, no 2.º teste, `pedidosValidos` vale 1 e `totalUnidades` vale 12. A quantidade já é 60, lida no fim da primeira iteração.

Durante a 2.ª iteração, o 60 é recusado. No 3.º teste, `pedidosRecusados` vale 1, e os válidos e o total não mudaram. Durante a 3.ª, o 30 é válido: no 4.º teste há 2 válidos e 42 unidades. Durante a 4.ª, o -4 é recusado: no 5.º teste há 2 recusados. Durante a 5.ª, o 50 é válido, porque `50 <= 50` é verdadeiro: no 6.º teste há 3 válidos e 92 unidades.

No 6.º teste, a quantidade é o 0, e o ciclo termina. Houve 5 iterações, uma por pedido, e 6 testes. Os valores finais são os da última linha: 3 válidos, 92 unidades, 2 recusados. No ecrã apareceram, durante o ciclo, as duas mensagens de pedido recusado, e depois do ciclo os três resultados.

Repara no que muda de uma linha para a seguinte: ou mudam os válidos e o total ao mesmo tempo, ou mudam só os recusados. Nunca mudam os válidos sem mudar o total, e nunca mudam os recusados ao mesmo tempo que os válidos, porque cada pedido vai para um só dos ramos do `SE`. Se, ao fazeres uma tabela destas, encontrares uma linha que não obedece a isto, há um erro no algoritmo ou no trace.

### Passo 9: Comparar com o previsto

Os quatro casos do passo 3, com os resultados que o algoritmo dá quando se faz o trace de cada um:

| Caso | Quantidades escritas | Iterações | Válidos | Unidades | Recusados | Mensagens de pedido recusado |
| --- | --- | ---: | ---: | ---: | ---: | ---: |
| A | 12, 60, 30, -4, 50, 0 | 5 | 3 | 92 | 2 | 2 |
| B | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 1, 50, 51, 0 | 3 | 2 | 51 | 1 | 1 |
| D | 75, 0 | 1 | 0 | 0 | 1 | 1 |

Coincidem com os resultados esperados nos quatro casos. No caso B, o ciclo tem zero iterações, e o algoritmo escreve três zeros, sem nenhuma mensagem de pedido recusado. No caso C, os dois extremos do intervalo foram aceites e o 51 foi recusado. No caso D, o total ficou em 0 mesmo havendo um pedido, porque o único pedido foi recusado. O conjunto destes quatro casos, com os resultados previstos e os obtidos, é o conjunto de testes do algoritmo, e faz parte da evidência do bloco.

## Erros comuns

Os erros desta secção são versões erradas dos algoritmos deste guia. Para cada um vais ver a entrada que o mostra, porque um erro só está bem explicado quando se consegue mostrar a entrada que o revela.

### A sentinela tratada como um pedido

Se, no exemplo dos pedidos, a leitura passar para o princípio do corpo, sem leitura antecipada, e a quantidade começar com um valor inventado:

```text
    quantidade ← 1
    ENQUANTO quantidade != SENTINELA FAZER
        ESCREVER "Quantidade do pedido (0 para terminar)?"
        LER quantidade
        SE quantidade >= QUANTIDADE_MINIMA E quantidade <= CAPACIDADE_MAXIMA ENTÃO
```

com o resto do corpo igual, então o 0 é lido e passa pelo `SE` antes de a condição do ciclo o poder testar. Como 0 não está entre 1 e 50, é contado como pedido recusado. No caso A, o algoritmo escreve "Pedido recusado: 0 unidades" e diz que houve 3 pedidos recusados, quando foram 2. A entrada que o mostra é qualquer uma, porque todas acabam com o 0. É o mesmo erro que viste no padrão sentinela, agora a aparecer no contador dos recusados.

### O contador fora do SE

Se o aumento de `pedidosValidos` ficar no corpo do ciclo, mas antes do `SE`:

```text
    ENQUANTO quantidade != SENTINELA FAZER
        pedidosValidos ← pedidosValidos + 1
        SE quantidade >= QUANTIDADE_MINIMA E quantidade <= CAPACIDADE_MAXIMA ENTÃO
            totalUnidades ← totalUnidades + quantidade
        SENÃO
```

então o contador conta todos os pedidos, e não só os válidos. No caso A, diz que houve 5 pedidos válidos, quando foram 3. A entrada que o mostra é qualquer uma com um pedido recusado. O caso D, com um único pedido recusado, mostra-o de forma mais clara: diz que houve 1 pedido válido e ao mesmo tempo 1 recusado, de um único pedido. Uma instrução de contar só conta o que queres se estiver dentro do `SE` que o escolhe.

### A leitura esquecida no fim do corpo

Se faltar a leitura da quantidade seguinte no fim do corpo, a quantidade nunca muda. Com o caso A:

| Teste | quantidade | pedidosValidos | pedidosRecusados | totalUnidades | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| 1.º | 12 | 0 | 0 | 0 | `12 != 0` é VERDADEIRO | nada |
| 2.º | 12 | 1 | 0 | 12 | `12 != 0` é VERDADEIRO | nada |
| 3.º | 12 | 2 | 0 | 24 | `12 != 0` é VERDADEIRO | nada |
| 4.º | 12 | 3 | 0 | 36 | `12 != 0` é VERDADEIRO | nada |

E assim para sempre. Este ciclo infinito é mais traiçoeiro do que o das senhas, porque o estado não se repete: os válidos e o total aumentam em cada iteração. Quem olhar só para essas colunas vê o algoritmo "a trabalhar". Mas a coluna que decide o ciclo é a da quantidade, que é a variável da condição, e essa está sempre em 12. A pergunta das três peças apanha o erro: em cada iteração, a variável da condição muda? Não. Então o ciclo é infinito.

### Uma iteração a mais ou a menos

No algoritmo das senhas, com `ENQUANTO senha < ULTIMA_SENHA` em vez de `<=`, o ciclo faz uma iteração a menos: escreve a senha 1 e a senha 2 e para, porque `3 < 3` é falso. Com `senha ← 0` na inicialização, faz uma iteração a mais, e a primeira senha impressa é a senha 0, que não existe. Estes erros não tornam o ciclo infinito, e por isso passam despercebidos a quem só verifica se o ciclo acaba.

A forma de os apanhar é contar. Antes de fazeres o trace, diz quantas iterações o ciclo devia ter e quais são o primeiro e o último valor da variável. Depois confirma na tabela de iterações. A primeira e a última iteração são as fronteiras de um ciclo, e é lá que estes erros se escondem, tal como os erros de decisão se escondem nas fronteiras de um intervalo.

### A condição de paragem no lugar da condição de continuação

Se, na validação repetida, alguém escrever a condição de valor válido em vez da de valor inválido:

```text
    ENQUANTO quantidade >= QUANTIDADE_MINIMA E quantidade <= CAPACIDADE_MAXIMA FAZER
```

o algoritmo faz o contrário do que devia. Quando a pessoa escreve 12, que é válido, aparece "Quantidade inválida" e o algoritmo pede outro valor. Se a pessoa escrever depois 30, pede outra vez. Se escrever 0, o ciclo termina e aparece "Pedido aceite: 0 unidades". O ciclo recusa os valores bons e aceita o primeiro valor mau. A condição do `ENQUANTO` descreve quando continuar: numa validação, continua-se enquanto o valor for inválido.

### O valor inicial errado ou esquecido

Um contador ou um totalizador sem inicialização obriga o algoritmo a somar a uma variável sem valor. Um contador inicializado a 1 dá sempre uma unidade a mais, e diz que houve um pedido num dia sem pedidos. Uma inicialização dentro do ciclo apaga o que foi contado nas iterações anteriores. O caso de zero voltas apanha os dois primeiros erros; uma entrada com dois ou mais valores apanha o terceiro.

### A seta de volta no sítio errado

No fluxograma, a seta de volta tem de chegar ao losango da condição. Se chegar à inicialização, as variáveis voltam ao valor inicial em cada iteração. No exemplo dos pedidos, com o caso A, os contadores voltam a zero em cada iteração, e a leitura antecipada repete-se logo a seguir à leitura do fim do corpo: o 60, o -4 e o próprio 0 são lidos e logo substituídos pelo valor seguinte, sem nunca chegarem ao losango. O algoritmo continua a pedir quantidades depois de o funcionário ter escrito 0. Se a seta chegar a uma figura que está depois do losango, a condição nunca mais é avaliada, e o ciclo nunca acaba. Confirma sempre: a seta que sobe termina no losango, e o losango tem uma saída `Sim` e uma saída `Não`.

### Testar só o caso normal

Todos os erros desta secção têm uma coisa em comum: vários deles não aparecem se testares só com o caso A. O contador inicializado a 1 aparece com o caso B. A iteração a menos aparece quando se contam as iterações. A sentinela contada como dado aparece em qualquer caso, mas só se olhares para os recusados. Os casos de teste de um ciclo escolhem-se assim: o caso de zero voltas, um caso com uma só volta, um caso com várias voltas, e os valores de fronteira das decisões que estão dentro do ciclo.

## Prática guiada (60 min)

A prática guiada deste bloco é feita no computador, no [laboratório](04-repeticao-e-padroes-laboratorio.md). Vais desenhar no diagrams.net o fluxograma do exemplo dos pedidos, aprender a desenhar a seta que volta ao losango sem cruzar as outras setas, e verificar o desenho percorrendo-o com um caso de teste. O laboratório pressupõe que já fizeste os laboratórios dos blocos 02 e 03, e remete para este guia sempre que precisares de rever uma ideia.

## Consolidação (60 min)

Um ciclo repete o seu corpo enquanto a condição for verdadeira, e tem três peças: a inicialização, antes do ciclo, que dá os valores de partida; a condição, que diz quando continuar; e a atualização, dentro do corpo, que muda a variável da condição na direção da saída. Se a condição for falsa logo no início, o ciclo tem zero iterações; se a atualização faltar ou andar no sentido errado, o ciclo nunca acaba. O `PARA` é a forma curta do ciclo contado, com as três peças no cabeçalho. O contador soma 1, o totalizador soma o valor, a sentinela marca o fim de uma sequência de dados e nunca é tratada como dado, e a validação repetida pede um valor até ele ser válido. A tabela de iterações, com uma linha por teste da condição, mostra como o estado muda de iteração em iteração.

### 1. Justifica as três peças (15 min)

Sem olhares para o passo 4 do exemplo, responde por escrito às três perguntas das peças para o algoritmo `ContarPedidosValidos`.

**a)** Com que valores começa o ciclo, e porquê?

**b)** Em que situação continua, e quando é que deixa de continuar?

**c)** O que muda em cada iteração, e porque é que isso aproxima o fim?

**d)** Explica a um colega, por palavras tuas, porque é que a quantidade é lida em dois sítios diferentes do algoritmo.

Se conseguires justificar as três peças sem hesitar, o checkpoint do bloco está cumprido.

### 2. Ordena as fotografias do estado (15 min)

O funcionário da papelaria usou o algoritmo `ContarPedidosValidos` e escreveu quatro quantidades e, no fim, a sentinela. As fotografias seguintes mostram o estado no momento de cada teste da condição do ciclo, mas foram baralhadas, e uma delas não pode ter acontecido.

| Fotografia | quantidade | pedidosValidos | pedidosRecusados | totalUnidades |
| --- | ---: | ---: | ---: | ---: |
| A | 40 | 1 | 1 | 8 |
| B | 40 | 0 | 1 | 8 |
| C | 8 | 0 | 0 | 0 |
| D | 0 | 2 | 2 | 48 |
| E | 55 | 1 | 0 | 8 |
| F | -3 | 2 | 1 | 48 |

**a)** Ordena as fotografias verdadeiras, do 1.º ao último teste.

**b)** Para cada passagem de uma fotografia para a seguinte, diz qual foi a quantidade tratada nessa iteração e que ramo do `SE` foi executado.

**c)** Descobre a fotografia impossível e explica, com as regras do algoritmo, porque é que ela nunca pode aparecer, seja qual for a quantidade escrita.

**d)** Escreve as quantidades que o funcionário escreveu, pela ordem, incluindo a sentinela.

### 3. Encontra o erro (15 min)

Um colega escreveu este algoritmo para um balcão de atendimento. O funcionário escreve a duração de cada atendimento, em minutos, e escreve 0 quando fecha o balcão. O algoritmo devia dizer quantos clientes foram atendidos e quantos minutos durou o atendimento ao todo.

```text
ALGORITMO ContarClientesAtendidos
CONSTANTES
    SENTINELA ← 0
VARIÁVEIS
    minutos: inteiro
    clientes: inteiro
    totalMinutos: inteiro
INÍCIO
    clientes ← 1
    totalMinutos ← 0
    ESCREVER "Minutos do atendimento (0 para fechar o balcão)?"
    LER minutos
    ENQUANTO minutos != SENTINELA FAZER
        clientes ← clientes + 1
        totalMinutos ← totalMinutos + minutos
        ESCREVER "Minutos do atendimento (0 para fechar o balcão)?"
        LER minutos
    FIM ENQUANTO
    ESCREVER "Clientes atendidos: ", clientes
    ESCREVER "Tempo total: ", totalMinutos, " minutos"
FIM
```

**a)** Faz a tabela de iterações com as durações 5 e 8, seguidas do 0. O que aparece no ecrã no fim, e o que devia aparecer?

**b)** Faz a tabela de iterações com o 0 sozinho. O que aparece no ecrã no fim, e o que devia aparecer?

**c)** Diz qual das três peças está errada e corrige a linha. Confirma que, com a correção, os dois casos dão o que devia aparecer.

**d)** Qual dos dois casos de teste mostra o erro de forma mais clara? Responde numa frase, e diz porquê.

### 4. Regista as tuas dificuldades (15 min)

Escreve duas ou três linhas sobre o que te custou mais neste bloco: perceber quando o ciclo volta atrás, fazer a tabela de iterações, escolher entre `ENQUANTO` e `PARA`, ou a leitura antecipada da sentinela. Guarda-as com a evidência.

**Evidência a guardar:** a tabela de iterações e o conjunto de testes do exemplo explicado, refeitos por ti sem olhar; o fluxograma desenhado no laboratório; as respostas às tarefas 1 a 3 desta consolidação; e as tuas notas de dificuldade.

## Verificar o que aprendeste

Usa esta lista para te testares. Para cada ponto, experimenta fazê-lo sem olhar para o guia. Se não conseguires, volta à secção correspondente.

- Consegues explicar por palavras tuas o que acontece quando o algoritmo chega ao `FIM ENQUANTO`.
- Consegues identificar, num ciclo que não escreveste, a inicialização, a condição e a atualização, e responder às três perguntas das peças.
- Consegues fazer o trace linha a linha de um ciclo curto e depois a tabela de iterações do mesmo ciclo, e mostrar que dizem o mesmo.
- Consegues dizer, antes de fazeres o trace, quantas iterações um ciclo vai ter e com que valor fica a variável da condição depois de ele terminar.
- Consegues mostrar, com uma tabela de iterações, porque é que um ciclo nunca acaba, e dizer qual das peças está errada.
- Consegues dar um exemplo de um ciclo com zero iterações que está errado e outro que está certo.
- Consegues reescrever um `PARA` como `ENQUANTO`, e dizer onde ficaram as três peças.
- Consegues explicar a diferença entre um contador e um totalizador, e porque é que ambos começam em 0 e fora do ciclo.
- Consegues escrever um ciclo com sentinela, com a leitura antecipada, e explicar porque é que a sentinela nunca é tratada como dado.
- Consegues escrever uma validação repetida e dizer o que se sabe sobre o valor depois do `FIM ENQUANTO`.
- Consegues escolher entre `ENQUANTO` e `PARA` para um problema novo e justificar a escolha com a pergunta certa.
- Consegues desenhar um ciclo em fluxograma, com a seta de volta a chegar ao losango da condição.
- Consegues escolher os casos de teste de um ciclo: o caso de zero voltas, um caso com uma só volta, um caso com várias voltas e as fronteiras.

## A seguir

O [laboratório](04-repeticao-e-padroes-laboratorio.md) ocupa 60 minutos e a [ficha de exercícios](04-repeticao-e-padroes-exercicios.md) os restantes 120. No bloco seguinte, o último desta área, vais juntar a sequência, a seleção e a repetição num problema maior, testá-lo de forma organizada, corrigir erros encontrados no trace e comparar duas soluções pelo número de passos. Mais tarde, em Python, os ciclos `ENQUANTO` passam a chamar-se `while`, e as tabelas de iterações que aprendeste a fazer aqui vão servir para prever o que o programa vai fazer antes de o executares.

## Referências

Unidade de competência UC00245, *Desenvolver algoritmos*, do referencial de Técnico/a de Informática de Gestão (481RA117), nível 4. A ficha oficial da unidade pode ser consultada no [Catálogo Nacional de Qualificações](https://catalogo.snq.gov.pt/ucDetalhe/355272).

![Rodapé](../imagens/rodape.png)
