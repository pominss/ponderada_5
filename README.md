# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 


b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Correta: letra "a"
Justificativa: o código não le o let y = 10 e nem o var = 5 pois eles foram declarados após o console.log. a jeito correto seria pondo o console log depois de declarar cada variavel, para o código ser lido da forma correta.


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Correta: letra "b"
Justificativa: A verificação a || b === 0 indica o numero como invalido pois na soma o valor de b está atribuido como 0, desta forma, a OU b sendo 0 o numero sera invalido. Ao fazer uma verificação separada, analisando "a" de forma isolada e depois determinando que "b" també deve ser zero, acaba com o erro de apenas um numero ser 0 e invalidar o outro.

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

correta: "b"
Justificativa: o código imprime 200 pois não possui um "break" após o case "eletrônico desta forma o código continua rodando e só para no case "vestuário"
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24

Correta: "d"   
Justificativa: o Let numeros cria a lista, definindo a sequência de números. o numeros.map cria uma nova lista, multiplicando todos os numeros da "let numeros" por 2. o .filter filtra todos os numeros da lista criada, e mostra somente os números maiores que 5, trazendo o resultado 6, 8, 10. o .reduce soma todos os valores da lista criado pelo .filter, iniciando por 0 sendo assim: 0 + 6; 0 + 8; 14 + 10; o que gera 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

Correta: "c"
Justificativa: O .splice remove e substitui os elementos dentro de uma lista, no exemplo mostrado, a lista inicial é definida, após isso o lista.splice o remove o elemento 1 e 2, respectivamente "maça" e "uva", pois o elemento 0 seria "banana". e substitui os dois elementos retirados por "abacaxi" e "manga". Por fim, o console.log mostra a nova lista com os elementos substituidos.

______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Correta: "b"
Justifica: A primeira e a segunda afirmação afirmação estão corretas, porém a primeira fala sobre o conceito de herança e sua função, e a segunda afirmação, não justifica o funcionamento de herança, mas sim mostra como usa-la.

______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

Correta: "a"
Justificativa: Alternativa I: A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente. Alternativa II: O método apresentar() da classe Funcionario sobrepõe o método da classe Pessoa, mas chama o método da classe pai usando super, está correta. alternativa III está errada porque o javascript suporta herança de classes.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Correta: "b"
Justificativa: A asserção está correta, pois o polimorfismo permite que diferentes classes respondam ao mesmo método de formas diferentes. A razão é falsa porque JavaScript não suporta a multi nomeação de métodos. Porém, o polimorfismo é implementado através de herança e sobrescrita de métodos.


______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

A variável soma deve ser inicializada com 0 para evitar erros de referência. O método correto para obter o tamanho de uma lista é .length, não .size. O operador += acumula a soma do dobro dos números.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

```javascript
function somaArray(numeros) {
    let soma = 0; // Inicializa a soma
    for (let i = 0; i < numeros.length; i++) { // Usa length no lugar de size que está incorreto
        soma += 2 * numeros[i]; // Soma corretamente
    }
    return soma;
}

console.log(somaArray([1, 2, 3, 4])); // Saída esperada: 20


console.log(somaArray(numeros)); // referenciando diretamente a var numeros ao inves de colocar os numeros
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript
// Classe Produto
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    // Método para aplicar desconto de 10%
    calcularDesconto() {
        return this.preco * 0.9; // Aplica 10% de desconto
    }
}

// Classe Livro que herda de Produto
class Livro extends Produto {
    constructor(nome, preco, autor) {
        super(nome, preco); // Chama o construtor da classe Produto
        this.autor = autor;
    }

    // Sobrescrevendo o método calcularDesconto() para aplicar 20%
    calcularDesconto() {
        return this.preco * 0.8; // Aplica 20% de desconto
    }
}

// Exemplo de uso
const produtoGenerico = new Produto("Mouse", 100);
console.log(`Preço com desconto do produto: R$${produtoGenerico.calcularDesconto().toFixed(2)}`);

const livro = new Livro("JavaScript Avançado", 150, "John Doe");
console.log(`Preço com desconto do livro: R$${livro.calcularDesconto().toFixed(2)}`);
```
Explicação: A classe "Livro" herda da classe "Produto" usando extends. Isso significa que "Livro" possui os mesmos atributos (nome, preco) e métodos "calcular desconto" de "Produto".
Uso do super(): no construtor de "Livro", usamos super(nome, preco); para chamar o construtor da classe pai (Produto) e inicializar nome e preco.
Sobrescrita de Método (calcularDesconto()): "Produto" possui um método "calcular esconto" que aplica 10% de desconto.
"Livro" modifica (sobrescreve) esse método para aplicar um desconto de 20%.
