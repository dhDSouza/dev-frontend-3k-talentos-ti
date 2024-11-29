# **Criação de Portfólio Pessoal com HTML, CSS e JavaScript** 🎨💻

## **Objetivo** 📚:

O objetivo desta atividade é construir um **portfólio pessoal** interativo e funcional utilizando HTML, CSS e JavaScript. O portfólio deverá conter seções de apresentação, habilidades, projetos e contato, e será estruturado com **tags semânticas**, **layout responsivo** com **Flexbox** e **Grid Layout**, além de incluir funcionalidades com **JavaScript**, como manipulação de DOM, consumo de APIs e interatividade com eventos.

## **Instruções** 📝:

### 1. **Estrutura do Portfólio** 🏗️:

   - O seu portfólio deve ser dividido em várias seções, sendo as mínimas necessárias:
     - **Seção de Introdução**: Uma breve apresentação sobre você.
     - **Seção de Habilidades**: Uma lista das suas principais habilidades e tecnologias.
     - **Seção de Projetos**: Exibição de 2 ou 3 projetos desenvolvidos (com links e descrições).
     - **Seção de Contato**: Formulário para envio de mensagem, com validação de campos.
   - Use **tags semânticas** para estruturar corretamente o conteúdo (exemplo: `<header>`, `<main>`, `<section>`, `<footer>`).

### 2. **HTML** 🔤:

   - A estrutura do HTML deve ser clara, com **tags semânticas** e boas práticas de acessibilidade.
   - O HTML deverá incluir links para o CSS e para o JavaScript.
   - Exemplo de estrutura básica:
     
     ```html
     <header>
       <h1>Meu Portfólio</h1>
       <nav>
         <ul>
           <li><a href="#introducao">Introdução</a></li>
           <li><a href="#habilidades">Habilidades</a></li>
           <li><a href="#projetos">Projetos</a></li>
           <li><a href="#contato">Contato</a></li>
         </ul>
       </nav>
     </header>

     <main>
       <section id="introducao">
         <!-- Conteúdo da introdução -->
       </section>
       <section id="habilidades">
         <!-- Conteúdo das habilidades -->
       </section>
       <section id="projetos">
         <!-- Conteúdo dos projetos -->
       </section>
       <section id="contato">
         <!-- Formulário de contato -->
       </section>
     </main>

     <footer>
       <p>&copy; 2024 Meu Portfólio</p>
     </footer>
     ```

### 3. **CSS** 🎨:

   - Utilize **Flexbox** e **Grid Layout** para criar um layout responsivo, ajustável para diferentes tamanhos de tela (desktop, tablet e mobile).
   - Aplique estilos para tornar o portfólio visualmente agradável, mantendo a clareza e simplicidade.
   - Exemplo básico de layout com Flexbox:
     
     ```css
     body {
       display: flex;
       flex-direction: column;
       justify-content: center;
       align-items: center;
     }

     header {
       background-color: #333;
       color: #fff;
       width: 100%;
       text-align: center;
     }

     main {
       display: grid;
       grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
       gap: 20px;
     }
     ```

### 4. **JavaScript** 📱:

   - **Manipulação de DOM**: Crie interatividade na página, como animações, mudanças de estilo, ou alternância de conteúdo.
   - **Eventos**: Utilize eventos como `click`, `submit`, e `mouseover` para interagir com o usuário.
   - **Validação de Formulário**: Adicione validação para os campos do formulário de contato, garantindo que todos os campos sejam preenchidos corretamente.
   - **Consumo de API com Fetch**: Implemente a exibição de dados dinâmicos em seu portfólio. Por exemplo, consuma uma API pública de projetos ou informações sobre tecnologias que você utiliza e exiba essas informações em uma seção do seu portfólio.
   - Exemplo de uso de `fetch` para consumir uma API:
     
     ```javascript
     fetch('https://api.example.com/projects')
       .then(response => response.json())
       .then(data => {
         const projectsContainer = document.getElementById('projetos');
         data.projects.forEach(project => {
           const projectElement = document.createElement('div');
           projectElement.innerHTML = `<h3>${project.name}</h3><p>${project.description}</p>`;
           projectsContainer.appendChild(projectElement);
         });
       })
       .catch(error => console.error('Erro ao carregar projetos:', error));
     ```

### 5. **Organização dos Arquivos** 📂:

   - **Pastas**: Organize seu projeto em pastas para facilitar a manutenção e escalabilidade.
     - `/assets` – Para imagens e outros recursos estáticos.
     - `/css` – Arquivo de estilo (ex: `styles.css`).
     - `/js` – Arquivo de scripts JavaScript (ex: `script.js`).
     - `/index.html` – Arquivo principal HTML.
   - Certifique-se de que todos os arquivos estejam devidamente linkados no HTML:
     ```html
     <link rel="stylesheet" href="css/styles.css">
     <script src="js/script.js" defer></script>
     ```

### 6. **Validação e Testes** ✅:

   - Teste o seu portfólio em diferentes navegadores (Chrome, Firefox, Safari, etc.) e dispositivos para garantir a compatibilidade e responsividade.
   - O formulário de contato deve ser validado para garantir que todos os campos obrigatórios sejam preenchidos antes do envio.

### 7. **Entrega** 📨:

   - Após concluir o projeto, submeta-o em um repositório no GitHub. O repositório deve estar bem organizado e conter um arquivo `README.md` com uma descrição do projeto e instruções básicas de como visualizar o portfólio.
   - O link para o seu repositório GitHub deve ser compartilhado com o professor para avaliação.

## **Critérios de Avaliação** 📊:

- **Organização e Estrutura do Código**: Utilização de tags semânticas, organização clara do HTML, CSS e JavaScript.
- **Responsividade e Layout**: Utilização correta de Flexbox e Grid Layout para garantir que o portfólio seja responsivo.
- **Interatividade**: Funcionalidades implementadas com JavaScript (validação de formulário, consumo de API, manipulação de DOM).
- **Design**: Estilo visual do portfólio, clareza e legibilidade.
- **Documentação**: Organização dos arquivos e descrição no GitHub.

## **Referências e Exemplos** 📚:

- **MDN Web Docs**: [HTML5 Semantics](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- **CSS Flexbox**: [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- **CSS Grid Layout**: [CSS Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- **JavaScript Fetch API**: [Fetch API MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)

**Boa sorte e mãos à obra! 🎉👨‍💻👩‍💻**
