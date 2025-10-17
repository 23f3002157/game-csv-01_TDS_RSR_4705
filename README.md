# Sales Summary Project

This project presents a modern sales summary HTML page that incorporates a currency selection feature. Users can select their preferred currency to view the total sales amount in that currency, providing an enhanced user experience.

## Features

- **Currency Select Picker**: Allows users to select from multiple currencies (USD, EUR, GBP).
- **Modern Design**: Utilizes a clean and attractive design with gradient backgrounds and styled elements.
- **Responsive Design**: The page is mobile-friendly and adapts to various screen sizes.
- **Total Sales Calculation**: Automatically calculates total sales based on selected currency.

## Changes Made

The following changes were made to enhance the functionality and appearance of the HTML code:

1. **Currency Select Picker**: Added a `<select>` element for users to choose their desired currency.
   ```html
   <div class="mb-3">
       <label for="currencySelector" class="form-label">Select Currency:</label>
       <select class="form-select" id="currencySelector">
           <option value="USD">USD</option>
           <option value="EUR">EUR</option>
           <option value="GBP">GBP</option>
       </select>
   </div>
   ```

2. **Modern Styling**: Introduced CSS styling to provide a gradient background and improved container aesthetics.
   ```css
   body {
       background: linear-gradient(to right, #00c6ff, #0072ff);
       color: #fff;
   }
   .container {
       background: rgba(255, 255, 255, 0.1);
       border-radius: 10px;
       padding: 20px;
       margin-top: 50px;
       box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
   }
   ```

3. **Dynamic Currency Conversion**: Implemented JavaScript logic to convert total sales values based on the selected currency.
   ```javascript
   function updateTotalSales(currency) {
       // Conversion logic here
   }
   ```

4. **Event Handling**: Added an event listener to update the displayed sales total when the currency selection changes.
   ```javascript
   document.getElementById('currencySelector').addEventListener('change', function() {
       updateTotalSales(this.value);
   });
   ```

## Installation

To run this project locally, follow these steps:

1. Clone the repository.
   
   ```bash
   git clone https://github.com/yourusername/sales-summary.git
   cd sales-summary
   ```

2. Open the `index.html` file in your web browser.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.