<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nosso Amor em Cada Página</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --rosa-claro: #ffd9e3;
            --rosa: #ff85a2;
            --vermelho-queimado: #d46a6a;
            --bege: #f7e9d4;
            --dourado: #e6c35c;
            --fonte-principal: 'Montserrat', sans-serif;
            --fonte-cursiva: 'Dancing Script', cursive;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--fonte-principal);
            background-color: var(--rosa-claro);
            color: #5a3e36;
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* Efeito de chuva de corações */
        .heart-rain {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background: var(--rosa);
            opacity: 0.7;
            pointer-events: none;
            animation: fall 8s linear infinite;
        }

        .heart:before, .heart:after {
            content: '';
            width: 20px;
            height: 20px;
            background: var(--rosa);
            border-radius: 50%;
            position: absolute;
        }

        .heart:before {
            top: -10px;
            left: 0;
        }

        .heart:after {
            top: 0;
            left: -10px;
        }

        @keyframes fall {
            0% {
                transform: translateY(-10vh) rotate(0deg);
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
            }
        }

        /* Seções gerais */
        section {
            padding: 80px 20px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            width: 100%;
        }

        h1, h2 {
            font-family: var(--fonte-cursiva);
            text-align: center;
            margin-bottom: 30px;
            color: var(--vermelho-queimado);
        }

        h1 {
            font-size: 3.5rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        h2 {
            font-size: 2.5rem;
        }

        p {
            margin-bottom: 20px;
            font-size: 1.1rem;
        }

        /* Cabeçalho */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 0;
            z-index: 1000;
            transition: background 0.3s ease;
        }

        header.scrolled {
            background: rgba(255, 255, 255, 0.9);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
        }

        nav ul li {
            margin: 0 15px;
        }

        nav ul li a {
            color: var(--vermelho-queimado);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            padding: 8px 15px;
            border-radius: 20px;
            transition: all 0.3s ease;
        }

        nav ul li a:hover {
            background: var(--rosa);
            color: white;
        }

        /* Hero Section */
        #hero {
            background: linear-gradient(135deg, var(--bege) 0%, var(--rosa-claro) 100%);
            text-align: center;
            padding-top: 120px;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .hero-title {
            font-size: 4rem;
            margin-bottom: 20px;
            animation: fadeInDown 1s ease;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 30px;
            color: var(--vermelho-queimado);
            animation: fadeInUp 1s ease 0.3s forwards;
            opacity: 0;
        }

        .countdown-container {
            background: rgba(255, 255, 255, 0.8);
            border-radius: 15px;
            padding: 20px;
            max-width: 500px;
            margin: 0 auto 40px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            animation: fadeInUp 1s ease 0.6s forwards;
            opacity: 0;
        }

        .countdown-title {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--dourado);
        }

        .countdown {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        .countdown-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            min-width: 70px;
        }

        .countdown-number {
            font-size: 2rem;
            font-weight: 700;
            color: var(--vermelho-queimado);
        }

        .countdown-label {
            font-size: 0.9rem;
            color: var(--dourado);
            text-transform: uppercase;
        }

        .btn {
            display: inline-block;
            background: var(--vermelho-queimado);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            margin-top: 20px;
            transition: all 0.3s ease;
            border: 2px solid var(--vermelho-queimado);
            animation: fadeIn 1s ease 0.9s forwards;
            opacity: 0;
        }

        .btn:hover {
            background: transparent;
            color: var(--vermelho-queimado);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        /* Timeline */
        #timeline {
            background: linear-gradient(to bottom, var(--rosa-claro) 0%, #ffebf3 100%);
        }

        .timeline-container {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline-container::after {
            content: '';
            position: absolute;
            width: 4px;
            background: var(--dourado);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
        }

        .timeline-item {
            padding: 20px 40px;
            position: relative;
            width: 50%;
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.5s ease;
        }

        .timeline-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .timeline-item:nth-child(odd) {
            left: 0;
        }

        .timeline-item:nth-child(even) {
            left: 50%;
        }

        .timeline-content {
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            position: relative;
        }

        .timeline-content::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background: white;
            top: 30px;
            z-index: -1;
            transform: rotate(45deg);
        }

        .timeline-item:nth-child(odd) .timeline-content::after {
            right: -10px;
        }

        .timeline-item:nth-child(even) .timeline-content::after {
            left: -10px;
        }

        .timeline-date {
            font-weight: 600;
            color: var(--dourado);
            margin-bottom: 10px;
        }

        .timeline-title {
            font-family: var(--fonte-cursiva);
            color: var(--vermelho-queimado);
            margin-bottom: 10px;
            font-size: 1.8rem;
        }

        .timeline-circle {
            position: absolute;
            width: 25px;
            height: 25px;
            background: var(--dourado);
            border: 4px solid white;
            border-radius: 50%;
            top: 30px;
            z-index: 1;
        }

        .timeline-item:nth-child(odd) .timeline-circle {
            right: -12px;
        }

        .timeline-item:nth-child(even) .timeline-circle {
            left: -13px;
        }

        /* Galeria */
        #gallery {
            background: var(--bege);
        }

        .gallery-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .gallery-item {
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            height: 250px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.5s ease;
        }

        .gallery-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background: rgba(0, 0, 0, 0.6);
            color: white;
            padding: 10px;
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }

        .gallery-item:hover .gallery-caption {
            transform: translateY(0);
        }

        /* Carta */
        #letter {
            background: linear-gradient(to bottom, #ffebf3 0%, var(--rosa-claro) 100%);
            text-align: center;
        }

        .letter-container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }

        .letter-container::before {
            content: '';
            position: absolute;
            top: -50px;
            right: -50px;
            width: 200px;
            height: 200px;
            background: var(--rosa);
            border-radius: 50%;
            opacity: 0.1;
        }

        .letter-container::after {
            content: '';
            position: absolute;
            bottom: -30px;
            left: -30px;
            width: 150px;
            height: 150px;
            background: var(--dourado);
            border-radius: 50%;
            opacity: 0.1;
        }

        .letter-content {
            position: relative;
            z-index: 2;
            text-align: left;
        }

        .letter-title {
            font-family: var(--fonte-cursiva);
            color: var(--vermelho-queimado);
            margin-bottom: 20px;
            text-align: center;
        }

        .typed-text {
            min-height: 200px;
            font-size: 1.2rem;
            line-height: 1.8;
        }

        .cursor {
            display: inline-block;
            width: 3px;
            background: var(--dourado);
            margin-left: 2px;
            animation: blink 1s infinite;
        }

        /* Playlist */
        #playlist {
            background: var(--bege);
        }

        .playlist-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .spotify-embed {
            width: 100%;
            max-width: 600px;
            height: 380px;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            margin: 30px 0;
        }

        /* Vídeo */
        #video {
            background: linear-gradient(to bottom, var(--rosa-claro) 0%, #ffebf3 100%);
        }

        .video-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 Aspect Ratio */
            height: 0;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 0;
        }

        /* Surpresa */
        #surprise {
            background: var(--bege);
            text-align: center;
        }

        .surprise-container {
            max-width: 600px;
            margin: 0 auto;
        }

        .surprise-content {
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            margin-bottom: 30px;
        }

        .password-form {
            margin-top: 30px;
        }

        .password-input {
            padding: 12px 20px;
            border: 2px solid var(--rosa);
            border-radius: 30px;
            font-size: 1rem;
            width: 100%;
            max-width: 300px;
            margin-right: 10px;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            padding: 40px;
            border-radius: 15px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            position: relative;
            animation: modalIn 0.5s ease;
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--vermelho-queimado);
        }

        .modal-title {
            font-family: var(--fonte-cursiva);
            color: var(--vermelho-queimado);
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .modal-text {
            font-size: 1.2rem;
            line-height: 1.8;
            margin-bottom: 30px;
        }

        /* Rodapé */
        footer {
            background: var(--vermelho-queimado);
            color: white;
            text-align: center;
            padding: 30px 20px;
        }

        .footer-hearts {
            font-size: 1.5rem;
            letter-spacing: 10px;
            color: var(--dourado);
            margin-bottom: 15px;
        }

        /* Animações */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        @keyframes modalIn {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsividade */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 2rem;
            }
            
            nav ul {
                flex-wrap: wrap;
            }
            
            nav ul li {
                margin: 5px;
            }
            
            .timeline-container::after {
                left: 31px;
            }
            
            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
                left: 0 !important;
            }
            
            .timeline-item:nth-child(even) {
                left: 0;
            }
            
            .timeline-item:nth-child(odd) .timeline-circle,
            .timeline-item:nth-child(even) .timeline-circle {
                left: 20px;
            }
            
            .timeline-item:nth-child(odd) .timeline-content::after,
            .timeline-item:nth-child(even) .timeline-content::after {
                left: -10px;
                right: auto;
            }
            
            .gallery-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
            
            .letter-container {
                padding: 20px;
            }
            
            .typed-text {
                min-height: 300px;
            }
        }

        @media (max-width: 480px) {
            .hero-title {
                font-size: 2.5rem;
            }
            
            .countdown {
                gap: 8px;
            }
            
            .countdown-item {
                min-width: 55px;
            }
            
            .countdown-number {
                font-size: 1.5rem;
            }
            
            .gallery-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Efeito de chuva de corações -->
    <div class="heart-rain" id="heartRain"></div>

    <!-- Menu de navegação -->
    <header id="header">
        <nav>
            <ul>
                <li><a href="#hero">Início</a></li>
                <li><a href="#timeline">Nossa História</a></li>
                <li><a href="#gallery">Momentos</a></li>
                <li><a href="#letter">Carta</a></li>
                <li><a href="#surprise">Surpresa</a></li>
            </ul>
        </nav>
    </header>

    <!-- Seção Hero -->
    <section id="hero">
        <div class="container hero-content">
            <h1 class="hero-title">Nosso Amor em Cada Página</h1>
            <p class="hero-subtitle">Um presente especial para celebrar nosso amor neste Dia dos Namorados</p>
            
            <div class="countdown-container">
                <h3 class="countdown-title">Desde que nos conhecemos</h3>
                <div class="countdown" id="countdown">
                    <div class="countdown-item">
                        <span class="countdown-number" id="years">0</span>
                        <span class="countdown-label">Anos</span>
                    </div>
                    <div class="countdown-item">
                        <span class="countdown-number" id="months">0</span>
                        <span class="countdown-label">Meses</span>
                    </div>
                    <div class="countdown-item">
                        <span class="countdown-number" id="days">0</span>
                        <span class="countdown-label">Dias</span>
                    </div>
                    <div class="countdown-item">
                        <span class="countdown-number" id="hours">0</span>
                        <span class="countdown-label">Horas</span>
                    </div>
                </div>
            </div>
            
            <a href="#timeline" class="btn">Nossa História</a>
        </div>
    </section>

    <!-- Linha do tempo -->
    <section id="timeline">
        <div class="container">
            <h2>Nossa História</h2>
            <div class="timeline-container">
                <div class="timeline-item">
                    <div class="timeline-circle"></div>
                    <div class="timeline-content">
                        <div class="timeline-date">14 de Fevereiro, 2021</div>
                        <h3 class="timeline-title">Primeiro Encontro</h3>
                        <p>Nosso primeiro encontro no Dia dos Namorados, em um café aconchegante. A conversa fluiu tão naturalmente que perdemos a noção do tempo.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-circle"></div>
                    <div class="timeline-content">
                        <div class="timeline-date">15 de Junho, 2021</div>
                        <h3 class="timeline-title">Primeira Viagem</h3>
                        <p>Nossa primeira viagem juntos para as montanhas. Dias incríveis de caminhadas, paisagens deslumbrantes e noites aconchegantes.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-circle"></div>
                    <div class="timeline-content">
                        <div class="timeline-date">24 de Dezembro, 2021</div>
                        <h3 class="timeline-title">Primeiro Natal</h3>
                        <p>Celebrando nosso primeiro Natal juntos com as famílias. Foi mágico compartilhar essa época especial com você ao meu lado.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-circle"></div>
                    <div class="timeline-content">
                        <div class="timeline-date">14 de Fevereiro, 2022</div>
                        <h3 class="timeline-title">Primeiro Ano</h3>
                        <p>Comemorando nosso primeiro ano juntos no mesmo café do nosso primeiro encontro. Cada dia ao seu lado tem sido uma bênção.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Galeria de fotos -->
    <section id="gallery">
        <div class="container">
            <h2>Nossos Momentos</h2>
            <div class="gallery-container">
                <div class="gallery-grid">
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1529254479751-fbacb4c7b087?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Casal na praia">
                        <div class="gallery-caption">Dia na praia</div>
                    </div>
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1511795409834-ef04bbd61622?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Casal na montanha">
                        <div class="gallery-caption">Caminhada nas montanhas</div>
                    </div>
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1519671482749-fd09be7ccebf?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Casal no café">
                        <div class="gallery-caption">Manhã de café</div>
                    </div>
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Casal no pôr do sol">
                        <div class="gallery-caption">Pôr do sol inesquecível</div>
                    </div>
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1534308983496-4fabb1a015ee?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Casal viajando">
                        <div class="gallery-caption">Nossa primeira viagem</div>
                    </div>
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1526662098125-5c0b9d0b9aba?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Casal abraçado">
                        <div class="gallery-caption">Abraços aconchegantes</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Carta de amor -->
    <section id="letter">
        <div class="container">
            <div class="letter-container">
                <h2 class="letter-title">Para você, meu amor</h2>
                <div class="letter-content">
                    <div class="typed-text" id="typedText"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Playlist -->
    <section id="playlist">
        <div class="container">
            <h2>Nossa Trilha Sonora</h2>
            <div class="playlist-container">
                <p>Músicas que marcaram nossa história e que sempre me lembram de você</p>
                <div class="spotify-embed">
                    <iframe src="https://open.spotify.com/embed/playlist/37i9dQZF1DX50QitC6Oqtn?utm_source=generator" frameborder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>
                </div>
            </div>
        </div>
    </section>

    <!-- Vídeo surpresa -->
    <section id="video">
        <div class="container">
            <h2>Nossa Mensagem</h2>
            <div class="video-container">
                <div class="video-wrapper">
                    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </div>
            </div>
        </div>
    </section>

    <!-- Surpresa final -->
    <section id="surprise">
        <div class="container">
            <div class="surprise-container">
                <h2>Surpresa Especial</h2>
                <div class="surprise-content">
                    <p>Para desbloquear sua surpresa final, digite a senha especial que só nós dois conhecemos.</p>
                    <p><small>(Dica: o nome do lugar do nosso primeiro encontro)</small></p>
                    
                    <div class="password-form">
                        <input type="text" class="password-input" id="passwordInput" placeholder="Digite a senha...">
                        <button class="btn" id="unlockBtn">Desbloquear Surpresa</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Modal de surpresa -->
    <div class="modal" id="surpriseModal">
        <div class="modal-content">
            <span class="close-modal" id="closeModal">&times;</span>
            <h2 class="modal-title">Feliz Dia dos Namorados!</h2>
            <div class="modal-text">
                <p>Meu amor, você é a pessoa mais especial da minha vida. Cada momento ao seu lado é um presente que guardo no coração.</p>
                <p>Neste Dia dos Namorados, quero renovar minha promessa de amor e compromisso. Você é minha melhor amiga, minha companheira e meu grande amor.</p>
                <p>Que possamos continuar construindo nossa história juntos, com muito amor, respeito e cumplicidade.</p>
                <p>Te amo hoje, amanhã e para sempre.</p>
            </div>
            <p class="footer-hearts">❤ ❤ ❤</p>
        </div>
    </div>

    <!-- Rodapé -->
    <footer>
        <div class="footer-hearts">❤ ❤ ❤</div>
        <p>Feito com amor para você, meu grande amor. Feliz Dia dos Namorados!</p>
        <p>© 2023 - Nosso Amor</p>
    </footer>

    <script>
        // Data do primeiro encontro (14 de fevereiro de 2021)
        const firstDate = new Date('2021-02-14');
        
        // Criar corações para o efeito de chuva
        function createHearts() {
            const heartRain = document.getElementById('heartRain');
            const numHearts = 30;
            
            for (let i = 0; i < numHearts; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                
                // Posição e tamanho aleatórios
                const size = Math.random() * 15 + 10;
                heart.style.width = `${size}px`;
                heart.style.height = `${size}px`;
                heart.style.left = `${Math.random() * 100}%`;
                heart.style.animationDuration = `${Math.random() * 5 + 5}s`;
                heart.style.animationDelay = `${Math.random() * 5}s`;
                
                heartRain.appendChild(heart);
            }
        }
        
        // Atualizar contador de tempo juntos
        function updateCountdown() {
            const now = new Date();
            const diff = now - firstDate;
            
            // Calcular anos, meses, dias e horas
            const years = Math.floor(diff / (1000 * 60 * 60 * 24 * 365));
            const months = Math.floor((diff % (1000 * 60 * 60 * 24 * 365)) / (1000 * 60 * 60 * 24 * 30));
            const days = Math.floor((diff % (1000 * 60 * 60 * 24 * 30)) / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            
            // Atualizar elementos
            document.getElementById('years').textContent = years;
            document.getElementById('months').textContent = months;
            document.getElementById('days').textContent = days;
            document.getElementById('hours').textContent = hours;
        }
        
        // Efeito de digitação na carta
        function typeLetter() {
            const text = `Meu amor,\n\nDesde o momento em que nossos caminhos se cruzaram, minha vida ganhou novas cores, novos significados e uma felicidade que eu nem sabia ser possível. Cada dia ao seu lado é um presente que agradeço ao universo.\n\nVocê é minha melhor amiga, minha confidente, minha parceira de aventuras e meu porto seguro. Seu sorriso ilumina meus dias mais cinzentos e seu abraço é meu lugar favorito no mundo.\n\nNeste Dia dos Namorados, quero renovar minha promessa de amor e compromisso. Prometo estar ao seu lado nos bons e maus momentos, celebrar suas conquistas, apoiar seus sonhos e amá-la mais a cada dia.\n\nObrigado por ser quem você é e por me permitir fazer parte da sua vida. Te amo mais do que as palavras podem expressar.\n\nPara sempre seu,\n[Seu Nome]`;
            const typedText = document.getElementById('typedText');
            let i = 0;
            let isNewLine = false;
            
            function type() {
                if (i < text.length) {
                    // Verificar se é uma quebra de linha
                    if (text.charAt(i) === '\n') {
                        typedText.innerHTML += '<br>';
                        isNewLine = true;
                    } else {
                        if (isNewLine) {
                            typedText.innerHTML += text.charAt(i);
                            isNewLine = false;
                        } else {
                            typedText.innerHTML += text.charAt(i);
                        }
                    }
                    i++;
                    
                    // Manter o cursor no final
                    typedText.innerHTML = typedText.innerHTML.replace('<span class="cursor"></span>', '');
                    typedText.innerHTML += '<span class="cursor"></span>';
                    
                    // Rolagem automática para o final
                    typedText.scrollTop = typedText.scrollHeight;
                    
                    // Velocidade de digitação
                    let speed = 50;
                    if (text.charAt(i) === '\n' || text.charAt(i) === ' ') {
                        speed = 0;
                    }
                    setTimeout(type, speed);
                } else {
                    // Remover o cursor quando terminar
                    typedText.innerHTML = typedText.innerHTML.replace('<span class="cursor"></span>', '');
                }
            }
            
            type();
        }
        
        // Verificar quando elementos entram na viewport para animação
        function animateOnScroll() {
            const timelineItems = document.querySelectorAll('.timeline-item');
            const galleryItems = document.querySelectorAll('.gallery-item');
            
            timelineItems.forEach(item => {
                const itemTop = item.getBoundingClientRect().top;
                if (itemTop < window.innerHeight - 100) {
                    item.classList.add('visible');
                }
            });
            
            galleryItems.forEach(item => {
                const itemTop = item.getBoundingClientRect().top;
                if (itemTop < window.innerHeight - 100) {
                    item.classList.add('visible');
                }
            });
        }
        
        // Desbloquear surpresa
        function unlockSurprise() {
            const password = document.getElementById('passwordInput').value.toLowerCase();
            if (password === 'café' || password === 'cafe') {
                document.getElementById('surpriseModal').style.display = 'flex';
            } else {
                alert('Senha incorreta! Tente novamente. Dica: o nome do lugar do nosso primeiro encontro.');
            }
        }
        
        // Fechar modal
        function closeModal() {
            document.getElementById('surpriseModal').style.display = 'none';
        }
        
        // Mudar estilo do header ao rolar
        function handleScroll() {
            const header = document.getElementById('header');
            if (window.scrollY > 100) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
            
            animateOnScroll();
        }
        
        // Event Listeners
        document.getElementById('unlockBtn').addEventListener('click', unlockSurprise);
        document.getElementById('closeModal').addEventListener('click', closeModal);
        window.addEventListener('scroll', handleScroll);
        
        // Inicialização
        document.addEventListener('DOMContentLoaded', function() {
            createHearts();
            updateCountdown();
            setInterval(updateCountdown, 3600000); // Atualizar a cada hora
            typeLetter();
            animateOnScroll();
            
            // Suavizar rolagem para links internos
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });
        });
    </script>
</body>
</html>
