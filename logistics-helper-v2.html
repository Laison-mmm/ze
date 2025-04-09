<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>物流查詢小幫手 🧸</title>
  <style>
    * { box-sizing: border-box; }
    body {
      font-family: '微軟正黑體', sans-serif;
      background-color: #fff8f0;
      margin: 0;
      padding: 20px;
      text-align: center;
    }
    h1 { font-size: 2rem; margin-bottom: 10px; }
    input, button {
      font-size: 1.1rem;
      padding: 12px;
      border-radius: 10px;
      margin: 10px auto;
      border: none;
      width: 90%;
      max-width: 400px;
      display: block;
      text-align: center;
    }
    .cute-btn {
      background-color: #ffd3e0;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    .cute-btn:hover { background-color: #ffc2d1; }
    .result-box, .login-box, .history-box {
      margin-top: 20px;
      padding: 15px;
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.05);
      display: none;
      animation: fade-in 0.4s ease-in-out;
      text-align: center;
    }
    .platform-buttons {
      display: flex;
      justify-content: center;
      gap: 10px;
      flex-wrap: wrap;
    }
    .platform-buttons button {
      margin: 5px;
      font-size: 1rem;
      padding: 10px 20px;
      border-radius: 8px;
      border: 1px solid #888;
      background: #f5f5f5;
      cursor: pointer;
    }
    .platform-buttons button:hover { background-color: #eee; }
    ul { list-style: none; padding: 0; }
    li { margin: 5px 0; }
    @keyframes fade-in {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="login-box" id="loginBox">
    <h1>🔐 這是專屬內部夥伴的查詢頁唷</h1>
    <p>請輸入密碼進入 🧸（提示：4位數 生日）</p>
    <input type="password" id="loginInput" placeholder="請輸入密碼" />
    <button class="cute-btn" onclick="checkPassword()">登入</button>
    <p id="loginError" style="color: red;"></p>
  </div>

  <div id="mainContent" style="display:none;">
    <h1>📦 物流查詢小幫手 🧸</h1>
    <input type="text" id="trackingNumber" placeholder="請貼上物流單號" />
    <button class="cute-btn" onclick="handleTracking()">下一步</button>

    <div class="result-box" id="resultBox">
      <p id="resultMsg"></p>
      <div class="platform-buttons" id="platformButtons"></div>
      <p id="copyMsg"></p>
    </div>

    <div class="history-box" id="historyBox">
      <h3>📂 最近查詢紀錄</h3>
      <ul id="historyList"></ul>
      <button class="cute-btn" onclick="clearHistory()">🧹 清除所有紀錄</button>
    </div>
  </div>

  <script>
    const correctPassword = "0919";

    window.onload = function() {
      document.getElementById("loginBox").style.display = "block";
      loadHistory();
    };

    function checkPassword() {
      const input = document.getElementById("loginInput").value.trim();
      const errorText = document.getElementById("loginError");
      if (input === correctPassword) {
        document.getElementById("loginBox").style.display = "none";
        document.getElementById("mainContent").style.display = "block";
      } else {
        errorText.textContent = "密碼錯囉～再試試看唷 🥺";
      }
    }

    function handleTracking() {
      const input = document.getElementById("trackingNumber").value.trim();
      const resultBox = document.getElementById("resultBox");
      const resultMsg = document.getElementById("resultMsg");
      const platformButtons = document.getElementById("platformButtons");
      const copyMsg = document.getElementById("copyMsg");
      let displayNumber = input;

      resultMsg.textContent = "";
      platformButtons.innerHTML = "";
      copyMsg.textContent = "";
      resultBox.style.display = "none";

      if (!input) {
        alert("請輸入單號唷～🥺");
        return;
      }

      let type = "未知";

      if (/^[A-Z]{1}[0-9]{14}$/i.test(input)) {
        displayNumber = input.slice(0, 8);
        resultMsg.innerHTML = `🔍 偵測為 <strong>7-11 統一速達</strong><br>✅ 已自動縮短單號為：<strong>${displayNumber}</strong>`;
        platformButtons.innerHTML = `<button onclick="goTo('https://eservice.7-11.com.tw/e-tracking/search.aspx', '${displayNumber}')">🛵 前往 7-11 查詢</button>`;
        type = "7-11";
      } else if (/^[0-9]{10}$/.test(input)) {
        resultMsg.innerHTML = `✅ 偵測為 <strong>新竹物流</strong><br>單號：<strong>${displayNumber}</strong>`;
        platformButtons.innerHTML = `<button onclick="goTo('https://www.hct.com.tw/Search/SearchGoods_n.aspx', '${displayNumber}')">🚛 前往新竹查詢</button>`;
        type = "新竹";
      } else if (/^[0-9]{11}$/.test(input)) {
        resultMsg.innerHTML = `✅ 偵測為 <strong>全家物流</strong><br>單號：<strong>${displayNumber}</strong>`;
        platformButtons.innerHTML = `<button onclick="goTo('https://fmec.famiport.com.tw/FP_Entrance/QueryBox', '${displayNumber}')">📦 前往全家查詢</button>`;
        type = "全家";
      } else {
        resultMsg.textContent = "❓ 無法判斷物流類型，請再次確認單號格式唷～";
      }

      if (type !== "未知") saveToHistory(type, displayNumber);
      resultBox.style.display = "block";
    }

    function goTo(url, number) {
      navigator.clipboard.writeText(number);
      document.getElementById("copyMsg").textContent = `✅ 單號 ${number} 已複製，請到查詢頁貼上即可唷～ ✨`;
      window.open(url, '_blank');
    }

    function saveToHistory(type, number) {
      const history = JSON.parse(localStorage.getItem("logiHistory") || "[]");
      const now = new Date().toLocaleString();
      history.unshift({ type, number, time: now });
      if (history.length > 10) history.pop();
      localStorage.setItem("logiHistory", JSON.stringify(history));
      renderHistory();
    }

    function loadHistory() {
      renderHistory();
    }

    function renderHistory() {
      const history = JSON.parse(localStorage.getItem("logiHistory") || "[]");
      const list = document.getElementById("historyList");
      if (!list) return;
      list.innerHTML = "";
      history.forEach(item => {
        const li = document.createElement("li");
        li.textContent = `📍 ${item.type}｜${item.number}｜${item.time}`;
        list.appendChild(li);
      });
    }

    function clearHistory() {
      localStorage.removeItem("logiHistory");
      renderHistory();
    }
  </script>

<script src="https://static.app/js/static.js" type="text/javascript"></script>
</body>
</html>
