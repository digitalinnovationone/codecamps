# Dificuldade Média: Ordem na Fortaleza!

## Ordenação de Poções com Bubble Sort

### Descrição
Na Fortaleza dos CodeMiners, há uma área especializada em alquimia, onde os aprendizes criam poções mágicas (extraídas dos óleos essenciais dos cogumelos da Grande Montanha) para aprimorar suas habilidades. As poções são armazenadas em frascos numerados e os aprendizes precisam organizá-las em ordem crescente de acordo com a numeração. Sua missão é criar um algoritmo em C que implemente o **Bubble Sort**¹ para ordenar os frascos de poção. Este algoritmo ajudará os aprendizes a manterem a área de alquimia organizada e eficiente.

¹ _**É um dos algoritmos de ordenação mais simples e é fácil de entender. Ele compara pares de elementos adjacentes e troca-os se estiverem fora de ordem, repetindo esse processo até que toda a lista esteja ordenada. Apesar de não ser eficiente, é um bom ponto de partida para o estudo de algoritmos de ordenação.**_ Saiba mais [aqui](https://pt.wikipedia.org/wiki/Bubble_sort).

### Entrada
 - 1ª Linha: Número inteiro N (1 <= N <= 1000), representando a quantidade de frascos de poção.
 - 2ª Linha: Lista com N números inteiros NÃO ORDENADOS e separados por espaços, representando a numeração de cada frasco de poção.

### Saída
 - Imprima a lista de frascos de poção ordenada em ordem crescente, com cada número separado por um espaço.

### Exemplos

| **Entrada** | **Saída** |
|---|---|
| 5 <br> 5 3 4 1 2 | 1 2 3 4 5 |
| 7 <br> 10 20 30 40 50 60 7 | 7 10 20 30 40 50 60 |
| 9 <br> 1000 1 10 100 0 4 4000 400 40 | 0 1 4 10 40 100 400 1000 4000 |

## Ordenação de Relíquias com Insertion Sort

### Descrição
Na Fortaleza dos CodeMiners, o processo de mineração de dados, eventualmente, coleta relíquias místicas que possuem poderes incríveis. Essas relíquias são numeradas de acordo com sua raridade e os estudiosos desejam organizá-las em ordem crescente para facilitar a pesquisa e o estudo. Sua missão é criar um algoritmo em C que implemente o **Insertion Sort**¹ para ordenar as relíquias. Com esse algoritmo, os estudiosos poderão manter suas relíquias organizadas e acessíveis, permitindo um estudo mais eficiente das propriedades místicas.

¹ **_Um passo à frente do Bubble Sort, o Insertion Sort é outro algoritmo simples de entender e implementar. Ele funciona construindo uma sublista ordenada, inserindo elementos um a um em suas posições corretas. Apesar de ainda não ser o mais eficiente, é uma evolução natural no aprendizado após o Bubble Sort._** Saiba mais [aqui](https://pt.wikipedia.org/wiki/Insertion_sort).

### Entrada
 - 1ª Linha: Número inteiro N (1 <= N <= 1000), representando a quantidade de relíquias.
 - 2ª Linha: Lista com N números inteiros NÃO ORDENADOS e separados por espaços, representando a raridade de cada relíquia.

### Saída
 - Imprima a lista de relíquias ordenada em ordem crescente, com cada número separado por um espaço.

### Exemplos

| **Entrada** | **Saída** |
|---|---|
| 5 <br> 5 3 4 1 2 | 1 2 3 4 5 |
| 7 <br> 10 20 30 40 50 60 7 | 7 10 20 30 40 50 60 |
| 9 <br> 1000 1 10 100 0 4 4000 400 40 | 0 1 4 10 40 100 400 1000 4000 |

## Ordenação de Armaduras com Selection Sort

### Descrição
Os guerreiros da Fortaleza dos CodeMiners precisam manter suas armaduras em ordem, para facilitar a escolha do equipamento certo antes das batalhas. As armaduras são numeradas de acordo com seu nível de proteção, e os guerreiros desejam organizá-las em ordem decrescente. Sua missão é criar um algoritmo em C que implemente o **_Selection Sort_**¹ para ordenar as armaduras. Com esse algoritmo, os guerreiros poderão encontrar a armadura mais adequada rapidamente, o que pode ser crucial em uma situação de combate.

¹ _**Este algoritmo é um pouco mais avançado que os anteriores. Ele divide a lista em duas partes: a parte ordenada e a parte não ordenada. A cada iteração, o algoritmo seleciona o menor (ou maior) elemento da parte não ordenada e o move para o final da parte ordenada. Isso ajuda a entender melhor a divisão do trabalho em algoritmos de ordenação.**_ Saiba mais [aqui](https://pt.wikipedia.org/wiki/Selection_sort).

### Entrada
 - 1ª Linha: Número inteiro N (1 <= N <= 1000), representando a quantidade de armaduras.
 - 2ª Linha: Lista com N números inteiros NÃO ORDENADOS e separados por espaços, representando o nível de proteção de cada armadura.

### Saída
 - Imprima a lista de armaduras ordenada em ordem decrescente, com cada número separado por um espaço.

### Exemplos

| **Entrada** | **Saída** |
|---|---|
| 5 <br> 5 3 4 1 2 | 5 4 3 2 1 |
| 7 <br> 10 20 30 40 50 60 7 | 60 50 40 30 20 10 7 |
| 9 <br> 1000 1 10 100 0 4 4000 400 40 | 4000 1000 400 100 40 10 4 1 0 |

## Busca Binária na Biblioteca

### Descrição
Em meio aos corredores da Fortaleza dos CodeMiners, você encontra uma magnífica biblioteca repleta de livros, pergaminhos e discos de Mithril, todos meticulosamente organizados. Esta biblioteca é gerida por Hella, uma CodeMiner conhecida por sua sagacidade, paixão e habilidades literárias. Você a encontra trabalhando em seu novo livro, "O Senhor dos Dados: O Retorno do Array", que precisa ser finalizado até o fim do dia para ser lançado na "CodeMiners I/O". Neste evento, jovens talentos serão treinados em mineração de dados no majestoso salão nobre da Fortaleza.

Percebendo a preocupação da escritora com o tempo, você se oferece para ajudá-la. Hella, então, propõe um acordo: se você desenvolver uma solução capaz de identificar a presença de conteúdos do tipo 777 (projetos práticos sobre a temática do seu novo livro) nas estantes da biblioteca, ela lhe concederá uma cadeira de honra na "CodeMiners I/O". Sua missão é criar um algoritmo em C que implemente, preferencialmente, uma **Busca Binária**¹ para verificar se uma determinada estante possui um conteúdo do tipo 777. Com isso, você ajudará Hella a encontrar de forma eficiente as localizações dos materiais complementares para o lançamento do livro, além de garantir sua cadeira de honra no evento.

¹ **_Busca Binária é um algoritmo eficiente para encontrar um elemento em uma lista ordenada. Ele divide a lista ao meio e compara o elemento do meio com o valor desejado. Dependendo da comparação, ele descarta metade da lista e repete o processo até encontrar o elemento desejado ou reduzir a lista a zero. Isso ensina a importância da otimização de algoritmos de busca e como a ordenação pode ser útil nesse contexto._** Saiba mais [aqui](https://pt.wikipedia.org/wiki/Pesquisa_bin%C3%A1ria).

### Entrada
 - 1ª Linha: Número inteiro N (1 <= N <= 1000), representando a quantidade de conteúdos na estante da biblioteca.
 - 2ª Linha: Lista com N números inteiros NÃO ORDENADOS e separados por espaços, representando os tipos de cada conteúdo de uma estante da biblioteca. Entretanto, prevendo a necessidade de ordenação dos conteúdos para uma **Busca Binária** efetiva, Hella já aplicou um de seus algoritmos de ordenação no código base deste desafio.

### Saída
 - Se o conteúdo do tipo 777 for encontrado na lista, imprima "S" (sem as aspas). Caso contrário, imprima "N" (sem as aspas).

### Exemplos

| **Entrada** | **Saída** |
|---|---|
| 10 <br> 70 63 56 49 42 35 28 21 14 7 | N |
| 7 <br> 776 772 773 775 774 771 **777** | S |
| 7 <br> 177 377 677 **777** 277 477 577  | S |
| 6 <br> 7 57 89 90 98 102 | N |
