![Cabeçalho](../imagens/cabecalho.png)

# Pseudocódigo e fluxogramas

Módulo Desenvolver algoritmos. Neste guia aprendes a escrever algoritmos em pseudocódigo, com variáveis, tipos de dados, contas e funções predefinidas. Aprendes também a reconhecer o mesmo algoritmo num fluxograma e a segui-lo à mão, numa tabela de trace. Lês o guia ao teu ritmo, de preferência em mais do que uma vez. Para praticar, há a [ficha de exercícios](02-pseudocodigo-e-fluxogramas-exercicios.md) e o [laboratório](02-pseudocodigo-e-fluxogramas-laboratorio.md) deste tema, que é de fluxogramas e só se faz quando o professor o indicar.

No guia 01 escreveste algoritmos em português, em passos numerados. Neste guia, o estado ganha nomes, as variáveis, e os passos ganham uma escrita própria. É a forma que o professor usa no quadro, e vais encontrá-la igual em todos os guias de algoritmos. Se já escreveste na aula as primeiras instruções em pseudocódigo, vais reconhecê-la, e aqui fica o porquê de cada peça. Todos os algoritmos deste guia são sequenciais: fazem sempre os mesmos passos, pela mesma ordem, seja qual for a entrada. Escolher entre caminhos é o assunto do guia 03, e repetir passos é o do guia 04.

Para estudares este guia, tem à mão papel quadriculado e lápis, porque os traces se fazem à mão. Os fluxogramas que aqui aparecem são para saberes o que são e como se leem. Desenhá-los, no papel ou numa aplicação, é opcional, e só o fazes quando o professor o indicar. Nenhum exercício obrigatório precisa de um fluxograma desenhado.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Uma notação própria para algoritmos
4. Variáveis e estado
5. Constantes
6. Tipos de dados
7. Onde nasce uma variável, e com que tipo
8. Atribuição: dar um valor não é perguntar se é igual
9. Ler e escrever
10. Expressões aritméticas
11. Funções predefinidas
12. Sequência
13. A forma do pseudocódigo nas aulas
14. Os símbolos do fluxograma
15. A tabela de trace
16. Exemplo guiado: as caixas de cadernos
17. Um segundo exemplo guiado, mais curto: o desconto ao cêntimo
18. Erros frequentes
19. Palavras novas deste guia
20. Verificar o que aprendeste
21. O que vem a seguir
22. Para saber mais

## O que vais aprender

No fim deste guia, consegues:

- explicar o que são uma variável, uma constante e o estado de um algoritmo, e escrever cada variável com o tipo onde ela nasce;
- escolher o tipo de cada valor, `int`, `float`, `string` ou `bool`, pelo que vais fazer com ele, e justificar a escolha;
- distinguir dar um valor a uma variável, com `=`, de perguntar se dois valores são iguais, com `==`;
- ler dados, mostrar resultados e fazer contas com `div`, `resto`, `/` e as quatro funções predefinidas, sem cair nos casos que enganam;
- escrever um algoritmo sequencial completo, em pseudocódigo ou em frases claras que não deixem dúvidas, e reconhecê-lo num fluxograma, figura a figura;
- prever o resultado de um algoritmo e confirmá-lo numa tabela de trace, instrução a instrução.

## O que já sabes e vais usar

- O contrato de um problema: guia [01 Do problema ao algoritmo](01-do-problema-ao-algoritmo.md), secção "O contrato do problema: entradas, saídas, restrições e condições".
- Os exemplos concretos, cada um com o resultado esperado, calculado à mão: guia [01](01-do-problema-ao-algoritmo.md), na mesma secção.
- A decomposição de um problema em subproblemas, que se resolvem e verificam um a um: guia [01](01-do-problema-ao-algoritmo.md), secção "Decompor um problema em subproblemas".
- A ação e o estado, e seguir o estado numa tabela, com uma coluna para cada valor: guia [01](01-do-problema-ao-algoritmo.md), secção "Ação e estado".
- As instruções ambíguas, que admitem mais do que uma leitura: guia [01](01-do-problema-ao-algoritmo.md), secção "Instruções ambíguas".
- As quatro operações, a divisão com resto e a ordem das operações numa conta, da matemática do ensino básico.
- As percentagens e as médias, da matemática do ensino básico.

## Uma notação própria para algoritmos

No guia 01 escreveste algoritmos em português, em passos numerados. Funcionou, mas viste o problema. O português deixa passar ambiguidades sem dar sinal. "Esperar um pouco" parece uma instrução e não é. Duas pessoas diferentes esperam tempos diferentes, e nenhuma delas está a desobedecer.

Uma linguagem de programação, como o Python que vais aprender a seguir, não tem esse problema, porque cada instrução tem um único significado. Mas tem outro, para quem está a começar. Obriga a respeitar regras de escrita muito rígidas, e um parêntese esquecido impede o programa de funcionar, mesmo que o raciocínio esteja certo. Quem começa por aí gasta a atenção na pontuação, e não no problema.

Existem duas formas de escrever algoritmos a meio caminho entre o português e uma linguagem de programação. Vais aprender as duas, porque servem para coisas diferentes.

O **pseudocódigo** é texto escrito com um vocabulário pequeno, umas poucas palavras e sinais que usamos sempre com o mesmo significado. A palavra "pseudo" quer dizer "falso" ou "parecido com". O pseudocódigo parece código, mas não é código de nenhuma linguagem, e nenhum computador o executa. Serve para pensar. Com ele escreves depressa, a tua atenção fica no raciocínio e não na pontuação, e quem lê percebe logo o que cada linha faz.

O **fluxograma** é um desenho do mesmo algoritmo, com figuras ligadas por setas. Mostra o caminho de um relance. Serve para explicar um processo a quem não programa, como alguém da contabilidade que quer saber como se calcula um desconto.

O mesmo algoritmo escreve-se das duas maneiras. Se as duas versões não disserem exatamente a mesma coisa, pelo menos uma delas está errada.

Há uma terceira maneira, que já conheces do guia 01 e que continua a valer: escrever o algoritmo em frases claras, em português. O que é preciso é que as frases não deixem dúvidas. A secção "A forma do pseudocódigo nas aulas", mais à frente, explica o que isso quer dizer e mostra um exemplo. Neste momento, o que conta é a lógica do algoritmo. A forma de escrever é uma ajuda para pensares e para te fazeres entender, e não uma lista de regras em que se pode errar.

## Variáveis e estado

Uma **variável** é um espaço com um nome, onde se guarda um valor que pode mudar enquanto o algoritmo é executado.

A imagem mais usada é a de uma caixa com uma etiqueta. A etiqueta é o nome, e nunca muda. O conteúdo é o valor, e pode ser trocado. Quando se guarda um valor novo na caixa, o antigo sai. Uma variável guarda um valor de cada vez, nunca dois, e o valor antigo não fica guardado em lado nenhum.

No dia a dia, o visor de uma balança de loja funciona assim. Há sempre um visor, no mesmo sítio e com a mesma função. O número que lá aparece muda cada vez que se pousa outra coisa no prato, e o número anterior desaparece.

No guia 01, o estado de uma fila de atendimento era uma fotografia. Por exemplo, "está a ser atendida a senha 14 e há 6 pessoas à espera". Com variáveis, cada parte dessa fotografia passa a ter nome próprio. `senhaAtual` vale 14, e `pessoasAEspera` vale 6. A definição de estado fica assim mais precisa. O **estado** de um algoritmo, num dado momento, é o valor de todas as suas variáveis nesse momento.

Cada instrução que muda o valor de uma variável muda o estado. Se quiseres saber o que um algoritmo está a fazer, não precisas de adivinhar. Olhas para o estado antes de uma instrução, olhas para o estado depois, e a diferença é o efeito dessa instrução. É esta a ideia da tabela de trace, que vais aprender neste guia.

Uma variável só existe a partir da linha do algoritmo onde aparece pela primeira vez, e nessa linha recebe logo o seu primeiro valor. Antes dessa linha, é como uma caixa que ainda ninguém etiquetou nem encheu. Nas tabelas deste guia, esse estado escreve-se "sem valor". Perguntar o que está dentro de uma caixa que ainda não recebeu nada não dá nenhuma resposta útil. Por isso, usar uma variável antes de ela receber um valor é um erro. É dos mais frequentes, e está explicado nos erros frequentes, no fim deste guia.

O nome de uma variável deve dizer o que ela guarda. `caixasCompletas` é um bom nome. `x`, `aux` ou `numero2` não são. Daqui a uma semana nem tu te lembras do que lá estava, e quem ler o teu algoritmo tem de adivinhar. Nos algoritmos desta disciplina, os nomes das variáveis escrevem-se assim, para toda a gente os ler da mesma maneira:

- começam por uma letra minúscula;
- não têm espaços. Quando têm várias palavras, juntam-se, e cada palavra a partir da segunda começa por maiúscula, como em `caixasCompletas` ou `precoEmCentimos`. Esta forma de escrever chama-se **camelCase**, porque as maiúsculas no meio lembram as bossas de um camelo;
- não têm acentos nem cedilhas, porque as linguagens de programação nem sempre os aceitam nos nomes, e é melhor habituares-te desde já. Escreve-se `preco` e não `preço`, e `numeroDeCaixas` e não `númeroDeCaixas`.

Há ainda uma regra sobre as palavras que o próprio pseudocódigo usa. Está na secção "A forma do pseudocódigo nas aulas", depois de essas palavras aparecerem.

## Constantes

Uma **constante** é um valor com nome que não muda durante a execução do algoritmo.

Há valores que fazem parte das regras do problema, e não dos dados. Uma caixa do fornecedor leva 12 cadernos, um dia tem 24 horas e uma loja distribui no máximo 40 senhas. Podias escrever o número diretamente nas contas, mas dar-lhe um nome traz duas vantagens.

A primeira é que se percebe o que o número significa. `UNIDADES_POR_CAIXA` diz muito mais do que um 12 solto no meio de uma conta. Esse 12 tanto podia ser o número de meses do ano como a idade de alguém.

A segunda é que, se a regra mudar, muda-se num sítio só. Se o fornecedor passar a entregar caixas de 24, altera-se a linha da constante e o resto do algoritmo fica igual. Sem a constante, terias de andar à procura de todos os 12 espalhados pelo texto. Corrias o risco de esquecer um, ou de mudar um 12 que afinal não era o das caixas. Um número escrito à mão em vários sítios do algoritmo é o sinal deste problema.

As constantes escrevem-se em maiúsculas, com as palavras separadas por um traço baixo, como `UNIDADES_POR_CAIXA`. A forma diferente serve para as distinguires das variáveis à primeira vista. Quando, a meio de uma conta, vês um nome todo em maiúsculas, sabes logo que é um valor fixo.

Uma constante cria-se numa linha própria, no início do algoritmo, antes de ser usada, com a palavra `const` à frente:

```text
const UNIDADES_POR_CAIXA = 12
```

Lê-se "a constante UNIDADES_POR_CAIXA vale 12". A palavra `const` é o princípio da palavra "constante", e avisa quem lê de que aquele valor não vai mudar. A constante recebe o valor nessa linha e nunca mais. Uma instrução que tente dar-lhe outro valor a meio do algoritmo está errada, porque ela deixava de ser constante.

Repara que a constante não leva tipo. Não é preciso, porque o tipo vê-se pelo valor. `12` é um número inteiro, e `"Papelaria"` é um texto. `0.23` é um número com parte decimal, escrito com um ponto no lugar da vírgula, como nas linguagens de programação. Os nomes dos tipos vêm já a seguir.

## Tipos de dados

Cada variável guarda valores de um **tipo**, e o tipo decide que valores são possíveis e o que se pode fazer com eles. Nesta disciplina usam-se quatro tipos, com os nomes curtos que o professor usa no quadro:

| Tipo | Guarda | Exemplos | O que se faz com ele |
| --- | --- | --- | --- |
| `int` | números inteiros, sem parte decimal | `12`, `0`, `-3` | contas, incluindo a divisão inteira |
| `float` | números com parte decimal | `1.5`, `0.75`, `-2.25` | contas em que a parte decimal interessa |
| `string` | texto: sequências de caracteres, entre aspas | `"Ana"`, `"caderno A4"` | mostrar e guardar; não se fazem contas |
| `bool` | só um de dois valores | `true`, `false` | guardar a resposta a uma pergunta de sim ou não |

Os nomes vêm do inglês, que é a língua das linguagens de programação, e cada um tem uma razão de ser. `int` é o princípio de *integer*, que quer dizer inteiro. `float` vem de *floating point*, "vírgula flutuante", o nome da forma como o computador guarda os números com parte decimal. `string` quer dizer "fio" ou "cordão". Um texto é uma fila de caracteres enfiados uns atrás dos outros, como as contas de um colar. `bool` vem do apelido de George Boole, um matemático inglês do século XIX que estudou a lógica do verdadeiro e do falso. Não precisas de decorar estas origens. Servem só para te lembrares do que cada nome quer dizer. E vais reencontrar os nomes, porque em Python os tipos chamam-se `int`, `float`, `str` e `bool`, e só o do texto muda.

Repara que, no pseudocódigo, a parte decimal de um número se separa com um ponto, `1.5`, tal como nas linguagens de programação. No texto em português continua a escrever-se com vírgula, 1,5. São dois hábitos para dois contextos, e não se misturam. Dentro do pseudocódigo e das tabelas de trace, que mostram valores do algoritmo, usa-se o ponto. No texto que escreves à volta, usa-se a vírgula.

Escolher o tipo é uma decisão com consequências. Decide-se pelo que o valor representa e pelo que vais fazer com ele, e não pelo aspeto que tem.

Um número de caixas, de alunos ou de senhas é um `int`, porque não existem 2,5 caixas. Um peso em quilogramas, uma média de notas ou uma temperatura são `float`, porque a parte decimal tem significado. O nome de um cliente ou a descrição de um artigo são `string`. A resposta a uma pergunta de sim ou não, como "a encomenda já foi paga?", é um `bool`.

O dinheiro merece uma nota à parte. Um preço como 3,49 euros tem parte decimal, e podia ser um `float`. Nesta disciplina, e na maior parte dos programas de gestão, prefere-se guardar o dinheiro em cêntimos, como um `int`: 3,49 euros são 349 cêntimos. A razão vais percebê-la melhor em Python. Os computadores guardam muitos números com parte decimal com pequenos erros de aproximação. Num valor em dinheiro, um erro de um cêntimo não é aceitável. Com cêntimos inteiros, as somas e as multiplicações dão sempre o valor exato.

Há valores que parecem números e devem ser texto. Um número de telefone, como 912345678, só tem algarismos, mas ninguém soma dois números de telefone nem calcula metade de um. Além disso, um número guardado como número perde os zeros à esquerda e não aceita um sinal de mais no início. E muitos números de telefone escrevem-se com o indicativo do país, como +351. Por isso, um número de telefone é uma `string`. A pergunta que resolve a dúvida é sempre a mesma: vou fazer contas com este valor? Se a resposta for não, é quase sempre uma `string`.

A confusão mais frequente é entre o número `12` e o texto `"12"`. No papel parecem iguais, e não são. Com o número podes fazer contas. O texto é uma sequência de dois caracteres, o 1 e o 2, tal como `"ab"` é uma sequência de duas letras. Juntar o texto `"12"` com o texto `"3"` dá `"123"`, e não 15, porque juntar textos é pô-los um a seguir ao outro. São as aspas que distinguem os dois: com aspas é texto, e sem aspas é um número ou o nome de uma variável.

O tipo `bool` só tem dois valores possíveis, que se escrevem `true` e `false`, as palavras inglesas para verdadeiro e falso, em minúsculas. Serve para guardar respostas a perguntas de sim ou não. Uma variável `pago`, do tipo `bool`, com o valor `false`, guarda que uma encomenda ainda não foi paga. Em Python, estes dois valores escrevem-se com maiúscula, `True` e `False`, e é uma das pequenas diferenças que vais encontrar quando lá chegares. Neste guia vais usar o `bool` pouco. No guia seguinte, quando o algoritmo tiver de tomar decisões, passa a aparecer em quase todos os algoritmos.

Quando uma conta mistura um `int` e um `float`, o resultado é um `float`: `2 + 0.5` dá `2.5`. E há uma operação que dá sempre um `float`, mesmo quando os dois números são inteiros. É a divisão com `/`, porque uma divisão pode dar parte decimal, como 7 a dividir por 2, que dá 3,5.

## Onde nasce uma variável, e com que tipo

Uma variável tem de existir antes de ser usada. Dizer que ela existe, de que tipo é e com que valor começa chama-se **declarar** a variável. No pseudocódigo das aulas, declara-se na linha onde a variável aparece pela primeira vez, com o tipo escrito à frente do nome:

```text
int caixas = 5
```

Lê-se "nasce a variável `caixas`, do tipo `int`, e recebe 5". O sinal `=` quer dizer "recebe": o valor que está à direita vai para a variável que está à esquerda. A secção seguinte é toda sobre ele.

Depois de nascer, a variável usa-se só pelo nome, sem o tipo. Antes de leres a explicação, tenta prever: com que valor fica `total` depois destas duas linhas?

```text
int total = 0
total = total + 5
```

`total` fica com 5.

Leitura guiada: a primeira linha faz nascer `total`, do tipo `int`, com o valor 0. A segunda já não leva `int`, porque `total` já existe, e só lhe muda o valor. Soma 5 ao 0 que lá estava. O tipo escreve-se uma única vez, na linha onde a variável nasce. Se o escrevesses outra vez, como em `int total = total + 5`, quem lesse ficava a pensar que tinha nascido uma segunda variável com o mesmo nome. Quando vires o tipo escrito numa variável que já nasceu mais acima, tira-o.

Escrever o tipo à frente do nome pode parecer uma formalidade. Tem três razões.

A primeira é que te obriga a pensar no valor antes de o usares. Quando escreves `int` à frente de `caixasCompletas`, estás a decidir que aquela caixa só guarda números inteiros. É outra vez o contrato a trabalhar. As entradas e as saídas do contrato aparecem quase sempre como variáveis, e o contrato já disse que valores podem ter.

A segunda é que o tipo fica à vista de quem lê. Quem lê `int caixasCompletas` fica a saber que ali nunca vai aparecer 2,5 caixas. Se aparecer, há um erro, e sabes onde o procurar. E se, mais abaixo no algoritmo, quiseres saber de que tipo é `caixasCompletas`, procuras a linha onde ela nasce, e está lá escrito.

A terceira é que ajuda a apanhar erros de escrita. Se `cadernos` nasceu numa linha e mais abaixo aparece `caderno`, sem o s, esse nome não nasceu em lado nenhum. Quem revir o algoritmo dá logo pelo engano, porque está a ser usada uma variável que não existe.

Porque é que a variável nasce onde aparece pela primeira vez, e não numa lista no topo do algoritmo? Porque assim cada coisa aparece quando faz falta. Lês o algoritmo de cima para baixo e, em cada linha, tens à frente tudo o que precisas para a perceber. Não tens de voltar ao princípio para consultar uma lista. Há livros e professores que escrevem todas as variáveis numa lista antes da primeira instrução. Essa forma também está certa. Nas aulas usamos esta, que é também a das linguagens de programação que vais aprender.

Algumas linguagens de programação obrigam a escrever o tipo de cada variável quando ela nasce. Outras não obrigam, como o Python, onde se escreve só `total = 0` e o tipo fica decidido pelo valor. Nas aulas escrevemos o tipo, porque escolhê-lo faz parte do raciocínio, e não só da escrita.

## Atribuição: dar um valor não é perguntar se é igual

Esta é a distinção mais importante do tema, e a que mais vezes se troca no início. No fim deste guia, tens de a conseguir explicar sem hesitar.

**Atribuir** é dar um valor a uma variável. No pseudocódigo das aulas escreve-se com um sinal de igual, `=`, com a variável à esquerda e o valor à direita:

```text
caixas = 5
```

Lê-se "caixas recebe 5", ou "caixas fica com 5". É uma ordem, e não uma pergunta. A partir deste momento, `caixas` vale 5, seja qual for o valor que tinha antes. Esta linha não tem `int` à frente porque, neste exemplo, `caixas` já tinha nascido mais acima. Na linha onde nasceu, a atribuição era a mesma, com o tipo à frente.

Cuidado com a leitura. Em matemática, x = 3 é uma afirmação: diz que x e 3 são a mesma coisa, agora e sempre. Num algoritmo, `caixas = 5` é uma ordem, executada num certo momento, que guarda um valor numa caixa. Se mais abaixo outra linha mandar `caixas = 8`, a caixa passa a ter 8, e ninguém se contradisse. Por isso, sempre que vires um `=` sozinho, lê "recebe".

A atribuição executa-se sempre em duas fases, por esta ordem. Primeiro calcula-se o lado direito do `=`, com os valores que as variáveis têm nesse momento. Depois guarda-se o resultado na variável do lado esquerdo, e o valor antigo dessa variável perde-se.

Antes de leres a explicação, tenta prever: com que valor fica `total` depois destas duas linhas?

```text
int total = 10
total = total + 5
```

`total` fica com 15.

Leitura guiada: se lesses a segunda linha como em matemática, "total é igual a total mais 5", seria uma afirmação impossível. Nenhum número é igual a ele próprio mais cinco. Lida como atribuição, faz todo o sentido. Calcula-se o lado direito com o valor atual de `total`, que é 10, e dá 15. Guarda-se 15 em `total`. No fim, `total` vale 15, e o 10 desapareceu. Esta forma, com a mesma variável dos dois lados do `=`, vai ser das mais usadas no guia 04, para contar e para somar.

Há duas consequências da atribuição que apanham muita gente, e veem-se melhor com números, numa tabela. Para veres o efeito de cada linha, usa-se uma tabela com uma coluna por variável e uma linha por instrução. Em cada linha fica o valor das variáveis depois dessa instrução. A linha do passo 0, antes de começar, tem "sem valor" em todas, porque nenhuma variável nasceu ainda. A última coluna, Ecrã, diz o que aparece no ecrã. Aqui fica "nada", porque nenhuma destas instruções escreve. A esta tabela chama-se tabela de trace, e a secção "A tabela de trace", mais abaixo, ensina a construí-la passo a passo.

A primeira consequência é que a atribuição copia um valor, e não cria uma ligação. Se já usaste uma folha de cálculo, sabes que uma célula com uma fórmula muda sozinha quando mudas as células de que ela depende. Uma variável não funciona assim. No exemplo seguinte, o `*` é o sinal de multiplicar. Antes de leres a tabela, tenta prever: quanto vale `total` no fim destas três linhas?

```text
int quantidade = 4
int total = quantidade * 250
quantidade = 6
```

| Passo | Instrução executada | quantidade | total | Ecrã |
| ---: | --- | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | nada |
| 1 | `int quantidade = 4` | 4 | sem valor | nada |
| 2 | `int total = quantidade * 250` | 4 | 1000 | nada |
| 3 | `quantidade = 6` | 6 | 1000 | nada |

`total` acaba com 1000. No passo 2 calculou-se `4 * 250`, que dá 1000, e guardou-se 1000 em `total`. No passo 3, `quantidade` passou a 6, mas `total` continua em 1000. A conta foi feita uma vez, no passo 2, com o valor que `quantidade` tinha nesse momento, e não volta a ser feita. Se quiseres o total das 6 unidades, tens de escrever outra vez uma linha que faça a conta, depois de mudares a quantidade. Essa linha é `total = quantidade * 250`, agora sem `int`, porque `total` já existe. Quando uma variável não mudou como esperavas, o trace mostra se a atribuição dela voltou a ser executada depois de a outra variável mudar.

A segunda consequência é que o valor antigo se perde mesmo. Imagina que queres trocar os valores de duas variáveis, `a` com 4 e `b` com 9. Antes de leres a tabela, tenta prever: com que valores ficam `a` e `b` depois destas quatro linhas?

```text
int a = 4
int b = 9
a = b
b = a
```

| Passo | Instrução executada | a | b | Ecrã |
| ---: | --- | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | nada |
| 1 | `int a = 4` | 4 | sem valor | nada |
| 2 | `int b = 9` | 4 | 9 | nada |
| 3 | `a = b` | 9 | 9 | nada |
| 4 | `b = a` | 9 | 9 | nada |

As duas ficam com 9. No passo 3, `a` recebe o valor de `b` e passa a valer 9. O 4 perdeu-se. No passo 4, `b` recebe o valor atual de `a`, que já é 9. Quem esperava que os valores trocassem de lugar esqueceu-se de que, depois do passo 3, o 4 já não existe em lado nenhum. Como se escreve uma troca que funcione é uma pergunta da ficha. Pensa no que farias com dois copos cheios, um de sumo e outro de água, se quisesses trocar os líquidos de copo.

Do lado esquerdo do `=` está sempre uma única variável, porque é lá que o valor vai ser guardado. `10 = total` não faz sentido, porque não se pode guardar um valor dentro do número 10. `total + 5 = total` também não, porque não se pode guardar um valor dentro de uma conta. O valor viaja sempre da direita para a esquerda, e vai parar à caixa cujo nome está sozinho à esquerda do `=`. Em alguns livros vais ver a atribuição desenhada com uma seta a apontar para a esquerda, do valor para a variável. A seta mostra esse caminho. É a mesma ideia com outro desenho. Nas aulas usamos o `=`, que é o que vais escrever em Python. Se tiveres dúvidas numa linha, olha para o lado esquerdo do `=`, onde tem de estar uma única variável.

**Comparar** é outra coisa. É perguntar se dois valores são iguais, ou se um é maior do que o outro. O resultado não fica guardado em lado nenhum. É uma resposta, `true` ou `false`, ou seja, um valor do tipo `bool`. No pseudocódigo das aulas, a pergunta "são iguais?" escreve-se com dois sinais de igual seguidos, `==`:

```text
caixas == 5
```

Isto lê-se "caixas é igual a 5?". Antes de continuares, tenta prever a resposta com `caixas` a valer 5, e depois a valer 2. Com 5, a resposta é `true`. Com 2, é `false`. Em nenhum dos casos `caixas` muda de valor, porque perguntar não altera nada. As comparações só são úteis dentro de uma decisão, do tipo "se caixas for igual a 5, faz isto". As decisões são o assunto do guia 03. Por isso, neste guia não vais escrever comparações. Só precisas de as reconhecer, para nunca as confundires com uma atribuição.

A tabela resume a diferença:

| Aspeto | Atribuição | Comparação |
| --- | --- | --- |
| Escreve-se com | `=`, um só sinal | `==`, dois sinais seguidos (e outros sinais, no guia 03) |
| Lê-se | "caixas recebe 5" | "caixas é igual a 5?" |
| É | uma ordem | uma pergunta |
| Muda a variável | sim, guarda um valor novo | não, só a consulta |
| Resultado | a variável fica com o valor novo | `true` ou `false` |
| Do lado esquerdo | sempre uma única variável | qualquer valor ou conta |

Porque é que se usa um sinal para dar um valor e dois para perguntar? Porque é assim nas linguagens de programação. No Python, que vais aprender a seguir, `total = 0` dá o valor 0 a `total`, e `total == 0` pergunta se `total` vale 0, como aqui. Aprender já esta forma poupa-te a desaprender outra mais tarde. O preço é teres de estar atento a um sinal. `total = total + 1` soma 1 a `total`. `total == total + 1` não soma nada. É uma pergunta, e a resposta é sempre `false`. Um sinal a mais transforma uma ordem numa pergunta, e o algoritmo fica com ar de certo sem fazer o que devia. Quando tiveres dúvidas, interpreta a linha por palavras. Se a instrução atribui um valor, "recebe", é um sinal; se compara valores, "é igual a?", são dois.

## Ler e escrever

Um algoritmo recebe dados e produz resultados. As entradas e as saídas do contrato têm, no pseudocódigo, formas próprias de se escrever.

Para receber um valor de fora do algoritmo, normalmente escrito por uma pessoa no teclado, usa-se `ler valor`, do lado direito de uma atribuição:

```text
int cadernos = ler valor
```

Lê-se "nasce a variável `cadernos`, do tipo `int`, e recebe o valor que a pessoa escrever". Ler é uma forma de atribuição. O valor vem de fora e é guardado na variável que está à esquerda do `=`. É por isso que se escreve como uma atribuição. Na primeira vez que a variável aparece, leva o tipo à frente, como em qualquer declaração. Se mais abaixo quiseres ler outro valor para a mesma variável, escreves só `cadernos = ler valor`, e o valor antigo perde-se, como em qualquer atribuição. Em Python vais escrever uma linha com a mesma forma: a variável à esquerda, o `=`, e à direita a instrução que lê.

Cada `ler valor` lê um único valor. Se o algoritmo precisa de dois valores, escreve duas linhas, uma para cada variável.

O valor lido tem de ser do tipo da variável. Se `cadernos` é um `int`, espera-se que a pessoa escreva um número inteiro. Um número que o contrato não aceita, como -5 cadernos, recusa-se com a validação de dados, assunto do guia 03. Uma resposta de outro tipo, como o texto "doze" onde se esperava um número, fica para quando passares para o Python. Por agora, os algoritmos partem do princípio de que quem os usa respeita o contrato.

Para mostrar informação a quem está a usar o algoritmo, usa-se `Escreve:`, seguido do que se quer mostrar. Pode mostrar texto e valores de variáveis, separados por vírgulas. O que está entre aspas aparece tal e qual. O que está sem aspas é o nome de uma variável, ou uma conta, e o que aparece é o seu valor. Os dois pontos a seguir a `Escreve` fazem parte da instrução, como quem diz "escreve o seguinte:", e não aparecem no ecrã.

A diferença entre o que está entre aspas e o que não está é uma fonte clássica de erros. Imagina que `caixas` vale 2. Antes de leres a coluna da direita, tapa-a e tenta prever o que aparece no ecrã com cada instrução.

| Instrução | O que aparece no ecrã |
| --- | --- |
| `Escreve: "caixas"` | caixas |
| `Escreve: caixas` | 2 |
| `Escreve: "Caixas completas: ", caixas` | Caixas completas: 2 |
| `Escreve: "Vão ", caixas, " caixas"` | Vão 2 caixas |
| `Escreve: "Vão", caixas, "caixas"` | Vão2caixas |

A terceira linha tem dois sinais de dois pontos. O primeiro é o de `Escreve:`, e não aparece. O segundo está dentro das aspas, e por isso aparece no ecrã, seguido do espaço que também lá está.

Repara nos espaços dentro das aspas nas duas últimas linhas. Sem eles, as palavras e o número aparecem colados. O algoritmo escreve exatamente o que lhe mandas, incluindo os espaços que te esqueceste de pôr, e nada mais.

Antes de cada `ler valor`, escreve-se quase sempre um `Escreve:` com uma pergunta, para quem está do outro lado saber o que tem de escrever. Uma leitura sem pergunta deixa a pessoa a olhar para um ecrã parado, sem saber que o algoritmo está à espera dela, nem do quê.

## Expressões aritméticas

Uma **expressão** é uma conta escrita no algoritmo, como `cadernos div UNIDADES_POR_CAIXA` ou `artigos * pesoPorArtigo + 200`. É formada por valores, nomes de variáveis e de constantes, e operadores. Um **operador** é o sinal ou a palavra que diz que conta se faz, como o `+` ou o `div`. O lado direito de uma atribuição é sempre uma expressão, mesmo quando é só um número.

Os operadores aritméticos são estes:

| Operador | O que faz | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `+` | soma | `7 + 2` | `9` |
| `-` | subtração | `7 - 2` | `5` |
| `*` | multiplicação | `7 * 2` | `14` |
| `/` | divisão, com parte decimal | `7 / 2` | `3.5` |
| `div` | divisão inteira: quantas vezes cabe | `7 div 2` | `3` |
| `resto` | o que sobra da divisão inteira | `7 resto 2` | `1` |

A multiplicação escreve-se com um asterisco porque o "x" é uma letra e podia ser o nome de uma variável.

`div` e `resto` são as contas de dividir que aprendeste na primária, antes de haver números decimais. Antes de continuares, tenta prever: com 17 cadernos, quantas caixas de 5 se enchem, sem partir caixas nem cadernos, e quantos cadernos sobram? Enchem-se 3 caixas, que levam 15 cadernos, e sobram 2. Em pseudocódigo, `17 div 5` dá `3`, que é o número de caixas cheias, e `17 resto 5` dá `2`, que é o que sobra.

Há uma forma simples de confirmar as duas contas ao mesmo tempo. O divisor vezes a divisão inteira, mais o resto, tem de dar o número de partida. Aqui, 5 vezes 3, mais 2, dá 17. Se não der, uma das contas está errada. E o resto é sempre mais pequeno do que o divisor: se sobrassem 5 ou mais cadernos, cabia mais uma caixa.

Há dois casos que enganam. Quando o número é múltiplo exato do divisor, o resto é zero: `12 resto 12` dá `0`, e `12 div 12` dá `1`. Quando o número é mais pequeno do que o divisor, não cabe nenhuma vez, e sobra tudo: `5 div 12` dá `0` e `5 resto 12` dá `5`. Muita gente responde 7 a esta última, porque faz 12 menos 5. A ordem conta. `5 resto 12` pergunta o que sobra de 5 quando se tiram grupos de 12, e de 5 não se tira nenhum grupo de 12. O número que se divide fica sempre à esquerda, e o divisor à direita. Se tiveres dúvidas, faz a verificação: o divisor vezes o `div`, mais o `resto`, tem de dar o número de partida.

Nesta disciplina, `div` e `resto` usam-se só com números inteiros. O número da esquerda é igual ou maior do que zero, e o divisor é maior do que zero. Com números negativos, as linguagens de programação não estão de acordo sobre o resultado, e não vais precisar deles. Escrevem-se em minúsculas, como as outras palavras que fazem contas. Noutros livros e noutras linguagens vais encontrar o resto escrito como `MOD` ou como `%`. É a mesma operação com outro nome. Em Python, que vais aprender a seguir, a divisão inteira escreve-se `//` e o resto escreve-se `%`.

A divisão com `/` dá o resultado completo, com parte decimal: `7 / 2` dá `3.5`. O resultado de `/` é sempre um `float`, mesmo quando a divisão é exata. `6 / 2` dá `3.0`, e o ponto zero está lá para lembrar que é um `float`. A conta podia ter dado parte decimal, e o algoritmo trata o resultado como tal. Por isso, o resultado de uma divisão com `/` guarda-se numa variável `float`. Também pode passar antes por uma das funções predefinidas que dão um `int`, que vais ver na secção seguinte.

A escolha entre `/` e `div` não é um pormenor. Usa `div` e `resto` quando as quantidades são inteiras e a parte decimal não faz sentido, como caixas, pessoas ou senhas. Usa `/` quando a parte decimal interessa, como numa média ou numa percentagem. Com 30 cadernos e caixas de 12, `30 / 12` dá `2.5`, e 2,5 caixas não existem no armazém. O que interessa é que há 2 caixas cheias e 6 cadernos de fora. Quando tiveres dúvidas, pergunta-te se o resultado pode ter parte decimal.

A ordem das operações é a que conheces da matemática:

1. primeiro o que está entre parênteses;
2. depois as multiplicações e as divisões, incluindo `div` e `resto`;
3. por fim as somas e as subtrações;
4. entre operações do mesmo nível, faz-se da esquerda para a direita.

Antes de leres o raciocínio, calcula tu cada uma destas expressões: `2 + 3 * 4`, `20 - 8 - 2`, `24 / 4 * 2` e `10 + 7 div 2`.

- `2 + 3 * 4` dá `14`. A multiplicação faz-se primeiro, 3 vezes 4 dá 12, e só depois se soma 2. Com parênteses, `(2 + 3) * 4` dá `20`, porque a soma passa à frente.
- `20 - 8 - 2` dá `10`. As duas subtrações estão no mesmo nível e fazem-se da esquerda para a direita: primeiro 20 menos 8, que dá 12, depois 12 menos 2. Quem fizer primeiro 8 menos 2 obtém 14, que é o resultado de outra conta, `20 - (8 - 2)`.
- `24 / 4 * 2` dá `12.0`. A divisão e a multiplicação estão no mesmo nível, e faz-se primeiro 24 a dividir por 4, que dá 6.0, e depois vezes 2. Não é o mesmo que `24 / (4 * 2)`, que dá `3.0`.
- `10 + 7 div 2` dá `13`. O `div` está no nível da multiplicação e faz-se antes da soma: 7 div 2 dá 3, mais 10 dá 13. Com parênteses, `(10 + 7) div 2` dá `8`.

O erro mais frequente com a ordem das operações aparece nas médias. A média de duas notas, 14 e 17, é a soma a dividir por dois: `(14 + 17) / 2` dá `15.5`. Sem parênteses, `14 + 17 / 2` divide só o 17 e dá `22.5`, uma média maior do que as duas notas, o que é impossível. Sempre que queres dividir uma soma, a soma vai entre parênteses. E quando tiveres dúvidas sobre a ordem, põe parênteses, que não custam nada e tiram a dúvida a quem ler. Se uma conta te parecer estranha, calcula-a à mão, pela ordem das operações.

## Funções predefinidas

Uma **função predefinida** é um pedaço de algoritmo que já vem feito, com um nome, pronto a usar. Dás-lhe um valor, entre parênteses, e ela devolve um resultado, que podes usar numa conta ou guardar numa variável. Ao valor que lhe dás chama-se **argumento**.

Pensa numa máquina de venda automática. Não sabes como funciona por dentro, e não precisas. Sabes o que lhe dás, sabes o que ela te devolve, e isso chega para a usar. É o contrato do guia 01 aplicado a um pedaço de algoritmo, com entrada, saída e regras. Para usar uma função predefinida chega-te o contrato dela.

Nesta disciplina existem quatro, e só estas quatro:

| Função | Entrada | O que devolve | Tipo do resultado |
| --- | --- | --- | --- |
| `abs(x)` | um número | o valor absoluto: o número sem sinal | o mesmo tipo de `x` |
| `arredondar(x)` | um número | o inteiro mais próximo; as meias arredondam para cima | `int` |
| `truncar(x)` | um número | a parte inteira, cortando as casas decimais | `int` |
| `raiz(x)` | um número igual ou maior do que zero | a raiz quadrada | `float` |

Os nomes escrevem-se em minúsculas, como `div` e `resto`, e o argumento vai sempre entre parênteses, logo a seguir ao nome. O argumento pode ser um número, uma variável ou uma conta inteira. Em `abs(precoA - precoB)`, primeiro calcula-se a subtração dentro dos parênteses, depois aplica-se a função ao resultado, e só depois o valor é usado ou guardado.

Cada uma tem os seus casos que enganam, e por isso vais vê-las uma a uma.

### `abs`, o valor absoluto

`abs` devolve a distância de um número a zero, ou seja, o número sem sinal. `abs(-7)` dá `7`, `abs(7)` dá `7` e `abs(0)` dá `0`. Com um `float`, dá um `float`: `abs(-2.5)` dá `2.5`.

Serve sempre que interessa o tamanho de uma diferença, e não o seu sentido. Imagina que um caderno custa 349 cêntimos num fornecedor e 415 noutro. Queres saber de quanto é a diferença de preço, seja qual for o mais caro. `349 - 415` dá `-66`, e uma diferença de menos 66 cêntimos não diz nada a ninguém. `abs(349 - 415)` dá `66`, e `abs(415 - 349)` também dá `66`. Com `abs`, a ordem da subtração deixa de importar:

```text
int diferencaDePreco = abs(precoA - precoB)
```

O caso que engana é o sítio dos parênteses. Antes de leres a explicação, tenta prever: quanto dão `abs(-3) + abs(5)` e `abs(-3 + 5)`? A função aplicada a cada parcela não é o mesmo que a função aplicada à conta toda. `abs(-3) + abs(5)` dá `8`, porque tira o sinal ao -3 antes de somar. `abs(-3 + 5)` dá `2`, porque primeiro soma, -3 mais 5 dá 2, e só depois tira o sinal.

### `arredondar`, o inteiro mais próximo

`arredondar` devolve o inteiro mais próximo do número que recebe. `arredondar(2.4)` dá `2`, porque 2,4 está mais perto de 2 do que de 3. `arredondar(2.6)` dá `3`. Um número que já é inteiro fica igual: `arredondar(7)` dá `7`. O resultado é sempre um `int`.

As meias precisam de uma regra, porque 2,5 está exatamente a meio caminho entre 2 e 3. Nesta disciplina, as meias arredondam para cima: `arredondar(2.5)` dá `3`. Também se pode arredondar o resultado de uma conta: `arredondar(10 / 4)` dá `3`, porque 10 a dividir por 4 dá 2,5. Algumas linguagens de programação usam outra regra para as meias, e o Python é uma delas, mas nos nossos algoritmos vale esta.

Há três casos que enganam. Antes de os leres, tenta prever: quanto dão `arredondar(2.49)`, `arredondar(2.2)` e `arredondar(-2.5)`?

O primeiro é arredondar em dois passos. `arredondar(2.49)` dá `2`, e não 3. Há quem pense "2,49 arredonda para 2,5, e 2,5 arredonda para 3", mas isso são dois arredondamentos seguidos. `arredondar` só faz um. Olha para o número tal como é, e 2,49 está mais perto de 2 do que de 3.

O segundo é pensar que `arredondar` arredonda sempre para cima. `arredondar(2.2)` dá `2`. Se precisares de arredondar sempre para cima, por exemplo para garantir que não fica a faltar uma caixa, nenhuma das quatro funções o faz diretamente. Vais ter de pensar noutra forma. A última pergunta de "Verificar o que aprendeste", no fim deste guia, põe-te esse problema.

O terceiro é o dos números negativos, porque "para cima" quer dizer para o lado dos números maiores. `arredondar(-2.4)` dá `-2` e `arredondar(-2.6)` dá `-3`, como esperavas, porque são os inteiros mais próximos. Mas `arredondar(-2.5)` dá `-2`. Está a meio caminho entre -3 e -2, e a meia vai para cima, para -2, que é o maior dos dois. Não vais precisar disto muitas vezes, mas é a regra aplicada à letra.

Onde é que isto serve? Por exemplo, num desconto. Um desconto de 15% num artigo de 1990 cêntimos dá 298,5 cêntimos, e meio cêntimo não se pode pagar. `arredondar(298.5)` dá 299. O segundo exemplo guiado deste guia trabalha este caso até ao fim.

### `truncar`, a parte inteira

`truncar` corta as casas decimais e fica só com a parte inteira. `truncar(3.9)` dá `3`, mesmo estando 3,9 muito perto de 4, e `truncar(3.1)` também dá `3`. `truncar(0.99)` dá `0`. Um número que já é inteiro fica igual: `truncar(7)` dá `7`. O resultado é sempre um `int`.

Serve quando só interessam as unidades completas. Um trabalho que demorou 2,75 horas demorou 2 horas completas e mais três quartos de hora: `truncar(2.75)` dá `2`.

O caso que engana é o dos números negativos. Antes de leres, tenta prever: quanto dá `truncar(-3.7)`? `truncar` corta as casas decimais, e por isso aproxima sempre o número de zero. `truncar(-3.7)` dá `-3`, e não -4. Compara com `arredondar(-3.7)`, que dá `-4`, porque -4 é o inteiro mais próximo de -3,7. Com números positivos, cortar as casas decimais é o mesmo que ir para baixo. Com números negativos, não é.

`truncar` e `div` estão ligados. Para dois inteiros positivos, `truncar(17 / 5)` dá `3`, porque 17 a dividir por 5 dá 3,4, e cortar as casas dá 3. É o mesmo que `17 div 5`. Se os dois valores são inteiros, usa `div`, que diz logo a quem lê que a conta é inteira. `truncar` fica para quando o valor já é um `float`, como um tempo em horas ou um peso.

### `raiz`, a raiz quadrada

`raiz` devolve a raiz quadrada do número que recebe, isto é, o número que, multiplicado por si próprio, dá o argumento. `raiz(25)` dá `5.0`, porque 5 vezes 5 dá 25. `raiz(0)` dá `0.0`. O resultado é sempre um `float`, mesmo quando a raiz é exata, e por isso aparece com o ponto zero. Quando a raiz não é exata, o resultado tem infinitas casas decimais, e o algoritmo guarda uma aproximação. Por exemplo, `raiz(2)` dá `1.4142...`, com mais casas decimais do que as que aqui se mostram.

Onde é que isto serve? Uma sala quadrada com 49 metros quadrados de área tem 7 metros de lado, porque 7 vezes 7 dá 49: `raiz(49)` dá `7.0`. Sempre que conheces a área de um quadrado e queres o lado, é uma raiz quadrada.

O primeiro caso que engana é que a raiz de uma soma não é a soma das raízes. Antes de leres, tenta prever: quanto dão `raiz(9 + 16)` e `raiz(9) + raiz(16)`? `raiz(9 + 16)` dá `5.0`, porque primeiro se soma, 9 mais 16 dá 25, e a raiz de 25 é 5. `raiz(9) + raiz(16)` dá `7.0`, porque é 3 mais 4. São contas diferentes, e só uma delas é a que o problema pede. Faz sempre primeiro a conta dentro dos parênteses, e só depois aplica a função.

O segundo caso que engana é o dos números negativos. Não existe raiz quadrada de um número negativo, porque nenhum número multiplicado por si próprio dá um resultado negativo. `raiz(-4)` não tem resultado, e um algoritmo que chegue a essa conta falha. O contrato de `raiz` diz que a entrada tem de ser igual ou maior do que zero. Cabe a quem usa a função garantir que é.

Estas quatro funções chegam para os problemas deste módulo. As linguagens de programação têm muitas mais, cada uma com o seu contrato, e vais conhecer algumas em Python. Nos algoritmos deste módulo, usa só estas quatro. Se um problema parecer precisar de outra, há uma forma de o resolver com as operações que já conheces, e encontrá-la faz parte do problema.

## Sequência

Uma **estrutura sequencial** é uma sequência de instruções executadas uma depois da outra, de cima para baixo. Cada uma executa-se exatamente uma vez, sem saltar nenhuma e sem voltar atrás.

É a forma mais simples de algoritmo, e é a única que usas neste tema. Uma receita em que todos os passos se fazem sempre, pela mesma ordem, é uma sequência. Uma receita com "se a massa estiver muito mole, junta mais farinha" já não é. Há um passo que umas vezes se faz e outras não, e esse tipo de instrução é o assunto do guia 03. E uma receita com "bate as claras até ficarem firmes" também não é. Manda repetir um gesto um número de vezes que não se sabe à partida, e a repetição é o assunto do guia 04.

Numa sequência, a ordem importa. Uma instrução só pode usar valores que já existem no momento em que é executada. Imagina uma conta que precisa de um valor que só é lido duas linhas abaixo. Essa conta usa uma variável que ainda não tem valor, e o resultado não faz sentido. Parece óbvio escrito assim, e é um dos erros mais frequentes de quem começa. A regra prática é esta. Primeiro leem-se os dados, depois fazem-se as contas, e só no fim se escrevem os resultados.

## A forma do pseudocódigo nas aulas

Há muitas formas de escrever pseudocódigo, e livros diferentes usam palavras diferentes. Nas aulas, e em todos os guias de algoritmos, usamos sempre a mesma, a que o professor usa no quadro. Se num livro ou num vídeo encontrares outra, não está errada. É outra maneira de escrever as mesmas ideias.

### Um vocabulário comum, sem erros de sintaxe

O pseudocódigo não é uma linguagem de programação, e nenhum computador o lê. As regras de escrita de uma linguagem chamam-se **sintaxe**, e um engano nessas regras, como um parêntese esquecido, é um **erro de sintaxe**. Em pseudocódigo não existe erro de sintaxe, porque uma linha escrita de outra maneira não faz o algoritmo parar. A forma das aulas é um **vocabulário**, um conjunto pequeno de palavras e de sinais que usamos sempre com o mesmo significado. Serve para duas coisas. A primeira é escreveres depressa, sem teres de inventar a cada linha uma maneira de dizer "mostra isto no ecrã". A segunda é toda a gente se entender. Quando toda a turma escreve `Escreve:` para mostrar uma coisa no ecrã, ninguém tem de perguntar o que aquela linha faz.

O objetivo do pseudocódigo, neste momento, é ajudar-te a pensar. Ajuda-te a dividir um problema em passos e a decidir a ordem desses passos. Ajuda-te também a perceber que dados entram, que contas se fazem e o que sai. É esse raciocínio lógico que se está a treinar, e é ele que conta. As regras fixas de escrita vêm mais tarde, com o Python, e aí sim, uma vírgula fora do sítio impede o programa de funcionar.

### Frases claras também valem

Se não te lembrares de como se escreve uma coisa na forma das aulas, escreve-a em frases. Faz o mesmo se uma ideia te sair melhor em português. Um algoritmo escrito em frases claras é tão válido como um escrito em pseudocódigo, desde que não deixe dúvidas. Não deixar dúvidas quer dizer que qualquer pessoa que siga as tuas frases faz exatamente o mesmo que tu, sem ter de adivinhar nada. Para o confirmares, faz a cada frase três perguntas: diz quanto? diz quando? diz o que acontece se não der? São perguntas do mesmo género das que usaste no guia 01 para encontrar ambiguidades.

Vê a diferença em dois algoritmos escritos em frases para o problema das caixas de cadernos, que vais estudar no exemplo guiado. Este primeiro deixa dúvidas:

1. Pergunta quantos cadernos foram encomendados.
2. Divide os cadernos pelas caixas.
3. Mostra o resultado.

A segunda frase não diz quantos cadernos leva uma caixa, nem que divisão se faz. Com parte decimal, para 30 cadernos daria 2,5 caixas. Inteira, daria 2 caixas e 6 cadernos de fora. A terceira não diz que resultado se mostra. Duas pessoas a seguir estas frases podiam chegar a respostas diferentes, e nenhuma delas estaria a desobedecer. Este segundo, pelo contrário, não deixa dúvidas:

1. Uma caixa leva sempre 12 cadernos.
2. Pergunta quantos cadernos foram encomendados e guarda a resposta, um número inteiro, em `cadernos`.
3. Guarda em `caixasCompletas` quantas vezes o 12 cabe inteiro em `cadernos`, sem partir caixas.
4. Guarda em `unidadesSoltas` quantos cadernos sobram depois de encher essas caixas.
5. Mostra "Caixas completas: " seguido do valor de `caixasCompletas`.
6. Mostra "Unidades soltas: " seguido do valor de `unidadesSoltas`.

Este segundo algoritmo está certo, e vale tanto como a versão em pseudocódigo do exemplo guiado. A versão em pseudocódigo só é mais curta e mais rápida de ler, e é por isso que a usamos. Quando escreveres, usa a forma das aulas sempre que te lembrares dela. Quando uma linha não te sair, pergunta-te o que essa linha tem de fazer, por palavras tuas. Depois escreve-a em frases claras e segue em frente. O que conta agora é a lógica.

### A forma, peça a peça

Um algoritmo na forma das aulas começa na primeira instrução e acaba na última. Não tem cabeçalho com o nome do algoritmo, nem uma lista de variáveis no topo, nem palavras a marcar onde começa e onde acaba. Lê-se de cima para baixo. Se for preciso dar um nome ao algoritmo, para se falar dele, esse nome fica fora do pseudocódigo. Fica no título ou na frase que o apresenta.

Vê um exemplo pequeno, que calcula quantos lugares sentados tem uma sala de mesas iguais. Antes de leres a explicação, tenta prever: com 6 mesas, o que aparece no ecrã no fim?

```text
const LUGARES_POR_MESA = 4
Escreve: "Quantas mesas tem a sala? "
int mesas = ler valor
int lugares = mesas * LUGARES_POR_MESA
Escreve: "Lugares sentados: ", lugares
```

Com 6 mesas, aparece "Lugares sentados: 24", porque 6 vezes 4 dá 24.

Leitura guiada, linha a linha:

1. `const LUGARES_POR_MESA = 4` cria a constante, no início, antes de ser usada. É uma regra do problema: cada mesa tem 4 lugares.
2. `Escreve: "Quantas mesas tem a sala? "` mostra a pergunta. O espaço antes da aspa final separa a pergunta do número que a pessoa vai escrever.
3. `int mesas = ler valor` faz nascer a variável `mesas`, do tipo `int`, com o valor que a pessoa escrever.
4. `int lugares = mesas * LUGARES_POR_MESA` faz nascer `lugares`, também do tipo `int`, com o resultado da conta.
5. `Escreve: "Lugares sentados: ", lugares` mostra o resultado.

A **indentação** é o recuo de uma linha em relação à margem esquerda, e na forma das aulas faz-se com quatro espaços. Nos algoritmos deste guia não há indentação, porque são sequenciais, e todas as linhas começam encostadas à esquerda. A partir do guia 03, a indentação passa a contar, porque é a única marca de onde começa e onde acaba um bloco de instruções. Um **bloco** é um conjunto de linhas que pertencem à mesma instrução e que se executam juntas. Vê o exemplo que o professor usa nas aulas. Ainda não precisas de perceber o `Se`, que é matéria do guia 03. Repara só na margem:

```text
const LIMITE = 50
Escreve: "Diz uma quantidade: "
int quantidade = ler valor
Se quantidade <= LIMITE
    Escreve: "Aceite"
Senão
    Escreve: "Recusado"
```

A linha `Escreve: "Aceite"` tem quatro espaços à esquerda, e é isso que diz que ela pertence ao `Se`. Só se executa quando a quantidade não passa do limite. A linha `Escreve: "Recusado"` tem o mesmo recuo por baixo do `Senão`, e pertence ao `Senão`. Não há nenhuma palavra a fechar os blocos. Um bloco acaba quando aparece uma linha com menos recuo, ou quando o algoritmo acaba. O Python funciona assim. Em Python, a indentação faz parte das regras da linguagem, porque é ela que diz o que está dentro de quê.

A tabela seguinte reúne a forma toda, incluindo o que vais aprender nos guias seguintes. Essas linhas estão marcadas na última coluna, e ainda não as usas. Estão aqui para teres um único sítio de consulta durante todo o percurso de algoritmos.

| Elemento | Como se escreve | Exemplo | Quando |
| --- | --- | --- | --- |
| Início e fim | não há cabeçalho nem palavras de início e de fim; o algoritmo começa na primeira instrução e acaba na última | o exemplo dos lugares, acima | já neste guia |
| Constante | `const`, o nome em maiúsculas, `=` e o valor; no início, antes de ser usada | `const UNIDADES_POR_CAIXA = 12` | já neste guia |
| Variável | nasce na linha onde aparece pela primeira vez, com o tipo à frente; depois usa-se só o nome | `int total = 0` e, mais abaixo, `total = total + preco` | já neste guia |
| Tipos | `int`, `float`, `string`, `bool` | `float descontoExato = precoEmCentimos * percentagem / 100` | já neste guia |
| Valores lógicos | `true`, `false` | `bool pago = false` | já neste guia |
| Dar um valor | a variável, `=` e a expressão; à esquerda do `=`, sempre uma só variável | `total = total + preco` | já neste guia |
| Entrada | `ler valor`, do lado direito de uma atribuição | `int cadernos = ler valor` na primeira vez; `cadernos = ler valor` nas seguintes | já neste guia |
| Saída | `Escreve:` com texto e valores separados por vírgulas | `Escreve: "Total: ", total` | já neste guia |
| Aritmética | `+`, `-`, `*`, `/`, `div`, `resto` e parênteses | `int caixas = unidades div UNIDADES_POR_CAIXA` | já neste guia |
| Funções predefinidas | o nome em minúsculas e o argumento entre parênteses; só `abs`, `arredondar`, `truncar` e `raiz` | `abs(precoA - precoB)` | já neste guia |
| Indentação | quatro espaços por nível; é a única marca de onde começa e onde acaba um bloco | o exemplo do `LIMITE`, acima | a partir do guia 03 |
| Comparações | `==` (igual), `!=` (diferente), `<`, `<=`, `>`, `>=` | `quantidade <= LIMITE` | vais usar no guia 03 |
| Operadores lógicos | `e`, `ou`, `não`, em minúsculas | `nota >= 0 e nota <= 20` | vais usar no guia 03 |
| Seleção | `Se condição`, `Senão se condição`, `Senão`; o que está dentro vai indentado, sem palavra de fim | o exemplo do `LIMITE`, acima | vais usar no guia 03 |
| Repetição condicional | `Enquanto condição`, com o corpo indentado | `Enquanto quantidade != SENTINELA` | vais usar no guia 04 |
| Repetição contada | `Para i de 1 até n`, com o corpo indentado | `Para i de 1 até n` | vais usar no guia 04, que mostra também outra forma de escrever o `Para` |
| Array | os valores entre parênteses retos, separados por vírgulas, como uma lista; cada valor pelo índice, que começa em 0 | `notas = [12, 8, 15]` e `notas[0]` | vais usar no guia 04 |
| Percorrer um array | pelo índice, com `Para i de 0 até` o último índice, ou pelo valor, com `Para cada` | `Para cada nota em notas` | vais usar no guia 04 |
| Função criada por ti | `Função`, o nome e os parâmetros entre parênteses; o corpo vai indentado, sem palavra de fim | `Função mostraStock(artigo, quantidade)` | vais usar no guia 05 |

Os nomes das variáveis e das constantes não podem ser palavras que o pseudocódigo já usa com outro significado. São exemplos `Escreve`, `Se`, `Enquanto`, `const` e `div`. Quem lê ficava sem saber se aquilo é um nome ou uma instrução. Nas linguagens de programação, estas palavras chamam-se **palavras reservadas**, e aí não podem mesmo ser usadas como nomes.

Há também alguns hábitos de escrita que ajudam a ler depressa. As palavras que abrem uma instrução começam por maiúscula: `Escreve:`, `Se`, `Senão`, `Senão se`, `Enquanto`, `Para` e `Função`. Os tipos, os operadores como `div`, `resto`, `e`, `ou` e `não`, as funções predefinidas e `ler valor` escrevem-se em minúsculas. Os nomes das variáveis escrevem-se em camelCase sem acentos, como `totalUnidades`, e os das constantes em maiúsculas com traço baixo, como `UNIDADES_POR_CAIXA`. Se escreveres `escreve:` com minúscula, ninguém deixa de te perceber. Mas quando todos escrevem da mesma maneira, lê-se mais depressa, e é mais fácil comparar o teu algoritmo com o de um colega.

## Os símbolos do fluxograma

Um fluxograma representa um algoritmo com figuras ligadas por setas. Cada figura tem uma forma que diz que tipo de instrução é, e as setas dizem a ordem.

Neste percurso, os fluxogramas são para saberes o que são e como se leem. Isto é, o que quer dizer cada figura, como se segue o caminho com o dedo e como se compara um fluxograma com o pseudocódigo. Desenhar fluxogramas, no papel ou numa aplicação, é opcional, e só o fazes quando o professor o indicar. O laboratório deste tema ensina a desenhá-los no diagrams.net, uma aplicação que se usa no browser, sem criar conta. O browser é o programa que abre as páginas da internet.

| Figura | Para que serve | O que leva escrito |
| --- | --- | --- |
| Oval, ou retângulo de pontas redondas | Início e fim do algoritmo | `Início` ou `Fim` |
| Paralelogramo | Entrada e saída de dados | uma leitura, com `ler valor`, ou uma saída, com `Escreve:` |
| Retângulo | Processamento: atribuições e contas | uma atribuição, como `int caixasCompletas = cadernos div UNIDADES_POR_CAIXA` |
| Losango | Decisão: o caminho divide-se em dois | uma pergunta, a partir do guia 03 |
| Seta | O sentido do percurso, de uma figura para a seguinte | nada, num algoritmo sequencial |

Há quatro pormenores sobre as figuras.

O paralelogramo serve tanto para a entrada como para a saída, porque as duas são comunicação com o exterior do algoritmo. O que distingue uma da outra é o que está escrito lá dentro, `ler valor` ou `Escreve:`. Uma leitura em que a variável nasce, como `int cadernos = ler valor`, vai num paralelogramo com o tipo e tudo. A figura leva a instrução tal como está no pseudocódigo.

Uma atribuição que usa uma função predefinida, como `int desconto = arredondar(descontoExato)`, vai num retângulo, porque é uma conta como as outras.

A linha da constante, como `const UNIDADES_POR_CAIXA = 12`, não tem figura. Não é uma ação que o algoritmo faça com os dados. É uma regra do problema, que vale do princípio ao fim, como se já lá estivesse antes de o algoritmo começar. Numa receita, a lista dos ingredientes também não é um dos passos da preparação.

O fluxograma tem sempre um oval de Início e um só oval de Fim, embora o pseudocódigo não tenha essas palavras. No texto não fazem falta, porque se começa a ler na primeira linha e se acaba na última. No desenho fazem, porque as figuras podem estar espalhadas pela página e as setas podem ir para qualquer lado. Quem olha tem de saber onde o percurso começa e onde acaba. A partir do guia 03, o percurso pode dividir-se em caminhos diferentes. Mesmo aí, os caminhos voltam a juntar-se antes do Fim, e o Fim continua a ser um só.

Um fluxograma bem feito cumpre sempre estas regras:

- tem um único início;
- tem um único fim;
- todas as figuras estão ligadas por setas, e nenhuma seta fica pendurada sem destino;
- cada figura tem uma só instrução, escrita como no pseudocódigo, para os dois se poderem comparar linha a linha.

Neste tema só aparecem o oval, o paralelogramo e o retângulo, ligados em linha reta, porque os algoritmos sequenciais nunca escolhem entre dois caminhos. O losango fica apresentado porque faz parte da simbologia, e aparece a partir do guia 03.

Neste guia, os fluxogramas aparecem desenhados pelo GitHub, o site onde estão guardados os materiais da disciplina. O GitHub desenha-os a partir de um texto que transforma em figuras. Se estiveres a ler o ficheiro noutro sítio e em vez do desenho vires texto com setas e parênteses, não faz mal. Cada fluxograma tem, logo a seguir, a descrição do percurso em palavras. Se o professor te pedir que desenhes um fluxograma, no papel ou na aplicação, usa as figuras verdadeiras.

## A tabela de trace

Uma **tabela de trace** é uma tabela onde se executa um algoritmo à mão, instrução a instrução. Em cada linha regista-se o valor de todas as variáveis depois dessa instrução. Em inglês chama-se trace table, e vais ouvir muitas vezes dizer apenas "fazer o trace".

Serve para veres o algoritmo por dentro. Um algoritmo só mostra o que escreve no ecrã, e quando o resultado está errado, isso não diz onde está o erro. O trace mostra o estado depois de cada instrução. Por isso, mostra o sítio exato onde um valor passou a ser diferente do que devia.

Uma tabela de trace constrói-se assim:

1. Faz uma coluna para o número do passo, uma para a instrução executada, uma para cada variável e uma para o que aparece no ecrã. As constantes não precisam de coluna, porque têm sempre o mesmo valor. A linha `const` também não conta como passo, pela mesma razão que não tem figura no fluxograma.
2. Na primeira linha, o passo 0, antes de qualquer instrução, escreve "sem valor" em todas as variáveis, porque nenhuma nasceu ainda.
3. Para cada instrução, pela ordem em que é executada, acrescenta uma linha. Copia os valores da linha de cima e muda só o que essa instrução muda.
4. Numa atribuição, incluindo as que leem um valor com `ler valor`, muda só a coluna da variável que está à esquerda do `=`. As outras ficam iguais. Numa leitura, a coluna do ecrã diz o valor que a pessoa escreveu, como "a pessoa escreve 30".
5. Num `Escreve:`, nenhuma variável muda. Escreve na coluna do ecrã exatamente o que aparece, com os valores que as variáveis têm nesse momento.

Há uma forma simples de ler uma tabela destas. O estado antes de uma instrução está na linha de cima, e o estado depois está na própria linha. Comparar as duas linhas mostra o efeito da instrução. Já viste duas tabelas assim na secção da atribuição.

A regra mais importante do trace é executar o que está escrito, e não o que achas que o algoritmo devia fazer. Se preencheres a tabela com os valores que esperavas, ela concorda sempre contigo e não encontra erro nenhum. O trace só serve se fores tão literal como um computador, que não sabe o que querias dizer e só sabe o que escreveste. Pode acontecer que uma linha do teu trace saia como esperavas sem teres feito a conta. Nesse caso, refaz essa linha com a conta que está escrita e com os valores da linha de cima.

## Exemplo guiado: as caixas de cadernos

### O problema

Uma papelaria vende cadernos que o fornecedor só entrega em caixas de 12 unidades. Dado o número de cadernos que um cliente encomendou, a papelaria quer saber quantas caixas completas isso dá. Quer saber também quantas unidades sobram fora das caixas completas, para as ir buscar à prateleira dos cadernos soltos.

### Passo 1: O contrato

Começa-se como no guia 01, porque a análise não desaparece só porque agora há notação:

| Pergunta | Resposta |
| --- | --- |
| Entradas | O número de cadernos encomendados, um inteiro igual ou maior do que zero |
| Saídas | O número de caixas completas, um inteiro igual ou maior do que zero, e o número de unidades soltas, um inteiro entre 0 e 11 |
| Restrições | As caixas têm sempre 12 unidades |
| Condições | Neste problema não há caminhos alternativos: os passos são sempre os mesmos |

Repara no intervalo das unidades soltas, de 0 a 11. Nunca podem ser 12 ou mais, porque 12 unidades soltas já enchem mais uma caixa. Escrever isto no contrato dá-te uma forma de apanhar erros: se o algoritmo alguma vez mostrar 12 ou mais unidades soltas, está errado.

Antes de haver algoritmo, escolhem-se os casos de teste e calcula-se à mão o resultado de cada um. Um **caso de teste** é o nome novo de um exemplo concreto do guia 01. É uma entrada escolhida para testar o algoritmo, com o resultado que se espera. É a tua previsão, feita antes de executar, e depois serve para testar o algoritmo. Estes três foram escolhidos de propósito, e cada um testa uma coisa diferente:

| cadernos | caixasCompletas | unidadesSoltas | Porque é que este caso foi escolhido |
| ---: | ---: | ---: | --- |
| 30 | 2 | 6 | Um caso normal: várias caixas e algumas unidades de fora |
| 24 | 2 | 0 | Um múltiplo exato de 12: enche as caixas e não sobra nada |
| 5 | 0 | 5 | Menos do que uma caixa: nenhuma caixa fica completa |

Testar só o caso normal esconde metade dos erros. Um algoritmo mal feito pode acertar no 30 e falhar no 24, se tratar mal o resto zero. Ou pode falhar no 5, se partir do princípio de que há sempre pelo menos uma caixa. O contrato diz que a entrada é igual ou maior do que zero, e por isso um valor negativo fica fora deste problema. O que fazer quando alguém escreve um valor fora do contrato é a validação de dados, assunto do guia 03.

### Passo 2: Decompor e pensar nas contas

A decomposição é curta: pedir e ler o número de cadernos, calcular as caixas completas, calcular as unidades soltas e mostrar os dois resultados.

As contas merecem mais atenção. Pensa no caso de 30 cadernos. Quantas caixas completas se enchem com 30 cadernos? É perguntar quantas vezes 12 cabe em 30, sem partir nenhuma caixa. Cabe 2 vezes, que levam 24 cadernos. É a divisão inteira: `30 div 12` dá `2`.

E quantos cadernos ficam de fora dessas 2 caixas? O que sobra, 30 menos 24, que dá 6. É o resto: `30 resto 12` dá `6`.

Confirma com a verificação da secção das expressões: 12 vezes 2, mais 6, dá 30. As duas contas estão certas, e 6 está entre 0 e 11, como o contrato exige.

Repara porque é que a divisão com `/` não serve. `30 / 12` dá `2.5`, e esse número não responde a nenhuma das duas perguntas. Não há 2,5 caixas no armazém, e o 0,5 não são 5 cadernos. São meia caixa, ou seja, 6 cadernos. Ler a parte decimal como se fossem unidades é um erro clássico.

### Passo 3: O pseudocódigo

Neste texto vamos chamar-lhe o algoritmo das caixas de cadernos. O nome fica aqui, na frase que o apresenta, e não dentro do pseudocódigo.

```text
const UNIDADES_POR_CAIXA = 12
Escreve: "Quantos cadernos foram encomendados? "
int cadernos = ler valor
int caixasCompletas = cadernos div UNIDADES_POR_CAIXA
int unidadesSoltas = cadernos resto UNIDADES_POR_CAIXA
Escreve: "Caixas completas: ", caixasCompletas
Escreve: "Unidades soltas: ", unidadesSoltas
```

Leitura guiada. Cada decisão deste pseudocódigo tem uma razão:

1. `UNIDADES_POR_CAIXA` é uma constante porque 12 é uma regra do fornecedor, e não um dado que mude de encomenda para encomenda. Está na primeira linha, antes de ser usada. Se um dia o fornecedor passar a caixas de 24, muda-se essa linha e o resto do algoritmo fica igual.
2. As três variáveis são do tipo `int`, porque cadernos, caixas e unidades soltas não têm meios. Foi o contrato que o decidiu, no passo 1. O tipo aparece uma única vez para cada uma, na linha onde nasce.
3. Não há nenhuma lista de variáveis no topo, e cada uma aparece quando é precisa. Se quiseres saber de que tipo é `unidadesSoltas`, procuras a linha onde ela nasce, e está lá escrito.
4. `cadernos` e `unidadesSoltas` têm nomes diferentes porque guardam coisas diferentes: o total encomendado e o que sobra depois de encher as caixas. Se usasses a mesma variável para as duas coisas, com `cadernos = cadernos resto UNIDADES_POR_CAIXA`, o total encomendado era apagado. Não havia forma de o recuperar.
5. Há um `Escreve:` com a pergunta antes da leitura, para quem usa o algoritmo saber o que lhe está a ser pedido.
6. As duas contas vêm depois da leitura, porque ambas precisam do valor de `cadernos`, que só existe depois de ser lido.
7. As duas contas usam a constante, e não o número 12 escrito à mão. É a mesma ideia do ponto 1. O valor está num sítio só.
8. Os dois `Escreve:` do fim juntam texto e valor. O espaço depois dos dois pontos, dentro das aspas, está lá para o ecrã mostrar "Caixas completas: 2" e não "Caixas completas:2".

Se tivesses escrito este algoritmo em frases claras, como o segundo exemplo da secção "A forma do pseudocódigo nas aulas", estaria igualmente certo. As frases dizem o mesmo, linha a linha. O pseudocódigo é a mesma lógica, escrita de forma mais curta.

### Passo 4: O fluxograma

O mesmo algoritmo, desenhado:

```mermaid
flowchart TD
    A([Início]) --> B[/"Escreve: #quot;Quantos cadernos foram encomendados? #quot;"/]
    B --> C[/"int cadernos = ler valor"/]
    C --> D["int caixasCompletas = cadernos div UNIDADES_POR_CAIXA"]
    D --> E["int unidadesSoltas = cadernos resto UNIDADES_POR_CAIXA"]
    E --> F[/"Escreve: #quot;Caixas completas: #quot;, caixasCompletas"/]
    F --> G[/"Escreve: #quot;Unidades soltas: #quot;, unidadesSoltas"/]
    G --> Z([Fim])
```

Descrição do percurso, para quem não vê o desenho. O fluxograma é uma única coluna de oito figuras ligadas por sete setas, de cima para baixo. Começa num oval com a palavra Início. Seguem-se dois paralelogramos, o primeiro com a instrução que escreve a pergunta e o segundo com `int cadernos = ler valor`. Depois vêm dois retângulos, com as duas atribuições, a das caixas completas e a das unidades soltas, por esta ordem. Seguem-se mais dois paralelogramos, com os dois `Escreve:` dos resultados. Termina num oval com a palavra Fim.

Segue o percurso com o dedo, de cima para baixo. É uma linha única, sem bifurcações, e é isso que significa uma estrutura sequencial.

Agora compara figura a figura com o pseudocódigo. A cada instrução corresponde uma figura, pela mesma ordem e com o mesmo texto. As seis instruções dão seis figuras, e o início e o fim dão mais duas, e é por isso que são oito. A linha da constante, `const UNIDADES_POR_CAIXA = 12`, não tem figura, pela razão que viste na secção dos símbolos. As três variáveis também não têm figuras próprias. Cada uma aparece, com o seu tipo, dentro da figura da instrução onde nasce. É esta a verificação que se faz sempre que se lê um fluxograma ao lado do pseudocódigo. O laboratório deste tema, que é opcional, pede-a no fim do desenho.

### Passo 5: O trace de três entradas

Já sabes, pelo passo 1, o que o ecrã tem de mostrar em cada caso, e o trace vai confirmar se o algoritmo o mostra. A constante não tem coluna, porque vale 12 do princípio ao fim. Pela mesma razão, a linha `const` não é um passo, e o passo 1 é a pergunta.

Primeiro caso: a pessoa escreve 30.

| Passo | Instrução executada | cadernos | caixasCompletas | unidadesSoltas | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `Escreve: "Quantos cadernos foram encomendados? "` | sem valor | sem valor | sem valor | Quantos cadernos foram encomendados? |
| 2 | `int cadernos = ler valor` | 30 | sem valor | sem valor | a pessoa escreve 30 |
| 3 | `int caixasCompletas = cadernos div UNIDADES_POR_CAIXA` | 30 | 2 | sem valor | nada |
| 4 | `int unidadesSoltas = cadernos resto UNIDADES_POR_CAIXA` | 30 | 2 | 6 | nada |
| 5 | `Escreve: "Caixas completas: ", caixasCompletas` | 30 | 2 | 6 | Caixas completas: 2 |
| 6 | `Escreve: "Unidades soltas: ", unidadesSoltas` | 30 | 2 | 6 | Unidades soltas: 6 |

Lê a tabela comparando cada linha com a de cima, que é o estado antes da instrução.

No passo 1 nenhuma variável muda, porque `Escreve:` não mexe no estado. Só aparece a pergunta no ecrã.

No passo 2, `cadernos` nasce e passa de "sem valor" para 30. É a única coluna que muda, porque a leitura só guarda valor na variável que está à esquerda do `=`.

No passo 3 calcula-se o lado direito com o valor que `cadernos` tem nesse momento, `30 div 12`. O 12 cabe duas vezes em 30, e por isso dá 2. Esse 2 é guardado em `caixasCompletas`. `cadernos` continua a valer 30, porque usar o valor de uma variável numa conta não o altera.

No passo 4 calcula-se `30 resto 12`. Depois de tirar duas caixas de 12, que levam 24 cadernos, sobram 6. `unidadesSoltas` passa de "sem valor" para 6.

Nos passos 5 e 6 nenhuma variável muda, e aparecem no ecrã os dois resultados, com os valores que as variáveis têm nesse momento.

Segundo caso: a pessoa escreve 24.

| Passo | Instrução executada | cadernos | caixasCompletas | unidadesSoltas | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `Escreve: "Quantos cadernos foram encomendados? "` | sem valor | sem valor | sem valor | Quantos cadernos foram encomendados? |
| 2 | `int cadernos = ler valor` | 24 | sem valor | sem valor | a pessoa escreve 24 |
| 3 | `int caixasCompletas = cadernos div UNIDADES_POR_CAIXA` | 24 | 2 | sem valor | nada |
| 4 | `int unidadesSoltas = cadernos resto UNIDADES_POR_CAIXA` | 24 | 2 | 0 | nada |
| 5 | `Escreve: "Caixas completas: ", caixasCompletas` | 24 | 2 | 0 | Caixas completas: 2 |
| 6 | `Escreve: "Unidades soltas: ", unidadesSoltas` | 24 | 2 | 0 | Unidades soltas: 0 |

A diferença para o primeiro caso está no passo 4. O 12 cabe exatamente duas vezes em 24, e não sobra nada, por isso `24 resto 12` dá 0. Repara que o algoritmo mostra "Unidades soltas: 0" e não deixa essa linha de fora. Numa sequência, todas as instruções se executam sempre, mesmo quando o resultado é zero. Não há caixas a mais nem a menos, e o múltiplo exato não precisou de nenhum cuidado especial.

Terceiro caso: a pessoa escreve 5.

| Passo | Instrução executada | cadernos | caixasCompletas | unidadesSoltas | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `Escreve: "Quantos cadernos foram encomendados? "` | sem valor | sem valor | sem valor | Quantos cadernos foram encomendados? |
| 2 | `int cadernos = ler valor` | 5 | sem valor | sem valor | a pessoa escreve 5 |
| 3 | `int caixasCompletas = cadernos div UNIDADES_POR_CAIXA` | 5 | 0 | sem valor | nada |
| 4 | `int unidadesSoltas = cadernos resto UNIDADES_POR_CAIXA` | 5 | 0 | 5 | nada |
| 5 | `Escreve: "Caixas completas: ", caixasCompletas` | 5 | 0 | 5 | Caixas completas: 0 |
| 6 | `Escreve: "Unidades soltas: ", unidadesSoltas` | 5 | 0 | 5 | Unidades soltas: 5 |

Agora a diferença está nos passos 3 e 4. O 12 não cabe nenhuma vez em 5, e por isso `5 div 12` dá 0. Como não se encheu nenhuma caixa, sobram os 5 cadernos todos, e `5 resto 12` dá 5. É o caso que engana da secção das expressões, agora dentro de um algoritmo.

Se fizeres também o trace de 0 cadernos, os passos 3 e 4 dão 0 e 0. O algoritmo trata o zero sem precisar de nenhuma instrução especial. Com 12 cadernos, dão 1 e 0.

### Passo 6: Confirmar que as representações concordam

Tens agora três representações do mesmo algoritmo: o pseudocódigo, o fluxograma e o trace. Estão certas se derem os mesmos resultados nos mesmos casos de teste. E esses resultados têm de ser os que o contrato previu à mão, no passo 1.

| cadernos | Previsto no contrato | O que o trace mostrou no ecrã |
| ---: | --- | --- |
| 30 | 2 caixas e 6 unidades soltas | Caixas completas: 2 e Unidades soltas: 6 |
| 24 | 2 caixas e 0 unidades soltas | Caixas completas: 2 e Unidades soltas: 0 |
| 5 | 0 caixas e 5 unidades soltas | Caixas completas: 0 e Unidades soltas: 5 |

Os três casos coincidem. O fluxograma tem as mesmas instruções que o pseudocódigo, pela mesma ordem. Por isso, percorrê-lo com o dedo, com os mesmos valores, produz as mesmas linhas de trace. Se algum caso não coincidisse, o passo seguinte seria procurar no trace a primeira linha onde um valor ficou diferente do previsto. É aí que está o erro.

## Um segundo exemplo guiado, mais curto: o desconto ao cêntimo

O exemplo das caixas de cadernos só tem valores do tipo `int`. Este mostra um algoritmo onde um `float` e vários `int` convivem, e onde uma função predefinida decide o resultado.

### O problema e o contrato

A papelaria faz descontos em percentagem, e os preços estão guardados em cêntimos. Dado o preço de um artigo e a percentagem de desconto, quer saber o desconto em cêntimos e o preço final. A regra da loja é que o desconto se arredonda ao cêntimo mais próximo, com as meias para cima, porque meio cêntimo não se paga.

Há duas entradas. A primeira é o preço do artigo em cêntimos, um inteiro maior do que zero. A segunda é a percentagem de desconto, um inteiro entre 0 e 100. As saídas são o desconto em cêntimos e o preço final em cêntimos, os dois inteiros. A restrição é a regra do arredondamento. Não há condições, porque os passos são sempre os mesmos.

### As contas e o pseudocódigo

Antes de olhares para o algoritmo, faz as contas à mão para um artigo de 1990 cêntimos com 15% de desconto. Uma percentagem é uma parte em cada cem. 15% de 1990 cêntimos calcula-se multiplicando 1990 por 15 e dividindo por 100. 1990 vezes 15 dá 29850, e 29850 a dividir por 100 dá 298,5. Como meio cêntimo não se paga, arredonda-se, e pela regra das meias fica 299. O preço final é 1990 menos 299, que dá 1691 cêntimos.

Chamemos-lhe o algoritmo do desconto ao cêntimo:

```text
Escreve: "Preço do artigo, em cêntimos? "
int precoEmCentimos = ler valor
Escreve: "Percentagem de desconto? "
int percentagem = ler valor
float descontoExato = precoEmCentimos * percentagem / 100
int desconto = arredondar(descontoExato)
int precoFinal = precoEmCentimos - desconto
Escreve: "Desconto: ", desconto, " cêntimos"
Escreve: "Preço final: ", precoFinal, " cêntimos"
```

Leitura guiada. Repara nas decisões:

1. Não há nenhuma linha `const`, porque este algoritmo não tem valores fixos. O preço e a percentagem mudam de artigo para artigo e de promoção para promoção, e por isso são lidos. O algoritmo começa logo na primeira instrução, a pergunta do preço.
2. `descontoExato` nasce como `float` por duas razões. Guarda o resultado de uma divisão com `/`, que é sempre um `float`, e 298,5 tem parte decimal que interessa. Todas as outras variáveis são `int`, porque são quantias em cêntimos.
3. O desconto passa por duas variáveis, `descontoExato` e `desconto`, para se ver no trace o valor antes e depois do arredondamento. Podia escrever-se tudo numa linha, `int desconto = arredondar(precoEmCentimos * percentagem / 100)`, e o resultado seria o mesmo. Enquanto estás a aprender, uma variável a mais que torna o raciocínio visível ajuda.
4. Em `precoEmCentimos * percentagem / 100`, a multiplicação e a divisão estão no mesmo nível, e fazem-se da esquerda para a direita. Primeiro faz-se 1990 vezes 15, depois a divisão por 100.
5. No fluxograma, a atribuição com `arredondar` fica num retângulo, como qualquer outra conta. O fluxograma deste algoritmo seria uma linha reta com 11 figuras: o início, as nove instruções e o fim.

### O trace

O trace completo com 1990 cêntimos e 15%:

| Passo | Instrução executada | precoEmCentimos | percentagem | descontoExato | desconto | precoFinal | Ecrã |
| ---: | --- | ---: | ---: | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | sem valor | sem valor | nada |
| 1 | `Escreve: "Preço do artigo, em cêntimos? "` | sem valor | sem valor | sem valor | sem valor | sem valor | Preço do artigo, em cêntimos? |
| 2 | `int precoEmCentimos = ler valor` | 1990 | sem valor | sem valor | sem valor | sem valor | a pessoa escreve 1990 |
| 3 | `Escreve: "Percentagem de desconto? "` | 1990 | sem valor | sem valor | sem valor | sem valor | Percentagem de desconto? |
| 4 | `int percentagem = ler valor` | 1990 | 15 | sem valor | sem valor | sem valor | a pessoa escreve 15 |
| 5 | `float descontoExato = precoEmCentimos * percentagem / 100` | 1990 | 15 | 298.5 | sem valor | sem valor | nada |
| 6 | `int desconto = arredondar(descontoExato)` | 1990 | 15 | 298.5 | 299 | sem valor | nada |
| 7 | `int precoFinal = precoEmCentimos - desconto` | 1990 | 15 | 298.5 | 299 | 1691 | nada |
| 8 | `Escreve: "Desconto: ", desconto, " cêntimos"` | 1990 | 15 | 298.5 | 299 | 1691 | Desconto: 299 cêntimos |
| 9 | `Escreve: "Preço final: ", precoFinal, " cêntimos"` | 1990 | 15 | 298.5 | 299 | 1691 | Preço final: 1691 cêntimos |

No passo 5, o valor guardado tem parte decimal, e por isso a variável tinha de ser um `float`. No passo 6, `arredondar` recebe 298.5, que é uma meia, e devolve 299. `descontoExato` continua com 298.5, porque dar o valor de uma variável a uma função não o altera.

Com mais dois casos, escolhidos para o arredondamento ir para baixo e para cima sem ser numa meia:

| precoEmCentimos | percentagem | descontoExato | desconto | precoFinal |
| ---: | ---: | ---: | ---: | ---: |
| 1990 | 15 | 298.5 | 299 | 1691 |
| 1234 | 10 | 123.4 | 123 | 1111 |
| 2499 | 20 | 499.8 | 500 | 1999 |

### `arredondar` e `truncar` dão resultados diferentes

Alguém podia achar que tanto faz arredondar como cortar as casas decimais. Vê a diferença nos mesmos três casos:

| precoEmCentimos | percentagem | descontoExato | com `arredondar` | com `truncar` |
| ---: | ---: | ---: | ---: | ---: |
| 1990 | 15 | 298.5 | 299 | 298 |
| 1234 | 10 | 123.4 | 123 | 123 |
| 2499 | 20 | 499.8 | 500 | 499 |

Num dos casos coincidem, e nos outros dois o cliente recebia um cêntimo a menos de desconto. Nenhuma das duas funções está errada em si. A certa é a que cumpre a regra escrita no contrato, e é por isso que o contrato diz como se arredonda. Sem essa restrição escrita, duas pessoas podiam fazer algoritmos diferentes, os dois "certos", com resultados diferentes.

### O erro que dá desconto zero

Há quem escreva a percentagem como `percentagem div 100`, a pensar em "15 a dividir por 100". Antes de leres, tenta prever: quanto dá `15 div 100`? Dá 0, porque 100 não cabe nenhuma vez em 15. E `precoEmCentimos * (percentagem div 100)` dá 0 para qualquer percentagem abaixo de 100. O algoritmo corria sem queixas e nunca fazia desconto nenhum. Aqui a parte decimal interessa, e por isso a divisão é com `/`. Com `/`, a ordem das contas já não muda o resultado. `precoEmCentimos * (percentagem / 100)` também dá 298.5, porque 15 a dividir por 100 dá 0.15, e 1990 vezes 0.15 dá 298.5.

## Erros frequentes

Os erros de cada ideia estão explicados na secção dela, ao pé da ideia. Se um algoritmo teu der um resultado errado e não souberes porquê, procura o sintoma nesta lista e vai à secção indicada:

- uma variável que não mudou quando outra mudou: "Atribuição: dar um valor não é perguntar se é igual", na primeira consequência;
- duas variáveis com o mesmo valor depois de uma troca: na mesma secção, na segunda consequência;
- um `=` onde se queria perguntar, um `==` onde se queria dar um valor, ou uma conta do lado esquerdo do `=`: na mesma secção;
- o tipo escrito outra vez numa variável que já tinha nascido: "Onde nasce uma variável, e com que tipo";
- um número guardado como texto, ou um código guardado como número: "Tipos de dados";
- o mesmo número escrito à mão em vários sítios: "Constantes";
- uma divisão com parte decimal onde só cabem inteiros, um resto que parece errado, ou uma média maior do que as notas: "Expressões aritméticas";
- uma função predefinida que dá outro número: a parte dessa função, em "Funções predefinidas";
- uma linha que não sabes como se escreve: "Frases claras também valem";
- um trace que concorda sempre contigo: "A tabela de trace".

Os erros seguintes não pertencem a uma só ideia, e por isso ficam aqui.

### Uma variável usada antes de ter valor

O que se vê: no trace, a coluna da variável diz "sem valor" na linha que a usa. A conta dessa linha fica sem resultado. Imagina o algoritmo dos lugares das mesas com a conta escrita antes da leitura:

```text
const LUGARES_POR_MESA = 4
int lugares = mesas * LUGARES_POR_MESA
Escreve: "Quantas mesas tem a sala? "
int mesas = ler valor
Escreve: "Lugares sentados: ", lugares
```

Na linha da conta, `mesas` ainda não nasceu, e por isso não tem valor. O algoritmo não tem como saber quantos lugares há. O que escrever no fim não é o número de lugares daquela sala, mesmo que a pessoa escreva o número de mesas depois.

Acontece porque, numa sequência, cada instrução só pode usar os valores que já existem no momento em que é executada. Para o encontrares, procura a linha onde a variável nasce, a que tem o tipo à frente. Depois vê se está antes ou depois da linha que a usa. Para o corrigires, passa a conta para depois da leitura. A regra prática da secção "Sequência" evita-o sempre. Primeiro leem-se os dados, depois fazem-se as contas, e só no fim se escrevem os resultados.

### Uma seta solta ou uma figura com a forma errada

O que se vê: num fluxograma, uma seta que acaba no vazio, uma figura onde não chega seta nenhuma, ou uma leitura num retângulo. Quem segue o percurso com o dedo fica sem saber por onde ir, ou lê uma conta onde está uma entrada. Acontece quando se desenha à pressa, figura a figura, sem voltar a seguir o caminho todo. Para o encontrares, segue o percurso com o dedo, do Início até ao Fim, e confirma que passas por todas as figuras. Para o corrigires, liga as setas soltas e põe cada instrução na figura certa. As leituras e os `Escreve:` vão em paralelogramos, as contas vão em retângulos, e há um só Início e um só Fim.

### Um fluxograma que não diz o mesmo que o pseudocódigo

O que se vê: uma figura a mais ou a menos, duas figuras pela ordem trocada, ou uma figura com um texto diferente da instrução. Seguido com o dedo, o fluxograma dá um ecrã diferente do trace do pseudocódigo. Acontece quando um dos dois se escreve sem olhar para o outro, ou quando se muda um e se esquece o outro. Para o encontrares, compara figura a figura com instrução a instrução, como no passo 4 do exemplo guiado. Para o evitares, escreve um, desenha o outro logo a seguir e verifica-os juntos.

## Palavras novas deste guia

- Pseudocódigo: texto escrito com um vocabulário pequeno, que parece código mas não é de nenhuma linguagem; nenhum computador o executa, e serve para pensar.
- Fluxograma: o desenho de um algoritmo, com figuras ligadas por setas.
- Variável: um espaço com um nome, onde se guarda um valor que pode mudar enquanto o algoritmo é executado.
- Estado: o valor de todas as variáveis de um algoritmo num dado momento.
- camelCase: a forma de escrever um nome com várias palavras juntas, cada uma a partir da segunda com maiúscula, como `caixasCompletas`.
- Palavra reservada: uma palavra que a linguagem já usa com outro significado e que não pode ser o nome de uma variável.
- Constante: um valor com nome que não muda durante a execução do algoritmo; escreve-se com `const`, em maiúsculas.
- Tipo: o que decide que valores uma variável pode guardar e o que se pode fazer com eles.
- `int`: o tipo dos números inteiros, sem parte decimal.
- `float`: o tipo dos números com parte decimal.
- `string`: o tipo do texto, uma sequência de caracteres entre aspas.
- `bool`: o tipo que só tem dois valores, `true` e `false`.
- Declarar: dizer que uma variável existe, de que tipo é e com que valor começa.
- Atribuir: dar um valor a uma variável, com `=`; lê-se "recebe".
- Comparar: perguntar se dois valores são iguais, ou se um é maior do que o outro; a resposta é `true` ou `false`.
- `ler valor`: a instrução que recebe um valor de fora do algoritmo, escrito por uma pessoa.
- `Escreve:`: a instrução que mostra texto e valores no ecrã.
- Expressão: uma conta escrita no algoritmo, com valores, nomes de variáveis e de constantes, e operadores.
- Operador: o sinal ou a palavra que diz que conta se faz, como `+`, `*` ou `div`.
- `div`: a divisão inteira, quantas vezes um número cabe noutro.
- `resto`: o que sobra da divisão inteira.
- Função predefinida: um pedaço de algoritmo já feito, com um nome, que recebe um valor entre parênteses e devolve um resultado.
- Argumento: o valor que se dá a uma função, entre parênteses.
- Valor absoluto: a distância de um número a zero, ou seja, o número sem sinal; é o que `abs` devolve.
- Estrutura sequencial: instruções executadas uma depois da outra, de cima para baixo, cada uma exatamente uma vez.
- Sintaxe: as regras de escrita de uma linguagem; um engano nessas regras é um erro de sintaxe.
- Vocabulário: o conjunto pequeno de palavras e de sinais que usamos sempre com o mesmo significado.
- Indentação: o recuo de uma linha em relação à margem esquerda, de quatro espaços na forma das aulas.
- Bloco: um conjunto de linhas que pertencem à mesma instrução e que se executam juntas, marcado pela indentação.
- Oval: a figura do fluxograma onde o algoritmo começa, com `Início`, e acaba, com `Fim`.
- Paralelogramo: a figura do fluxograma para as entradas e as saídas, com `ler valor` ou `Escreve:`.
- Retângulo: a figura do fluxograma para as atribuições e as contas.
- Losango: a figura do fluxograma para uma decisão, que só se usa a partir do guia 03.
- Tabela de trace: uma tabela onde se executa um algoritmo à mão, com o valor de todas as variáveis depois de cada instrução.
- Caso de teste: o nome novo de um exemplo concreto do guia 01. Tem a entrada e o resultado que se espera, calculado antes de executar o algoritmo.

## Verificar o que aprendeste

1. Com `total` a valer 10, o que faz `total = total + 5`, e o que faz `total == total + 5`? Diz com que valor fica `total` depois de cada linha, e o que cada uma responde, se responder alguma coisa.
2. Que tipo usas para guardar o número de caixas de uma encomenda? E o peso de uma encomenda em quilogramas, um número de telefone e a resposta à pergunta "o cliente já pagou?"? Justifica cada escolha pelo que vais fazer com o valor.
3. Porque é que se escreve `UNIDADES_POR_CAIXA` nas contas, e não o número 12? Dá as duas razões.
4. Depois de `int a = 7`, `int b = a * 2` e `a = 1`, quanto vale `b`? Porquê?
5. Quanto dão `29 div 6` e `29 resto 6`? Como confirmas as duas contas ao mesmo tempo?
6. Porque é que `14 + 17 / 2` não é a média de 14 e 17? Como se escreve a média, e quanto dá?
7. Quanto dão `arredondar(3.5)`, `arredondar(3.49)`, `truncar(-1.8)` e `raiz(64)`? De que tipo é cada resultado?
8. Com 24 cadernos, porque é que o algoritmo das caixas de cadernos escreve "Unidades soltas: 0", em vez de saltar essa linha?
9. Um colega escreveu um algoritmo em frases. Que três perguntas fazes a cada frase para saberes se deixa dúvidas?
10. Um algoritmo sequencial tem uma linha `const` e cinco instruções. Quantas figuras e quantas setas tem o fluxograma? Em que figura vai uma leitura, e em que figura vai uma conta?
11. Este algoritmo devia calcular o preço total de uma encomenda de cadernos, sabendo que cada caderno custa 150 cêntimos:

    ```text
    const PRECO_POR_CADERNO = 150
    int total = cadernos * PRECO_POR_CADERNO
    Escreve: "Quantos cadernos? "
    int cadernos = ler valor
    Escreve: "Total em cêntimos: ", total
    ```

    Faz o trace com 4 cadernos e vê o que acontece. Em que instrução está o erro, por que razão existe e como o corriges? Que valor aparece no ecrã depois de o corrigires?

12. Uma escola precisa de distribuir cadernos pelos alunos de uma turma, um por aluno. Os cadernos vêm em caixas de 12, e a escola quer saber quantas caixas tem de encomendar para chegar para todos. Copia e completa:

    ```text
    const UNIDADES_POR_CAIXA = 12
    Escreve: "Quantos alunos tem a turma? "
    .......... alunos = ler valor
    int caixasCompletas = alunos div UNIDADES_POR_CAIXA
    int sobra = alunos .......... UNIDADES_POR_CAIXA
    int caixasAEncomendar = ..........
    Escreve: "Caixas a encomendar: ", caixasAEncomendar
    ```

    a) A primeira lacuna é o tipo de `alunos`, e a segunda é a operação que dá o que sobra. Completa-as.

    b) A linha de `caixasAEncomendar` é a que interessa. Se sobrar algum aluno sem caderno, chega encomendar as caixas completas? Escreve por palavras tuas o que tem de acontecer, antes de tentares escrevê-lo em pseudocódigo. Lembra-te de que `arredondar` não arredonda sempre para cima. Se não conseguires escrever a regra sem usar a palavra "se", deixa-a em frases claras.

    c) Antes de calcular, escreve quantas caixas achas que são precisas para uma turma de 25 alunos. Depois faz o trace completo, com uma coluna por variável. Se o resultado não for o que previste, procura onde é que o teu raciocínio se desviou.

    d) Para 24 alunos e para 12 alunos, não precisas de repetir o trace completo. Escreve só, numa tabela, os valores com que ficam `caixasCompletas`, `sobra` e `caixasAEncomendar`.

    e) Troca o teu algoritmo com o de um colega, e faz o trace do dele com uma entrada que ele não tenha testado. Zero, um número mais pequeno do que uma caixa e um múltiplo exato de 12 costumam revelar problemas. Devolve-lhe a tabela preenchida, e não apenas a conclusão, para ele ver em que linha o valor mudou.

    Se estiveres com dificuldade, volta ao exemplo guiado e muda-lhe só o nome das variáveis, mantendo a estrutura. Quando isso estiver certo, acrescenta a linha das caixas a encomendar. Uma dificuldade de cada vez.

## O que vem a seguir

Para praticar este tema, faz a [ficha de exercícios](02-pseudocodigo-e-fluxogramas-exercicios.md). O [laboratório](02-pseudocodigo-e-fluxogramas-laboratorio.md) é de fluxogramas e é opcional: só o fazes quando o professor o indicar. Nele desenhas no diagrams.net o fluxograma das caixas de cadernos e confirmas que diz o mesmo que o pseudocódigo.

O tema seguinte é [Decisões e validação](03-decisoes-e-validacao.md). Todos os algoritmos deste guia fazem sempre as mesmas contas, por mais estranha que seja a entrada. Se alguém escrever -30 cadernos, o contrato diz que a entrada não é válida, mas o algoritmo não tem forma de o verificar. Para verificar uma entrada, ou para fazer coisas diferentes consoante os dados, o algoritmo precisa de tomar decisões. É isso que vais aprender no guia 03.

## Para saber mais

- [A unidade de algoritmos no Catálogo Nacional de Qualificações](https://catalogo.snq.gov.pt/ucDetalhe/355272): o texto oficial do que esta unidade ensina.

![Rodapé](../imagens/rodape.png)
