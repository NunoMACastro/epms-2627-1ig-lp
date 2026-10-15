![Cabeçalho](../../../imagens/cabecalho.png)

# Algoritmos da aula de intervalos e validação

Oito algoritmos curtos, cada um com uma ideia só, sobre os intervalos, as fronteiras e a validação dos dados. É usado nos temas [03 Decisões e validação](../../../01-algoritmos/03-decisoes-e-validacao.md) e [04 Repetição e padrões](../../../01-algoritmos/04-repeticao-e-padroes.md).

Todos usam a mesma situação: um ar condicionado que aceita temperaturas de 16 a 30 graus, incluindo o 16 e o 30. Nos algoritmos 4, 5 e 6 há mais uma regra. A partir de 24 graus, incluindo o 24, o aparelho entra em modo económico.

## O que está nesta pasta

- `1-dentro-do-intervalo.txt`: um intervalo com os dois extremos incluídos, escrito com duas comparações ligadas por `e` (guia das decisões, "Intervalos").
- `2-fora-do-intervalo.txt`: o contrário do intervalo, escrito com `ou` (guia das decisões, "O contrário de um intervalo").
- `3-e-em-vez-de-ou.txt`: um engano de propósito, o contrário do intervalo escrito com `e` (guia das decisões, nos erros frequentes).
- `4-erro-na-fronteira.txt`: outro engano de propósito, no limite do modo económico (guia das decisões, "Fronteiras e casos de teste").
- `5-sem-validacao.txt`: o que faz um algoritmo que não valida a temperatura antes de a usar (guia das decisões, "Validar os dados antes de os usar").
- `6-validar-primeiro.txt`: a validação como primeira condição, antes de qualquer decisão que use o valor (guia das decisões, "Validar os dados antes de os usar").
- `7-validacao-repetida.txt`: um ciclo que volta a pedir a temperatura até ela ser válida (guia da repetição, "Padrão validação repetida").
- `8-leitura-esquecida.txt`: um terceiro engano de propósito, dentro do ciclo (guia da repetição, nos erros frequentes).

## Como correr

Estes algoritmos não correm num computador. São pseudocódigo, como os dos guias, e abrem-se aqui no GitHub ou em qualquer editor de texto. Para perceberes cada um, segue-o à mão, com um valor de cada vez, e escreve em papel o que aparece no ecrã.

Escolhe os valores como o guia ensina, junto de cada limite: o valor imediatamente abaixo, o próprio limite e o valor imediatamente acima. Para os limites 16 e 30, são o 15, o 16 e o 17, e o 29, o 30 e o 31.

O que deves ver: no algoritmo 1, o 16, o 17, o 29 e o 30 dão "Temperatura aceite". O 15 e o 31 dão "Temperatura fora do intervalo".

Os algoritmos 3, 4 e 8 estão errados de propósito, e o erro não se vê com qualquer valor. Experimenta cada um com vários valores, dentro e fora do intervalo, até encontrares aquele que mostra o erro. Depois diz qual é a linha que está mal e como a corrigias.

Para o algoritmo 7, faz a tabela de iterações, como no guia da repetição. A pessoa escreve primeiro um valor acima de 30, depois um abaixo de 16 e por fim um válido.

## Versões com que foi testado

O pseudocódigo não depende de nenhum programa, por isso não há versões. Os resultados de cada algoritmo foram conferidos a 8 de outubro de 2026, com os valores junto de cada limite.

![Rodapé](../../../imagens/rodape.png)
