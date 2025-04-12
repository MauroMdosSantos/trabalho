<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Projeto Final P5.js</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.0/p5.js"></script>
    <style>
      body {
        margin: 0;
        overflow: hidden;
        background-color: #000;
      }
    </style>
  </head>
  <body>
    <script>
      // Variáveis para posição do sol
      let sunX;
      let sunY;

      function setup() {
        createCanvas(600, 400);
        sunX = width / 2;
        sunY = height / 2;
        console.log("Projeto iniciado! Bem-vindo ao Céu Dinâmico.");
      }

      function draw() {
        // Fundo que muda de cor conforme o mouse (céu animado)
        let bgColor = map(mouseY, 0, height, 255, 100);
        background(bgColor, bgColor, 255);

        // Sol que segue o mouse
        sunX = mouseX;
        sunY = mouseY;

        noStroke();
        fill(255, 204, 0);
        circle(sunX, sunY, 80);

        // Montanha com triângulo
        fill(34, 139, 34);
        triangle(100, 400, 300, 200, 500, 400);

        // Linha como chão
        stroke(0);
        line(0, 400, width, 400);

        // Estrelas piscando
        for (let i = 0; i < 20; i++) {
          fill(255);
          circle(random(width), random(height / 2), random(2, 4));
        }
      }
    </script>
  </body>
</html>
