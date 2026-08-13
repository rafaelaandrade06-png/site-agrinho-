<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Projeto Agrinho - Blog e Feed</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <header class="header-azul">
    <h1>🌱 Projeto Agrinho</h1>
    <p>Sustentabilidade, Inovação e Campo</p>
  </header>

  <main class="container">
    <section class="card novo-post">
      <h2>Criar Nova Publicação</h2>
      <form id="form-post">
        <input type="text" id="titulo" placeholder="Título da publicação..." required>
        <textarea id="conteudo" rows="4" placeholder="Escreva sobre o seu projeto do Agrinho..." required></textarea>
        <button type="submit">Publicar</button>
      </form>
    </section>

    <section>
      <h2>Publicações</h2>
      <div id="feed-posts"></div>
    </section>
  </main>

  <script src="script.js"></script>
</body>
</html>
/* Configurações Gerais */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
  background-color: #f4f7f6;
  color: #333;
}

/* Cabeçalho Azul */
.header-azul {
  background-color: #1e88e5;
  color: #ffffff;
  text-align: center;
  padding: 2.5rem 1rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.header-azul h1 {
  font-size: 2.2rem;
  margin-bottom: 0.5rem;
}

/* Container Principal */
.container {
  max-width: 700px;
  margin: 2rem auto;
  padding: 0 1rem;
}

/* Estilo dos Cards */
.card {
  background: #ffffff;
  border-radius: 8px;
  padding: 1.5rem;
  margin-bottom: 1.5rem;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
}

/* Formulário */
.novo-post h2 {
  margin-bottom: 1rem;
  color: #1e88e5;
}

.novo-post input, 
.novo-post textarea {
  width: 100%;
  padding: 0.8rem;
  margin-bottom: 1rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 1rem;
}

.novo-post button {
  background-color: #2e7d32; /* Verde Agrinho */
  color: white;
  border: none;
  padding: 0.8rem 1.5rem;
  font-size: 1rem;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s;
}

.novo-post button:hover {
  background-color: #1b5e20;
}

/* Posts do Feed */
.post h3 {
  color: #1565c0;
  margin-bottom: 0.5rem;
}

.post p {
  line-height: 1.5;
  margin-bottom: 1rem;
}

.btn-curtir {
  background-color: #e3f2fd;
  color: #1e88e5;
  border: 1px solid #90caf9;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  cursor: pointer;
  font-weight: bold;
  transition: all 0.2s;
}

.btn-curtir:hover {
  background-color: #1e88e5;
  color: white;
}
document.addEventListener('DOMContentLoaded', () => {
  const formPost = document.getElementById('form-post');
  const feedPosts = document.getElementById('feed-posts');

  // Adiciona um post inicial de exemplo
  criarPost('Sustentabilidade na Escola', 'Nosso projeto do Agrinho deste ano foca na reciclagem e hortas comunitárias.');

  // Evento ao enviar o formulário
  formPost.addEventListener('submit', (e) => {
    e.preventDefault();

    const titulo = document.getElementById('titulo').value;
    const conteudo = document.getElementById('conteudo').value;

    criarPost(titulo, conteudo);

    // Limpa o formulário
    formPost.reset();
  });

  // Função para criar a estrutura do post
  function criarPost(titulo, conteudo) {
    const postArtigo = document.createElement('article');
    postArtigo.classList.add('card', 'post');

    let curtidas = 0;

    postArtigo.innerHTML = `
      <h3>${titulo}</h3>
      <p>${conteudo}</p>
      <button class="btn-curtir">👍 Curtir (<span class="qtd-curtidas">0</span>)</button>
    `;

    // Lógica do Botão de Curtir
    const btnCurtir = postArtigo.querySelector('.btn-curtir');
    const spanCurtidas = postArtigo.querySelector('.qtd-curtidas');

    btnCurtir.addEventListener('click', () => {
      curtidas++;
      spanCurtidas.textContent = curtidas;
    });

    // Insere o novo post no topo do feed
    feedPosts.prepend(postArtigo);
  }
});

























