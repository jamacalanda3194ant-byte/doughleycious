# doughleycious
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dough Leycious - Pick Your Box</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

<!-- navigation bar -->
<nav class="navbar">
  <div class="nav-logo">DoughLEYcious</div>
  <ul class="nav-links">
    <li><a href="#">Shop</a></li>
    <li><a href="#">Flavors</a></li>
    <li>
  <a href="#">Cart (<span id="cart-count">0</span>)</a>
</li>
  </ul>
</nav>

<!-- flat image sa header -->
<header class="header">
  <img src="images/header.jpg" alt="Cookies Banner">

  <div class="header-overlay">
    <h1>Freshly Baked Cookies</h1>
    <p>Choose how you want to order</p>

    <div class="order-options">
      <button onclick="selectOrder('4pcs')">Box of 4</button>
      <button onclick="selectOrder('8pcs')">Box of 8</button>
      <button onclick="selectOrder('per piece')">Per Piece</button>
    </div>
  </div>
</header>

<main class="shop-container">

  <h1 class="shop-title">Dough LEYcious Cookies</h1>

  <div class="product-grid">

    <div class="product-card">
      <img src="images/choco chip.jpg">
      <h3>Classic Choc Chip</h3>
      <p class="price">₱119.00</p>
<!-- add or minus button lang ginagawa nito -->
      <div class="quantity">
  <button class="minus">−</button>
  <input type="number" value="0" min="0">
  <button class="plus">+</button>

</div>
      <button>Add to Cart</button>

    </div>

    <div class="product-card">
      <img src="images/choco chip.jpg">
      <h3>Oatmeal Choco Chip</h3>
      <p class="price">₱139.00</p>

     <div class="quantity">
  <button class="minus">−</button>
  <input type="number" value="0" min="0">
  <button class="plus">+</button>

</div>
      <button>Add to Cart</button>
    </div>

    <div class="product-card">
      <img src="images/smores.jpg">
      <h3>Smores Choco Chip</h3>
      <p class="price">₱149.00</p>

     <div class="quantity">
  <button class="minus">−</button>
  <input type="number" value="0" min="0">
  <button class="plus">+</button>

</div>

      <button>Add to Cart</button>
    </div>

    <div class="product-card">
      <img src="images/oreo.jpg">
      <h3>Oreo Crumbl</h3>
      <p class="price">₱159.00</p>

      <div class="quantity">
  <button class="minus">−</button>
  <input type="number" value="0" min="0">
  <button class="plus">+</button>
</div>

      <button>Add to Cart</button>
    </div>

    <div class="product-card">
      <img src="peanut.jpg">
      <h3>Biscoff</h3>
      <p class="price">₱169.00</p>
      <input type="number" min="0">
      <button>Add to Cart</button>
    </div>

  </div>

</main>
<script>
let cartCount = 0;

const counter = document.getElementById("cart-count");

// java na to para sa plus, minus, at add to cart button
document.querySelectorAll(".product-card").forEach(card => {
  const input = card.querySelector("input");
  const plus = card.querySelector(".plus");
  const minus = card.querySelector(".minus");
  const button = card.querySelector("button:last-of-type");

  // dito yung plus button
  plus.addEventListener("click", () => {
    input.value = parseInt(input.value) + 1;
  });

  // dito yung minus button
  minus.addEventListener("click", () => {
    if (input.value > 0) {
      input.value = parseInt(input.value) - 1;
    }
  });

  // dito yung add to cart button
  button.addEventListener("click", () => {
    let qty = parseInt(input.value);

    if (qty > 0) {
      cartCount += qty;
      counter.textContent = cartCount;
      input.value = 0; // reset after adding
    } else {
      alert("Please select quantity first!");
    }
  });
});
</script>

<script>
function selectOrder(type) {
  alert("You selected: " + type);

  // scroll to products
  document.querySelector(".shop-container").scrollIntoView({
    behavior: "smooth"
  });
}
</script>

<footer class="footer">

  <div class="footer-content">

    <div class="footer-section">
      <h1>Find Us</h1>
      <div class="socials">
  <a href="#"><i class="fab fa-facebook"></i></a>
  <a href="#"><i class="fab fa-instagram"></i></a>
</div>
    </div>

    <div class="footer-section">
      <h1>About Us</h1>
      <button onclick="location.href='#'">About Us</button>
    </div>

  </div>

</footer>

</body>
</html>
