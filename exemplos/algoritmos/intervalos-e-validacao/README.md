![Cabeçalho](../../../imagens/cabecalho.png)

# Algoritmos da aula de intervalos e validação

Estes são os algoritmos preparados para a aula dos intervalos e da validação. A matéria está explicada no [guia das decisões](../../../01-algoritmos/03-decisoes-e-validacao.md), nas secções "Intervalos", "A reta com as regiões", "O contrário de um intervalo", "Fronteiras e casos de teste" e "Validar os dados antes de os usar", e no [guia da repetição](../../../01-algoritmos/04-repeticao-e-padroes.md), na secção "Padrão validação repetida".

São mais curtos do que os dos guias, e cada um mostra uma ideia só. Todos usam a mesma situação: um ar condicionado que aceita temperaturas de 16 a 30 graus, incluindo o 16 e o 30. Nos algoritmos 4, 5 e 6 há mais uma regra: a partir de 24 graus, incluindo o 24, o aparelho entra em modo económico.

Os ficheiros abrem-se aqui no GitHub ou em qualquer editor de texto. Não se executam: são pseudocódigo, como os dos guias. Para perceberes cada um, segue-o com um valor de cada vez, em papel, e escreve o que aparece no ecrã. Escolhe os valores como o guia ensina, junto de cada limite: o valor imediatamente abaixo, o próprio limite e o valor imediatamente acima. Para os limites 16 e 30, são o 15, o 16 e o 17, e o 29, o 30 e o 31.

| Ficheiro | O que mostra | No guia |
| --- | --- | --- |
| `1-dentro-do-intervalo.txt` | Um intervalo com os dois extremos incluídos, escrito com duas comparações ligadas por `e` | Decisões, "Intervalos" |
| `2-fora-do-intervalo.txt` | O contrário do intervalo, escrito com `ou` | Decisões, "O contrário de um intervalo" |
| `3-e-em-vez-de-ou.txt` | Um engano de propósito: o contrário do intervalo escrito com `e` | Decisões, "Erros comuns", "`e` onde é preciso `ou`" |
| `4-erro-na-fronteira.txt` | Outro engano de propósito, no limite do modo económico | Decisões, "Fronteiras e casos de teste" |
| `5-sem-validacao.txt` | O que faz um algoritmo que não valida a temperatura antes de a usar | Decisões, "Validar os dados antes de os usar" |
| `6-validar-primeiro.txt` | A validação como primeira condição, antes de qualquer decisão que use o valor | Decisões, "Validar os dados antes de os usar" |
| `7-validacao-repetida.txt` | Um ciclo que volta a pedir a temperatura até ela ser válida | Repetição, "Padrão validação repetida" |
| `8-leitura-esquecida.txt` | Um terceiro engano de propósito, dentro do ciclo | Repetição, "Erros comuns" |

Os algoritmos 3, 4 e 8 estão errados de propósito, e o erro não se vê com qualquer valor. Experimenta cada um com vários valores, dentro e fora do intervalo, até encontrares aquele que mostra o erro. Depois diz qual é a linha que está mal e como a corrigias.

Para o algoritmo 7, faz a tabela de iterações, como no guia da repetição, quando a pessoa escreve primeiro um valor acima de 30, depois um abaixo de 16 e por fim um válido.

[Voltar à área de algoritmos](../../../01-algoritmos/README.md)

![Rodapé](../../../imagens/rodape.png)
