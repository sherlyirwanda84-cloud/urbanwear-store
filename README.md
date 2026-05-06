<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UrbanWear Store</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI';
}

body {
  background: #0f172a;
  color: white;
}

/* NAVBAR */
nav {
  display: flex;
  justify-content: space-between;
  padding: 20px;
  background: rgba(0,0,0,0.5);
}

nav h1 {
  color: #38bdf8;
}

nav span {
  cursor: pointer;
}

/* HERO */
.hero {
  text-align: center;
  padding: 60px 20px;
}

.hero h2 {
  font-size: 40px;
}

.hero p {
  color: #94a3b8;
}

/* PRODUK */
.products {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  padding: 20px;
}

.card {
  background: #1e293b;
  padding: 20px;
  border-radius: 15px;
  width: 200px;
  text-align: center;
  transition: 0.3s;
}

.card:hover {
  transform: scale(1.05);
  background: #334155;
}

.card h3 {
  margin: 10px 0;
}

button {
  background: #38bdf8;
  border: none;
  padding: 8px;
  border-radius: 8px;
  cursor: pointer;
}

/* CART */
.cart {
  position: fixed;
  right: 0;
  top: 0;
  width: 250px;
  height: 100%;
  background: #020617;
  padding: 20px;
}

</style>
</head>

<body>

<!-- NAVBAR -->
<nav>
  <h1>UrbanWear</h1>
  <span onclick="toggleCart()">🛒 Cart</span>
</nav>

<!-- HERO -->
<div class="hero">
  <h2>Upgrade Your Style 🔥</h2>
  <p>Fashion kekinian, tampil lebih percaya diri</p>
</div>

<!-- PRODUK -->
<div class="products">

<div class="card">
  <h3>Kaos Hitam</h3>
  <p>Rp 80.000</p>
  <button onclick="addCart('Kaos Hitam',80000)">Beli</button>
</div>

<div class="card">
  <h3>Hoodie Street</h3>
  <p>Rp 150.000</p>
  <button onclick="addCart('Hoodie Street',150000)">Beli</button>
</div>

<div class="card">
  <h3>Jaket Denim</h3>
  <p>Rp 200.000</p>
  <button onclick="addCart('Jaket Denim',200000)">Beli</button>
</div>

</div>

<!-- CART -->
<div class="cart" id="cart" style="display:none;">
  <h2>Keranjang</h2>
  <ul id="list"></ul>
  <p>Total: Rp <span id="total">0</span></p>
</div>

<script>
let total = 0;

function addCart(nama, harga) {
  let li = document.createElement("li");
  li.innerText = nama;
  document.getElementById("list").appendChild(li);

  total += harga;
  document.getElementById("total").innerText = total;
}

function toggleCart() {
  let cart = document.getElementById("cart");
  cart.style.display = cart.style.display === "none" ? "block" : "none";
}
</script>

</body>
</html>
