<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8" />
  <title>Gran Canária – Roteiro Premium</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --bg: #050816;
      --card: #0f172a;
      --accent: #22c55e;
      --accent-soft: rgba(34, 197, 94, 0.15);
      --text: #e5e7eb;
      --muted: #9ca3af;
      --border: #1f2937;
      --danger: #f97373;
      --radius: 14px;
      --shadow: 0 18px 45px rgba(0, 0, 0, 0.55);
      --transition: 0.25s ease;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "SF Pro Text",
        "Segoe UI", sans-serif;
      background: radial-gradient(circle at top, #1f2937 0, #020617 55%);
      color: var(--text);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      padding: 32px 12px;
    }

    .app {
      width: 100%;
      max-width: 980px;
      background: radial-gradient(circle at top left, #111827 0, #020617 55%);
      border-radius: 28px;
      border: 1px solid rgba(148, 163, 184, 0.18);
      box-shadow: var(--shadow);
      overflow: hidden;
      position: relative;
    }

    .app-header {
      padding: 22px 26px 18px;
      border-bottom: 1px solid rgba(148, 163, 184, 0.18);
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      background: radial-gradient(circle at top left, #22c55e22 0, transparent 55%);
    }

    .app-title {
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .app-title h1 {
      font-size: 1.25rem;
      font-weight: 650;
      letter-spacing: 0.02em;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .app-title h1 span.emoji {
      font-size: 1.4rem;
    }

    .app-title p {
      font-size: 0.85rem;
      color: var(--muted);
    }

    .pill {
      padding: 6px 12px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.4);
      font-size: 0.75rem;
      color: var(--muted);
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: rgba(15, 23, 42, 0.8);
      backdrop-filter: blur(10px);
    }

    .pill-dot {
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: #22c55e;
      box-shadow: 0 0 0 4px rgba(34, 197, 94, 0.25);
    }

    .tabs {
      display: flex;
      justify-content: space-between;
      gap: 4px;
      padding: 8px 10px 10px;
      border-bottom: 1px solid rgba(148, 163, 184, 0.18);
      background: linear-gradient(to right, #020617, #020617dd);
    }

    .tab {
      flex: 1;
      text-align: center;
      padding: 8px 6px;
      border-radius: 999px;
      font-size: 0.8rem;
      color: var(--muted);
      cursor: pointer;
      border: 1px solid transparent;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      transition: var(--transition);
      user-select: none;
    }

    .tab span.icon {
      font-size: 1rem;
    }

    .tab.active {
      color: #e5fbe9;
      border-color: rgba(34, 197, 94, 0.6);
      background: radial-gradient(circle at top, #22c55e33 0, #020617 60%);
      box-shadow: 0 0 0 1px rgba(34, 197, 94, 0.35);
    }

    .tab:hover:not(.active) {
      background: rgba(15, 23, 42, 0.9);
      border-color: rgba(148, 163, 184, 0.4);
    }

    .content {
      padding: 18px 20px 20px;
      max-height: 70vh;
      overflow-y: auto;
      scroll-behavior: smooth;
    }

    .section {
      margin-bottom: 18px;
      padding: 14px 14px 12px;
      border-radius: var(--radius);
      background: radial-gradient(circle at top left, #111827 0, #020617 70%);
      border: 1px solid rgba(31, 41, 55, 0.9);
    }

    .section-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 10px;
      gap: 8px;
    }

    .section-title {
      font-size: 0.95rem;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .section-title span.icon {
      font-size: 1.1rem;
    }

    .section-sub {
      font-size: 0.78rem;
      color: var(--muted);
    }

    .badge {
      font-size: 0.7rem;
      padding: 4px 8px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.4);
      color: var(--muted);
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 10px;
      margin-top: 6px;
    }

    .card {
      padding: 10px 10px 9px;
      border-radius: 12px;
      border: 1px solid rgba(31, 41, 55, 0.9);
      background: radial-gradient(circle at top left, #020617 0, #020617 60%);
      font-size: 0.8rem;
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .card-title {
      font-weight: 550;
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 0.82rem;
    }

    .card-title span.icon {
      font-size: 1rem;
    }

    .card-meta {
      font-size: 0.72rem;
      color: var(--muted);
    }

    .tag-row {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 4px;
    }

    .tag {
      font-size: 0.7rem;
      padding: 3px 7px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.4);
      color: var(--muted);
    }

    .tag.accent {
      border-color: rgba(34, 197, 94, 0.7);
      color: #bbf7d0;
      background: rgba(34, 197, 94, 0.08);
    }

    .list {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 4px;
      font-size: 0.8rem;
      margin-top: 4px;
    }

    .list li::before {
      content: "•";
      color: var(--accent);
      margin-right: 6px;
    }

    .checklist {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 4px;
      font-size: 0.8rem;
      margin-top: 4px;
    }

    .checklist li {
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .check {
      width: 13px;
      height: 13px;
      border-radius: 4px;
      border: 1px solid rgba(148, 163, 184, 0.7);
      flex-shrink: 0;
    }

    .check.done {
      background: var(--accent);
      border-color: var(--accent);
      box-shadow: 0 0 0 2px rgba(34, 197, 94, 0.35);
    }

    .day-label {
      font-size: 0.78rem;
      font-weight: 600;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.06em;
      margin-bottom: 4px;
    }

    .pill-small {
      font-size: 0.7rem;
      padding: 3px 7px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.4);
      color: var(--muted);
      display: inline-flex;
      align-items: center;
      gap: 4px;
    }

    .link-row {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 6px;
    }

    .link-chip {
      font-size: 0.72rem;
      padding: 4px 8px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.4);
      color: var(--muted);
      display: inline-flex;
      align-items: center;
      gap: 6px;
      cursor: pointer;
      text-decoration: none;
    }

    .link-chip span.icon {
      font-size: 0.9rem;
    }

    .link-chip:hover {
      border-color: rgba(34, 197, 94, 0.7);
      color: #bbf7d0;
      background: rgba(34, 197, 94, 0.08);
    }

    .muted {
      color: var(--muted);
      font-size: 0.78rem;
    }

    @media (max-width: 720px) {
      .app {
        border-radius: 22px;
      }
      .app-header {
        padding: 18px 16px 14px;
      }
      .tabs {
        padding: 8px 8px 9px;
      }
      .content {
        padding: 14px 14px 16px;
      }
    }
  </style>
</head>
<body>
  <div class="app">
    <header class="app-header">
      <div class="app-title">
        <h1><span class="emoji">🌴</span> Gran Canária – Roteiro Premium</h1>
        <p>Base: Abora Buenaventura · Playa del Inglés · 7 dias all‑inclusive</p>
      </div>
      <div class="pill">
        <span class="pill-dot"></span>
        Roteiro automático · Versão HTML
      </div>
    </header>

    <nav class="tabs">
      <div class="tab active" data-tab="home">
        <span class="icon">🏠</span><span>Home</span>
      </div>
      <div class="tab" data-tab="roteiro">
        <span class="icon">📅</span><span>Roteiro</span>
      </div>
      <div class="tab" data-tab="locais">
        <span class="icon">🗺️</span><span>Locais</span>
      </div>
      <div class="tab" data-tab="planner">
        <span class="icon">🧳</span><span>Planner</span>
      </div>
      <div class="tab" data-tab="dicas">
        <span class="icon">ℹ️</span><span>Dicas</span>
      </div>
    </nav>

    <main class="content">
      <!-- HOME -->
      <section class="tab-panel" id="tab-home">
        <div class="section">
          <div class="section-header">
            <div>
              <div class="section-title">
                <span class="icon">✨</span>
                <span>Resumo da viagem</span>
              </div>
              <p class="section-sub">
                Gran Canária em 7 dias: relax, natureza, praias, compras e parques temáticos.
              </p>
            </div>
            <span class="badge">Modo: Premium · All‑inclusive</span>
          </div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🏨</span>
                <span>Base da viagem</span>
              </div>
              <p class="card-meta">
                Hotel Abora Buenaventura · Playa del Inglés · perto das dunas, Yumbo e praia.
              </p>
              <div class="tag-row">
                <span class="tag accent">All‑inclusive</span>
                <span class="tag">Piscinas</span>
                <span class="tag">Animação noturna</span>
              </div>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🌅</span>
                <span>Destaques principais</span>
              </div>
              <ul class="list">
                <li>Dunas de Maspalomas ao pôr do sol</li>
                <li>Pico de las Nieves & Roque Nublo</li>
                <li>Puerto de Mogán & Anfi del Mar</li>
                <li>Las Palmas, Triana & Las Canteras</li>
              </ul>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🧭</span>
                <span>Navegação rápida</span>
              </div>
              <div class="link-row">
                <a class="link-chip" data-jump="roteiro">
                  <span class="icon">📅</span><span>Ir para Roteiro</span>
                </a>
                <a class="link-chip" data-jump="locais">
                  <span class="icon">🗺️</span><span>Ver Locais</span>
                </a>
                <a class="link-chip" data-jump="planner">
                  <span class="icon">🧳</span><span>Abrir Planner</span>
                </a>
                <a class="link-chip" data-jump="dicas">
                  <span class="icon">ℹ️</span><span>Dicas rápidas</span>
                </a>
              </div>
            </div>
          </div>
        </div>

        <div class="section">
          <div class="section-header">
            <div class="section-title">
              <span class="icon">🔗</span>
              <span>Link simbólico do “app”</span>
            </div>
          </div>
          <p class="muted">
            Podes usar este URL como referência em documentos, Notion ou Figma:
          </p>
          <div class="tag-row" style="margin-top:6px;">
            <span class="tag accent">https://gran-canaria-premium.app</span>
          </div>
        </div>
      </section>

      <!-- ROTEIRO -->
      <section class="tab-panel" id="tab-roteiro" style="display:none;">
        <div class="section">
          <div class="section-header">
            <div>
              <div class="section-title">
                <span class="icon">📅</span>
                <span>Roteiro Premium – 7 Dias</span>
              </div>
              <p class="section-sub">
                Estrutura automática do teu roteiro, dia a dia, com foco em conforto e simplicidade.
              </p>
            </div>
            <span class="badge">Base: Playa del Inglés</span>
          </div>
        </div>

        <!-- Dia 1 -->
        <div class="section">
          <div class="day-label">Dia 1 · Chegada & Ambientação</div>
          <div class="card">
            <div class="card-title">
              <span class="icon">🛬</span>
              <span>Chegada & primeira impressão</span>
            </div>
            <ul class="list">
              <li>Aeroporto → Hotel Abora Buenaventura (~30 min de transfer)</li>
              <li>Check‑in e tempo para respirar</li>
              <li>Primeiro mergulho: Praia de Playa del Inglés (a ~500 m)</li>
            </ul>
            <div class="tag-row">
              <span class="tag accent">Jantar no hotel (all‑inclusive)</span>
              <span class="tag">Passeio opcional no Yumbo Centrum</span>
            </div>
          </div>
        </div>

        <!-- Dia 2 -->
        <div class="section">
          <div class="day-label">Dia 2 · Relax no Hotel</div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🌞</span>
                <span>Manhã</span>
              </div>
              <ul class="list">
                <li>Pequeno‑almoço no hotel</li>
                <li>Piscina principal ou infantil</li>
              </ul>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🌴</span>
                <span>Tarde & fim de tarde</span>
              </div>
              <ul class="list">
                <li>Praia de Playa del Inglés ou espreguiçadeiras</li>
                <li>Almoço no hotel</li>
                <li>Bar ou lounge para café / cocktails</li>
              </ul>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🌙</span>
                <span>Noite</span>
              </div>
              <ul class="list">
                <li>Jantar no hotel</li>
                <li>Show ou entretenimento noturno do hotel</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Dia 3 -->
        <div class="section">
          <div class="day-label">Dia 3 · Montanhas & Natureza</div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🏔️</span>
                <span>Pico de las Nieves</span>
              </div>
              <p class="card-meta">
                ~1h de carro · ponto mais alto da ilha, vista para o Teide e trilha leve.
              </p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">📸</span>
                <span>Barranco de las Vacas</span>
              </div>
              <p class="card-meta">
                Mini “Antelope Canyon” canário · spot perfeito para fotos.
              </p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🏘️</span>
                <span>Tejeda & Roque Nublo</span>
              </div>
              <ul class="list">
                <li>Tejeda: vila de montanha charmosa</li>
                <li>Roque Nublo: trilha curta + pôr do sol incrível</li>
                <li>Regresso para jantar no hotel</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Dia 4 -->
        <div class="section">
          <div class="day-label">Dia 4 · Sul & Dunas de Maspalomas</div>
          <div class="card">
            <div class="card-title">
              <span class="icon">🏖️</span>
              <span>Dia dividido entre piscina e dunas</span>
            </div>
            <ul class="list">
              <li>Manhã de piscina e descanso no hotel</li>
              <li>Tarde nas Dunas de Maspalomas (~15 min de carro)</li>
              <li>Melhor horário: pôr do sol nas dunas</li>
            </ul>
            <div class="tag-row">
              <span class="tag accent">Jantar no hotel</span>
              <span class="tag">Yumbo Centrum opcional à noite</span>
            </div>
          </div>
        </div>

        <!-- Dia 5 -->
        <div class="section">
          <div class="day-label">Dia 5 · Compras & Puerto de Mogán</div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🛍️</span>
                <span>Manhã – Compras</span>
              </div>
              <p class="card-meta">
                Mogan Mall ou Las Terrazas Outlet (40–50 min de carro) · shoppings modernos e outlets.
              </p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🌊</span>
                <span>Tarde – Puerto de Mogán</span>
              </div>
              <p class="card-meta">
                “Veneza das Canárias” · vila romântica e super fotogénica.
              </p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🍽️</span>
                <span>Refeições</span>
              </div>
              <ul class="list">
                <li>Almoço no hotel (antes ou depois do passeio)</li>
                <li>Jantar no hotel ao regressar</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Dia 6 -->
        <div class="section">
          <div class="day-label">Dia 6 · Diversão & Parques</div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🐬</span>
                <span>Palmitos Park</span>
              </div>
              <p class="card-meta">
                Zoo + jardim botânico + espetáculo de golfinhos · ~35 min do hotel.
              </p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">💦</span>
                <span>Aqualand Maspalomas</span>
              </div>
              <p class="card-meta">
                Parque aquático com escorregas e áreas para todas as idades.
              </p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🐠</span>
                <span>Poema del Mar</span>
              </div>
              <p class="card-meta">
                Aquário futurista em Las Palmas · tanques gigantes e túneis subaquáticos.
              </p>
            </div>
          </div>
          <p class="card-meta" style="margin-top:6px;">
            Almoço no hotel (se der tempo) ou lanche preparado · jantar no hotel ao final do dia.
          </p>
        </div>

        <!-- Dia 7 -->
        <div class="section">
          <div class="day-label">Dia 7 · Praias & Despedida</div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🏝️</span>
                <span>Anfi del Mar</span>
              </div>
              <p class="card-meta">
                Areia branca estilo Caraíbas, água calma, ilha em forma de coração.
              </p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🛍️</span>
                <span>Rua de Triana / Relax</span>
              </div>
              <p class="card-meta">
                Últimas compras em Las Palmas ou descanso final no hotel.
              </p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">✈️</span>
                <span>Regresso</span>
              </div>
              <ul class="list">
                <li>Almoço no hotel</li>
                <li>Devolução do carro</li>
                <li>Transfer para o aeroporto</li>
                <li>Jantar no hotel se o horário permitir</li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- LOCAIS -->
      <section class="tab-panel" id="tab-locais" style="display:none;">
        <div class="section">
          <div class="section-header">
            <div>
              <div class="section-title">
                <span class="icon">🗺️</span>
                <span>Locais-chave da viagem</span>
              </div>
              <p class="section-sub">
                Natureza, vilas, praias e compras organizados por categoria.
              </p>
            </div>
            <span class="badge">Explorar por tema</span>
          </div>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">🌋</span>
            <span>Natureza & Paisagens</span>
          </div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🏔️</span>
                <span>Pico de las Nieves</span>
              </div>
              <p class="card-meta">Ponto mais alto da ilha, vistas amplas e clima mais fresco.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🪨</span>
                <span>Roque Nublo</span>
              </div>
              <p class="card-meta">Símbolo sagrado da ilha, trilha curta e pôr do sol épico.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">📸</span>
                <span>Barranco de las Vacas</span>
              </div>
              <p class="card-meta">Formações rochosas que lembram o Antelope Canyon.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🏞️</span>
                <span>Caldera de Bandama</span>
              </div>
              <p class="card-meta">Cratera vulcânica gigante com vistas sobre Las Palmas.</p>
            </div>
          </div>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">🏘️</span>
            <span>Vilas & Cidades</span>
          </div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🌉</span>
                <span>Puerto de Mogán</span>
              </div>
              <p class="card-meta">“Veneza das Canárias” · a vila mais fotogénica da ilha.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🏡</span>
                <span>Teror</span>
              </div>
              <p class="card-meta">Varandas típicas e essência tradicional canária.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">⛰️</span>
                <span>Tejeda</span>
              </div>
              <p class="card-meta">Vila de montanha, considerada das mais bonitas de Espanha.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🏙️</span>
                <span>Las Palmas (Vegueta)</span>
              </div>
              <p class="card-meta">Centro histórico, arquitetura colonial e ambiente urbano.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">⚓</span>
                <span>Agaete / Puerto de las Nieves</span>
              </div>
              <p class="card-meta">Casas brancas, ambiente piscatório e piscinas naturais.</p>
            </div>
          </div>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">🏖️</span>
            <span>Praias & Piscinas naturais</span>
          </div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🏝️</span>
                <span>Playa del Inglés</span>
              </div>
              <p class="card-meta">Praia extensa, junto ao teu hotel, com muita vida e acessos fáceis.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">💙</span>
                <span>Anfi del Mar</span>
              </div>
              <p class="card-meta">Areia branca importada, água calma e ilha em forma de coração.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🌊</span>
                <span>Las Canteras</span>
              </div>
              <p class="card-meta">Praia urbana em Las Palmas, com recife natural protetor.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🪨</span>
                <span>Las Salinas (Agaete)</span>
              </div>
              <p class="card-meta">Piscinas naturais de água salgada no norte da ilha.</p>
            </div>
          </div>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">🛍️</span>
            <span>Compras & Shoppings</span>
          </div>
          <div class="grid">
            <div class="card">
              <div class="card-title">
                <span class="icon">🏬</span>
                <span>Mogan Mall</span>
              </div>
              <p class="card-meta">Shopping moderno ao ar livre em Puerto Rico, com espetáculo de fontes.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🛒</span>
                <span>CC Alisios</span>
              </div>
              <p class="card-meta">Grande centro comercial em Las Palmas, com espaços abertos.</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🏷️</span>
                <span>Las Terrazas Outlet</span>
              </div>
              <p class="card-meta">Outlets com grandes marcas e bons descontos (Jinámar).</p>
            </div>
            <div class="card">
              <div class="card-title">
                <span class="icon">🛣️</span>
                <span>Rua de Triana</span>
              </div>
              <p class="card-meta">Rua comercial histórica em Las Palmas, ótima para passear e comprar.</p>
            </div>
          </div>
        </div>
      </section>

      <!-- PLANNER -->
      <section class="tab-panel" id="tab-planner" style="display:none;">
        <div class="section">
          <div class="section-header">
            <div>
              <div class="section-title">
                <span class="icon">🧳</span>
                <span>Planner diário</span>
              </div>
              <p class="section-sub">
                Usa este checklist como se fosse uma app de tarefas para cada dia da viagem.
              </p>
            </div>
            <span class="badge">Modo viagem</span>
          </div>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">✔️</span>
            <span>Checklist geral (todos os dias)</span>
          </div>
          <ul class="checklist">
            <li><span class="check"></span><span>Ver previsão do tempo (sul / norte)</span></li>
            <li><span class="check"></span><span>Levar água engarrafada</span></li>
            <li><span class="check"></span><span>Protetor solar e óculos de sol</span></li>
            <li><span class="check"></span><span>Carregar telemóvel e powerbank</span></li>
            <li><span class="check"></span><span>Confirmar rota do dia e combustível</span></li>
          </ul>
        </div>

        <!-- Dia a dia -->
        <div class="section">
          <div class="day-label">Dia 1 · Chegada & Ambientação</div>
          <ul class="checklist">
            <li><span class="check"></span><span>Transfer do aeroporto para o hotel</span></li>
            <li><span class="check"></span><span>Check‑in no Abora Buenaventura</span></li>
            <li><span class="check"></span><span>Primeira ida à Praia de Playa del Inglés</span></li>
            <li><span class="check"></span><span>Jantar no hotel</span></li>
            <li><span class="check"></span><span>Passeio no Yumbo Centrum (opcional)</span></li>
          </ul>
        </div>

        <div class="section">
          <div class="day-label">Dia 2 · Relax no Hotel</div>
          <ul class="checklist">
            <li><span class="check"></span><span>Pequeno‑almoço no hotel</span></li>
            <li><span class="check"></span><span>Tempo de piscina</span></li>
            <li><span class="check"></span><span>Praia ou descanso nas espreguiçadeiras</span></li>
            <li><span class="check"></span><span>Almoço no hotel</span></li>
            <li><span class="check"></span><span>Bar / lounge ao fim da tarde</span></li>
            <li><span class="check"></span><span>Jantar + entretenimento noturno</span></li>
          </ul>
        </div>

        <div class="section">
          <div class="day-label">Dia 3 · Montanhas & Natureza</div>
          <ul class="checklist">
            <li><span class="check"></span><span>Subida ao Pico de las Nieves</span></li>
            <li><span class="check"></span><span>Paragem no Barranco de las Vacas</span></li>
            <li><span class="check"></span><span>Visita à vila de Tejeda</span></li>
            <li><span class="check"></span><span>Trilha até o Roque Nublo</span></li>
            <li><span class="check"></span><span>Regresso e jantar no hotel</span></li>
          </ul>
        </div>

        <div class="section">
          <div class="day-label">Dia 4 · Dunas & Sul</div>
          <ul class="checklist">
            <li><span class="check"></span><span>Manhã de piscina no hotel</span></li>
            <li><span class="check"></span><span>Visita às Dunas de Maspalomas</span></li>
            <li><span class="check"></span><span>Ver o pôr do sol nas dunas</span></li>
            <li><span class="check"></span><span>Jantar no hotel</span></li>
            <li><span class="check"></span><span>Yumbo à noite (opcional)</span></li>
          </ul>
        </div>

        <div class="section">
          <div class="day-label">Dia 5 · Compras & Mogán</div>
          <ul class="checklist">
            <li><span class="check"></span><span>Ir ao Mogan Mall ou Las Terrazas Outlet</span></li>
            <li><span class="check"></span><span>Passeio em Puerto de Mogán</span></li>
            <li><span class="check"></span><span>Almoço no hotel (antes ou depois)</span></li>
            <li><span class="check"></span><span>Jantar no hotel</span></li>
          </ul>
        </div>

        <div class="section">
          <div class="day-label">Dia 6 · Parques Temáticos</div>
          <ul class="checklist">
            <li><span class="check"></span><span>Escolher: Palmitos Park / Aqualand / Poema del Mar</span></li>
            <li><span class="check"></span><span>Preparar lanche ou alinhar almoço</span></li>
            <li><span class="check"></span><span>Jantar no hotel</span></li>
          </ul>
        </div>

        <div class="section">
          <div class="day-label">Dia 7 · Despedida</div>
          <ul class="checklist">
            <li><span class="check"></span><span>Manhã em Anfi del Mar</span></li>
            <li><span class="check"></span><span>Últimas compras na Rua de Triana ou descanso</span></li>
            <li><span class="check"></span><span>Devolver o carro</span></li>
            <li><span class="check"></span><span>Transfer para o aeroporto</span></li>
          </ul>
        </div>
      </section>

      <!-- DICAS -->
      <section class="tab-panel" id="tab-dicas" style="display:none;">
        <div class="section">
          <div class="section-header">
            <div>
              <div class="section-title">
                <span class="icon">ℹ️</span>
                <span>Dicas essenciais</span>
              </div>
              <p class="section-sub">
                Pequenos detalhes que fazem a viagem correr muito melhor.
              </p>
            </div>
            <span class="badge">Qualidade de vida em viagem</span>
          </div>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">🚗</span>
            <span>Transporte</span>
          </div>
          <ul class="list">
            <li>Carro alugado é praticamente essencial para explorar a ilha com liberdade.</li>
            <li>Cicar é uma opção local muito recomendada.</li>
          </ul>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">🌤️</span>
            <span>Clima</span>
          </div>
          <ul class="list">
            <li>Sul da ilha: mais sol, ideal para praia e piscina.</li>
            <li>Norte: mais nuvens baixas, a famosa “Panza de Burro”.</li>
          </ul>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">💧</span>
            <span>Água & alimentação</span>
          </div>
          <ul class="list">
            <li>Prefere sempre água engarrafada (a da torneira sabe a cloro).</li>
            <li>Aproveita bem o all‑inclusive do hotel para controlar gastos.</li>
          </ul>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">👜</span>
            <span>Mercado de rua – “Manteros”</span>
          </div>
          <p class="card-meta">
            Zona: Playa del Inglés (Paseo Costa Canaria, acessos ao Yumbo/Kasbah, Anexo II, Águila Roja).
          </p>
          <ul class="list" style="margin-top:4px;">
            <li>Horário: final da tarde e noite (a partir das 19h/20h).</li>
            <li>Produtos: réplicas de malas, sapatilhas, óculos.</li>
            <li>Regras de ouro: regatear sempre, pagar em dinheiro vivo, atenção à polícia.</li>
          </ul>
        </div>

        <div class="section">
          <div class="section-title">
            <span class="icon">🧐</span>
            <span>Curiosidades & segredos</span>
          </div>
          <ul class="list">
            <li>Cachorros quentes gigantes no Parque de Santa Catalina (Las Palmas) – tradição local.</li>
            <li>Único café da Europa cultivado no Valle de Agaete (Finca La Laja).</li>
            <li>Filmes como Fast & Furious 6 tiveram cenas gravadas em Gran Canária.</li>
          </ul>
        </div>
      </section>
    </main>
  </div>

  <script>
    const tabs = document.querySelectorAll(".tab");
    const panels = {
      home: document.getElementById("tab-home"),
      roteiro: document.getElementById("tab-roteiro"),
      locais: document.getElementById("tab-locais"),
      planner: document.getElementById("tab-planner"),
      dicas: document.getElementById("tab-dicas"),
    };

    tabs.forEach((tab) => {
      tab.addEventListener("click", () => {
        const target = tab.getAttribute("data-tab");
        tabs.forEach((t) => t.classList.remove("active"));
        tab.classList.add("active");
        Object.keys(panels).forEach((key) => {
          panels[key].style.display = key === target ? "block" : "none";
        });
      });
    });

    document.querySelectorAll("[data-jump]").forEach((el) => {
      el.addEventListener("click", () => {
        const target = el.getAttribute("data-jump");
        const tab = document.querySelector(`.tab[data-tab="${target}"]`);
        if (tab) tab.click();
      });
    });
  </script>
</body>
</html>
