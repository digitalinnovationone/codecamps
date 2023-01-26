## O Vale do Jacarandá Dourado

Você é um ativista a favor da natureza e se juntou com um grupo para resolver problemas que a grande empresa Oil Corp está causando no Vale do Jacarandá Dourado, um lugar mágico com uma fauna e uma flora excepcionais e importantes para a regulação e manutenção da vida na região.

### Parte 1 - Chegando no Acampamento

- **String**

Em um primeiro momento, é necessário imprimir um cartão com o nome de todos os ativistas para que vocês se reconheçam, logo que é a primeira vez que estão se vendo.

Crie um código que, com duas entradas Nome, Sobrenome e ID, print no console concatenando essas três variáveis.

Venilton, uma pessoa já experiente, te diz que é possível utilizar a interpolação de strings, uma coisa bem útil para colocar variáveis na String durante o print. Para utilizar basta fazer assim:

`Aqui você coloca a string normalmente e quando quiser usar uma variável, use ${variavel}`

Código:

```jsx
let nome = gets();
let sobrenome = gets();
let id = parseInt(gets());

print(`Nome: ${nome} ${sobrenome} ID: ${id}`)
```

- **Lógica com If/else**

Agora, precisamos separar a equipe em diversos grupos. Os IDs pares devem ir para o acampamento da direita e os ímpares devem ir para os da esquerda. Para isso crie um código que verifique o ID do ativista e indique para onde ele deve ir.

Código:

```jsx
let id = gets();

if (id % 2 === 0) {
    print"Direita");
} else {
    print("Esquerda");
}
```

- **Lógica com Métodos Math**

Nessa manhã, após todos estarem descansados e alimentados, vocês iniciarão a plantação de jacarandás. Porém, é necessário plantar a uma certa distância um pé do outro para que nenhuma planta roube o nutriente da outra fazendo com que algumas não se desenvolvam. É necessário que cada pé esteja a exatos 10 metros de distancia um do outro, assim conseguiremos plantar todas as mudas e evitar que algumas não se desenvolvam.

Crie um código que, com as entradas de distancias dos buracos avaliadas pelo drone, verifique se o espaço entre um buraco e outro é igual a 10 metros. Se for, print no console “Plantar!”. Se não for, print no console a distância que o buraco deve retroceder ou avançar para chegar ao número ideal. 

Código:

```jsx
const distanciaPadrao = 10;
let distanciaDrone = parseInt(gets());
let distanciaBuraco = distanciaPadrao - distanciaDrone;

if (distanciaBuraco === 10) {
    print("Plantar!");
    
} else {
    if (Math.sign(distanciaBuraco) === 1) {
        print(`O buraco deve avançar ${distanciaBuraco} metros`)
    } else {
        print(`O buraco deve retroceder ${Math.abs(distanciaBuraco)} metros`)
    }
}
```

### Parte 2 - O Vale e o Rio

- **Array, For, Lógica e if/else**

Chegando no Vale, ao lado do rio Jacará-Mirim, a natureza se mostra exuberante. Porém, é necessário verificar se a qualidade da madeira, e consequentemente a vida das árvores, está em um nível aceitável ou necessitando de cuidados. Antes de chegarmos no vale, foram colhidas amostras de celulose e criada uma lista com os resultados de cada árvore separando o vale por blocos.

Crie um código que, para cada item dessa lista, verifique se a amostra está com um nível: Bom, aceitável ou inaceitável. Para cada uma, print no console se devemos descartar da lista de cuidados, manter sob observação ou isolar e iniciar protocolo de cuidados.

Sendo que:
Bom - Mais de 75% de celulose na amostra
Aceitável - Mais de 50% e menos de 75% de celulose na amostra
Inaceitável - Menos de 50% de celulose na amostra

Em todas as amostras foram coletadas 100g igualmente.

(obs: celulose não indica saúde das árvores, esse conceito foi utilizado meramente para fins de criar o exercício e relacionar algo à árvore)

Código:

```jsx
let amostra = [gets()] //[52, 75, 99, 1, 15, 20, 37]

for (i = 0; i < amostra.length; i++) {
    if (amostra[i] >= 75) {
        print("Descartar da lista.");

    } else if (amostra[i] < 75 && amostra[i] >= 50) {
        print("Manter sob observação.");

    } else {
        print("Isolar e iniciar protocolo de cuidados");

    }
}
```

- **Lógica e While**

Por conta do extrativismo e a presença humana na região, o rio Jacará-Mirim está com níveis altíssimos de plástico em todas as suas formas. Para isso, nossa Líder Camila, que além de ser uma ecologista ainda programa em Java, criou uma Ecobarreira com sua equipe. Essa ecobarreira, como a palavra já diz, barra o plástico e o mantem acumulado em uma porção do rio para que depois ele seja coletado e retirado da água. 

Uma equipe do Japão encontrou uma bactéria conhecida como *Ideonella sakaiensis.* Eles descobriram que essa bactéria possui uma enzima capaz de decompor o plástico: a PETase. Essa enzima é muito eficaz e acaba com o plástico em muito menos tempo em comparação com a natureza que leva séculos. 

O plástico é degradado sempre pela metade por dia. Então se temos 1000kg em um dia, no próximo teremos 500kg, no seguinte 250kg e assim por diante. Crie um código que, dependendo da quantidade de plástico, nos diga em quantos dias teremos 1.0kg ou menos de plástico.

(obs: mais sobre essa bactéria pode ser encontrado nessa matéria da Super Interessante de Dezembro/22: [https://super.abril.com.br/ciencia/o-futuro-do-plastico/](https://super.abril.com.br/ciencia/o-futuro-do-plastico/))

Código:

```jsx
let plastico = gets();
let diasNecessarios = 0;

while (plastico > 1) {
    plastico /= 2;
    diasNecessarios++;
}

print(diasNecessarios);
```

- **Lógica, Arrow Function, Array, For e Objetos**

A equipe jurídica que está acompanhando vocês sugeriu que aplicassem, através da justiça, multas para a Oil Corp caso eles não comecem a tratar todas as formas que estão poluindo a região e também a realizar protocolos de reflorestamento e cuidados com a fauna e a flora da região respeitando a natureza.

As atividades que demandam tratamento e atenção são: Reflorestamento, Esgoto Tratado, Emissão de Carbono e Energia Sustentável. Para cada uma delas existem três critério: Não feito, Em progresso e Feito. O que não foi feito deve receber multa, o que está em progresso avaliação de progresso e o que está feito não multar.

Crie um código que analise cada uma dessas atividades e print no console o que deverá ser feito.

Nosso amigo e companheiro Felipão nos ajudou com um pedaço do código. Ele criou a arrowFunction findItem. O que ela faz é criar um filtro para encontrar as chaves no nosso objeto. Podemos notar que os parâmetros dela não estão exatamente ao lado como uma função normal (function exemplo(parâmetros)) mas funciona exatamente do mesmo jeito.

A utilização dela é feita da mesma forma: findItem(objeto, index). Porém isso irá nos retornar a chave. Para termos o valor da chave precisamos fazer dessa forma: list[findItem(objeto, index)]

Código:

```jsx
let arr = [gets()] //["Reflorestamento", "EsgotoTratado", "EmissaoDeCarbono", "EnergiaSustentavel"];

const list = {
    Reflorestamento: gets(),
    EsgotoTratado: gets(),
    EmissaoDeCarbono: gets(),
    EnergiaSustentavel: gets(),
}

const findItem = (object, index) => Object.keys(object).filter(item => item.toString() == index);

for (i = 0; i < arr.length; i++) {
    if (list[findItem(list, arr[i])] === "Não feito") {
        print("Multa")

    } else if (list[findItem(list, arr[i])] === "Em progresso") {
        print("Avaliação de progresso")

    } else {
        print("Não multar")
    } 
}
```

### Parte 3 - A Oil Corp

- Array

Após vocês promoverem diversas atividades a favor da natureza, a liderança e a diretoria da Oil Corp convidaram vocês para os ajudarem a melhorarem as relações com a natureza e a serem mais ecológicos e sustentáveis. Para isso eles precisam de ajuda para criar o algoritmo que direciona os resíduos da água para a estação de tratamento correta antes de ser descartada no rio Jacará-Mirim.

Via de regra, as moléculas que possuem até, ou igual, a 6 caracteres passam pelo filtro Normal, as que possuem até, ou igual, a 10 caracteres passam pelo filtro Específico e as que possuem mais que 10 caracteres passam pelo filtro Duplo Especifico. Essas moléculas estão misturadas nos resíduos, se houver ao menos uma que tenha o número específico de caracteres esse resíduo já deve passar pelo filtro correto.

Crie um código que verifique 

HCCCCH - 6 caracteres

Código:

```jsx
const arr = gets() //["HCCH", "NOH3", "NOC"]
let qualFiltro = 0;

for (i = 0; i < arr.length; i++) {
    if (arr[i].length <= 6) {
        if (qualFiltro <= 1) {
            qualFiltro = 1;
        }

    } else if (arr[i].length > 6 && arr[i].length <= 10) {
        if (qualFiltro <= 2) {
            qualFiltro = 2;
        }

    } else if (arr[i].length > 10) {
        if (qualFiltro <= 3) {
            qualFiltro = 3;
        }

    }
}

if (qualFiltro === 1) {
    print("O filtro que deve ser usado é o Normal");
} else if (qualFiltro === 2) {
    print("O filtro que deve ser usado é o Específico");
} else {
    print("O filtro que deve ser usado é o Duplo Específico");
}
```

- Array de Arrays

A Oil Corp compilou e entregou para vocês uma lista contendo vários gases que eles liberam durante a extração de óleo. Alguns desses gases são extremamente prejudiciais para a camada de ozônio e para a natureza local como: NO2, SO2, CO e FHO.

Durante a extração os gases saem misturados. Crie um código que, de acordo com a lista, verifique se há pelo menos UM desses gases. Se não houver, print que deverá passar por um filtro simples.  Se houver, print no console que deverá passar por um filtro especial e especifique qual gás.

Código: 

```jsx
const arr = gets(); //[["CO2", "OH"], ["NO2", "CF", "CO2"]]
let qualFiltro = false;
let qualMolecula;

for (i = 0; i < arr.length; i++) {
    for(j = 0; j < arr[i].length; j++) {
        if (arr[i][j] === "NO2" || arr[i][j] === "SO2" || arr[i][j] === "CO" || arr[i][j] === "FHO") {
            qualFiltro = true;
            qualMolecula = arr[i][j];
        }
    }
}

if (qualFiltro === false) {
    print("O gás deve passar por um filtro simples.")

} else {
    print(`O gás deve passar por um filtro especial por conta da molécula: ${qualMolecula}`)

}
```

- Json

Vocês decidem que vão enviar projetos e ideias para a Oil Corp seguir sendo mais sustentável. Uma pessoa do seu grupo diz que tem vocês receberam um JSON com diversos funcionários da Oil Corp, e seus emails, e que vocês deveriam tentar enviar as ideias para esses endereços. Porém, vocês devem poupar esforços e enviar esses emails somente para cargos de liderança e diretoria. 

Crie um código que, faça a analise do JSON procurando por cargos e emails válidos, e print no console o nome, o cargo e seu email válido.

OBS: Emails válidos são aqueles que possuem @oilcorp.com.br

Código:

```jsx
let offset = gets();
let limit = gets();

const info = 
[
{
    nome: "Caique Andrade", 
    idade: 23, 
    cargo: "Trainee", 
    email: "caiqueandrade@hotmail.com", 
    tempoDeEmpresa: "3 meses"
},
{
    nome: "Júlio Cesar", 
    idade: 65, 
    cargo: "Diretoria", 
    email: "julio.cesar@oilcorp.com.br", 
    tempoDeEmpresa: "44 anos"
},
{
    nome: "Enzo Gaben", 
    idade: 25, 
    cargo: "Auxiliar Administrativo", 
    email: "enzogaben@oilcorp.com", 
    tempoDeEmpresa: "1 ano"
},
{
    nome: "Lenite Longo", 
    idade: 70, 
    cargo: "Diretoria", 
    email: "lenite@oilcorp.com.br", 
    tempoDeEmpresa: "50 anos"
},
{
    nome: "Renan Oliveira", 
    idade: 35, 
    cargo: "Liderança", 
    email: "renan@oilcorp.com", 
    tempoDeEmpresa: "10 anos"
},
{
    nome: "Renato Linhares", 
    idade: 32, 
    cargo: "Liderança", 
    email: "renatolinhares@oilcorp.com.br", 
    tempoDeEmpresa: "5 anos"
},
{
    nome: "Emerson Junior", 
    idade: 22, 
    cargo: "Tech lead", 
    email: "emersonjunior@oilcorp.com.br", 
    tempoDeEmpresa: "5 anos"
},
{
    nome: "Igor Alves", 
    idade: 26, 
    cargo: "DBA", 
    email: "igor.alves@hotmail.com", 
    tempoDeEmpresa: "Terceirizado"
},
{
    nome: "Marcela Kawakame", 
    idade: 28, 
    cargo: "Liderança", 
    email: "marcela@oilcorp.com.br", 
    tempoDeEmpresa: "6 anos"
},
{
    nome: "Eric Velloso", 
    idade: 29, 
    cargo: "Diretoria", 
    email: "e.velloso@oilcorp.com.br", 
    tempoDeEmpresa: "11 anos"
},
]

for (i = offset; i < limit; i++) {
    if ((info[i].cargo === "Liderança" || info[i].cargo === "Diretoria") && ((info[i].email).includes("@oilcorp.com.br"))) {
        print(`Nome: ${info[i].nome}, Cargo: ${info[i].cargo}, Email: ${info[i].email}`)
    }
}
```
