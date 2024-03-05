<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anso FG Trading App</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Anso FG Trading App</h1>
    </header>
    <main>
        <section id="stocks">
            <h2>Available Stocks</h2>
            <ul id="stock-list"></ul>
        </section>
        <section id="transactions">
            <h2>Transactions</h2>
            <ul id="transaction-list"></ul>
        </section>
    </main>
    <script src="app.js"></script>
</body>
</html>
CSS Styling: Create a CSS file (styles.css) to style the app.
css
Copy code
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: #fff;
    padding: 1rem;
    text-align: center;
}

main {
    display: flex;
    justify-content: space-around;
    padding: 2rem 0;
}

section {
    flex: 1;
    margin: 0 1rem;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    margin-bottom: 1rem;
}

button {
    padding: 0.5rem 1rem;
    background-color: #007bff;
    color: #fff;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
JavaScript Functionality: Create a JavaScript file (app.js) to add interactivity to the app.
javascript
Copy code
// Sample stock data
const stocks = [
    { symbol: 'AAPL', name: 'Apple Inc.', price: 150.50 },
    { symbol: 'GOOGL', name: 'Alphabet Inc.', price: 2800.00 },
    { symbol: 'MSFT', name: 'Microsoft Corporation', price: 300.25 }
];

// Display stocks on the page
const stockList = document.getElementById('stock-list');
stocks.forEach(stock => {
    const li = document.createElement('li');
    li.innerHTML = `${stock.symbol} - ${stock.name} - $${stock.price}`;
    const buyButton = document.createElement('button');
    buyButton.textContent = 'Buy';
    buyButton.addEventListener('click', () => buyStock(stock.symbol, stock.price));
    li.appendChild(buyButton);
    stockList.appendChild(li);
});

// Buy stock function
const transactionList = document.getElementById('transaction-list');
function buyStock(symbol, price) {
    const li = document.createElement('li');
    li.textContent = `Bought ${symbol} at $${price}`;
    transactionList.appendChild(li);
}
