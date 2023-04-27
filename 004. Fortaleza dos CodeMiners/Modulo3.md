# Módulo III: Programação Orientada a Objetos Mágicos em C++							

## Batalha Final: Enfrentando o Boss Overfitting

Após uma noite de gala no lançamento do livro de Hella na CodeMiners I/O, os trabalhos de mineração de dados voltaram a todo vapor. Com novas técnicas e boas práticas exploradas na conferência, a eficiência na mineração aumentou consideravelmente. Foi então que, finalmente, os CodeMiners localizaram a lendária masmorra do temido Boss Overfitting.

Overfitting é um Boss astuto, conhecido por sua capacidade de se adaptar excessivamente às estratégias de seus adversários, tornando-se imprevisível e difícil de ser derrotado. Os CodeMiners, durante séculos de mineração de dados, documentaram suas descobertas e identificaram as fraquezas do Boss Overfitting. Essas informações são valiosas, pois indicam quais equipamentos devem ser usados pelos CodeMiners para derrotá-lo.

O desafio consiste em criar um programa em C++ que utilize Orientação a Objetos e algoritmos de busca (busca linear, binária ou outros mais eficientes) para determinar se os CodeMiners têm em seu arsenal os equipamentos necessários para derrotar o Boss Overfitting. Para isso, teremos em nosso template de código as classes `FortalezaCodeMiner` e `Boss` com atributos relacionados às nossas entradas, além do método `possui_equipamento` preparado para implementação de seu algoritmo de busca escolhido.

### Entrada
O programa receberá duas linhas: 
1. A primeira contendo os pontos fracos do Boss (inteiros separados por espaços); 
2. A segunda com os equipamentos disponíveis no Arsenal dos CodeMiners (inteiros separados por espaços).

### Saída
O objetivo é verificar se a lista de equipamentos possui TODOS os itens necessários para eliminar os pontos fracos do Boss. Se sim, o programa deve imprimir "Vencemos!". Caso contrário, deve imprimir "Perdemos!".

### Exemplos

| **Entrada** | **Saída** |
|---|---|
| 1 2 3 5<br>1 2 3 4 5 6 7 8 9 10 | Vencemos |
| 1 2 3 5<br>1 3 4 6 8 7 9 10 2 5	 | Vencemos |
| 1 3 5 7<br>1 2 4 6 8 9 10  | Perdemos |
| 1 3 5 7<br>6 4 8 1 9 10 2 7 | Perdemos |

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <string>

using namespace std;

class FortalezaCodeMiner {
public:
    FortalezaCodeMiner(const vector<int>& equipamentos) : equipamentos_(equipamentos) {}

    bool possui_equipamento(int id_equipamento) {
        //TODO: Implementar um algoritmo de busca que identifique se o equipamento existe ou não no Arsenal.
        return false;
    }

private:
    vector<int> equipamentos_;
};

class Chefe {
public:
    Chefe(const vector<int>& pontos_fracos) : pontos_fracos_(pontos_fracos) {}

    const vector<int>& pontos_fracos() const {
        return pontos_fracos_;
    }

private:
    vector<int> pontos_fracos_;
};

int main() {
    vector<int> pontos_fracos_chefe = {3, 6, 2, 9, 1};
    vector<int> equipamentos_arsenal = {1, 2, 2, 3, 4, 5, 6, 6, 7, 8, 9, 10};

    Chefe chefe(pontos_fracos_chefe);
    Arsenal arsenal(equipamentos_arsenal);

    bool vitoria = true;
    for (int ponto_fraco : chefe.pontos_fracos()) {
        if (!arsenal.possui_equipamento(ponto_fraco)) {
            vitoria = false;
            break;
        }
    }

    cout << (vitoria ? "Vitória" : "Derrota") << endl;

    return 0;
}
```
