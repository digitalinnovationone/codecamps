# O Vale do Jacarandá Dourado

Imagine um mundo onde a grande empresa *Oil Corp* está causando problemas no **Vale do Jacarandá Dourado**, um lugar mágico com fauna e flora excepcionais, que vêm sendo exploradas por essa corporação.

Nesse contexto, você é um(a) entusiasta de tecnologia e meio ambiente que acredita em soluções disruptivas, desde que sejam sustentáveis. Essa paixão te levou a um papel de liderança em um grupo de pessoas e *CleanTechs* na região do **Vale do Jacarandá Dourado**, engajadas na luta contra a *Oil Corp*. Cada membro desse grupo é chamado de *CleanCoder* (em homenagem à *Uncle Bob*, autor de livros aclamados pela comunidade de desenvolvimento de software).

Bora superar os desafios impostos nesta jornada e codar um final feliz 😎

## Módulo 0 - Prepare-se Para a Jornada

Nesse módulo inicial teremos:

- Curso padrão - Conheça as Oportunidades da DIO
- Curso padrão (novo) - Por Dentro dos Code Camps que vai possuir:
    1. Vídeo do Caio
    2. Vídeo do Venilton explicando o que é um desafio de código
    3. Aula textual com sugestões de conteúdos (para pessoas que estão começando do zero)
- Curso padrão - "Bem-vindo ao Vale do Jacarandá Dourado":
    1. Vídeo genérico de boas vindas e falando para a galera ler e prestar bastante atenção na história base e nas dicas de estudo
    2. Aula textual - Conhecendo a História (Aqui vem a explicação da situação problema central e de cada módulo)
    3. Aula textual - Dicas de Estudo (Aqui vem pautado o que o dev precisa saber para conseguir realizar os desafios e um conjunto de cursos da plataforma + documentação oficial para que ele possa ter como base se sentir dificuldades)
- Aula Inaugural

## Módulo 1 - Chegando no Acampamento

- Soft Skill: **`Comunicação`**

### Desafio "Conhecendo os *CleanCoders*"

- Hard Skill: **`Strings`**

Buscando planejar as ações para conter a *Oil Corp*, um acampamento foi criado e muitos *CleanCoders* (inclusive novos adeptos da causa) estão chegando. Com isso, para faciliar a comunicação e interação, precisamos imprimir cartões de identificação para todas as pessoas.

Crie um código que com três entradas (NOME, SOBRENOME e ID) que imprima essas informações no seguinte padrão: "Nome: `NOME` `SOBRENOME` ID: `ID`"

Venilton, um *CleanCoder* experiente, compartilhou uma dica bem útil. Ele disse que é possível utilizar o conceito de **interpolação de strings** para facilitar a impressão de textos concatenados à variáveis. Para utilizar basta fazer assim:

```jsx
print(`Coloque sua string normalmente e quando quiser usar uma variável, use ${variavel}`);
```

Código:

```jsx
let nome = gets();
let sobrenome = gets();
let id = parseInt(gets());

print(`Nome: ${nome} ${sobrenome} ID: ${id}`);
```

### Desafio "Dividindo Para Preservar"

- Hard Skills: **`Estruturas de Decisão`** **`Strings`**

Agora precisamos separar os *CleanCoders* em dois grupos, isso vai facilitar a execução de ações estratégicas. Para isso, foi definido que os IDs pares devem ir para as barracas à direita da estrada que corta o acampamento e os ímpares para a esquerda. Aproveite essa oportunidade para criar um código que verifique o ID do *CleanCoder* e indique para onde ele deve ir: Direita ou Esquerda.

Código:

```jsx
let id = gets();

if (id % 2 === 0) {
    print"Direita");
} else {
    print("Esquerda");
}
```

### Desafio "Plantando o Futuro"

- Hard Skills: **`Objetos e Métodos`** **`Estruturas de Decisão`** **`Strings`**

Pela manhã, com todos descansados, sua primeira missão será aumentar a plantação de jacarandás, árvore fundamental para a magia do vale. Para isso, é necessário plantá-los a uma certa distância um pé do outro para que nenhuma muda roube o nutriente da outra, fazendo com que algumas não se desenvolvam. Nesse sentido, é necessário que cada pé esteja a exatos 10 metros de distancia um do outro, assim conseguiremos plantar todas as mudas e evitar que algumas não se desenvolvam.

Crie um código que, com as entradas de distancias dos buracos avaliadas pelo drone, verifique se o espaço entre um buraco e outro é igual a 10 metros. Se for, imprima no console "Plantar!". Se não for, imprima no console a distância que o buraco deve retroceder ou avançar para chegar ao número ideal. 

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

## Módulo 2 - O Vale e o Rio

- Soft Skill: **`Engajamento`**

### Desafio "Examinando Árvores"

- Hard Skills: **`Arrays`** **`Estruturas de Repetição`** **`Estruturas de Decisão`** **`Strings`**

Chegando no Vale, ao lado do rio Jacará-Mirim, a natureza se mostra exuberante. Porém, é necessário verificar as árvores da região estão saudáveis ou necessitando de cuidados. Para isso, durante nossa jornada até o vale, utilizamos um dispositivo de ultrassom desenvolvido por uma das *CleanTechs* parceiras, a *Cleanduino* (especializada em projetos com Arduino e JavaScript, usando o Framework [Johnny-Five](https://github.com/rwaldron/johnny-five)). Através desse dispositivo coletamos uma lista de amostras, onde cada registro tem o percentual de saúde da árvore avaliada.

Crie um código que, para cada item dessa lista, verifique se a amostra está com um nível: Bom, Aceitável ou Inaceitável. Para cada nível, imprima a ação que deve ser realizada considerando as seguintes regras:

- Bom (mais de 75% de saúde na amostra)
  - Imprima `"Descartar da lista."`
- Aceitável (mais de 50% e menos de 75%)
  - Imprima `"Manter sob observação."`
- Inaceitável (menos de 50%)
  - Imprima `"Isolar e iniciar protocolo de cuidados."`

Código:

```jsx
let amostra = [gets()] //[52, 75, 99, 1, 15, 20, 37]

for (i = 0; i < amostra.length; i++) {
    if (amostra[i] >= 75) {
        print("Descartar da lista.");

    } else if (amostra[i] < 75 && amostra[i] >= 50) {
        print("Manter sob observação.");

    } else {
        print("Isolar e iniciar protocolo de cuidados.");

    }
}
```

### Desafio "Bactériaaaaaaaaa!"

- Hard Skills: **`Estruturas de Repetição`** **`Estruturas de Decisão`** **`Strings`**

Por conta do extrativismo e a presença humana na região, o rio Jacará-Mirim está com níveis altíssimos de plástico em todas as suas formas, em sua maioria originados de descartes irregulares da *Oil Corp*. Para isso, a coordenadora da expedição Camila (uma ecologista engajada e expert em Java), criou uma ecobarreira com sua equipe. Essa ecobarreira, como a palavra já diz, barra o plástico e o mantém acumulado em uma porção do rio para que depois ele seja coletado e retirado da água. 

Felizmente, *CleanCoders* do Japão descobriram uma bactéria conhecida como *Ideonella sakaiensis.* Eles confirmaram que essa bactéria possui uma enzima capaz de decompor o plástico: a *PETase*. Essa enzima é muito eficaz e acaba com o plástico em muito menos tempo em comparação com a decomposição na natureza, que pode levar séculos. 

Nesse contexto, o plástico é degradado sempre pela metade a cada dia. Então se temos 1000kg em um dia, no próximo teremos 500kg, no seguinte 250kg e assim por diante. Crie um código que, dependendo da quantidade de plástico, nos diga em quantos dias teremos 1kg ou menos de plástico (viabilizando a coleta manual).

*Nota: mais sobre essa bactéria pode ser encontrado nessa matéria da Super Interessante de Dezembro/2022: [https://super.abril.com.br/ciencia/o-futuro-do-plastico/](https://super.abril.com.br/ciencia/o-futuro-do-plastico/)*

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

### Desafio "Aplicando o Peso da Lei!"

- Hard Skills: **`Funções`** **`Arrays`** **`Estruturas de Repetição`** **`Estruturas de Decisão`** **`Strings`**

A equipe jurídica que está acompanhando vocês sugeriu que aplicassem, através da justiça, multas para a *Oil Corp* caso eles não comecem a tratar todas as formas que estão poluindo a região. Além de realizar protocolos de reflorestamento e cuidados com a fauna e a flora do vale, respeitando a natureza.

As atividades que demandam tratamento e atenção são: Reflorestamento, Esgoto Tratado, Emissão de Carbono e Energia Sustentável. Para cada uma delas existem três critério: Não feito, Em progresso e Feito. O que não foi feito deve receber multa, o que está em progresso avaliação de progresso e o que está feito não multar.

Crie um código que analise cada uma dessas atividades e print no console o que deverá ser feito.

Nosso amigo e *CleanCoder* Felipão nos ajudou com um pedaço do código. Ele criou a [*Arrow Function*](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Functions/Arrow_functions) `findItem`. O que ela faz é criar um filtro para encontrar as chaves no nosso objeto. Podemos notar que os parâmetros dela não estão exatamente ao lado como uma função normal: `function exemplo(parametros)`, mas funciona exatamente do mesmo jeito.

A utilização dela é feita da mesma forma: `findItem(objeto, index)`. Porém isso irá nos retornar a chave. Para termos o valor da chave precisamos fazer dessa forma: `list[findItem(objeto, index)]`.

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

## Módulo 3 - Reciclando a *Oil Corp*

- Soft Skill: **`Resiliência`**

### Desafio "Parceria de Milhões, Para a Natureza ;)"

- Hard Skills: **`Arrays`** **`Estruturas de Repetição`** **`Estruturas de Decisão`** **`Strings`**

Após vocês promoverem diversas atividades a favor da natureza, a liderança e a diretoria da *Oil Corp* convidaram vocês para os ajudarem a preservar a natureza e a serem una empresa sustentável. Para isso, eles precisam de ajuda para criar o algoritmo que direciona os resíduos da água para a estação de tratamento correta antes de ser descartada no rio Jacará-Mirim.

Via de regra, as moléculas que possuem até 6 caracteres passam pelo filtro Normal, as que possuem até 10 caracteres passam pelo filtro Específico e as que possuem mais que 10 caracteres passam pelo filtro Duplo Especifico. Essas moléculas estão misturadas nos resíduos, se houver ao menos uma que tenha o número específico de caracteres esse resíduo já deve passar pelo filtro correto.

Crie um código que implemente essas regras e imprima o filtro adequado para cada molécula:
- `<= 6` -  Imprimir "Filtro Normal";
- `<= 10` -  Imprimir "Filtro Específico";
- `> 10` -  Imprimir "Filtro DuploEspecífico".

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
    print("Filtro Normal");
} else if (qualFiltro === 2) {
    print("Filtro Específico");
} else {
    print("Filtro Duplo Específico");
}
```

### Desafio "Isso Não Está Cheirando Bem... Bora Filtrar!"

- Hard Skills: **`Arrays`** **`Estruturas de Repetição`** **`Estruturas de Decisão`** **`Strings`**

A *Oil Corp* abriu o jogo e entregou para vocês uma lista contendo vários gases que eles liberam durante a extração de óleo. Alguns desses gases são extremamente prejudiciais para a camada de ozônio e para a natureza local como: NO2, SO2, CO e FHO.

Durante a extração os gases saem misturados. Crie um código que, de acordo com a lista, verifique se há pelo menos UM desses gases. Se não houver, imprima que deverá passar por um filtro simples.  Se houver, imprima no console que deverá passar por um filtro especial e especifique qual gás.

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
    print("Filtro Simples.")

} else {
    print(`Filtro Especial Para Molécula ${qualMolecula}`)

}
```

### Desafio "Network É Tudo!"

- Hard Skills: **`JSON`** **`Estruturas de Repetição`** **`Estruturas de Decisão`** **`Strings`**

Vocês decidem que vão enviar projetos e ideias para a *Oil Corp* seguir sendo mais sustentável. Uma pessoa do seu grupo diz que vocês receberam um JSON com diversos funcionários da *Oil Corp*, e seus emails, e que vocês deveriam tentar enviar as ideias para esses endereços. Porém, vocês devem poupar esforços e enviar esses emails somente para cargos de liderança e diretoria. 

Crie um código que, faça a analise do JSON procurando por cargos e emails válidos, e print no console o nome, o cargo e seu email válido.

OBS: Emails válidos são aqueles que possuem @oilcorp.com.br

Código:

```jsx
let offset = gets();
let limit = gets();

const info = [
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
    }
];

for (i = offset; i < limit; i++) {
    if ((info[i].cargo === "Liderança" || info[i].cargo === "Diretoria") 
        && ((info[i].email).includes("@oilcorp.com.br"))) {
        print(`Nome: ${info[i].nome}, Cargo: ${info[i].cargo}, Email: ${info[i].email}`);
    }
}
```
### Curso de finalização

- Vídeo final do Caio

### Feedback

- Onde as pessoas poderão acessar o forms para avaliação
