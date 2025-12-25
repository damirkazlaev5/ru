<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Scratch</title>
  <style>
    * {margin:0;padding:0;box-sizing:border-box;}
    body {font-family:sans-serif;background:#8b2323;color:#fff;min-height:100vh;position:relative;}
    .snow {position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:1;}
    .snowflake {position:absolute;color:#fff;font-size:1em;opacity:0.8;animation:fall 10s linear infinite;}
    @keyframes fall {0%{transform:translateY(-10%);opacity:0}10%,90%{opacity:1}100%{transform:translateY(110%);opacity:0}}
    .container {position:relative;z-index:2;max-width:900px;margin:0 auto;padding:10px;}
    header {text-align:center;padding:20px 0;}
    h1 {font-size:2em;margin-bottom:10px;text-shadow:2px 2px 4px rgba(0,0,0,0.5);}
    .nav {display:flex;justify-content:center;gap:15px;margin:15px 0;}
    .btn {background:#ff8c00;color:#fff;border:none;padding:10px 15px;border-radius:5px;cursor:pointer;font-weight:bold;}
    .btn:hover {background:#e67e00;}
    .section {display:none;padding:20px;background:rgba(255,255,255,0.1);border-radius:10px;margin-top:15px;}
    .active {display:block;}
    .grid {display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:15px;margin-top:15px;}
    .card {background:rgba(0,0,0,0.2);border-radius:8px;padding:15px;text-align:center;}
    .card img {max-width:100%;border-radius:8px;}
    .card a {color:#fff;text-decoration:none;display:block;margin-top:10px;font-weight:bold;}
    .card a:hover {color:#ff8c00;}
    footer {text-align:center;margin-top:30px;padding:15px;font-size:0.9em;opacity:0.8;}
  </style>
</head>
<body>
  <div class="snow" id="snow"></div>
  <div class="container">
    <header>
      <img src="https://scratch.mit.edu/static/img/scratch-logo.png" alt="Scratch" style="width:120px;border:3px solid #ff8c00;border-radius:50%;">
      <h1>Scratch</h1>
    </header>

    <!-- Меню навигации -->
    <div class="nav">
      <button class="btn" onclick="showSection('videos')">Видеоуроки</button>
      <button class="btn" onclick="showSection('projects')">Мои проекты</button>
      <button class="btn" onclick="showSection('links')">Полезные ссылки</button>
    </div>

    <!-- Разделы -->
    <div id="videos" class="section active">
      <h2>Видеоуроки</h2>
      <div class="grid">
        <div class="card">
          <img src="https://i.ytimg.com/vi/dQw4w9WgXcQ/hqdefault.jpg" alt="Урок 1">
          <a href="https://youtube.com/watch?v=dQw4w9WgXcQ" target="_blank">Основы Scratch</a>
        </div>
        <div class="card">
          <img src="https://i.ytimg.com/vi/abc123/hqdefault.jpg" alt="Урок 2">
          <a href="https://youtube.com/watch?v=abc123" target="_blank">Анимация в Scratch</a>
        </div>
      </div>
    </div>

    <div id="projects" class="section">
      <h2>Мои проекты</h2>
      <div class="grid">
        <div class="card">
          <img src="https://scratch.mit.edu/static/img/projects/project-default.png" alt="Проект 1">
          <a href="#" target="_blank">Игра «Лабиринт»</a>
        </div>
        <div class="card">
          <img src="https://scratch.mit.edu/static/img/projects/project-default.png" alt="Проект 2">
          <a href="#" target="_blank">Мультфильм «Кот»</a>
        </div>
      </div>
    </div>

    <div id="links" class="section">
      <h2>Полезные ссылки</h2>
      <div class="grid">
        <div class="card">
          <img src="https://scratch.mit.edu/static/img/logo.png" alt="Официальный сайт">
          <a href="https://scratch.mit.edu" target="_blank">Официальный сайт</a>
        </div>
        <div class="card">
          <img src="https://en.scratch-wiki.info/wiki/images/thumb/Scratch_Wiki_Logo.png/80px-Scratch_Wiki_Logo.png" alt="Wiki">
          <a href="https://ru.scratch-wiki.info" target="_blank">Scratch Wiki</a>
        </div>
        <div class="card">
          <img src="https://www.khanacademy.org/images/logo-square.png" alt="Khan Academy">
          <a href="https://www.khanacademy.org/computing/computer-programming/scratch" target="_blank">Khan Academy</a>
        </div>
      </div>
    </div>

    <footer>
      © 2025 Scratch | Образовательный ресурс
    </footer>
  </div>

  <script>
    // Функция переключения разделов
    function showSection(id) {
      document.querySelectorAll('.section').forEach(section => {
        section.classList.toggle('active', section.id === id);
      });
    }

    // Генерация снежинок
    function createSnowflake() {
      const snow = document.getElementById('snow');
      const flake = document.createElement('div');
      flake.className = 'snowflake';
      flake.textContent = '❄';

      const size = Math.random() * 20 + 10;
      const left = Math.random() * 100;
      const opacity = Math.random() * 0.7 + 0.3;
      const duration = Math.random() * 5 + 5;

      flake.style.fontSize = `${size}px`;
      flake.style.left = `${left}%`;
      flake.style.opacity = opacity;
      flake.style.animationDuration = `${duration}s`;

      snow.appendChild(flake);

      setTimeout(() => flake.remove(), duration * 1000);
    }

    setInterval(createSnowflake, 200);
    for (let i = 0; i < 15; i++) createSnowflake();
  </script>
</body>
</html>
