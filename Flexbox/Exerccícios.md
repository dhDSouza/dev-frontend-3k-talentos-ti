# Exercício de Flexbox para fixação

## Exercícios Básicos: Conceitos Fundamentais do Flexbox

1. **Centralizar um item**:

   - Crie um contêiner com um único item dentro.
   - Use o `display: flex` no contêiner e centralize o item horizontal e verticalmente.

2. **Centralizar uma coluna de itens**:

   - Coloque 3 itens em um contêiner flex.
   - Alinhe todos os itens ao centro (horizontal e verticalmente).

3. **Distribuição de espaço entre itens**:

   - Coloque 4 itens em um contêiner.
   - Use o `justify-content` para testar diferentes espaçamentos (`space-between`, `space-around`, `space-evenly`).

4. **Direção de layout com flex-direction**:

   - Crie uma linha de 3 itens em um contêiner flex.
   - Altere o `flex-direction` para coluna e veja como os itens se comportam.

5. **Mudando a ordem dos itens**:
   - Crie 3 itens em um contêiner e use a propriedade `order` para alterar a posição de cada um deles.

## Exercícios Intermediários: Ajustando Layouts com Flexbox

1. **Dividir a tela em duas colunas**:

   - Crie um layout onde o contêiner tem duas colunas (50% cada).
   - Use `flex-grow`, `flex-shrink`, e `flex-basis` para ajustar o tamanho de cada coluna responsivamente.

2. **Criar uma barra de navegação horizontal**:

   - Monte um menu de navegação com 4 itens que se alinhem horizontalmente e com espaçamento entre eles.
   - Centralize o menu na parte superior da página, e faça-o ocupar toda a largura do contêiner.

3. **Layout de Cards**:

   - Monte 4 cards em um contêiner flex que se alinhem em uma linha.
   - Defina um espaçamento igual entre os cards, e configure para que a linha quebre quando a tela for reduzida.

4. **Criar um layout de "footer" flexível**:

   - Coloque 3 itens no footer (ex: links, redes sociais, direitos autorais).
   - Faça o primeiro item alinhar à esquerda, o segundo ao centro e o terceiro à direita.

## Exercícios Avançados: Layouts Mais Complexos

1. **Grid de Galeria de Imagens**:

    - Crie uma galeria de imagens em 3 colunas.
    - Faça o layout ajustar para 2 colunas em tablets e 1 coluna em celulares.

2. **Layout de "Dashboard"**:

    - Crie um contêiner com uma barra lateral e um contêiner principal.
    - Use `flex-direction: row` para alinhar a barra lateral à esquerda e o conteúdo principal à direita.
    - Faça a barra lateral ocupar 25% e o contêiner principal 75% da largura da tela.

3. **Reproduzir uma “landing page” básica**:

    - Divida a página em um cabeçalho com título centralizado, uma seção de conteúdo e um footer.
    - No conteúdo, crie uma seção de três colunas (com flexbox) com títulos, descrições e botões de ação.

4. **Desenvolver um layout de "tabela de preços"**:

    - Monte três cards de preços com título, descrição e botão.
    - Centralize cada card no contêiner flex e configure para que o layout se ajuste a telas menores.

### Extras e Desafios

1. **Simular um layout tipo "mural" com flex-wrap**:

    - Coloque 10 itens no contêiner e use `flex-wrap` para que eles se alinhem automaticamente em múltiplas linhas.

2. **Layout de "Cartão de Perfil" com Flexbox**:

    - Crie um cartão de perfil com avatar, nome, descrição e botões de ação.
    - Use `align-items` e `justify-content` para ajustar o layout do conteúdo dentro do card.

### Dicas Adicionais

- **Inspecionar**: Utilize as ferramentas de desenvolvimento do navegador para inspecionar e testar o flexbox ao vivo.

- **Refatoração**: Experimente diferentes combinações de propriedades `align-items`, `justify-content`, `flex-direction` para ver os efeitos no layout.
