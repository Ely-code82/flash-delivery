<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>FlashDelivery — Bairro Primavera</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#f6f7fb;
      --card:#ffffff;
      --muted:#6b7280;
      --accent:#0f6f5b;
      --accent-2:#07a08a;
      --glass: rgba(255,255,255,0.6);
      --radius:14px;
      font-family: 'Poppins', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    body{margin:0; background:linear-gradient(180deg,var(--bg),#eef2f6); color:#111827; -webkit-font-smoothing:antialiased;}

    header{padding:22px 18px; display:flex; gap:12px; align-items:center; justify-content:space-between;}
    .brand{display:flex; gap:12px; align-items:center}
    .logo{width:56px; height:56px; border-radius:12px; background:linear-gradient(135deg,var(--accent),var(--accent-2)); display:flex; align-items:center; justify-content:center; color:white; font-weight:700; font-size:18px; box-shadow:0 6px 18px rgba(11,68,56,0.12)}
    .title{line-height:1}
    .title h1{margin:0; font-size:18px}
    .title p{margin:0; font-size:12px; color:var(--muted)}

    .container{max-width:980px; margin:12px auto; padding:18px;}

    .card{background:var(--card); border-radius:var(--radius); box-shadow:0 8px 30px rgba(10,20,40,0.06); padding:18px}

    .controls{display:flex; gap:12px; margin-bottom:12px; flex-wrap:wrap}
    .search{flex:1; min-width:210px}
    input[type=text]{width:100%; padding:12px 14px; border-radius:12px; border:1px solid #e6e9ef; background:transparent}

    .tables{display:grid; grid-template-columns:1fr 360px; gap:18px}

    table{width:100%; border-collapse:collapse}
    thead th{ text-align:left; font-weight:600; font-size:13px; padding:12px 10px; color:var(--muted)}
    tbody td{ padding:12px 10px; border-top:1px solid #f1f3f6}

    .section-title{font-weight:700; font-size:14px; margin-bottom:8px}

    /* mobile-friendly card view for small screens */
    @media (max-width:820px){
      .tables{grid-template-columns:1fr;}
      table, thead, tbody, th, td, tr{display:block}
      thead{display:none}
      tr{margin-bottom:12px; border-radius:12px; background:var(--bg); padding:10px}
      td{display:flex; justify-content:space-between; padding:8px 10px; border-top:none}
      td[data-label]{position:relative}
      td[data-label]::before{content:attr(data-label); display:block; font-size:12px; color:var(--muted); margin-bottom:6px}
    }

    /* small touches */
    .note{font-size:13px; color:var(--muted); margin-top:8px}
    .download{padding:10px 14px; border-radius:10px; background:transparent; border:1px solid #e6e9ef}
    footer{max-width:980px; margin:18px auto; text-align:center; color:var(--muted); font-size:13px}
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <div class="logo">FD</div>
      <div class="title">
        <h1>FlashDelivery</h1>
        <p>Bairro Primavera</p>
      </div>
    </div>
    <div style="min-width:160px; text-align:right">
      <small style="color:var(--muted)">Tabela de taxas</small>
    </div>
  </header>

  <main class="container">
    <section class="card">
      <div class="controls">
        <div class="search">
          <input id="q" type="text" placeholder="Pesquisar bairro..." aria-label="Pesquisar bairro" />
        </div>
        <div>
          <button id="downloadCsv" class="download">Baixar CSV</button>
        </div>
      </div>

      <div class="tables">
        <div>
          <div class="section-title">Bairros</div>
          <table id="table-main">
            <thead>
              <tr><th>Bairro</th><th>Valor (R$)</th></tr>
            </thead>
            <tbody>
              <!-- dados inseridos via JS -->
            </tbody>
          </table>
        </div>

        <div>
          <div class="section-title">Lote / Residencial</div>
          <table id="table-lotes">
            <thead>
              <tr><th>Local</th><th>Valor (R$)</th></tr>
            </thead>
            <tbody>
              <!-- dados inseridos via JS -->
            </tbody>
          </table>
        </div>
      </div>

      <p class="note">Toque em um item no celular para copiar o valor rapidamente.</p>
    </section>
  </main>

  <footer>
    Criado com ♥ — FlashDelivery • Atualize os valores neste arquivo <code>index.html</code>
  </footer>

  <script>
    const bairros = [
      ["Alto do Cruzeiro","6,00"],["Baixão","5,00"],["Baixa Grande","6,00"],["Brasília","6,00"],["Boa Vista","7,00"],["Batingas","10,00"],["Bom Sucesso","7,00"],["Brasiliana","6,00"],["Centro","5,00"],["Cavaco","6,00"],["Cacimbas","5,00"],["Caititus","6,00"],["Capiatá","6,00"],["Canafístula","7,00"],["Canaã","12,00"],["Distrito Industrial","8,00"],["Eldorado","5,00"],["Guaribas","6,00"],["Itapuã","6,00"],["Jardim Esperança","7,00"],["Jardim de Maria","6,00"],["Jardim Tropical","6,00"],["João Paulo II","5,00"],["Massaranduba","7,00"],["Manoel Teles","5,00"],["Novo Horizonte","6,00"],["Nova Esperança","6,00"],["Olho D'Gua Do C","6,00"],["Ouro Preto","5,00"],["Planalto","7,00"],["Primavera","5,00"],["Santa Esmeralda","6,00"],["Santa Edwiges","6,00"],["São Luís","6,00"],["S. Amon de Melo","7,00"],["S. Teotônio Vilela","6,00"],["S. Nilo Coelho","7,00"],["Verdes Campos","7,00"],["Zélia Barbosa R.","6,00"]
    ];

    const lotes = [
      ["Aroeiras","9,00"],["Agreste","12,00"],["Alto do Morro","9,00"],["Brisa do Lago","8,00"],["Bem Viver","10,00"],["Colorado","9,00"],["Cerejeiras","8,00"],["Campo Grande","8,00"],["Dona Lourdes","8,00"],["Flor de Maria","8,00"],["Felicita","8,00"],["Jatobá","8,00"],["J. Perucaba","7,00"],["J. Europa","8,00"],["JBR","9,00"],["José Ernesto","10,00"],["Nª Sra Aparecida","10,00"],["Monte Sinai","10,00"],["Riviera","8,00"],["Porto Vitória","9,00"],["R. Perucaba","8,00"],["Recanto Boa V.","8,00"],["San Lorenzo","9,00"],["Sonho Verde","8,00"],["Pedra Azul","8,00"],["Val Paraíso","10,00"],["Vale Perucaba","9,00"],["UFAL","12,00"]
    ];

    const tMain = document.querySelector('#table-main tbody');
    const tLotes = document.querySelector('#table-lotes tbody');
    const q = document.getElementById('q');

    function render(){
      const term = q.value.trim().toLowerCase();
      tMain.innerHTML = '';
      tLotes.innerHTML = '';

      bairros.forEach(([b,v])=>{
        if(term && !b.toLowerCase().includes(term)) return;
        const tr = document.createElement('tr');
        const td1 = document.createElement('td'); td1.textContent = b; td1.setAttribute('data-label','Bairro');
        const td2 = document.createElement('td'); td2.textContent = v; td2.setAttribute('data-label','Valor');
        tr.append(td1,td2);
        tMain.appendChild(tr);
      });

      lotes.forEach(([b,v])=>{
        if(term && !b.toLowerCase().includes(term)) return;
        const tr = document.createElement('tr');
        const td1 = document.createElement('td'); td1.textContent = b; td1.setAttribute('data-label','Local');
        const td2 = document.createElement('td'); td2.textContent = v; td2.setAttribute('data-label','Valor');
        tr.append(td1,td2);
        tLotes.appendChild(tr);
      });

      // adicionar clique para copiar valor (útil no celular)
      document.querySelectorAll('td[data-label="Valor"]').forEach(td=>{
        td.style.cursor='pointer';
        td.onclick = ()=>{
          navigator.clipboard?.writeText(td.textContent).then(()=>{
            const original = td.textContent;
            td.textContent = 'Copiado ✓';
            setTimeout(()=> td.textContent = original,900);
          }).catch(()=>{
            alert('Não foi possível copiar.');
          });
        }
      });
    }

    q.addEventListener('input', render);
    render();

    // CSV download
    document.getElementById('downloadCsv').addEventListener('click', ()=>{
      let csv = 'Bairro,Valor\n';
      bairros.forEach(([b,v])=> csv += `"${b}","${v}"\n`);
      csv += '\nLote/Residencial,Valor\n';
      lotes.forEach(([b,v])=> csv += `"${b}","${v}"\n`);
      const blob = new Blob([csv],{type:'text/csv;charset=utf-8;'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href = url; a.download = 'taxas-flashdelivery.csv'; document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
    });
  </script>
</body>
</html>
