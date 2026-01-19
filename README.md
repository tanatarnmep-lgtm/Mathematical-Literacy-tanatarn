<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์การเงิน ป.5</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
      font-family: 'Kanit', sans-serif;
    }
    
    .coin-float {
      animation: float 3s ease-in-out infinite;
    }
    
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    
    .sparkle {
      animation: sparkle 1.5s ease-in-out infinite;
    }
    
    @keyframes sparkle {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(1.2); }
    }
    
    .bounce-in {
      animation: bounceIn 0.5s ease-out;
    }
    
    @keyframes bounceIn {
      0% { transform: scale(0); opacity: 0; }
      50% { transform: scale(1.1); }
      100% { transform: scale(1); opacity: 1; }
    }
    
    .slide-up {
      animation: slideUp 0.4s ease-out;
    }
    
    @keyframes slideUp {
      from { transform: translateY(20px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }
    
    .money-icon {
      filter: drop-shadow(0 2px 4px rgba(0,0,0,0.2));
    }
    
    .gradient-bg {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    }
    
    .card-shadow {
      box-shadow: 0 10px 40px rgba(102, 126, 234, 0.3);
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app-container" class="min-h-full w-full gradient-bg overflow-auto"><!-- Header -->
   <header class="py-6 px-4 text-center">
    <div class="flex items-center justify-center gap-3 mb-2"><span class="text-4xl coin-float">💰</span>
     <h1 id="main-title" class="text-2xl md:text-3xl font-bold text-white drop-shadow-lg">คณิตศาสตร์การเงิน ป.5</h1><span class="text-4xl coin-float" style="animation-delay: 0.5s;">🪙</span>
    </div>
    <p class="text-purple-100 text-sm">เรียนรู้เรื่องเงินอย่างสนุกสนาน!</p>
   </header><!-- Score Display -->
   <div class="flex justify-center gap-4 px-4 mb-6">
    <div class="bg-white/20 backdrop-blur-sm rounded-2xl px-4 py-2 flex items-center gap-2"><span class="text-2xl">⭐</span>
     <div class="text-white">
      <div class="text-xs">
       คะแนน
      </div>
      <div id="score" class="text-xl font-bold">
       0
      </div>
     </div>
    </div>
    <div class="bg-white/20 backdrop-blur-sm rounded-2xl px-4 py-2 flex items-center gap-2"><span class="text-2xl">🏆</span>
     <div class="text-white">
      <div class="text-xs">
       ด่าน
      </div>
      <div id="level" class="text-xl font-bold">
       1
      </div>
     </div>
    </div>
    <div class="bg-white/20 backdrop-blur-sm rounded-2xl px-4 py-2 flex items-center gap-2"><span class="text-2xl">❤️</span>
     <div class="text-white">
      <div class="text-xs">
       ชีวิต
      </div>
      <div id="lives" class="text-xl font-bold">
       3
      </div>
     </div>
    </div>
   </div><!-- Main Content -->
   <main class="px-4 pb-8"><!-- Creator Info -->
    <div class="max-w-md mx-auto mb-4">
     <div class="bg-white/90 backdrop-blur-sm rounded-2xl px-4 py-3 text-center shadow-lg">
      <div class="flex items-center justify-center gap-2 text-sm"><span class="text-xl">👨‍💻</span>
       <div class="text-purple-800"><span class="font-semibold">สร้างโดย:</span> เด็กชาย ธนธาร วงศ์กุหมัด <span class="text-purple-600 ml-1">ป.5 MEP</span>
       </div>
      </div>
     </div>
    </div><!-- Menu Screen -->
    <div id="menu-screen" class="max-w-md mx-auto">
     <div class="bg-white rounded-3xl p-6 card-shadow slide-up">
      <h2 class="text-xl font-bold text-purple-800 text-center mb-6">🎮 เลือกโหมดเรียนรู้</h2>
      <div class="space-y-4"><button onclick="startMode('coins')" class="w-full bg-gradient-to-r from-yellow-400 to-orange-500 hover:from-yellow-500 hover:to-orange-600 text-white font-bold py-4 px-6 rounded-2xl transition-all transform hover:scale-105 flex items-center gap-4"> <span class="text-3xl">🪙</span>
        <div class="text-left">
         <div class="text-lg">
          นับเหรียญ
         </div>
         <div class="text-xs opacity-80">
          ฝึกนับเหรียญชนิดต่างๆ
         </div>
        </div></button> <button onclick="startMode('bills')" class="w-full bg-gradient-to-r from-green-400 to-emerald-500 hover:from-green-500 hover:to-emerald-600 text-white font-bold py-4 px-6 rounded-2xl transition-all transform hover:scale-105 flex items-center gap-4"> <span class="text-3xl">💵</span>
        <div class="text-left">
         <div class="text-lg">
          นับธนบัตร
         </div>
         <div class="text-xs opacity-80">
          ฝึกนับธนบัตรชนิดต่างๆ
         </div>
        </div></button> <button onclick="startMode('shopping')" class="w-full bg-gradient-to-r from-pink-400 to-rose-500 hover:from-pink-500 hover:to-rose-600 text-white font-bold py-4 px-6 rounded-2xl transition-all transform hover:scale-105 flex items-center gap-4"> <span class="text-3xl">🛒</span>
        <div class="text-left">
         <div class="text-lg">
          ซื้อของ
         </div>
         <div class="text-xs opacity-80">
          คำนวณเงินซื้อของและทอน
         </div>
        </div></button> <button onclick="startMode('problem')" class="w-full bg-gradient-to-r from-blue-400 to-indigo-500 hover:from-blue-500 hover:to-indigo-600 text-white font-bold py-4 px-6 rounded-2xl transition-all transform hover:scale-105 flex items-center gap-4"> <span class="text-3xl">🧮</span>
        <div class="text-left">
         <div class="text-lg">
          โจทย์ปัญหา
         </div>
         <div class="text-xs opacity-80">
          แก้โจทย์ปัญหาเกี่ยวกับเงิน
         </div>
        </div></button>
      </div>
     </div>
    </div><!-- Game Screen -->
    <div id="game-screen" class="max-w-md mx-auto hidden">
     <div class="bg-white rounded-3xl p-6 card-shadow slide-up">
      <div class="flex items-center justify-between mb-4"><button onclick="backToMenu()" class="text-purple-600 hover:text-purple-800 font-medium flex items-center gap-1"> <span>←</span> กลับ </button>
       <div id="question-number" class="text-sm text-gray-500">
        ข้อ 1/10
       </div>
      </div>
      <div id="question-area" class="text-center"><!-- Question content will be inserted here -->
      </div>
      <div id="answer-area" class="mt-6"><!-- Answer options will be inserted here -->
      </div>
      <div id="feedback" class="mt-4 text-center hidden"><!-- Feedback will be shown here -->
      </div>
     </div>
    </div><!-- Result Screen -->
    <div id="result-screen" class="max-w-md mx-auto hidden">
     <div class="bg-white rounded-3xl p-8 card-shadow bounce-in text-center">
      <div id="result-icon" class="text-6xl mb-4">
       🎉
      </div>
      <h2 id="result-title" class="text-2xl font-bold text-purple-800 mb-2">ยอดเยี่ยม!</h2>
      <p id="result-message" class="text-gray-600 mb-4">คุณได้คะแนน 80 จาก 100</p>
      <div id="result-stars" class="text-4xl mb-6">
       ⭐⭐⭐
      </div>
      <div class="space-y-3"><button onclick="restartGame()" class="w-full bg-gradient-to-r from-purple-500 to-indigo-600 hover:from-purple-600 hover:to-indigo-700 text-white font-bold py-3 px-6 rounded-xl transition-all"> 🔄 เล่นอีกครั้ง </button> <button onclick="backToMenu()" class="w-full bg-gray-200 hover:bg-gray-300 text-gray-700 font-bold py-3 px-6 rounded-xl transition-all"> 🏠 กลับหน้าหลัก </button>
      </div>
     </div>
    </div>
   </main>
  </div>
  <script>
    // Default configuration
    const defaultConfig = {
      app_title: 'คณิตศาสตร์การเงิน ป.5',
      primary_color: '#667eea',
      secondary_color: '#764ba2',
      text_color: '#1e1b4b',
      accent_color: '#f59e0b',
      background_color: '#667eea'
    };

    let config = { ...defaultConfig };

    // Game state
    let gameState = {
      mode: '',
      score: 0,
      level: 1,
      lives: 3,
      currentQuestion: 0,
      totalQuestions: 10,
      correctAnswers: 0,
      questions: []
    };

    // Thai currency data
    const coins = [
      { value: 0.25, name: '25 สตางค์', emoji: '🪙' },
      { value: 0.50, name: '50 สตางค์', emoji: '🪙' },
      { value: 1, name: '1 บาท', emoji: '🪙' },
      { value: 2, name: '2 บาท', emoji: '🪙' },
      { value: 5, name: '5 บาท', emoji: '🪙' },
      { value: 10, name: '10 บาท', emoji: '🪙' }
    ];

    const bills = [
      { value: 20, name: '20 บาท', color: 'bg-green-500' },
      { value: 50, name: '50 บาท', color: 'bg-blue-500' },
      { value: 100, name: '100 บาท', color: 'bg-red-500' },
      { value: 500, name: '500 บาท', color: 'bg-purple-500' },
      { value: 1000, name: '1,000 บาท', color: 'bg-gray-600' }
    ];

    const items = [
      { name: 'ดินสอ', price: 5, emoji: '✏️' },
      { name: 'ยางลบ', price: 8, emoji: '🧽' },
      { name: 'ไม้บรร�����ด', price: 12, emoji: '📏' },
      { name: 'สมุด', price: 15, emoji: '📓' },
      { name: 'ปากกา', price: 18, emoji: '🖊️' },
      { name: 'กาว', price: 25, emoji: '🧴' },
      { name: 'กรรไกร', price: 35, emoji: '✂️' },
      { name: 'ขนม', price: 10, emoji: '🍪' },
      { name: 'น้ำดื่ม', price: 7, emoji: '💧' },
      { name: 'นม', price: 13, emoji: '🥛' },
      { name: 'ขนมปัง', price: 20, emoji: '🍞' },
      { name: 'ไอศกรีม', price: 15, emoji: '🍦' }
    ];

    // Initialize SDK
    function initApp() {
      if (window.elementSdk) {
        window.elementSdk.init({
          defaultConfig,
          onConfigChange: async (newConfig) => {
            config = { ...defaultConfig, ...newConfig };
            updateUI();
          },
          mapToCapabilities: (cfg) => ({
            recolorables: [
              {
                get: () => cfg.background_color || defaultConfig.background_color,
                set: (value) => {
                  cfg.background_color = value;
                  window.elementSdk.setConfig({ background_color: value });
                }
              },
              {
                get: () => cfg.accent_color || defaultConfig.accent_color,
                set: (value) => {
                  cfg.accent_color = value;
                  window.elementSdk.setConfig({ accent_color: value });
                }
              }
            ],
            borderables: [],
            fontEditable: {
              get: () => cfg.font_family || 'Kanit',
              set: (value) => {
                cfg.font_family = value;
                window.elementSdk.setConfig({ font_family: value });
              }
            },
            fontSizeable: undefined
          }),
          mapToEditPanelValues: (cfg) => new Map([
            ['app_title', cfg.app_title || defaultConfig.app_title]
          ])
        });
      }
      updateUI();
    }

    function updateUI() {
      const title = document.getElementById('main-title');
      if (title) {
        title.textContent = config.app_title || defaultConfig.app_title;
      }
      
      const container = document.getElementById('app-container');
      if (container) {
        const bgColor = config.background_color || defaultConfig.background_color;
        container.style.background = `linear-gradient(135deg, ${bgColor} 0%, ${adjustColor(bgColor, -30)} 100%)`;
      }
      
      if (config.font_family) {
        document.body.style.fontFamily = `${config.font_family}, Kanit, sans-serif`;
      }
    }

    function adjustColor(hex, amount) {
      const num = parseInt(hex.replace('#', ''), 16);
      const r = Math.min(255, Math.max(0, (num >> 16) + amount));
      const g = Math.min(255, Math.max(0, ((num >> 8) & 0x00FF) + amount));
      const b = Math.min(255, Math.max(0, (num & 0x0000FF) + amount));
      return '#' + (0x1000000 + (r << 16) + (g << 8) + b).toString(16).slice(1);
    }

    function startMode(mode) {
      gameState = {
        mode,
        score: 0,
        level: 1,
        lives: 3,
        currentQuestion: 0,
        totalQuestions: 10,
        correctAnswers: 0,
        questions: generateQuestions(mode)
      };
      
      updateScoreDisplay();
      showScreen('game');
      showQuestion();
    }

    function generateQuestions(mode) {
      const questions = [];
      
      for (let i = 0; i < 10; i++) {
        switch(mode) {
          case 'coins':
            questions.push(generateCoinQuestion());
            break;
          case 'bills':
            questions.push(generateBillQuestion());
            break;
          case 'shopping':
            questions.push(generateShoppingQuestion());
            break;
          case 'problem':
            questions.push(generateProblemQuestion());
            break;
        }
      }
      
      return questions;
    }

    function generateCoinQuestion() {
      const selectedCoins = [];
      const count = Math.floor(Math.random() * 4) + 2;
      let total = 0;
      
      for (let i = 0; i < count; i++) {
        const coin = coins[Math.floor(Math.random() * coins.length)];
        selectedCoins.push(coin);
        total += coin.value;
      }
      
      total = Math.round(total * 100) / 100;
      
      const options = generateOptions(total);
      
      return {
        type: 'coins',
        display: selectedCoins,
        question: 'เหรียญเหล่านี้รวมกันเป็นเงินเท่าไร?',
        answer: total,
        options
      };
    }

    function generateBillQuestion() {
      const selectedBills = [];
      const count = Math.floor(Math.random() * 3) + 1;
      let total = 0;
      
      for (let i = 0; i < count; i++) {
        const bill = bills[Math.floor(Math.random() * bills.length)];
        selectedBills.push(bill);
        total += bill.value;
      }
      
      const options = generateOptions(total);
      
      return {
        type: 'bills',
        display: selectedBills,
        question: 'ธนบัตรเหล่านี้รวมกันเป็นเงินเท่าไร?',
        answer: total,
        options
      };
    }

    function generateShoppingQuestion() {
      const item1 = items[Math.floor(Math.random() * items.length)];
      let item2 = items[Math.floor(Math.random() * items.length)];
      while (item2.name === item1.name) {
        item2 = items[Math.floor(Math.random() * items.length)];
      }
      
      const questionType = Math.random() > 0.5 ? 'total' : 'change';
      
      if (questionType === 'total') {
        const total = item1.price + item2.price;
        return {
          type: 'shopping',
          questionType: 'total',
          items: [item1, item2],
          question: `ซื้อ${item1.name} ${item1.price} บาท และ ${item2.name} ${item2.price} บาท ต้องจ่ายเงินทั้งหมดเท่าไร?`,
          answer: total,
          options: generateOptions(total)
        };
      } else {
        const paid = Math.ceil((item1.price) / 10) * 10 + 10;
        const change = paid - item1.price;
        return {
          type: 'shopping',
          questionType: 'change',
          items: [item1],
          paid,
          question: `ซื้อ${item1.name} ${item1.price} บาท จ่าย ${paid} ���าท ได้เงินทอนเท่าไร?`,
          answer: change,
          options: generateOptions(change)
        };
      }
    }

    function generateProblemQuestion() {
      const problems = [
        () => {
          const a = Math.floor(Math.random() * 50) + 20;
          const b = Math.floor(Math.random() * 30) + 10;
          return {
            question: `แม่ให้เงินค่าขนม ${a} บาท ใช้ไป ${b} บาท เหลือเงินเท่าไร?`,
            answer: a - b
          };
        },
        () => {
          const daily = Math.floor(Math.random() * 20) + 10;
          const days = Math.floor(Math.random() * 5) + 2;
          return {
            question: `ออมเงินวันละ ${daily} บาท เป็นเวลา ${days} วัน จะมีเงินออมเท่��ไร?`,
            answer: daily * days
          };
        },
        () => {
          const total = Math.floor(Math.random() * 100) + 50;
          const people = Math.floor(Math.random() * 4) + 2;
          const share = Math.floor(total / people);
          return {
            question: `มีเงิน ${share * people} บาท แบ่งให้เพื่อน ${people} คน เท่าๆ ก��น แต่ละคนได้กี่��าท?`,
            answer: share
          };
        },
        () => {
          const item = items[Math.floor(Math.random() * items.length)];
          const qty = Math.floor(Math.random() * 3) + 2;
          return {
            question: `${item.name}ราคา ${item.price} บาท ซื้อ ${qty} อัน ต้องจ่ายเงินกี่บาท?`,
            answer: item.price * qty
          };
        }
      ];
      
      const problem = problems[Math.floor(Math.random() * problems.length)]();
      return {
        type: 'problem',
        question: problem.question,
        answer: problem.answer,
        options: generateOptions(problem.answer)
      };
    }

    function generateOptions(correctAnswer) {
      const options = [correctAnswer];
      
      while (options.length < 4) {
        let wrong;
        const variance = Math.max(5, Math.abs(correctAnswer * 0.3));
        wrong = correctAnswer + (Math.floor(Math.random() * variance * 2) - variance);
        wrong = Math.round(wrong * 100) / 100;
        
        if (wrong > 0 && wrong !== correctAnswer && !options.includes(wrong)) {
          options.push(wrong);
        }
      }
      
      return shuffleArray(options);
    }

    function shuffleArray(array) {
      const newArray = [...array];
      for (let i = newArray.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [newArray[i], newArray[j]] = [newArray[j], newArray[i]];
      }
      return newArray;
    }

    function showQuestion() {
      const question = gameState.questions[gameState.currentQuestion];
      document.getElementById('question-number').textContent = 
        `ข้อ ${gameState.currentQuestion + 1}/${gameState.totalQuestions}`;
      
      const questionArea = document.getElementById('question-area');
      const answerArea = document.getElementById('answer-area');
      
      let displayHTML = '';
      
      if (question.type === 'coins') {
        displayHTML = `
          <div class="flex flex-wrap justify-center gap-2 mb-4">
            ${question.display.map(coin => `
              <div class="w-14 h-14 rounded-full bg-gradient-to-br from-yellow-300 to-yellow-500 flex items-center justify-center shadow-lg money-icon">
                <span class="text-xs font-bold text-yellow-900">${coin.value >= 1 ? coin.value + '฿' : (coin.value * 100) + 'ส.'}</span>
              </div>
            `).join('')}
          </div>
          <p class="text-lg font-medium text-gray-800">${question.question}</p>
        `;
      } else if (question.type === 'bills') {
        displayHTML = `
          <div class="flex flex-wrap justify-center gap-2 mb-4">
            ${question.display.map(bill => `
              <div class="w-20 h-10 ${bill.color} rounded flex items-center justify-center shadow-lg money-icon">
                <span class="text-xs font-bold text-white">${bill.value}฿</span>
              </div>
            `).join('')}
          </div>
          <p class="text-lg font-medium text-gray-800">${question.question}</p>
        `;
      } else if (question.type === 'shopping') {
        displayHTML = `
          <div class="flex flex-wrap justify-center gap-4 mb-4">
            ${question.items.map(item => `
              <div class="bg-purple-50 rounded-xl p-3 text-center">
                <span class="text-3xl">${item.emoji}</span>
                <div class="text-sm font-medium">${item.name}</div>
                <div class="text-purple-600 font-bold">${item.price} บาท</div>
              </div>
            `).join('')}
          </div>
          <p class="text-lg font-medium text-gray-800">${question.question}</p>
        `;
      } else {
        displayHTML = `
          <div class="text-4xl mb-4">🤔</div>
          <p class="text-lg font-medium text-gray-800">${question.question}</p>
        `;
      }
      
      questionArea.innerHTML = displayHTML;
      
      answerArea.innerHTML = `
        <div class="grid grid-cols-2 gap-3">
          ${question.options.map((option, index) => `
            <button onclick="checkAnswer(${option})" class="bg-purple-100 hover:bg-purple-200 text-purple-800 font-bold py-3 px-4 rounded-xl transition-all transform hover:scale-105">
              ${formatMoney(option)}
            </button>
          `).join('')}
        </div>
      `;
      
      document.getElementById('feedback').classList.add('hidden');
    }

    function formatMoney(amount) {
      if (amount < 1) {
        return (amount * 100) + ' สตางค์';
      }
      return amount.toLocaleString() + ' บาท';
    }

    function checkAnswer(selected) {
      const question = gameState.questions[gameState.currentQuestion];
      const feedback = document.getElementById('feedback');
      const isCorrect = Math.abs(selected - question.answer) < 0.01;
      
      if (isCorrect) {
        gameState.score += 10;
        gameState.correctAnswers++;
        feedback.innerHTML = `
          <div class="bounce-in text-green-500">
            <span class="text-4xl">🎉</span>
            <p class="font-bold text-lg">ถูกต้อง!</p>
            <p class="text-sm">+10 คะแนน</p>
          </div>
        `;
      } else {
        gameState.lives--;
        feedback.innerHTML = `
          <div class="bounce-in text-red-500">
            <span class="text-4xl">😢</span>
            <p class="font-bold text-lg">ไม่ถูกต้อง</p>
            <p class="text-sm">คำตอบคือ ${formatMoney(question.answer)}</p>
          </div>
        `;
      }
      
      feedback.classList.remove('hidden');
      updateScoreDisplay();
      
      // Disable answer buttons
      const buttons = document.querySelectorAll('#answer-area button');
      buttons.forEach(btn => {
        btn.disabled = true;
        btn.classList.add('opacity-50');
      });
      
      setTimeout(() => {
        if (gameState.lives <= 0) {
          showResults();
        } else if (gameState.currentQuestion < gameState.totalQuestions - 1) {
          gameState.currentQuestion++;
          showQuestion();
        } else {
          showResults();
        }
      }, 1500);
    }

    function updateScoreDisplay() {
      document.getElementById('score').textContent = gameState.score;
      document.getElementById('level').textContent = gameState.level;
      document.getElementById('lives').textContent = gameState.lives;
    }

    function showResults() {
      const percentage = (gameState.correctAnswers / gameState.totalQuestions) * 100;
      let stars = '';
      let icon = '';
      let title = '';
      
      if (percentage >= 80) {
        stars = '⭐⭐⭐';
        icon = '🎉';
        title = 'ยอดเยี่ยมมาก!';
      } else if (percentage >= 60) {
        stars = '⭐⭐';
        icon = '👍';
        title = 'ดีมาก!';
      } else if (percentage >= 40) {
        stars = '⭐';
        icon = '💪';
        title = 'พยายามต่อไป!';
      } else {
        stars = '';
        icon = '📚';
        title = 'ฝึกฝนเพิ่มเติมนะ';
      }
      
      document.getElementById('result-icon').textContent = icon;
      document.getElementById('result-title').textContent = title;
      document.getElementById('result-message').textContent = 
        `คุณตอบ��ูก ${gameState.correctAnswers} จาก ${gameState.totalQuestions} ข้อ (${percentage}%)`;
      document.getElementById('result-stars').textContent = stars || '🌟';
      
      showScreen('result');
    }

    function restartGame() {
      startMode(gameState.mode);
    }

    function backToMenu() {
      gameState = {
        mode: '',
        score: 0,
        level: 1,
        lives: 3,
        currentQuestion: 0,
        totalQuestions: 10,
        correctAnswers: 0,
        questions: []
      };
      updateScoreDisplay();
      showScreen('menu');
    }

    function showScreen(screen) {
      document.getElementById('menu-screen').classList.add('hidden');
      document.getElementById('game-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.add('hidden');
      document.getElementById(`${screen}-screen`).classList.remove('hidden');
    }

    // Initialize app
    initApp();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c031ccfb4e27325',t:'MTc2ODc5MTk0OS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
