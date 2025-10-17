# Sales Summary Project

This project is a single-page site that fetches sales data from a CSV file, computes the total sales, and displays it on the page. It uses Bootstrap 5 for styling.

## Features

- Fetches `data.csv` to obtain sales data.
- Sums the sales based on the price and units sold.
- Displays the total sales in a formatted manner.
- Utilizes Bootstrap 5 for a responsive design.

## Usage

1. Ensure you have a `data.csv` file in the same directory as `index.html`. The CSV should have the following format:
   ```
   Item,Units Sold,Price
   Widget A,10,2.50
   Widget B,5,3.00
   ...
   ```

2. Open `index.html` in a web browser.

## Setup

You need to have a basic HTML file structure. Here’s the provided HTML code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sales Summary</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <div class="container mt-5">
        <h1>Sales Summary</h1>
        <div class="alert alert-info" id="total-sales">Total Sales: $0.00</div>
    </div>
    
    <script>
        fetch('data.csv')
            .then(response => response.text())
            .then(data => {
                const rows = data.split('\n').slice(1);
                let totalSales = 0;

                rows.forEach(row => {
                    const columns = row.split(',');
                    if (columns.length === 3) {
                        const price = parseFloat(columns[2]);
                        const units = parseInt(columns[1]);
                        totalSales += price * units;
                    }
                });

                document.getElementById('total-sales').textContent = 'Total Sales: $' + totalSales.toFixed(2);
            })
            .catch(error => console.error('Error fetching the CSV file:', error));
    </script>
    
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

## License

MIT License. See [LICENSE](LICENSE) for more information.