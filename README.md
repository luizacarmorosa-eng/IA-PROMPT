# IA-PROMPT
import weasyprint

html_content = """<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>README - K-Pulse News</title>
    <style>
        @page {
            size: A4;
            margin: 18mm 15mm;
            background-color: #0f0c1b;
        }

        *, *::before, *::after {
            box-sizing: border-box;
        }

        body {
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            color: #f1f1f1;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #0f0c1b;
            font-size: 10.5pt;
        }

        .header {
            background: linear-gradient(135deg, #7b2cbf, #ff2a74);
            padding: 24px 20px;
            border-radius: 12px;
            margin-bottom: 25px;
            text-align: center;
        }

        .header h1 {
            margin: 0;
            font-size: 22pt;
            color: #ffffff;
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        .header p {
            margin: 8px 0 0 0;
            color: #f0e6ff;
            font-size: 11pt;
            font-weight: 300;
        }

        .badge {
            display: inline-block;
            background-color: rgba(255, 255, 255, 0.2);
            padding: 3px 10px;
            border-radius: 15px;
            font-size: 8.5pt;
            margin-top: 10px;
            color: #fff;
        }

        h2 {
            font-size: 14pt;
            color: #ff2a74;
            border-bottom: 2px solid #7b2cbf;
            padding-bottom: 5px;
            margin-top: 22px;
            margin-bottom: 12px;
            page-break-after: avoid;
        }

        h3 {
            font-size: 11.5pt;
            color: #d1cbdc;
            margin-top: 15px;
            margin-bottom: 8px;
            page-break-after: avoid;
        }

        p {
            margin-bottom: 10px;
            color: #d1cbdc;
        }

        ul, ol {
            margin-top: 5px;
            margin-bottom: 12px;
            padding-left: 20px;
            color: #d1cbdc;
        }

        li {
            margin-bottom: 5px;
        }

        code {
            font-family: 'Courier New', Courier, monospace;
            background-color: #1a162b;
            color: #ff2a74;
            padding: 2px 6px;
            border-radius: 4px;
            font-size: 9.5pt;
        }

        pre {
            background-color: #1a162b;
            border: 1px solid #332d4a;
            border-left: 4px solid #ff2a74;
            padding: 12px;
            border-radius: 6px;
            overflow-x: auto;
            font-family: 'Courier New', Courier, monospace;
            font-size: 9pt;
            color: #e0e0e0;
            margin-bottom: 15px;
            page-break-inside: avoid;
        }

        .grid-table {
            width: 100%;
            border-collapse: collapse;
            margin: 15px 0;
            page-break-inside: avoid;
        }

        .grid-table th, .grid-table td {
            border: 1px solid #332d4a;
            padding: 8px 12px;
            text-align: left;
            font-size: 9.5pt;
        }

        .grid-table th {
            background-color: #1a162b;
            color: #ff2a74;
        }

        .grid-table td {
            background-color: rgba(26, 22, 43, 0.5);
            color: #d1cbdc;
        }

        .footer {
            margin-top: 30px;
            text-align: center;
            font-size: 8.5pt;
            color: #a099b5;
            border-top: 1px solid #332d4a;
            padding-top: 15px;
        }
    </style>
</head>
<body>

    <div class="header">
        <h1>K-Pulse News — README</h1>
        <p>Documentação do Portal de Notícias de K-Pop</p>
        <span class="badge">Versão 1.0.0</span>
        <span class="badge">Front-End Pure Stack</span>
    </div>

    <h2>📌 Sobre o Projeto</h2>
    <p>O <strong>K-Pulse News</strong> é um portal de notícias responsivo e moderno focado na cultura pop coreana (K-Pop). O projeto foi desenvolvido com uma estética <em>Dark Mode</em> vibrante inspirada em portais internacionais do segmento (como Soompi e Allkpop), utilizando nuances de roxo, rosa neon e tipografia fluida.</p>

    <h2>🎯 Destaques de Conteúdo</h2>
    <ul>
        <li><strong>Polemic BTS (RM & J-Hope):</strong> Cobertura e análise da repercussão sobre a presença dos membros no show de Chris Brown em Toronto.</li>
        <li><strong>Aniversário de 10 Anos do BLACKPINK:</strong> Matéria comemorativa da primeira década de debut do quarteto da YG Entertainment.</li>
        <li><strong>Mais Lidas & Newsletter:</strong> Seções laterais preparadas para retenção de leitores e captura de e-mails.</li>
    </ul>

    <h2>🛠️ Tecnologias Utilizadas</h2>
    <table class="grid-table">
        <thead>
            <tr>
                <th>Tecnologia</th>
                <th>Aplicação</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><code>HTML5</code></td>
                <td>Estruturação semântica do conteúdo (header, main, section, article, aside, footer).</td>
            </tr>
            <tr>
                <td><code>CSS3</code></td>
                <td>Estilização completa, variáveis de cor CSS, suporte a Flexbox e CSS Grid.</td>
            </tr>
            <tr>
                <td><code>Google Fonts</code></td>
                <td>Integração da tipografia moderna <em>Poppins</em> (pesos 300, 400, 600 e 700).</td>
            </tr>
        </tbody>
    </table>

    <h2>📐 Arquitetura do Layout</h2>
    <ul>
        <li><strong>Header Sticky:</strong> Navegação fixa no topo com suporte a <code>backdrop-filter: blur()</code> para transparência elegante ao rolar.</li>
        <li><strong>Grid Principal:</strong> Layout em duas colunas (2.5fr / 1fr) que divide o feed de matérias e a sidebar do portal.</li>
        <li><strong>Cards Interativos:</strong> Microinterações com <code>transform: translateY()</code> e sombras coloridas no estado <code>:hover</code>.</li>
        <li><strong>Media Queries:</strong> Design responsivo que se adapta para telas de dispositivos móveis.</li>
    </ul>

    <h2>🚀 Como Executar o Projeto</h2>
    <p>Por ser um projeto puramente front-end (HTML + CSS incorporado), não há necessidade de instalação de dependências ou servidores complexos:</p>
    <ol>
        <li>Crie um arquivo chamado <code>index.html</code> no seu computador.</li>
        <li>Cole o código completo do projeto no arquivo.</li>
        <li>Abra o arquivo diretamente em qualquer navegador web (Google Chrome, Firefox, Edge, Safari).</li>
    </ol>

    <h2>📂 Estrutura de Arquivos Recomendada</h2>
    <pre>
k-pulse-news/
├── index.html          # Código do blog (HTML + CSS)
├── README.md           # Documentação do projeto
└── README.pdf          # Versão PDF da documentação
    </pre>

    <div class="footer">
        K-Pulse News &copy; 2026 — Desenvolvido para projetos de Front-End K-Pop.
    </div>

</body>
</html>
"""

with open("README.html", "w", encoding="utf-8") as f:
    f.write(html_content)

weasyprint.HTML("README.html").write_pdf("README.pdf")
print("PDF gerado com sucesso!")