<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Caminhos Sustentáveis</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

    <header>
        <h1>🌱 Caminhos Sustentáveis</h1>
        <p>Conectando o campo e a cidade por um futuro melhor</p>
    </header>

    <main>

        <article>
            <img src="imagem-agrinho.png"
                alt="Ilustração representando a conexão entre o campo e a cidade">

            <div>
                <h2>Campo e cidade: uma conexão necessária</h2>

                <p class="artigo-autor">Por: Rafaela Andrade</p>

                <p>
                    O campo e a cidade possuem diferenças, mas também dependem
                    um do outro. Enquanto o campo é responsável por grande parte
                    da produção de alimentos e matérias-primas, a cidade concentra
                    serviços, comércio, tecnologia e muitas oportunidades.
                </p>

                <p>
                    A sustentabilidade é fundamental para aproximar esses dois
                    espaços e construir um futuro com mais equilíbrio,
                    responsabilidade e qualidade de vida.
                </p>

                <button class="botao-curtir">
                    ❤️ <span>0</span>
                </button>

                <button class="botao-curtir">
                    👍 <span>0</span>
                </button>
            </div>
        </article>


        <article>
            <img src="imagem-agrinho.png"
                alt="Paisagem mostrando uma área rural e uma cidade">

            <div>
                <h2>A importância do campo</h2>

                <p class="artigo-autor">Por: Rafaela Andrade</p>

                <p>
                    O campo tem um papel essencial na nossa sociedade. É nele
                    que são produzidos muitos dos alimentos que chegam até as
                    nossas mesas, além de matérias-primas utilizadas em diversos
                    produtos.
                </p>

                <p>
                    Utilizar práticas agrícolas sustentáveis ajuda a preservar
                    o solo, a água, a biodiversidade e os recursos naturais.
                </p>

                <button class="botao-curtir">
                    ❤️ <span>0</span>
                </button>

                <button class="botao-curtir">
                    👍 <span>0</span>
                </button>
            </div>
        </article>


        <article>
            <img src="imagem-agrinho.png"
                alt="Cidade sustentável com áreas verdes e tecnologias">

            <div>
                <h2>Uma cidade mais sustentável</h2>

                <p class="artigo-autor">Por: Rafaela Andrade</p>

                <p>
                    Nas cidades, pequenas atitudes podem contribuir para a
                    sustentabilidade. A separação do lixo, a reciclagem,
                    a economia de água e energia e o uso consciente dos
                    recursos são exemplos importantes.
                </p>

                <p>
                    A tecnologia também pode ajudar na criação de cidades
                    mais inteligentes, organizadas e sustentáveis.
                </p>

                <button class="botao-curtir">
                    ❤️ <span>0</span>
                </button>

                <button class="botao-curtir">
                    👍 <span>0</span>
                </button>
            </div>
        </article>


        <article>
            <img src="imagem-agrinho.png"
                alt="Representação da união entre agricultura, tecnologia e sustentabilidade">

            <div>
                <h2>Tecnologia e sustentabilidade</h2>

                <p class="artigo-autor">Por: Rafaela Andrade</p>

                <p>
                    A tecnologia pode contribuir tanto no campo quanto na cidade.
                    No campo, ela pode auxiliar no monitoramento das plantações,
                    na economia de água e no aumento da eficiência da produção.
                </p>

                <p>
                    Quando utilizada de maneira consciente, a tecnologia pode
                    ajudar a diminuir desperdícios e preservar os recursos
                    naturais.
                </p>

                <button class="botao-curtir">
                    ❤️ <span>0</span>
                </button>

                <button class="botao-curtir">
                    👍 <span>0</span>
                </button>
            </div>
        </article>

    </main>

    <script src="script.js"></script>

</body>
</html>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #eef5e8;
    color: #263b28;
}

header {
    background-color: #2e6b3e;
    color: #ffffff;
    text-align: center;
    padding: 35px 20px;
}

header h1 {
    font-size: 36px;
    margin-bottom: 10px;
}

header p {
    font-size: 18px;
}

main {
    max-width: 1000px;
    margin: 30px auto;
    padding: 0 20px;
}

article {
    display: flex;
    gap: 25px;
    background-color: #ffffff;
    padding: 25px;
    margin-bottom: 25px;
    border-radius: 15px;
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.10);
}

article img {
    width: 180px;
    height: 180px;
    object-fit: cover;
    border-radius: 12px;
}

article div {
    flex: 1;
}

article h2 {
    color: #2e6b3e;
    margin-bottom: 8px;
}

article p {
    line-height: 1.6;
    margin-bottom: 12px;
}

.artigo-autor {
    font-weight: bold;
    color: #56745a;
}

button {
    border: none;
    background-color: #e5f0df;
    padding: 8px 14px;
    border-radius: 20px;
    cursor: pointer;
    font-size: 16px;
    margin-right: 8px;
}

button:hover {
    background-color: #cfe3c8;
}

@media (max-width: 700px) {

    article {
        flex-direction: column;
    }

    article img {
        width: 100%;
        height: 200px;
    }

    header h1 {
        font-size: 28px;
    }
}


const botoes = document.querySelectorAll(".botao-curtir");

botoes.forEach(function(botao) {

    let curtiu = false;

    botao.addEventListener("click", function() {

        let texto = botao.querySelector("span");

        if (curtiu === false) {
            texto.textContent++;
            curtiu = true;
        } else {
            texto.textContent--;
            curtiu = false;
        }

    });

});
