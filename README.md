<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>FlashDelivery — Tabela de Preços</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#07120b;
      --card:#0e2017;
      --muted:#9fb39a;
      --accent-1:#19a974;
      --accent-2:#0ea56b;
      --glass: rgba(255,255,255,0.03);
      --radius:14px;
      --container-width:1000px;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: "Poppins", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background:linear-gradient(180deg,var(--bg),#071814 120%);
      color:#e6f5ea;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      text-align:center;
      padding:28px 16px;
    }

    header{
      max-width:var(--container-width);
      margin:0 auto 22px;
      background:linear-gradient(135deg,var(--accent-1),var(--accent-2));
      color:#02210f;
      padding:26px 20px;
      border-radius:20px;
      box-shadow:0 12px 30px rgba(2,33,15,0.35);
      font-weight:700;
      letter-spacing:1px;
      font-size:24px;
    }

    .card{
      max-width:var(--container-width);
      margin:18px auto;
      background:var(--card);
      border-radius:var(--radius);
      padding:22px;
      box-shadow:0 10px 30px rgba(2,33,15,0.35);
      overflow:hidden;
    }

    .top-actions{
      display:flex;
      gap:12px;
      justify-content:center;
      flex-wrap:wrap;
      margin-bottom:18px;
    }

    .btn{
      background:linear-gradient(135deg,var(--accent-2),var(--accent-1));
      color:#05210f;
      padding:10px 18px;
      border-radius:12px;
      text-decoration:none;
      font-weight:600;
      box-shadow:0 8px 18px rgba(14,165,107,0.16);
      transition:transform .18s ease,filter .18s ease;
    }
    .btn:hover{transform:translateY(-3px);filter:brightness(1.03)}

    h2{color:var(--accent-1);margin:6px 0 14px;font-size:20px}

    /* tabela responsiva */
    table{width:100%;border-collapse:collapse;border-radius:10px;overflow:hidden}
    thead th{background:linear-gradient(90deg,rgba(255,255,255,0.03),rgba(255,255,255,0.02));color:var(--muted);text-align:left;padding:12px 16px;font-weight:600;font-size:15px}
    tbody td{padding:12px 16px;border-bottom:1px solid rgba(255,255,255,0.03);font-size:15px}
    tbody tr:nth-child(even){background:rgba(255,255,255,0.01)}

    /* cards em mobile */
    @media (max-width:720px){
      table{display:block}
      thead{display:none}
      tbody tr{display:block;margin:10px 0;padding:12px;background:var(--glass);border-radius:12px}
      tbody td{display:flex;justify-content:space-between;padding:8px 12px;border-bottom:none}
    }

    footer{max-width:var(--container-width);margin:26px auto 0;color:var(--muted);font-size:13px}

    /* âncoras suaves */
    html{scroll-behavior:smooth}

    .note{color:var(--muted);font-size:13px;margin-top:8px}
  </style>
</head>
<body>
  <header id="top">FlashDelivery — Tabela de Preços de Entrega</header>

  <main class="card" role="main">
    <h2>Bairros</h2>

    <div class="top-actions">
      <a class="btn" href="#lotes">Ver Lotes e Residenciais</a>
      <a class="btn" href="#top">Voltar ao topo</a>
    </div>

    <div style="overflow:auto">
      <table aria-label="Tabela de preços por bairro">
        <thead>
          <tr><th>Bairro</th><th>Valor (R$)</th></tr>
        </thead>
        <tbody>
          <tr><td>Alto do Cruzeiro</td><td>6,00</td></tr>
          <tr><td>Baixão</td><td>5,00</td></tr>
          <tr><td>Baixa Grande</td><td>6,00</td></tr>
          <tr><td>Brasília</td><td>6,00</td></tr>
          <tr><td>Boa Vista</td><td>7,00</td></tr>
          <tr><td>Batingas</td><td>10,00</td></tr>
          <tr><td>Bom Sucesso</td><td>7,00</td></tr>
          <tr><td>Brasiliana</td><td>6,00</td></tr>
          <tr><td>Centro</td><td>5,00</td></tr>
          <tr><td>Cavaco</td><td>6,00</td></tr>
          <tr><td>Cacimbas</td><td>5,00</td></tr>
          <tr><td>Caititus</td><td>6,00</td></tr>
          <tr><td>Capiatá</td><td>6,00</td></tr>
          <tr><td>Canafístula</td><td>7,00</td></tr>
          <tr><td>Canaã</td><td>12,00</td></tr>
          <tr><td>Distrito Industrial</td><td>8,00</td></tr>
          <tr><td>Eldorado</td><td>5,00</td></tr>
          <tr><td>Guaribas</td><td>6,00</td></tr>
          <tr><td>Itapuã</td><td>6,00</td></tr>
          <tr><td>Jardim Esperança</td><td>7,00</td></tr>
          <tr><td>Jardim de Maria</td><td>6,00</td></tr>
          <tr><td>Jardim Tropical</td><td>6,00</td></tr>
          <tr><td>João Paulo II</td><td>5,00</td></tr>
          <tr><td>Massaranduba</td><td>7,00</td></tr>
          <tr><td>Manoel Teles</td><td>5,00</td></tr>
          <tr><td>Novo Horizonte</td><td>6,00</td></tr>
          <tr><td>Nova Esperança</td><td>6,00</td></tr>
          <tr><td>Olho D'Água do C</td><td>6,00</td></tr>
          <tr><td>Ouro Preto</td><td>5,00</td></tr>
          <tr><td>Planalto</td><td>7,00</td></tr>
          <tr><td>Primavera</td><td>5,00</td></tr>
          <tr><td>Santa Esmeralda</td><td>6,00</td></tr>
          <tr><td>Santa Edwiges</td><td>6,00</td></tr>
          <tr><td>São Luís</td><td>6,00 <span style="color:var(--muted);font-size:13px">(meio)</span></td></tr>
          <tr><td>S. Amon de Melo</td><td>7,00</td></tr>
          <tr><td>S. Teotônio Vilela</td><td>6,00</td></tr>
          <tr><td>S. Nilo Coelho</td><td>7,00</td></tr>
          <tr><td>Verdes Campos</td><td>7,00</td></tr>
          <tr><td>Zélia Barbosa R.</td><td>6,00</td></tr>
        </tbody>
      </table>
    </div>

    <p class="note">Dica: toque em "Ver Lotes e Residenciais" para ir direto à seção</p>
  </main>

  <section class="card" id="lotes">
    <h2>Lotes e Residenciais</h2>

    <div style="overflow:auto">
      <table aria-label="Tabela de preços por lote/residencial">
        <thead>
          <tr><th>Residencial</th><th>Valor (R$)</th></tr>
        </thead>
        <tbody>
          <tr><td>Aroeiras</td><td>9,00</td></tr>
          <tr><td>Agreste</td><td>12,00</td></tr>
          <tr><td>Alto do Morro</td><td>9,00</td></tr>
          <tr><td>Brisa do Lago</td><td>8,00</td></tr>
          <tr><td>Bem Viver</td><td>10,00</td></tr>
          <tr><td>Colorado</td><td>9,00</td></tr>
          <tr><td>Cerejeiras</td><td>8,00</td></tr>
          <tr><td>Campo Grande</td><td>8,00</td></tr>
          <tr><td>Dona Lourdes</td><td>8,00</td></tr>
          <tr><td>Flor de Maria</td><td>8,00</td></tr>
          <tr><td>Felicita</td><td>8,00</td></tr>
          <tr><td>Jatobá</td><td>8,00</td></tr>
          <tr><td>J. Perucaba</td><td>7,00 (meio)</td></tr>
          <tr><td>J. Europa</td><td>8,00</td></tr>
          <tr><td>JBR</td><td>9,00</td></tr>
          <tr><td>José Ernesto</td><td>10,00</td></tr>
          <tr><td>Nª Sra Aparecida</td><td>10,00</td></tr>
          <tr><td>Monte Sinai</td><td>10,00</td></tr>
          <tr><td>Riviera</td><td>8,00</td></tr>
          <tr><td>Porto Vitória</td><td>9,00</td></tr>
          <tr><td>R. Perucaba</td><td>8,00</td></tr>
          <tr><td>Recanto Boa V.</td><td>8,00</td></tr>
          <tr><td>San Lorenzo</td><td>9,00</td></tr>
          <tr><td>Sonho Verde</td><td>8,00</td></tr>
          <tr><td>Pedra Azul</td><td>8,00</td></tr>
          <tr><td>Val Paraíso</td><td>10,00</td></tr>
          <tr><td>Vale Perucaba</td><td>9,00</td></tr>
          <tr><td>UFAL</td><td>12,00</td></tr>
        </tbody>
      </table>
    </div>

  </section>

  <footer>© 2025 FlashDelivery • Rápido • Confiável • Profissional</footer>
</body>
</html>
