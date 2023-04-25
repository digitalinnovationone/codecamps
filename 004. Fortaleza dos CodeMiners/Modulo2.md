# Dificuldade Média: Busca e Ordenação na Fortaleza!

## Busca Binária na Biblioteca

### Descrição
Em meio aos corredores da Fortaleza dos CodeMiners, você encontra uma magnífica biblioteca repleta de livros, pergaminhos e discos de Mithril, todos meticulosamente organizados. Esta biblioteca é gerida por Hella, uma CodeMiner conhecida por sua sagacidade, paixão e habilidades literárias. Enquanto explora a fortaleza em busca de desafios, você a encontra trabalhando em seu novo livro, "O Senhor dos Dados: O Retorno do Array", que precisa ser finalizado até o fim do dia para ser apresentado na "CodeMiners I/O". Neste evento, jovens talentos serão treinados em mineração de dados no majestoso salão nobre da Fortaleza.

Percebendo sua preocupação, você se oferece para ajudá-la. Hella, então, propõe um acordo: se você desenvolver uma solução capaz de identificar a presença de conteúdos do tipo 7 (projetos práticos sobre mineração de dados) nas estantes da biblioteca, ela lhe concederá uma cadeira de honra na "CodeMiners I/O". Sua missão é criar um algoritmo em C que implemente uma busca binária para verificar se uma determinada estante contém ou não um conteúdo do tipo 7, auxiliando Hella a identificar de forma eficiente materiais complementares para sua apresentação e garantindo sua cadeira de honra no evento.

### Entrada
Primeira linha com um número inteiro N (1 <= N <= 100), representando a quantidade de conteúdos na estante da biblioteca.

Segunda linha com uma lista com N números inteiros em ordem crescente (graças a Moradin, Hella é muito organizada), representando os tipos de conteúdo de uma estante da biblioteca, separados por espaço. Lembrando que, o número 7 representa o tipo que estamos buscando.

### Saída
Se o conteúdo do tipo 7 for encontrado, imprima "S" (sem as aspas). Caso contrário, imprima "N" (sem as aspas).

### Exemplos

| **Entrada** | **Saída** |
|---|---|
| 10 <br> 1 2 3 4 5 6 **7** 8 9 0 | S |
| 7 <br> 95 96 97 98 99 100 101 | N |
| 5 <br> 7 20 45 76 210 | S |
| 6 <br> 34 57 89 90 98 102 | N |

### Busca Linear

Caminhando em direção a Fortaleza você chega em uma plantação de cevada e encontra uma criatura magra, alta e tão barbuda quanto um anão. Essa criatura parece muito desesperada e anda de um lado para o outro segurando um bloco imenso de papeis. Ao perguntar qual o problema, a criatura te diz que está perdida, que será punida por seu erro. Ela é responsável por contabilizar quais grãos de cevada já foram colhidos e quais não, porém acabou dormindo muito e não dará tempo dele fazer a contagem. Você se oferece para ajuda-lo com seu problema e ele te explica:

Existem dois montes de papeis: Um para as fileiras e um para os números.

As fileiras são listas de números que representam cada um dos pés da cevada e os números são quais desses pés que devem ser verificados se já foram colhidos ou não. Os grãos que já tiverem sido colhidos não estarão mais na lista.

Crie um algoritmo que verifique se o número está na lista, ou não printando no console se os grãos já foram colhidos ou não.

**Código**

```cpp
#include <iostream>
using namespace std;

int buscaLinear(int arr[], int n, int x)
{
    int i;
    for (i = 0; i < n; i++)
        if (arr[i] == x)
            return i;
    return -1;
}

int main()
{
    int arr[] = { 2, 3, 4, 10, 40 };
    int x = 1;
    int n = sizeof(arr) / sizeof(arr[0]);
    int resultado = buscaLinear(arr, n, x);
    (resultado == -1) ? cout << "Grãos ainda não colhidos" : cout << "Grãos já colhidos" << resultado;
    return 0;
}
```

### Ordenação por Seleção

Chegando próximo aos portões você encontra uma multidão diversa. Muitas criaturas bem vestidas, outras cheias de lama e outras com guarda costas mal encarados. Todas elas possuem uma senha na mão e estão reclamando que querem entrar antes uns dos outros. Os guardas Anões da Fortaleza estão correndo de um lado pro outro e todos, sem exceção, estão nervosos e sem saber o que fazer. Você chega até o mais bigodudo de todos, que aparenta ser o líder, e oferece sua ajuda. 

Ele te diz que as senhas foram distribuídas para chamar, em ordem, cada uma das criaturas presentes para validar os seus convites um de cada vez. Porém, tudo acabou ficando confuso e virou uma bagunça generalizada.

Ajude os guardas a organizar a lista em ordem crescente de acordo com os números dessas listas.

**Código**

```cpp
#include <iostream>
using namespace std;

void ordenacaoPorSelecao(int arr[], int n)
{
    int i, j, min_idx;
    for (i = 0; i < n-1; i++)
    {
        min_idx = i;
        for (j = i+1; j < n; j++)
            if (arr[j] < arr[min_idx])
                min_idx = j;
        swap(arr[min_idx], arr[i]);
    }
}

void imprimirArray(int arr[], int n)
{
    for (int i = 0; i < n; i++)
        if (i != n) {
            cout << arr[i] << " ";
        } else {
            cout << arr[i];
        }
    cout << endl;
}

int main()
{
    int arr[] = {64, 25, 12, 22, 11, 2, 4, 6, 2, 0, 67, 102};
    int n = sizeof(arr)/sizeof(arr[0]);
    ordenacaoPorSelecao(arr, n);
    cout << "Lista de Convidados Ordenada: \n";
    imprimirArray(arr, n);
    return 0;
}
```

### Ordenação por Inserção
