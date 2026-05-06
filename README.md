<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UrbanWear Store</title>

<style>
body {
  font-family: Arial;
  margin: 0;
  background: #f4f4f4;
}

header {
  background: #111;
  color: white;
  text-align: center;
  padding: 15px;
  font-size: 22px;
}

.container {
  max-width: 1000px;
  margin: auto;
  padding: 20px;
}

.products {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px,1fr));
  gap: 20px;
}

.card {
  background: white;
  padding: 15px;
  border-radius: 10px;
  text-align: center;
  box-shadow: 0 3px 8px rgba(0,0,0,0.1);
}

.card img {
  width: 100%;
  border-radius: 10px;
}

button {
  padding: 10px;
  border: none;
  background: black;
  color: white;
  border-radius: 8px;
  cursor: pointer;
}

button:hover {
  background: #444;
}

.cart {
  margin-top: 30px;
  background: white;
  padding: 20px;
  border-radius: 10px;
}

input {
  padding: 10px;
  width: 100%;
  margin-top: 10px;
  border-radius: 8px;
  border: 1px solid #ccc;
}
</style>
</head>

<body>

<header>🛍️ UrbanWear Store</header>

<div class="container">

<h2>Daftar Produk</h2>

<div class="products">

<div class="card">
<img src="https://via.placeholder.com/200">
<h3>Kaos Hitam</h3>
<p>Rp 80.000</p>
<button onclick="tambah('Kaos Hitam',80000)">Tambah</button>
</div>

<div class="card">
<img src="https://via.placeholder.com/200">
<h3>Hoodie Abu</h3>
<p>Rp 150.000</p>
<button onclick="tambah('Hoodie Abu',150000)">Tambah</button>
</div>

<div class="card">
<img src="https://via.placeholder.com/200">
<h3>Jaket Denim</h3>
<p>Rp 200.000</p>
<button onclick="tambah('Jaket Denim',200000)">Tambah</button>
</div>

</div>

<div class="cart">
<h2>Keranjang</h2>
<ul id="list"></ul>

<p><b>Total: Rp <span id="total">0</span></b></p>

<button onclick="hapus()">Hapus Semua</button>

<h3>Checkout</h3>
<input type="text" id="nama" placeholder="Nama Pembeli">
<button onclick="checkout()">Checkout</button>

</div>

</div>

<script>
let total = 0;

function tambah(nama, harga){
  let li = document.createElement("li");
  li.innerText = nama + " - Rp " + harga;
  document.getElementById("list").appendChild(li);

  total += harga;
  document.getElementById("total").innerText = total;
}

function hapus(){
  document.getElementById("list").innerHTML = "";
  total = 0;
  document.getElementById("total").innerText = total;
}

function checkout(){
  let nama = document.getElementById("nama").value;

  if(nama === ""){
    alert("Isi nama dulu!");
  } else if(total === 0){
    alert("Keranjang kosong!");
  } else {
    alert("Terima kasih " + nama + " sudah belanja!");
  }
}
</script>

</body>
</html>
