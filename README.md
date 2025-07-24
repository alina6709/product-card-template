
product-card-template/
├── index.html
├── styles.css
└── script.js
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Product Card Template</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="product-card">
    <img src="https://via.placeholder.com/300" alt="Product Name" />
    <h3 class="name">Product Name</h3>
    <p class="price">$99.99</p>
    <select class="variant">
      <option>Variant 1</option>
      <option>Variant 2</option>
    </select>
    <button class="add-btn">Add to Cart</button>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  font-family: sans-serif;
  padding: 2rem;
}

.product-card {
  max-width: 320px;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1rem;
  display: grid;
  grid-template-rows: auto 1fr auto auto;
  gap: 0.5rem;
}

.product-card img {
  width: 100%;
  border-radius: 4px;
}

.add-btn {
  padding: 0.75rem;
  background: #007bff;
  border: none;
  color: white;
  font-size: 1rem;
  border-radius: 4px;
  cursor: pointer;
}

.add-btn:disabled {
  background: #ccc;
  cursor: not-allowed;
}

@media (min-width: 640px) {
  .product-card {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto auto;
    align-items: start;
  }
  .product-card img {
    grid-row: span 2;
    margin-right: 1rem;
  }
}
document.addEventListener('DOMContentLoaded', () => {
  const inStock = false; // Change based on your actual data
  const btn = document.querySelector('.add-btn');
  if (!inStock) {
    btn.disabled = true;
    btn.textContent = 'Out of Stock';
  }
});
git init
git add index.html styles.css script.js
git commit -m "Add responsive Product Card template"
git remote add origin (https://github.com/alina6709)
git push -u origin main
npm install gh-pages --save-dev
"homepage": (https://github.com/alina6709),
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build",
  ...
}
