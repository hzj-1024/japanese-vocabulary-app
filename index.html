
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>日文單字複習</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: "Microsoft JhengHei", sans-serif;
      background: #f3f8f6;
      color: #263b35;
      line-height: 1.6;
    }
    header {
      background: #dcefe8;
      text-align: center;
      padding: 28px 15px;
    }
    header h1 { margin: 0 0 8px; }
    header p { margin: 0; }
    main { width: min(760px, 92%); margin: 25px auto; }
    .tabs { display: flex; gap: 10px; margin-bottom: 16px; }
    button {
      cursor: pointer;
      font-size: 16px;
      border-radius: 10px;
      padding: 11px 16px;
    }
    .tab {
      flex: 1;
      border: 1px solid #c8ddd5;
      background: white;
      color: #356c59;
    }
    .tab.active, .primary {
      background: #548c76;
      color: white;
      border: 1px solid #548c76;
    }
    .panel {
      background: white;
      border: 1px solid #e0eae5;
      border-radius: 16px;
      padding: 24px;
      box-shadow: 0 5px 18px #244c3b0d;
    }
    .hidden { display: none; }
    .progress { text-align: center; color: #708078; }
    .word-card {
      background: #f9fcfa;
      border: 1px solid #e0eae5;
      border-radius: 14px;
      padding: 28px 15px;
      margin: 18px 0;
      text-align: center;
    }
    .kana { color: #75847d; margin: 0; }
    .japanese { font-size: 42px; font-weight: bold; margin: 6px 0; }
    .meaning { color: #356c59; font-size: 24px; font-weight: bold; }
    .example { margin-top: 15px; }
    .example span { display: block; color: #75847d; }
    .actions { display: flex; flex-wrap: wrap; justify-content: center; gap: 10px; }
    .primary { border: 0; }
    .secondary { background: #edf5f1; color: #356c59; border: 1px solid #d7e7df; }
    .quiz-question { font-size: 21px; font-weight: bold; margin: 20px 0; }
    .options { display: grid; gap: 10px; }
    .option {
      background: white;
      border: 1px solid #dce7e1;
      color: #263b35;
      text-align: left;
      width: 100%;
    }
    .option:hover:not(:disabled) { background: #f1f8f4; }
    .option:disabled { cursor: default; }
    .option.correct { background: #e1f5e8; border-color: #55a574; }
    .option.wrong { background: #fff0f0; border-color: #d77b7b; }
    .feedback { min-height: 28px; font-weight: bold; margin: 12px 0; }
    .quiz-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 10px;
      margin-top: 18px;
    }
    .score { color: #708078; }
    footer { text-align: center; color: #708078; padding: 15px; }
    @media (max-width: 480px) {
      .panel { padding: 17px; }
      .japanese { font-size: 34px; }
      .quiz-footer { flex-direction: column; align-items: stretch; }
    }
  </style>
</head>
<body>
  <header>
    <h1>日文單字複習</h1>
    <p>每天複習一點點，讓日文慢慢進步！</p>
  </header>

  <main>
    <div class="tabs">
      <button class="tab active" id="studyTab" onclick="showPanel('study')">單字複習</button>
      <button class="tab" id="quizTab" onclick="showPanel('quiz')">小測驗</button>
    </div>

    <section class="panel" id="studyPanel">
      <p class="progress" id="wordProgress"></p>
      <div class="word-card">
        <p class="kana" id="wordKana"></p>
        <div class="japanese" id="wordJapanese"></div>
        <div class="meaning hidden" id="wordMeaning"></div>
        <div class="example hidden" id="wordExample">
          <strong id="exampleJapanese"></strong>
          <span id="exampleChinese"></span>
        </div>
      </div>
      <div class="actions">
        <button class="secondary" id="answerButton" onclick="toggleAnswer()">查看答案</button>
        <button class="primary" onclick="nextWord()">下一個單字 →</button>
      </div>
    </section>

    <section class="panel hidden" id="quizPanel">
      <h2>日文單字小測驗</h2>
      <p class="progress" id="quizProgress"></p>
      <div class="quiz-question" id="quizQuestion"></div>
      <div class="options" id="quizOptions"></div>
      <div class="feedback" id="quizFeedback" aria-live="polite"></div>
      <div class="quiz-footer">
        <span class="score" id="quizScore">目前答對：0 題</span>
        <button class="primary" id="nextQuestionButton" onclick="nextQuestion()" disabled>下一題 →</button>
      </div>
    </section>
  </main>

  <footer>日文單字複習小工具｜持續練習，一定會越來越進步！</footer>

  <script>
    const words = [
      { kanji: "食べる", kana: "たべる", meaning: "吃", example: "毎日、野菜を食べます。", translation: "每天吃蔬菜。" },
      { kanji: "飲む", kana: "のむ", meaning: "喝", example: "水を飲みます。", translation: "喝水。" },
      { kanji: "見る", kana: "みる", meaning: "看", example: "映画を見ます。", translation: "看電影。" },
      { kanji: "聞く", kana: "きく", meaning: "聽；詢問", example: "音楽を聞きます。", translation: "聽音樂。" },
      { kanji: "行く", kana: "いく", meaning: "去", example: "学校へ行きます。", translation: "去學校。" },
      { kanji: "来る", kana: "くる", meaning: "來", example: "友達が来ます。", translation: "朋友會來。" },
      { kanji: "帰る", kana: "かえる", meaning: "回家；回去", example: "家に帰ります。", translation: "回家。" },
      { kanji: "読む", kana: "よむ", meaning: "讀；看書", example: "本を読みます。", translation: "看書。" },
      { kanji: "書く", kana: "かく", meaning: "寫", example: "名前を書きます。", translation: "寫名字。" },
      { kanji: "買う", kana: "かう", meaning: "買", example: "パンを買います。", translation: "買麵包。" },
      { kanji: "話す", kana: "はなす", meaning: "說話", example: "日本語を話します。", translation: "說日文。" },
      { kanji: "勉強する", kana: "べんきょうする", meaning: "學習；讀書", example: "日本語を勉強します。", translation: "學習日文。" }
    ];

    let currentWord = 0;
    let answerVisible = false;
    let quizQuestions = [];
    let currentQuestion = 0;
    let correctCount = 0;
    let answered = false;

    function showPanel(name) {
      const study = name === "study";
      document.getElementById("studyPanel").classList.toggle("hidden", !study);
      document.getElementById("quizPanel").classList.toggle("hidden", study);
      document.getElementById("studyTab").classList.toggle("active", study);
      document.getElementById("quizTab").classList.toggle("active", !study);
      if (!study && quizQuestions.length === 0) startQuiz();
    }

    function renderWord() {
      const word = words[currentWord];
      document.getElementById("wordProgress").textContent =
        `第 ${currentWord + 1} / ${words.length} 個單字`;
      document.getElementById("wordKana").textContent = word.kana;
      document.getElementById("wordJapanese").textContent = word.kanji;
      document.getElementById("wordMeaning").textContent = word.meaning;
      document.getElementById("exampleJapanese").textContent = word.example;
      document.getElementById("exampleChinese").textContent = word.translation;
      answerVisible = false;
      document.getElementById("wordMeaning").classList.add("hidden");
      document.getElementById("wordExample").classList.add("hidden");
      document.getElementById("answerButton").textContent = "查看答案";
    }

    function toggleAnswer() {
      answerVisible = !answerVisible;
      document.getElementById("wordMeaning").classList.toggle("hidden", !answerVisible);
      document.getElementById("wordExample").classList.toggle("hidden", !answerVisible);
      document.getElementById("answerButton").textContent =
        answerVisible ? "隱藏答案" : "查看答案";
    }

    function nextWord() {
      currentWord = (currentWord + 1) % words.length;
      renderWord();
    }

    function startQuiz() {
      quizQuestions = [...words].sort(() => Math.random() - 0.5).slice(0, 5);
      currentQuestion = 0;
      correctCount = 0;
      answered = false;
      renderQuestion();
    }

    function renderQuestion() {
      const nextButton = document.getElementById("nextQuestionButton");

      if (currentQuestion >= quizQuestions.length) {
        document.getElementById("quizProgress").textContent = "測驗完成！";
        document.getElementById("quizQuestion").textContent =
          `你答對了 ${correctCount} / ${quizQuestions.length} 題！`;
        document.getElementById("quizOptions").innerHTML = "";
        document.getElementById("quizFeedback").textContent =
          correctCount === quizQuestions.length
            ? "太棒了！全部答對！"
            : "做得很好！再複習一次會更熟悉。";
        document.getElementById("quizScore").textContent =
          `最後成績：${correctCount} / ${quizQuestions.length} 題`;
        nextButton.textContent = "再測一次 ↻";
        nextButton.disabled = false;
        return;
      }

      answered = false;
      const question = quizQuestions[currentQuestion];
      document.getElementById("quizProgress").textContent =
        `第 ${currentQuestion + 1} / ${quizQuestions.length} 題`;
      document.getElementById("quizQuestion").textContent =
        `「${question.kanji}（${question.kana}）」是什麼意思？`;
      document.getElementById("quizFeedback").textContent = "";
      document.getElementById("quizScore").textContent = `目前答對：${correctCount} 題`;
      nextButton.textContent = "下一題 →";
      nextButton.disabled = true;

      const wrongChoices = words
        .filter(word => word.meaning !== question.meaning)
        .sort(() => Math.random() - 0.5)
        .slice(0, 3)
        .map(word => word.meaning);
      const choices = [...wrongChoices, question.meaning]
        .sort(() => Math.random() - 0.5);

      const options = document.getElementById("quizOptions");
      options.innerHTML = "";

      choices.forEach(choice => {
        const button = document.createElement("button");
        button.className = "option";
        button.textContent = choice;
        button.onclick = () => chooseAnswer(button, choice, question.meaning);
        options.appendChild(button);
      });
    }

    function chooseAnswer(button, choice, correctAnswer) {
      if (answered) return;
      answered = true;

      document.querySelectorAll(".option").forEach(option => {
        option.disabled = true;
        if (option.textContent === correctAnswer) {
          option.classList.add("correct");
        }
      });

      if (choice === correctAnswer) {
        correctCount++;
        document.getElementById("quizFeedback").textContent = "答對了！太棒了！";
      } else {
        button.classList.add("wrong");
        document.getElementById("quizFeedback").textContent =
          `正確答案是「${correctAnswer}」，再記一下喔！`;
      }

      document.getElementById("quizScore").textContent =
        `目前答對：${correctCount} 題`;
      document.getElementById("nextQuestionButton").disabled = false;
    }

    function nextQuestion() {
      if (currentQuestion >= quizQuestions.length) {
        startQuiz();
        return;
      }
      currentQuestion++;
      renderQuestion();
    }

    renderWord();
  </script>
</body>
</html>
