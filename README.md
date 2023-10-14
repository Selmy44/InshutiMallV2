# InshutiMallV2
This is a sale platform
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My E-Commerce Store</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }

        header {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 10px;
        }

        .product-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }

        .product-card {
            background-color: #fff;
            margin: 10px;
            padding: 20px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
            border-radius: 5px;
            width: 300px;
        }

        .product-card img {
            max-width: 100%;
            height: auto;
        }

        .product-title {
            font-size: 1.2rem;
            margin: 10px 0;
        }

        .product-price {
            font-size: 1.5rem;
            color: #007bff;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to My E-Commerce Store</h1>
    </header>

    <div class="product-container">
        <div class="product-card">
            <img src="product1.jpg" alt="Product 1">
            <div class="product-title">Product 1</div>
            <div class="product-price">$19.99</div>
            <button onclick="addToCart(1)">Add to Cart</button>
        </div>

        <div class="product-card">
            <img src="product2.jpg" alt="Product 2">
            <div class="product-title">Product 2</div>
            <div class="product-price">$29.99</div>
            <button onclick="addToCart(2)">Add to Cart</button>
        </div>

        <!-- Add more product cards here -->
    </div>

    <div id="cart">
        <h2>Shopping Cart</h2>
        <ul id="cart-items"></ul>
        <p>Total: $<span id="cart-total">0.00</span></p>
    </div>

    <script>
        const cartItems = [];
        const productData = [
            { id: 1, name: "Product 1", price: 19.99 },
            { id: 2, name: "Product 2", price: 29.99 },
            // Add more product data here
        ];

        function addToCart(productId) {
            const product = productData.find(item => item.id === productId);
            if (product) {
                cartItems.push(product);
                updateCart();
            }
        }

        function updateCart() {
            const cartItemsList = document.getElementById("cart-items");
            const cartTotal = document.getElementById("cart-total");

            cartItemsList.innerHTML = '';
            let total = 0;

            for (const item of cartItems) {
                const li = document.createElement("li");
                li.textContent = `${item.name} - $${item.price.toFixed(2)}`;
                cartItemsList.appendChild(li);
                total += item.price;
            }

            cartTotal.textContent = total.toFixed(2);
        }
    </script>
</body>
</html>
