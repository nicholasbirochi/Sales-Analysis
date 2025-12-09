# Sales Data Analysis with Pandas (Notebook)

A Python notebook project focused on exploring, cleaning, and analyzing sales data using **Pandas** and **NumPy**. The workflow includes basic EDA, feature engineering (total revenue), missing data handling, aggregations by product/month/category, and dataset merging.

## What this project does

- Loads sales data from `vendas.csv`
- Performs quick EDA:
  - `head()`, `tail()`, `info()`, `describe()`
- Creates a new metric:
  - `Receita_Total = Quantidade * Preco_Unitario`
- Filters and selects data using:
  - boolean filters, `loc`, `iloc`, `filter`, `query`
- Simulates missing values (NaN) for practice
- Handles missing data:
  - fills `Quantidade` with mean
  - drops rows with missing `Preco_Unitario`
- Aggregates sales:
  - by product (total quantity and total revenue)
  - identifies most sold product and highest revenue product
- Loads product metadata from `produtos.csv`
- Merges sales + products to analyze:
  - revenue by category
- Converts date fields and analyzes:
  - revenue by month

## Tech Stack

- Python 3.x
- Pandas
- NumPy
- Jupyter Notebook / Google Colab / VS Code Notebook

## Dataset requirements

Place the following files in the expected paths:

- `vendas.csv` (sales transactions)
- `produtos.csv` (product catalog with categories)

Expected columns in `vendas.csv`:
- `ID_Venda`
- `Produto`
- `Quantidade`
- `Preco_Unitario`
- `Data_Venda`

Expected columns in `produtos.csv`:
- `Produto`
- `Categoria`
(You may have extra columns — they will be kept after the merge.)

## How to run

### Option 1 — Google Colab
1. Upload the notebook to Colab
2. Upload the CSV files to the runtime (or mount Google Drive)
3. Update paths if needed:
   - `df_vendas = pd.read_csv("/content/vendas.csv")`
   - `df_produtos = pd.read_csv("content/produtos.csv")`  (note: may need `/content/produtos.csv`)
4. Run the cells from top to bottom

### Option 2 — Local (Jupyter / VS Code)
1. Create and activate a virtual environment (optional)
2. Install dependencies:
   pip install pandas numpy
3. Ensure the CSV files are in the correct folders (or adjust `read_csv` paths)
4. Open the notebook and run all cells

## Outputs / Key results you’ll get

- Total sales revenue (sum of `Receita_Total`)
- Average unit price (`Preco_Unitario` mean)
- Min/max quantity sold
- Table of sales by product:
  - `Quantidade_total`, `Receita_Total`
- The most sold product (by quantity)
- The product with the highest revenue
- Revenue by month
- Revenue by category (after merging with products)

## Notes about file paths

The notebook uses:
- `/content/vendas.csv`
- `content/produtos.csv`

Depending on your environment, you may need to change the second one to:
- `/content/produtos.csv`

## Next improvements (ideas)

- Add visualizations (matplotlib/plotly): revenue by month, revenue by category, top products
- Validate data types and enforce schema checks
- Treat outliers (quantity/price) and invalid records
- Export summary tables to CSV/Excel
- Turn the notebook into a reusable pipeline (functions + parameters)

## License
This project is under the MIT license. See the LICENSE file for more details.

---
Made with ♥ by Rocketseat
