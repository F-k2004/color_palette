<!-- color_palette.html -->
<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8">
  <title>🎨 تولید پالت رنگ</title>
  <style>
    body {
      font-family: sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
      background: #ffffff;
      transition: background 0.3s;
    }
    h1 {
      margin-bottom: 20px;
    }
    .colors {
      display: flex;
      gap: 10px;
      margin-top: 20px;
    }
    .color-box {
      width: 80px;
      height: 80px;
      border-radius: 10px;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 12px;
      font-weight: bold;
      color: #fff;
      text-shadow: 0 0 3px #000;
      transition: transform 0.2s;
    }
    .color-box:hover {
      transform: scale(1.1);
    }
    button {
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      background: #333;
      color: #fff;
      cursor: pointer;
      margin-top: 10px;
      transition: 0.3s;
    }
    button:hover {
      background: #555;
    }
  </style>
</head>
<body>
  <h1>🎨 تولید پالت رنگ تصادفی</h1>
  <button onclick="generatePalette()">تولید رنگ‌ها</button>
  <div class="colors" id="palette"></div>

  <script>
    function getRandomColor() {
      const letters = "0123456789ABCDEF";
      let color = "#";
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    }

    function generatePalette() {
      const paletteDiv = document.getElementById("palette");
      paletteDiv.innerHTML = "";
      for (let i = 0; i < 5; i++) {
        const color = getRandomColor();
        const box = document.createElement("div");
        box.className = "color-box";
        box.style.backgroundColor = color;
        box.textContent = color;
        box.onclick = () => {
          document.body.style.backgroundColor = color;
        };
        paletteDiv.appendChild(box);
      }
    }

    generatePalette();
  </script>
</body>
</html>
