# Fundamentos do JavaScript

## 1. Introdução ao JavaScript

- **O que é JavaScript?**

- `JavaScript` é uma linguagem de programação de alto nível, amplamente usada para tornar páginas web interativas. Enquanto `HTML` estrutura a página e o `CSS` define o estilo, o `JavaScript` lida com a lógica, permitindo criar funcionalidades dinâmicas, como animações, validação de formulários, e muito mais.
  
- **Inserindo JavaScript em uma página HTML**

- Podemos inserir `JavaScript` diretamente em um documento `HTML` usando a tag `<script>`. Isso pode ser feito dentro do corpo (`<body>`) ou no cabeçalho (`<head>`), mas geralmente é melhor colocá-lo no final do corpo para garantir que o `HTML` seja carregado antes de executar o `JavaScript`.

```html
<!DOCTYPE html>
<html lang="pt-BR">
    <head>
        <meta charset="UTF-8">
        <title>Introdução ao JavaScript</title>
    </head>
    <body>
        <h1>Minha primeira página com JavaScript</h1>
        <script>
            alert('Hello, World!');
        </script>
    </body>
</html>
```

## 2. Variáveis e Tipos de Dados

- **Declaração de Variáveis**

    - `var`, `let`, e `const` são usados para declarar variáveis:

        - `var`: Funciona em um escopo global ou de função. Seu uso diminuiu após o surgimento do `let` e `const` devido a problemas com escopo.

        - `let`: Tem escopo de bloco, o que significa que só é acessível dentro das chaves `{}` em que foi declarada.

        - `const`: Também tem escopo de bloco, mas uma vez atribuído um valor, ele não pode ser reatribuído.

```javascript
var nome = "Daniel";
let idade = 28;
const cidade = "São Leopoldo";
```

- **Tipos de Dados**

    - O JavaScript suporta vários tipos de dados:

        - **String**: Texto (ex.: `"Olá, Mundo!"`).

        - **Number**: Números (ex.: `42`, `3.14`).

        - **Boolean**: Verdadeiro ou falso (`true`, `false`).

        - **Array**: Lista de elementos (ex.: `[1, 2, 3]`).

        - **Object**: Estrutura para armazenar coleções de dados (ex.: `{nome: "Daniel", idade: 28}`).

        - **undefined**: Quando uma variável é declarada, mas não inicializada.

        - **null**: Intencionalmente define uma variável como "vazia".

```javascript
let texto = "Olá, Mundo!";
let numero = 42;
let verdadeiro = true;
let lista = [1, 2, 3, 4];
let objeto = {nome: "Daniel", idade: 28};
```

## 3. Operadores

- **Operadores Aritméticos**

    - Realizam cálculos matemáticos básicos.

```javascript
let soma = 5 + 3;  // retornará 8
let subtracao = 5 - 3;  // retornará  2
let multiplicacao = 5 * 3;  // retornará  15
let divisao = 5 / 3;  // retornará  1.666...
let resto = 5 % 3;  // retornará  2
```

- **Operadores de Comparação**

  - Comparam dois valores e retornam `true` ou `false`.

```javascript
console.log(5 == "5");  // retornará  true (compara valor)
console.log(5 === "5");  // retornará  false (compara valor e tipo)
console.log(5 != 3);  // retornará  true
console.log(5 !== "5");  // retornará  true
```

- **Operadores Lógicos**

    - Combinam expressões booleanas.

```javascript
console.log(true && false);  // retornará  false
console.log(true || false);  // retornará  true
console.log(!true);  // retornará  false
```

## Exercícios

### **1. Introdução ao JavaScript**

**Exercício 1.1:**

- Crie uma página `HTML` simples e insira um script `JavaScript` que exiba uma mensagem "Bem-vindo ao JavaScript!" quando a página for carregada.

### **2. Variáveis e Tipos de Dados**

**Exercício 2.1:**

- Crie variáveis usando `var`, `let`, e `const` para armazenar as seguintes informações: seu nome, sua idade, e a cidade onde você mora. Exiba essas informações no console.

**Exercício 2.2:**

- Crie um objeto chamado `aluno` que contenha as seguintes propriedades: `nome`, `idade`, e `curso`. Em seguida, crie um array chamado `alunos` e adicione o objeto `aluno` a esse array. Exiba o array no console.

**Exercício 2.3:**

- Declare uma variável sem atribuir nenhum valor a ela e, em seguida, exiba seu valor no console. Agora, atribua o valor `null` a essa variável e exiba novamente o valor.

### **3. Operadores**

**Exercício 3.1:**

- Crie uma função que receba dois números como parâmetros e retorne a soma deles. Teste a função no console com diferentes valores.

**Exercício 3.2:**

- Crie uma função que receba dois números e retorne `true` se o primeiro número for maior que o segundo, e `false` caso contrário. Teste a função no console.

**Exercício 3.3:**

- Usando operadores lógicos, crie uma expressão que verifique se um número está entre 10 e 20. A expressão deve retornar `true` se o número estiver nesse intervalo, e `false` caso contrário. Teste a expressão no console.