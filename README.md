# filipe-barbershop-
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <title>Filipe Barber Shop</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet" />
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(-45deg, #0f0c29, #302b63, #24243e, #1c1c3c);
      background-size: 400% 400%;
      animation: gradientBG 15s ease infinite;
      color: #e6e6e6;
      text-align: center;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      padding-bottom: 40px;
      user-select: none;
    }

    @keyframes gradientBG {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }

    header {
      background: rgba(30, 30, 50, 0.85);
      padding: 40px 20px 50px;
      box-shadow: 0 0 20px #cc2b2baa;
      border-radius: 0 0 30px 30px;
      margin-bottom: 30px;
      position: relative;
      overflow: hidden;
    }

    header::before {
      content: "";
      position: absolute;
      width: 120%;
      height: 200px;
      background: radial-gradient(circle at center, #cc2b2baa, transparent 70%);
      top: -100px;
      left: -10%;
      animation: pulseGlow 3s ease-in-out infinite alternate;
      z-index: 0;
      border-radius: 50%;
    }

    @keyframes pulseGlow {
      0% {transform: scale(1); opacity: 0.6;}
      100% {transform: scale(1.2); opacity: 0.9;}
    }

    header > * {
      position: relative;
      z-index: 1;
      animation: none !important;
      text-shadow: none !important;
      color: #cc2b2b;
    }

    .logo {
      width: 160px;
      border-radius: 20px;
      box-shadow: 0 0 20px #cc2b2bcc;
      transition: transform 0.3s ease;
      cursor: pointer;
      animation: fadeIn 1.2s ease forwards;
    }

    .logo:hover {
      transform: rotate(5deg) scale(1.1);
      box-shadow: 0 0 40px #cc2b2bff;
    }

    h1 {
      font-size: 3.2rem;
      margin: 15px 0 10px;
      font-weight: 600;
      letter-spacing: 2px;
      color: #cc2b2b;
      text-shadow: none;
      animation: none;
    }

    header p {
      font-size: 1.2rem;
      font-weight: 500;
      letter-spacing: 1px;
      color: #cc2b2b;
      text-shadow: none;
      animation: none;
    }

    .form-container {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      padding: 35px 30px;
      border-radius: 25px;
      max-width: 400px;
      margin: 0 auto 40px;
      box-shadow: 0 0 20px #cc2b2b88;
      transition: box-shadow 0.3s ease;
    }

    .form-container:hover {
      box-shadow: 0 0 35px #cc2b2bcc;
    }

    .form-container h2 {
      margin-bottom: 25px;
      font-weight: 600;
      font-size: 1.8rem;
      color: #cc2b2b;
      text-shadow: none;
      animation: none;
    }

    input, button {
      width: 100%;
      padding: 15px 18px;
      margin: 12px 0;
      border-radius: 15px;
      border: none;
      font-size: 1.1rem;
      font-weight: 500;
      box-shadow: inset 0 0 8px rgba(255, 255, 255, 0.15);
      transition: all 0.3s ease;
    }

    input {
      background: rgba(255, 255, 255, 0.9);
      color: #222;
      font-weight: 600;
      letter-spacing: 0.7px;
    }

    input::placeholder {
      color: #999;
      font-weight: 400;
    }

    input:focus {
      outline: none;
      box-shadow: 0 0 20px #cc2b2bff;
      background: #fff;
    }

    button {
      background: linear-gradient(135deg, #cc2b2b, #e53935);
      color: #fff;
      cursor: pointer;
      font-weight: 700;
      letter-spacing: 1.2px;
      box-shadow: 0 0 15px #cc2b2bcc;
      text-transform: uppercase;
      filter: drop-shadow(0 0 5px #e5393599);
      position: relative;
      overflow: hidden;
      animation: buttonGlow 2.5s ease-in-out infinite alternate;
    }

    button::before {
      content: "";
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: radial-gradient(circle, rgba(255,255,255,0.5) 20%, transparent 70%);
      opacity: 0;
      transition: opacity 0.4s ease;
      transform: rotate(25deg);
      pointer-events: none;
    }

    button:hover::before {
      opacity: 1;
      animation: shine 1s ease forwards;
    }

    @keyframes buttonGlow {
      0% {
        box-shadow: 0 0 8px #cc2b2bcc;
      }
      100% {
        box-shadow: 0 0 15px #e5393555, 0 0 25px #cc2b2b99;
      }
    }

    @keyframes shine {
      0% { transform: translateX(-100%) rotate(25deg); opacity: 0; }
      50% { opacity: 1; }
      100% { transform: translateX(100%) rotate(25deg); opacity: 0; }
    }

    button:hover {
      transform: scale(1.05);
      box-shadow: 0 0 25px #e53935cc;
    }

    .agendamentos {
      max-width: 650px;
      margin: 0 auto 60px;
      padding: 0 20px;
      text-align: left;

      /* lista oculta por padrão */
      display: none;
    }

    .agendamentos h2 {
      font-weight: 600;
      font-size: 2rem;
      color: #cc2b2b;
      margin-bottom: 25px;
      text-shadow: none;
      animation: none;
    }

    .agendamento {
      background: rgba(255, 255, 255, 0.1);
      padding: 20px 25px;
      margin: 15px 0;
      border-radius: 20px;
      border-left: 6px solid #cc2b2b;
      box-shadow: 0 0 15px rgba(204, 43, 43, 0.5);
      transition: all 0.3s ease;
      font-weight: 600;
      color: #ffd1d1;
      letter-spacing: 0.5px;
      cursor: default;
      user-select: text;

      text-shadow: none !important;
      animation: none !important;
    }

    .agendamento.atendido {
      text-decoration: line-through;
      opacity: 0.6;
    }

    .agendamento:hover {
      background: rgba(255, 255, 255, 0.2);
      box-shadow: 0 0 25px rgba(204, 43, 43, 0.8);
      transform: translateX(6px);
    }

    .btnAtendido {
      margin-top: 8px;
      padding: 6px 12px;
      background-color: #4CAF50;
      border: none;
      border-radius: 12px;
      color: white;
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .btnAtendido:hover {
      background-color: #45a049;
    }

    footer {
      background: #111;
      padding: 25px 10px;
      color: #bbb;
      font-size: 0.9rem;
      font-weight: 500;
      letter-spacing: 0.8px;
      border-radius: 30px 30px 0 0;
      max-width: 700px;
      margin: 0 auto;
      box-shadow: 0 -5px 15px rgba(204, 43, 43, 0.4);
    }

    .whatsapp-link {
      background-color: #25D366;
      padding: 10px 20px;
      border-radius: 30px;
      color: white;
      text-decoration: none;
      font-weight: 700;
      letter-spacing: 1px;
      box-shadow: 0 0 12px #25d366cc;
      transition: all 0.3s ease;
      display: inline-block;
      user-select: none;
    }

    .whatsapp-link:hover {
      background-color: #1ebe57;
      box-shadow: 0 0 25px #1ebe57cc;
      transform: scale(1.05);
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-30px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>

  <header>
    <img src="logo.jpeg" alt="Logo Filipe Barber Shop" class="logo" />
    <h1>Filipe Barber Shop</h1>
    <p>Agende seu horário com estilo!</p>
  </header>

  <div class="form-container">
    <h2>📅 Agendar Horário</h2>
    <form id="formAgendamento">
      <input type="text" id="nome" placeholder="Seu nome" required />
      <input type="date" id="data" required />
      <input type="time" id="hora" required />
      <button type="submit">Confirmar Agendamento</button>
    </form>
  </div>

  <div class="agendamentos">
    <h2>🗓️ Agendamentos Salvos</h2>
    <div id="listaAgendamentos"></div>
  </div>

  <footer>
    📞 WhatsApp: <a href="https://wa.me/5579981254335" class="whatsapp-link" target="_blank">Falar com o Filipe</a><br /><br />
    © 2025 Filipe Barber Shop
  </footer>

  <script>
    const form = document.getElementById('formAgendamento');
    const lista = document.getElementById('listaAgendamentos');
    const agendamentosDiv = document.querySelector('.agendamentos');

    function carregarAgendamentos() {
      lista.innerHTML = '';
      const agendamentos = JSON.parse(localStorage.getItem('agendamentos')) || [];

      agendamentos.forEach((ag, index) => {
        const div = document.createElement('div');
        const atendidoClass = ag.atendido ? ' atendido' : '';
        div.className = 'agendamento' + atendidoClass;

        div.innerHTML = `
          <strong>${ag.nome}</strong> ${ag.atendido ? '<span style="color:#4CAF50; font-weight:bold;">(Atendido)</span>' : ''}
          <br />
          📅 ${ag.data} ⏰ ${ag.hora}
          <br />
          ${!ag.atendido ? `<button onclick="marcarAtendido(${index})" class="btnAtendido">Marcar como atendido</button>` : ''}
        `;
        lista.appendChild(div);
      });
    }

    function marcarAtendido(index) {
      const agendamentos = JSON.parse(localStorage.getItem('agendamentos')) || [];
      agendamentos[index].atendido = true;
      localStorage.setItem('agendamentos', JSON.stringify(agendamentos));
      carregarAgendamentos();
    }

    form.addEventListener('submit', (e) => {
      e.preventDefault();

      const nome = document.getElementById('nome').value;
      const data = document.getElementById('data').value;
      const hora = document.getElementById('hora').value;

      const novo = { nome, data, hora, atendido: false };

      const agendamentos = JSON.parse(localStorage.getItem('agendamentos')) || [];
      agendamentos.push(novo);
      localStorage.setItem('agendamentos', JSON.stringify(agendamentos));

      form.reset();
      carregarAgendamentos();
    });

    window.onload = () => {
      const senha = prompt("Digite a senha para acessar os agendamentos:");

      if (senha === "barbeiro123") {
        agendamentosDiv.style.display = 'block';
        carregarAgendamentos();
      } else {
        alert("Senha incorreta. Lista de agendamentos não será exibida.");
        agendamentosDiv.style.display = 'none';
      }
    };
  </script>
</body>
</html>

