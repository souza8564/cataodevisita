<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DANIELSONSMA - Automação Industrial</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --vermelho: #ff3333;
            --preto: #000000;
            --preto-claro: #0a0a0a;
            --branco: #ffffff;
            --cinza: #cccccc;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: var(--preto);
            color: var(--branco);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 15px;
            overflow-x: hidden;
        }
        
        /* Efeitos de fundo otimizados */
        #bg-effects {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle at 20% 30%, rgba(255,51,51,0.1) 0%, transparent 50%),
                        radial-gradient(circle at 80% 70%, rgba(255,51,51,0.1) 0%, transparent 50%);
            animation: pulseBg 8s infinite alternate;
        }
        
        @keyframes pulseBg {
            0% { opacity: 0.5; }
            100% { opacity: 0.8; }
        }
        
        /* Cartão principal */
        .business-card {
            width: 100%;
            max-width: 800px;
            background: rgba(10, 10, 10, 0.9);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(255, 51, 51, 0.3);
            border: 1px solid rgba(255, 51, 51, 0.2);
            position: relative;
            backdrop-filter: blur(10px);
        }
        
        /* Cabeçalho */
        .card-header {
            background: linear-gradient(90deg, var(--preto) 0%, #8b0000 100%);
            padding: 30px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .card-header::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            animation: shine 3s infinite;
        }
        
        @keyframes shine {
            100% { left: 100%; }
        }
        
        .logo-text {
            font-size: 3rem;
            font-weight: 800;
            letter-spacing: 2px;
            color: var(--branco);
            text-shadow: 0 0 15px var(--vermelho);
            margin-bottom: 5px;
            animation: glow 2s infinite alternate;
        }
        
        @keyframes glow {
            0% { text-shadow: 0 0 10px var(--vermelho); }
            100% { text-shadow: 0 0 20px var(--vermelho), 0 0 30px rgba(255,51,51,0.7); }
        }
        
        .tagline {
            font-size: 1.3rem;
            color: var(--cinza);
            margin-top: 10px;
        }
        
        /* Botão WhatsApp FIXO */
        .whatsapp-float {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 60px;
            height: 60px;
            background: #25D366;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 30px;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(37, 211, 102, 0.5);
            z-index: 1000;
            animation: pulseWhatsapp 2s infinite;
            transition: all 0.3s;
        }
        
        .whatsapp-float:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 20px rgba(37, 211, 102, 0.7);
        }
        
        @keyframes pulseWhatsapp {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        
        /* Conteúdo principal */
        .card-content {
            display: flex;
            flex-wrap: wrap;
            padding: 30px 20px;
            gap: 20px;
        }
        
        .column {
            flex: 1;
            min-width: 300px;
        }
        
        .section {
            margin-bottom: 25px;
        }
        
        .section-title {
            color: var(--vermelho);
            font-size: 1.4rem;
            margin-bottom: 15px;
            padding-bottom: 8px;
            border-bottom: 2px solid rgba(255,51,51,0.3);
            position: relative;
            display: flex;
            align-items: center;
        }
        
        .section-title i {
            margin-right: 10px;
        }
        
        /* Contato */
        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            padding: 12px;
            background: rgba(255,255,255,0.05);
            border-radius: 10px;
            transition: all 0.3s;
            border-left: 3px solid transparent;
        }
        
        .contact-item:hover {
            background: rgba(255,51,51,0.1);
            border-left: 3px solid var(--vermelho);
            transform: translateX(5px);
        }
        
        .contact-icon {
            width: 40px;
            height: 40px;
            background: rgba(255,51,51,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            color: var(--vermelho);
        }
        
        .contact-text {
            font-size: 1.1rem;
        }
        
        .contact-text a {
            color: var(--branco);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .contact-text a:hover {
            color: var(--vermelho);
        }
        
        /* Serviços */
        .service-item {
            padding: 12px;
            margin-bottom: 12px;
            background: rgba(255,255,255,0.05);
            border-radius: 10px;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .service-item:hover {
            background: rgba(255,51,51,0.1);
            transform: translateY(-3px);
        }
        
        .service-item::before {
            content: '▶';
            position: absolute;
            left: -20px;
            color: var(--vermelho);
            transition: left 0.3s;
        }
        
        .service-item:hover::before {
            left: 10px;
        }
        
        .service-name {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .service-desc {
            color: var(--cinza);
            font-size: 0.9rem;
        }
        
        /* Botão WhatsApp interno */
        .whatsapp-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #25D366, #128C7E);
            color: white;
            padding: 15px;
            border-radius: 10px;
            text-decoration: none;
            font-weight: bold;
            margin-top: 20px;
            transition: all 0.3s;
            text-align: center;
            gap: 10px;
        }
        
        .whatsapp-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(37, 211, 102, 0.4);
        }
        
        /* Rodapé */
        .card-footer {
            background: rgba(0,0,0,0.8);
            padding: 20px;
            text-align: center;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: var(--cinza);
            font-size: 0.9rem;
        }
        
        /* Responsividade */
        @media (max-width: 768px) {
            .logo-text { font-size: 2.2rem; }
            .tagline { font-size: 1.1rem; }
            .card-content { padding: 20px 15px; }
            .column { min-width: 100%; }
            .whatsapp-float {
                bottom: 15px;
                right: 15px;
                width: 50px;
                height: 50px;
                font-size: 24px;
            }
        }
        
        @media (max-width: 480px) {
            .logo-text { font-size: 1.8rem; }
            .section-title { font-size: 1.2rem; }
            .contact-text { font-size: 1rem; }
            .card-header { padding: 20px 15px; }
        }
        @media (max-width: 420px) {
            .business-card { max-width: 420px; border-radius: 16px; }
            .card-content { padding: 15px; }
            .logo-text { font-size: 1.6rem; }
            .tagline { font-size: 1rem; }
        }

        /* Menu de gaveta (drawer) */
        .drawer {
            position: fixed;
            left: 12px;
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            gap: 10px;
            z-index: 1200;
        }

        .drawer-item {
            width: 48px;
            height: 48px;
            background: rgba(0,0,0,0.6);
            color: white;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            cursor: pointer;
            transition: transform 0.18s ease, background 0.18s;
            box-shadow: 0 4px 12px rgba(0,0,0,0.4);
        }

        .drawer-item:active { transform: scale(0.98); }

        .drawer-item .label {
            position: absolute;
            left: 60px;
            top: 50%;
            transform: translateY(-50%) translateX(-8px);
            background: rgba(10,10,10,0.9);
            padding: 8px 12px;
            border-radius: 8px;
            white-space: nowrap;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.18s ease, transform 0.18s ease;
            font-size: 0.95rem;
            color: var(--branco);
            border: 1px solid rgba(255,255,255,0.05);
        }

        .drawer-item:hover .label,
        .drawer-item.open .label {
            opacity: 1;
            transform: translateY(-50%) translateX(0);
            pointer-events: auto;
        }

        .drawer-item .submenu {
            position: absolute;
            left: 60px;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(10,10,10,0.95);
            border-radius: 8px;
            padding: 8px;
            box-shadow: 0 6px 20px rgba(0,0,0,0.5);
            display: none;
            min-width: 180px;
            z-index: 1300;
        }

        .drawer-item.open .submenu,
        .drawer-item:hover .submenu {
            display: block;
        }

        .drawer-item .submenu a {
            display: block;
            color: var(--branco);
            text-decoration: none;
            padding: 8px 10px;
            border-radius: 6px;
            font-size: 0.95rem;
        }

        .drawer-item .submenu a:hover { background: rgba(255,255,255,0.03); color: var(--vermelho); }

        @media (max-width: 600px) {
            .drawer { left: 8px; }
            .drawer-item { width: 44px; height: 44px; }
            .drawer-item .label { display: none; }
        }

    </style>
</head>
<body>
    <!-- Efeitos de fundo -->
    <div id="bg-effects"></div>
    
    <!-- Cartão principal -->
    <div class="business-card">
        <!-- Cabeçalho -->
        <div class="card-header">
            <div class="logo-text">DANIELSONSMA</div>
            <div class="tagline">Solução em Manutenção Industrial e Automação</div>
        </div>
        
        <!-- Conteúdo -->
        <div class="card-content">
            <!-- Coluna 1: Contato -->
            <div class="column">
                <div class="section">
                    <h2 class="section-title"><i class="fas fa-address-card"></i> CONTATO</h2>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone-alt"></i>
                        </div>
                        <div class="contact-text">
                            <a href="tel:+5588996116544">(88) 99611-6544</a>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-tools"></i>
                        </div>
                        <div class="contact-text">
                            Especialista em CLPs e Automação
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-industry"></i>
                        </div>
                        <div class="contact-text">
                            Manutenção Industrial e Soluções
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-text">
                            <a href="mailto:machadodanielson733@gmail.com">machadodanielson733@gmail.com</a>
                        </div>
                    </div>
                    
                          <a href="https://wa.me/5588996116544?text=Olá%20DANIELSONSMA!%20Vi%20seu%20cartão%20de%20visita%20e%20preciso%20de%20serviços%20de%20automação." 
                              class="whatsapp-btn" target="_blank" rel="noopener noreferrer" aria-label="Abrir conversa no WhatsApp" role="button">
                        <i class="fab fa-whatsapp"></i>
                        Falar no WhatsApp
                    </a>
                </div>
            </div>
            
            <!-- Coluna 2: Serviços -->
            <div class="column">
                <div class="section">
                    <h2 class="section-title"><i class="fas fa-cogs"></i> SERVIÇOS</h2>
                    
                    <div class="service-item">
                        <div class="service-name">CLPs Siemens</div>
                        <div class="service-desc">Configuração e programação avançada</div>
                    </div>
                    
                    <div class="service-item">
                        <div class="service-name">CLPs Schneider</div>
                        <div class="service-desc">Desenvolvimento e implementação</div>
                    </div>
                    
                    <div class="service-item">
                        <div class="service-name">Software para Automação</div>
                        <div class="service-desc">Criação personalizada para CLPs</div>
                    </div>
                    
                    <div class="service-item">
                        <div class="service-name">Diversas Marcas</div>
                        <div class="service-desc">Soluções para várias marcas de CLPs</div>
                    </div>
                </div>
                
                <div class="section">
                    <h2 class="section-title"><i class="fas fa-bolt"></i> ESPECIALIDADES</h2>
                    
                    <div class="service-item">
                        <div class="service-name">Manutenção Industrial</div>
                        <div class="service-desc">Preventiva e corretiva</div>
                    </div>
                    
                    <div class="service-item">
                        <div class="service-name">Automação de Processos</div>
                        <div class="service-desc">Soluções completas</div>
                    </div>
                    
                    <div class="service-item">
                        <div class="service-name">Indústria 4.0</div>
                        <div class="service-desc">Tecnologia moderna</div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Rodapé -->
        <div class="card-footer">
            Tecnologia e Inovação para a Indústria Moderna • Atendimento em todo Brasil
        </div>
    </div>
    
    <!-- Botão flutuante do WhatsApp -->
    <!-- Menu de gaveta (drawer) -->
    <nav class="drawer" aria-label="Menu rápido">
        <div class="drawer-item" data-key="servicos" tabindex="0" role="button" aria-haspopup="true" aria-expanded="false">
            <i class="fas fa-cogs" aria-hidden="true"></i>
            <div class="label">Serviços</div>
            <div class="submenu" role="menu" aria-label="Serviços">
                <a href="#" role="menuitem">CLPs Siemens</a>
                <a href="#" role="menuitem">CLPs Schneider</a>
                <a href="#" role="menuitem">Software para Automação</a>
            </div>
        </div>

        <div class="drawer-item" data-key="especialidades" tabindex="0" role="button" aria-haspopup="true" aria-expanded="false">
            <i class="fas fa-bolt" aria-hidden="true"></i>
            <div class="label">Especialidades</div>
            <div class="submenu" role="menu" aria-label="Especialidades">
                <a href="#" role="menuitem">Manutenção Industrial</a>
                <a href="#" role="menuitem">Automação de Processos</a>
                <a href="#" role="menuitem">Indústria 4.0</a>
            </div>
        </div>

        <div class="drawer-item" data-key="contatos" tabindex="0" role="button" aria-haspopup="true" aria-expanded="false">
            <i class="fas fa-address-card" aria-hidden="true"></i>
            <div class="label">Contatos</div>
            <div class="submenu" role="menu" aria-label="Contatos">
                <a href="tel:+5588996116544" role="menuitem">(88) 99611-6544</a>
                <a href="mailto:machadodanielson733@gmail.com" role="menuitem">machadodanielson733@gmail.com</a>
                <a href="https://wa.me/5588996116544" target="_blank" rel="noopener noreferrer" role="menuitem">WhatsApp</a>
            </div>
        </div>
    </nav>

    <!-- Botão flutuante do WhatsApp -->
    <a href="https://wa.me/5588996116544?text=Olá%20DANIELSONSMA!%20Gostaria%20de%20solicitar%20um%20orçamento%20para%20serviços%20de%20automação." 
        class="whatsapp-float" target="_blank" rel="noopener noreferrer" aria-label="Abrir conversa no WhatsApp" title="Fale conosco no WhatsApp" role="button">
        <i class="fab fa-whatsapp"></i>
    </a>
    
    <script>
        // Animação de digitação
        function typeWriter() {
            const logo = document.querySelector('.logo-text');
            const text = 'DANIELSONSMA';
            let i = 0;
            
            logo.textContent = '';
            
            function type() {
                if (i < text.length) {
                    logo.textContent += text.charAt(i);
                    i++;
                    setTimeout(type, 150);
                }
            }
            
            // Delay inicial
            setTimeout(type, 500);
        }
        
        // Efeitos de hover nos itens
        function addHoverEffects() {
            const items = document.querySelectorAll('.contact-item, .service-item');
            
            items.forEach(item => {
                item.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateX(5px)';
                });
                
                item.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateX(0)';
                });
            });
        }
        
        // Efeito de partículas leves
        function createLightParticles() {
            const container = document.getElementById('bg-effects');
            
            // Apenas 5 partículas para performance
            for (let i = 0; i < 5; i++) {
                const particle = document.createElement('div');
                particle.style.cssText = `
                    position: absolute;
                    width: ${2 + Math.random() * 3}px;
                    height: ${2 + Math.random() * 3}px;
                    background: rgba(255, 51, 51, ${0.3 + Math.random() * 0.4});
                    border-radius: 50%;
                    top: ${Math.random() * 100}%;
                    left: ${Math.random() * 100}%;
                    animation: floatParticle ${8 + Math.random() * 12}s infinite linear;
                `;
                
                // Adicionar keyframes dinamicamente
                const style = document.createElement('style');
                style.textContent = `
                    @keyframes floatParticle {
                        0% {
                            transform: translate(0, 0);
                            opacity: 0;
                        }
                        10% {
                            opacity: 1;
                        }
                        90% {
                            opacity: 1;
                        }
                        100% {
                            transform: translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px);
                            opacity: 0;
                        }
                    }
                `;
                document.head.appendChild(style);
                
                container.appendChild(particle);
            }
        }
        
        // Inicializar quando carregar
        document.addEventListener('DOMContentLoaded', function() {
            typeWriter();
            addHoverEffects();
            createLightParticles();
            
            // Efeito 3D suave no cartão
            const card = document.querySelector('.business-card');
            
            card.addEventListener('mousemove', function(e) {
                const rect = this.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                
                const rotateY = (x - centerX) / 30;
                const rotateX = (centerY - y) / 30;

                this.style.transform = `perspective(800px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'perspective(800px) rotateX(0) rotateY(0)';
            });

            // Menu de gaveta: hover já abre via CSS; aqui adicionamos toque/click e acessibilidade
            const drawerItems = document.querySelectorAll('.drawer-item');

            function closeAllDrawers(except) {
                drawerItems.forEach(it => {
                    if (it !== except) {
                        it.classList.remove('open');
                        it.setAttribute('aria-expanded', 'false');
                    }
                });
            }

            drawerItems.forEach(item => {
                // Toggle on click/touch
                item.addEventListener('click', function(e) {
                    const isOpen = this.classList.toggle('open');
                    this.setAttribute('aria-expanded', isOpen ? 'true' : 'false');
                    if (isOpen) closeAllDrawers(this);
                    e.stopPropagation();
                });

                // Keyboard support (Enter / Space)
                item.addEventListener('keydown', function(e) {
                    if (e.key === 'Enter' || e.key === ' ') {
                        e.preventDefault();
                        this.click();
                    }
                });

                // Prevent immediate blur on touch devices
                item.addEventListener('touchstart', function(e) {
                    // small delay to allow click handler to run properly
                    e.stopPropagation();
                });
            });

            // Close drawers when clicking/tapping outside
            document.addEventListener('click', function(e) {
                if (!e.target.closest('.drawer')) closeAllDrawers();
            });
        });
    </script>
</body>
</html>
