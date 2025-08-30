<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>StyleSphere — Modern E-commerce</title>

  <!-- ✅ Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- ✅ Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css" />

  <!-- ✅ Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet" />

  <!-- ✅ Custom CSS -->
  <link rel="stylesheet" href="style.css" />
</head>
<body class="font-[Poppins] bg-gray-50">

  <!-- ✅ Navbar -->
  <header class="bg-white shadow sticky top-0 z-50">
    <nav class="container mx-auto flex items-center justify-between p-4">
      <h1 class="text-2xl font-bold text-pink-600">StyleSphere</h1>
      <ul class="hidden md:flex space-x-6">
        <li><a href="#home" class="hover:text-pink-600">Home</a></li>
        <li><a href="#featured" class="hover:text-pink-600">Featured</a></li>
        <li><a href="#categories" class="hover:text-pink-600">Categories</a></li>
        <li><a href="#reviews" class="hover:text-pink-600">Reviews</a></li>
      </ul>
      <button id="menu-btn" class="md:hidden text-2xl"><i class="fas fa-bars"></i></button>
    </nav>
    <div id="mobile-menu" class="hidden flex-col bg-white shadow md:hidden p-4">
      <a href="#home" class="py-2 block">Home</a>
      <a href="#featured" class="py-2 block">Featured</a>
      <a href="#categories" class="py-2 block">Categories</a>
      <a href="#reviews" class="py-2 block">Reviews</a>
    </div>
  </header>

  <!-- ✅ Hero Section -->
  <section id="home" class="bg-gradient-to-r from-pink-500 to-purple-500 text-white py-20 text-center">
    <h2 class="text-4xl md:text-5xl font-bold mb-4">Shop the Latest Fashion Trends</h2>
    <p class="mb-6">Trendy collections, exclusive offers, and more.</p>
    <a href="#featured" class="bg-white text-pink-600 px-6 py-3 rounded-full font-semibold hover:bg-gray-100 transition">Shop Now</a>
  </section>

  <!-- ✅ Featured Products -->
  <section id="featured" class="container mx-auto px-4 py-10">
    <h2 class="text-2xl md:text-3xl font-semibold text-center mb-8">Featured Products</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
      
      <!-- Card 1 -->
      <article class="bg-white rounded-xl shadow p-4 hover:shadow-2xl transition">
        <img src="images/product1.jpg" alt="Product 1" class="rounded-lg mb-4" />
        <h3 class="font-semibold text-lg">Red Dress</h3>
        <p class="text-gray-600">₹1499</p>
        <button class="add-to-cart bg-pink-600 text-white px-4 py-2 rounded mt-3 hover:bg-pink-700 transition">Add to Cart</button>
      </article>

      <!-- Card 2 -->
      <article class="bg-white rounded-xl shadow p-4 hover:shadow-2xl transition">
        <img src="images/product2.jpg" alt="Product 2" class="rounded-lg mb-4" />
        <h3 class="font-semibold text-lg">Denim Jacket</h3>
        <p class="text-gray-600">₹2299</p>
        <button class="add-to-cart bg-pink-600 text-white px-4 py-2 rounded mt-3 hover:bg-pink-700 transition">Add to Cart</button>
      </article>

      <!-- Card 3 -->
      <article class="bg-white rounded-xl shadow p-4 hover:shadow-2xl transition">
        <img src="images/product3.jpg" alt="Product 3" class="rounded-lg mb-4" />
        <h3 class="font-semibold text-lg">Sneakers</h3>
        <p class="text-gray-600">₹3299</p>
        <button class="add-to-cart bg-pink-600 text-white px-4 py-2 rounded mt-3 hover:bg-pink-700 transition">Add to Cart</button>
      </article>

      <!-- Card 4 -->
      <article class="bg-white rounded-xl shadow p-4 hover:shadow-2xl transition">
        <img src="images/product4.jpg" alt="Product 4" class="rounded-lg mb-4" />
        <h3 class="font-semibold text-lg">Summer Top</h3>
        <p class="text-gray-600">₹799</p>
        <button class="add-to-cart bg-pink-600 text-white px-4 py-2 rounded mt-3 hover:bg-pink-700 transition">Add to Cart</button>
      </article>
    </div>
  </section>

  <!-- ✅ Toast Notification -->
  <div id="toast" class="hidden fixed bottom-5 right-5 bg-green-600 text-white px-4 py-2 rounded shadow"></div>

  <!-- ✅ Footer -->
  <footer class="bg-gray-800 text-white py-6 text-center">
    <p>© 2025 StyleSphere. All rights reserved.</p>
  </footer>



  /* Extra custom CSS (on top of Tailwind) */

body {
  scroll-behavior: smooth;
}

#toast {
  animation: fadeInOut 3s ease-in-out;
}

@keyframes fadeInOut {
  0% { opacity: 0; transform: translateY(20px); }
  20% { opacity: 1; transform: translateY(0); }
  80% { opacity: 1; }
  100% { opacity: 0; transform: translateY(20px); }
}


  <!-- ✅ Custom JS -->
  <script src="script.js"></script>
</body>
</html>



/* Extra custom CSS (on top of Tailwind) */

body {
  scroll-behavior: smooth;
}

#toast {
  animation: fadeInOut 3s ease-in-out;
}

@keyframes fadeInOut {
  0% { opacity: 0; transform: translateY(20px); }
  20% { opacity: 1; transform: translateY(0); }
  80% { opacity: 1; }
  100% { opacity: 0; transform: translateY(20px); }
}





// ✅ Mobile Menu Toggle
const menuBtn = document.getElementById("menu-btn");
const mobileMenu = document.getElementById("mobile-menu");

menuBtn.addEventListener("click", () => {
  mobileMenu.classList.toggle("hidden");
});

// ✅ Toast Notification for Add to Cart
const buttons = document.querySelectorAll(".add-to-cart");
const toast = document.getElementById("toast");

buttons.forEach((btn) => {
  btn.addEventListener("click", () => {
    toast.textContent = "✅ Item added to cart!";
    toast.classList.remove("hidden");

    setTimeout(() => {
      toast.classList.add("hidden");
    }, 3000);
  });
});

