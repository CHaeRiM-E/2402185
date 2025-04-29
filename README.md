<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>타자기</title>
  <style>
    body {
      text-align: center;
      font-family: 'Georgia', serif;
      background-color: #f7f7f7;
    }

    h1, h2, p {
      margin-top: 20px;
    }

    .display {
      width: 500px;
      height: 120px;
      margin: 20px auto;
      background-color: #ffffff;
      border: 4px solid #ff0000;
      border-radius: 10px;
      padding: 10px;
      font-size: 24px;
      text-align: left;
      overflow-y: auto;
    }

    .keyboard {
      display: inline-block;
      margin-top: 20px;
      padding: 20px;
      border: 5px solid #c90000;
      border-radius: 20px;
      background-color: #ffffff;
    }

 
    .row {
      margin: 5px 0;
    }

    
    .key {
      font-size: 18px;
      padding: 12px 18px;
      margin: 3px;
      border: none;
      border-radius: 8px;
    }

 
    .number {
      background-color: #ffffff;
      color: black;
    }

    .qwerty {
      background-color: #d70000;
      color: white;
    }

    .asdf {
      background-color: #ad0000;
      color: white;
    }

    .zxcv {
      background-color: #710000;
      color: white;
    }

  </style>
</head>
<body>

<h1>타자기</h1>
<p>제작자: 한양여대, 유채림, 2402185, 빅데이터학과</p>

<div class="display" id="display"></div>

<div class="keyboard">
  <div class="row number">
    <button class="key number">1</button>
    <button class="key number">2</button>
    <button class="key number">3</button>
    <button class="key number">4</button>
    <button class="key number">5</button>
    <button class="key number">6</button>
    <button class="key number">7</button>
    <button class="key number">8</button>
    <button class="key number">9</button>
    <button class="key number">0</button>
  </div>
  <div class="row qwerty">
    <button class="key qwerty">Q</button>
    <button class="key qwerty">W</button>
    <button class="key qwerty">E</button>
    <button class="key qwerty">R</button>
    <button class="key qwerty">T</button>
    <button class="key qwerty">Y</button>
    <button class="key qwerty">U</button>
    <button class="key qwerty">I</button>
    <button class="key qwerty">O</button>
    <button class="key qwerty">P</button>
  </div>
  <div class="row asdf">
    <button class="key asdf">A</button>
    <button class="key asdf">S</button>
    <button class="key asdf">D</button>
    <button class="key asdf">F</button>
    <button class="key asdf">G</button>
    <button class="key asdf">H</button>
    <button class="key asdf">J</button>
    <button class="key asdf">K</button>
    <button class="key asdf">L</button>
  </div>
  <div class="row zxcv">
    <button class="key zxcv">Z</button>
    <button class="key zxcv">X</button>
    <button class="key zxcv">C</button>
    <button class="key zxcv">V</button>
    <button class="key zxcv">B</button>
    <button class="key zxcv">N</button>
    <button class="key zxcv">M</button>
  </div>
</div>

<script>
  const display = document.getElementById('display');
  const keys = document.querySelectorAll('.key');

  
  keys.forEach(key => {
    key.addEventListener('click', () => {
      display.textContent += key.textContent;
    });
  });

 
  document.addEventListener('keydown', (event) => {
    const pressedKey = event.key;

    if (pressedKey === 'Backspace') {
    
      display.textContent = display.textContent.slice(0, -1);
    } else {
      const upperKey = pressedKey.toUpperCase();
      if ((upperKey >= 'A' && upperKey <= 'Z') || (upperKey >= '0' && upperKey <= '9')) {
        display.textContent += upperKey;
      }
    }
  });
</script>

</body>
</html>
