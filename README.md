<script src="https://telegram.org/js/telegram-web-app.js"></script>
<!doctype html>
<html lang="ru">

<head>
  <meta charset="UTF-8">
  
  <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>BestShop</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200;500&display=swap');
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    .image-coin {
      margin-top: 10%;
      margin-left: 25%;
      width: 200px;
      height: 200px;
      border: none;
      border-radius: 50%;
      background-image: url('https://i.sstatic.net/fzSbVP56.jpg');
      background-size: 111%;
      background-position: 50% 50%;
    }
  </style>
</head>

<body>
  <div>
    <p>Clicks: <a id="clicks">0</a></p>
    <button id="coin_click" class="image-coin" onClick="onClick()"></button>
  </div>
  <script src="https://telegram.org/js/telegram-web-app.js"></script>
  <script>
    let tg = window.Telegram.WebApp;
    let coin_click = document.getElementById("coin_click")

    var clicks = 0;

    function onClick() {
      clicks += 1;
      document.getElementById("clicks").innerHTML = clicks;
    }

    coin_click.addEventListener("click", () => {
      let data = {
        clicks: clicks
      }

      tg.sendData(JSON.stringify(data));
    })
  </script>
</body>

</html>
