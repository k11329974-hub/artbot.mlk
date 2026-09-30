<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
  <title>Арт бот</title>
  <script src="https://telegram.org/js/telegram-web-app.js"></script>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: sans-serif;
      background: #fce4ec;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow-x: hidden;
    }
    .screen {
      display: none;
      width: 100%;
      max-width: 600px;
      position: relative;
    }
    .screen.active { display: block; }
    .screen img {
      width: 100%;
      display: block;
      border-radius: 12px;
    }
    .click-zone {
      position: absolute;
      cursor: pointer;
    }
    .btn-artikuly { top: 31%; left: 5%; width: 40%; height: 8%; }
    .btn-chat     { top: 44%; left: 5%; width: 40%; height: 8%; }
    .btn-kanal    { top: 55%; left: 5%; width: 40%; height: 8%; }
    .btn-ym   { top: 31%; left: 5%; width: 50%; height: 8%; }
    .btn-wb   { top: 44%; left: 5%; width: 50%; height: 8%; }
    .btn-ozon { top: 55%; left: 5%; width: 50%; height: 8%; }
    .btn-back { top: 2%; left: 2%; width: 12%; height: 8%; }
  </style>
</head>
<body>

  <div class="screen active" id="screen1">
    <img src="menu.jpg" alt="Меню">
    <div class="click-zone btn-artikuly" onclick="showScreen('screen2')"></div>
    <div class="click-zone btn-chat" onclick="openLink('https://t.me/+sq1oQq3hxgg3Mzdi')"></div>
    <div class="click-zone btn-kanal" onclick="openLink('https://t.me/aallaasskkaammaia')"></div>
  </div>

  <div class="screen" id="screen2">
    <img src="artikuly.jpg" alt="Артикулы">
    <div class="click-zone btn-back" onclick="showScreen('screen1')"></div>
    <div class="click-zone btn-ym" onclick="openLink('https://market.yandex.ru/cc/BC8b84')"></div>
    <div class="click-zone btn-wb" onclick="openLink('https://www.wildberries.ru/catalog/1520586983/detail.aspx?size=2321237179')"></div>
    <div class="click-zone btn-ozon" onclick="openLink('https://ozon.ru/t/GALlxa8')"></div>
  </div>

  <script>
    Telegram.WebApp.ready();
    Telegram.WebApp.expand();

    function showScreen(id) {
      document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
      document.getElementById(id).classList.add('active');
    }

    function openLink(url) {
      Telegram.WebApp.openLink(url);
    }
  </script>

</body>
</html>