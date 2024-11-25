# Eventos Interativos e Manipulação de DOM com JavaScript

## Objetivo:

Esta aula tem como objetivo ensinar os conceitos de eventos interativos e manipulação de DOM *`(Document Object Model)`* utilizando JavaScript. Ao final, você será capaz de responder a interações do usuário e modificar elementos da página em tempo real.

### 1. **O que é o DOM?**

O **DOM** *`(Document Object Model)`* é a estrutura que o navegador cria para representar a página web. Ele é uma árvore de objetos que corresponde a todos os elementos `HTML` da página. A partir do `DOM`, podemos acessar, modificar e manipular esses elementos com JavaScript.

Imagine o `DOM` como um mapa da sua página web, onde cada tag (como `<div>`, `<p>`, `<h1>`, etc.) é um nó dessa árvore. Você pode usar JavaScript para acessar e modificar esses nós dinamicamente, criando uma experiência interativa para o usuário.

### 2. **Manipulação de DOM**

A manipulação de DOM é o processo de acessar, modificar ou excluir elementos HTML da página com JavaScript. Vamos ver como fazer isso com alguns exemplos práticos:

#### 2.1 **Acessando Elementos no DOM**

Existem várias formas de acessar um elemento no DOM. As mais comuns são:

- `document.getElementById(id)`: Retorna o elemento com o ID especificado.
- `document.querySelector(selector)`: Retorna o primeiro elemento que corresponde ao seletor CSS fornecido.
- `document.querySelectorAll(selector)`: Retorna todos os elementos que correspondem ao seletor CSS.

**Exemplo:**

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Manipulação de DOM</title>
</head>
<body>
    <h1 id="titulo">Olá, Mundo!</h1>
    <p class="paragrafo">Este é um exemplo de manipulação de DOM.</p>

    <script>
        // Acessando elementos
        let titulo = document.getElementById('titulo');
        let paragrafo = document.querySelector('.paragrafo');

        // Modificando conteúdo
        titulo.innerHTML = 'Novo Título';
        paragrafo.style.color = 'blue'; // Alterando a cor do texto
    </script>
</body>
</html>
```

#### 2.2 **Criando e Removendo Elementos**

Podemos criar novos elementos e adicionar à página, ou remover elementos existentes.

**Exemplo:**

```javascript
let novoParagrafo = document.createElement('p'); // Cria um novo <p>
novoParagrafo.innerHTML = 'Este é um novo parágrafo!';
document.body.appendChild(novoParagrafo); // Adiciona ao corpo da página

// Remover um elemento
document.body.removeChild(novoParagrafo); // Remove o parágrafo criado
```

### 3. **Eventos Interativos**

Eventos são ações que acontecem em uma página web, como um clique de mouse, pressionamento de tecla ou o envio de um formulário. O JavaScript permite capturar esses eventos e executar ações em resposta a eles.

#### 3.1 **Tipos de Eventos**

Os eventos mais comuns são:

- **click**: Ocorre quando o usuário clica em um elemento.
- **mouseover**: Ocorre quando o usuário passa o mouse sobre um elemento.
- **keydown**: Ocorre quando o usuário pressiona uma tecla.
- **submit**: Ocorre quando um formulário é enviado.

#### 3.2 **Exemplo de Manipulação de Eventos**

Para manipular um evento, usamos o método `addEventListener()`. Esse método permite que associemos uma função *(callback)* a um evento específico de um elemento.

**Exemplo:**

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eventos Interativos</title>
</head>
<body>
    <button id="botao">Clique em mim!</button>
    <p id="mensagem"></p>

    <script>
        let botao = document.getElementById('botao');
        let mensagem = document.getElementById('mensagem');

        // Adicionando um evento de clique
        botao.addEventListener('click', function() {
            mensagem.innerHTML = 'Você clicou no botão!';
            mensagem.style.color = 'green';
        });
    </script>
</body>
</html>
```

#### 3.3 **Exemplo de Evento de Teclado**

É possível também, capturar eventos de teclado, como quando o usuário pressiona uma tecla.

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Evento de Teclado</title>
</head>
<body>
    <h1>Pressione qualquer tecla</h1>
    <p id="tecla"></p>

    <script>
        let tecla = document.getElementById('tecla');

        // Capturando o evento de tecla pressionada
        document.addEventListener('keydown', function(event) {
            tecla.innerHTML = 'Você pressionou a tecla: ' + event.key;
        });
    </script>
</body>
</html>
```

### 4. **Eventos de Formulário**

Eventos de formulário são essenciais para interações em páginas de login, cadastro, pesquisa e outros formulários.

#### Exemplo de Envio de Formulário

Aqui, vamos capturar o envio de um formulário e prevenir o comportamento padrão (o envio para um servidor).

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Evento de Formulário</title>
</head>
<body>
    <form id="meuFormulario">
        <label for="nome">Nome:</label>
        <input type="text" id="nome" required>
        <button type="submit">Enviar</button>
    </form>

    <script>
        let formulario = document.getElementById('meuFormulario');
        
        // Prevenindo o envio padrão
        formulario.addEventListener('submit', function(event) {
            event.preventDefault(); // Impede o envio real do formulário
            alert('Formulário enviado com sucesso!');
        });
    </script>
</body>
</html>
```

### 5. **Desafio Prático**

Agora que já vimos alguns conceitos importantes, que tal colocar em prática o que aprendemos? Abaixo estão alguns desafios.

#### Exercícios:

1. **Alterar o Texto de um Elemento:**

   - Crie uma página com um `<h2>` contendo algum texto. Ao clicar em um botão, altere o texto desse `<h2>` para "Texto Alterado com Sucesso!"

2. **Mudar a Cor de Fundo:**

   - Crie um botão que, ao ser clicado, muda a cor de fundo da página para uma cor aleatória.

3. **Contador de Cliques:**

   - Crie um contador de cliques. Cada vez que o usuário clicar em um botão, o número de cliques deve ser exibido em um parágrafo.

4. **Formulário de Contato:**

   - Crie um formulário com campos para `"Nome"`, `"Email"` e `"Mensagem"`. Ao clicar no botão de `"Enviar"`, mostre uma mensagem de agradecimento abaixo do formulário, mas sem realmente enviar o formulário (use `event.preventDefault()`).
