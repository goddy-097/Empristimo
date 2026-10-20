<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>e-Mola | Empréstimo rápido e seguro</title>
  <!-- Font Awesome 6 (free) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
    }

    body {
      background: #f5f9ff;
      color: #0a2540;
      line-height: 1.5;
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }

    /* container */
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* header */
    .header {
      background: white;
      box-shadow: 0 4px 12px rgba(0, 20, 40, 0.04);
      padding: 16px 0;
      position: sticky;
      top: 0;
      z-index: 20;
    }

    .header-content {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 16px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 1.8rem;
      font-weight: 700;
      letter-spacing: -0.5px;
    }

    .logo i {
      color: #1a7f64;
      font-size: 2rem;
    }

    .logo span {
      color: #0a2540;
    }

    .logo .highlight {
      color: #1a7f64;
    }

    .nav-links {
      display: flex;
      gap: 32px;
      font-weight: 500;
    }

    .nav-links a {
      text-decoration: none;
      color: #2d4a66;
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: #1a7f64;
    }

    .btn-outline {
      border: 1.5px solid #1a7f64;
      background: transparent;
      color: #1a7f64;
      padding: 10px 22px;
      border-radius: 40px;
      font-weight: 600;
      font-size: 0.95rem;
      cursor: pointer;
      transition: all 0.2s;
    }

    .btn-outline:hover {
      background: #e8f3f0;
      border-color: #0e5e4a;
    }

    /* main */
    .main {
      flex: 1;
      padding: 48px 0 64px;
    }

    .hero {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 40px;
      margin-bottom: 48px;
    }

    .hero-text {
      flex: 1 1 350px;
    }

    .hero-text h1 {
      font-size: 2.8rem;
      font-weight: 800;
      line-height: 1.2;
      letter-spacing: -1px;
      margin-bottom: 20px;
    }

    .hero-text h1 span {
      color: #1a7f64;
      background: linear-gradient(145deg, #1a7f64, #2a9d7e);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .hero-text p {
      font-size: 1.2rem;
      color: #3a5a78;
      margin-bottom: 32px;
      max-width: 500px;
    }

    .trust-badge {
      display: flex;
      align-items: center;
      gap: 12px;
      background: white;
      padding: 12px 20px;
      border-radius: 60px;
      box-shadow: 0 6px 16px rgba(0, 50, 30, 0.05);
      width: fit-content;
      font-weight: 500;
      color: #1e4a3b;
    }

    .trust-badge i {
      color: #1a7f64;
      font-size: 1.2rem;
    }

    .hero-card {
      flex: 1 1 350px;
      background: white;
      border-radius: 36px;
      padding: 32px;
      box-shadow: 0 25px 40px -12px rgba(0, 40, 20, 0.2);
      border: 1px solid rgba(26, 127, 100, 0.1);
    }

    .hero-card h2 {
      font-size: 1.6rem;
      font-weight: 700;
      margin-bottom: 8px;
    }

    .hero-card .sub {
      color: #5a6e82;
      margin-bottom: 28px;
      font-size: 0.95rem;
    }

    .simulacao-group {
      margin-bottom: 24px;
    }

    .simulacao-group label {
      display: block;
      font-weight: 600;
      margin-bottom: 8px;
      font-size: 0.95rem;
      color: #1f3b4f;
    }

    .input-wrapper {
      display: flex;
      align-items: center;
      background: #f0f6ff;
      border-radius: 16px;
      padding: 4px 16px;
      border: 1.5px solid transparent;
      transition: 0.2s;
    }

    .input-wrapper:focus-within {
      border-color: #1a7f64;
      background: white;
      box-shadow: 0 0 0 4px rgba(26, 127, 100, 0.1);
    }

    .input-wrapper span {
      font-weight: 600;
      color: #1a7f64;
      margin-right: 8px;
      font-size: 1.1rem;
    }

    .input-wrapper input {
      border: none;
      background: transparent;
      width: 100%;
      padding: 16px 0;
      font-size: 1.2rem;
      font-weight: 600;
      color: #0a2540;
      outline: none;
    }

    .input-wrapper input::placeholder {
      font-weight: 400;
      color: #9bb0c2;
    }

    .result-box {
      background: #e8f3f0;
      border-radius: 20px;
      padding: 18px 20px;
      margin: 28px 0 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .result-box .label {
      font-weight: 500;
      color: #1f4a3a;
    }

    .result-box .value {
      font-weight: 800;
      font-size: 1.8rem;
      color: #1a7f64;
    }

    .btn-primary {
      background: #1a7f64;
      border: none;
      color: white;
      width: 100%;
      padding: 18px;
      border-radius: 60px;
      font-weight: 700;
      font-size: 1.2rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      cursor: pointer;
      transition: background 0.2s, transform 0.1s;
      box-shadow: 0 12px 20px -10px rgba(26, 127, 100, 0.5);
    }

    .btn-primary:hover {
      background: #0e5e4a;
    }

    .btn-primary:active {
      transform: scale(0.98);
    }

    .disclaimer {
      text-align: center;
      font-size: 0.8rem;
      color: #7a8f9e;
      margin-top: 16px;
    }

    /* vantagens */
    .section-title {
      font-size: 2.2rem;
      font-weight: 800;
      text-align: center;
      margin: 64px 0 16px;
      letter-spacing: -0.5px;
    }

    .section-sub {
      text-align: center;
      color: #3f5e78;
      max-width: 600px;
      margin: 0 auto 48px;
      font-size: 1.15rem;
    }

    .cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 28px;
      margin-bottom: 20px;
    }

    .card {
      background: white;
      border-radius: 28px;
      padding: 32px 24px;
      box-shadow: 0 10px 25px -8px rgba(0, 30, 20, 0.06);
      transition: 0.2s;
      border: 1px solid #e3eef7;
    }

    .card:hover {
      transform: translateY(-6px);
      border-color: #b7d9cf;
      box-shadow: 0 25px 30px -12px rgba(26, 127, 100, 0.2);
    }

    .card i {
      font-size: 2.4rem;
      color: #1a7f64;
      margin-bottom: 24px;
      background: #e8f3f0;
      padding: 12px;
      border-radius: 18px;
    }

    .card h3 {
      font-size: 1.4rem;
      font-weight: 700;
      margin-bottom: 12px;
    }

    .card p {
      color: #4e6b82;
    }

    /* footer */
    .footer {
      background: #0a2540;
      color: #cddbe8;
      padding: 48px 0 24px;
      margin-top: 40px;
    }

    .footer-content {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 40px;
      margin-bottom: 40px;
    }

    .footer-logo {
      font-size: 1.8rem;
      font-weight: 700;
      color: white;
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 16px;
    }

    .footer-logo i {
      color: #2a9d7e;
    }

    .footer-logo .highlight {
      color: #2a9d7e;
    }

    .footer p {
      max-width: 300px;
      font-size: 0.95rem;
      color: #a9c0d4;
    }

    .footer-links h4 {
      color: white;
      margin-bottom: 16px;
      font-size: 1.1rem;
    }

    .footer-links a {
      display: block;
      color: #b8cee0;
      text-decoration: none;
      margin-bottom: 10px;
      font-size: 0.95rem;
      transition: color 0.2s;
    }

    .footer-links a:hover {
      color: #2a9d7e;
    }

    .footer-bottom {
      border-top: 1px solid #24445f;
      padding-top: 24px;
      font-size: 0.9rem;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 12px;
      color: #a1b8cc;
    }

    /* responsivo */
    @media (max-width: 768px) {
      .hero-text h1 {
        font-size: 2.2rem;
      }
      .header-content {
        flex-direction: column;
        align-items: flex-start;
      }
      .nav-links {
        gap: 20px;
        flex-wrap: wrap;
      }
      .hero-card {
        padding: 24px;
      }
      .result-box .value {
        font-size: 1.5rem;
      }
    }

    @media (max-width: 480px) {
      .hero-text h1 {
        font-size: 1.9rem;
      }
      .hero-card {
        padding: 20px;
      }
      .btn-primary {
        font-size: 1rem;
        padding: 16px;
      }
    }
  </style>
</head>
<body>
  <!-- Header -->
  <header class="header">
    <div class="container header-content">
      <div class="logo">
        <i class="fas fa-bolt"></i>
        <span>e<span class="highlight">-Mola</span></span>
      </div>
      <nav class="nav-links">
        <a href="#">Início</a>
        <a href="#">Como funciona</a>
        <a href="#">Taxas</a>
        <a href="#">Ajuda</a>
      </nav>
      <button class="btn-outline"><i class="fas fa-user-circle" style="margin-right: 6px;"></i> Entrar</button>
    </div>
  </header>

  <!-- Main -->
  <main class="main">
    <div class="container">
      <!-- Hero / Simulação -->
      <div class="hero">
        <div class="hero-text">
          <h1>Crédito rápido com a <span>e-Mola</span></h1>
          <p>Simule e contrate seu empréstimo 100% digital, sem burocracia e com as melhores taxas do mercado.</p>
          <div class="trust-badge">
            <i class="fas fa-shield-alt"></i>
            <span>Seguro, transparente e regulamentado</span>
          </div>
        </div>

        <!-- Card de simulação -->
        <div class="hero-card">
          <h2>Simule seu empréstimo</h2>
          <div class="sub">Preencha o valor desejado</div>

          <div class="simulacao-group">
            <label for="valorEmprestimo">Valor do empréstimo (R$)</label>
            <div class="input-wrapper">
              <span>R$</span>
              <input type="number" id="valorEmprestimo" value="5000" min="500" max="50000" step="100" placeholder="5.000">
            </div>
          </div>

          <div class="result-box">
            <span class="label">Parcela estimada</span>
            <span class="value" id="parcelaValor">R$ 480,00</span>
          </div>

          <button class="btn-primary" id="btnSolicitar">
            <i class="fas fa-hand-holding-usd"></i> Solicitar empréstimo
          </button>
          <div class="disclaimer">
            <i class="fas fa-lock"></i> Seus dados estão protegidos
          </div>
        </div>
      </div>

      <!-- Vantagens -->
      <h2 class="section-title">Por que escolher a e-Mola?</h2>
      <p class="section-sub">Milhares de clientes já realizaram seus sonhos com a gente. Veja como é simples.</p>

      <div class="cards-grid">
        <div class="card">
          <i class="fas fa-rocket"></i>
          <h3>Rápido e fácil</h3>
          <p>Análise em minutos e dinheiro na conta em até 24h úteis.</p>
        </div>
        <div class="card">
          <i class="fas fa-chart-line"></i>
          <h3>Taxas justas</h3>
          <p>Juros competitivos e transparência total nas parcelas.</p>
        </div>
        <div class="card">
          <i class="fas fa-mobile-alt"></i>
          <h3>100% digital</h3>
          <p>Todo o processo pelo celular ou computador, sem filas.</p>
        </div>
        <div class="card">
          <i class="fas fa-headset"></i>
          <h3>Suporte humano</h3>
          <p>Atendimento por chat, e-mail e telefone quando precisar.</p>
        </div>
      </div>

      <!-- Chamada extra -->
      <div style="background: linear-gradient(135deg, #e8f3f0, #d4ebe4); border-radius: 48px; padding: 48px 40px; margin-top: 64px; text-align: center;">
        <h3 style="font-size: 1.9rem; font-weight: 800; margin-bottom: 12px;">Pronto para começar?</h3>
        <p style="font-size: 1.15rem; color: #1e4a3b; margin-bottom: 24px;">Simule agora e descubra as melhores condições para você.</p>
        <button class="btn-primary" style="max-width: 300px; margin: 0 auto;" onclick="document.getElementById('valorEmprestimo').focus()">
          <i class="fas fa-calculator"></i> Fazer simulação
        </button>
      </div>
    </div>
  </main>

  <!-- Footer -->
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div>
          <div class="footer-logo">
            <i class="fas fa-bolt"></i>
            <span>e<span class="highlight">-Mola</span></span>
          </div>
          <p>Crédito consciente e acessível para realizar seus projetos. Confiança e tecnologia a seu favor.</p>
        </div>
        <div class="footer-links">
          <h4>Institucional</h4>
          <a href="#">Sobre nós</a>
          <a href="#">Taxas e tarifas</a>
          <a href="#">Política de privacidade</a>
          <a href="#">Termos de uso</a>
        </div>
        <div class="footer-links">
          <h4>Ajuda</h4>
          <a href="#">Central de ajuda</a>
          <a href="#">Fale conosco</a>
          <a href="#">Segurança</a>
          <a href="#">Ouvidoria</a>
        </div>
        <div class="footer-links">
          <h4>Legal</h4>
          <a href="#">Regulamentação</a>
          <a href="#">Prevenção a fraudes</a>
          <a href="#">Relatórios</a>
        </div>
      </div>
      <div class="footer-bottom">
        <span>© 2025 e-Mola Empréstimos S.A. — CNPJ 12.345.678/0001-90</span>
        <span><i class="fas fa-lock"></i> Ambiente seguro</span>
      </div>
    </div>
  </footer>

  <!-- Script de simulação -->
  <script>
    (function() {
      const inputValor = document.getElementById('valorEmprestimo');
      const parcelaDisplay = document.getElementById('parcelaValor');
      const btnSolicitar = document.getElementById('btnSolicitar');

      // Taxa de juros mensal fixa para demonstração (1.9% ao mês) + parcelas fixas em 12x (exemplo)
      // Para simulação mais realista, pode-se implementar diferentes prazos, mas mantemos simples.
      const TAXA_MENSAL = 0.019; // 1,9% a.m.
      const NUM_PARCELAS = 12;

      function calcularParcela(valor) {
        if (!valor || valor < 500) return 0;
        if (valor > 50000) valor = 50000; // limite máximo
        
        // Cálculo de parcela com juros compostos: PMT = valor * (taxa * (1+taxa)^n) / ((1+taxa)^n - 1)
        const i = TAXA_MENSAL;
        const n = NUM_PARCELAS;
        const fator = (i * Math.pow(1 + i, n)) / (Math.pow(1 + i, n) - 1);
        const parcela = valor * fator;
        return parcela;
      }

      function atualizarSimulacao() {
        let valor = parseFloat(inputValor.value);
        if (isNaN(valor)) valor = 0;

        // limita o valor para não estourar
        if (valor < 500) valor = 500;
        if (valor > 50000) valor = 50000;

        // Atualiza o input visualmente se estiver fora dos limites
        if (parseFloat(inputValor.value) !== valor) {
          inputValor.value = valor;
        }

        const parcela = calcularParcela(valor);
        // Formata para Real brasileiro
        const formatado = parcela.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
        parcelaDisplay.textContent = formatado;
      }

      // Eventos
      inputValor.addEventListener('input', atualizarSimulacao);
      inputValor.addEventListener('change', atualizarSimulacao);

      // Botão solicitar (simula uma ação)
      btnSolicitar.addEventListener('click', function(e) {
        e.preventDefault();
        const valor = parseFloat(inputValor.value) || 0;
        const parcela = calcularParcela(valor);
        
        if (valor < 500) {
          alert('O valor mínimo para empréstimo é R$ 500,00.');
          inputValor.focus();
          return;
        }
        if (valor > 50000) {
          alert('O valor máximo para empréstimo é R$ 50.000,00.');
          inputValor.focus();
          return;
        }

        // Simulação de solicitação
        alert(`✅ Solicitação enviada!\n\nValor: R$ ${valor.toFixed(2)}\nParcela estimada (12x): ${parcela.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' })}\n\nEm breve nossa equipe entrará em contato.`);
      });

      // Inicializa com o valor do input (5000)
      atualizarSimulacao();
    })();
  </script>
  <!-- Pequeno ajuste para o botão "Fazer simulação" focar no input -->
  <script>
    // Já está implementado via onclick no botão, mas garantimos que o campo seja visível.
    // Nenhuma ação extra necessária.
  </script>
</body>
</html>
