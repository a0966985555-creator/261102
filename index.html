<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>高中英文選擇題測驗系統</title>

  <!-- 引入需求指定字型 (LXGW WenKai TC 與 Fraunces) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,100..900;1,9..144,100..900&family=LXGW+WenKai+TC&display=swap" rel="stylesheet">

  <!-- 載入 p5.js 函式庫 -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.9.0/p5.min.js"></script>

  <style>
    * { box-sizing: border-box; }
    html, body {
      margin: 0;
      padding: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      background-color: #f5f7fa;
    }
  </style>
</head>
<body>
<script>
// =================================================================
// 題庫資料 (模擬讀取 questions.csv 後隨機抽出 5 題)
// =================================================================
const csvData = [
  { question: "She decided to _______ her dream of studying abroad after winning the competition.", options: ["pursue", "persuade", "preserve", "prevent"], answer: 0, explanation: "pursue 意為「追求（夢想、學業）」，最符合句意。" },
  { question: "The heavy rain caused severe _______ in the low-lying valley area.", options: ["floods", "fleets", "fleeces", "flights"], answer: 0, explanation: "floods 意為「洪水、水災」，符合暴雨造成災害的情境。" },
  { question: "It is essential to _______ regular exercise into your daily schedule.", options: ["incorporate", "interpret", "investigate", "isolate"], answer: 0, explanation: "incorporate 意為「納入、結合」，為高中常見高頻動詞。" },
  { question: "The scientist made a groundbreaking _______ in cancer treatment.", options: ["discovery", "disaster", "disgrace", "discount"], answer: 0, explanation: "discovery 意為「重大發現」，符合科學研究成果。" },
  { question: "Despite many difficulties, he remained _______ about his future.", options: ["optimistic", "pessimistic", "suspicious", "jealous"], answer: 0, explanation: "optimistic 意為「樂觀的」，與前句「儘管困難」形成對比。" },
  { question: "Please make sure to _______ your essay carefully before submitting it.", options: ["review", "remove", "replace", "rely"], answer: 0, explanation: "review 意為「檢查、審視」，繳交前需再次檢查。" },
  { question: "The company offers a wide _______ of services to satisfy customers.", options: ["variety", "victim", "victory", "vessel"], answer: 0, explanation: "a wide variety of 意為「各式各樣的」，為固定搭配用法。" }
];

// =================================================================
// 全域狀態變數
// =================================================================
let questions = [];      // 總題庫
let quizList = [];       // 隨機抽取的 5 題
let currentIndex = 0;    // 當前題目索引 (0~4)
let score = 0;           // 答對題數
let favorability = 0;    // NPC 好感度 (0~100)
let selectedOption = null; // 當前選擇選項 (0~3)
let isAnswered = false;     // 當前題目是否已作答

// 動畫特效變數
let heartAnimTimer = 0;   // +20 愛心動畫計時器 (3秒 = 180幀)
let showHeartAnim = false; // 是否顯示 +20 動畫

// 1. 初始化設定
function setup() {
  createCanvas(windowWidth, windowHeight);
  questions = [...csvData];
  startNewQuiz();
}

// 2. 隨機抽出 5 題開始新測驗
function startNewQuiz() {
  let shuffled = shuffle([...questions]);
  quizList = shuffled.slice(0, 5);
  currentIndex = 0;
  score = 0;
  favorability = 0;
  resetQuestionState();
}

// 重置單題狀態
function resetQuestionState() {
  selectedOption = null;
  isAnswered = false;
}

// 3. 主要繪製迴圈
function draw() {
  background(245, 247, 250);

  drawHeader();     // 標題與進度
  drawNPCSection(); // 左側灰色貓咪 NPC 與好感度列

  if (currentIndex < 5) {
    drawQuizSection(); // 題目與選項
  } else {
    drawResultSection(); // 結算畫面
  }

  // 處理「❤️ +20」動效 (持續 3 秒消失)
  if (showHeartAnim) {
    drawHeartAnimation();
    heartAnimTimer--;
    if (heartAnimTimer <= 0) {
      showHeartAnim = false;
    }
  }
}

// 繪製上方標題
function drawHeader() {
  push();
  textFont('LXGW WenKai TC');
  textSize(Math.min(width * 0.032, 26));
  fill(50);
  textAlign(CENTER, TOP);
  text("高中英文互動測驗系統", width / 2, height * 0.03);

  if (currentIndex < 5) {
    textSize(Math.min(width * 0.018, 16));
    fill(100);
    text(`目前進度：第 ${currentIndex + 1} 題 / 共 5 題`, width / 2, height * 0.08);
  }
  pop();
}

// 繪製灰色貓咪 NPC 與好感度
function drawNPCSection() {
  push();
  let npcSize = Math.min(width, height) * 0.22;
  let npcX = width * 0.16;
  let npcY = height * 0.30;

  // 繪製精美可愛的灰色貓咪 NPC
  drawCuteGreyCat(npcX, npcY, npcSize);

  // 好感度進度條
  textAlign(CENTER, TOP);
  textFont('LXGW WenKai TC');
  textSize(16);
  fill(60);
  text(`NPC 好感度: ${favorability} / 100`, npcX, npcY + npcSize / 2 + 15);

  let barW = npcSize * 1.1;
  let barH = 12;
  let barX = npcX - barW / 2;
  let barY = npcY + npcSize / 2 + 40;
  fill(225);
  noStroke();
  rect(barX, barY, barW, barH, 6);

  fill(235, 85, 85);
  let filledW = (favorability / 100) * barW;
  rect(barX, barY, filledW, barH, 6);

  // 結算結果特寫：答對率 >= 60% 冒出❤️，<= 40% 冒出💔
  if (currentIndex >= 5) {
    let accuracy = (score / 5) * 100;
    textSize(42);
    if (accuracy >= 60) {
      text("❤️", npcX, npcY - npcSize / 2 - 45);
    } else if (accuracy <= 40) {
      text("💔", npcX, npcY - npcSize / 2 - 45);
    }
  }
  pop();
}

// 簡潔可愛的灰色貓咪繪製邏輯
function drawCuteGreyCat(x, y, s) {
  push();
  translate(x, y);

  stroke(60);
  strokeWeight(Math.max(2, s * 0.025));

  // 1. 貓咪耳朵 (深灰色)
  fill(120, 125, 135);
  triangle(-s * 0.35, -s * 0.1, -s * 0.42, -s * 0.42, -s * 0.12, -s * 0.32);
  triangle(s * 0.35, -s * 0.1, s * 0.42, -s * 0.42, s * 0.12, -s * 0.32);

  // 耳內粉色
  fill(245, 180, 190);
  noStroke();
  triangle(-s * 0.32, -s * 0.15, -s * 0.38, -s * 0.36, -s * 0.16, -s * 0.28);
  triangle(s * 0.32, -s * 0.15, s * 0.38, -s * 0.36, s * 0.16, -s * 0.28);

  // 2. 貓咪圓潤頭部 (灰色)
  stroke(60);
  strokeWeight(Math.max(2, s * 0.025));
  fill(160, 165, 175);
  ellipse(0, 0, s * 0.85, s * 0.72);

  // 3. 腮紅
  noStroke();
  fill(255, 170, 180, 150);
  ellipse(-s * 0.26, s * 0.1, s * 0.14, s * 0.09);
  ellipse(s * 0.26, s * 0.1, s * 0.14, s * 0.09);

  // 4. 大眼睛 (深色瞳孔 + 白色光點)
  stroke(40);
  strokeWeight(Math.max(2, s * 0.02));
  fill(40);
  ellipse(-s * 0.18, -s * 0.04, s * 0.14, s * 0.18);
  ellipse(s * 0.18, -s * 0.04, s * 0.14, s * 0.18);

  // 眼睛小白光點
  noStroke();
  fill(255);
  ellipse(-s * 0.21, -s * 0.07, s * 0.05, s * 0.05);
  ellipse(s * 0.15, -s * 0.07, s * 0.05, s * 0.05);

  // 5. 粉紅小鼻子與嘴巴
  fill(240, 140, 155);
  triangle(0, s * 0.04, -s * 0.04, s * 0.08, s * 0.04, s * 0.08);

  stroke(60);
  strokeWeight(Math.max(2, s * 0.018));
  noFill();
  beginShape();
  vertex(-s * 0.06, s * 0.14);
  bezierVertex(-s * 0.03, s * 0.18, 0, s * 0.16, 0, s * 0.11);
  bezierVertex(0, s * 0.16, s * 0.03, s * 0.18, s * 0.06, s * 0.14);
  endShape();

  // 6. 可愛鬍鬚
  line(-s * 0.38, 0, -s * 0.52, -s * 0.04);
  line(-s * 0.38, s * 0.08, -s * 0.52, s * 0.08);
  line(s * 0.38, 0, s * 0.52, -s * 0.04);
  line(s * 0.38, s * 0.08, s * 0.52, s * 0.08);
  pop();
}

// 繪製題目與選項區塊
function drawQuizSection() {
  if (quizList.length === 0) return;
  let currentQ = quizList[currentIndex];

  push();
  let qX = width * 0.33;
  let qY = height * 0.16;
  let qW = width * 0.60;
  let qH = height * 0.22;

  fill(255);
  stroke(215);
  strokeWeight(1);
  rect(qX, qY, qW, qH, 10);

  noStroke();
  fill(40);
  textFont('LXGW WenKai TC');
  textSize(Math.min(width * 0.02, 19));
  textAlign(LEFT, TOP);
  text(`Q${currentIndex + 1}. ${currentQ.question}`, qX + 22, qY + 20, qW - 44, qH - 40);
  pop();

  // 選項按鈕排版
  let optX = width * 0.33;
  let optStartY = height * 0.41;
  let optW = width * 0.60;
  let optH = Math.min(height * 0.08, 52);
  let optGap = 12;

  for (let i = 0; i < 4; i++) {
    let currentOptY = optStartY + i * (optH + optGap);
    let btnColor = color(255);

    if (isAnswered) {
      if (i === currentQ.answer) {
        // 答錯時正確選項顯示指定顏色 #dde5b6
        btnColor = color('#dde5b6');
      } else if (i === selectedOption && selectedOption !== currentQ.answer) {
        btnColor = color(255, 205, 205);
      }
    } else if (mouseX > optX && mouseX < optX + optW && mouseY > currentOptY && mouseY < currentOptY + optH) {
      btnColor = color(240, 244, 248);
    }

    push();
    fill(btnColor);
    stroke(195);
    strokeWeight(1);
    rect(optX, currentOptY, optW, optH, 8);

    noStroke();
    fill(50);
    textFont('Fraunces'); // 英文部分使用 Fraunces
    textSize(Math.min(width * 0.018, 17));
    textAlign(LEFT, CENTER);
    let prefix = ['(A)', '(B)', '(C)', '(D)'];
    text(`${prefix[i]} ${currentQ.options[i]}`, optX + 20, currentOptY + optH / 2);
    pop();
  }

  if (isAnswered) {
    drawExplanationAndNextButton();
  }
}

// 繪製解析與下一題按鈕
function drawExplanationAndNextButton() {
  let currentQ = quizList[currentIndex];

  push();
  let expX = width * 0.33;
  let expY = height * 0.79;
  let expW = width * 0.44;
  let expH = height * 0.15;

  fill(250, 247, 238);
  stroke(225, 210, 185);
  rect(expX, expY, expW, expH, 8);

  noStroke();
  fill(80);
  textFont('LXGW WenKai TC');
  textSize(Math.min(width * 0.016, 15));
  textAlign(LEFT, TOP);
  text(`💡 解析：\n${currentQ.explanation}`, expX + 15, expY + 12, expW - 30, expH - 24);

  let btnW = Math.min(width * 0.14, 150);
  let btnH = 46;
  let btnX = width * 0.93 - btnW;
  let btnY = height * 0.88;

  fill(70, 130, 180);
  rect(btnX, btnY, btnW, btnH, 8);

  fill(255);
  textSize(16);
  textAlign(CENTER, CENTER);
  let label = (currentIndex === 4) ? "查看結算 ➔" : "下一題 ➔";
  text(label, btnX + btnW / 2, btnY + btnH / 2);
  pop();
}

// 繪製測驗結算頁面
function drawResultSection() {
  push();
  let cardW = width * 0.55;
  let cardH = height * 0.48;
  let cardX = (width - cardW) / 2;
  let cardY = (height - cardH) / 2;

  fill(255);
  stroke(210);
  strokeWeight(2);
  rect(cardX, cardY, cardW, cardH, 15);

  noStroke();
  fill(40);
  textFont('LXGW WenKai TC');
  textSize(Math.min(width * 0.03, 26));
  textAlign(CENTER, CENTER);
  text("🎉 測驗完成！", width / 2, cardY + cardH * 0.22);

  textSize(Math.min(width * 0.022, 20));
  fill(70);
  text(`答對題數： ${score} / 5 題`, width / 2, cardY + cardH * 0.42);
  text(`最終好感度： ${favorability} / 100`, width / 2, cardY + cardH * 0.55);

  let btnW = 170;
  let btnH = 48;
  let btnX = width / 2 - btnW / 2;
  let btnY = cardY + cardH * 0.76;

  fill(80, 150, 110);
  rect(btnX, btnY, btnW, btnH, 8);

  fill(255);
  textSize(17);
  text("再測驗一次", btnX + btnW / 2, btnY + btnH / 2);
  pop();
}

// 繪製 ❤️ +20 愛心動畫 (持續 3 秒)
function drawHeartAnimation() {
  push();
  let npcX = width * 0.16;
  let npcY = height * 0.30;

  let progress = heartAnimTimer / 180;
  let floatY = -35 - (1 - progress) * 45;

  textSize(28);
  textAlign(LEFT, CENTER);
  fill(230, 40, 40, progress * 255);
  text("❤️ +20", npcX + 35, npcY + floatY);
  pop();
}

// 滑鼠點擊觸發
function mousePressed() {
  if (currentIndex < 5 && !isAnswered) {
    let optX = width * 0.33;
    let optStartY = height * 0.41;
    let optW = width * 0.60;
    let optH = Math.min(height * 0.08, 52);
    let optGap = 12;

    for (let i = 0; i < 4; i++) {
      let currentOptY = optStartY + i * (optH + optGap);
      if (mouseX > optX && mouseX < optX + optW && mouseY > currentOptY && mouseY < currentOptY + optH) {
        selectedOption = i;
        isAnswered = true;

        let currentQ = quizList[currentIndex];
        if (selectedOption === currentQ.answer) {
          score++;
          favorability = min(100, favorability + 20);
          showHeartAnim = true;
          heartAnimTimer = 180; // 3 秒 (60 FPS * 3)
        }
        break;
      }
    }
  } else if (currentIndex < 5 && isAnswered) {
    let btnW = Math.min(width * 0.14, 150);
    let btnH = 46;
    let btnX = width * 0.93 - btnW;
    let btnY = height * 0.88;

    if (mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH) {
      currentIndex++;
      resetQuestionState();
    }
  } else if (currentIndex >= 5) {
    let cardW = width * 0.55;
    let cardH = height * 0.48;
    let cardY = (height - cardH) / 2;
    let btnW = 170;
    let btnH = 48;
    let btnX = width / 2 - btnW / 2;
    let btnY = cardY + cardH * 0.76;

    if (mouseX > btnX && mouseX < btnX + btnW && mouseY > btnY && mouseY < btnY + btnH) {
      startNewQuiz();
    }
  }
}

// 響應式畫布自適應
function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
}
</script>
</body>
</html>