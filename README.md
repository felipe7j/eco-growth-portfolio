<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Eco Growth | Agência de Marketing Sustentável</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&family=Poppins:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 (gratuito) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- AOS animação simples (opcional, mas elegante) -->
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: #F9FBF9;
            color: #1A2E1A;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        h1, h2, h3, h4, .logo {
            font-family: 'Poppins', sans-serif;
        }

        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* Glassmorphism e cards */
        .card, .pacote-card, .servico-card, .depoimento-card {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(2px);
            border-radius: 28px;
            padding: 24px;
            transition: all 0.3s ease;
            border: 1px solid rgba(76, 175, 80, 0.2);
            box-shadow: 0 8px 20px rgba(0,0,0,0.02);
        }

        .card:hover, .pacote-card:hover, .servico-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 30px -12px rgba(46, 125, 50, 0.2);
            border-color: #4CAF50;
        }

        /* Botões */
        .btn-primary {
            background: linear-gradient(135deg, #2E7D32 0%, #4CAF50 100%);
            color: white;
            border: none;
            padding: 12px 28px;
            border-radius: 40px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
            display: inline-block;
            text-decoration: none;
            font-size: 1rem;
        }

        .btn-primary:hover {
            transform: scale(1.02);
            background: linear-gradient(135deg, #1B5E20 0%, #2E7D32 100%);
            box-shadow: 0 8px 18px rgba(46,125,50,0.3);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid #4CAF50;
            color: #2E7D32;
            padding: 10px 24px;
            border-radius: 40px;
            font-weight: 600;
            transition: 0.2s;
        }

        /* Header */
        header {
            background: rgba(255,255,240,0.96);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid #e0f0e0;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 16px 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            color: #1B5E20;
        }

        .logo span {
            color: #4CAF50;
        }

        .nav-links {
            display: flex;
            gap: 32px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: #1A2E1A;
            font-weight: 500;
            transition: color 0.2s;
        }

        .nav-links a:hover {
            color: #2E7D32;
        }

        .menu-hamburger {
            display: none;
            font-size: 1.8rem;
            cursor: pointer;
        }

        /* Hero */
        .hero {
            padding: 80px 0;
            background: linear-gradient(135deg, #E8F5E9 0%, #FFFFFF 100%);
        }

        .hero-grid {
            display: flex;
            align-items: center;
            gap: 48px;
            flex-wrap: wrap;
        }

        .hero-content {
            flex: 1;
        }

        .hero-content h1 {
            font-size: 3.2rem;
            line-height: 1.2;
            margin-bottom: 20px;
        }

        .hero-image {
            flex: 1;
            text-align: center;
        }

        /* Serviços grid */
        .servicos-grid, .pacotes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 28px;
            margin: 40px 0;
        }

        .preco {
            font-size: 1.8rem;
            font-weight: 700;
            color: #2E7D32;
            margin: 12px 0;
        }

        .badge {
            background: #4CAF50;
            color: white;
            padding: 4px 12px;
            border-radius: 30px;
            font-size: 0.75rem;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 12px;
        }

        /* Rodapé */
        footer {
            background: #0A2F0A;
            color: #ccc;
            padding: 48px 0 24px;
            margin-top: 60px;
        }

        /* Botão flutuante WhatsApp */
        .whatsapp-float {
            position: fixed;
            bottom: 24px;
            right: 24px;
            background: #25D366;
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
            transition: 0.2s;
            z-index: 99;
        }

        .whatsapp-float:hover {
            transform: scale(1.05);
            background: #128C7E;
        }

        /* Responsivo */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                flex-direction: column;
                background: white;
                position: absolute;
                top: 70px;
                left: 0;
                width: 100%;
                padding: 24px;
                box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            }
            .nav-links.active {
                display: flex;
            }
            .menu-hamburger {
                display: block;
            }
            .hero-content h1 {
                font-size: 2.2rem;
            }
        }

        input, textarea, select {
            width: 100%;
            padding: 12px;
            border-radius: 16px;
            border: 1px solid #ddd;
            margin-bottom: 16px;
            font-family: 'Inter', sans-serif;
        }

        form button {
            width: 100%;
        }
    </style>
</head>
<body>

<header>
    <div class="container">
        <div class="navbar">
            <div class="logo">Eco<span>Growth</span></div>
            <div class="menu-hamburger" id="menuToggle">
                <i class="fas fa-bars"></i>
            </div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">Início</a></li>
                <li><a href="#servicos">Serviços</a></li>
                <li><a href="#pacotes">Pacotes</a></li>
                <li><a href="#portfolio">Portfólio</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </div>
    </div>
</header>

<main>
    <!-- Hero -->
    <section id="home" class="hero">
        <div class="container hero-grid">
            <div class="hero-content" data-aos="fade-right">
                <h1>Sua marca cresce com a gente, <span style="color:#2E7D32;">de forma sustentável</span></h1>
                <p style="font-size: 1.2rem; margin: 24px 0;">Estratégia, identidade e gestão digital para negócios que querem resultados reais sem promessas vazias.</p>
                <a href="#contato" class="btn-primary">Falar com especialista →</a>
            </div>
            <div class="hero-image" data-aos="fade-left">
                <img src="https://placehold.co/500x400/2E7D32/white?text=🌿+Crescimento+Sustentável" alt="Eco Growth" style="max-width:100%; border-radius: 48px;">
            </div>
        </div>
    </section>

    <!-- Serviços -->
    <section id="servicos" class="container" style="margin: 60px auto;">
        <h2 style="font-size: 2.2rem; text-align:center;" data-aos="fade-up">Nossos serviços <span style="color:#2E7D32;">🌱</span></h2>
        <div class="servicos-grid">
            <!-- Cada card de serviço conforme planilha -->
            <div class="servico-card" data-aos="zoom-in"><i class="fas fa-pen-nib" style="font-size: 32px; color:#4CAF50;"></i><h3>Criação de logotipo</h3><p>3 variações + manual da marca</p><div class="preco">R$56</div></div>
            <div class="servico-card" data-aos="zoom-in"><i class="fas fa-laptop-code" style="font-size: 32px; color:#4CAF50;"></i><h3>Site Institucional</h3><p>5 páginas, responsivo + SEO básico</p><div class="preco">R$883</div></div>
            <div class="servico-card" data-aos="zoom-in"><i class="fab fa-instagram" style="font-size: 32px; color:#4CAF50;"></i><h3>Gerenciamento de redes</h3><p>12 posts + 4 reels/mês</p><div class="preco">R$650</div></div>
            <div class="servico-card" data-aos="zoom-in"><i class="fas fa-palette" style="font-size: 32px; color:#4CAF50;"></i><h3>Identidade visual completa</h3><p>Cartão, papelaria, capa social</p><div class="preco">R$900</div></div>
            <div class="servico-card" data-aos="zoom-in"><i class="fas fa-chart-line" style="font-size: 32px; color:#4CAF50;"></i><h3>Tráfego pago básico</h3><p>R$400 + verba (Google/Meta Ads)</p><div class="preco">R$400 + verba</div></div>
            <div class="servico-card" data-aos="zoom-in"><i class="fas fa-graduation-cap" style="font-size: 32px; color:#4CAF50;"></i><h3>Curso Digital</h3><p>eBook/vídeo + design + hospedagem</p><div class="preco">R$633</div></div>
            <div class="servico-card" data-aos="zoom-in"><i class="fas fa-calendar-alt" style="font-size: 32px; color:#4CAF50;"></i><h3>Gestão mensal Social Media</h3><p>8 a 12 posts/mês</p><div class="preco">R$159</div></div>
            <div class="servico-card" data-aos="zoom-in"><i class="fab fa-google" style="font-size: 32px; color:#4CAF50;"></i><h3>Google + SEO local</h3><p>Google Meu Negócio completo</p><div class="preco">R$97</div></div>
            <div class="servico-card" data-aos="zoom-in"><i class="fas fa-rocket" style="font-size: 32px; color:#4CAF50;"></i><h3>Tráfego pago (básico)</h3><p>Gestão de campanhas</p><div class="preco">R$237</div></div>
        </div>
    </section>

    <!-- Pacotes -->
    <section id="pacotes" class="container" style="margin: 60px auto;">
        <h2 style="font-size: 2.2rem; text-align:center;" data-aos="fade-up">Pacotes estratégicos <span style="color:#2E7D32;">⚡</span></h2>
        <div class="pacotes-grid">
            <div class="pacote-card" data-aos="flip-left"><span class="badge">Entrada</span><h3>🟢 PACOTE START</h3><p>Google Meu Negócio + Instagram básico</p><div class="preco">R$237</div><button class="btn-outline" style="margin-top:12px;">Quero esse</button></div>
            <div class="pacote-card" data-aos="flip-left"><span class="badge">🔥 MAIS VENDIDO</span><h3>🔵 PACOTE PRESENÇA DIGITAL</h3><p>Google Meu Negócio + Site profissional + WhatsApp integrado</p><div class="preco">R$380</div><button class="btn-primary" style="margin-top:12px;">Assinar agora</button></div>
            <div class="pacote-card" data-aos="flip-left"><span class="badge">Premium</span><h3>🟣 PACOTE CRESCIMENTO</h3><p>Tudo acima + Google/Meta Ads + Estratégia de conteúdo</p><div class="preco">R$517</div><button class="btn-outline" style="margin-top:12px;">Quero crescer</button></div>
        </div>
    </section>

    <!-- Diferenciais -->
    <section class="container" style="margin: 60px auto;">
        <div style="display: flex; flex-wrap: wrap; gap: 32px; justify-content: center;">
            <div class="card" style="text-align:center; flex:1;"><i class="fas fa-headset" style="font-size: 42px; color:#2E7D32;"></i><h3>Atendimento humanizado</h3><p>Você fala com quem resolve</p></div>
            <div class="card" style="text-align:center; flex:1;"><i class="fas fa-seedling" style="font-size: 42px; color:#2E7D32;"></i><h3>Crescimento real</h3><p>Sem promessas vazias, só estratégia sustentável</p></div>
            <div class="card" style="text-align:center; flex:1;"><i class="fas fa-stopwatch" style="font-size: 42px; color:#2E7D32;"></i><h3>Entrega rápida</h3><p>Identidade visual em até 15 dias</p></div>
        </div>
    </section>

    <!-- Portfólio fictício -->
    <section id="portfolio" class="container" style="margin: 60px auto;">
        <h2 style="font-size: 2.2rem; text-align:center;">Cases que inspiram <span style="color:#2E7D32;">✨</span></h2>
        <div class="servicos-grid">
            <div class="card"><img src="https://placehold.co/400x200/CFEBD0/1B5E20?text=Logotipo+Eco" style="width:100%; border-radius: 20px;"><h3>Clínica Viver Bem</h3><p>Identidade visual + site responsivo</p></div>
            <div class="card"><img src="https://placehold.co/400x200/CFEBD0/1B5E20?text=Site+Institucional" style="width:100%; border-radius: 20px;"><h3>Eco Ótica</h3><p>E-commerce + integração WhatsApp</p></div>
            <div class="card"><img src="https://placehold.co/400x200/CFEBD0/1B5E20?text=Gestão+de+Redes" style="width:100%; border-radius: 20px;"><h3>Studio Pilates Flow</h3><p>+47% engajamento em 2 meses</p></div>
        </div>
    </section>

    <!-- Contato -->
    <section id="contato" class="container" style="margin: 60px auto;">
        <div class="card" data-aos="fade-up">
            <h2>Vamos plantar sua presença digital?</h2>
            <p>Preencha o formulário e em até 2h um especialista responde.</p>
            <form id="formContato">
                <input type="text" placeholder="Seu nome" required>
                <input type="email" placeholder="E-mail" required>
                <input type="tel" placeholder="WhatsApp">
                <textarea rows="4" placeholder="Conte sobre seu negócio..."></textarea>
                <button type="submit" class="btn-primary">Enviar mensagem 🌿</button>
            </form>
        </div>
    </section>
</main>

<footer>
    <div class="container">
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 32px;">
            <div><h3>EcoGrowth</h3><p>Marketing sustentável que gera resultado de verdade.</p></div>
            <div><h4>Links</h4><a href="#" style="color:#ccc; display:block;">Serviços</a><a href="#" style="color:#ccc;">Política de privacidade</a></div>
            <div><h4>Contato</h4><p><i class="fab fa-whatsapp"></i> (11) 99999-9999</p><p>contato@ecogrowth.com</p></div>
        </div>
        <hr style="margin: 32px 0; border-color:#2E4A2E;">
        <p style="text-align:center;">© <span id="ano"></span> Eco Growth - Agência que faz seu negócio florescer.</p>
    </div>
</footer>

<a href="https://wa.me/5511999999999" class="whatsapp-float" target="_blank"><i class="fab fa-whatsapp"></i></a>

<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
<script>
    AOS.init({ duration: 800, once: true });
    // Menu hamburguer
    const menuToggle = document.getElementById('menuToggle');
    const navLinks = document.getElementById('navLinks');
    menuToggle.addEventListener('click', () => navLinks.classList.toggle('active'));
    // Ano atual no rodapé
    document.getElementById('ano').innerText = new Date().getFullYear();
    // Simular envio formulário
    document.getElementById('formContato').addEventListener('submit', function(e) {
        e.preventDefault();
        alert('🌿 Mensagem enviada! Em breve nossa equipe Eco Growth retorna.');
        this.reset();
    });
</script>
</body>
</html>
