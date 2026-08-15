
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#071a3d">
  <title>FiltroAmb | Checklist</title>

  <style>
    :root {
      --navy: #071a3d;
      --blue: #123d86;
      --blue-light: #2563c7;
      --cyan: #28b8d8;
      --bg: #eef3f8;
      --text: #172033;
      --muted: #64748b;
      --border: #e2e8f0;
      --white: #ffffff;
      --shadow: 0 18px 45px rgba(15, 44, 107, 0.12);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      color: var(--text);
      background:
        radial-gradient(circle at 10% 0%, rgba(40, 184, 216, 0.1), transparent 28%),
        var(--bg);
      font-family: "Segoe UI", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
    }

    button {
      font: inherit;
    }

    .hero {
      position: relative;
      min-height: 315px;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      color: var(--white);
      text-align: center;
      background:
        linear-gradient(115deg, rgba(4, 22, 56, 0.88), rgba(12, 58, 123, 0.62)),
        url("banner-filtroamb.webp") center / cover no-repeat;
    }

    .hero::before {
      content: "";
      position: absolute;
      inset: 0;
      opacity: 0.42;
      background:
        linear-gradient(135deg, rgba(3, 18, 47, 0.32), rgba(40, 184, 216, 0.2)),
        rgba(3, 18, 47, 0.18);
    }

    .hero::after {
      content: "";
      position: absolute;
      right: -10%;
      bottom: -120px;
      left: -10%;
      height: 190px;
      border-radius: 50% 50% 0 0;
      background: var(--bg);
    }

    .hero-content {
      position: relative;
      z-index: 2;
      padding: 40px 20px 70px;
    }

    .brand-mark {
      width: 64px;
      height: 64px;
      display: grid;
      place-items: center;
      margin: 0 auto 18px;
      border: 1px solid rgba(255, 255, 255, 0.3);
      border-radius: 18px;
      color: var(--white);
      font-size: 1.8rem;
      background: rgba(255, 255, 255, 0.12);
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.18);
      backdrop-filter: blur(8px);
    }

    .hero h1 {
      margin-bottom: 4px;
      font-size: clamp(2.3rem, 5vw, 3.8rem);
      font-weight: 800;
      letter-spacing: 0.8px;
      text-shadow: 0 4px 18px rgba(0, 0, 0, 0.3);
    }

    .hero p {
      color: #cfe5ff;
      font-size: 1.15rem;
      font-weight: 500;
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    .fullscreen-btn {
      position: absolute;
      z-index: 4;
      top: 22px;
      right: 24px;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 10px 15px;
      border: 1px solid rgba(255, 255, 255, 0.28);
      border-radius: 10px;
      color: var(--white);
      cursor: pointer;
      background: rgba(255, 255, 255, 0.12);
      backdrop-filter: blur(10px);
      transition: 0.2s ease;
    }

    .fullscreen-btn:hover {
      background: rgba(255, 255, 255, 0.24);
      transform: translateY(-2px);
    }

    .container {
      position: relative;
      z-index: 5;
      max-width: 1080px;
      margin: -55px auto 48px;
      padding: 0 18px;
    }

    .card {
      overflow: hidden;
      border: 1px solid rgba(255, 255, 255, 0.8);
      border-radius: 20px;
      background: var(--white);
      box-shadow: var(--shadow);
    }

    .card-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      padding: 22px 26px;
      border-bottom: 1px solid var(--border);
    }

    .card-header h2 {
      color: var(--navy);
      font-size: 1.15rem;
    }

    .card-header p {
      margin-top: 4px;
      color: var(--muted);
      font-size: 0.88rem;
    }

    .status {
      display: flex;
      align-items: center;
      gap: 7px;
      color: #15803d;
      font-size: 0.82rem;
      font-weight: 600;
    }

    .status::before {
      content: "";
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #22c55e;
      box-shadow: 0 0 0 4px #dcfce7;
    }

    table {
      width: 100%;
      border-collapse: collapse;
    }

    th {
      padding: 15px 22px;
      color: #dbeafe;
      background: var(--navy);
      font-size: 0.78rem;
      font-weight: 700;
      letter-spacing: 0.5px;
      text-align: left;
      text-transform: uppercase;
    }

    td {
      padding: 17px 22px;
      border-bottom: 1px solid #edf1f5;
      font-size: 0.92rem;
    }

    tbody tr {
      transition: background 0.2s ease;
    }

    tbody tr:hover {
      background: #f7fbff;
    }

    tbody tr:last-child td {
      border-bottom: 0;
    }

    .btn-check {
      width: 40px;
      height: 40px;
      display: inline-grid;
      place-items: center;
      border: 0;
      border-radius: 11px;
      color: var(--white);
      cursor: pointer;
      font-size: 1.1rem;
      background: linear-gradient(135deg, var(--blue), var(--blue-light));
      box-shadow: 0 5px 12px rgba(37, 99, 199, 0.24);
      transition: 0.2s ease;
    }

    .btn-check:hover {
      transform: translateY(-2px) scale(1.04);
      box-shadow: 0 8px 18px rgba(37, 99, 199, 0.32);
    }

    .loading {
      padding: 70px 20px;
      color: var(--muted);
      text-align: center;
    }

    .loading::before {
      content: "";
      width: 25px;
      height: 25px;
      display: block;
      margin: 0 auto 14px;
      border: 3px solid #dbeafe;
      border-top-color: var(--blue-light);
      border-radius: 50%;
      animation: spin 0.8s linear infinite;
    }

    @keyframes spin {
      to { transform: rotate(360deg); }
    }

    .modal-overlay {
      position: fixed;
      z-index: 1000;
      inset: 0;
      display: none;
      align-items: center;
      justify-content: center;
      padding: 20px;
      background: rgba(3, 13, 32, 0.72);
      backdrop-filter: blur(5px);
    }

    .modal-overlay.active {
      display: flex;
    }

    .modal {
      width: 100%;
      max-width: 700px;
      max-height: 88vh;
      overflow-y: auto;
      border-radius: 20px;
      background: var(--white);
      box-shadow: 0 25px 70px rgba(0, 0, 0, 0.3);
      animation: slideIn 0.25s ease;
    }

    @keyframes slideIn {
      from { opacity: 0; transform: translateY(25px) scale(0.98); }
      to { opacity: 1; transform: translateY(0) scale(1); }
    }

    .modal-header {
      position: sticky;
      top: 0;
      z-index: 2;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 20px 24px;
      color: var(--white);
      background: var(--navy);
    }

    .modal-header h2 {
      font-size: 1.15rem;
    }

    .close-btn {
      width: 36px;
      height: 36px;
      display: grid;
      place-items: center;
      border: 1px solid rgba(255, 255, 255, 0.2);
      border-radius: 9px;
      color: var(--white);
      cursor: pointer;
      font-size: 1.4rem;
      background: rgba(255, 255, 255, 0.12);
    }

    .modal-body {
      padding: 25px;
    }

    .info-row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-bottom: 24px;
    }

    .info-item {
      padding: 11px 14px;
      border: 1px solid var(--border);
      border-radius: 9px;
      color: var(--muted);
      font-size: 0.86rem;
      background: #f8fafc;
    }

    .info-item strong {
      color: var(--navy);
    }

    .checklist-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
    }

    .check-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      padding: 12px 14px;
      border-left: 4px solid #94a3b8;
      border-radius: 8px;
      color: #334155;
      font-size: 0.86rem;
      background: #f8fafc;
    }

    .check-item.ok { border-left-color: #22c55e; }
    .check-item.pendencia { border-left-color: #f59e0b; }
    .check-item.nao { border-left-color: #ef4444; }
    .check-item.na { border-left-color: #94a3b8; }

    .badge {
      padding: 4px 9px;
      border-radius: 20px;
      font-size: 0.72rem;
      font-weight: 700;
      white-space: nowrap;
    }

    .badge.ok { color: #166534; background: #dcfce7; }
    .badge.pendencia { color: #92400e; background: #fef3c7; }
    .badge.nao { color: #991b1b; background: #fee2e2; }
    .badge.na { color: #475569; background: #f1f5f9; }

    @media (max-width: 650px) {
      .hero {
        min-height: 270px;
      }

      .fullscreen-btn {
        top: 14px;
        right: 14px;
        padding: 9px 11px;
        font-size: 0;
      }

      .fullscreen-btn span {
        font-size: 1.1rem;
      }

      .card-header {
        align-items: flex-start;
        flex-direction: column;
        padding: 18px;
      }

      th, td {
        padding: 14px 12px;
      }

      th:nth-child(3),
      td:nth-child(3) {
        display: none;
      }

      .checklist-grid {
        grid-template-columns: 1fr;
      }

      .modal-body {
        padding: 18px;
      }
    }
  </style>
</head>

<body>
  <header class="hero">
    <button class="fullscreen-btn" onclick="alternarTelaCheia()" title="Alternar tela cheia">
      <span>⛶</span>
      <b>Tela cheia</b>
    </button>

    <div class="hero-content">
      <div class="brand-mark">✓</div>
      <h1>FiltroAmb</h1>
      <p>Checklist</p>
    </div>
  </header>

  <main class="container">
    <section class="card">
      <div class="card-header">
        <div>
          <h2>Inspeções de veículos</h2>
          <p>Acompanhe os checklists registrados pela equipe</p>
        </div>
        <div class="status">Sistema conectado</div>
      </div>

      <div id="loading" class="loading">Carregando dados...</div>

      <table id="tabela" style="display: none;">
        <thead>
          <tr>
            <th>Data</th>
            <th>Placa</th>
            <th>Nome do motorista</th>
            <th style="width: 100px; text-align: center;">Checklist</th>
          </tr>
        </thead>
        <tbody id="tbody"></tbody>
      </table>
    </section>
  </main>

  <div class="modal-overlay" id="modal">
    <div class="modal">
      <div class="modal-header">
        <h2 id="modal-title">Checklist</h2>
        <button class="close-btn" onclick="fecharModal()" aria-label="Fechar">×</button>
      </div>
      <div class="modal-body" id="modal-body"></div>
    </div>
  </div>

  <script>
    const CSV_URL = "https://docs.google.com/spreadsheets/d/1qrDeKu6-CtaJ02x26puLgi6eUON0CEJG3J9nR8dQoJA/export?format=csv&gid=1550304863";

    let dados = [];
    let headers = [];

    function parseCSV(text) {
      const lines = text.trim().split(/\r?\n/);
      const result = [];

      for (const line of lines) {
        const row = [];
        let current = "";
        let insideQuotes = false;

        for (const char of line) {
          if (char === '"') {
            insideQuotes = !insideQuotes;
          } else if (char === "," && !insideQuotes) {
            row.push(current.trim());
            current = "";
          } else {
            current += char;
          }
        }

        row.push(current.trim());
        result.push(row);
      }

      return result;
    }

    function escaparHTML(valor) {
      return String(valor || "-")
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/"/g, "&quot;")
        .replace(/'/g, "&#039;");
    }

    function classificar(valor) {
      if (!valor) return "na";

      const v = valor.toUpperCase().trim();

      if (v === "OK" || v === "SIM") return "ok";
      if (v.includes("PENDEN")) return "pendencia";
      if (v === "NÃO" || v === "NAO") return "nao";

      return "na";
    }

    function badgeHTML(valor) {
      const tipo = classificar(valor);
      return `<span class="badge ${tipo}">${escaparHTML(valor || "N.A")}</span>`;
    }

    async function carregarDados() {
      try {
        const response = await fetch(CSV_URL);

        if (!response.ok) {
          throw new Error("Não foi possível carregar os dados.");
        }

        const text = await response.text();
        const rows = parseCSV(text);

        headers = rows[0] || [];
        dados = rows.slice(1).filter(row => row[0]);

        const tbody = document.getElementById("tbody");
        tbody.innerHTML = "";

        dados.forEach((row, index) => {
          const tr = document.createElement("tr");

          tr.innerHTML = `
            <td>${escaparHTML(row[0])}</td>
            <td><strong>${escaparHTML(row[1])}</strong></td>
            <td>${escaparHTML(row[2])}</td>
            <td style="text-align: center;">
              <button class="btn-check" onclick="abrirChecklist(${index})" title="Ver checklist completo">
                📋
              </button>
            </td>
          `;

          tbody.appendChild(tr);
        });

        document.getElementById("loading").style.display = "none";
        document.getElementById("tabela").style.display = "table";
      } catch (err) {
        document.getElementById("loading").textContent = "Erro ao carregar os dados.";
        console.error(err);
      }
    }

    function abrirChecklist(index) {
      const row = dados[index];
      const placa = row[1] || "";
      const motorista = row[2] || "";
      const data = row[0] || "";

      document.getElementById("modal-title").textContent = `Checklist - ${placa}`;

      let html = `
        <div class="info-row">
          <div class="info-item"><strong>Data:</strong> ${escaparHTML(data)}</div>
          <div class="info-item"><strong>Placa:</strong> ${escaparHTML(placa)}</div>
          <div class="info-item"><strong>Motorista:</strong> ${escaparHTML(motorista)}</div>
          <div class="info-item"><strong>KM:</strong> ${escaparHTML(row[3])}</div>
        </div>
        <div class="checklist-grid">
      `;

      for (let i = 4; i < headers.length; i++) {
        const titulo = headers[i] || "";
        const valor = row[i] || "";

        if (titulo.toUpperCase().includes("FOTO") || titulo.toUpperCase() === "*****") {
          continue;
        }

        const tipo = classificar(valor);

        html += `
          <div class="check-item ${tipo}">
            <span>${escaparHTML(titulo)}</span>
            ${badgeHTML(valor)}
          </div>
        `;
      }

      html += "</div>";

      document.getElementById("modal-body").innerHTML = html;
      document.getElementById("modal").classList.add("active");
    }

    function fecharModal() {
      document.getElementById("modal").classList.remove("active");
    }

    async function alternarTelaCheia() {
      try {
        if (!document.fullscreenElement) {
          await document.documentElement.requestFullscreen();
        } else {
          await document.exitFullscreen();
        }
      } catch (error) {
        console.error("Tela cheia não disponível:", error);
      }
    }

    document.getElementById("modal").addEventListener("click", function (event) {
      if (event.target === this) {
        fecharModal();
      }
    });

    document.addEventListener("keydown", function (event) {
      if (event.key === "Escape") {
        fecharModal();
      }
    });

    carregarDados();
  </script>
</body>
</html>
