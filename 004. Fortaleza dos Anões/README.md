# Fortaleza dos CodeMiners

Enquanto você caminha, ao longe, avista a Grande Montanha, um colosso rochoso que se eleva até a altura das nuvens. Essa Montanha é o lar dos CodeMiners, uma comunidade resiliente e habilidosa que habita a Fortaleza dos CodeMiners. A cada dia, eles escavam mais fundo em busca de recursos valiosos, incluindo informações ancestrais sobre a Grande Montanha. Para ser aceito, você precisa provar que será útil para todos e não apenas um peso para o grupo.

Nesta colônia, existem diversas profissões e atividades. A produção de cerveja e cultivo de cogumelos são essenciais, pois são a fonte de toda energia necessária para escavar. Além disso, é importante possuir destreza com a picareta e alguma habilidade na operação de máquinas pesadas, equipamentos fundamentais para mineração de dados raros sobre Grande Montanha. Esses dados são mais valiosos que qualquer pedra preciosa, pois podem determinar o futuro do lar dos CodeMiners.

Atualmente, eles enfrentam muitos problemas com suas máquinas pesadas, que, apesar de serem codificadas em C/C++, utilizam apenas técnicas de força bruta e algoritmos pouco performáticos. É aí que você pode fazer a diferença, pois você é um mestre na arte da programação! Isso te confere habilidades e poderes que nenhum CodeMiner jamais presenciou. Ajude-os com seus desafios diários e aprenda com eles a arte da escavação, enquanto desvenda os segredos da Fortaleza dos CodeMiners.

## Desafios Básicos

### 1. Ajuste das Máquinas

#### Descrição
As máquinas pesadas da Fortaleza dos CodeMiners precisam de ajustes em suas configurações. Proativamente, você sugere uma solução que calcule a média de consumo energético considerando 3 máquinas. Desta forma, será possível analisar e planejar a estratégia de escavação mais eficiente, pois diferentes combinações de máquinas poderiam ser avaliadas por meio do mesmo algoritmo.

#### Entrada
Três valores inteiros positivos, representando o consumo de energia de cada máquina, separados por espaços.

#### Saída
A média de consumo das três máquinas, formatada com duas casas decimais.

#### Exemplos

| Entrada | Saída |
|---|---|
| 10 20 30 | 20.00 |
| 15 25 35 | 25.00 |
| 5 10 20 | 11.67 |

## Desafios Intermediários

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

### Busca Binária

Continuando sua caminhada, você encontra um casebre com uma senhora Anão sentada na varanda olhando para uma imensa plantação de abóboras. Chegando mais perto você nota que algumas delas são douradas e brilham majestosamente. Ela te diz que hoje haverá uma grande festa no salão Nobre da Fortaleza e que as abóboras são utilizadas para fazer a melhor cerveja do continente e que as abóboras douradas são exclusivamente da realeza.

Ela te diz que está bem cansada e que seu grande sonho era guerrear contra os Elfos nos campos da Luz Brilhante e que se você fizer o serviço dela, enquanto ela arruma seu equipamento de batalha, ela te dará o convite para você entrar na grandiosa festa.

O trabalho da senhora é verificar onde estão as abóboras douradas. Ela possui listas com números de abóboras que representam cada fileira da plantação. O número 10 SEMPRE representa as abóboras douradas.

Crie um algoritmo que verifique se a abóbora dourada está presente naquela fileira da plantação e em qual index ela está localizada para ser recolhida.

**Código**

```cpp
#include <iostream>
using namespace std;

int buscaBinaria(int arr[], int left, int right, int x) {
   while (left <= right) {
      int mid = left + (right - left) / 2;
      if (arr[mid] == x)
         return mid;
      else if (arr[mid] < x)
         left = mid + 1;
      else
         right = mid - 1;
   }
   return -1;
}

int main() {
   int arr[] = { 2, 5, 7, 10, 1, 11, 12 };
   int n = sizeof(arr) / sizeof(arr[0]);
   int x = 10;
   int result = buscaBinaria(arr, 0, n - 1, x);
   if (result == -1)
      cout << "Abóbora dourada não encontrada";
   else
      cout << "Abóbora dourada encontrada na posição " << result;
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
