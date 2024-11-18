# Aula sobre `grid-layout` em CSS

## O que é `grid-layout`?

O CSS Grid Layout é um modelo de layout bidimensional que permite criar designs complexos e responsivos de forma intuitiva. Ele organiza o conteúdo em uma grade de linhas e colunas, facilitando a criação de layouts tanto em linhas quanto em colunas.

## Como funciona o Grid Layout?

Ao aplicar `display: grid` a um container, ele se torna um **grid container**, e seus filhos se tornam **grid items**. O container é dividido em linhas e colunas, e você pode posicionar os itens nas células da grade.

## Propriedades do Grid Container

### `grid-template-columns`

Define o número e o tamanho das colunas da grade. Você pode usar valores absolutos, relativos, ou até mesmo funções como `fr` (fração).

**Exemplo:**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr; /* Três colunas com larguras proporcionais */
}
```

Neste exemplo, a largura das colunas é dividida em três partes, onde a coluna do meio é duas vezes mais larga que as outras duas.

### `grid-template-rows`

Define o número e o tamanho das linhas da grade, semelhante a `grid-template-columns`.

**Exemplo:**

```css
.container {
  display: grid;
  grid-template-rows: 100px auto 200px; /* Três linhas com tamanhos específicos */
}
```

Aqui, a primeira linha tem 100px de altura, a segunda se ajusta automaticamente ao conteúdo, e a terceira tem 200px de altura.

### `grid-template-areas`

Cria áreas nomeadas na grade para um layout mais intuitivo e fácil de visualizar.

**Exemplo:**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
  grid-template-rows: auto 1fr auto;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}

.header {
  grid-area: header;
}

.sidebar {
  grid-area: sidebar;
}

.content {
  grid-area: content;
}

.footer {
  grid-area: footer;
}
```

Neste exemplo, você define áreas nomeadas que são atribuídas aos itens, facilitando a visualização e o gerenciamento do layout.

### `grid-column` e `grid-row`

Essas propriedades permitem que você especifique a posição e o tamanho dos itens nas linhas e colunas da grade.

**Exemplo:**

```css
.item {
  grid-column: 1 / 3; /* O item ocupa da coluna 1 até a 3 */
  grid-row: 2 / 4; /* O item ocupa da linha 2 até a 4 */
}
```

Esse item será posicionado na primeira e segunda coluna e na segunda e terceira linha.

### `grid-template`

O `grid-template` é uma propriedade curta que combina `grid-template-rows` e `grid-template-columns`.

**Exemplo:**

```css
.container {
  display: grid;
  grid-template: 50% 50% / 200px; 
}
```

Isso irá criar uma grade com duas linhas com 50% cada, e uma coluna que tem 200 pixels de largura.

### `grid-gap`

Define o espaço entre as linhas e colunas da grade.

**Exemplo:**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto;
  grid-gap: 10px; /* Espaço de 10px entre colunas e linhas */
}
```

Aqui, o `grid-gap` adiciona 10px de espaço entre todas as células da grade.

### `justify-items` e `align-items`

Controlam o alinhamento dos itens dentro de suas células.

**Exemplo:**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  justify-items: center; /* Alinha os itens horizontalmente ao centro */
  align-items: start; /* Alinha os itens verticalmente ao início */
}
```

Os itens serão centralizados horizontalmente e alinhados ao início da célula verticalmente.

### `justify-content` e `align-content`

Controlam o alinhamento da grade inteira dentro do container.

**Exemplo:**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto;
  justify-content: space-between; /* Distribui o espaço horizontalmente entre a grade e as bordas do container */
  align-content: center; /* Alinha a grade verticalmente ao centro do container */
}
```

A grade será distribuída uniformemente horizontalmente, e verticalmente, será centralizada no container.

### `grid-auto-flow`

Controla o fluxo automático dos itens quando não são explicitamente posicionados.

**Exemplo:**

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-flow: dense; /* Preenche espaços vazios de forma densa */
}
```

Com `grid-auto-flow: dense`, o Grid Layout tenta preencher os espaços vazios, ajustando o layout dos itens para usar o espaço disponível de forma mais eficiente.

### `minmax()`

A função `minmax()` permite definir o tamanho mínimo e máximo de uma faixa (track) no grid. Isso é especialmente útil para criar layouts responsivos onde os tamanhos dos elementos podem ajustar-se dinamicamente com base no espaço disponível.

#### Sintaxe

```css
grid-template-columns: minmax(min, max);
grid-template-rows: minmax(min, max);
```

- `min` é o tamanho mínimo da faixa.
- `max` é o tamanho máximo da faixa.

**Exemplo:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exemplo minmax</title>
    <style>
        .grid-container {
            display: grid;
            grid-template-columns: repeat(3, minmax(100px, 1fr));
            gap: 10px;
        }
        .grid-item {
            background-color: #bada55;
            padding: 20px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="grid-container">
        <div class="grid-item">1</div>
        <div class="grid-item">2</div>
        <div class="grid-item">3</div>
        <div class="grid-item">4</div>
        <div class="grid-item">5</div>
        <div class="grid-item">6</div>
    </div>
</body>
</html>
```

Neste exemplo, cada coluna terá pelo menos 100px de largura, mas pode expandir até ocupar 1fr (uma fração do espaço disponível) se houver espaço suficiente.

### `auto-fit` e `auto-fill`

Os valores `auto-fit` e `auto-fill` são usados com a função `repeat()` para criar faixas (tracks) responsivas que se ajustam automaticamente com base no espaço disponível no container.

#### `auto-fit`

O `auto-fit` ajusta automaticamente o número de faixas para caber no container, mesmo que algumas delas estejam vazias. Isso pode criar espaços flexíveis que se ajustam dinamicamente.

**Exemplo:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exemplo auto-fit</title>
    <style>
        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 10px;
        }
        .grid-item {
            background-color: #bada55;
            padding: 20px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="grid-container">
        <div class="grid-item">1</div>
        <div class="grid-item">2</div>
        <div class="grid-item">3</div>
        <div class="grid-item">4</div>
        <div class="grid-item">5</div>
        <div class="grid-item">6</div>
    </div>
</body>
</html>
```

Com `auto-fit`, o grid ajustará o número de colunas para caber no espaço disponível. Se houver mais espaço do que colunas, as colunas restantes se expandirão para ocupar o espaço disponível.

#### `auto-fill`

O `auto-fill` funciona de maneira similar ao `auto-fit`, mas ao invés de ajustar o número de faixas para caber no container, ele cria tantas faixas quanto possível, mesmo que isso signifique que algumas delas estarão vazias.

**Exemplo:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exemplo auto-fill</title>
    <style>
        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
            gap: 10px;
        }
        .grid-item {
            background-color: #bada55;
            padding: 20px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="grid-container">
        <div class="grid-item">1</div>
        <div class="grid-item">2</div>
        <div class="grid-item">3</div>
        <div class="grid-item">4</div>
        <div class="grid-item">5</div>
        <div class="grid-item">6</div>
    </div>
</body>
</html>
```

Com `auto-fill`, o grid criará tantas colunas de 100px (ou mais, se houver espaço) quanto possível. Se houver mais espaço do que colunas, as colunas vazias ocuparão o espaço disponível.

>[!TIP]
><details>
><summary>DICA</summary>  
>  Usar <code>minmax()</code>, <code>auto-fit</code> e <code>auto-fill</code> ajuda a criar layouts flexíveis e responsivos, ajustando os elementos de acordo com o espaço disponível no container. Isso permite que os layouts sejam mais adaptáveis a diferentes tamanhos de tela e resoluções.  
></details>

## Exemplos Práticos

### Layout de Site

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    .container {
      display: grid;
      grid-template-columns: 1fr 2fr;
      grid-template-rows: auto 1fr auto;
      grid-template-areas:
        "header header"
        "sidebar content"
        "footer footer";
      grid-gap: 10px;
    }
    .header {
      grid-area: header;
      background-color: lightcoral;
      padding: 20px;
    }
    .sidebar {
      grid-area: sidebar;
      background-color: lightblue;
      padding: 20px;
    }
    .content {
      grid-area: content;
      background-color: lightgreen;
      padding: 20px;
    }
    .footer {
      grid-area: footer;
      background-color: lightgoldenrodyellow;
      padding: 20px;
    }
  </style>
  <title>Grid Layout Example</title>
</head>
<body>
  <div class="container">
    <div class="header">Header</div>
    <div class="sidebar">Sidebar</div>
    <div class="content">Content</div>
    <div class="footer">Footer</div>
  </div>
</body>
</html>
```

### Layout com Áreas Nomeadas

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    .container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-template-rows: 100px auto;
      grid-template-areas:
        "header header"
        "main aside";
      grid-gap: 20px;
    }
    .header {
      grid-area: header;
      background-color: lightcoral;
    }
    .main {
      grid-area: main;
      background-color: lightblue;
    }
    .aside {
      grid-area: aside;
      background-color: lightgreen;
    }
  </style>
  <title>Named Areas Example</title>
</head>
<body>
  <div class="container">
    <div class="header">Header</div>
    <div class="main">Main Content</div>
    <div class="aside">Aside</div>
  </div>
</body>
</html>
```
