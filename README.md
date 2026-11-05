<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Loja Criativa – Seu Produto Favorito</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- Link do CSS -->
    <link rel="stylesheet" href="style.css">
    <!-- Ícone da aba -->
    <link rel="icon" href="https://img.icons8.com/color/48/000000/shopping-cart.png">
</head>
<body>

    <!-- Cabeçalho -->
    <header>
        <div class="logo">
            <img src="https://img.icons8.com/color/48/000000/online-store.png" alt="Logo">
            <h1>Loja Criativa</h1>
        </div>
        <nav>
            <a href="#produtos">Produtos</a>
            <a href="#sobre">Sobre</a>
            <a href="#contato">Contato</a>
            <a href="#" class="carrinho" onclick="abrirCarrinho()">🛒 <span id="qtde-itens">0</span></a>
        </nav>
    </header>

    <!-- Banner principal -->
    <section class="hero">
        <h2>Descubra o que há de melhor para você!</h2>
        <p>Produtos exclusivos, preços imbatíveis e entrega rápida.</p>
        <button onclick="rolarPara('#produtos')">Ver Produtos</button>
    </section>

    <!-- Lista de produtos -->
    <section id="produtos" class="produtos">
        <h2>Nossos Produtos</h2>
        <div class="grid">
            <!-- Cada .produto pode ser duplicado/gerado dinamicamente -->
            <div class="produto" data-id="1" data-nome="Caneca Arte" data-preco="29.90">
                <img src="https://images.unsplash.com/photo-1606813907362-7e5b3d3a7c19?auto=format&fit=crop&w=400&q=80" alt="Caneca Arte">
                <h3>Caneca Arte</h3>
                <p class="preco">R$ 29,90</p>
                <button class="add" onclick="adicionarAoCarrinho(this)">Adicionar ao carrinho</button>
            </div>

            <div class="produto" data-id="2" data-nome="Camiseta Retro" data-preco="79.90">
                <img src="https://images.unsplash.com/photo-1520975911458-2c2c7f0e5b74?auto=format&fit=crop&w=400&q=80" alt="Camiseta Retro">
                <h3>Camiseta Retro</h3>
                <p class="preco">R$ 79,90</p>
                <button class="add" onclick="adicionarAoCarrinho(this)">Adicionar ao carrinho</button>
            </div>

            <div class="produto" data-id="3" data-nome="Fone Bluetooth" data-preco="149.90">
                <img src="https://images.unsplash.com/photo-1580910051070-2f9b3a5c4f2a?auto=format&fit=crop&w=400&q=80" alt="Fone Bluetooth">
                <h3>Fone Bluetooth</h3>
                <p class="preco">R$ 149,90</p>
                <button class="add" onclick="adicionarAoCarrinho(this)">Adicionar ao carrinho</button>
            </div>

            <!-- Adicione quantos produtos quiser seguindo o mesmo padrão -->
        </div>
    </section>

    <!-- Sobre a loja -->
    <section id="sobre" class="sobre">
        <h2>Sobre a Loja Criativa</h2>
        <p>Somos uma equipe apaixonada por design e tecnologia. Cada item que oferecemos foi escolhido a dedo para trazer praticidade e estilo ao seu dia a dia.</p>
        <img src="https://images.unsplash.com/photo-1503387762-592deff5e3b2?auto=format&fit=crop&w=800&q=80" alt="Sobre nós">
    </section>

    <!-- Contato -->
    <section id="contato" class="contato">
        <h2>Fale Conosco</h2>
        <form onsubmit="enviarContato(event)">
            <input type="text" placeholder="Seu nome" required>
            <input type="email" placeholder="E‑mail" required>
            <textarea placeholder="Sua mensagem..." rows="4" required></textarea>
            <button type="submit">Enviar</button>
        </form>
    </section>

    <!-- Modal do carrinho -->
    <div id="modal-carrinho" class="modal">
        <div class="modal-conteudo">
            <span class="fechar" onclick="fecharCarrinho()">×</span>
            <h3>Seu Carrinho</h3>
            <ul id="lista-carrinho"></ul>
            <p class="total">Total: <strong>R$ <span id="valor-total">0,00</span></strong></p>
            <button class="checkout" onclick="finalizarCompra()">Finalizar Compra</button>
        </div>
    </div>

    <!-- Rodapé -->
    <footer>
        <p>© 2026 Loja Criativa – Todos os direitos reservados.</p>
        <div class="social">
            <a href="#" target="_blank">🌐</a>
            <a href="#" target="_blank">📘</a>
            <a href="#" target="_blank">📸</a>
        </div>
    </footer>

    <!-- Script -->
    <script src="script.js"></script>
</body>
</html>

      

    

---

## 2️⃣ style.css  

      

        
css
📋 Copiar

        
/* Reset simples */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Tipografia e cores base */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333;
    background: #f7f9fc;
}

/* ---------- HEADER ---------- */
header {
    background: #2c3e50;
    color: #fff;
    padding: 15px 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
}
header .logo {
    display: flex;
    align-items: center;
}
header .logo img {
    width: 40px;
    margin-right: 10px;
}
header nav a {
    color: #fff;
    margin-left: 20px;
    text-decoration: none;
    font-weight: 500;
}
header nav a.carrinho {
    background: #e67e22;
    padding: 5px 10px;
    border-radius: 5px;
}

/* ---------- HERO ---------- */
.hero {
    background: linear-gradient(rgba(44,62,80,0.85), rgba(44,62,80,0.85)), url('https://images.unsplash.com/photo-1508051123996-69f8caf4891c?auto=format&fit=crop&w=1200&q=80');
    background-size: cover;
    background-position: center;
    color: #fff;
    text-align: center;
    padding: 120px 20px;
}
.hero h2 {
    font-size: 2.5rem;
    margin-bottom: 15px;
}
.hero p {
    font-size: 1.2rem;
    margin-bottom: 30px;
}
.hero button {
    background: #e67e22;
    border: none;
    color: #fff;
    padding: 12px 30px;
    font-size: 1rem;
    cursor: pointer;
    border-radius: 5px;
}

/* ---------- PRODUTOS ---------- */
.produtos {
    padding: 60px 20px;
    text-align: center;
}
.produtos h2 {
    margin-bottom: 40px;
    font-size: 2rem;
}
.produtos .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 30px;
}
.produto {
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0,0,0,.07);
    padding: 20px;
    transition: transform .2s;
}
.produto:hover {
    transform: translateY(-5px);
}
.produto img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    border-radius: 8px;
    margin-bottom: 15px;
}
.produto h3 {
    margin: 10px 0;
    font-size: 1.2rem;
}
.produto .preco {
    color: #e67e22;
    font-weight: bold;
    margin-bottom: 15px;
}
.produto button.add {
    background: #2c3e50;
    color: #fff;
    border: none;
    padding: 8px 15px;
    cursor: pointer;
    border-radius: 4px;
}

/* ---------- SOBRE ---------- */
.sobre {
    background: #ecf0f1;
    padding: 60px 20px;
    text-align: center;
}
.sobre h2 {
    margin-bottom: 30px;
}
.sobre p {
    max-width: 700px;
    margin: 0 auto 30px;
}
.sobre img {
    width: 100%;
    max-width: 800px;
    border-radius: 10px;
}

/* ---------- CONTATO ---------- */
.contato {
    padding: 60px 20px;
    text-align: center;
}
.contato h2 {
    margin-bottom: 30px;
}
.contato form {
    max-width: 500px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
}
.contato input,
.contato textarea {
    padding: 12px;
    margin-bottom: 15px;
    border: 1px solid #bdc3c7;
    border-radius: 4px;
}
.contato button {
    background: #e67e22;
    color: #fff;
    border: none;
    padding: 12px;
    cursor: pointer;
    border-radius: 4px;
}

/* ---------- MODAL CARRINHO ---------- */
.modal {
    display: none; /* será exibido via JS */
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,.5);
    justify-content: center;
    align-items: center;
    z-index: 1000;
}
.modal-conteudo {
    background: #fff;
    padding: 30px;
    border-radius: 10px;
    width: 90%;
    max-width: 500px;
    position: relative;
}
.modal-conteudo .fechar {
    position: absolute;
    top: 10px;
    right: 15px;
    font-size: 1.5rem;
    cursor: pointer;
}
.modal-conteudo ul {
    list-style: none;
    margin-bottom: 20px;
}
.modal-conteudo li {
    display: flex;
    justify-content: space-between;
    margin-bottom: 8px;
}
.modal-conteudo .total {
    font-size: 1.2rem;
    margin-bottom: 20px;
}
.modal-conteudo .checkout {
    background: #27ae60;
    color: #fff;
    border: none;
    width: 100%;
    padding: 12px;
    cursor: pointer;
    border-radius: 5px;
}

/* ---------- FOOTER ---------- */
footer {
    background: #2c3e50;
    color: #fff;
    text-align: center;
    padding: 20px;
}
footer .social a {
    color: #fff;
    margin: 0 8px;
    font-size: 1.3rem;
    text-decoration: none;
}

/* ---------- RESPONSIVO ---------- */
@media (max-width: 600px) {
    header nav a {
        margin-left: 10px;
        font-size: 0.9rem;
    }
    .hero h2 {
        font-size: 2rem;
    }
}
