<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cherry's Fast Food</title>
  <style>
    /* === GENERAL STYLES === */
    body {
      margin: 0;
      font-family: "Poppins", sans-serif;
      background-color: #fff;
      color: #333;
      overflow-x: hidden;
    }

    h1, h2 {
      margin: 0;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    /* === HOMEPAGE === */
    .homepage {
      height: 100vh;
      width: 100%;
      background:
        linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)),
        url('cherrys-logo.png') no-repeat center center;
      background-size: contain;
      background-color: #000;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      animation: fadeIn 1.5s ease-in forwards, slowZoom 25s ease-in-out infinite alternate;
      position: relative;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: scale(0.98);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }

    @keyframes slowZoom {
      0% {
        background-size: contain;
      }
      100% {
        background-size: cover;
      }
    }

    .menu-btn {
      font-family: 'Poppins', sans-serif;
      font-size: 2rem;
      font-weight: 600;
      color: #fff;
      background-color: #e60023;
      padding: 15px 50px;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 20px rgba(230, 0, 35, 0.5);
      margin-top: 60px;
    }

    .menu-btn:hover {
      background-color: #ff002b;
      transform: scale(1.08);
      box-shadow: 0 6px 25px rgba(255, 0, 43, 0.6);
    }

    /* === MENU CATEGORIES PAGE === */
    .menu-categories {
      display: none;
      min-height: 100vh;
      padding: 60px 20px;
      background: #fff5f5;
      text-align: center;
      animation: fadeIn 1s ease;
    }

    .categories-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      margin-top: 50px;
    }

    .category-card {
      background: #fff;
      border-radius: 20px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
      padding: 30px;
      font-size: 1.5rem;
      font-weight: 600;
      color: #e60023;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .category-card:hover {
      transform: translateY(-10px);
      background: #e60023;
      color: #fff;
    }

    /* === CATEGORY DETAIL PAGE === */
    .category-page {
      display: none;
      min-height: 100vh;
      padding: 60px 20px;
      background-size: cover;
      background-position: center;
      color: #fff;
      text-align: center;
      animation: fadeIn 1s ease;
    }

    .menu-items {
      max-width: 800px;
      margin: 50px auto;
      background: rgba(0, 0, 0, 0.6);
      border-radius: 20px;
      padding: 20px;
    }

    .menu-item {
      display: flex;
      justify-content: space-between;
      padding: 10px 0;
      border-bottom: 1px solid rgba(255,255,255,0.2);
      font-size: 1.1rem;
    }

    .back-btn {
      background: #e60023;
      border: none;
      color: #fff;
      padding: 10px 25px;
      border-radius: 25px;
      font-weight: 600;
      cursor: pointer;
      margin-top: 20px;
      transition: 0.3s;
    }

    .back-btn:hover {
      background: #ff002b;
      transform: scale(1.05);
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <!-- HOMEPAGE -->
  <section class="homepage" id="home">
    <button class="menu-btn" onclick="showCategories()">Menu</button>
  </section>

  <!-- MENU CATEGORIES -->
  <section class="menu-categories" id="categories">
    <h1>🍒 Cherry’s Menu Categories</h1>
    <div class="categories-grid">
      <div class="category-card" onclick="openCategory('fastfood')">● Fast Food</div>
      <div class="category-card" onclick="openCategory('pizzas')">● Pizzas</div>
      <div class="category-card" onclick="openCategory('grillades')">● Grillades</div>
      <div class="category-card" onclick="openCategory('mixtes')">● Mixtes à partager</div>
      <div class="category-card" onclick="openCategory('glace')">● Glaces</div>
      <div class="category-card" onclick="openCategory('cafe')">● Café</div>
      <div class="category-card" onclick="openCategory('the')">● Thé</div>
      <div class="category-card" onclick="openCategory('mocktail')">● Mocktails</div>
    </div>
  </section>

  <!-- FAST FOOD CATEGORY PAGE -->
  <section class="category-page" id="fastfood" style="background-image:url('https://images.unsplash.com/photo-1606755962773-0b850fa995ed?auto=format&fit=crop&w=1400&q=80');">
    <h1>🍔 Fast Food</h1>
    <div class="menu-items">
      <div class="menu-item"><span>Gyros au poulet</span><span>3000f</span></div>
      <div class="menu-item"><span>Gyros au bœuf</span><span>2000f</span></div>
      <div class="menu-item"><span>Gyros Cherry's</span><span>4500f</span></div>
      <div class="menu-item"><span>Sandwich poulet</span><span>1500f</span></div>
      <div class="menu-item"><span>Hamburger</span><span>2500f</span></div>
      <div class="menu-item"><span>Tacos Cherry's</span><span>4500f</span></div>
      <div class="menu-item"><span>KFC</span><span>4000f</span></div>
    </div>
    <button class="back-btn" onclick="backToCategories()">⬅ Back</button>
  </section>

  <!-- ADD OTHER CATEGORY PAGES (same structure as above) -->

  <script>
    function showCategories() {
      document.getElementById('home').style.display = 'none';
      document.getElementById('categories').style.display = 'block';
      window.scrollTo(0, 0);
    }

    function openCategory(id) {
      document.getElementById('categories').style.display = 'none';
      document.getElementById(id).style.display = 'block';
      window.scrollTo(0, 0);
    }

    function backToCategories() {
      const pages = document.querySelectorAll('.category-page');
      pages.forEach(page => page.style.display = 'none');
      document.getElementById('categories').style.display = 'block';
      window.scrollTo(0, 0);
    }
  </script>
</body>
</html>
