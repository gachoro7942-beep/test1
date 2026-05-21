<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>숫자 맞추기 게임</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: sans-serif;
      background: #f5f5f3;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      min-height: 100vh;
      padding: 2rem 1rem;
    }

    .container {
      width: 100%;
      max-width: 420px;
    }

    h1 {
      text-align: center;
      font-size: 22px;
      font-weight: 500;
      margin-bottom: 1.5rem;
      color: #1a1a18;
    }

    .card {
      background: #ffffff;
      border: 0.5px solid #d3d1c7;
      border-radius: 12px;
      padding: 1.5rem;
      margin-bottom: 1rem;
    }

    .info-row {
      display: flex;
      justify-content: space-between;
      margin-bottom: 1.2rem;
    }
    .info-box {
      text-align: center;
      flex: 1;
    }
    .info-box .label {
      font-size: 12px;
      color: #888780;
      margin-bottom: 4px;
    }
    .info-box .value {
      font-size: 22px;
      font-weight: 500;
      color: #1a1a18;
    }

    .hint-area {
      text-align: center;
      min-height: 48px;
      margin-bottom: 1.2rem;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .hint-badge {
      display: inline-block;
      padding: 6px 18px;
      border-radius: 20px;
      font-size: 15px;
      font-weight: 500;
    }
    .hint-up   { background: #fcebeb; color: #a32d2d; }
    .hint-down { background: #e6f1fb; color: #185fa5; }
    .hint-win  { background: #eaf3de; color: #3b6d11; }
    .hint-init { background: #f1efe8; color: #5f5e5a; }

    .input-row {
      display: flex;
      gap: 8px;
      margin-bottom: 1rem;
    }
    input[type="number"] {
      flex: 1;
      padding: 10px 14px;
      font-size: 16px;
      border: 0.5px solid #d3d1c7;
      border-radius: 8px;
      background: #fafaf9;
      color: #1a1a18;
      outline: none;
    }
    input[type="number"]:focus {
      border-color: #7f77dd;
    }
    input[type="number"]::-webkit-inner-spin-button { -webkit-appearance: none; }

    .submit-btn {
      padding: 10px 20px;
      font-size: 15px;
      font-weight: 500;
      border: 0.5px solid #d3d1c7;
      border-radius: 8px;
      background: #1a1a18;
      color: #ffffff;
      cursor: pointer;
      transition: background 0.15s;
    }
    .submit-btn:hover { background: #3a3a38; }
    .submit-btn:disabled { background: #b4b2a9; cursor: default; }

    .reset-btn {
      width: 100%;
      padding: 10px;
      font-size: 14px;
      border: 0.5px solid #d3d1c7;
      border-radius: 8px;
      background: #ffffff;
      color: #888780;
      cursor: pointer;
    }
    .reset-btn:hover { background: #ebebea; }

    .history {
      margin-top: 1rem;
    }
    .history-title {
      font-size: 13px;
      color: #888780;
      margin-bottom: 8px;
    }
    .history-list {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }
    .history-item {
      font-size: 13px;
      padding: 3px 10px;
      border-radius: 20px;
      background: #ebebea;
      color: #5f5e5a;
    }
    .history-item.high { background: #fcebeb; color: #a32d2d; }
    .history-item.low  { background: #e6f1fb; color: #185fa5; }

    @keyframes pop {
      0%   { transform: scale(0.8); opacity: 0; }
      60%  { transform: scale(1.1); }
      100% { transform: scale(1);   opacity: 1; }
    }
    .pop { animation: pop 0.3s ease forwards; }
  </style>
</head>
<body>
<div class="container">
  <h1>숫자 맞추기</h1>

  <div class="card">
    <div class="info-row">
      <div class="info-box">
        <div class="label">범위</div>
        <div class="value">1 – 100</div>
      </div>
      <div class="info-box">
        <div class="label">시도 횟수</div>
        <div class="value" id="tries">0</div>
      </div>
    </div>

    <div class="hint-area" id="hint-area">
      <span class="hint-badge hint-init">1~100 숫자를 입력하세요!</span>
    </div>

    <div class="input-row">
      <input type="number" id="guess-input" min="1" max="100" placeholder="숫자 입력" />
      <button class="submit-btn" id="submit-btn" onclick="submit()">확인</button>
    </div>

    <button class="reset-btn" onclick="reset()">새 게임</button>

    <div class="history" id="history" style="display:none;">
      <div class="history-title">입력 기록</div>
      <div class="history-list" id="history-list"></div>
    </div>
  </div>
</div>

<script>
  let answer = rand();
  let tries  = 0;
  let done   = false;
  const history = [];

  function rand() {
    return Math.floor(Math.random() * 100) + 1;
  }

  document.getElementById('guess-input').addEventListener('keydown', e => {
    if (e.key === 'Enter') submit();
  });

  function submit() {
    if (done) return;

    const input = document.getElementById('guess-input');
    const val   = parseInt(input.value);

    if (isNaN(val) || val < 1 || val > 100) {
      showHint('1~100 사이의 숫자를 입력하세요.', 'hint-init');
      input.focus();
      return;
    }

    tries++;
    document.getElementById('tries').textContent = tries;
    input.value = '';
    input.focus();

    if (val < answer) {
      showHint('📈 더 큰 숫자입니다!', 'hint-up');
      addHistory(val, 'low');
    } else if (val > answer) {
      showHint('📉 더 작은 숫자입니다!', 'hint-down');
      addHistory(val, 'high');
    } else {
      showHint(`🎉 정답! ${answer} (${tries}번 만에 성공!)`, 'hint-win');
      addHistory(val, 'win');
      done = true;
      document.getElementById('submit-btn').disabled = true;
      input.disabled = true;
    }
  }

  function showHint(msg, cls) {
    const area = document.getElementById('hint-area');
    area.innerHTML = `<span class="hint-badge ${cls} pop">${msg}</span>`;
  }

  function addHistory(val, type) {
    history.push({ val, type });
    const histEl = document.getElementById('history');
    const list   = document.getElementById('history-list');
    histEl.style.display = 'block';
    const cls = type === 'high' ? 'high' : type === 'low' ? 'low' : '';
    list.innerHTML = history.map(h =>
      `<span class="history-item ${h.type === 'high' ? 'high' : h.type === 'low' ? 'low' : ''}">${h.val}</span>`
    ).join('');
  }

  function reset() {
    answer = rand();
    tries  = 0;
    done   = false;
    history.length = 0;

    document.getElementById('tries').textContent   = 0;
    document.getElementById('history').style.display = 'none';
    document.getElementById('history-list').innerHTML = '';
    document.getElementById('submit-btn').disabled  = false;
    document.getElementById('guess-input').disabled = false;
    document.getElementById('guess-input').value    = '';
    document.getElementById('guess-input').focus();
    showHint('1~100 숫자를 입력하세요!', 'hint-init');
  }
</script>
</body>
</html>
