<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>RS Online Shop</title>
  <meta
    name="description"
    content="RS Online Shop - Quality products at the best price."
  />

  <style>
    /* =========================
       RESET & GLOBAL
    ========================= */

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --primary: #111827;
      --secondary: #ef4444;
      --accent: #f59e0b;
      --light: #f8fafc;
      --white: #ffffff;
      --dark: #111827;
      --gray: #64748b;
      --border: #e5e7eb;
      --success: #16a34a;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: #f8fafc;
      color: var(--dark);
      line-height: 1.5;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    button,
    input {
      font-family: inherit;
    }

    img {
      width: 100%;
      display: block;
    }

    .container {
      width: min(1180px, 92%);
      margin: auto;
    }

    /* =========================
       TOP BAR
    ========================= */

    .top-bar {
      background: var(--primary);
      color: white;
      text-align: center;
      padding: 9px;
      font-size: 14px;
    }

    /* =========================
       HEADER
    ========================= */

    header {
      background: white;
      border-bottom: 1px solid var(--border);
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    .header-main {
      min-height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 25px;
    }

    .logo {
      font-size: 25px;
      font-weight: 800;
      white-space: nowrap;
    }

    .logo span {
      color: var(--secondary);
    }

    .search-box {
      flex: 1;
      max-width: 550px;
      position: relative;
    }

    .search-box input {
      width: 100%;
      border: 1px solid var(--border);
      background: #f8fafc;
      border-radius: 30px;
      padding: 13px 50px 13px 18px;
      outline: none;
      font-size: 15px;
    }

    .search-box button {
      position: absolute;
      right: 5px;
      top: 5px;
      border: none;
      background: var(--primary);
      color: white;
      width: 38px;
      height: 38px;
      border-radius: 50%;
      cursor: pointer;
    }

    .header-actions {
      display: flex;
      align-items: center;
      gap: 18px;
    }

    .cart-btn {
      border: none;
      background: transparent;
      font-size: 23px;
      cursor: pointer;
      position: relative;
    }

    .cart-count {
      position: absolute;
      top: -8px;
      right: -10px;
      background: var(--secondary);
      color: white;
      font-size: 11px;
      width: 20px;
      height: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
    }

    /* =========================
       NAVIGATION
    ========================= */

    nav {
      background: white;
      border-top: 1px solid #f1f5f9;
    }

    .nav-list {
      display: flex;
      justify-content: center;
      gap: 35px;
      list-style: none;
      padding: 13px 0;
      font-size: 14px;
      font-weight: 600;
    }

    .nav-list a:hover {
      color: var(--secondary);
    }

    /* =========================
       HERO
    ========================= */

    .hero {
      margin-top: 25px;
      min-height: 410px;
      border-radius: 20px;
      overflow: hidden;
      background:
        linear-gradient(
          90deg,
          rgba(0, 0, 0, 0.78),
          rgba(0, 0, 0, 0.25)
        ),
        url("https://images.unsplash.com/photo-1441986300917-64674bd600d8?auto=format&fit=crop&w=1600&q=80")
        center/cover;
      display: flex;
      align-items: center;
    }

    .hero-content {
      color: white;
      padding: 50px;
      max-width: 650px;
    }

    .hero-content small {
      color: #fbbf24;
      font-weight: bold;
      text-transform: uppercase;
      letter-spacing: 2px;
    }

    .hero-content h1 {
      font-size: clamp(36px, 6vw, 62px);
      line-height: 1.05;
      margin: 12px 0 18px;
    }

    .hero-content p {
      font-size: 17px;
      margin-bottom: 25px;
      color: #e5e7eb;
    }

    .hero-btn {
      display: inline-block;
      background: var(--secondary);
      color: white;
      padding: 13px 25px;
      border-radius: 7px;
      font-weight: bold;
    }

    .hero-btn:hover {
      background: #dc2626;
    }

    /* =========================
       SECTION
    ========================= */

    .section {
      padding: 55px 0;
    }

    .section-heading {
      display: flex;
      align-items: end;
      justify-content: space-between;
      margin-bottom: 25px;
      gap: 15px;
    }

    .section-heading h2 {
      font-size: 28px;
    }

    .section-heading p {
      color: var(--gray);
      font-size: 14px;
    }

    /* =========================
       CATEGORIES
    ========================= */

    .categories {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 18px;
    }

    .category {
      background: white;
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 25px;
      text-align: center;
      cursor: pointer;
      transition: 0.25s;
    }

    .category:hover {
      transform: translateY(-4px);
      box-shadow: 0 10px 25px rgba(0,0,0,.07);
    }

    .category-icon {
      width: 60px;
      height: 60px;
      margin: 0 auto 12px;
      border-radius: 50%;
      background: #fee2e2;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 28px;
    }

    .category h3 {
      font-size: 16px;
    }

    /* =========================
       FILTERS
    ========================= */

    .filters {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-bottom: 25px;
    }

    .filter-btn {
      border: 1px solid var(--border);
      background: white;
      padding: 9px 17px;
      border-radius: 30px;
      cursor: pointer;
      font-size: 14px;
    }

    .filter-btn.active,
    .filter-btn:hover {
      background: var(--primary);
      color: white;
    }

    /* =========================
       PRODUCTS
    ========================= */

    .products {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
    }

    .product {
      background: white;
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
      transition: 0.25s;
      position: relative;
    }

    .product:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 30px rgba(0,0,0,.08);
    }

    .product-image {
      height: 240px;
      overflow: hidden;
      background: #f1f5f9;
      cursor: pointer;
    }

    .product-image img {
      height: 100%;
      object-fit: cover;
      transition: 0.4s;
    }

    .product:hover .product-image img {
      transform: scale(1.05);
    }

    .discount {
      position: absolute;
      top: 12px;
      left: 12px;
      background: var(--secondary);
      color: white;
      padding: 5px 8px;
      border-radius: 5px;
      font-size: 12px;
      font-weight: bold;
    }

    .product-info {
      padding: 15px;
    }

    .product-category {
      color: var(--gray);
      font-size: 12px;
      margin-bottom: 5px;
    }

    .product-name {
      font-size: 16px;
      font-weight: bold;
      margin-bottom: 9px;
    }

    .rating {
      font-size: 13px;
      color: #f59e0b;
      margin-bottom: 8px;
    }

    .price-row {
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 13px;
    }

    .price {
      font-weight: 800;
      font-size: 18px;
    }

    .old-price {
      color: #94a3b8;
      text-decoration: line-through;
      font-size: 13px;
    }

    .product-buttons {
      display: flex;
      gap: 7px;
    }

    .add-cart,
    .buy-now {
      flex: 1;
      padding: 10px 7px;
      border-radius: 6px;
      border: none;
      cursor: pointer;
      font-weight: bold;
      font-size: 12px;
    }

    .add-cart {
      background: #f1f5f9;
      color: var(--dark);
    }

    .buy-now {
      background: var(--primary);
      color: white;
    }

    .add-cart:hover {
      background: #e2e8f0;
    }

    .buy-now:hover {
      background: #374151;
    }

    /* =========================
       PROMO
    ========================= */

    .promo {
      background: var(--primary);
      color: white;
      border-radius: 16px;
      padding: 45px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 30px;
    }

    .promo h2 {
      font-size: 32px;
      margin-bottom: 8px;
    }

    .promo p {
      color: #cbd5e1;
    }

    .promo a {
      background: var(--secondary);
      padding: 13px 22px;
      border-radius: 7px;
      font-weight: bold;
      white-space: nowrap;
    }

    /* =========================
       FEATURES
    ========================= */

    .features {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
    }

    .feature {
      background: white;
      padding: 25px;
      text-align: center;
      border: 1px solid var(--border);
      border-radius: 10px;
    }

    .feature-icon {
      font-size: 30px;
      margin-bottom: 10px;
    }

    .feature h3 {
      font-size: 16px;
      margin-bottom: 5px;
    }

    .feature p {
      font-size: 13px;
      color: var(--gray);
    }

    /* =========================
       FOOTER
    ========================= */

    footer {
      background: #0f172a;
      color: white;
      margin-top: 40px;
    }

    .footer-main {
      padding: 55px 0;
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1.4fr;
      gap: 40px;
    }

    .footer-logo {
      font-size: 25px;
      font-weight: bold;
      margin-bottom: 12px;
    }

    .footer-logo span {
      color: #ef4444;
    }

    footer p,
    footer a {
      color: #94a3b8;
      font-size: 14px;
    }

    footer h3 {
      margin-bottom: 15px;
    }

    .footer-links {
      list-style: none;
    }

    .footer-links li {
      margin-bottom: 9px;
    }

    .footer-links a:hover {
      color: white;
    }

    .copyright {
      border-top: 1px solid #1e293b;
      text-align: center;
      padding: 18px;
      color: #64748b;
      font-size: 13px;
    }

    /* =========================
       CART SIDEBAR
    ========================= */

    .cart-overlay {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,.5);
      z-index: 2000;
      opacity: 0;
      visibility: hidden;
      transition: .3s;
    }

    .cart-overlay.open {
      opacity: 1;
      visibility: visible;
    }

    .cart-sidebar {
      position: absolute;
      right: 0;
      top: 0;
      width: min(420px, 92%);
      height: 100%;
      background: white;
      padding: 20px;
      transform: translateX(100%);
      transition: .3s;
      display: flex;
      flex-direction: column;
    }

    .cart-overlay.open .cart-sidebar {
      transform: translateX(0);
    }

    .cart-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid var(--border);
      padding-bottom: 15px;
    }

    .close-cart {
      border: none;
      background: none;
      font-size: 28px;
      cursor: pointer;
    }

    .cart-items {
      flex: 1;
      overflow-y: auto;
      padding: 15px 0;
    }

    .cart-item {
      display: flex;
      gap: 12px;
      border-bottom: 1px solid var(--border);
      padding: 12px 0;
    }

    .cart-item img {
      width: 70px;
      height: 70px;
      object-fit: cover;
      border-radius: 7px;
    }

    .cart-item-info {
      flex: 1;
    }

    .cart-item-info h4 {
      font-size: 14px;
      margin-bottom: 4px;
    }

    .cart-item-info p {
      font-weight: bold;
    }

    .qty-controls {
      display: flex;
      align-items: center;
      gap: 8px;
      margin-top: 6px;
    }

    .qty-controls button {
      width: 25px;
      height: 25px;
      border: 1px solid var(--border);
      background: white;
      border-radius: 4px;
      cursor: pointer;
    }

    .cart-footer {
      border-top: 1px solid var(--border);
      padding-top: 15px;
    }

    .total-row {
      display: flex;
      justify-content: space-between;
      font-size: 19px;
      font-weight: bold;
      margin-bottom: 15px;
    }

    .checkout {
      display: block;
      width: 100%;
      border: none;
      background: var(--success);
      color: white;
      padding: 14px;
      border-radius: 7px;
      font-weight: bold;
      cursor: pointer;
      text-align: center;
    }

    /* =========================
       PRODUCT MODAL
    ========================= */

    .modal {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,.65);
      z-index: 3000;
      display: none;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }

    .modal.open {
      display: flex;
    }

    .modal-box {
      background: white;
      width: min(850px, 100%);
      border-radius: 15px;
      overflow: hidden;
      position: relative;
      max-height: 90vh;
      overflow-y: auto;
    }

    .modal-close {
      position: absolute;
      right: 15px;
      top: 10px;
      z-index: 2;
      width: 35px;
      height: 35px;
      border: none;
      background: white;
      border-radius: 50%;
      font-size: 23px;
      cursor: pointer;
      box-shadow: 0 2px 10px rgba(0,0,0,.15);
    }

    .modal-content {
      display: grid;
      grid-template-columns: 1fr 1fr;
    }

    .modal-image {
      min-height: 450px;
    }

    .modal-image img {
      height: 100%;
      object-fit: cover;
    }

    .modal-details {
      padding: 45px 30px;
    }

    .modal-details h2 {
      font-size: 30px;
      margin-bottom: 12px;
    }

    .modal-price {
      font-size: 26px;
      font-weight: bold;
      margin: 15px 0;
    }

    .modal-description {
      color: var(--gray);
      margin-bottom: 20px;
    }

    .modal-buy {
      display: inline-block;
      background: var(--success);
      color: white;
      padding: 13px 25px;
      border-radius: 7px;
      font-weight: bold;
    }

    /* =========================
       RESPONSIVE
    ========================= */

    @media (max-width: 900px) {
      .products {
        grid-template-columns: repeat(3, 1fr);
      }

      .categories,
      .features {
        grid-template-columns: repeat(2, 1fr);
      }

      .footer-main {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    @media (max-width: 650px) {
      .header-main {
        flex-wrap: wrap;
        padding: 12px 0;
        gap: 12px;
      }

      .search-box {
        order: 3;
        flex-basis: 100%;
      }

      .nav-list {
        overflow-x: auto;
        justify-content: flex-start;
        padding-left: 4%;
        gap: 25px;
      }

      .hero {
        min-height: 390px;
      }

      .hero-content {
        padding: 30px 25px;
      }

      .hero-content h1 {
        font-size: 40px;
      }

      .products {
        grid-template-columns: repeat(2, 1fr);
        gap: 12px;
      }

      .product-image {
        height: 190px;
      }

      .categories,
      .features {
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
      }

      .category {
        padding: 18px 10px;
      }

      .promo {
        padding: 30px 20px;
        flex-direction: column;
        align-items: flex-start;
      }

      .footer-main {
        grid-template-columns: 1fr;
      }

      .modal-content {
        grid-template-columns: 1fr;
      }

      .modal-image {
        min-height: 300px;
      }
    }

    @media (max-width: 400px) {
      .products {
        grid-template-columns: 1fr;
      }

      .product-image {
        height: 270px;
      }
    }
  </style>
</head>

<body>

  <!-- TOP BAR -->
  <div class="top-bar">
    🚚 Free Delivery on selected orders | Cash on Delivery Available
  </div>

  <!-- HEADER -->
  <header>
    <div class="container header-main">

      <a href="#" class="logo">
        RS <span>Online Shop</span>
      </a>

      <div class="search-box">
        <input
          type="text"
          id="searchInput"
          placeholder="Search products..."
        />
        <button onclick="searchProducts()">🔍</button>
      </div>

      <div class="header-actions">
        <button class="cart-btn" onclick="openCart()">
          🛒
          <span class="cart-count" id="cartCount">0</span>
        </button>
      </div>

    </div>

    <nav>
      <ul class="nav-list">
        <li><a href="#home">Home</a></li>
        <li><a href="#products">Shop</a></li>
        <li><a href="#categories">Categories</a></li>
        <li><a href="#offers">Offers</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- HERO -->
  <main id="home">

    <div class="container">
      <section class="hero">

        <div class="hero-content">
          <small>Welcome to RS Online Shop</small>

          <h1>
            Quality Products.<br>
            Better Prices.
          </h1>

          <p>
            Discover our latest collection and shop your favorite
            products from the comfort of your home.
          </p>

          <a href="#products" class="hero-btn">
            Shop Now →
          </a>
        </div>

      </section>
    </div>

    <!-- CATEGORIES -->
    <section class="section" id="categories">

      <div class="container">

        <div class="section-heading">
          <div>
            <h2>Shop by Category</h2>
            <p>Explore our popular categories</p>
          </div>
        </div>

        <div class="categories">

          <div class="category" onclick="filterProducts('Fashion')">
            <div class="category-icon">👕</div>
            <h3>Fashion</h3>
          </div>

          <div class="category" onclick="filterProducts('Electronics')">
            <div class="category-icon">📱</div>
            <h3>Electronics</h3>
          </div>

          <div class="category" onclick="filterProducts('Beauty')">
            <div class="category-icon">💄</div>
            <h3>Beauty</h3>
          </div>

          <div class="category" onclick="filterProducts('Home')">
            <div class="category-icon">🏠</div>
            <h3>Home & Living</h3>
          </div>

        </div>

      </div>

    </section>

    <!-- PRODUCTS -->
    <section class="section" id="products">

      <div class="container">

        <div class="section-heading">
          <div>
            <h2>Featured Products</h2>
            <p>Our most popular products</p>
          </div>
        </div>

        <div class="filters">

          <button
            class="filter-btn active"
            onclick="filterProducts('All', this)"
          >
            All
          </button>

          <button
            class="filter-btn"
            onclick="filterProducts('Fashion', this)"
          >
            Fashion
          </button>

          <button
            class="filter-btn"
            onclick="filterProducts('Electronics', this)"
          >
            Electronics
          </button>

          <button
            class="filter-btn"
            onclick="filterProducts('Beauty', this)"
          >
            Beauty
          </button>

          <button
            class="filter-btn"
            onclick="filterProducts('Home', this)"
          >
            Home
          </button>

        </div>

        <div class="products" id="productGrid"></div>

      </div>

    </section>

    <!-- PROMO -->
    <section class="section" id="offers">

      <div class="container">

        <div class="promo">

          <div>
            <h2>Special Offer</h2>
            <p>
              Get amazing discounts on selected products.
              Limited time only!
            </p>
          </div>

          <a href="#products">
            Shop Offers →
          </a>

        </div>

      </div>

    </section>

    <!-- FEATURES -->
    <section class="section">

      <div class="container">

        <div class="features">

          <div class="feature">
            <div class="feature-icon">🚚</div>
            <h3>Fast Delivery</h3>
            <p>Quick and reliable delivery service.</p>
          </div>

          <div class="feature">
            <div class="feature-icon">💳</div>
            <h3>Secure Payment</h3>
            <p>Safe and trusted payment options.</p>
          </div>

          <div class="feature">
            <div class="feature-icon">🔄</div>
            <h3>Easy Return</h3>
            <p>Simple return policy for customers.</p>
          </div>

          <div class="feature">
            <div class="feature-icon">📞</div>
            <h3>Customer Support</h3>
            <p>We're here to help you.</p>
          </div>

        </div>

      </div>

    </section>

  </main>

  <!-- FOOTER -->
  <footer id="contact">

    <div class="container footer-main">

      <div>
        <div class="footer-logo">
          RS <span>Online Shop</span>
        </div>

        <p>
          Your trusted online shopping destination.
          Quality products at affordable prices.
        </p>
      </div>

      <div>
        <h3>Quick Links</h3>

        <ul class="footer-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#products">Shop</a></li>
          <li><a href="#offers">Offers</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>

      <div>
        <h3>Categories</h3>

        <ul class="footer-links">
          <li><a href="#">Fashion</a></li>
          <li><a href="#">Electronics</a></li>
          <li><a href="#">Beauty</a></li>
          <li><a href="#">Home & Living</a></li>
        </ul>
      </div>

      <div>
        <h3>Contact Us</h3>

        <p>📞 +880 1XXXXXXXXX</p>
        <p>📧 support@rsonlineshop.com</p>
        <p>📍 Bangladesh</p>
      </div>

    </div>

    <div class="copyright">
      © 2026 RS Online Shop. All Rights Reserved.
    </div>

  </footer>

  <!-- CART -->
  <div class="cart-overlay" id="cartOverlay">

    <div class="cart-sidebar">

      <div class="cart-header">

        <h2>Your Cart</h2>

        <button class="close-cart" onclick="closeCart()">
          ×
        </button>

      </div>

      <div class="cart-items" id="cartItems">
        <p style="text-align:center;color:#64748b;padding:30px;">
          Your cart is empty.
        </p>
      </div>

      <div class="cart-footer">

        <div class="total-row">
          <span>Total:</span>
          <span id="cartTotal">৳0</span>
        </div>

        <button class="checkout" onclick="checkoutWhatsApp()">
          Order via WhatsApp
        </button>

      </div>

    </div>

  </div>

  <!-- PRODUCT MODAL -->
  <div class="modal" id="productModal">

    <div class="modal-box">

      <button class="modal-close" onclick="closeModal()">
        ×
      </button>

      <div class="modal-content">

        <div class="modal-image">
          <img id="modalImage" src="" alt="">
        </div>

        <div class="modal-details">

          <div id="modalCategory"></div>

          <h2 id="modalName"></h2>

          <div class="rating">
            ★★★★★
          </div>

          <div class="modal-price" id="modalPrice"></div>

          <p class="modal-description">
            Premium quality product from RS Online Shop.
            Order now and enjoy our reliable delivery service.
          </p>

          <a
            href="#"
            class="modal-buy"
            id="modalBuy"
          >
            Order Now
          </a>

        </div>

      </div>

    </div>

  </div>


  <script>

    /* =================================
       PRODUCT DATA
    ================================= */

    const products = [

      {
        id: 1,
        name: "Premium T-Shirt",
        category: "Fashion",
        price: 650,
        oldPrice: 850,
        discount: "24% OFF",
        rating: 5,
        image:
          "https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?auto=format&fit=crop&w=700&q=80"
      },

      {
        id: 2,
        name: "Wireless Headphone",
        category: "Electronics",
        price: 1450,
        oldPrice: 1800,
        discount: "19% OFF",
        rating: 5,
        image:
          "https://images.unsplash.com/photo-1505740420928-5e560c06d30e?auto=format&fit=crop&w=700&q=80"
      },

      {
        id: 3,
        name: "Smart Watch",
        category: "Electronics",
        price: 2200,
        oldPrice: 2900,
        discount: "24% OFF",
        rating: 5,
        image:
          "https://images.unsplash.com/photo-1523275335684-37898b6baf30?auto=format&fit=crop&w=700&q=80"
      },

      {
        id: 4,
        name: "Women's Handbag",
        category: "Fashion",
        price: 1200,
        oldPrice: 1500,
        discount: "20% OFF",
        rating: 5,
        image:
          "https://images.unsplash.com/photo-1584917865442-de89df76afd3?auto=format&fit=crop&w=700&q=80"
      },

      {
        id: 5,
        name: "Skin Care Product",
        category: "Beauty",
        price: 850,
        oldPrice: 1100,
        discount: "23% OFF",
        rating: 5,
        image:
          "https://images.unsplash.com/photo-1556229010-6c3f2c9ca5f8?auto=format&fit=crop&w=700&q=80"
      },

      {
        id: 6,
        name: "Modern Table Lamp",
        category: "Home",
        price: 950,
        oldPrice: 1250,
        discount: "24% OFF",
        rating: 5,
        image:
          "https://images.unsplash.com/photo-1507473885765-e6ed057f782c?auto=format&fit=crop&w=700&q=80"
      },

      {
        id: 7,
        name: "Running Shoes",
        category: "Fashion",
        price: 1800,
        oldPrice: 2300,
        discount: "22% OFF",
        rating: 5,
        image:
          "https://images.unsplash.com/photo-1542291026-7eec264c27ff?auto=format&fit=crop&w=700&q=80"
      },

      {
        id: 8,
        name: "Bluetooth Speaker",
        category: "Electronics",
        price: 1250,
        oldPrice: 1600,
        discount: "22% OFF",
        rating: 5,
        image:
          "https://images.unsplash.com/photo-1608043152269-423dbba4e7e1?auto=format&fit=crop&w=700&q=80"
      }

    ];


    /* =================================
       CART
    ================================= */

    let cart = [];


    /* =================================
       DISPLAY PRODUCTS
    ================================= */

    function displayProducts(list = products) {

      const grid =
        document.getElementById("productGrid");

      grid.innerHTML = "";

      if (list.length === 0) {

        grid.innerHTML = `
          <p style="
            grid-column:1/-1;
            text-align:center;
            padding:50px;
            color:#64748b;
          ">
            No products found.
          </p>
        `;

        return;
      }


      list.forEach(product => {

        const card = document.createElement("div");

        card.className = "product";

        card.innerHTML = `

          <div class="discount">
            ${product.discount}
          </div>

          <div
            class="product-image"
            onclick="openProduct(${product.id})"
          >
            <img
              src="${product.image}"
              alt="${product.name}"
              loading="lazy"
            >
          </div>

          <div class="product-info">

            <div class="product-category">
              ${product.category}
            </div>

            <div class="product-name">
              ${product.name}
            </div>

            <div class="rating">
              ★★★★★
            </div>

            <div class="price-row">

              <span class="price">
                ৳${product.price}
              </span>

              <span class="old-price">
                ৳${product.oldPrice}
              </span>

            </div>

            <div class="product-buttons">

              <button
                class="add-cart"
                onclick="addToCart(${product.id})"
              >
                🛒 Add Cart
              </button>

              <button
                class="buy-now"
                onclick="buyNow(${product.id})"
              >
                Buy Now
              </button>

            </div>

          </div>
        `;

        grid.appendChild(card);

      });

    }


    /* =================================
       FILTER
    ================================= */

    function filterProducts(category, button) {

      if (button) {

        document
          .querySelectorAll(".filter-btn")
          .forEach(btn => {
            btn.classList.remove("active");
          });

        button.classList.add("active");
      }

      if (category === "All") {

        displayProducts(products);

      } else {

        const filtered =
          products.filter(
            product =>
              product.category === category
          );

        displayProducts(filtered);
      }

      document
        .getElementById("products")
        .scrollIntoView({
          behavior: "smooth"
        });

    }


    /* =================================
       SEARCH
    ================================= */

    function searchProducts() {

      const query =
        document
          .getElementById("searchInput")
          .value
          .toLowerCase()
          .trim();

      const result =
        products.filter(product =>
          product.name
            .toLowerCase()
            .includes(query) ||
          product.category
            .toLowerCase()
            .includes(query)
        );

      displayProducts(result);

      document
        .getElementById("products")
        .scrollIntoView({
          behavior: "smooth"
        });

    }


    document
      .getElementById("searchInput")
      .addEventListener(
        "keyup",
        function(event) {

          if (event.key === "Enter") {
            searchProducts();
          }

        }
      );


    /* =================================
       ADD TO CART
    ================================= */

    function addToCart(id) {

      const product =
        products.find(p => p.id === id);

      const existing =
        cart.find(item => item.id === id);

      if (existing) {

        existing.quantity++;

      } else {

        cart.push({
          ...product,
          quantity: 1
        });

      }

      updateCart();

      alert(
        product.name +
        " added to your cart!"
      );

    }


    /* =================================
       UPDATE CART
    ================================= */

    function updateCart() {

      const count =
        cart.reduce(
          (total, item) =>
            total + item.quantity,
          0
        );

      document
        .getElementById("cartCount")
        .textContent = count;


      const cartItems =
        document.getElementById("cartItems");

      if (cart.length === 0) {

        cartItems.innerHTML = `
          <p style="
            text-align:center;
            color:#64748b;
            padding:30px;
          ">
            Your cart is empty.
          </p>
        `;

        document
          .getElementById("cartTotal")
          .textContent = "৳0";

        return;
      }


      cartItems.innerHTML = "";


      let total = 0;


      cart.forEach(item => {

        total +=
          item.price * item.quantity;


        const div =
          document.createElement("div");

        div.className = "cart-item";

        div.innerHTML = `

          <img
            src="${item.image}"
            alt="${item.name}"
          >

          <div class="cart-item-info">

            <h4>${item.name}</h4>

            <p>
              ৳${item.price}
            </p>

            <div class="qty-controls">

              <button
                onclick="changeQuantity(${item.id}, -1)"
              >
                −
              </button>

              <span>
                ${item.quantity}
              </span>

              <button
                onclick="changeQuantity(${item.id}, 1)"
              >
                +
              </button>

              <button
                onclick="removeFromCart(${item.id})"
                style="
                  margin-left:auto;
                  color:#ef4444;
                  border:none;
                "
              >
                🗑
              </button>

            </div>

          </div>
        `;

        cartItems.appendChild(div);

      });


      document
        .getElementById("cartTotal")
        .textContent =
        "৳" + total.toLocaleString();

    }


    /* =================================
       CHANGE QUANTITY
    ================================= */

    function changeQuantity(id, amount) {

      const item =
        cart.find(item => item.id === id);

      if (!item) return;

      item.quantity += amount;

      if (item.quantity <= 0) {

        cart =
          cart.filter(
            item => item.id !== id
          );

      }

      updateCart();

    }


    /* =================================
       REMOVE CART ITEM
    ================================= */

    function removeFromCart(id) {

      cart =
        cart.filter(
          item => item.id !== id
        );

      updateCart();

    }


    /* =================================
       OPEN CART
    ================================= */

    function openCart() {

      document
        .getElementById("cartOverlay")
        .classList.add("open");

    }


    function closeCart() {

      document
        .getElementById("cartOverlay")
        .classList.remove("open");

    }


    /* =================================
       BUY NOW
    ================================= */

    function buyNow(id) {

      const product =
        products.find(
          product => product.id === id
        );

      const phone =
        "8801XXXXXXXXX";

      const message =
        `Hello RS Online Shop,%0A%0A` +
        `I want to order:%0A` +
        `${product.name}%0A` +
        `Price: ৳${product.price}`;

      window.open(
        `https://wa.me/${phone}?text=${message}`,
        "_blank"
      );

    }


    /* =================================
       CHECKOUT VIA WHATSAPP
    ================================= */

    function checkoutWhatsApp() {

      if (cart.length === 0) {

        alert("Your cart is empty.");

        return;
      }


      const phone =
        "8801XXXXXXXXX";


      let message =
        "Hello RS Online Shop,%0A%0A" +
        "I want to place an order:%0A%0A";


      let total = 0;


      cart.forEach(item => {

        const subtotal =
          item.price * item.quantity;

        total += subtotal;


        message +=
          `• ${item.name} x ${item.quantity} = ৳${subtotal}%0A`;

      });


      message +=
        `%0ATotal: ৳${total}`;


      window.open(
        `https://wa.me/${phone}?text=${message}`,
        "_blank"
      );

    }


    /* =================================
       PRODUCT MODAL
    ================================= */

    function openProduct(id) {

      const product =
        products.find(
          product => product.id === id
        );

      document
        .getElementById("modalImage")
        .src = product.image;

      document
        .getElementById("modalName")
        .textContent =
        product.name;

      document
        .getElementById("modalCategory")
        .textContent =
        product.category;

      document
        .getElementById("modalPrice")
        .textContent =
        "৳" +
        product.price.toLocaleString();


      document
        .getElementById("modalBuy")
        .onclick = function() {

          buyNow(product.id);

        };


      document
        .getElementById("productModal")
        .classList.add("open");

    }


    function closeModal() {

      document
        .getElementById("productModal")
        .classList.remove("open");

    }


    /* =================================
       CLOSE MODAL ON OUTSIDE CLICK
    ================================= */

    document
      .getElementById("productModal")
      .addEventListener(
        "click",
        function(event) {

          if (event.target === this) {
            closeModal();
          }

        }
      );


    /* =================================
       INITIALIZE
    ================================= */

    displayProducts();

    updateCart();

  </script>

</body>
</html>