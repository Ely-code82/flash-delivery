<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>FlashDelivery - Tabela de Entregas</title>

    <!-- Fonte Google -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

    <style>
        body {
            margin: 0;
            font-family: "Poppins", sans-serif;
            background: #0d0d0d;
            color: #fff;
            text-align: center;
        }

        header {
            background: linear-gradient(135deg, #0aff72, #00c95e);
            padding: 35px 20px;
            color: #000;
            font-size: 34px;
            font-weight: 700;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
            letter-spacing: 1px;
        }

        .container {
            max-width: 1000px;
            margin: 40px auto;
            background: #121212;
            padding: 30px;
            border-radius: 18px;
            box-shadow: 0 4px 25px rgba(0, 255, 127, 0.15);
        }

        h2 {
            color: #00ff88;
            font-size: 26px;
            margin-bottom: 20px;
            font-weight: 600;
            text-transform: uppercase;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 35px;
            overflow: hidden;
        }

        table th {
            background: #00ff88;
            color: #000;
            padding: 14px;
            font-size: 18px;
            font-weight: 700;
        }

        table td {
            padding: 12px;
            border-bottom: 1px solid #333;
        }

        tr:nth-child(even) {
            background: #0f0f0f;
        }

        tr:nth-child(odd) {
            background: #181818;
        }

        .btn {
            background: linear-gradient(135deg, #00ff88, #00c46a);
            color: #000;
            padding: 14px 24px;
            border-radius: 10px;
            font-size: 18px;
            font-weight: 600;
            text-decoration: none;
            display: inline-block;
            transition: 0.3s;
            box-shadow: 0 4px 15px rgba(0, 255, 127, 0.4);
            margin-bottom: 20px;
        }

        .btn:hover {
            transform: scale(1.05);
            filter: brightness(1.1);
        }

        footer {
            text-align: center;
            padding: 20px;
            margin-top: 40px;
            background: #0a0a0a;
            color: #00ff88;
            font-size: 15px;
            font-weight: 300;
            letter-spacing: 1px;
        }

        /* MOBILE */
        @media (max-width: 600px) {
            header {
                font-size: 26px;
            }

            table th, table td {
                font-size: 15px;
                padding: 10px;
            }

            .container {
                padding: 18px;
            }
        }
    </style>
</head>
<body id="top">
    <header>FlashDelivery • Tabela de Entregas</header>

    <div class="container">
        <h2>Bairros</h2>

        <a href="#lotes" class="btn">Acessar Lotes e Residenciais</a>

        <table>
            <tr><th>Bairro</th><th>Valor</th></tr>
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
            <tr><td>Olho D'Água do C.</td><td>6,00</td></tr>
            <tr><td>Ouro Preto</td><td>5,00</td></tr>
            <tr><td>Planalto</td><td>7,00</td></tr>
            <tr><td>Primavera</td><td>5,00</td></tr>
            <tr><td>Santa Esmeralda</td><td>6,00</td></tr>
            <tr><td>Santa Edwiges</td><td>6,00</td></tr>
            <tr><td>São Luís</td><td>1/2 — 6,00</td></tr>
            <tr><td>S. Amon de Melo</td><td>7,00</td></tr>
            <tr><td>S. Teotônio Vilela</td><td>6,00</td></tr>
            <tr><td>S. Nilo Coelho</td><td>7,00</td></tr>
            <tr><td>Verdes Campos</td><td>7,00</td></tr>
            <tr><td>Zélia Barbosa Rocha</td><td>6,00</td></tr>
        </table>

        <h2 id="lotes">Lotes e Residenciais</h2>

        <a href="#top" class="btn">Voltar ao topo</a>

        <table>
            <tr><th>Lote / Residencial</th><th>Valor</th></tr>
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
            <tr><td>J. Perucaba</td><td>1/2 — 7,00</td></tr>
            <tr><td>J. Europa</td><td>8,00</td></tr>
            <tr><td>JBR</td><td>9,00</td></tr>
            <tr><td>José Ernesto</td><td>10,00</td></tr>
            <tr><td>Nª Sra Aparecida</td><td>10,00</td></tr>
            <tr><td>Monte Sinai</td><td>10,00</td></tr>
            <tr><td>Riviera</td><td>8,00</td></tr>
            <tr><td>Porto Vitória</td><td>9,00</td></tr>
            <tr><td>R. Perucaba</td><td>8,00</td></tr>
            <tr><td>Recanto Boa Vista</td><td>8,00</td></tr>
            <tr><td>San Lorenzo</td><td>9,00</td></tr>
            <tr><td>Sonho Verde</td><td>8,00</td></tr>
            <tr><td>Pedra Azul</td><td>8,00</td></tr>
            <tr><td>Val Paraíso</td><td>10,00</td></tr>
            <tr><td>Vale Perucaba</td><td>9,00</td></tr>
            <tr><td>UFAL</td><td>12,00</td></tr>
        </table>
    </div>

    <footer>© 2025 FlashDelivery • Rápido • Confiável • Profissional</footer>
</body>
</html>
