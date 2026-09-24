<template>
  <div class="portfolio-app">
    <!-- NAVBAR -->
    <header class="navbar">
      <div class="container nav-container">
        <a href="#hero" class="logo">&lt;Devis Borg /&gt;</a>
        <nav>
          <ul class="nav-links">
            <li><a href="#about">Sobre</a></li>
            <li><a href="#skills">Habilidades</a></li>
            <li><a href="#projects">Projetos</a></li>
            <li><a href="#contact">Contato</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <!-- HERO SECTION -->
    <section id="hero" class="hero-section">
      <div class="container hero-content">
        <span class="badge-role">Desenvolvedor Web & Infraestrutura</span>
        <h1>Devis Borg de Alcino</h1>
        <p class="hero-subtext">
          Desenvolvimento de aplicações web modernas, APIs RESTful de alta performance em Python/FastAPI, 
          conteinerização com Docker e gestão de infraestrutura Linux.
        </p>
        <div class="hero-buttons">
          <a href="#projects" class="btn primary-btn">Ver Vitrine de Projetos</a>
          <a href="#contact" class="btn secondary-btn">Entrar em Contato</a>
        </div>
      </div>
    </section>

    <!-- SOBRE MIM -->
    <section id="about" class="section">
      <div class="container">
        <h2 class="section-title">Sobre Mim</h2>
        <div class="about-card">
          <p>
            Sou desenvolvedor com foco em soluções web integradas, automação de processos e infraestrutura de servidores. 
            Atualmente cursando Pós-Graduação em <strong>Cibersegurança em Aplicações de Inteligência Artificial</strong> e graduando em <strong>Cibersegurança</strong> pela Faculdade Anhanguera.
          </p>
          <p>
            Possuo sólida experiência prática no desenvolvimento backend com Python (FastAPI/Uvicorn), criação de interfaces web com Vue.js/JavaScript, conteinerização de serviços com Docker, versionamento de código com Git/GitHub e administração de servidores Linux.
          </p>
        </div>
      </div>
    </section>

    <!-- HABILIDADES -->
    <section id="skills" class="section bg-alt">
      <div class="container">
        <h2 class="section-title">Conhecimentos & Habilidades</h2>
        <div class="skills-grid">
          <div class="skill-category" v-for="(cat, idx) in skillCategories" :key="idx">
            <h3>{{ cat.title }}</h3>
            <div class="skill-tags">
              <span class="skill-tag" v-for="skill in cat.skills" :key="skill">{{ skill }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- PORTFÓLIO / VITRINE DE PROJETOS -->
    <section id="projects" class="section">
      <div class="container">
        <div class="projects-header">
          <h2 class="section-title">Vitrine de Projetos</h2>
          <p class="section-subtitle">
            Repositórios públicos e projetos hospedados no GitHub (<strong>@SuppaHackaD</strong>)
          </p>
        </div>

        <div class="projects-grid">
          <div class="project-card" v-for="proj in repositorios" :key="proj.nome">
            <div class="card-header">
              <span class="folder-icon">📁</span>
              <h3>{{ proj.nome }}</h3>
            </div>
            <p class="project-desc">{{ proj.descricao }}</p>
            <div class="project-techs">
              <span class="tech-badge" v-for="tech in proj.techs" :key="tech">{{ tech }}</span>
            </div>
            <div class="card-footer">
              <a :href="proj.githubUrl" target="_blank" rel="noopener" class="repo-link">
                Ver no GitHub &rarr;
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CONTATO -->
    <section id="contact" class="section bg-alt">
      <div class="container contact-container">
        <h2 class="section-title">Entre em Contato</h2>
        <p>Aberto para oportunidades e colaborações em desenvolvimento web e infraestrutura.</p>
        
        <div class="contact-links">
          <a href="https://github.com/SuppaHackaD" target="_blank" class="contact-card">
            <span class="icon">💻</span>
            <span>GitHub (@SuppaHackaD)</span>
          </a>
          <a href="https://www.linkedin.com/in/devis-borg-de-alcino-305b36295/" target="_blank" class="contact-card">
            <span class="icon">👔</span>
            <span>LinkedIn</span>
          </a>
          <a href="mailto:devisbalcino@gmail.com" class="contact-card">
            <span class="icon">✉️</span>
            <span>E-mail Direto</span>
          </a>
        </div>
      </div>
    </section>

    <!-- FOOTER -->
    <footer class="footer">
      <div class="container">
        <p>© 2026 Devis Borg de Alcino. Desenvolvido com Vue.js 3 e hospedado Github pages.</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// Categorias de Habilidades (Alinhadas com o edital do IFMG)
const skillCategories = ref([
  {
    title: 'Desenvolvimento Web Front-End',
    skills: ['Vue.js', 'JavaScript (ES6+)', 'HTML5', 'CSS3', 'Vite', 'PWAs']
  },
  {
    title: 'Back-End & APIs',
    skills: ['Python', 'FastAPI', 'Uvicorn', 'APIs RESTful', 'JSON']
  },
  {
    title: 'Infraestrutura & DevOps',
    skills: ['Docker', 'Containers', 'Linux', 'Git', 'GitHub', 'Cloudflare Tunnels', 'Tailscale']
  },
  {
    title: 'Linguagens de Baixo Nível',
    skills: ['C', 'Fortran', 'Raylib', 'OpenMP', 'OpenSSL']
  }
])

// Vitrine dos seus projetos públicos ativos no GitHub
const repositorios = ref([
  {
    nome: 'trindas_bot',
    descricao: 'Sistema backend em Python estruturando APIs RESTful com FastAPI e Uvicorn, incluindo dashboard web para monitoramento.',
    techs: ['Python', 'FastAPI', 'Uvicorn', 'REST API'],
    githubUrl: 'https://github.com/SuppaHackaD/trindas_bot'
  },
  {
    nome: 'Merlin',
    descricao: 'Ferramenta em Python para download, automação, organização e conversão automática de mídias digitais para formato CBZ.',
    techs: ['Python', 'Automação', 'CLI', 'Git'],
    githubUrl: 'https://github.com/SuppaHackaD/Merlin'
  },
  {
    nome: 'SuppaTalk',
    descricao: 'Aplicação de comunicação em tempo real e troca de mensagens com foco em integração web.',
    techs: ['JavaScript', 'Web', 'Real-Time', 'Sockets'],
    githubUrl: 'https://github.com/SuppaHackaD/SuppaTalk'
  },
  {
    nome: 'SuppaClicker',
    descricao: 'Utilitário de automação de rotinas e simulação de eventos no sistema operacional desenvolvido em Python.',
    techs: ['Python', 'Automação', 'Win32API', 'Scripting'],
    githubUrl: 'https://github.com/SuppaHackaD/SuppaClicker'
  },
  {
    nome: 'SuppaBreaker',
    descricao: 'Ferramenta de análise criptográfica e processamento paralelo de alta performance desenvolvida em C com OpenMP e OpenSSL.',
    techs: ['C', 'OpenMP', 'OpenSSL', 'Paralelismo'],
    githubUrl: 'https://github.com/SuppaHackaD/SuppaBreaker'
  },
  {
    nome: 'SuppaR1',
    descricao: 'Desenvolvimento de baixo nível em C focado na interceptação e emulação de chamadas de API de jogos via Proxy DLL.',
    techs: ['C', 'Systems Programming', 'Proxy DLL', 'Low Level'],
    githubUrl: 'https://github.com/SuppaHackaD/SuppaR1'
  }
])
</script>

<style>
/* CSS Reset e Variáveis de Estilo */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
  background-color: #0f172a;
  color: #f8fafc;
  line-height: 1.6;
}

.portfolio-app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

/* Header & Nav */
.navbar {
  position: sticky;
  top: 0;
  background-color: rgba(15, 23, 42, 0.9);
  backdrop-filter: blur(8px);
  border-bottom: 1px solid #1e293b;
  z-index: 100;
  padding: 1rem 0;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.25rem;
  font-weight: 700;
  color: #38bdf8;
  text-decoration: none;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 1.5rem;
}

.nav-links a {
  color: #94a3b8;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.2s;
}

.nav-links a:hover {
  color: #38bdf8;
}

/* Sections */
.section {
  padding: 5rem 0;
}

.bg-alt {
  background-color: #1e293b;
}

.section-title {
  font-size: 2rem;
  margin-bottom: 1.5rem;
  color: #f8fafc;
  position: relative;
}

.section-title::after {
  content: '';
  display: block;
  width: 50px;
  height: 4px;
  background-color: #42b883; /* Vue Green */
  margin-top: 0.5rem;
  border-radius: 2px;
}

/* Hero Section */
.hero-section {
  padding: 7rem 0 5rem;
  display: flex;
  align-items: center;
}

.badge-role {
  display: inline-block;
  background-color: rgba(66, 184, 131, 0.15);
  color: #42b883;
  padding: 0.35rem 0.8rem;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.hero-content h1 {
  font-size: 3rem;
  font-weight: 800;
  margin-bottom: 1rem;
  line-height: 1.2;
}

.hero-subtext {
  font-size: 1.15rem;
  color: #94a3b8;
  max-width: 650px;
  margin-bottom: 2rem;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.2s;
}

.primary-btn {
  background-color: #42b883;
  color: #0f172a;
}

.primary-btn:hover {
  background-color: #33a06f;
}

.secondary-btn {
  background-color: transparent;
  color: #f8fafc;
  border: 1px solid #334155;
}

.secondary-btn:hover {
  border-color: #94a3b8;
}

/* About Card */
.about-card {
  background-color: #1e293b;
  padding: 2rem;
  border-radius: 8px;
  border: 1px solid #334155;
}

.about-card p {
  margin-bottom: 1rem;
  color: #cbd5e1;
}

.about-card p:last-child {
  margin-bottom: 0;
}

/* Skills */
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1.5rem;
}

.skill-category {
  background-color: #0f172a;
  padding: 1.5rem;
  border-radius: 8px;
  border: 1px solid #334155;
}

.skill-category h3 {
  font-size: 1.1rem;
  margin-bottom: 1rem;
  color: #38bdf8;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.skill-tag {
  background-color: #1e293b;
  color: #e2e8f0;
  padding: 0.25rem 0.6rem;
  border-radius: 4px;
  font-size: 0.85rem;
  border: 1px solid #334155;
}

/* Projects */
.projects-header {
  margin-bottom: 2rem;
}

.section-subtitle {
  color: #94a3b8;
  margin-top: -0.5rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
}

.project-card {
  background-color: #1e293b;
  border-radius: 8px;
  padding: 1.5rem;
  border: 1px solid #334155;
  display: flex;
  flex-direction: column;
  transition: transform 0.2s, border-color 0.2s;
}

.project-card:hover {
  transform: translateY(-4px);
  border-color: #42b883;
}

.card-header {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 0.75rem;
}

.card-header h3 {
  font-size: 1.2rem;
  color: #f8fafc;
}

.project-desc {
  color: #94a3b8;
  font-size: 0.95rem;
  flex-grow: 1;
  margin-bottom: 1.25rem;
}

.project-techs {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-bottom: 1.25rem;
}

.tech-badge {
  background-color: rgba(56, 189, 248, 0.1);
  color: #38bdf8;
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
  font-size: 0.75rem;
  font-weight: 600;
}

.repo-link {
  color: #42b883;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.9rem;
}

.repo-link:hover {
  text-decoration: underline;
}

/* Contact */
.contact-container {
  text-align: center;
}

.contact-container .section-title::after {
  margin: 0.5rem auto 0;
}

.contact-container p {
  color: #94a3b8;
  margin-bottom: 2rem;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.contact-card {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  background-color: #0f172a;
  padding: 1rem 1.5rem;
  border-radius: 8px;
  border: 1px solid #334155;
  color: #f8fafc;
  text-decoration: none;
  font-weight: 500;
  transition: border-color 0.2s;
}

.contact-card:hover {
  border-color: #38bdf8;
}

/* Footer */
.footer {
  border-top: 1px solid #1e293b;
  padding: 2rem 0;
  text-align: center;
  color: #64748b;
  font-size: 0.9rem;
  margin-top: auto;
}

/* Responsividade */
@media (max-width: 768px) {
  .hero-content h1 {
    font-size: 2.2rem;
  }
  .nav-links {
    display: none; /* Em projetos reais você pode colocar um menu hambúrguer */
  }
}
</style>