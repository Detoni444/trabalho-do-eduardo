<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no" />
<title>Site Complexo Moderno</title>
<style>
  /* Reset & base */
  *, *::before, *::after {
    box-sizing: border-box;
  }
  body {
    margin: 0; 
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: #121212;
    color: #eee;
    overflow-x: hidden;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
  a {
    color: #1dd1a1;
    text-decoration: none;
    transition: color 0.3s ease;
  }
  a:hover, a:focus {
    color: #10ac84;
  }
  img {
    max-width: 100%;
    display: block;
  }
  h1, h2, h3, h4 {
    margin: 0 0 1rem 0;
    font-weight: 700;
  }
  p {
    line-height: 1.5;
    margin: 0 0 1rem 0;
  }
  section {
    padding: 3rem 1.5rem;
  }
  /* Container */
  .container {
    max-width: 900px;
    margin-left: auto;
    margin-right: auto;
  }
  /* Navigation */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    background: rgba(18,18,18,0.95);
    display: flex;
    justify-content: center;
    box-shadow: 0 2px 10px rgba(0,0,0,0.7);
    z-index: 9999;
  }
  nav ul {
    list-style: none;
    display: flex;
    padding: 0.75rem 1rem;
    margin: 0;
  }
  nav ul li {
    margin: 0 1rem;
  }
  nav ul li a {
    font-size: 1.1rem;
    font-weight: 600;
    padding: 0.5rem;
    border-radius: 5px;
    display: inline-block;
  }
  nav ul li a.active,
  nav ul li a:hover {
    background: #1dd1a1;
    color: #121212;
  }
  /* Hero */
  #hero {
    height: 600px;
    min-height: 600px;
    background: linear-gradient(120deg, #1dd1a1, #10ac84);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 0 1rem;
  }
  #hero h1 {
    font-size: 2.5rem;
    color: #fff;
    text-shadow: 0 0 15px #10ac84;
  }
  #hero p {
    font-size: 1.2rem;
    margin-top: 1rem;
    color: #e0f7f1;
    max-width: 500px;
  }
  #hero button {
    margin-top: 2rem;
    background: #121212;
    color: #1dd1a1;
    font-weight: 700;
    border: none;
    padding: 0.75rem 2rem;
    border-radius: 50px;
    cursor: pointer;
    box-shadow: 0 0 8px #1dd1a1aa;
    transition: background 0.3s ease, color 0.3s ease;
    font-size: 1.1rem;
  }
  #hero button:hover, #hero button:focus {
    background: #1dd1a1;
    color: #121212;
    outline: none;
  }
  /* About Section */
  #about {
    background: #181818;
    border-radius: 15px;
  }
  #about .content {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    align-items: center;
    justify-content: center;
  }
  #about .content img {
    border-radius: 15px;
    width: 280px;
    height: 280px;
    object-fit: cover;
    box-shadow: 0 0 15px #10ac84aa;
    transition: transform 0.3s ease;
  }
  #about .content img:hover {
    transform: scale(1.05);
  }
  #about .text {
    max-width: 540px;
  }
  #about .text h2 {
    color: #1dd1a1;
  }
  /* Services */
  #services {
    background: linear-gradient(45deg, #10ac84, #1dd1a1);
    border-radius: 15px;
    color: #121212;
  }
  #services h2 {
    text-align: center;
    margin-bottom: 2rem;
  }
  .service-list {
    display: flex;
    gap: 1.5rem;
    flex-wrap: wrap;
    justify-content: center;
  }
  .service-card {
    background: #e0f7f1;
    flex: 1 1 260px;
    border-radius: 15px;
    padding: 1.5rem;
    box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    cursor: default;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  .service-card:hover, .service-card:focus {
    box-shadow: 0 6px 30px rgba(0,0,0,0.2);
    transform: translateY(-10px);
    outline: none;
  }
  .service-icon {
    font-size: 3rem;
    color: #10ac84;
    margin-bottom: 1rem;
  }
  /* Portfolio */
  #portfolio {
    background: #181818;
    border-radius: 15px;
  }
  #portfolio h2 {
    text-align: center;
    color: #1dd1a1;
    margin-bottom: 2rem;
  }
  .gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: center;
  }
  .gallery-item {
    flex: 1 1 140px;
    max-width: 140px;
    overflow: hidden;
    border-radius: 10px;
    cursor: pointer;
    box-shadow: 0 0 15px #1dd1a1aa;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    position: relative;
  }
  .gallery-item:hover, .gallery-item:focus {
    transform: scale(1.1);
    box-shadow: 0 0 25px #10ac84ff;
    outline: none;
    z-index: 5;
  }
  .gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  /* Modal for Portfolio */
  .modal {
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background: rgba(0,0,0,0.85);
    display: none;
    justify-content: center;
    align-items: center;
    z-index: 10000;
    padding: 1rem;
  }
  .modal.active {
    display: flex;
  }
  .modal-content {
    max-width: 90vw;
    max-height: 80vh;
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 0 30px #10ac84ff;
  }
  .modal-content img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    background: #181818;
  }
  .modal-close {
    position: fixed;
    top: 1rem;
    right: 1rem;
    background: #10ac84;
    border: none;
    color: #121212;
    font-size: 1.25rem;
    font-weight: 700;
    padding: 0.25rem 0.75rem;
    border-radius: 50px;
    cursor: pointer;
    box-shadow: 0 0 8px #10ac84aa;
    transition: background 0.3s ease;
    z-index: 11000;
  }
  .modal-close:hover, .modal-close:focus {
    background: #1dd1a1;
    outline: none;
  }
  /* Contact Section */
  #contact {
    background: linear-gradient(120deg, #1dd1a1, #10ac84);
    border-radius: 15px;
    color: #121212;
  }
  #contact h2 {
    text-align: center;
    color: #121212;
    margin-bottom: 2rem;
  }
  form {
    max-width: 450px;
    margin: 0 auto;
  }
  form label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 600;
    color: #121212;
  }
  form input, form textarea {
    width: 100%;
    padding: 0.75rem 1rem;
    margin-bottom: 1.25rem;
    border-radius: 10px;
    border: none;
    font-size: 1rem;
    resize: vertical;
  }
  form input:focus, form textarea:focus {
    outline: 3px solid #121212;
  }
  form button {
    background: #121212;
    color: #1dd1a1;
    font-weight: 700;
    border: none;
    padding: 0.75rem 2rem;
    border-radius: 50px;
    cursor: pointer;
    width: 100%;
    font-size: 1.1rem;
    box-shadow: 0 0 10px #1dd1a1aa;
    transition: background 0.3s ease, color 0.3s ease;
  }
  form button:hover, form button:focus {
    background: #1dd1a1;
    color: #121212;
    outline: none;
  }
  /* Footer */
  footer {
    background: #121212;
    text-align: center;
    padding: 1.5rem 1rem;
    font-size: 0.9rem;
    color: #777;
  }
  footer a {
    color: #1dd1a1;
    margin: 0 0.5rem;
    font-weight: 600;
  }
  /* Responsive */
  @media (max-width: 600px) {
    #about .content {
      flex-direction: column;
    }
    #about .content img {
      width: 100%;
      height: auto;
    }
  }
</style>
</head>
<body>

<nav>
  <ul>
    <li><a href="#hero" class="active">Início</a></li>
    <li><a href="#about">Sobre</a></li>
    <li><a href="#services">Serviços</a></li>
    <li><a href="#portfolio">Portfólio</a></li>
    <li><a href="#contact">Contato</a></li>
  </ul>
</nav>

<section id="hero" tabindex="-1" aria-label="Seção inicial">
  <h1>Bem-vindo ao Nosso Site Complexo</h1>
  <p>Uma experiência visual moderna, interativa e totalmente responsiva. Explore nossos serviços e portfólio!</p>
  <button onclick="scrollToSection('contact')" aria-label="Ir para a seção de contato">Fale Conosco</button>
</section>

<section id="about" class="container" tabindex="-1" aria-labelledby="about-title">
  <h2 id="about-title">Sobre Nós</h2>
  <div class="content">
    <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=320&q=80" alt="Foto do time" />
    <div class="text">
      <p>Somos uma equipe dedicada a criar soluções inovadoras e projetos de alta qualidade. Com amplo conhecimento em design, desenvolvimento e tecnologias modernas, entregamos produtos que encantam nossos clientes e transformam suas ideias em realidade.</p>
      <p>Nosso compromisso é a excelência, inovação e atendimento personalizado para cada desafio que enfrentamos.</p>
    </div>
  </div>
</section>

<section id="services" tabindex="-1" aria-labelledby="services-title">
  <div class="container">
    <h2 id="services-title">Nossos Serviços</h2>
    <div class="service-list">
      <article class="service-card" tabindex="0" aria-label="Design Responsivo">
        <div class="service-icon" aria-hidden="true">🎨</div>
        <h3>Design Responsivo</h3>
        <p>Criação de interfaces modernas e responsivas para todos os dispositivos, garantindo experiência fluida e intuitiva.</p>
      </article>

      <article class="service-card" tabindex="0" aria-label="Desenvolvimento Web">
        <div class="service-icon" aria-hidden="true">💻</div>
        <h3>Desenvolvimento Web</h3>
        <p>Construção de sites e aplicativos usando as tecnologias mais recentes, focando em performance, SEO e acessibilidade.</p>
      </article>

      <article class="service-card" tabindex="0" aria-label="Consultoria Técnica">
        <div class="service-icon" aria-hidden="true">🧠</div>
        <h3>Consultoria Técnica</h3>
        <p>Orientação especializada para otimizar processos, infraestrutura e estratégias digitais com foco em resultados.</p>
      </article>
    </div>
  </div>
</section>

<section id="portfolio" tabindex="-1" aria-labelledby="portfolio-title">
  <div class="container">
    <h2 id="portfolio-title">Portfólio</h2>
    <div class="gallery" role="list">
      <div class="gallery-item" role="listitem" tabindex="0" aria-label="Projeto 1: site de e-commerce" onclick="openModal(this)" onkeypress="if(event.key==='Enter') openModal(this)">
        <img src="https://images.unsplash.com/photo-1521737604893-d14cc237f11d?auto=format&fit=crop&w=140&q=80" alt="Screenshot Projeto 1" />
      </div>
      <div class="gallery-item" role="listitem" tabindex="0" aria-label="Projeto 2: blog corporativo" onclick="openModal(this)" onkeypress="if(event.key==='Enter') openModal(this)">
        <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=140&q=80" alt="Screenshot Projeto 2" />
      </div>
      <div class="gallery-item" role="listitem" tabindex="0" aria-label="Projeto 3: aplicativo mobile" onclick="openModal(this)" onkeypress="if(event.key==='Enter') openModal(this)">
        <img src="https://images.unsplash.com/photo-1555529669-0f84df3d04e9?auto=format&fit=crop&w=140&q=80" alt="Screenshot Projeto 3" />
      </div>
      <div class="gallery-item" role="listitem" tabindex="0" aria-label="Projeto 4: landing page de campanha" onclick="openModal(this)" onkeypress="if(event.key==='Enter') openModal(this)">
        <img src="https://images.unsplash.com/photo-1515377905703-c4788e51af15?auto=format&fit=crop&w=140&q=80" alt="Screenshot Projeto 4" />
      </div>
      <div class="gallery-item" role="listitem" tabindex="0" aria-label="Projeto 5: portal institucional" onclick="openModal(this)" onkeypress="if(event.key==='Enter') openModal(this)">
        <img src="https://images.unsplash.com/photo-1497493292307-31c376b6e479?auto=format&fit=crop&w=140&q=80" alt="Screenshot Projeto 5" />
      </div>
      <div class="gallery-item" role="listitem" tabindex="0" aria-label="Projeto 6: aplicação SaaS" onclick="openModal(this)" onkeypress="if(event.key==='Enter') openModal(this)">
        <img src="https://images.unsplash.com/photo-1508830524289-0adcbe822b40?auto=format&fit=crop&w=140&q=80" alt="Screenshot Projeto 6" />
      </div>
    </div>
  </div>
</section>

<div class="modal" role="dialog" aria-modal="true" aria-label="Visualização de imagem" id="modal">
  <button class="modal-close" aria-label="Fechar modal" onclick="closeModal()">×</button>
  <div class="modal-content" id="modal-content" tabindex="0"></div>
</div>

<section id="contact" tabindex="-1" aria-labelledby="contact-title">
  <div class="container">
    <h2 id="contact-title">Contato</h2>
    <form id="contact-form" novalidate>
      <label for="name">Nome</label>
      <input type="text" id="name" name="name" placeholder="Seu nome" required minlength="2" aria-required="true" />

      <label for="email">Email</label>
      <input type="email" id="email" name="email" placeholder="seu@email.com" required aria-required="true" />

      <label for="message">Mensagem</label>
      <textarea id="message" name="message" placeholder="Escreva sua mensagem" rows="4" required aria-required="true" minlength="10"></textarea>

      <button type="submit" aria-label="Enviar mensagem">Enviar</button>
    </form>
  </div>
</section>

<footer role="contentinfo">
  <p>© 2024 Site Complexo Moderno. Todos os direitos reservados.</p>
  <p>
    <a href="https://www.linkedin.com" target="_blank" rel="noopener" aria-label="LinkedIn">LinkedIn</a> |
    <a href="https://github.com" target="_blank" rel="noopener" aria-label="GitHub">GitHub</a> |
    <a href="https://twitter.com" target="_blank" rel="noopener" aria-label="Twitter">Twitter</a>
  </p>
</footer>

<script>
  // Smooth scrolling for nav links
  document.querySelectorAll('nav a').forEach(link => {
    link.addEventListener('click', e => {
      e.preventDefault();
      document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
      link.classList.add('active');
      const targetId = link.getAttribute('href').substring(1);
      const targetSection = document.getElementById(targetId);
      if(targetSection) {
        targetSection.scrollIntoView({behavior: 'smooth', block: 'start'});
        // For keyboard accessibility, focus after scroll
        setTimeout(() => {
          targetSection.focus();
        }, 500);
      }
    });
  });

  // Scroll to section helper used on hero button
  function scrollToSection(id) {
    const el = document.getElementById(id);
    if(el) {
      el.scrollIntoView({behavior: 'smooth', block: 'start'});
      setTimeout(() => {
        el.focus();
      }, 500);
    }
  }

  // Portfolio modal logic
  const modal = document.getElementById('modal');
  const modalContent = document.getElementById('modal-content');
  const galleryItems = document.querySelectorAll('.gallery-item');

  function openModal(element) {
    const img = element.querySelector('img');
    if(img) {
      modalContent.innerHTML = '';
      const fullImg = document.createElement('img');
      fullImg.src = img.src.replace(/w=140/, 'w=900');
      fullImg.alt = img.alt;
      modalContent.appendChild(fullImg);
      modal.classList.add('active');
      modalContent.focus();
    }
  }

  function closeModal() {
    modal.classList.remove('active');
    modalContent.innerHTML = '';
  }

  modal.addEventListener('click', e => {
    if(e.target === modal) {
      closeModal();
    }
  });

  document.addEventListener('keydown', e => {
    if(e.key === 'Escape' && modal.classList.contains('active')) {
      closeModal();
    }
  });

  // Contact form validation & submit handler
  const form = document.getElementById('contact-form');
  form.addEventListener('submit', e => {
    e.preventDefault();

    // Simple client validation
    let valid = form.checkValidity();
    if(!valid) {
      form.reportValidity();
      return;
    }

    // Simulate form submission
    const submitButton = form.querySelector('button[type="submit"]');
    submitButton.disabled = true;
    submitButton.textContent = 'Enviando...';

    // Fake delay
    setTimeout(() => {
      alert('Mensagem enviada com sucesso! Obrigado por entrar em contato.');
      form.reset();
      submitButton.disabled = false;
      submitButton.textContent = 'Enviar';
    }, 1500);
  });

</script>

</body>
</html>

