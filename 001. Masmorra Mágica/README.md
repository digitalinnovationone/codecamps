# A Masmorra Mágica

Você é um(a) jovem que, inspirada(o) pelo espírito aventureiro e pelas histórias de sua mãe, decide que está na hora de partir para uma aventura. Entre sua casa e o vilarejo existe uma Masmorra Mágica que todos os moradores da região evitam ir e onde dizem existir criaturas, magia e tesouros.

## Parte 1 - A Casa

- String
    
    Você decide partir antes do amanhecer e vai até os fundos da sua casa para coletar suprimentos. Chegando lá você encontra diversos equipamentos que podem ser uteis ou apenas serem mais um peso na sua mochila.
    
    Crie um código que print no console os equipamentos necessários para você iniciar sua viagem.
    
    Código: 
    
    ```jsx
    let equipment = gets()
    
    print(equipment);
    ```
    

- Concatenação de Strings
    
    Enquanto você estava procurando o que levar, decidiu contabilizar cada um dos suprimentos para não levar tudo e deixar sua família sem. 
    
    Crie um código que print no console o nome do suprimento e sua quantidade.
    
    Código:
    
    ```jsx
    let suply = gets()
    let suplyQuantity = gets();
    
    print(`${suply} possui ${suplyQuantity} unidades`)
    ```
    

- If simples
    
    Ao sair da sua casa, sua irmã mais nova aparece correndo e te acompanha até o portão. Lá ela te mostra várias poções e porções mágicas (mais conhecidas como almoço) para você levar e não passar fome no caminho. Porém, sua mochila está lotada e possuí pequenos espaços disponíveis.
    
    *Espaços maiores que 5 unidades não cabem na mochila.
    
    Crie um código que verifique se o tamanho não é maior que o que cabe na sua mochila para que você leve aquela refeição feita com tanto carinho pela sua irmãzinha e print no console se é possível ou não levar aquele determinado item.
    
    Código:
    
    ```jsx
    let meal = gets();
    const spaceFree = 5;
    
    if (meal <= spaceFree) {
        print(`É possível levar ${meal}`)
    } else {
        print(`não é possível levar ${meal}`)
    }
    ```
    
- BOSS

## Parte 2 - O Bosque e o Caminho

- If duplo com concatenação de Strings
    
    Após alguns minutos de caminhada você já encontra o seu primeiro desafio. Desembainhando sua grandiosa espada você se prepara para a batalha e desfere o primeiro golpe.
    
    Crie um código que verifique se seu ataque foi o suficiente para acabar com o inimigo, print no console que tipo de criatura era e se ela se manteve em pé ou não.
    
    Código:
    
    ```jsx
    let creature = gets();
    let creatureHp = gets();
    let selfAtack = gets();
    
    if (creatureHp - selfAtack <= 0) {
        print(`${creature} caiu!`);
    } else {
        print(`${creature} se manteve em pé!`);
    }
    ```
    

- If/Else if/Else
    
    Continuando sua viagem por aquele bosque fresco você sente o doce cheiro de maçãs. Seguindo o cheiro você encontra uma jovem camponesa tentando pega-las. Ela te diz que aquelas maçãs não são meras frutas, elas são mágicas e tem a capacidade de curar qualquer ferimento. Tentado(a) pela ideia de levar algumas, você saca seu arco para acertar e derrubar algumas do pé.
    
    Com uma única flechada excelente é possível derrubar até três maçãs de uma vez, com uma boa flechada uma e errando nenhuma.
    
    0 - 3 = Erro
    4 - 7 = Boa flechada
    8 - 10 = Flechada excelente
    
    Crie um código que verifique se seu acerto foi crítico, normal ou se errou e quantas maçãs foram derrubadas nesse processo.
    
    Código:
    
    ```jsx
    let arrowChance = gets()
    
    if (arrowChance <= 3) {
        print(`Foram derrubadas 0 maçãs`)
    
    } else if (arrowChance > 3 && arrowChance <= 7) {
        print(`Foram derrubadas 1 maçãs`)
    
    } else if (arrowChance > 7 && arrowChance <= 10) {
        print(`Foram derrubadas 3 maçãs`)
    
    }
    ```
    

- Função
    
    Caminhando mais alguns minutos você se depara com um senhor bigodudo. Ele te diz que quer construir placas para informar viajantes dos diversos perigos daquela estrada: bandidos, buracos e armadilhas deixadas por caçadores. Mas ele não sabe como se faz isso e você decide ajuda-lo. Porém, as madeiras que esse senhor possui limitam as frases cabendo frases com até 24 caracteres (contando espaços e pontuações).
    
    Crie um código, utilizando uma função, que verifique o tamanho da frase e, se couber na placa, print as instruções para os viajantes. Se não couber, print uma frase dizendo que não cabe.
    
    Código:
    
    ```jsx
    let textIn = gets();
    
    function signText(text) {
        if (text.length <= 24) {
            print(`${text}`);
        } else {
            print(`A frase não cabe na placa`);
        }
    }
    
    print(signText(textIn));
    ```
    
- BOSS

## Parte 3 - A Masmorra

- Array
    
    Chegando na Masmorra, você encontra uma porta selada. Em um primeiro momento parece ser impossível atravessa-la para explora-la. Ao longe uma risada pode ser ouvida e uma bruxa aparece caminhando. Ela para ao seu lado e te entrega um pergaminho com palavras sem sentido. Ela diz que há uma charada para poder desfazer o selo.
    
    ”Maiores do que quatro não podemos ser, diga as palavras certas e dentro você poderá ver”
    
    Crie um código que, de acordo com a lista que representa cada linha do pergaminho, print as palavras corretas para desfazer o selo.
    
    Código:
    
    ```jsx
    let paper = [];
    
    for (i = 0; i < paper.length; i++){
        let magicWord = paper[i];
        if (magicWord.length <= 4) {
            print(magicWord);
        }
    }
    ```
    
- While
    
    Uma vez dentro da Masmorra você percorre um caminho mal iluminado e com um cheiro podre. Uma forte luz é vista e quando você chega lá, várias tochas estão iluminando um grande espaço. Uma criatura gosmenta cai do teto e vai em sua direção, você sabe que ela quer te engolir. A grandiosa SLIME sempre se divide em duas partes iguais após sofrer um ferimento e deve ser reduzida a nada para morrer.
    
    Crie um código que verifique quantos ataques serão necessários para derrotar a Slime de acordo com seu tamanho x.
    
    Código:
    
    ```jsx
    let slime = 50;
    let golpes = 0;
    
    while (slime > 1) {
        slime /= 2;
        golpes++;
    }
    
    print(`Serão necessários ${golpes} para derrotar a Slime`);
    ```
    
- Objetos
    
    A sala do tesouro é magnífica e seus olhos ficam marejados com a sensação de exploração completa. Você escolhe um tesouro para levar para casa como forma de recompensa até que ouve a porta se abrindo. Um outro aventureiro entra atrás de você, com sua armadura reluzente, e te saca sua espada e escudo. Ele quer uma batalha.
    
    Você não sabe quão forte ele é, mas para conseguir escapar com vida, terá que derrota-lo.
    
    Crie um código que, dados os atributos de cada um, faça um calculo para verificar quem venceria. O calculo deve ser feito da seguinte maneira: Vida do inimigo - (Seu ataque - defesa do inimigo) e Sua vida - (Ataque inimigo - sua defesa). Esses dois calculos irão render dois valores, o valor que for maior é o vencedor.
    
    Código:
    
    ```jsx
    let inimigo = {
        vida: 15,
        ataque: 10,
        defesa: 5
    }
    
    let voce = {
        vida: 2,
        ataque: 15,
        defesa: 10
    }
    
    if (voce.vida - (inimigo.ataque - voce.defesa) > inimigo.vida - (voce.ataque - inimigo.defesa)) {
        print("você venceu")
    } else {
        print("inimigo venceu")
    }
    ```
    
- BOSS
