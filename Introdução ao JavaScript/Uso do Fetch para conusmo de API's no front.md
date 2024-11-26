# Uso do `fetch`

### **O que é `fetch`?**

`fetch` é uma função embutida em navegadores modernos que permite fazer requisições `HTTP` de maneira assíncrona. Com ele, podemos interagir com APIs, obtendo dados ou enviando informações. O `fetch` utiliza Promises, tornando o código mais legível e fácil de trabalhar.

### **Sintaxe básica:**

```javascript
fetch(url, options)
  .then(response => response.json()) // Converte a resposta em JSON
  .then(data => console.log(data))    // Exibe os dados recebidos no console
  .catch(error => console.error('Erro:', error)); // Trata erros
```

- **url**: O endpoint da API que você deseja acessar.
- **options**: Objeto opcional para configurar o método, cabeçalhos, corpo, etc.
- **response.json()**: Converte a resposta da API em JSON (geralmente o formato de dados de uma API REST).
- **.catch()**: Trata erros na requisição.

### **Passo a Passo da Requisição:**

1. **Faz a requisição** usando a função `fetch()`.
2. **Recebe a resposta** (promessa resolvida).
3. **Transforma os dados** em um formato utilizável, como JSON.
4. **Exibe ou manipula os dados** no navegador.
5. **Trata erros** usando `.catch()`.

## 2. Exemplos Práticos

### Exemplo 1: Fazendo uma Requisição GET

Vamos consumir uma API pública que retorna uma lista de usuários. Neste exemplo, usaremos a API da [JSONPlaceholder](https://jsonplaceholder.typicode.com).

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Requisição GET com fetch</title>
</head>
<body>
  <h1>Lista de Usuários</h1>
  <ul id="userList"></ul>

  <script>
    // Fazendo uma requisição GET para obter dados de usuários
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(response => response.json()) // Converte a resposta em JSON
      .then(data => {
        const userList = document.getElementById('userList');
        
        // Itera sobre os dados e os exibe na página
        data.forEach(user => {
          const li = document.createElement('li');
          li.textContent = `${user.name} - ${user.email}`;
          userList.appendChild(li);
        });
      })
      .catch(error => console.error('Erro na requisição:', error)); // Tratamento de erros
  </script>
</body>
</html>
```

Neste exemplo, a lista de usuários é exibida na página, utilizando a função `appendChild` para adicionar elementos dinamicamente.

---

### Exemplo 2: Fazendo uma Requisição POST

Neste exemplo, enviaremos dados para a API usando o método POST.

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Requisição POST com fetch</title>
</head>
<body>
  <h1>Criação de Post</h1>

  <form id="postForm">
    <label for="title">Título:</label>
    <input type="text" id="title" placeholder="Título" required />
    
    <label for="body">Conteúdo:</label>
    <textarea id="body" placeholder="Conteúdo" required></textarea>
    
    <button type="submit">Enviar</button>
  </form>

  <script>
    document.getElementById('postForm').addEventListener('submit', function (e) {
      e.preventDefault(); // Evita o comportamento padrão do formulário

      const title = document.getElementById('title').value;
      const body = document.getElementById('body').value;

      // Enviando dados com uma requisição POST
      fetch('https://jsonplaceholder.typicode.com/posts', {
        method: 'POST', // Define o método como POST
        headers: {
          'Content-Type': 'application/json' // Cabeçalhos indicando o formato dos dados enviados
        },
        body: JSON.stringify({ title, body, userId: 1 }) // Convertendo o objeto para JSON
      })
        .then(response => response.json())
        .then(data => console.log('Post criado:', data))
        .catch(error => console.error('Erro ao enviar:', error));
    });
  </script>
</body>
</html>
```

Aqui, o formulário captura o título e o conteúdo do post e faz uma requisição POST para criar um novo post na API.

---

### Exemplo 3: Requisição GET para uma API de Filmes

Neste exemplo, vamos consumir a [OMDb API](http://www.omdbapi.com/) para buscar informações sobre um filme. Exibiremos o título, ano de lançamento e pôster do filme na página.

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Filmes com OMDb API</title>
</head>
<body>
  <h1>Detalhes do Filme</h1>
  <p id="title"></p>
  <p id="year"></p>
  <img id="poster" src="" alt="Poster do filme" />

  <script>
    const apiKey = 'sua_api_key_aqui'; // Lembre-se de substituir pela sua chave de API
    fetch(`http://www.omdbapi.com/?t=Inception&apikey=${apiKey}`)
      .then(response => response.json())
      .then(data => {
        document.getElementById('title').textContent = `Título: ${data.Title}`;
        document.getElementById('year').textContent = `Ano: ${data.Year}`;
        document.getElementById('poster').src = data.Poster;
      })
      .catch(error => console.error('Erro:', error));
  </script>
</body>
</html>
```

Este exemplo demonstra como exibir informações de um filme na página usando dados retornados pela OMDb API.

---

### Exemplo 4: Criando um Formulário Dinâmico para Busca de Filmes

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Busca de Filmes</title>
</head>
<body>
  <h1>Buscar Filme</h1>
  <form id="movieForm">
    <input type="text" id="movieTitle" placeholder="Digite o título do filme" required />
    <button type="submit">Buscar</button>
  </form>

  <h2>Resultado:</h2>
  <p id="title"></p>
  <p id="year"></p>
  <img id="poster" src="" alt="Poster do filme" />

  <script>
    const apiKey = 'sua_api_key_aqui'; // Lembre-se de substituir pela sua chave de API

    document.getElementById('movieForm').addEventListener('submit', function (e) {
      e.preventDefault(); // Evita o envio padrão do formulário

      const movieTitle = document.getElementById('movieTitle').value;

      fetch(`http://www.omdbapi.com/?t=${movieTitle}&apikey=${apiKey}`)
        .then(response => response.json())
        .then(data => {
          if (data.Response === "True") {
            document.getElementById('title').textContent = `Título: ${data.Title}`;
            document.getElementById('year').textContent = `Ano: ${data.Year}`;
            document.getElementById('poster').src = data.Poster;
          } else {
            document.getElementById('title').textContent = 'Filme não encontrado';
            document.getElementById('year').textContent = '';
            document.getElementById('poster').src = '';
          }
        })
        .catch(error => console.error('Erro:', error));
    });
  </script>
</body>
</html>
```

Este exemplo adiciona um formulário para que o usuário possa buscar informações sobre qualquer filme pela OMDb API. A pesquisa é realizada com base no título inserido no formulário.

---

### Considerações Finais

- **Trate os erros**: Sempre use `.catch()` para tratar possíveis erros na comunicação com a API.
- **Manipule o DOM**: Após obter os dados da API, exiba-os na página manipulando o DOM com JavaScript.
- **Teste em diferentes navegadores**: Embora `fetch` seja suportado pela maioria dos navegadores modernos, é importante garantir a compatibilidade com versões mais antigas, caso necessário.

Com esses exemplos, temos uma boa base para usar `fetch` tanto para consumir quanto para enviar dados para APIs.
