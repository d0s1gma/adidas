<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Adidas Store</title>
  <style>
    :root {
      --main-bg-light: #f4f4f4;
      --card-bg-light: #ffffff;
      --text-color-light: #111111;
      --accent-light: #0d0d0d;

      --main-bg-dark: #121212;
      --card-bg-dark: #1e1e1e;
      --text-color-dark: #f4f4f4;
      --accent-dark: #ffffff;
    }

    html[data-theme="light"] {
      --main-bg: var(--main-bg-light);
      --card-bg: var(--card-bg-light);
      --text-color: var(--text-color-light);
      --accent-color: var(--accent-light);
    }

    html[data-theme="dark"] {
      --main-bg: var(--main-bg-dark);
      --card-bg: var(--card-bg-dark);
      --text-color: var(--text-color-dark);
      --accent-color: var(--accent-dark);
    }

    body {
      background-color: var(--main-bg);
      color: var(--text-color);
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      transition: background 0.3s, color 0.3s;
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      background-color: var(--card-bg);
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
      transition: background 0.3s;
    }

    nav img {
      height: 40px;
    }

    .menu a {
      margin: 0 1rem;
      text-decoration: none;
      color: var(--text-color);
      font-weight: 600;
      transition: color 0.3s;
    }

    .theme-toggle {
      font-size: 1.3rem;
      background: none;
      border: none;
      cursor: pointer;
      color: var(--text-color);
      transition: color 0.3s;
    }

  </style>
</head>
<body>

<nav>
  <img src="https://upload.wikimedia.org/wikipedia/commons/2/20/Adidas_Logo.svg" alt="Adidas Logo">
  <div class="menu">
    <a href="#">Home</a>
    <a href="#">Men</a>
    <a href="#">Women</a>
    <a href="#">Kids</a>
  </div>
  <button class="theme-toggle" id="themeToggle">🌙</button>
</nav>

<script>
  const toggleBtn = document.getElementById('themeToggle');
  const root = document.documentElement;

  function setTheme(theme) {
    root.setAttribute('data-theme', theme);
    localStorage.setItem('theme', theme);
    toggleBtn.textContent = theme === 'dark' ? '☀️' : '🌙';
  }

  toggleBtn.addEventListener('click', () => {
    const currentTheme = root.getAttribute('data-theme');
    const newTheme = currentTheme === 'light' ? 'dark' : 'light';
    setTheme(newTheme);
  });

  const savedTheme = localStorage.getItem('theme') || 'light';
  setTheme(savedTheme);
</script>

</body>
</html>
