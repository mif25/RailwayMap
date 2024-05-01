<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Карта NT1 v01.05</title>
<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: darkgrey;
    }
    #canvasContainer {
        padding: 10px;
        width: 100%;
        max-width: 1000px;
        min-width: 300px;
        position: relative;
    }
    #canvas {
        width: 100%;
        height: 100%;
        border: 2px solid #ccc;
        position: relative;
    }
    .point {
        width: 8px;
        height: 8px;
        border-radius: 50%;
        background-color: red;
        position: absolute;
    }
    .info-name {
        position: absolute;
        background-color: rgba(0, 0, 0, 0.7);
        color: #fff;
        padding: 5px;
        border-radius: 5px;
        display: none;
    }
</style>
</head>
<body>

<div id="canvasContainer">
    <div id="canvas"></div>
    <div id="coordinatesDisplay"></div>
    <div id="info">
      <br><br>
      Серая ветка - маршрут #1<br>
      Красная ветка - маршрут #2<br>
      Жёлтая ветка - маршрут #3<br>
      Цвета могут отличаться от действительных, позже будут нанесены станции.<br>
    </div>
</div>

<script>
  var lines = [
    {x1: 0, y1: -5000, x2: 0, y2: 5000, name: "x", color: "black"},
    {x1: -5000, y1: 0, x2: 5000, y2: 0, name: "y", color: "black"},
    {x1: -4829, y1: 2310, x2: 3740, y2: 2310, name: "Маршрут #1", color: "grey"},
    {x1: 3740, y1: 2310, x2: 3740, y2: 1533, name: "Маршрут #1", color: "grey"},
    {x1: 3740, y1: 1533, x2: 4900, y2: 1533, name: "Маршрут #1", color: "grey"},
    {x1: 3599, y1: 2300, x2: 3599, y2: 4500, name: "Маршрут #2", color: "red"},
    // {x1: 3599, y1: 4500, x2: 4600, y2: 4500, name: "Маршрут #2", color: "red"},
    {x1: -3690, y1: 4377, x2: -3476, y2: 4377, name: "Маршрут #3", color: "yellow"},
    {x1: -3476, y1: 4377, x2: -3476, y2: -200, name: "Маршрут #3", color: "yellow"},
    // {x1: -3476, y1: -200, x2: -2450, y2: -200, name: "Маршрут #3", color: "yellow"},
    // {x1: -2450, y1: -200, x2: -2450, y2: -800, name: "Маршрут #3", color: "yellow"},
  ];

  var data = `
  cool warp:-3688:87:4439:true:6C7A1D
  sysano:3582:65:3499:true:821FB0
  dark:4601:31:4664:true:FC2790
  SerZax Base:4480:77:4517:true:9B06F3
  kapysta:4887:66:1442:true:EC8D33
  k1mbor base:-2369:78:-563:true:EBDDEB
  _F_I_Z_I_K_:3927:210:-3827:true:FC0FEC
  VOLKrust:-678:82:2126:true:9C7086
  Seeesh:-3047:85:-157:true:8ACCF8
  Dragon2206:-3603:67:-2509:true:F97DF4
  warp exe:-8:109:1576:true:8B88FF
  moder house:-2500:90:-760:true:37E782
  YamYam:2048:88:-3500:true:589D6F
  Gjart:-8:141:4:true:47DD91
  m_i_f base:-4718:66:2097:true:D14EAC
  warp lenta:-4617:68:2407:true:B705A0
  _Dr1ke_:-2043:80:2309:true:1771CF
  lobotomy1:-2549:73:-598:true:0643AF
  karver:2343:201:-3612:true:4F9607
  The Lobotomy Palace:-2242:89:1981:true:00FF00
  `;

  // Регулярное выражение для извлечения данных
  var regex = /([^:]+):(-?\d+):[^:]+:(-?\d+):[^:]+:([0-9A-F]+)/g;

  var points = [];
  var match;
  while ((match = regex.exec(data)) !== null) {
    var name = match[1].replace('\n  ', '');
    var x = parseInt(match[2]);
    var y = parseInt(match[3]);
    var color = match[4];
    points.push({ x: x, y: y, name: name, color: color });
  }

  // Метод отслеживания курсора
  canvas.addEventListener('mousemove', function(event) {
    var canvas = document.getElementById('canvas');
    var coordinatesDisplay = document.getElementById('coordinatesDisplay');
    var scale = canvas.offsetWidth / 10000;

      // Получаем координаты курсора относительно элемента плоскости
      var rect = canvas.getBoundingClientRect();
      var x = (event.clientX - rect.left) / scale - 5000;
      var y = (event.clientY - rect.top) / scale - 5000;

      // Отображаем координаты курсора в элементе для отображения координат
      coordinatesDisplay.textContent = 'X: ' + Math.round(x) + ', Y: ' + Math.round(y);
  });

  function drawLines() {
    var canvas = document.getElementById('canvas');
    var scale = canvas.offsetWidth / 10000;

    var existingSvg = document.getElementById('svg');
    if (existingSvg) {
        canvas.removeChild(existingSvg);
    }

    var svgNS = "http://www.w3.org/2000/svg";
    var svg = document.createElementNS(svgNS, "svg");

    svg.setAttribute("id", "svg");
    svg.setAttribute("width", 10000 * scale);
    svg.setAttribute("height", 10000 * scale);

    lines.forEach(function(line) {
      var lineElement = document.createElementNS(svgNS, "line");
      lineElement.setAttribute("x1", (line.x1 + 5000) * scale);
      lineElement.setAttribute("y1", (line.y1 + 5000) * scale);
      lineElement.setAttribute("x2", (line.x2 + 5000) * scale);
      lineElement.setAttribute("y2", (line.y2 + 5000) * scale);
      lineElement.setAttribute("stroke", line.color || "black");
      lineElement.setAttribute("stroke-width", "3");

      svg.appendChild(lineElement);
    });

    canvas.appendChild(svg);
  }

  function drawPoints() {
    var canvas = document.getElementById('canvas');
    var scale = canvas.offsetWidth / 10000;

    points.forEach(function(point, index) {
      var div = document.createElement('div');
      div.className = 'point';
      div.dataset.index = index;
      div.style.left = ((point.x + 5000) * scale - 4) + 'px';
      div.style.top = ((point.y + 5000) * scale - 4) + 'px';
      div.style.backgroundColor = '#' + point.color;
      div.setAttribute('title', point.name);
      canvas.appendChild(div);

      div.addEventListener('mouseover', function() {
        var nameDiv = document.createElement('div');
        nameDiv.className = 'info-name';
        nameDiv.innerHTML = point.name;
        nameDiv.style.left = ((point.x + 5000) * scale + 10) + 'px';
        nameDiv.style.top = ((point.y + 5000) * scale - 20) + 'px';
        canvas.appendChild(nameDiv);

        div.addEventListener('mouseout', function() {
          canvas.removeChild(nameDiv);
        });
      });
    });
  }

  function redrawPoints() {
    var canvas = document.getElementById('canvas');
    var scale = canvas.offsetWidth / 10000; // Вычисляем масштаб
    var pointsElements = document.querySelectorAll('.point');

    pointsElements.forEach(function(pointElement) {
      var pointIndex = parseInt(pointElement.dataset.index);
      var point = points[pointIndex];
      pointElement.style.left = ((point.x + 5000) * scale - 4) + 'px';
      pointElement.style.top = ((point.y + 5000) * scale - 4) + 'px';
    });
  }

  window.onload = function() {
    var canvasContainer = document.getElementById('canvasContainer');

    // Обновление размеров canvas
    function updateCanvasSize() {
      canvasContainer.style.height = canvasContainer.offsetWidth - 20 + "px";
      redrawPoints();
      drawLines();
    }

    updateCanvasSize();
    window.addEventListener('resize', updateCanvasSize);
  };

  drawPoints();
  drawLines();
</script>

</body>
</html>
