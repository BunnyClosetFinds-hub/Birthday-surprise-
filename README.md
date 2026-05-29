animation: float 8s infinite linear;
}

@keyframes float {
  from {
    transform: translateY(100vh) scale(0.5);
  }
  to {
    transform: translateY(-100vh) scale(1.2);
  }
}

  </style>
</head>
<body>  <div class="container" id="quizBox">
    <h1>🎂 Birthday Surprise 🎂</h1>
    <p id="question">Hey Birthday Boy 💖<br>Choose a path to unlock your surprise ✨</p><div id="options">
  <button class="option-btn" onclick="nextStep('music')">🎁 Open Gift Box</button>
  <button class="option-btn" onclick="nextStep('movie')">🍰 Cut the Cake</button>
  <button class="option-btn" onclick="nextStep('study')">💌 Read Secret Message</button>
</div>

  </div>  <script>
    const question = document.getElementById('question');
    const options = document.getElementById('options');

    function nextStep(choice) {
      if(choice === 'music') {
        question.innerHTML = '🎀 Which gift do you want first?';
        options.innerHTML = `
          <button class="option-btn" onclick="showAnswer('You unlocked unlimited hugs + happiness forever 🧸💖')">🧸 Cute Gift</button>
          <button class="option-btn" onclick="showAnswer('Surprise! You deserve the whole universe today 🌎✨')">🌟 Mystery Gift</button>
        `;
      }

      else if(choice === 'movie') {
        question.innerHTML = '🍰 Pick your birthday cake flavor';
        options.innerHTML = `
          <button class="option-btn" onclick="showAnswer('Chocolate cake chosen 🍫 = extra birthday luck unlocked ✨')">🍫 Chocolate</button>
          <button class="option-btn" onclick="showAnswer('Strawberry cake chosen 🍓 = cutest birthday energy ever 💕')">🍓 Strawberry</button>
        `;
      }

      else if(choice === 'study') {
        question.innerHTML = '💌 Ready for your secret message?';
        options.innerHTML = `
          <button class="option-btn" onclick="showAnswer('Happy Birthday 💖 You make life brighter and today is all about you ✨')">💖 Open Message</button>
          <button class="option-btn" onclick="showAnswer('Plot twist: you are officially the main character today 👑')">👑 Another Surprise</button>
        `;
      }
    }

    function showAnswer(text) {
      question.innerHTML = '💌 Final Answer';
      options.innerHTML = `
        <p style="font-size:1.2rem; color:#ff4fa3; margin-bottom:20px;">${text}</p>
        <button class="option-btn" onclick="location.reload()">🔄 Start Again</button>
      `;
    }

