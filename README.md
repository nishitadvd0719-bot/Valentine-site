# Valentine-site
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Be My Valentine 💖</title>

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #fff;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    .container {
      width: 90%;
      max-width: 400px;
    }

    img {
      width: 180px;
      margin-bottom: 20px;
    }

    h1 {
      font-size: 22px;
      margin-bottom: 20px;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 15px;
    }

    button {
      border: none;
      border-radius: 8px;
      padding: 12px 22px;
      font-size: 16px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .yes {
      background-color: #4CAF50;
      color: white;
    }

    .no {
      background-color: #E53935;
      color: white;
    }
  </style>
</head>

<body>

  <div class="container" id="app">
    <!-- START GIF -->
    <img src="https://tenor.com/en-IN/view/mocha-bear-hearts-mocha-and-milk-bears-milk-mocha-bear-gif-love-gif-7355347396987361923.gif" alt="cute bear" />

    <h1 id="question">Will you be my Valentine?</h1>

    <div class="buttons">
      <button class="yes" id="yesBtn">Yes</button>
      <button class="no" id="noBtn">No</button>
    </div>
  </div>

  <script>
    const noTexts = [
      "Are you sure?",
      "Think again 😢",
      "Last chance!",
      "Really sure?",
      "Change of heart?"
    ];

    let noCount = 0;

    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const question = document.getElementById("question");
    const app = document.getElementById("app");

    noBtn.addEventListener("click", () => {
      question.innerText = noTexts[noCount % noTexts.length];
      noCount++;

      // make YES button bigger every time
      let size = parseFloat(window.getComputedStyle(yesBtn).fontSize);
      yesBtn.style.fontSize = (size + 6) + "px";
      yesBtn.style.padding = "16px 30px";
    });

    yesBtn.addEventListener("click", () => {
      app.innerHTML = `
        <img src="https://tenor.com/en-IN/view/love-you-gif-16464856326135066512.gif" alt="hugging bears" />
        <h1>Ok,yay!!! 💕🥰</h1>
      `;
    });
  </script>

</body>
</html> 
