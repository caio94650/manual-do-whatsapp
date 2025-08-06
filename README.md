<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Manual do WhatsApp</title>
  <style>
    body {
      font-family: sans-serif;
      background-color: #e5ddd5;
      margin: 0;
      padding: 0;
    }
    .chat-container {
      max-width: 400px;
      margin: 40px auto;
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      overflow: hidden;
    }
    .header {
      background: #075e54;
      color: white;
      padding: 15px;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .header img {
      border-radius: 50%;
      height: 40px;
      width: 40px;
    }
    .chat-box {
      padding: 20px;
    }
    .message {
      max-width: 75%;
      padding: 10px 14px;
      border-radius: 7px;
      margin-bottom: 10px;
      line-height: 1.4;
      position: relative;
    }
    .bot {
      background-color: #dcf8c6;
      align-self: flex-start;
    }
    .user {
      background-color: #fff;
      border: 1px solid #ccc;
      align-self: flex-end;
      margin-left: auto;
    }
    .button-group {
      display: flex;
      flex-direction: column;
      gap: 10px;
      margin-top: 20px;
    }
    .button-group button {
      padding: 10px;
      border: none;
      background: #25d366;
      color: white;
      font-size: 16px;
      border-radius: 6px;
      cursor: pointer;
    }
    .button-group button:hover {
      background: #128c7e;
    }
  </style>
</head>
<body>

<div class="chat-container">
  <div class="header">
    <img src="https://cdn-icons-png.flaticon.com/512/4712/4712038.png" alt="Bot">
    <strong>SharkBot</strong>
  </div>
  <div class="chat-box" id="chatBox">
    <!-- Mensagens serão inseridas via JS -->
  </div>
</div>

<script>
  const chatBox = document.getElementById('chatBox');

  const messages = [
    { type: 'bot', text: 'Olá! 👋 Eu sou o SharkBot.' },
    { type: 'bot', text: 'Você quer aprender como aquecer o WhatsApp sem risco de banimento?' },
    { type: 'button', options: ['Sim, quero o manual 📘', 'Me explica melhor antes 🤔'] },
    { type: 'bot', text: 'Perfeito! Com esse guia, você vai aprender a proteger seus números e escalar com segurança.' },
    { type: 'bot', text: 'Clique no botão abaixo para receber o eBook agora mesmo via WhatsApp.' },
    { type: 'button', options: ['Receber via WhatsApp'] },
    { type: 'bot', text: '💡 Bônus: lá no WhatsApp, você também vai descobrir como automatizar o aquecimento com apenas 1 clique usando o SharkBotzap.' }
  ];

  let index = 0;

  function showMessage() {
    if (index >= messages.length) return;

    const msg = messages[index];

    if (msg.type === 'bot') {
      const div = document.createElement('div');
      div.className = 'message bot';
      div.innerText = msg.text;
      chatBox.appendChild(div);
    } else if (msg.type === 'button') {
      const div = document.createElement('div');
      div.className = 'button-group';
      msg.options.forEach(option => {
        const btn = document.createElement('button');
        btn.innerText = option;
        btn.onclick = () => {
          const userMsg = document.createElement('div');
          userMsg.className = 'message user';
          userMsg.innerText = option;
          chatBox.appendChild(userMsg);

          if (option.includes('WhatsApp')) {
            window.location.href = 'https://encurtador.com.br/cEiuS';
          } else {
            index++;
            showMessage();
          }
        };
        div.appendChild(btn);
      });
      chatBox.appendChild(div);
    }

    chatBox.scrollTop = chatBox.scrollHeight;
    index++;

    if (msg.type === 'bot') {
      setTimeout(showMessage, 1200);
    }
  }

  // Iniciar conversa
  setTimeout(showMessage, 800);
</script>

</body>
</html>
