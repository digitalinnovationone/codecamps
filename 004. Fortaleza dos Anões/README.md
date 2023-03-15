## A Fortaleza dos Anões

Durante suas aventuras você chegou em uma grande colônia de anões. Uma caverna gigantesca que a cada dia está sendo mais escavada em busca de pedras e materiais preciosos. Porém, para ser aceito, você precisa se provar digno de que será útil para todos e não somente um peso para o grupo.

Nessa colônia existem diversas profissões e coisas para se fazer. Uma das coisas mais importantes é a produção de cerveja e cogumelos, a fonte de toda energia para escavar dos anões. A segunda coisa mais importante é possuir habilidades com uma picareta e músculos para passar semanas escavando.

Uma coisa com que eles não contavam é que você é um mestre da magia da programação. Isso te da habilidades e poderes que nenhum anão jamais presenciou. Ajude-os com suas tarefas diárias e aprenda com eles a arte da escavação. 

### A Entrada da Caverna

- **If e Lógica**

Ao chegar na entrada da grande Cidade dos Anões você se depara com os guardas apartando uma briga. Um dos guardas te diz que eles são dois irmãos nunca conseguem chegar a um acordo para dividir seus espólios de suas aventuras pela Terra Média. Você propõe para eles a seguinte solução: Aquele que coletou mais tesouros ficaria com 10% de todo o tesouro. Após esse calculo seria realizado a separação do tesouro de acordo com as porcentagens de coleta de cada um individualmente. 

Ajude-os, usando seus poderes de código, criando uma máquina capaz de realizar os cálculos de cada uma de suas aventuras para que os irmãos não briguem mais.

Código:

```cpp
#include <iostream>
using namespace std;

double calculoTesouro(double tesouroEncontrado, double tesouros, double porcentagem) {
    double tesouroTotal = tesouros - (tesouros * porcentagem);
    return tesouroTotal * (tesouroEncontrado / 10);
}

int main() {
    double irmao1TesourosEncontrados, irmao2TesourosEncontrados, tesouros, porcentagem = 0.1;
    double irmao1 = 0, irmao2 = 0;

    cin >> irmao1TesourosEncontrados;
    cin >> irmao2TesourosEncontrados;
    cin >> tesouros;

    if (irmao1TesourosEncontrados > irmao2TesourosEncontrados) {
        tesouros *= porcentagem;
        irmao1 += tesouros + calculoTesouro(irmao1TesourosEncontrados, tesouros, porcentagem);
        irmao2 += calculoTesouro(irmao2TesourosEncontrados, tesouros, porcentagem);
    } else {
        tesouros *= porcentagem;
        irmao1 += calculoTesouro(irmao1TesourosEncontrados, tesouros, porcentagem);
        irmao2 += tesouros + calculoTesouro(irmao2TesourosEncontrados, tesouros, porcentagem);
    }

    cout << irmao1 << endl;
    cout << irmao2 << endl;

    return 0;
}
```

- **String, Number, Lógica**

Adentrando a caverna, quando somente a luz das tochas iluminam o ambiente, você se depara com um grupo de guardas jogando uma espécie de jogo com dados feitos de pedra. Os guardas são barbudos e estão uniformizados e ao te verem eles dizem que estão jogando um jogo que um forasteiro os ensinou. O guarda, que parece o chefe, te mostra as regras do jogo. Ao ler as regras você nota que eles estão jogando errado, logo que eles jogam os dados e tentam se acertar com socos e pontapés.

As regras são as seguintes:

Um dado preto e um dado cinza. 
Se o dado preto for jogado com a mão esquerda e cair um número par, ele ganha 2 pontos a mais. Se for jogado com a mão direita e cair um número ímpar, ele ganha 3 pontos a mais.

Se o dado cinza for jogado com a mão esquerda e cair um número par, ele ganha 3 pontos a mais.
Se for jogado com a mão direita e cair um número ímpar, ele ganha 2 pontos a mais.

Os dois dados, se forem jogados com uma mão e cair o número contrário a regra, ele se mantém o mesmo valor.

A pessoa que tirar o maior valor, em 2 rodadas, ganha. Se os dois possuírem o mesmo valor, empate.

Crie um código que, seguindo as regras descritas no documento do forasteiro, diga aos Anões quem é o vencedor.

Código:

```cpp
#include <iostream>
#include <string>

using namespace std;

int dwarfDice(string dice, string dwarf, int dwarfNumber) {
    if (dice == "black") {
        if (dwarf == "left") {
            dwarfNumber += 3;
        } else if (dwarf == "right") {
            dwarfNumber += 2;
        }
    } else if (dice == "gray") {
        if (dwarf == "left") {
            dwarfNumber += 2;
        } else if (dwarf == "right") {
            dwarfNumber += 3;
        }
    }
    return dwarfNumber;
}

int main() {
    int dwarfOne = 0;
    string dwarfOneDice, dwarfOneHand;
    cin >> dwarfOneDice >> dwarfOneHand;
    int dwarfOneNumber;
    cin >> dwarfOneNumber;

    int dwarfTwo = 0;
    string dwarfTwoDice, dwarfTwoHand;
    cin >> dwarfTwoDice >> dwarfTwoHand;
    int dwarfTwoNumber;
    cin >> dwarfTwoNumber;

    for (int i = 0; i < 2; i++) {
        dwarfOne += dwarfDice(dwarfOneDice, dwarfOneHand, dwarfOneNumber);
        dwarfTwo += dwarfDice(dwarfTwoDice, dwarfTwoHand, dwarfTwoNumber);
    }

    if (dwarfOne == dwarfTwo) {
        cout << "Empate de Dwarf" << endl;
    } else if (dwarfOne > dwarfTwo) {
        cout << "Dwarf One é o melhor" << endl;
    } else if (dwarfOne < dwarfTwo) {
        cout << "Dwarf Two é o melhor" << endl;
    }

    return 0;
}
```

- **Array**

Caminhando por algumas horas em direção ao coração da Montanha, você chega a uma humilde e aconchegante estalagem conhecida como Estalagem da Bifurcação, onde existem diversos caminhos a serem percorridos a partir dela. Entrando nela é possível ver um anão visivelmente preocupado, bigodudo e vermelho berrando e esperneando. Ao ouvi-lo você descobre que ele está assim porque seu melhor funcionário partiu para uma aventura para caçar o grande Dragão Vermelho e deixou instruções extremamente confusas sobre todo o estoque da estalagem.

As instruções eram as seguintes:

Itens comprados: [X, Y, Z]

Itens utilizados: [A, B, C]

Itens estoque: […,…,…]

Utilizando o poder da programação você decidiu ajudar o dono da estalagem em troca de uma noite de descanso. Para isso, crie um programa que subtraia os índices das listas existentes e crie uma nova lista com os novos valores.

Código:

```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main() {
    string entrada1, entrada2;
    getline(cin, entrada1);
    getline(cin, entrada2);

    vector<string> arr1, arr2;
    string num;
    for (char c : entrada1) {
        if (c == ',') {
            arr1.push_back(num);
            num = "";
        } else {
            num += c;
        }
    }
    arr1.push_back(num);
    num = "";
    for (char c : entrada2) {
        if (c == ',') {
            arr2.push_back(num);
            num = "";
        } else {
            num += c;
        }
    }
    arr2.push_back(num);

    vector<int> newArr;
    for (int i = 0; i < arr1.size(); i++) {
        int produto = stoi(arr1[i]) - stoi(arr2[i]);
        newArr.push_back(produto);
    }

    for (int i = 0; i < newArr.size(); i++) {
        cout << newArr[i];
        if (i != newArr.size() - 1) {
            cout << ",";
        }
    }

    return 0;
}
```
