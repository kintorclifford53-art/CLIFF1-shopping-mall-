{
    name: "iPhone 17",
    category: "Phones",
    image: "images/iphone-17.jpg",
    oldPrice: 10000,
    price: 8000
},
{
    name: "iPhone 16",
    category: "Phones",
    image: "images/iphone-16.jpg",
    oldPrice: 9000,
    price: 7200
},
{
    name: "iPhone 15",
    category: "Phones",
    image: "images/iphone-15.jpg",
    oldPrice: 8000,
    price: 6400
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>CLIFF 1 Shopping Mall</title>

<style>
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
  font-family:Arial,sans-serif;
}

body{
  background:#f3f4f6;
  color:#222;
}

header{
  background:#111827;
  color:white;
  text-align:center;
  padding:25px 12px;
}

header h1{
  font-size:32px;
}

header p{
  margin-top:8px;
  color:#d1d5db;
}

nav{
  background:#f97316;
  padding:12px;
  display:flex;
  justify-content:center;
  flex-wrap:wrap;
  gap:8px;
  position:sticky;
  top:0;
  z-index:10;
}

nav button{
  border:0;
  background:white;
  padding:10px 14px;
  border-radius:20px;
  font-weight:bold;
  cursor:pointer;
}

nav button:hover{
  background:#111827;
  color:white;
}

.hero{
  background:white;
  text-align:center;
  padding:42px 15px;
}

.hero h2{
  font-size:30px;
  margin-bottom:10px;
}

.hero p{
  color:#666;
}

.search{
  text-align:center;
  padding:20px;
}

.search input{
  width:92%;
  max-width:650px;
  padding:15px;
  border:1px solid #ccc;
  border-radius:25px;
  font-size:16px;
}

.section-title{
  max-width:1200px;
  margin:20px auto 0;
  padding:0 20px;
}

.section-title h2{
  margin-bottom:5px;
}

.products{
  max-width:1200px;
  margin:auto;
  padding:20px;
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(210px,1fr));
  gap:20px;
}

.product{
  background:white;
  border-radius:12px;
  overflow:hidden;
  box-shadow:0 3px 12px rgba(0,0,0,.12);
  transition:.2s;
}

.product:hover{
  transform:translateY(-4px);
}

.product-image{
  height:210px;
  background:#e5e7eb;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:75px;
}

.product-info{
  padding:15px;
}

.product-info h3{
  margin-bottom:7px;
}

.category{
  color:#777;
  font-size:13px;
}

.old-price{
  color:#999;
  text-decoration:line-through;
  margin-top:8px;
}

.price{
  color:#f97316;
  font-size:19px;
  font-weight:bold;
  margin:8px 0 12px;
}

.discount{
  display:inline-block;
  background:#16a34a;
  color:white;
  padding:4px 7px;
  border-radius:5px;
  font-size:12px;
  margin-bottom:10px;
}

.cart-btn{
  width:100%;
  padding:11px;
  background:#f97316;
  color:white;
  border:0;
  border-radius:7px;
  font-weight:bold;
  cursor:pointer;
}

.cart-btn:hover{
  background:#ea580c;
}

.cart{
  max-width:1200px;
  margin:25px auto;
  padding:20px;
  background:white;
  border-radius:12px;
}

.cart h2{
  margin-bottom:15px;
}

.cart-item{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
  padding:10px 0;
  border-bottom:1px solid #ddd;
}

.cart-controls button{
  padding:5px 9px;
  border:0;
  border-radius:5px;
  cursor:pointer;
}

.remove{
  background:#dc2626;
  color:white;
}

.cart-total{
  font-size:21px;
  font-weight:bold;
  margin-top:18px;
}

.clear-btn{
  margin-top:15px;
  padding:10px 15px;
  border:0;
  border-radius:7px;
  background:#dc2626;
  color:white;
  cursor:pointer;
}

footer{
  background:#111827;
  color:white;
  text-align:center;
  padding:30px 15px;
  margin-top:30px;
}

footer p{
  margin-top:8px;
  color:#d1d5db;
}

@media(max-width:500px){
  header h1{
    font-size:25px;
  }

  .products{
    grid-template-columns:repeat(2,1fr);
    gap:10px;
    padding:10px;
  }

  .product-image{
    height:160px;
    font-size:55px;
  }

  .product-info{
    padding:10px;
  }

  .product-info h3{
    font-size:15px;
  }

  .price{
    font-size:16px;
  }
}
</style>
</head>

<body>

<header>
  <h1>🛍️ CLIFF 1 SHOPPING MALL</h1>
  <p>Phones • Clothes • Electrical Gadgets • Shoes • Bags</p>
</header>

<nav>
  <button onclick="showCategory('all')">🏪 All</button>
  <button onclick="showCategory('phones')">📱 Phones</button>
  <button onclick="showCategory('clothes')">👕 Clothes</button>
  <button onclick="showCategory('gadgets')">🔌 Gadgets</button>
  <button onclick="showCategory('shoes')">👟 Shoes</button>
  <button onclick="showCategory('bags')">👜 Bags</button>
</nav>

<section class="hero">
  <h2>Welcome to CLIFF 1 Shopping Mall</h2>
  <p>Quality products at affordable prices.</p>
</section>

<div class="search">
  <input
    id="search"
    type="text"
    placeholder="🔎 Search for any product..."
    onkeyup="searchProducts()"
  >
</div>

<div class="section-title">
  <h2>🛍️ Our Products</h2>
  <p>60 products available</p>
</div>

<section class="products" id="products"></section>

<section class="cart">
  <h2>🛒 Shopping Cart</h2>

  <div id="cartItems">
    Your cart is empty.
  </div>

  <p class="cart-total">
    Total: GH₵ <span id="cartTotal">0</span>
  </p>

  <button class="clear-btn" onclick="clearCart()">
    Clear Cart
  </button>
</section>

<footer>
  <h3>CLIFF 1 Shopping Mall</h3>
  <p>Phones • Clothes • Electrical Gadgets • Shoes • Bags</p>
  <p>© 2026 CLIFF 1 Shopping Mall</p>
</footer>

<script>

/* =========================================
   CLIFF 1 - 60 PRODUCTS
   ========================================= */

const products = [

/* PHONES - 12 */

{
 name:"iPhone 17",
 category:"phones",
 icon:"📱",
 old:10000
},

{
 name:"iPhone 16",
 category:"phones",
 icon:"📱",
 old:9000
},

{
 name:"iPhone 15",
 category:"phones",
 icon:"📱",
 old:8000
},

{
 name:"iPhone 14",
 category:"phones",
 icon:"📱",
 old:7000
},

{
 name:"iPhone 13",
 category:"phones",
 icon:"📱",
 old:6000
},

{
 name:"iPhone 12",
 category:"phones",
 icon:"📱",
 old:5000
},

{
 name:"iPhone 11",
 category:"phones",
 icon:"📱",
 old:4000
},

{
 name:"Samsung Galaxy S26",
 category:"phones",
 icon:"📱",
 old:9000
},

{
 name:"Samsung Galaxy S25",
 category:"phones",
 icon:"📱",
 old:8000
},

{
 name:"Samsung Galaxy S24",
 category:"phones",
 icon:"📱",
 old:7000
},

{
 name:"Samsung Galaxy S10",
 category:"phones",
 icon:"📱",
 old:3000
},

{
 name:"Samsung Galaxy S9",
 category:"phones",
 icon:"📱",
 old:2500
},

/* CLOTHES - 12 */

{
 name:"Classic T-Shirt",
 category:"clothes",
 icon:"👕",
 old:150
},

{
 name:"Designer T-Shirt",
 category:"clothes",
 icon:"👕",
 old:220
},

{
 name:"Polo Shirt",
 category:"clothes",
 icon:"👕",
 old:250
},

{
 name:"Designer Jeans",
 category:"clothes",
 icon:"👖",
 old:300
},

{
 name:"Slim Jeans",
 category:"clothes",
 icon:"👖",
 old:280
},

{
 name:"Fashion Jacket",
 category:"clothes",
 icon:"🧥",
 old:450
},

{
 name:"Hoodie",
 category:"clothes",
 icon:"🧥",
 old:350
},

{
 name:"Sports Jersey",
 category:"clothes",
 icon:"👕",
 old:250
},

{
 name:"Shorts",
 category:"clothes",
 icon:"🩳",
 old:180
},

{
 name:"Track Pants",
 category:"clothes",
 icon:"👖",
 old:250
},

{
 name:"Sweater",
 category:"clothes",
 icon:"🧥",
 old:300
},

{
 name:"Formal Shirt",
 category:"clothes",
 icon:"👔",
 old:280
},

/* ELECTRICAL GADGETS - 12 */

{
 name:"Wireless Headphones",
 category:"gadgets",
 icon:"🎧",
 old:350
},

{
 name:"Bluetooth Earbuds",
 category:"gadgets",
 icon:"🎧",
 old:300
},

{
 name:"Smart Watch",
 category:"gadgets",
 icon:"⌚",
 old:500
},

{
 name:"Bluetooth Speaker",
 category:"gadgets",
 icon:"🔊",
 old:450
},

{
 name:"Power Bank",
 category:"gadgets",
 icon:"🔋",
 old:300
},

{
 name:"Fast Phone Charger",
 category:"gadgets",
 icon:"🔌",
 old:180
},

{
 name:"USB Cable",
 category:"gadgets",
 icon:"🔌",
 old:100
},

{
 name:"LED Desk Lamp",
 category:"gadgets",
 icon:"💡",
 old:250
},

{
 name:"Ring Light",
 category:"gadgets",
 icon:"💡",
 old:300
},

{
 name:"Electric Fan",
 category:"gadgets",
 icon:"🌀",
 old:650
},

{
 name:"Digital Alarm Clock",
 category:"gadgets",
 icon:"⏰",
 old:180
},

{
 name:"Mini Projector",
 category:"gadgets",
 icon:"📽️",
 old:900
},

/* SHOES - 12 */

{
 name:"Running Sneakers",
 category:"shoes",
 icon:"👟",
 old:400
},

{
 name:"Classic Sneakers",
 category:"shoes",
 icon:"👟",
 old:450
},

{
 name:"Sports Shoes",
 category:"shoes",
 icon:"👟",
 old:500
},

{
 name:"Casual Shoes",
 category:"shoes",
 icon:"👞",
 old:350
},

{
 name:"Formal Shoes",
 category:"shoes",
 icon:"👞",
 old:500
},

{
 name:"Outdoor Boots",
 category:"shoes",
 icon:"🥾",
 old:600
},

{
 name:"Leather Boots",
 category:"shoes",
 icon:"🥾",
 old:650
},

{
 name:"School Shoes",
 category:"shoes",
 icon:"👞",
 old:300
},

{
 name:"Football Boots",
 category:"shoes",
 icon:"👟",
 old:450
},

{
 name:"Canvas Shoes",
 category:"shoes",
 icon:"👟",
 old:280
},

{
 name:"Slip-On Shoes",
 category:"shoes",
 icon:"👞",
 old:320
},

{
 name:"Fashion Sandals",
 category:"shoes",
 icon:"🩴",
 old:250
},

/* BAGS - 12 */

{
 name:"School Backpack",
 category:"bags",
 icon:"🎒",
 old:250
},

{
 name:"Travel Backpack",
 category:"bags",
 icon:"🎒",
 old:400
},

{
 name:"Fashion Handbag",
 category:"bags",
 icon:"👜",
 old:300
},

{
 name:"Leather Handbag",
 category:"bags",
 icon:"👜",
 old:500
},

{
 name:"Business Bag",
 category:"bags",
 icon:"💼",
 old:400
},

{
 name:"Laptop Bag",
 category:"bags",
 icon:"💼",
 old:450
},

{
 name:"Travel Bag",
 category:"bags",
 icon:"🧳",
 old:500
},

{
 name:"Sports Bag",
 category:"bags",
 icon:"🎒",
 old:350
},

{
 name:"Crossbody Bag",
 category:"bags",
 icon:"👜",
 old:280
},

{
 name:"Shoulder Bag",
 category:"bags",
 icon:"👜",
 old:320
},

{
 name:"Mini Backpack",
 category:"bags",
 icon:"🎒",
 old:250
},

{
 name:"Shopping Bag",
 category:"bags",
 icon:"🛍️",
 old:180
}

];


/* =========================================
   20% DISCOUNT
   ========================================= */

products.forEach(function(product){

  product.price =
    Math.round(product.old * 0.80);

});


/* =========================================
   DISPLAY PRODUCTS
   ========================================= */

const productContainer =
document.getElementById("products");


function displayProducts(list){

  productContainer.innerHTML="";

  list.forEach(function(product,index){

    const card =
    document.createElement("div");

    card.className="product";

    card.dataset.category =
    product.category;

    card.innerHTML=`

      <div class="product-image">
        ${product.icon}
      </div>

      <div class="product-info">

        <h3>${product.name}</h3>

        <p class="category">
          ${getCategoryName(product.category)}
        </p>

        <span class="discount">
          20% OFF
        </span>

        <p class="old-price">
          GH₵ ${product.old.toLocaleString()}
        </p>

        <p class="price">
          GH₵ ${product.price.toLocaleString()}
        </p>

        <button
          class="cart-btn"
          onclick="addToCart(${index})">

          🛒 Add to Cart

        </button>

      </div>
    `;

    productContainer.appendChild(card);

  });

}


function getCategoryName(category){

  if(category==="phones")
    return "📱 Phones";

  if(category==="clothes")
    return "👕 Clothes";

  if(category==="gadgets")
    return "🔌 Electrical Gadgets";

  if(category==="shoes")
    return "👟 Shoes";

  if(category==="bags")
    return "👜 Bags";

  return "All Products";
}


/* =========================================
   CATEGORY FILTER
   ========================================= */

function showCategory(category){

  if(category==="all"){

    displayProducts(products);

    return;
  }

  const filtered =
  products.filter(function(product){

    return product.category === category;

  });

  displayProducts(filtered);

}


/* =========================================
   SEARCH
   ========================================= */

function searchProducts(){

  const search =
  document.getElementById("search")
  .value
  .toLowerCase()
  .trim();

  if(search===""){

    displayProducts(products);

    return;
  }

  const results =
  products.filter(function(product){

    return (
      product.name
      .toLowerCase()
      .includes(search)
    );

  });

  displayProducts(results);

}


/* =========================================
   SHOPPING CART
   ========================================= */

let cart=[];


function addToCart(index){

  const product =
  products[index];

  const existing =
  cart.find(function(item){

    return item.name === product.name;

  });


  if(existing){

    existing.quantity++;

  }else{

    cart.push({

      name:product.name,

      price:product.price,

      quantity:1

    });

  }

  displayCart();

}


function increaseQuantity(index){

  cart[index].quantity++;

  displayCart();

}


function decreaseQuantity(index){

  if(cart[index].quantity>1){

    cart[index].quantity--;

  }else{

    cart.splice(index,1);

  }

  displayCart();

}


function removeItem(index){

  cart.splice(index,1);

  displayCart();

}


function clearCart(){

  cart=[];

  displayCart();

}


function displayCart(){

  const cartItems =
  document.getElementById("cartItems");

  const cartTotal =
  document.getElementById("cartTotal");


  if(cart.length===0){

    cartItems.innerHTML =
    "Your cart is empty.";

    cartTotal.textContent="0";

    return;

  }


  let total=0;

  cartItems.innerHTML="";


  cart.forEach(function(item,index){

    total +=
    item.price * item.quantity;


    const div =
    document.createElement("div");

    div.className="cart-item";


    div.innerHTML=`

      <div>

        <strong>
          ${item.name}
        </strong>

        <br>

        GH₵ ${item.price.toLocaleString()}
        × ${item.quantity}

      </div>


      <div class="cart-controls">

        <button
          onclick="decreaseQuantity(${index})">

          −

        </button>


        <button
          onclick="increaseQuantity(${index})">

          +

        </button>


        <button
          class="remove"
          onclick="removeItem(${index})">

          Remove

        </button>

      </div>

    `;


    cartItems.appendChild(div);

  });


  cartTotal.textContent =
  total.toLocaleString();

}


/* =========================================
   START WEBSITE
   ========================================= */

displayProducts(products);

displayCart();<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CLIFF 1 Shopping Mall</title>

<style>
*{box-sizing:border-box;margin:0;padding:0;font-family:Arial,sans-serif}

body{background:#f4f4f4;color:#222}

header{
background:#111827;
color:white;
text-align:center;
padding:25px 12px
}

header h1{font-size:30px}
header p{margin-top:8px;color:#ddd}

nav{
background:#f97316;
padding:12px;
display:flex;
justify-content:center;
flex-wrap:wrap;
gap:8px
}

nav button{
border:0;
background:white;
padding:10px 14px;
border-radius:20px;
font-weight:bold;
cursor:pointer
}

nav button:hover{
background:#111827;
color:white
}

.hero{
background:white;
text-align:center;
padding:40px 15px
}

.hero h2{
font-size:28px;
margin-bottom:10px
}

.hero p{color:#666}

.search{
text-align:center;
padding:20px
}

.search input{
width:90%;
max-width:600px;
padding:14px;
border:1px solid #ccc;
border-radius:25px;
font-size:16px
}

.products{
max-width:1200px;
margin:auto;
padding:20px;
display:grid;
grid-template-columns:repeat(auto-fit,minmax(210px,1fr));
gap:20px
}

.product{
background:white;
border-radius:12px;
overflow:hidden;
box-shadow:0 3px 12px rgba(0,0,0,.12)
}

.product-image{
height:210px;
background:#e5e7eb;
display:flex;
align-items:center;
justify-content:center;
font-size:70px
}

.product-info{padding:15px}

.product-info h3{margin-bottom:7px}

.category{
font-size:13px;
color:#777
}

.old-price{
color:#999;
text-decoration:line-through;
margin-top:8px
}

.price{
color:#f97316;
font-size:19px;
font-weight:bold;
margin:8px 0 12px
}

.cart-btn{
width:100%;
padding:11px;
border:0;
border-radius:7px;
background:#f97316;
color:white;
font-weight:bold;
cursor:pointer
}

.cart-btn:hover{background:#ea580c}

.cart{
max-width:1200px;
margin:25px auto;
padding:20px;
background:white;
border-radius:12px
}

.cart h2{margin-bottom:15px}

.cart-item{
padding:9px 0;
border-bottom:1px solid #ddd
}

.cart-total{
font-size:20px;
font-weight:bold;
margin-top:15px
}

.clear-btn{
margin-top:15px;
padding:10px 15px;
border:0;
border-radius:7px;
background:#dc2626;
color:white;
cursor:pointer
}

footer{
background:#111827;
color:white;
text-align:center;
padding:30px 15px;
margin-top:30px
}

footer p{
margin-top:8px;
color:#ddd
}
</style>
</head>

<body>

<header>
<h1>🛍️ CLIFF 1 SHOPPING MALL</h1>
<p>Phones • Clothes • Electrical Gadgets • Shoes • Bags</p>
</header>

<nav>
<button onclick="showCategory('all')">🏪 All</button>
<button onclick="showCategory('phones')">📱 Phones</button>
<button onclick="showCategory('clothes')">👕 Clothes</button>
<button onclick="showCategory('gadgets')">🔌 Gadgets</button>
<button onclick="showCategory('shoes')">👟 Shoes</button>
<button onclick="showCategory('bags')">👜 Bags</button>
</nav>

<section class="hero">
<h2>Welcome to CLIFF 1 Shopping Mall</h2>
<p>Shop quality products at affordable prices.</p>
</section>

<div class="search">
<input
id="search"
type="text"
placeholder="🔎 Search products..."
onkeyup="searchProducts()">
</div>

<section class="products" id="products">

<!-- PHONES -->

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>iPhone 17</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 10,000</p>
<p class="price">GH₵ 8,000</p>
<button class="cart-btn" onclick="addToCart('iPhone 17',8000)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>iPhone 15</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 8,000</p>
<p class="price">GH₵ 6,400</p>
<button class="cart-btn" onclick="addToCart('iPhone 15',6400)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>iPhone 13</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 6,000</p>
<p class="price">GH₵ 4,800</p>
<button class="cart-btn" onclick="addToCart('iPhone 13',4800)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>iPhone 12</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 5,000</p>
<p class="price">GH₵ 4,000</p>
<button class="cart-btn" onclick="addToCart('iPhone 12',4000)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>iPhone 11</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 4,000</p>
<p class="price">GH₵ 3,200</p>
<button class="cart-btn" onclick="addToCart('iPhone 11',3200)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>Samsung Galaxy S26</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 9,000</p>
<p class="price">GH₵ 7,200</p>
<button class="cart-btn" onclick="addToCart('Samsung Galaxy S26',7200)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>Samsung Galaxy S24</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 7,000</p>
<p class="price">GH₵ 5,600</p>
<button class="cart-btn" onclick="addToCart('Samsung Galaxy S24',5600)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>Tecno Spark</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 2,000</p>
<p class="price">GH₵ 1,600</p>
<button class="cart-btn" onclick="addToCart('Tecno Spark',1600)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="phones">
<div class="product-image">📱</div>
<div class="product-info">
<h3>Infinix Hot</h3>
<p class="category">Phones</p>
<p class="old-price">GH₵ 1,800</p>
<p class="price">GH₵ 1,440</p>
<button class="cart-btn" onclick="addToCart('Infinix Hot',1440)">Add to Cart</button>
</div>
</div>

<!-- CLOTHES -->

<div class="product" data-category="clothes">
<div class="product-image">👕</div>
<div class="product-info">
<h3>Classic T-Shirt</h3>
<p class="category">Clothes</p>
<p class="old-price">GH₵ 150</p>
<p class="price">GH₵ 120</p>
<button class="cart-btn" onclick="addToCart('Classic T-Shirt',120)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="clothes">
<div class="product-image">👖</div>
<div class="product-info">
<h3>Designer Jeans</h3>
<p class="category">Clothes</p>
<p class="old-price">GH₵ 300</p>
<p class="price">GH₵ 240</p>
<button class="cart-btn" onclick="addToCart('Designer Jeans',240)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="clothes">
<div class="product-image">🧥</div>
<div class="product-info">
<h3>Fashion Jacket</h3>
<p class="category">Clothes</p>
<p class="old-price">GH₵ 450</p>
<p class="price">GH₵ 360</p>
<button class="cart-btn" onclick="addToCart('Fashion Jacket',360)">Add to Cart</button>
</div>
</div>

<!-- GADGETS -->

<div class="product" data-category="gadgets">
<div class="product-image">🎧</div>
<div class="product-info">
<h3>Wireless Headphones</h3>
<p class="category">Electrical Gadgets</p>
<p class="old-price">GH₵ 350</p>
<p class="price">GH₵ 280</p>
<button class="cart-btn" onclick="addToCart('Wireless Headphones',280)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="gadgets">
<div class="product-image">⌚</div>
<div class="product-info">
<h3>Smart Watch</h3>
<p class="category">Electrical Gadgets</p>
<p class="old-price">GH₵ 500</p>
<p class="price">GH₵ 400</p>
<button class="cart-btn" onclick="addToCart('Smart Watch',400)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="gadgets">
<div class="product-image">🔊</div>
<div class="product-info">
<h3>Bluetooth Speaker</h3>
<p class="category">Electrical Gadgets</p>
<p class="old-price">GH₵ 450</p>
<p class="price">GH₵ 360</p>
<button class="cart-btn" onclick="addToCart('Bluetooth Speaker',360)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="gadgets">
<div class="product-image">🔋</div>
<div class="product-info">
<h3>Power Bank</h3>
<p class="category">Electrical Gadgets</p>
<p class="old-price">GH₵ 300</p>
<p class="price">GH₵ 240</p>
<button class="cart-btn" onclick="addToCart('Power Bank',240)">Add to Cart</button>
</div>
</div>

<!-- SHOES -->

<div class="product" data-category="shoes">
<div class="product-image">👟</div>
<div class="product-info">
<h3>Running Sneakers</h3>
<p class="category">Shoes</p>
<p class="old-price">GH₵ 400</p>
<p class="price">GH₵ 320</p>
<button class="cart-btn" onclick="addToCart('Running Sneakers',320)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="shoes">
<div class="product-image">👞</div>
<div class="product-info">
<h3>Classic Shoes</h3>
<p class="category">Shoes</p>
<p class="old-price">GH₵ 350</p>
<p class="price">GH₵ 280</p>
<button class="cart-btn" onclick="addToCart('Classic Shoes',280)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="shoes">
<div class="product-image">🥾</div>
<div class="product-info">
<h3>Outdoor Boots</h3>
<p class="category">Shoes</p>
<p class="old-price">GH₵ 500</p>
<p class="price">GH₵ 400</p>
<button class="cart-btn" onclick="addToCart('Outdoor Boots',400)">Add to Cart</button>
</div>
</div>

<!-- BAGS -->

<div class="product" data-category="bags">
<div class="product-image">🎒</div>
<div class="product-info">
<h3>School Backpack</h3>
<p class="category">Bags</p>
<p class="old-price">GH₵ 250</p>
<p class="price">GH₵ 200</p>
<button class="cart-btn" onclick="addToCart('School Backpack',200)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="bags">
<div class="product-image">👜</div>
<div class="product-info">
<h3>Fashion Handbag</h3>
<p class="category">Bags</p>
<p class="old-price">GH₵ 300</p>
<p class="price">GH₵ 240</p>
<button class="cart-btn" onclick="addToCart('Fashion Handbag',240)">Add to Cart</button>
</div>
</div>

<div class="product" data-category="bags">
<div class="product-image">💼</div>
<div class="product-info">
<h3>Business Bag</h3>
<p class="category">Bags</p>
<p class="old-price">GH₵ 400</p>
<p class="price">GH₵ 320</p>
<button class="cart-btn" onclick="addToCart('Business Bag',320)">Add to Cart</button>
</div>
</div>

</section>

<!-- CART -->

<section class="cart">

<h2>🛒 Shopping Cart</h2>

<div id="cartItems">
Your cart is empty.
</div>

<p class="cart-total">
Total: GH₵ <span id="cartTotal">0</span>
</p>

<button class="clear-btn" onclick="clearCart()">
Clear Cart
</button>

</section>

<footer>

<h3>CLIFF 1 Shopping Mall</h3>

<p>
Phones • Clothes • Electrical Gadgets • Shoes • Bags
</p>

<p>
© 2026 CLIFF 1 Shopping Mall
</p>

</footer>

<script>

let cart=[];
let total=0;

function addToCart(name,price){

cart.push({
name:name,
price:price
});

total+=price;

displayCart();

}

function displayCart(){

let cartItems=document.getElementById("cartItems");
let cartTotal=document.getElementById("cartTotal");

if(cart.length===0){

cartItems.innerHTML="Your cart is empty.";

}else{

cartItems.innerHTML="";

cart.forEach(function(item,index){

let div=document.createElement("div");

div.className="cart-item";

div.innerHTML=
(index+1)+". "+
item.name+
" - GH₵ "+
item.price.toLocaleString();

cartItems.appendChild(div);

});

}

cartTotal.textContent=total.toLocaleString();

}

function clearCart(){

cart=[];
total=0;

displayCart();

}

function showCategory(category){

let products=document.querySelectorAll(".product");

products.forEach(function(product){

if(
category==="all" ||
product.dataset.category===category
){

product.style.display="";

}else{

product.style.display="none";

}

});

}

function searchProducts(){

let search=document
.getElementById("search")
.value
.toLowerCase();

let products=document.querySelectorAll(".product");

products.forEach(function(product){

let name=product
.querySelector("h3")
.textContent
.toLowerCase();

if(name.includes(search)){

product.style.display="";

}else{

product.style.display="none";

}

});

}

</script>

</body>
</html>

</script>

</body>
</html>}# CLIFF1-shopping-mall-
