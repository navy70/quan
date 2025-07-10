<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Sidebar Menu | CodingNepal</title>
    <link rel="stylesheet" href="style.css" />
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded" />
    <script src="script.js" defer></script>
    <style>
      .hidden { display: none; }
    </style>
  </head>
  <body>
    <!-- Navbar -->
    <nav class="site-nav">
      <button class="sidebar-toggle">
        <span class="material-symbols-rounded">menu</span>
      </button>
    </nav>

    <div class="container">
      <!-- Sidebar -->
      <aside class="sidebar collapsed">
        <div class="sidebar-header">
          <img src="logo.png" alt="CodingNepal" class="header-logo" />
          <button class="sidebar-toggle">
            <span class="material-symbols-rounded">chevron_left</span>
          </button>
        </div>

        <div class="sidebar-content">
          <form action="#" class="search-form">
            <span class="material-symbols-rounded">search</span>
            <input type="search" placeholder="Search..." required />
          </form>

          <ul class="menu-list">
            <li class="menu-item"><a href="#" class="menu-link" onclick="showSection('dashboard')"><span class="material-symbols-rounded">dashboard</span><span class="menu-label">Dashboard</span></a></li>
            <li class="menu-item"><a href="#" class="menu-link" onclick="showSection('draw')"><span class="material-symbols-rounded">edit</span><span class="menu-label">Draw</span></a></li>
            <li class="menu-item"><a href="#" class="menu-link" onclick="showSection('game')"><span class="material-symbols-rounded">sports_esports</span><span class="menu-label">Game</span></a></li>
          </ul>
        </div>

        <div class="sidebar-footer">
          <button class="theme-toggle">
            <div class="theme-label">
              <span class="theme-icon material-symbols-rounded">dark_mode</span>
              <span class="theme-text">Dark Mode</span>
            </div>
            <div class="theme-toggle-track">
              <div class="theme-toggle-indicator"></div>
            </div>
          </button>
        </div>
      </aside>

      <!-- Main Content -->
      <div class="main-content">
        <div id="dashboard" class="page-section">
          <h1 class="page-title">Dashboard Overview</h1>
          <p class="card">Welcome to your dashboard! Use the menu to navigate.</p>
        </div>

        <div id="draw" class="page-section hidden">
          <section class="tools-board">
            <div class="row">
              <label class="title">Shapes</label>
              <ul class="options">
                <li class="option tool" id="rectangle"><img src="icons/rectangle.svg"><span>Rectangle</span></li>
                <li class="option tool" id="circle"><img src="icons/circle.svg"><span>Circle</span></li>
                <li class="option tool" id="triangle"><img src="icons/triangle.svg"><span>Triangle</span></li>
                <li class="option"><input type="checkbox" id="fill-color"><label for="fill-color">Fill color</label></li>
              </ul>
            </div>
            <div class="row">
              <label class="title">Options</label>
              <ul class="options">
                <li class="option active tool" id="brush"><img src="icons/brush.svg"><span>Brush</span></li>
                <li class="option tool" id="eraser"><img src="icons/eraser.svg"><span>Eraser</span></li>
                <li class="option"><input type="range" id="size-slider" min="1" max="30" value="5"></li>
              </ul>
            </div>
            <div class="row colors">
              <label class="title">Colors</label>
              <ul class="options">
                <li class="option"></li>
                <li class="option selected"></li>
                <li class="option"></li>
                <li class="option"></li>
                <li class="option"><input type="color" id="color-picker" value="#4A98F7"></li>
              </ul>
            </div>
            <div class="row buttons">
              <button class="clear-canvas">Clear Canvas</button>
              <button class="save-img">Save As Image</button>
            </div>
          </section>
          <section class="drawing-board"><canvas></canvas></section>
        </div>

        <div id="game" class="page-section hidden">
          <div class="wrapper">
            <ul class="cards">
              <!-- Bạn có thể rút gọn hoặc để nguyên danh sách 15 thẻ từ file game.html -->
              <li class="card"><div class="view front-view"><img src="images/que_icon.svg"></div><div class="view back-view"><img src="images/img-1.png"></div></li>
              <!-- thêm các thẻ khác tại đây -->
            </ul>
          </div>
        </div>
      </div>
    </div>

    <script>
      function showSection(id) {
        document.querySelectorAll('.page-section').forEach(sec => sec.classList.add('hidden'));
        document.getElementById(id).classList.remove('hidden');
      }
    </script>
  </body>
</html>
