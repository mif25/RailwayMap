<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Карта NT1 v03.05.24</title>
<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: #bbbbbd;
    }
    #canvasContainer {
        width: 100%;
        max-width: 1000px;
        min-width: 200px;
        position: relative;
        border: 4px solid #ccc;
    }
    #canvas {
        width: 100%;
        height: 100%;
        position: relative;
    }
    #coordinatesDisplay {
      position: fixed;
      font-size: 3vh;
      bottom: 5px;
      right: 5px;
    }
    .point {
        position: absolute;
        width: 2vh;
        height: 2vh;
        border-radius: 0 100% 100% 100%;
        background-color: red;
    }
    .info-name {
        position: absolute;
        background-color: rgba(0, 0, 0, 0.7);
        color: #fff;
        padding: 5px;
        border-radius: 5px;
        z-index: 5;
    }
</style>
</head>
<body>
<div class="title">
  <h1>Карта МЖД на сервере NanoTech#1</h1>
</div>
<div id="canvasContainer">
    <div id="canvas"></div>
</div>
<div id="coordinatesDisplay"></div>
<div id="info-block">
  Серая ветка - маршрут #1 [m_i_f - Kapysta19]<br>
  Красная ветка - маршрут #2 не введена в эксплуатацию<br>
  Жёлтая ветка - маршрут #3 [MACROCEIYT - IAzotI] в процессе расширения<br>
  <br>
  Станции отображаются квадратами, точками указаны базы игроков<br>
  Для того, чтобы поставить вагонетку на рельсы, используйте плиты около соответствующих железнодорожных путей.<br>
  На МЖД используется правосторонее движение, поэтому используйте ближний путь для движения направо, а дальний для движения налево.<br>
  Станции именуются ближайшим к ним точкам, которые указаны на карте или названиями линий, на которые можно совершить пересадку.<br>
  <br>
  Проект, на котором всё это реализуется - StreamCraft, сервер NanoTech #1.<br>
  Страница и железнодорожная сеть администрируется игроком m_i_f.<br>
</div>

<script>
  var lines = [
    {x1: 0, y1: -5000, x2: 0, y2: 5000, name: "x", color: "black"},
    {x1: -5000, y1: 0, x2: 5000, y2: 0, name: "y", color: "black"},
    {x1: -4780, y1: 2097, x2: -4857, y2: 2097, name: "Маршрут #1", color: "grey"},
    {x1: -4857, y1: 2097, x2: -4857, y2: 2310, name: "Маршрут #1", color: "grey"},
    {x1: -4857, y1: 2310, x2: 3740, y2: 2310, name: "Маршрут #1", color: "grey"},
    {x1: 3740, y1: 2310, x2: 3740, y2: 1533, name: "Маршрут #1", color: "grey"},
    {x1: 3740, y1: 1533, x2: 4900, y2: 1533, name: "Маршрут #1", color: "grey"},
    {x1: 3599, y1: 2300, x2: 3599, y2: 4500, name: "Маршрут #2", color: "red"},
    // {x1: 3599, y1: 4500, x2: 4600, y2: 4500, name: "Маршрут #2", color: "red"},
    {x1: -3700, y1: 4377, x2: -3476, y2: 4377, name: "Маршрут #3", color: "yellow"},
    {x1: -3476, y1: 4377, x2: -3476, y2: -200, name: "Маршрут #3", color: "yellow"},
    // {x1: -3476, y1: -200, x2: -2450, y2: -200, name: "Маршрут #3", color: "yellow"},
    // {x1: -2450, y1: -200, x2: -2450, y2: -800, name: "Маршрут #3", color: "yellow"},
  ];

  var squares = [
    {x: -4825, y: 2050, name: "x", color: "white"},
    {x: -4650, y: 2260, name: "x", color: "white"},
    {x: -3530, y: 2260, name: "x", color: "white"},
    {x: -1955, y: 2260, name: "x", color: "grey"},
    {x: -700, y: 2260, name: "x", color: "white"},
    {x: 3545, y: 2260, name: "x", color: "white"},
    {x: 4800, y: 1475, name: "x", color: "white"},
    {x: -3750, y: 4325, name: "x", color: "white"},
  ];

  var data = `
  MACROICEYT [warp cool]:-3688:87:4439:true:6C7A1D
  sysano:3582:65:3499:true:821FB0
  MafioznikZMP [warp dark]:4601:31:4664:true:FC2790
  SerZax:4480:77:4517:true:9B06F3
  Kapysta19:4887:66:1442:true:EC8D33
  k1mbor:-2369:78:-563:true:EBDDEB
  _F_I_Z_I_K_:3927:210:-3827:true:FC0FEC
  VOLKrust:-678:82:2126:true:9C7086
  Seeesh:-3047:85:-157:true:8ACCF8
  Dragon2206:-3603:67:-2509:true:F97DF4
  _DER3KIIY_ [warp exe]:-8:109:1576:true:8B88FF
  moder house:-2500:90:-760:true:37E782
  YamYam:2048:88:-3500:true:589D6F
  Gjart:0:141:0:true:47DD91
  m_i_f:-4718:66:2097:true:D14EAC
  _FurIon4IK_ [warp lenta]:-4617:68:2407:true:B705A0
  _Dr1ke__:-4793:67:2280:false:26AE09
  lobotomy1:-2549:73:-598:true:0643AF
  karver:2343:201:-3612:true:4F9607
  The Lobotomy Palace [warp chill]:-2242:89:1981:true:00FF00
  Yral4uk:87:89:1259:true:D2C400
  Perech:-1618:85:119:true:4DBCAF
  Audist:3943:144:759:true:5160AF
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

  function drawShapes() {
    var canvas = document.getElementById('canvas');
    var scale = canvas.offsetWidth / 10000;

    var existingSvg = document.getElementById('svg');
    if (existingSvg) {
        canvas.removeChild(existingSvg);
    }

    var svgNS = "http://www.w3.org/2000/svg";
    var svg = document.createElementNS(svgNS, "svg");

    svg.setAttribute("id", "svg");
    svg.setAttribute("width", canvas.offsetWidth);
    svg.setAttribute("height", canvas.offsetHeight);

    lines.forEach(function(line) {
      var lineElement = document.createElementNS(svgNS, "line");
      lineElement.setAttribute("x1", (line.x1 + 5000) * scale);
      lineElement.setAttribute("y1", (line.y1 + 5000) * scale);
      lineElement.setAttribute("x2", (line.x2 + 5000) * scale);
      lineElement.setAttribute("y2", (line.y2 + 5000) * scale);
      lineElement.setAttribute("stroke", line.color || "black");
      lineElement.setAttribute("stroke-width", "0.5vh");

      svg.appendChild(lineElement);
    });

    squares.forEach(function(square) {
        var rectElement = document.createElementNS(svgNS, "rect");
        rectElement.setAttribute("x", (square.x + 5000) * scale);
        rectElement.setAttribute("y", (square.y + 5000) * scale);
        rectElement.setAttribute("width", 100 * scale);
        rectElement.setAttribute("height", 100 * scale);
        rectElement.setAttribute("fill", "transparent");
        rectElement.setAttribute("stroke", square.color || "black");
        rectElement.setAttribute("stroke-width", square.strokeWidth || "0.4vh");

        svg.appendChild(rectElement);
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
      div.style.left = ((point.x + 5000) * scale) + 'px';
      div.style.top = ((point.y + 5000) * scale) + 'px';
      div.style.backgroundColor = '#' + point.color;
      canvas.appendChild(div);

      var nameDiv = document.createElement('div');
      nameDiv.className = 'info-name';
      nameDiv.innerHTML = point.name;
      nameDiv.dataset.pointName = point.name;
      nameDiv.style.visibility = 'hidden';
      canvas.appendChild(nameDiv);

      nameDiv.style.left = ((point.x + 5000) * scale) + 10 + 'px';
      nameDiv.style.top = ((point.y + 5000) * scale) - 20; + 'px';

      if (canvas.offsetWidth - (point.x + 5000) * scale < nameDiv.offsetWidth) {
        nameDiv.style.left = ((point.x + 5000) * scale) - nameDiv.offsetWidth - 10 + 'px';
      }

      div.addEventListener('click', function() {
        if (!div.classList.contains('clicked')) {
          nameDiv.style.visibility = 'visible';
          div.classList.add('clicked');
        } else {
          nameDiv.style.visibility = 'hidden';
          div.classList.remove('clicked');
        }
      });

      nameDiv.addEventListener('click', function() {
        if (div.classList.contains('clicked')) {
          nameDiv.style.visibility = 'hidden';
          div.classList.remove('clicked');
        }
      });

      var isMobile = /iPhone|iPad|iPod|Android/i.test(navigator.userAgent);

      if (!isMobile) {
        div.addEventListener('mouseover', function() {
          if (!div.classList.contains('clicked')) {
            nameDiv.style.visibility = 'visible';
          }
        });

        div.addEventListener('mouseout', function() {
          var nameDiv = canvas.querySelector(`.info-name[data-point-name="${point.name}"]`);
          if (!div.classList.contains('clicked')) {
            nameDiv.style.visibility = 'hidden';
          }
        });
      }
    });
  }

  function redrawPoints() {
    var canvas = document.getElementById('canvas');
    var scale = canvas.offsetWidth / 10000;
    var pointsElements = document.querySelectorAll('.point');

    pointsElements.forEach(function(pointElement) {
      var pointIndex = parseInt(pointElement.dataset.index);
      var point = points[pointIndex];
      pointElement.style.left = ((point.x + 5000) * scale) + 'px';
      pointElement.style.top = ((point.y + 5000) * scale) + 'px';

      var nameDiv = canvas.querySelector(`.info-name[data-point-name="${point.name}"]`);
      nameDiv.style.left = ((point.x + 5000) * scale) + 10 + 'px';
      nameDiv.style.top = ((point.y + 5000) * scale) - 20 + 'px';

      if (canvas.offsetWidth - (point.x + 5000) * scale < nameDiv.offsetWidth) {
        nameDiv.style.left = ((point.x + 5000) * scale) - nameDiv.offsetWidth - 10 + 'px';
      }
    });
  }

  window.onload = function() {
    var canvasContainer = document.getElementById('canvasContainer');

    // Обновление размеров canvas
    function updateCanvasSize() {
      canvasContainer.style.height = canvasContainer.offsetWidth - 4 + "px";
      redrawPoints();
      drawShapes();
    }

    updateCanvasSize();
    window.addEventListener('resize', updateCanvasSize);
  };

  drawPoints();
  drawShapes();
</script>

</body>
</html>