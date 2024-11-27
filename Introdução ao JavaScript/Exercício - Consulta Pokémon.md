# Pokémon API

A `API` do Pokémon *(Pokémon API ou PokeAPI)* é uma interface que permite acessar informações sobre Pokémon, suas habilidades, movimentos, tipos e muito mais. Ela é muito útil para desenvolvedores criarem aplicativos ou sites relacionados ao mundo dos Pokémon.

Neste exercício, vamos usar a `API` para criar uma Pokédex, manipulando o DOM e fazendo uso do `fetch` para buscar as informações da `API`.

### Como Funciona a API do Pokémon

A `PokeAPI` fornece endpoints que podem ser acessados via requisições `HTTP`. Cada endpoint retorna dados no formato `JSON`, que podem ser manipulados para exibir informações na interface do usuário.

### Endpoints Principais da PokeAPI

Aqui está uma tabela com alguns dos principais endpoints da `PokeAPI` e os parâmetros que podem ser usados com eles:

| **Endpoint**                           | **Descrição**                                            | **Argumentos**                                                                                   |
|----------------------------------------|----------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| `/pokemon/{id}`                        | Obtém informações sobre um Pokémon específico.            | `id` ou `name`: Número ou nome do Pokémon (ex.: "pikachu", "25")                                  |
| `/pokemon-species/{id}`                | Obtém informações sobre a espécie do Pokémon.             | `id`: ID do Pokémon na base de dados (ex.: "pikachu" tem o ID 25).                               |
| `/pokemon/{id}/abilities`              | Obtém as habilidades de um Pokémon.                       | `id`: ID ou nome do Pokémon (ex.: "charizard", "6")                                               |
| `/type/{id}`                           | Obtém informações sobre um tipo específico (ex.: Fogo).   | `id`: Nome ou número do tipo (ex.: "fire", "1")                                                  |
| `/ability/{id}`                        | Obtém informações sobre uma habilidade específica.       | `id`: ID ou nome da habilidade (ex.: "overgrow")                                                  |
| `/move/{id}`                           | Obtém informações sobre um movimento de Pokémon.         | `id`: ID ou nome do movimento (ex.: "flamethrower")                                               |
| `/pokemon/{id}/moves`                  | Obtém os movimentos que um Pokémon pode aprender.        | `id`: ID ou nome do Pokémon (ex.: "bulbasaur")                                                   |
| `/pokemon/{id}/stats`                  | Obtém as estatísticas de um Pokémon (HP, Attack, etc.).   | `id`: ID ou nome do Pokémon (ex.: "squirtle")                                                    |
| `/region/{id}`                         | Obtém informações sobre uma região do jogo Pokémon.      | `id`: ID ou nome da região (ex.: "kanto", "johto")                                               |

### Exemplo de Uso da API

#### 1. **Obter informações sobre um Pokémon**:

Requisição: `GET /pokemon/{id}`  
Exemplo: Para obter dados sobre o Pikachu (ID = 25):

```javascript
fetch('https://pokeapi.co/api/v2/pokemon/25')
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(error => console.error('Erro:', error));
```

### Exercício: Criar uma Pokédex com Manipulação de DOM

**Objetivo:** Usar `fetch` para pegar os dados de um Pokémon e exibi-los na página. O aluno deve manipular o `DOM` para mostrar o nome, imagem, tipo, e algumas estatísticas de um Pokémon.

#### Passos:

1. **Criar a estrutura HTML**:

   Crie um campo de busca para o nome do Pokémon e uma área para exibir as informações.

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pokédex</title>
</head>
<body>
    <h1>Pokédex</h1>
    <input type="text" id="pokemonName" placeholder="Digite o nome do Pokémon">
    <button id="searchButton">Buscar</button>
    
    <div id="pokemonInfo">
        <h2 id="pokemonTitle"></h2>
        <img id="pokemonImage" src="" alt="Imagem do Pokémon">
        <p id="pokemonType"></p>
        <p id="pokemonStats"></p>
    </div>

    <script src="script.js"></script>
</body>
</html>
```

2. **Criar a lógica em JavaScript**:
   Agora, crie um arquivo `script.js` que faz a requisição à PokeAPI usando o `fetch` e manipula o DOM para exibir os dados.

```javascript
document.getElementById('searchButton').addEventListener('click', () => {
    let pokemonName = document.getElementById('pokemonName').value.toLowerCase();
    fetch(`https://pokeapi.co/api/v2/pokemon/${pokemonName}`)
        .then(response => response.json())
        .then(data => {
            // Manipulando o DOM para exibir as informações
            document.getElementById('pokemonTitle').textContent = data.name.toUpperCase();
            document.getElementById('pokemonImage').src = data.sprites.front_default;
            document.getElementById('pokemonType').textContent = `Tipo(s): ${data.types.map(type => type.type.name).join(', ')}`;
            
            // Exibindo as estatísticas
            let stats = data.stats.map(stat => `${stat.stat.name}: ${stat.base_stat}`).join(', ');
            document.getElementById('pokemonStats').textContent = `Estatísticas: ${stats}`;
        })
        .catch(error => {
            alert('Pokémon não encontrado!');
            console.error('Erro:', error);
        });
});
```

3. **Explicação do Código**:

   - O usuário digita o nome do Pokémon no campo de entrada.
   - Quando o botão "Buscar" é clicado, a função `fetch` é chamada com a URL da API, que retorna dados sobre o Pokémon em formato JSON.
   - O nome, imagem, tipo e estatísticas do Pokémon são extraídos da resposta e exibidos no DOM.
   - Se o Pokémon não for encontrado, um erro é exibido.

### Resultado Esperado:

Ao digitar o nome de um Pokémon (ex.: "pikachu"), a Pokédex mostrará informações como o nome, a imagem, o tipo (como "Elétrico") e suas estatísticas (HP, Attack, Defense, etc.).

### Desafio:

- Mostrar uma lista de todos os tipos de Pokémon com suas descrições.
- Adicionar a funcionalidade para pesquisar por ID (número) do Pokémon em vez do nome.
