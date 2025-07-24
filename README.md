# product-card-template
ProductCard 
index.html
git add index.html styles.css script.jsstyles.css body {
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
script.js
document.addEventListener('DOMContentLoaded', () => {
  const inStock = false;  // change based on your data
  const btn = document.querySelector('.add-btn');
  if (!inStock) {
    btn.disabled = true;
    btn.textContent = 'Out of Stock';
  }
});
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>Product Card Template</title>
  <link rel="stylesheet" href="styles.css"/>
</head>
<body>
  <div class="product-card">
    <img src="https://via.placeholder.com/300" alt="Product Name"/>
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
ProductCard.jsx 
function ProductCard({ product }) {
  const { image, name, price, options, inStock } = product;
  return (
    <div className="product-card">
      <img src={image} alt={name}/>
      <h3 className="name">{name}</h3>
      <p className="price">${price}</p>
      {options && (
        <select className="variant">
          {options.map(o => <option key={o}>{o}</option>)}
        </select>
      )}
      <button className="add-btn" disabled={!inStock}>
        {inStock ? 'Add to Cart' : 'Out of Stock'}
      </button>
    </div>
  );
}
export default ProductCard;
"homepage": "https://your-username.github.io/repo-name",
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
}

