# Aula sobre `display: flex` em CSS

## O que é `display: flex`?

A propriedade `display: flex` ativa o **Flexbox**, um modelo de layout que facilita a criação de layouts flexíveis e responsivos. Ele permite alocar espaço e alinhar itens dentro de um container de maneira eficiente, mesmo quando o tamanho dos itens é desconhecido ou dinâmico.

## Como funciona o Flexbox?

Quando você aplica `display: flex` a um container, ele se torna um **flex container**. Seus filhos se tornam **flex items** e são automaticamente organizados de acordo com o modelo Flexbox. O Flexbox é baseado em dois eixos:

1. **Eixo Principal (Main Axis)**: O eixo principal é o eixo ao longo do qual os itens são organizados. Por padrão, é horizontal.
2. **Eixo Transversal (Cross Axis)**: O eixo transversal é perpendicular ao eixo principal. Por padrão, é vertical.

## Propriedades Principais

### No Flex Container

1. **`flex-direction`**: Define a direção dos itens no eixo principal.
   - `row` (padrão): Alinha os itens horizontalmente.
   - `column`: Alinha os itens verticalmente.
   - `row-reverse`: Alinha os itens horizontalmente na ordem inversa.
   - `column-reverse`: Alinha os itens verticalmente na ordem inversa.

2. **`flex-wrap`**: Controla se os itens devem quebrar para a próxima linha quando não houver espaço suficiente.
   - `nowrap` (padrão): Todos os itens ficam em uma única linha.
   - `wrap`: Os itens quebram em várias linhas.
   - `wrap-reverse`: Os itens quebram em várias linhas, mas na ordem inversa.

3. **`flex-flow`**: É uma combinação de `flex-direction` e `flex-wrap`.
   - Exemplo: `flex-flow: row wrap;`

4. **`justify-content`**: Alinha os itens ao longo do eixo principal.
   - `flex-start` (padrão): Alinha os itens no início do container.
   - `center`: Alinha os itens no centro do container.
   - `space-between`: Distribui os itens com espaço igual entre eles.
   - `space-around`: Distribui os itens com espaço igual ao redor deles.
   - `space-evenly`: Distribui os itens com espaço igual entre e ao redor deles.

5. **`align-items`**: Alinha os itens ao longo do eixo transversal.
   - `stretch` (padrão): Estica os itens para preencher o container.
   - `flex-start`: Alinha os itens no início do eixo transversal.
   - `center`: Alinha os itens no centro do eixo transversal.
   - `flex-end`: Alinha os itens no final do eixo transversal.
   - `baseline`: Alinha os itens ao longo da linha de base do texto.

6. **`align-content`**: Alinha as linhas de itens no eixo transversal quando há múltiplas linhas.
   - `flex-start`: Alinha no início do container.
   - `center`: Alinha no centro do container.
   - `space-between`: Distribui linhas com espaço igual entre elas.
   - `space-around`: Distribui linhas com espaço igual ao redor delas.
   - `stretch`: Estica as linhas para preencher o container.

7. **`align-self`**: Permite que um item individual se alinhe de maneira diferente do restante dos itens no eixo transversal. É aplicado a um item flexível específico.
   - Pode ser `auto`, `flex-start`, `center`, `flex-end`, `baseline`, ou `stretch`.

### Nos Flex Items

1. **`flex`**: Define a capacidade de crescimento, encolhimento e a base dos itens. É uma combinação de `flex-grow`, `flex-shrink`, e `flex-basis`.
   - Exemplo: `flex: 1;` faz o item crescer para preencher o espaço disponível.

2. **`flex-grow`**: Define a capacidade de crescimento do item. `1` significa que o item cresce para preencher o espaço disponível.

3. **`flex-shrink`**: Define a capacidade do item de encolher quando o espaço é limitado. `1` significa que o item encolhe conforme necessário.

4. **`flex-basis`**: Define o tamanho inicial do item antes de o espaço disponível ser distribuído. Pode ser um valor específico como `200px` ou `20%`.

5. **`align-self`**: Permite definir a aliança individual do item ao longo do eixo transversal, sobrescrevendo `align-items`.

## Quando Utilizar Flexbox?

- **Layouts Responsivos**: Flexbox é ideal para criar layouts que se adaptam a diferentes tamanhos de tela e dispositivos.
- **Alinhamento e Distribuição**: Quando você precisa alinhar itens ou distribuir espaço de maneira uniforme entre eles.
- **Organização de Layout**: Quando o layout precisa ser dinâmico e os tamanhos dos itens podem variar.

## Exemplo Prático

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    .container {
      display: flex;
      flex-direction: row;
      justify-content: space-around;
      align-items: center;
      height: 100vh;
    }
    .item {
      background-color: lightblue;
      padding: 20px;
      border: 1px solid #333;
    }
  </style>
  <title>Flexbox Example</title>
</head>
<body>
  <div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
  </div>
</body>
</html>
```

Neste exemplo, os itens são distribuídos horizontalmente (`flex-direction: row`), centralizados verticalmente (`align-items: center`), e o espaço entre eles é distribuído uniformemente (`justify-content: space-around`).
