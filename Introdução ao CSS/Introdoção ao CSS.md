# Aula de CSS

## Objetivos da Aula

- Compreender o que é CSS e para que serve.
- Aprender a incluir CSS em um documento HTML.
- Conhecer os principais seletores e propriedades CSS.
- Aplicar estilização básica com margin, padding, alinhamento e fontes.

## O que é CSS?

- **CSS (Cascading Style Sheets)** é uma linguagem de estilo usada para descrever a apresentação de um documento escrito em HTML ou XML.

- CSS separa o conteúdo do documento (HTML) da sua apresentação visual.

## Incluindo CSS no HTML

Existem três maneiras principais de adicionar CSS a um documento HTML:

1. **Inline CSS**:

    ```html
    <h1 style="color: blue;">Título Azul</h1>
    ```

2. **Internal CSS** (dentro da tag `<style>` no `<head>`):

    ```html
    <head>
      <style>
        h1 {
          color: blue;
        }
      </style>
    </head>
    ```

3. **External CSS** (em um arquivo separado):

    ```html
    <head>
      <link rel="stylesheet" type="text/css" href="styles.css">
    </head>
    ```

## Sintaxe CSS

- **Seletores**: Definem quais elementos HTML serão estilizados.
- **Declarações**: Dentro das chaves `{}`, especificam as propriedades e valores.

    ```css
    h1 {
      color: blue;
      font-size: 24px;
    }
    ```

## Seletores Básicos

- **Elemento**: Seleciona todos os elementos do mesmo tipo.

    ```css
    p {
      color: green;
    }
    ```

- **Classe**: Seleciona elementos com um atributo de classe específico.

    ```css
    .myClass {
      color: red;
    }
    ```

- **ID**: Seleciona um elemento com um atributo de ID específico.

    ```css
    #myId {
      color: purple;
    }
    ```

## Propriedades CSS Comuns

- **Cor e Fonte**:

    ```css
    color: blue; /* Cor do texto */
    font-size: 16px; /* Tamanho da fonte */
    font-family: Arial, sans-serif; /* Tipo de fonte */
    ```

- **Margem e Espaçamento**:

    ```css
    margin: 20px; /* Margem externa */
    padding: 10px; /* Espaçamento interno */
    ```

- **Alinhamento**:

    ```css
    text-align: center; /* Alinhamento do texto */
    ```

## Exemplo Completo

Vamos aplicar o que aprendemos em um exemplo completo:

**HTML**:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Exemplo CSS</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <h1 class="title">Bem-vindo ao CSS!</h1>
  <p id="intro">CSS é incrível para estilizar seu HTML.</p>
</body>
</html>
```

**CSS**:

```css
/* Estilizando o título */
.title {
  color: blue;
  font-size: 24px;
  text-align: center;
}

/* Estilizando o parágrafo */
#intro {
  color: green;
  font-size: 18px;
  margin: 20px;
  padding: 10px;
  font-family: Arial, sans-serif;
}
```
