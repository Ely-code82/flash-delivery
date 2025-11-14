# flash-delivery
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Flash Delivery — Taxas de Entrega</title>
  <style>
    :root{
      --bg:#0b2540;
      --card:#07293f;
      --accent:#ffb703;
      --muted:#a8c0d8;
      --glass: rgba(255,255,255,0.04);
      --white: #ffffff;
      font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    body{margin:0;background:linear-gradient(180deg,var(--bg),#01203a);color:var(--white);min-height:100vh}
    .container{max-width:1100px;margin:32px auto;padding:24px}
    header{display:flex;gap:16px;align-items:center}
    .logo{width:80px;height:80px;border-radius:14px;background:linear-gradient(135deg,var(--accent),#ff7b00);display:flex;align-items:center;justify-content:center;font-weight:800;color:#07293f;font-size:20px}
    h1{margin:0;font-size:28px}
    p.lead{margin:4px 0 0;color:var(--muted)}

    .card{background:linear-gradient(180deg,var(--card), rgba(7,41,63,0.6));border-radius:12px;padding:18px;margin-top:20px;box-shadow:0 6px 18px rgba(2,6,23,0.6)}

    .controls{display:flex;gap:12px;align-items:center;margin-bottom:14px;flex-wrap:wrap}
    .search{flex:1;min-width:200px}
    input[type=text]{width:100%;padding:10px 12px;border-radius:8px;border:1px solid rgba(255,255,255,0.06);background:var(--glass);color:var(--white)}
    .seg{display:flex;background:rgba(255,255,255,0.03);border-radius:8px;padding:4px}
    .seg button{background:transparent;color:var(--muted);border:0;padding:6px 12px;border-radius:6px;cursor:pointer}
    .seg button.active{background:var(--accent);color:#07293f;font-weight:700}

    table{width:100%;border-collapse:collapse;margin-top:6px}
    thead th{text-align:left;padding:10px 8px;font-size:14px;color:var(--muted);border-bottom:1px solid rgba(255,255,255,0.05)}
    tbody td{padding:10px 8px;border-bottom:1px dashed rgba(255,255,255,0.03)}
    tbody tr:hover{background:rgba(255,255,255,0.02)}
    .badge{display:inline-block;padding:6px 8px;border-radius:8px;background:rgba(255,255,255,0.03);color:var(--muted);font-size:13px}

    .grid{display:grid;grid-template-columns:1fr 420px;gap:18px}
    .right{padding:12px;border-radius:10px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01))}

    footer{margin-top:18px;color:var(--muted);font-size:13px}

    /* responsive */
    @media(max-width:900px){
      .grid{grid-template-columns:1fr}
      .right{order:2}
    }

    .download{background:var(--accent);color:#07293f;border:0;padding:10px 12px;border-radius:8px;cursor:pointer;font-weight:700}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">FD</div>
      <div>
        <h1>Flash Delivery — Taxas de Entrega</h1>
        <p class="lead">Lista atualizada de bairros e lotes/residenciais. Use a busca para filtrar rápido.</p>
      </div>
    </header>

    <div class="card">
      <div class="controls">
        <div class="search">
          <input id="q" type="text" placeholder="Buscar bairro ou valor... (ex: Centro ou 6,00)" oninput="filterTable()" />
        </div>
        <div class="seg" role="tablist">
          <button id="btn-bairros" class="active" onclick="show('bairros', this)">Bairros</button>
          <button id="btn-lotes" onclick="show('lotes', this)">Lotes / Residenciais</button>
        </div>
        <button class="download" onclick="downloadCSV()">Baixar CSV</button>
      </div>

      <div class="grid">
        <div id="bairros" class="table-wrap">
          <table id="tblBairros" aria-label="Tabela de bairros">
            <thead><tr><th>Bairro</th><th>Valor</th></tr></thead>
            <tbody>
              <!-- Rows geradas por script -->
            </tbody>
          </table>
        </div>

        <aside class="right">
          <h3 style="margin-top:0">Resumo</h3>
          <p class="lead">Selecione a aba de <strong>Bairros</strong> ou <strong>Lotes</strong>. A pesquisa filtra nomes e valores. O botão <em>Baixar CSV</em> gera o arquivo com os dados exibidos.</p>

          <div style="margin-top:12px">
            <div class="badge">Total bairros: <span id="countB">0</span></div>
            &nbsp;
            <div class="badge">Total lotes: <span id="countL">0</span></div>
          </div>

          <div style="margin-top:18px;color:var(--muted);font-size:13px">Contato: <strong>Flash Delivery</strong> — (82) 99999-9999</div>
        </aside>
      </div>

      <div id="lotes" style="display:none;margin-top:14px">
        <table id="tblLotes" aria-label="Tabela de lotes">
          <thead><tr><th>Lote / Residencial</th><th>Valor</th></tr></thead>
          <tbody>
            <!-- Rows geradas por script -->
          </tbody>
        </table>
      </div>

    </div>

    <footer>Feito para Flash Delivery • Dados exibidos apenas para exemplo.</footer>
  </div>

  <script>
    // Dados originais (coloquei exatamente como você enviou)
    const dataBairros = [
["Alto do Cruzeiro","6,00"],
["Baixão","5,00"],
["Baixa Grande","6,00"],
["Brasília","6,00"],
["Boa Vista","7,00"],
["Batingas","10,00"],
["Bom Sucesso","7,00"],
["Brasiliana","6,00"],
["Centro","5,00"],
["Cavaco","6,00"],
["Cacimbas","5,00"],
["Caititus","6,00"],
["Capiatá","6,00"],
["Canafístula","7,00"],
["Canaã","12,00"],
["Distrito Industrial","8,00"],
["Eldorado","5,00"],
["Guaribas","6,00"],
["Itapuã","6,00"],
["Jardim Esperança","7,00"],
["Jardim de Maria","6,00"],
["Jardim Tropical","6,00"],
["João Paulo II","5,00"],
["Massaranduba","7,00"],
["Manoel Teles","5,00"],
["Novo Horizonte","6,00"],
["Nova Esperança","6,00"],
["Olho D'Gua Do C","6,00"],
["Ouro Preto","5,00"],
["Planalto","7,00"],
["Primavera","5,00"],
["Santa Esmeralda","6,00"],
["Santa Edwiges","6,00"],
["São Luís","1/2 6,00"],
["S. Amon de Melo","7,00"],
["S. Teotônio Vilela","6,00"],
["S. Nilo Coelho","7,00"],
["Verdes Campos","7,00"],
["Zélia Barbosa R.","6,00"],
];

    const dataLotes = [
["Aroeiras","9,00"],
["Agreste","12,00"],
["Alto do Morro","9,00"],
["Brisa do Lago","8,00"],
["Bem Viver","10,00"],
["Colorado","9,00"],
["Cerejeiras","8,00"],
["Campo Grande","8,00"],
["Dona Lourdes","8,00"],
["Flor de Maria","8,00"],
["Felicita","8,00"],
["Jatobá","8,00"],
["J. Perucaba","1/2 7,00"],
["J. Europa","8,00"],
["JBR","9,00"],
["José Ernesto","10,00"],
["Nª Sra Aparecida","10,00"],
["Monte Sinai","10,00"],
["Riviera","8,00"],
["Porto Vitória","9,00"],
["R. Perucaba","8,00"],
["Recanto Boa V.","8,00"],
["San Lorenzo","9,00"],
["Sonho Verde","8,00"],
["Pedra Azul","8,00"],
["Val Paraíso","10,00"],
["Vale Perucaba","9,00"],
["UFAL","12,00"],
];

    // Render tables
    function renderTable(tableId, data){
      const tbody = document.querySelector(`#${tableId} tbody`);
      tbody.innerHTML = '';
      data.forEach(row=>{
        const tr = document.createElement('tr');
        const td1 = document.createElement('td'); td1.textContent = row[0];
        const td2 = document.createElement('td'); td2.textContent = row[1];
        tr.appendChild(td1); tr.appendChild(td2);
        tbody.appendChild(tr);
      });
    }

    renderTable('tblBairros', dataBairros);
    renderTable('tblLotes', dataLotes);

    document.getElementById('countB').textContent = dataBairros.length;
    document.getElementById('countL').textContent = dataLotes.length;

    // Show/hide
    function show(name, btn){
      document.getElementById('bairros').style.display = name==='bairros' ? 'block' : 'none';
      document.getElementById('lotes').style.display = name==='lotes' ? 'block' : 'none';
      document.querySelectorAll('.seg button').forEach(b=>b.classList.remove('active'));
      btn.classList.add('active');
      document.getElementById('q').value = '';
    }

    // Filter function
    function normalize(s){return String(s).toLowerCase();}
    function filterTable(){
      const q = normalize(document.getElementById('q').value);
      filterGrid('tblBairros', dataBairros, q);
      filterGrid('tblLotes', dataLotes, q);
    }
    function filterGrid(tableId, data, q){
      const tbody = document.querySelector(`#${tableId} tbody`);
      tbody.innerHTML='';
      data.forEach(row=>{
        if(!q || normalize(row[0]).includes(q) || normalize(row[1]).includes(q)){
          const tr = document.createElement('tr');
          const td1 = document.createElement('td'); td1.textContent = row[0];
          const td2 = document.createElement('td'); td2.textContent = row[1];
          tr.appendChild(td1); tr.appendChild(td2);
          tbody.appendChild(tr);
        }
      });
    }

    // CSV download
    function downloadCSV(){
      const active = document.getElementById('bairros').style.display!=='none';
      const data = active ? dataBairros : dataLotes;
      const rows = [['Nome','Valor']].concat(data);
      const csv = rows.map(r=>r.map(c=>`"${c.replace(/\"/g,'""') }"`).join(',')).join('\n');
      const blob = new Blob([csv],{type:'text/csv;charset=utf-8;'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href = url; a.download = active ? 'bairros_flash_delivery.csv' : 'lotes_flash_delivery.csv';
      document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
    }
  </script>
</body>
</html>
