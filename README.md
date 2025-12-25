<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Всё о Scratch</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #8b2323; /* Тёмно‑красный */
      color: #fff;
      min-height: 100vh;
      position: relative;
      overflow-x: hidden;
    }
    /* Эффект падающего снега */
    .snow {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 1;
    }
    .snowflake {
      position: absolute;
      color: white;
      font-size: 1em;
      opacity: 0.8;
      animation: fall 10s linear infinite;
    }
    @keyframes fall {
      0% {
        transform: translateY(-10%);
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      90% {
        opacity: 1;
      }
      100% {
        transform: translateY(110%);
        opacity: 0;
      }
    }
    .container {
      position: relative;
      z-index: 2;
      max-width: 900px;
      margin: 0 auto;
      padding: 20px;
    }
    header {
      text-align: center;
      padding: 30px 0;
    }
    h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
    }
    .subtitle {
      font-style: italic;
      opacity: 0.9;
      margin-bottom: 30px;
    }
    .logo {
      width: 150px;
      height: 150px;
      border-radius: 50%;
      object-fit: cover;
      border: 5px solid #ff8c00; /* Оранжевый */
      box-shadow: 0 0 15px rgba(255, 140, 0, 0.6);
    }
    main {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
      margin-top: 30px;
    }
    .card {
      background: rgba(255, 255, 255, 0.15);
      border-radius: 15px;
      padding: 25px;
      backdrop-filter: blur(10px);
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
    }
    h2 {
      color: #ff8c00;
      margin-bottom: 15px;
      border-bottom: 2px solid #ff8c00;
      padding-bottom: 5px;
    }
    ul {
      list-style: none;
      padding-left: 0;
    }
    li {
      margin: 15px 0;
      padding-left: 20px;
      position: relative;
    }
    li::before {
      content: "→";
      color: #ff8c00;
      position: absolute;
      left: 0;
    }
    a {
      color: #fff;
      text-decoration: none;
      font-weight: 500;
      transition: color 0.3s;
    }
    a:hover {
      color: #ff8c00;
    }
    .image-section {
      grid-column: 1 / -1;
      text-align: center;
      margin: 40px 0;
    }
    .scratch-img {
      max-width: 100%;
      height: auto;
      border-radius: 15px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    }
    footer {
      text-align: center;
      margin-top: 50px;
      padding: 20px;
      font-size: 0.9em;
      opacity: 0.8;
    }
    @media (max-width: 768px) {
      main {
        grid-template-columns: 1fr;
      }
      h1 {
        font-size: 2em;
      }
    }
  </style>
</head>
<body>
  <!-- Эффект падающего снега -->
  <div class="snow" id="snow"></div>

  <div class="container">
    <header>
      <img src="https://scratch.mit.edu/static/img/scratch-logo.png" alt="Логотип Scratch" class="logo">
      <h1>Добро пожаловать в мир Scratch!</h1>
      <p class="subtitle">Платформа для обучения программированию через творчество</p>
    </header>

    <main>
      <!-- Ссылки на Scratch -->
      <div class="card">
        <h2>Официальные ресурсы</h2>
        <ul>
          <li><a href="https://scratch.mit.edu" target="_blank">Официальный сайт Scratch</a></li>
          <li><a href="https://scratch.mit.edu/ideas" target="_blank">Идеи для проектов</a></li>
          <li><a href="https://scratch.mit.edu/help" target="_blank">Справка и руководство</a></li>
          <li><a href="https://scratch.mit.edu/discuss" target="_blank">Форум сообщества</a></li>
        </ul>
      </div>

      <!-- Видеоуроки -->
      <div class="card">
        <h2>Видеоуроки</h2>
        <ul>
          <li><a href="https://www.youtube.com/results?search_query=scratch+уроки" target="_blank">Поиск уроков на YouTube</a></li>
          <li><a href="https://www.khanacademy.org/computing/computer-programming/scratch" target="_blank">Уроки на Khan Academy</a></li>
          <li><a href="https://www.codeclubworld.org/projects/?language=ru&tag=scratch" target="_blank">Проекты Code Club</a></li>
          <li><a href="https://edu.skratch.me/" target="_blank">Интерактивные уроки</a></li>
        </ul>
      </div>

      <!-- Документация и обучение -->
      <div class="card">
        <h2>Обучение и документация</h2>
        <ul>
          <li><a href="https://en.scratch-wiki.info/wiki/Main_Page" target="_blank">Scratch Wiki (англ.)</a></li>
          <li><a href="https://ru.scratch-wiki.info/wiki/Заглавная_страница" target="_blank">Scratch Wiki (рус.)</a></li>
          <li><a href="https://scratch.mit.edu/studios" target="_blank">Коллекции проектов</a></li>
          <li><a href="https://scratch.mit.edu/explore/projects/all" target="_blank">Галерея проектов</a></li>
        </ul>
      </div>

      <!-- Сообщество -->
      <div class="card">
        <h2>Сообщество</h2>
        <ul>
          <li><a href="https://scratch.mit.edu/my/" target="_blank">Мой профиль Scratch</a></li>
          <li><a href="https://scratch.mit.edu/teams" target="_blank">Команды и клубы</
